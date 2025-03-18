# algebracket-kenpomstats
This just serves as a placeholder for some simple combinations of different team metrics for men's college basketball - all of the necessary data to reach the results provided in the screenshots under *scores* is provided in the folder *data_kenpom*. By adding statistics sourced from *Ken Pomeroy* (in addition to those provided by *algebracket.com / Peter Rifel*), and by placing weights for specific rounds, you can backfit somewhat prettier results for previous years. Below is a breakdown of the results for each year (which you can find in the *scores* folder, as previously outlined):

| Year / Group | Picks Correct | Score | Upsets |
|--------------|---------------|-------|--------|
| 2010         | 42            | 123   | 13     |
| 2011         | 36            | 56    | 13     |
| 2012         | 44            | 140   | 6      |
| 2013         | 45            | 147   | 11     |
| 2014         | 44            | 93    | 10     |
| 2015         | 48            | 158   | 7      |
| 2016         | 48            | 160   | 14     |
| 2017         | 44            | 127   | 8      |
| 2018         | 37            | 104   | 7      |
| 2019         | 47            | 137   | 6      |
| 2021         | 43            | 146   | 9      |
| 2022         | 41            | 120   | 8      |
| 2023         | 37            | 106   | 13     |
| 2024         | 47            | 157   | 8      |
| Total        | 603           | 1774  | 133    |
| Average      | 43.1          | 126.7 | 9.5    |

The result is 12 out of the last 14 winners correct, with the last incorrect winner being in 2014. Obviously, the biggest thing to look out for when doing any project like this (and as I have said, I'm no data scientist) is overfitting your backward-looking results. That is, when I first explored this idea last year, my resulting bracket was poor for 2024 (unsurprising, but albeit without any KenPom metrics and without weights assigned to each round) - which was only improved by changing weights FOLLOWING last year. To put it simply, I'm essentially saying to take all of these numbers with a grain of salt - far smarter people have tried making sense of predicting March Madness before, and to no substantial avail, so if you are expecting incredible results from the predicted bracket included (*./scores/2025.png*), you are in for a world of hurt (as I was last year)! Approach anything you see in here as purely theoretical and more for fun than anything.

The individual weights are below:
* Round of 64, Round of 32, Sweet Sixteen, and Elite Eight:
  * Win %: 2
  * SoS: 1
  * Offense Rating: 1
  * Free Throw %: 1
  * NetRtgTotalPlusLuck: 3
* Final Four:
  * Win %: 2
  * SoS: 3
  * Offense Rating: 6
  * Opp. Turnover %: 2
  * NetRtgTotal: 17
* Championship:
  * Win %: 4
  * SoS: 1
  * Rebound %: 0.8
  * Off. Rebound %: 0.8
  * Opp. Turnover %: 1.2
  * NetRtgTotalPlusLuck: 20 

## Included files / folders
+ *./data_kenpom/* => folder containing all of the data as it pertains to the results above - these are simply just copies of existing data provided by algebracket, with additional columns related to KenPom tacked onto the end of each CSV file.
    > __Note__ files included: 2010.csv, 2011.csv, 2012.csv, 2013.csv, 2014.csv, 2015.csv, 2016.csv, 2017.csv, 2018.csv, 2019.csv, 2021.csv, 2022.csv, 2023.csv, 2024.csv, 2025.csv
+ *./scores/* => folder containing images of all the results yielded each year using the data from the CSV files listed above. You would have to modify some of the code in the existing algebracket repository (namely the engine.js file) to utilize the additional weights as needed.
    > __Note__ files included: 2010.png, 2011.png, 2012.png, 2013.png, 2014.png, 2015.png, 2016.png, 2017.png, 2018.png, 2019.png, 2021.png, 2022.png, 2023.png, 2024.png, 2025.png

## Credits
Data is sourced from the following:
* **[algebracket.com](https://algebracket.com/)** / **[Peter Rifel](https://github.com/rifelpet/weighted-bracket-picker)** (*for all initial data / webpage to display results*)
* **[kenpom.com / Ken Pomeroy](https://kenpom.com/)** (*for all additional data in each .csv - namely NetRtg, NetRtg.1, Luck, NetRtgTotal, and NetRtgTotalPlusLuck columns*)
