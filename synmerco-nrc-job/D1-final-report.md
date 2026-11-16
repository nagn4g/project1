# US nuclear fleet power watch from the NRC daily status file

Seller DID: did:pkh:eip155:8453:0xDD740093893AA5Bb9659a34cAA774064605CAFb2
Escrow: esc_43082e54fd834fa69956aa73. Buyer: Fieldnote Docs. Awarded 2026-11-14 14:06:47 UTC.
Amount $5.00, net to seller $4.84. Deliver by 2026-11-18 22:06:47 UTC.
Source: NRC power reactor status file, host www.nrc.gov, no login, no key.
Three timed pulls, each at least 24 hours after the previous progress note.

## Answers (one per ACCEPTANCE line, in order)

1. The three CSV files are attached as data files under Rule 25 (see synmerco-data block):
   nrc-fleet-pull1.csv, nrc-fleet-pull2.csv, nrc-fleet-pull3.csv — each 95 rows,
   columns unit, latest date, power, power 7 days before, power 30 days before,
   days below 100 in last 30, days at 0 in file, state, state since; key column unit;
   one row per unit with a line on the latest date; sorted by unit.
2. Each CSV's latest-date power values match that pull's PROOF lines (verified row by row;
   see PROOF, one line per unit per pull, copied exactly as the source returned them).
3. States, state-since dates, day counts and the fleet table follow the TASK and agree
   with the CSVs (see Fleet table and Offline / Reduced lists below; all three pulls agree).
4. The platform record (GET /v1/escrows/esc_43082e54fd834fa69956aa73/progress) shows PULL 1:
   recorded 2026-11-14 14:22:00 UTC, PULL 2: 2026-11-15 14:27:52 UTC (24h 05m 52s later),
   PULL 3: 2026-11-16 14:30:13 UTC (24h 02m 21s later), each with its CSV row count and
   SHA-256. Each pull's first-request HTTP Date is later than the previous pull's
   (14:21:18 GMT, then 14:27:48 GMT, then 14:30:10 GMT). Change counts agree with the CSVs.

## Fleet table (latest date 2026-11-13; identical in all three pulls)

| measure | value |
|---|---|
| units reported | 95 |
| full (100) | 77 (81.05%) |
| reduced (1-99) | 4 (4.21%) |
| offline (0) | 14 (14.74%) |
| mean power | 83.34 |

## Offline units (14) — state since and days offline in that run

| unit | state since | days offline in run |
|---|---|---|
| Comanche Peak 1 | 2026-10-19 | 26 |
| Cooper | 2026-11-10 | 4 |
| Dresden 3 | 2026-10-26 | 19 |
| Millstone 3 | 2026-10-12 | 33 |
| North Anna 2 | 2026-09-06 | 69 |
| Oconee 1 | 2026-10-31 | 14 |
| Palisades | 2025-11-16 | 363 |
| Palo Verde 1 | 2026-10-03 | 42 |
| Point Beach 1 | 2026-11-11 | 3 |
| Prairie Island 1 | 2026-10-03 | 42 |
| Salem 1 | 2026-10-04 | 41 |
| Summer | 2026-11-08 | 6 |
| Waterford 3 | 2026-10-17 | 28 |
| Watts Bar 2 | 2026-11-07 | 7 |

## Reduced units (4) — power on 2026-11-13

| unit | power | state since |
|---|---|---|
| Byron 1 | 94 | 2026-11-05 |
| Farley 2 | 14 | 2026-11-13 |
| Point Beach 2 | 49 | 2026-11-13 |
| Robinson 2 | 60 | 2026-11-12 |

## PROOF — PULL 1

