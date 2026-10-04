[README.md](https://github.com/user-attachments/files/33023653/README.md)
# SPL Nav Practice

Mock navigation papers for the UK Sailplane Pilot Licence theory exam. Each paper is built around a task plotted on the CAA Southern England & Wales 1:500 000 chart (sheet 2171CD, Edition 52, 2026), mirroring the real paper where half the navigation questions hang off a plotted route.

## Papers

| Exam | Route | Length | Themes |
|---|---|---|---|
| 1 | Husbands Bosworth → Gransden Lodge | 37 NM / 69 km | Daventry CTA steps (Class A and C), London TMA at destination, 1-in-60, final glides from Grafham Water |
| 2 | Nympsfield → Bidford | 30 NM / 55 km | Cotswold escarpment as handrail and lift, Gloucestershire ATZ, part-time Birmingham Class D, GVS and HIRTA hazards |
| 3 | Lasham → Parham | 26 NM / 49 km | Odiham MATZ, Farnborough Class D steps and TMZ, D130 Longmoor, South Downs scarp as handrail and backstop |

Each exam has versions A and B with different wind and QNH, so the calculations differ. Every paper has 20 four-option questions spread across the topics the real exam uses: plotting and wind triangle (4), navigation technique (4), airspace (5), radio and rules (2), altimetry (2), glide calculations (3). Pass mark 75%.

## Running it

It is a single `index.html` with no build step and no dependencies apart from Google Fonts. Open the file locally or publish it with GitHub Pages (Settings → Pages → deploy from branch, root). Deep links such as `index.html#exam2b` open a paper directly. Best scores are kept in the browser's local storage only.

## Editing or adding questions

All content is in the `EXAMS` array at the top of the script in `index.html`. Each exam has `plot` (the plotting brief), `common` planning data, and two `versions` with their own `data` rows and `qs`. A question is:

```js
{t:"Airspace", q:"Stem text", o:["A","B","C","D"], a:1, e:"Explanation shown after marking"}
```

`a` is the zero-based index of the correct option. Keep 20 questions per version and the topic tags consistent so the result breakdown stays meaningful.

## Sources and caveats

Airspace, frequencies and site data come from the UK AIP (AIRAC 2026-10-01: ENR 1.6, 1.7, 2.1, 2.2, 5.1, 5.3, 5.5 and AD 2 entries), the ASSelect/yaixm transcription of it, club briefing documents and UK Airprox Board reports. They were not read off the printed chart, so verify any base, boundary or hours figure against your own sheet and against current NOTAMs before relying on it. Glide figures use a generic 30:1 trainer at 50 kt, 1 NM = 6076 ft, and 30 ft per hPa.

This is a study aid, not an operational briefing.
