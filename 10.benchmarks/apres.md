# Letterflop — Rapport de benchmark API

> Généré le 27/05/2026 à 12:42:11
> Outil : `This is ApacheBench, Version 2.3 <$Revision: 1913912 $>`
> Paramètres : **100 requêtes**, concurrence **10** | Hôte : `http://localhost:8080`

---

## Table des matières

- [GET /api/logs](#get-apilogs)
- [GET /api/logs?size=1000 — la mauvaise pratique](#get-apilogssize1000--la-mauvaise-pratique)
- [GET /api/logs/movie/{tmdbId}](#get-apilogsmovietmdbid)
- [GET /api/movies/search](#get-apimoviesearch)
- [GET /api/movies/{tmdbId}](#get-apimovietmdbid)
- [POST /api/logs](#post-apilogs)
- [PUT /api/logs/{id}](#put-apilogsid)

---

## GET /api/logs

**URL** : `http://localhost:8080/api/logs?page=0&size=20`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 140.35 req/s            |
| Temps moyen / requête     | 71.248 ms         |
| Débit                     | 1037.99 KB/s        |
| Latence p50               | 67 ms               |
| Latence p95               | 112 ms               |
| Latence p99               | 168 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/logs?page=0&size=20
Document Length:        7379 bytes

Concurrency Level:      10
Time taken for tests:   0.712 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      757300 bytes
HTML transferred:       737900 bytes
Requests per second:    140.35 [#/sec] (mean)
Time per request:       71.248 [ms] (mean)
Time per request:       7.125 [ms] (mean, across all concurrent requests)
Transfer rate:          1037.99 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.2      0       2
Processing:    21   68  27.0     66     168
Waiting:       20   62  25.4     60     167
Total:         21   68  27.0     67     168

Percentage of the requests served within a certain time (ms)
  50%     67
  66%     80
  75%     87
  80%     90
  90%    100
  95%    112
  98%    131
  99%    168
 100%    168 (longest request)
```

</details>

---

## GET /api/logs?size=1000 — la mauvaise pratique

**URL** : `http://localhost:8080/api/logs?page=0&size=1000`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 75.95 req/s            |
| Temps moyen / requête     | 131.670 ms         |
| Débit                     | 9173.12 KB/s        |
| Latence p50               | 118 ms               |
| Latence p95               | 210 ms               |
| Latence p99               | 227 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/logs?page=0&size=1000
Document Length:        123487 bytes

Concurrency Level:      10
Time taken for tests:   1.317 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      12368100 bytes
HTML transferred:       12348700 bytes
Requests per second:    75.95 [#/sec] (mean)
Time per request:       131.670 [ms] (mean)
Time per request:       13.167 [ms] (mean, across all concurrent requests)
Transfer rate:          9173.12 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:    50  123  40.5    118     227
Waiting:       24   74  29.0     70     148
Total:         51  123  40.5    118     227

Percentage of the requests served within a certain time (ms)
  50%    118
  66%    137
  75%    145
  80%    155
  90%    192
  95%    210
  98%    227
  99%    227
 100%    227 (longest request)
```

</details>

---

## GET /api/logs/movie/{tmdbId}

**URL** : `http://localhost:8080/api/logs/movie/27205`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 245.95 req/s            |
| Temps moyen / requête     | 40.659 ms         |
| Débit                     | 925.67 KB/s        |
| Latence p50               | 34 ms               |
| Latence p95               | 61 ms               |
| Latence p99               | 72 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/logs/movie/27205
Document Length:        3660 bytes

Concurrency Level:      10
Time taken for tests:   0.407 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      385400 bytes
HTML transferred:       366000 bytes
Requests per second:    245.95 [#/sec] (mean)
Time per request:       40.659 [ms] (mean)
Time per request:       4.066 [ms] (mean, across all concurrent requests)
Transfer rate:          925.67 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.2      0       1
Processing:     8   33  15.6     33      72
Waiting:        8   29  13.4     27      66
Total:          9   34  15.6     34      72

Percentage of the requests served within a certain time (ms)
  50%     34
  66%     40
  75%     45
  80%     48
  90%     58
  95%     61
  98%     70
  99%     72
 100%     72 (longest request)
```

</details>

---

## GET /api/movies/search

**URL** : `http://localhost:8080/api/movies/search?query=inception`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 28.80 req/s            |
| Temps moyen / requête     | 347.278 ms         |
| Débit                     | 8.77 KB/s        |
| Latence p50               | 245 ms               |
| Latence p95               | 323 ms               |
| Latence p99               | 921 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/movies/search?query=inception
Document Length:        118 bytes

Concurrency Level:      10
Time taken for tests:   3.473 seconds
Complete requests:      100
Failed requests:        0
Non-2xx responses:      100
Total transferred:      31200 bytes
HTML transferred:       11800 bytes
Requests per second:    28.80 [#/sec] (mean)
Time per request:       347.278 [ms] (mean)
Time per request:       34.728 [ms] (mean, across all concurrent requests)
Transfer rate:          8.77 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:   120  257  79.4    245     921
Waiting:      120  256  79.1    242     920
Total:        121  257  79.4    245     921

Percentage of the requests served within a certain time (ms)
  50%    245
  66%    264
  75%    290
  80%    294
  90%    311
  95%    323
  98%    367
  99%    921
 100%    921 (longest request)
```

</details>

---

## GET /api/movies/{tmdbId}

**URL** : `http://localhost:8080/api/movies/27205`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 38.24 req/s            |
| Temps moyen / requête     | 261.529 ms         |
| Débit                     | 11.61 KB/s        |
| Latence p50               | 238 ms               |
| Latence p95               | 304 ms               |
| Latence p99               | 329 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/movies/27205
Document Length:        117 bytes

Concurrency Level:      10
Time taken for tests:   2.615 seconds
Complete requests:      100
Failed requests:        0
Non-2xx responses:      100
Total transferred:      31100 bytes
HTML transferred:       11700 bytes
Requests per second:    38.24 [#/sec] (mean)
Time per request:       261.529 [ms] (mean)
Time per request:       26.153 [ms] (mean, across all concurrent requests)
Transfer rate:          11.61 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:   125  242  41.1    237     329
Waiting:      122  241  41.3    236     328
Total:        125  242  41.1    238     329

Percentage of the requests served within a certain time (ms)
  50%    238
  66%    265
  75%    272
  80%    280
  90%    292
  95%    304
  98%    328
  99%    329
 100%    329 (longest request)
```

</details>

---

## POST /api/logs

**URL** : `http://localhost:8080/api/logs`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 8               |
| Requêtes / seconde        | 245.44 req/s            |
| Temps moyen / requête     | 40.743 ms         |
| Débit                     | 117.42 KB/s        |
| Latence p50               | 36 ms               |
| Latence p95               | 68 ms               |
| Latence p99               | 132 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/logs
Document Length:        296 bytes

Concurrency Level:      10
Time taken for tests:   0.407 seconds
Complete requests:      100
Failed requests:        8
   (Connect: 0, Receive: 0, Length: 8, Exceptions: 0)
Total transferred:      48990 bytes
Total body sent:        42700
HTML transferred:       29590 bytes
Requests per second:    245.44 [#/sec] (mean)
Time per request:       40.743 [ms] (mean)
Time per request:       4.074 [ms] (mean, across all concurrent requests)
Transfer rate:          117.42 [Kbytes/sec] received
                        102.35 kb/s sent
                        219.77 kb/s total

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:    10   38  17.6     36     132
Waiting:       10   35  17.2     34     130
Total:         11   38  17.6     36     132

Percentage of the requests served within a certain time (ms)
  50%     36
  66%     41
  75%     46
  80%     49
  90%     57
  95%     68
  98%     90
  99%    132
 100%    132 (longest request)
```

</details>

---

## PUT /api/logs/{id}

**URL** : `http://localhost:8080/api/logs/332`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 250.26 req/s            |
| Temps moyen / requête     | 39.958 ms         |
| Débit                     | 120.49 KB/s        |
| Latence p50               | 30 ms               |
| Latence p95               | 65 ms               |
| Latence p99               | 94 ms               |

<details>
<summary>Sortie brute ab</summary>

```
This is ApacheBench, Version 2.3 <$Revision: 1913912 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient).....done


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /api/logs/332
Document Length:        299 bytes

Concurrency Level:      10
Time taken for tests:   0.400 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      49300 bytes
Total body sent:        24000
HTML transferred:       29900 bytes
Requests per second:    250.26 [#/sec] (mean)
Time per request:       39.958 [ms] (mean)
Time per request:       3.996 [ms] (mean, across all concurrent requests)
Transfer rate:          120.49 [Kbytes/sec] received
                        58.66 kb/s sent
                        179.14 kb/s total

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:     9   33  17.8     30      94
Waiting:        8   29  16.2     27      93
Total:          9   33  17.8     30      94

Percentage of the requests served within a certain time (ms)
  50%     30
  66%     41
  75%     44
  80%     48
  90%     58
  95%     65
  98%     85
  99%     94
 100%     94 (longest request)
```

</details>

---
