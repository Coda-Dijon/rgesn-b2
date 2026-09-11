# Letterflop — Rapport de benchmark API

> Généré le 27/05/2026 à 12:34:59
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
| Requêtes / seconde        | 79.42 req/s            |
| Temps moyen / requête     | 125.915 ms         |
| Débit                     | 593.24 KB/s        |
| Latence p50               | 122 ms               |
| Latence p95               | 187 ms               |
| Latence p99               | 233 ms               |

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
Document Length:        7455 bytes

Concurrency Level:      10
Time taken for tests:   1.259 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      764900 bytes
HTML transferred:       745500 bytes
Requests per second:    79.42 [#/sec] (mean)
Time per request:       125.915 [ms] (mean)
Time per request:       12.591 [ms] (mean, across all concurrent requests)
Transfer rate:          593.24 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:    38  120  38.2    122     232
Waiting:       38  114  36.3    115     206
Total:         39  120  38.2    122     233

Percentage of the requests served within a certain time (ms)
  50%    122
  66%    140
  75%    144
  80%    149
  90%    162
  95%    187
  98%    218
  99%    233
 100%    233 (longest request)
```

</details>

---

## GET /api/logs?size=1000 — la mauvaise pratique

**URL** : `http://localhost:8080/api/logs?page=0&size=1000`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 70.37 req/s            |
| Temps moyen / requête     | 142.114 ms         |
| Débit                     | 8589.97 KB/s        |
| Latence p50               | 137 ms               |
| Latence p95               | 206 ms               |
| Latence p99               | 255 ms               |

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
Document Length:        124811 bytes

Concurrency Level:      10
Time taken for tests:   1.421 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      12500500 bytes
HTML transferred:       12481100 bytes
Requests per second:    70.37 [#/sec] (mean)
Time per request:       142.114 [ms] (mean)
Time per request:       14.211 [ms] (mean, across all concurrent requests)
Transfer rate:          8589.97 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       0
Processing:    66  136  38.7    137     255
Waiting:       29   94  31.0     92     166
Total:         66  136  38.7    137     255

Percentage of the requests served within a certain time (ms)
  50%    137
  66%    150
  75%    159
  80%    163
  90%    191
  95%    206
  98%    227
  99%    255
 100%    255 (longest request)
```

</details>

---

## GET /api/logs/movie/{tmdbId}

**URL** : `http://localhost:8080/api/logs/movie/27205`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 273.78 req/s            |
| Temps moyen / requête     | 36.526 ms         |
| Débit                     | 1040.03 KB/s        |
| Latence p50               | 32 ms               |
| Latence p95               | 59 ms               |
| Latence p99               | 97 ms               |

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
Document Length:        3696 bytes

Concurrency Level:      10
Time taken for tests:   0.365 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      389000 bytes
HTML transferred:       369600 bytes
Requests per second:    273.78 [#/sec] (mean)
Time per request:       36.526 [ms] (mean)
Time per request:       3.653 [ms] (mean, across all concurrent requests)
Transfer rate:          1040.03 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       0
Processing:     9   33  14.7     32      97
Waiting:        8   28  11.1     28      56
Total:          9   33  14.7     32      97

Percentage of the requests served within a certain time (ms)
  50%     32
  66%     37
  75%     40
  80%     44
  90%     53
  95%     59
  98%     75
  99%     97
 100%     97 (longest request)
```

</details>

---

## GET /api/movies/search

**URL** : `http://localhost:8080/api/movies/search?query=inception`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 7.76 req/s            |
| Temps moyen / requête     | 1288.465 ms         |
| Débit                     | 35.63 KB/s        |
| Latence p50               | 919 ms               |
| Latence p95               | 2241 ms               |
| Latence p99               | 3093 ms               |

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
Document Length:        4507 bytes

Concurrency Level:      10
Time taken for tests:   12.885 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      470100 bytes
HTML transferred:       450700 bytes
Requests per second:    7.76 [#/sec] (mean)
Time per request:       1288.465 [ms] (mean)
Time per request:       128.846 [ms] (mean, across all concurrent requests)
Transfer rate:          35.63 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       1
Processing:   519 1066 578.4    919    3093
Waiting:      518 1065 578.4    918    3092
Total:        519 1066 578.4    919    3093

Percentage of the requests served within a certain time (ms)
  50%    919
  66%   1220
  75%   1415
  80%   1561
  90%   1923
  95%   2241
  98%   2821
  99%   3093
 100%   3093 (longest request)
```

</details>

---

## GET /api/movies/{tmdbId}

**URL** : `http://localhost:8080/api/movies/27205`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 29.50 req/s            |
| Temps moyen / requête     | 338.991 ms         |
| Débit                     | 29.30 KB/s        |
| Latence p50               | 136 ms               |
| Latence p95               | 1131 ms               |
| Latence p99               | 1667 ms               |

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
Document Length:        823 bytes

Concurrency Level:      10
Time taken for tests:   3.390 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      101700 bytes
HTML transferred:       82300 bytes
Requests per second:    29.50 [#/sec] (mean)
Time per request:       338.991 [ms] (mean)
Time per request:       33.899 [ms] (mean, across all concurrent requests)
Transfer rate:          29.30 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.1      0       0
Processing:   121  290 329.8    136    1667
Waiting:      120  289 329.8    135    1666
Total:        121  290 329.8    136    1667

Percentage of the requests served within a certain time (ms)
  50%    136
  66%    148
  75%    217
  80%    396
  90%    856
  95%   1131
  98%   1401
  99%   1667
 100%   1667 (longest request)
```

</details>

---

## POST /api/logs

**URL** : `http://localhost:8080/api/logs`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 6               |
| Requêtes / seconde        | 193.34 req/s            |
| Temps moyen / requête     | 51.723 ms         |
| Débit                     | 92.50 KB/s        |
| Latence p50               | 49 ms               |
| Latence p95               | 83 ms               |
| Latence p99               | 113 ms               |

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
Time taken for tests:   0.517 seconds
Complete requests:      100
Failed requests:        6
   (Connect: 0, Receive: 0, Length: 6, Exceptions: 0)
Total transferred:      48994 bytes
Total body sent:        42700
HTML transferred:       29594 bytes
Requests per second:    193.34 [#/sec] (mean)
Time per request:       51.723 [ms] (mean)
Time per request:       5.172 [ms] (mean, across all concurrent requests)
Transfer rate:          92.50 [Kbytes/sec] received
                        80.62 kb/s sent
                        173.12 kb/s total

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.2      0       1
Processing:    16   48  18.8     49     112
Waiting:       15   43  17.1     44     103
Total:         16   48  18.8     49     113

Percentage of the requests served within a certain time (ms)
  50%     49
  66%     55
  75%     59
  80%     65
  90%     75
  95%     83
  98%     88
  99%    113
 100%    113 (longest request)
```

</details>

---

## PUT /api/logs/{id}

**URL** : `http://localhost:8080/api/logs/332`

| Métrique                  | Valeur                       |
|---------------------------|------------------------------|
| Requêtes complètes        | 100             |
| Requêtes échouées         | 0               |
| Requêtes / seconde        | 183.04 req/s            |
| Temps moyen / requête     | 54.632 ms         |
| Débit                     | 88.12 KB/s        |
| Latence p50               | 45 ms               |
| Latence p95               | 68 ms               |
| Latence p99               | 99 ms               |

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
Time taken for tests:   0.546 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      49300 bytes
Total body sent:        24000
HTML transferred:       29900 bytes
Requests per second:    183.04 [#/sec] (mean)
Time per request:       54.632 [ms] (mean)
Time per request:       5.463 [ms] (mean, across all concurrent requests)
Transfer rate:          88.12 [Kbytes/sec] received
                        42.90 kb/s sent
                        131.03 kb/s total

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.2      0       1
Processing:    14   47  14.1     45      98
Waiting:       13   41  13.1     40      93
Total:         14   47  14.1     45      99

Percentage of the requests served within a certain time (ms)
  50%     45
  66%     54
  75%     58
  80%     60
  90%     64
  95%     68
  98%     75
  99%     99
 100%     99 (longest request)
```

</details>

---
