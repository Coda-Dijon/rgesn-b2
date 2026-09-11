# Benchmarks - Avant / Après RGESN

> **Outil** : ApacheBench 2.3 - 100 requêtes, concurrence 10, hôte `http://localhost:8080`  
> **Avant** : letter-flop tel que livré (violations intactes)  
> **Après** : corrections RGESN appliquées (pagination Pageable, index, posterPath)

## Vue d'ensemble

| Endpoint                        | Avant req/s | Après req/s | Δ throughput | Avant p50 | Après p50 | Δ latence p50 |
|---------------------------------|:-----------:|:-----------:|:------------:|:---------:|:---------:|:-------------:|
| `GET /api/logs?size=20`         | 79          | 140         | **+77 %**    | 122 ms    | 67 ms     | **−45 %**     |
| `GET /api/logs?size=1000`       | 70          | 76          | +8 %         | 137 ms    | 118 ms    | −14 %         |
| `GET /api/logs/movie/{tmdbId}`  | 274         | 246         | −10 %        | 32 ms     | 34 ms     | ~stable       |
| `POST /api/logs`                | 193         | 245         | **+27 %**    | 49 ms     | 36 ms     | −27 %         |
| `PUT /api/logs/{id}`            | 183         | 250         | **+37 %**    | 45 ms     | 30 ms     | −33 %         |

En résumé :

| Correction RGESN              | Impact mesuré                                      |
|-------------------------------|---------------------------------------------------|
| Pageable (7.1a)               | +77 % throughput / −45 % latence p50 sur `/logs`  |
| Index watched_at (7.1a)       | Contribue au gain Pageable (non isolable)          |
| size=20 vs size=1000 (6.5/7.1)| −94 % données transférées (123 KB → 7.4 KB)       |
| Simplification service (7.1b) | +27–37 % throughput sur POST/PUT                   |

> Les gains sur `/logs` sont **conservateurs** : ils ont été mesurés sur une table de ~330 entrées. Avec des millions de lignes, l'écart entre O(n) et O(log n) est un ordre de grandeur, pas 2×.
