## Script de conversion d'images

```bash
#!/usr/bin/env bash
# convert_to_webp.sh
# Convertit tous les PNG/JPEG d'un répertoire en WebP.
# Usage : ./convert_to_webp.sh [répertoire] [qualité]
# Exemple : ./convert_to_webp.sh ./img 82

set -euo pipefail

DIR="${1:-.}"
QUALITY="${2:-82}"
CONVERTED=0
SKIPPED=0
ERRORS=0

if ! command -v magick &>/dev/null; then
  echo "❌  ImageMagick introuvable. Installez-le avec :"
  echo "    macOS  → brew install imagemagick"
  echo "    Ubuntu → sudo apt install imagemagick"
  exit 1
fi

echo "📁  Répertoire : $DIR"
echo "🎚️   Qualité    : $QUALITY"
echo "─────────────────────────────────────"

while IFS= read -r -d '' file; do
  out="${file%.*}.webp"

  if [[ -f "$out" ]]; then
    echo "⏭️   Déjà converti : $(basename "$file")"
    ((SKIPPED++))
    continue
  fi

  if magick "$file" -quality "$QUALITY" "$out" 2>/dev/null; then
    original_size=$(du -k "$file"  | cut -f1)
    webp_size=$(du -k "$out" | cut -f1)
    gain=$(( (original_size - webp_size) * 100 / (original_size + 1) ))
    echo "✅  $(basename "$file") → $(basename "$out")  (${original_size}K → ${webp_size}K, −${gain}%)"
    ((CONVERTED++))
  else
    echo "⚠️   Échec : $(basename "$file")"
    ((ERRORS++))
  fi

done < <(find "$DIR" -maxdepth 1 \( -iname "*.png" -o -iname "*.jpg" -o -iname "*.jpeg" \) -print0 | sort -z)

echo "─────────────────────────────────────"
echo "✔  Convertis : $CONVERTED  |  ⏭  Existants : $SKIPPED  |  ⚠  Erreurs : $ERRORS"
```