- Request: GET https://www.nrc.gov/reading-rm/doc-collections/event-status/reactor-status/powerreactorstatusforlast365days.txt
  (old path; the server answers 301 Moved Permanently to the new location, same file:
  GET https://www.nrc.gov/documents-reports/document-collections/events-reports-associated-with/power-reactor-status-reports/PowerReactorStatusForLast365Days.txt)
- Retrieved (UTC): 2026-11-14 14:21:19 UTC
- Progress note recorded: 2026-11-14 14:22:00 UTC (server time)
- File first line: ReportDt|Unit|Power
- Number of lines in file: 34676 (header + 34675 data lines)
- Latest date in file: 2026-11-13
- HTTP Date header of first request (301 response): Sat, 14 Nov 2026 14:21:18 GMT
- HTTP Date header of final response (200 OK): Sat, 14 Nov 2026 14:21:19 GMT
- CSV: nrc-fleet-pull1.csv, rows 95, sha256 b5d60d623f4d86fb18d02be8cefd21d32335b824844761e43e7aef268b8798fa
- Every line of the latest date (2026-11-13) as returned, one per line
  (the file's first line heads the block, then the latest-date lines):

```
ReportDt|Unit|Power
11/13/2026 12:00:00 AM|Arkansas Nuclear 1|100
11/13/2026 12:00:00 AM|Arkansas Nuclear 2|100
11/13/2026 12:00:00 AM|Beaver Valley 1|100
11/13/2026 12:00:00 AM|Beaver Valley 2|100
11/13/2026 12:00:00 AM|Braidwood 1|100
11/13/2026 12:00:00 AM|Braidwood 2|100
11/13/2026 12:00:00 AM|Browns Ferry 1|100
11/13/2026 12:00:00 AM|Browns Ferry 2|100
11/13/2026 12:00:00 AM|Browns Ferry 3|100
11/13/2026 12:00:00 AM|Brunswick 1|100
11/13/2026 12:00:00 AM|Brunswick 2|100
11/13/2026 12:00:00 AM|Byron 1|94
11/13/2026 12:00:00 AM|Byron 2|100
11/13/2026 12:00:00 AM|Callaway|100
11/13/2026 12:00:00 AM|Calvert Cliffs 1|100
11/13/2026 12:00:00 AM|Calvert Cliffs 2|100
11/13/2026 12:00:00 AM|Catawba 1|100
11/13/2026 12:00:00 AM|Catawba 2|100
11/13/2026 12:00:00 AM|Clinton|100
11/13/2026 12:00:00 AM|Columbia Generating Station|100
11/13/2026 12:00:00 AM|Comanche Peak 1|0
11/13/2026 12:00:00 AM|Comanche Peak 2|100
11/13/2026 12:00:00 AM|Cooper|0
11/13/2026 12:00:00 AM|D.C. Cook 1|100
11/13/2026 12:00:00 AM|D.C. Cook 2|100
11/13/2026 12:00:00 AM|Davis-Besse|100
11/13/2026 12:00:00 AM|Diablo Canyon 1|100
11/13/2026 12:00:00 AM|Diablo Canyon 2|100
11/13/2026 12:00:00 AM|Dresden 2|100
11/13/2026 12:00:00 AM|Dresden 3|0
11/13/2026 12:00:00 AM|Farley 1|100
11/13/2026 12:00:00 AM|Farley 2|14
11/13/2026 12:00:00 AM|Fermi 2|100
11/13/2026 12:00:00 AM|FitzPatrick|100
11/13/2026 12:00:00 AM|Ginna|100
11/13/2026 12:00:00 AM|Grand Gulf 1|100
11/13/2026 12:00:00 AM|Harris 1|100
11/13/2026 12:00:00 AM|Hatch 1|100
11/13/2026 12:00:00 AM|Hatch 2|100
11/13/2026 12:00:00 AM|Hope Creek 1|100
11/13/2026 12:00:00 AM|LaSalle 1|100
11/13/2026 12:00:00 AM|LaSalle 2|100
11/13/2026 12:00:00 AM|Limerick 1|100
11/13/2026 12:00:00 AM|Limerick 2|100
11/13/2026 12:00:00 AM|McGuire 1|100
11/13/2026 12:00:00 AM|McGuire 2|100
11/13/2026 12:00:00 AM|Millstone 2|100
11/13/2026 12:00:00 AM|Millstone 3|0
11/13/2026 12:00:00 AM|Monticello|100
11/13/2026 12:00:00 AM|Nine Mile Point 1|100
11/13/2026 12:00:00 AM|Nine Mile Point 2|100
11/13/2026 12:00:00 AM|North Anna 1|100
11/13/2026 12:00:00 AM|North Anna 2|0
11/13/2026 12:00:00 AM|Oconee 1|0
11/13/2026 12:00:00 AM|Oconee 2|100
11/13/2026 12:00:00 AM|Oconee 3|100
11/13/2026 12:00:00 AM|Palisades|0
11/13/2026 12:00:00 AM|Palo Verde 1|0
11/13/2026 12:00:00 AM|Palo Verde 2|100
11/13/2026 12:00:00 AM|Palo Verde 3|100
11/13/2026 12:00:00 AM|Peach Bottom 2|100
11/13/2026 12:00:00 AM|Peach Bottom 3|100
11/13/2026 12:00:00 AM|Perry 1|100
11/13/2026 12:00:00 AM|Point Beach 1|0
11/13/2026 12:00:00 AM|Point Beach 2|49
11/13/2026 12:00:00 AM|Prairie Island 1|0
11/13/2026 12:00:00 AM|Prairie Island 2|100
11/13/2026 12:00:00 AM|Quad Cities 1|100
11/13/2026 12:00:00 AM|Quad Cities 2|100
11/13/2026 12:00:00 AM|River Bend Station 1|100
11/13/2026 12:00:00 AM|Robinson 2|60
11/13/2026 12:00:00 AM|Saint Lucie 1|100
11/13/2026 12:00:00 AM|Saint Lucie 2|100
11/13/2026 12:00:00 AM|Salem 1|0
11/13/2026 12:00:00 AM|Salem 2|100
11/13/2026 12:00:00 AM|Seabrook 1|100
11/13/2026 12:00:00 AM|Sequoyah 1|100
11/13/2026 12:00:00 AM|Sequoyah 2|100
11/13/2026 12:00:00 AM|South Texas 1|100
11/13/2026 12:00:00 AM|South Texas 2|100
11/13/2026 12:00:00 AM|Summer|0
11/13/2026 12:00:00 AM|Surry 1|100
11/13/2026 12:00:00 AM|Surry 2|100
11/13/2026 12:00:00 AM|Susquehanna 1|100
11/13/2026 12:00:00 AM|Susquehanna 2|100
11/13/2026 12:00:00 AM|Turkey Point 3|100
11/13/2026 12:00:00 AM|Turkey Point 4|100
11/13/2026 12:00:00 AM|Vogtle 1|100
11/13/2026 12:00:00 AM|Vogtle 2|100
11/13/2026 12:00:00 AM|Vogtle 3|100
11/13/2026 12:00:00 AM|Vogtle 4|100
11/13/2026 12:00:00 AM|Waterford 3|0
11/13/2026 12:00:00 AM|Watts Bar 1|100
11/13/2026 12:00:00 AM|Watts Bar 2|0
11/13/2026 12:00:00 AM|Wolf Creek 1|100
```

## PROOF — PULL 2

- Request: GET https://www.nrc.gov/reading-rm/doc-collections/event-status/reactor-status/powerreactorstatusforlast365days.txt
  (old path; the server answers 301 Moved Permanently to the new location, same file:
  GET https://www.nrc.gov/documents-reports/document-collections/events-reports-associated-with/power-reactor-status-reports/PowerReactorStatusForLast365Days.txt)
- Retrieved (UTC): 2026-11-15 14:27:50 UTC
- Progress note recorded: 2026-11-15 14:27:52 UTC (server time)
- File first line: ReportDt|Unit|Power
- Number of lines in file: 34581 (header + 34580 data lines)
- Latest date in file: 2026-11-13
- HTTP Date header of first request (301 response): Sun, 15 Nov 2026 14:27:48 GMT
- HTTP Date header of final response (200 OK): Sun, 15 Nov 2026 14:27:50 GMT
- CSV: nrc-fleet-pull2.csv, rows 95, sha256 3809c367348bffc1d6ebf40d88189d94818fe12477996528ae880e2f108557fe
- Every line of the latest date (2026-11-13) as returned, one per line
  (the file's first line heads the block, then the latest-date lines):

```
ReportDt|Unit|Power
11/13/2026 12:00:00 AM|Arkansas Nuclear 1|100
11/13/2026 12:00:00 AM|Arkansas Nuclear 2|100
11/13/2026 12:00:00 AM|Beaver Valley 1|100
11/13/2026 12:00:00 AM|Beaver Valley 2|100
11/13/2026 12:00:00 AM|Braidwood 1|100
11/13/2026 12:00:00 AM|Braidwood 2|100
11/13/2026 12:00:00 AM|Browns Ferry 1|100
11/13/2026 12:00:00 AM|Browns Ferry 2|100
11/13/2026 12:00:00 AM|Browns Ferry 3|100
11/13/2026 12:00:00 AM|Brunswick 1|100
11/13/2026 12:00:00 AM|Brunswick 2|100
11/13/2026 12:00:00 AM|Byron 1|94
11/13/2026 12:00:00 AM|Byron 2|100
11/13/2026 12:00:00 AM|Callaway|100
11/13/2026 12:00:00 AM|Calvert Cliffs 1|100
11/13/2026 12:00:00 AM|Calvert Cliffs 2|100
11/13/2026 12:00:00 AM|Catawba 1|100
11/13/2026 12:00:00 AM|Catawba 2|100
11/13/2026 12:00:00 AM|Clinton|100
11/13/2026 12:00:00 AM|Columbia Generating Station|100
11/13/2026 12:00:00 AM|Comanche Peak 1|0
11/13/2026 12:00:00 AM|Comanche Peak 2|100
11/13/2026 12:00:00 AM|Cooper|0
11/13/2026 12:00:00 AM|D.C. Cook 1|100
11/13/2026 12:00:00 AM|D.C. Cook 2|100
11/13/2026 12:00:00 AM|Davis-Besse|100
11/13/2026 12:00:00 AM|Diablo Canyon 1|100
11/13/2026 12:00:00 AM|Diablo Canyon 2|100
11/13/2026 12:00:00 AM|Dresden 2|100
11/13/2026 12:00:00 AM|Dresden 3|0
11/13/2026 12:00:00 AM|Farley 1|100
11/13/2026 12:00:00 AM|Farley 2|14
11/13/2026 12:00:00 AM|Fermi 2|100
11/13/2026 12:00:00 AM|FitzPatrick|100
11/13/2026 12:00:00 AM|Ginna|100
11/13/2026 12:00:00 AM|Grand Gulf 1|100
11/13/2026 12:00:00 AM|Harris 1|100
11/13/2026 12:00:00 AM|Hatch 1|100
11/13/2026 12:00:00 AM|Hatch 2|100
11/13/2026 12:00:00 AM|Hope Creek 1|100
11/13/2026 12:00:00 AM|LaSalle 1|100
11/13/2026 12:00:00 AM|LaSalle 2|100
11/13/2026 12:00:00 AM|Limerick 1|100
11/13/2026 12:00:00 AM|Limerick 2|100
11/13/2026 12:00:00 AM|McGuire 1|100
11/13/2026 12:00:00 AM|McGuire 2|100
11/13/2026 12:00:00 AM|Millstone 2|100
11/13/2026 12:00:00 AM|Millstone 3|0
11/13/2026 12:00:00 AM|Monticello|100
11/13/2026 12:00:00 AM|Nine Mile Point 1|100
11/13/2026 12:00:00 AM|Nine Mile Point 2|100
11/13/2026 12:00:00 AM|North Anna 1|100
11/13/2026 12:00:00 AM|North Anna 2|0
11/13/2026 12:00:00 AM|Oconee 1|0
11/13/2026 12:00:00 AM|Oconee 2|100
11/13/2026 12:00:00 AM|Oconee 3|100
11/13/2026 12:00:00 AM|Palisades|0
11/13/2026 12:00:00 AM|Palo Verde 1|0
11/13/2026 12:00:00 AM|Palo Verde 2|100
11/13/2026 12:00:00 AM|Palo Verde 3|100
11/13/2026 12:00:00 AM|Peach Bottom 2|100
11/13/2026 12:00:00 AM|Peach Bottom 3|100
11/13/2026 12:00:00 AM|Perry 1|100
11/13/2026 12:00:00 AM|Point Beach 1|0
11/13/2026 12:00:00 AM|Point Beach 2|49
11/13/2026 12:00:00 AM|Prairie Island 1|0
11/13/2026 12:00:00 AM|Prairie Island 2|100
11/13/2026 12:00:00 AM|Quad Cities 1|100
11/13/2026 12:00:00 AM|Quad Cities 2|100
11/13/2026 12:00:00 AM|River Bend Station 1|100
11/13/2026 12:00:00 AM|Robinson 2|60
11/13/2026 12:00:00 AM|Saint Lucie 1|100
11/13/2026 12:00:00 AM|Saint Lucie 2|100
11/13/2026 12:00:00 AM|Salem 1|0
11/13/2026 12:00:00 AM|Salem 2|100
11/13/2026 12:00:00 AM|Seabrook 1|100
11/13/2026 12:00:00 AM|Sequoyah 1|100
11/13/2026 12:00:00 AM|Sequoyah 2|100
11/13/2026 12:00:00 AM|South Texas 1|100
11/13/2026 12:00:00 AM|South Texas 2|100
11/13/2026 12:00:00 AM|Summer|0
11/13/2026 12:00:00 AM|Surry 1|100
11/13/2026 12:00:00 AM|Surry 2|100
11/13/2026 12:00:00 AM|Susquehanna 1|100
11/13/2026 12:00:00 AM|Susquehanna 2|100
11/13/2026 12:00:00 AM|Turkey Point 3|100
11/13/2026 12:00:00 AM|Turkey Point 4|100
11/13/2026 12:00:00 AM|Vogtle 1|100
11/13/2026 12:00:00 AM|Vogtle 2|100
11/13/2026 12:00:00 AM|Vogtle 3|100
11/13/2026 12:00:00 AM|Vogtle 4|100
11/13/2026 12:00:00 AM|Waterford 3|0
11/13/2026 12:00:00 AM|Watts Bar 1|100
11/13/2026 12:00:00 AM|Watts Bar 2|0
11/13/2026 12:00:00 AM|Wolf Creek 1|100
```

## PROOF — PULL 3

- Request: GET https://www.nrc.gov/reading-rm/doc-collections/event-status/reactor-status/powerreactorstatusforlast365days.txt
  (old path; the server answers 301 Moved Permanently to the new location, same file:
  GET https://www.nrc.gov/documents-reports/document-collections/events-reports-associated-with/power-reactor-status-reports/PowerReactorStatusForLast365Days.txt)
- Retrieved (UTC): 2026-11-16 14:30:11 UTC
- Progress note recorded: 2026-11-16 14:30:13 UTC (server time)
- File first line: ReportDt|Unit|Power
- Number of lines in file: 34486 (header + 34485 data lines)
- Latest date in file: 2026-11-13
- HTTP Date header of first request (301 response): Mon, 16 Nov 2026 14:30:10 GMT
- HTTP Date header of final response (200 OK): Mon, 16 Nov 2026 14:30:11 GMT
- CSV: nrc-fleet-pull3.csv, rows 95, sha256 cbab7b539e97d7b17efe56ebcb91f49a5b2434b7bc7170606eb2c21b70c3fded
- Every line of the latest date (2026-11-13) as returned, one per line
  (the file's first line heads the block, then the latest-date lines):

```
ReportDt|Unit|Power
11/13/2026 12:00:00 AM|Arkansas Nuclear 1|100
11/13/2026 12:00:00 AM|Arkansas Nuclear 2|100
11/13/2026 12:00:00 AM|Beaver Valley 1|100
11/13/2026 12:00:00 AM|Beaver Valley 2|100
11/13/2026 12:00:00 AM|Braidwood 1|100
11/13/2026 12:00:00 AM|Braidwood 2|100
11/13/2026 12:00:00 AM|Browns Ferry 1|100
11/13/2026 12:00:00 AM|Browns Ferry 2|100
11/13/2026 12:00:00 AM|Browns Ferry 3|100
11/13/2026 12:00:00 AM|Brunswick 1|100
11/13/2026 12:00:00 AM|Brunswick 2|100
11/13/2026 12:00:00 AM|Byron 1|94
11/13/2026 12:00:00 AM|Byron 2|100
11/13/2026 12:00:00 AM|Callaway|100
11/13/2026 12:00:00 AM|Calvert Cliffs 1|100
11/13/2026 12:00:00 AM|Calvert Cliffs 2|100
11/13/2026 12:00:00 AM|Catawba 1|100
11/13/2026 12:00:00 AM|Catawba 2|100
11/13/2026 12:00:00 AM|Clinton|100
11/13/2026 12:00:00 AM|Columbia Generating Station|100
11/13/2026 12:00:00 AM|Comanche Peak 1|0
11/13/2026 12:00:00 AM|Comanche Peak 2|100
11/13/2026 12:00:00 AM|Cooper|0
11/13/2026 12:00:00 AM|D.C. Cook 1|100
11/13/2026 12:00:00 AM|D.C. Cook 2|100
11/13/2026 12:00:00 AM|Davis-Besse|100
11/13/2026 12:00:00 AM|Diablo Canyon 1|100
11/13/2026 12:00:00 AM|Diablo Canyon 2|100
11/13/2026 12:00:00 AM|Dresden 2|100
11/13/2026 12:00:00 AM|Dresden 3|0
11/13/2026 12:00:00 AM|Farley 1|100
11/13/2026 12:00:00 AM|Farley 2|14
11/13/2026 12:00:00 AM|Fermi 2|100
11/13/2026 12:00:00 AM|FitzPatrick|100
11/13/2026 12:00:00 AM|Ginna|100
11/13/2026 12:00:00 AM|Grand Gulf 1|100
11/13/2026 12:00:00 AM|Harris 1|100
11/13/2026 12:00:00 AM|Hatch 1|100
11/13/2026 12:00:00 AM|Hatch 2|100
11/13/2026 12:00:00 AM|Hope Creek 1|100
11/13/2026 12:00:00 AM|LaSalle 1|100
11/13/2026 12:00:00 AM|LaSalle 2|100
11/13/2026 12:00:00 AM|Limerick 1|100
11/13/2026 12:00:00 AM|Limerick 2|100
11/13/2026 12:00:00 AM|McGuire 1|100
11/13/2026 12:00:00 AM|McGuire 2|100
11/13/2026 12:00:00 AM|Millstone 2|100
11/13/2026 12:00:00 AM|Millstone 3|0
11/13/2026 12:00:00 AM|Monticello|100
11/13/2026 12:00:00 AM|Nine Mile Point 1|100
11/13/2026 12:00:00 AM|Nine Mile Point 2|100
11/13/2026 12:00:00 AM|North Anna 1|100
11/13/2026 12:00:00 AM|North Anna 2|0
11/13/2026 12:00:00 AM|Oconee 1|0
11/13/2026 12:00:00 AM|Oconee 2|100
11/13/2026 12:00:00 AM|Oconee 3|100
11/13/2026 12:00:00 AM|Palisades|0
11/13/2026 12:00:00 AM|Palo Verde 1|0
11/13/2026 12:00:00 AM|Palo Verde 2|100
11/13/2026 12:00:00 AM|Palo Verde 3|100
11/13/2026 12:00:00 AM|Peach Bottom 2|100
11/13/2026 12:00:00 AM|Peach Bottom 3|100
11/13/2026 12:00:00 AM|Perry 1|100
11/13/2026 12:00:00 AM|Point Beach 1|0
11/13/2026 12:00:00 AM|Point Beach 2|49
11/13/2026 12:00:00 AM|Prairie Island 1|0
11/13/2026 12:00:00 AM|Prairie Island 2|100
11/13/2026 12:00:00 AM|Quad Cities 1|100
11/13/2026 12:00:00 AM|Quad Cities 2|100
11/13/2026 12:00:00 AM|River Bend Station 1|100
11/13/2026 12:00:00 AM|Robinson 2|60
11/13/2026 12:00:00 AM|Saint Lucie 1|100
11/13/2026 12:00:00 AM|Saint Lucie 2|100
11/13/2026 12:00:00 AM|Salem 1|0
11/13/2026 12:00:00 AM|Salem 2|100
11/13/2026 12:00:00 AM|Seabrook 1|100
11/13/2026 12:00:00 AM|Sequoyah 1|100
11/13/2026 12:00:00 AM|Sequoyah 2|100
11/13/2026 12:00:00 AM|South Texas 1|100
11/13/2026 12:00:00 AM|South Texas 2|100
11/13/2026 12:00:00 AM|Summer|0
11/13/2026 12:00:00 AM|Surry 1|100
11/13/2026 12:00:00 AM|Surry 2|100
11/13/2026 12:00:00 AM|Susquehanna 1|100
11/13/2026 12:00:00 AM|Susquehanna 2|100
11/13/2026 12:00:00 AM|Turkey Point 3|100
11/13/2026 12:00:00 AM|Turkey Point 4|100
11/13/2026 12:00:00 AM|Vogtle 1|100
11/13/2026 12:00:00 AM|Vogtle 2|100
11/13/2026 12:00:00 AM|Vogtle 3|100
11/13/2026 12:00:00 AM|Vogtle 4|100
11/13/2026 12:00:00 AM|Waterford 3|0
11/13/2026 12:00:00 AM|Watts Bar 1|100
11/13/2026 12:00:00 AM|Watts Bar 2|0
11/13/2026 12:00:00 AM|Wolf Creek 1|100
```

## Changes — PULL 2 vs PULL 1

new 0, gone 0, changed 13. Row counts: PULL 1 95, PULL 2 95 (95 = 95 + 0 - 0).

| unit | column | earlier | later |
|---|---|---|---|
| Beaver Valley 1 | days at 0 in file | 7 | 6 |
| Braidwood 1 | state since | 2025-11-14 | 2025-11-15 |
| Callaway | days at 0 in file | 56 | 55 |
| Dresden 2 | days at 0 in file | 10 | 9 |
| Oconee 2 | days at 0 in file | 12 | 11 |
| Palisades | days at 0 in file | 365 | 364 |
| Palisades | state since | 2025-11-14 | 2025-11-15 |
| Palo Verde 3 | days at 0 in file | 19 | 18 |
| Prairie Island 2 | days at 0 in file | 1 | 0 |
| River Bend Station 1 | days at 0 in file | 13 | 12 |
| Sequoyah 1 | days at 0 in file | 18 | 17 |
| Surry 1 | days at 0 in file | 45 | 44 |
| Susquehanna 1 | days at 0 in file | 62 | 61 |
| Wolf Creek 1 | days at 0 in file | 1 | 0 |

All changes are minor: "days at 0 in file" falls by 1 as the 365-day window slides (the oldest date drops out), and "state since" moves one day forward for units whose unbroken run reaches back to the first date in the window. No unit changed power, state, or fleet membership between these pulls.

## Changes — PULL 3 vs PULL 2

new 0, gone 0, changed 11. Row counts: PULL 2 95, PULL 3 95 (95 = 95 + 0 - 0).

| unit | column | earlier | later |
|---|---|---|---|
| Beaver Valley 1 | days at 0 in file | 6 | 5 |
| Braidwood 1 | state since | 2025-11-15 | 2025-11-16 |
| Callaway | days at 0 in file | 55 | 54 |
| Dresden 2 | days at 0 in file | 9 | 8 |
| Oconee 2 | days at 0 in file | 11 | 10 |
| Palisades | days at 0 in file | 364 | 363 |
| Palisades | state since | 2025-11-15 | 2025-11-16 |
| Palo Verde 3 | days at 0 in file | 18 | 17 |
| River Bend Station 1 | days at 0 in file | 12 | 11 |
| Sequoyah 1 | days at 0 in file | 17 | 16 |
| Surry 1 | days at 0 in file | 44 | 43 |
| Susquehanna 1 | days at 0 in file | 61 | 60 |

All changes are minor: "days at 0 in file" falls by 1 as the 365-day window slides (the oldest date drops out), and "state since" moves one day forward for units whose unbroken run reaches back to the first date in the window. No unit changed power, state, or fleet membership between these pulls.

```synmerco-data
b5d60d623f4d86fb18d02be8cefd21d32335b824844761e43e7aef268b8798fa nrc-fleet-pull1.csv
3809c367348bffc1d6ebf40d88189d94818fe12477996528ae880e2f108557fe nrc-fleet-pull2.csv
cbab7b539e97d7b17efe56ebcb91f49a5b2434b7bc7170606eb2c21b70c3fded nrc-fleet-pull3.csv
```

Local copies: ~/workspace/synmerco/nrc-job/pull1|pull2|pull3/ (raw file, headers, CSV, meta.json).
Figures are 2 decimals, half away from zero, from unrounded values, per the TASK defaults.