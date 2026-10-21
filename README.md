# The City Records

Standalone interactive newspaper from Ratlantis, by Isabel Zulawski. Opens directly at the newspaper, with no game, player creation, story progression or saved-game access.

Live site: https://isabelzulawski.github.io/rat-newspaper/

## Run locally

Install Node.js once. Run `npm install`, then `npm run dev` and open the printed URL ending in `/rat-newspaper/`. `npm test` checks the calculations. `npm run build` builds `dist/`; `npm run preview` serves the built site.

## Edit the newspaper

- `src/data/living-newspaper.js`: interactive D3 bars, lines, map, movable paper and interface copy.
- `src/data/living-newspaper-model.js`: row conversion, monthly grouping and denominators.
- `src/data/living-newspaper.css`: typography, layout and interactions.
- `src/data/newspaper-articles.js`: full articles, captions and methodology.
- `src/data/Newspaper.js`: page turns and close/reopen behavior.
- `src/data/newspaper-visualizations.js`: shared CSV loader and original chart functions.

## Data

The supplied `public/data/rats_2025_initial.csv` is preserved, along with its identical gzip copy. It contains 144,314 initial inspection visits in calendar 2025 from NYC DOHMH Rodent Inspection: https://data.cityofnewyork.us/Health/Rodent-Inspection/p937-wjvj/about_data

Rat-activity findings include Failed for Rat Activity and Failed for Rat Activity and Other Reason. Percentages divide findings by all included initial visits in a borough or borough-month. Unknown outcomes remain in the denominator. Missing months are gaps, not zeros. Repeat property visits remain inspection events. The map excludes 3,550 visits with unusable coordinates, retaining 140,764 visits and 24,815 findings; these visits remain in the other charts. Borough boundaries are local NYC Department of City Planning geometry.

Inspected properties are not a random sample. More recorded findings can reflect more inspections. Uninspected places are not evidence of no rats. Inspection findings do not count individual rats. The exact snapshot/schema context is retained in `public/data/schema.json`.

## Controls

Click ranking controls or bars; choose a borough or all boroughs on the monthly page. Queens remains the subject of the December headline and comparison. Drag the generated loose scrap to uncover the comparison; click/tap can park it, arrow keys move it and Home replaces it. Choose a map layer and move the magnifying glass to inspect source counts in that area. Turn pages using the folded corners. Full articles and sources remain readable.

## Deployment

The GitHub Actions workflow builds and deploys this project on pushes to main. GitHub Pages source must be GitHub Actions. Asset paths use `/rat-newspaper/`. The original Ratlantis repository is separate.

## Figma styling and scrap coverage

All three spreads follow the edited Figma newspaper style using bundled Texturina, Oranienbaum and Labrada fonts. The December scrap fully covers the comparison when reset and parks clear of the text when clicked. Dragging, keyboard reset, charts and map controls remain available. Style overrides are in `src/data/newspaper-figma.css`; font licenses are in `src/data/fonts/`.
