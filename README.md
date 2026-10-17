# NYC Taxi Trip Analysis (Automatidata Capstone)

Python analysis of 2017 NYC Taxi and Limousine Commission (TLC) yellow-taxi trip data (22,699 trips), completed for the Google Advanced Data Analytics Professional Certificate (Coursera). This is a practice capstone: the scenario (a consulting firm, Automatidata, analysing TLC data) is fictional, and the dataset is the course-provided sample.

## Question
Do customers who pay by credit card pay higher fares than customers who pay cash?

## Key finding
- Average fare: **$13.34 (credit card)** vs **$12.18 (cash)**, a difference of **$1.16** per trip.
- A two-sample Welch's t-test at the 5% significance level gave t = 7.04, p ≈ 1.96e-12, so the null hypothesis of equal mean fares was rejected.
- Results were almost identical before cleaning ($1.22 difference), so the finding does not depend on the records removed.
- **Caveat:** the difference is statistically significant but small, about 9% of the average fare. The data is observational and the test does not control for trip distance or duration, so it shows an association, not a cause.

## What I did
1. **Prepared the data:** converted timestamps, renamed columns, and created trip duration, month, and day-of-week fields.
2. **Checked data quality:** found negative fares, zero-distance and zero-passenger trips, and invalid rate codes, and excluded them for the hypothesis test.
3. **Explored the data:** distributions of trip distance, total amount, and tip amount; tips by vendor and passenger count; monthly and daily ride and revenue trends; mean trip distance by drop-off location.
4. **Tested the hypothesis:** stated H0 and H1, ran Welch's t-test on cleaned and uncleaned data, and interpreted the result including its practical size.

## Tools
Python (pandas, NumPy, SciPy, matplotlib, seaborn), Jupyter Notebook

## Files
- `TLC coursera analysis (5).ipynb`: full analysis with charts and commentary

## Run it yourself
1. Get the course dataset and save it as `data/2017_Yellow_Taxi_Trip_Data.csv`. The data is not included in this repository.
2. Install the libraries: `pip install pandas numpy scipy matplotlib seaborn jupyter`
3. Open the notebook and run all cells.

## Next steps
A regression of fare on trip distance, duration, and payment type would show whether payment type matters once trip length is accounted for.
