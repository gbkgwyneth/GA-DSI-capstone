## <span style="color:#37535e">Milestone 3</span>

### <span style='color:#3b748a'>Requirements</span>
<span style='color:#3b748a'>Submit a progress report that contains:</span>
<ul>
    <li><b><span style='color:#3b748a'>Do you have data fully in hand and if not, what blockers are you facing?</span></b></li>
    <span style='color:#3b748a'>I currently have two datasets: bike trip data for eight cities and weather data for those same cities. For the bike trips, all is downloaded and six are cleaned. For weather data, I have a script that has worked well for 2 years worth of data for all 8 cities. The data cannot all be uploaded to GitHub as some sets are too large.</span>
    <li><b><span style='color:#3b748a'>Have you done a full EDA on all of your data?</span></b></li>
    <span style='color:#3b748a'>I have done a pass at looking for duplicates (none), firguring out how to compute missing data (in some cases very accurate, in others not so much). I've made some preliminary plots.</span>
    <li><b><span style='color:#3b748a'>Have you begun the modeling process? How accurate are your predictions so far?</span></b></li>
    <span style='color:#3b748a'>I have made a simple model to predict number of bike trips in city, given weather data, day of week, and week of year.</span>
    <li><b><span style='color:#3b748a'>What blockers are you facing, including processing power, data acquisition, modeling difficulties, data cleaning, etc.? How can we help you overcome those challenges?</span></b></li>
    <span style='color:#3b748a'>At the moment, my only blocker is time!</span>
    <li><b><span style='color:#3b748a'>Have you changed topics since your lightning talk? Since you submitted your Problem Statement and EDA? If so, do you have the necessary data in hand (and the requisite EDA completed) to continue moving forward?</span></b></li>
    <span style='color:#3b748a'>I've expanded my scope as my original idea turned out to be somewhat trivial. I've expanded to looking at 6-8 cities instead of only Atlanta. I've also added in weather data as my first pass of EDA made me believe that weather is highly correlated with bike rentals (unsurprisingly).</span>
    <li><b><span style='color:#3b748a'>What is your timeline for the next week and a half? What do you have to get done versus what would you like to get done?</span></b></li>
    <span style='color:#3b748a'>I'll cycle between digging deeper in the data, making more models, and working on my presentation.</span>
    <li><b><span style='color:#3b748a'>What topics do you want to discuss during your 1:1?</span></b></li>
    <span style='color:#3b748a'>Nothing in particular.</span>
    <li><b><span style='color:#3b748a'>We will use your progress report as a leaping off point for a deep 1:1 with a member of the instructional staff. The best use of your time is to really flesh out this document so that your remaining time here can be most productive.</span></b></li>
</ul>

<hr>

### <span style='color:#3b748a'>Progress report</span>
<span style='color:#3b748a'>For my capstone project, I have been exploring 8 cities worth of bicycle share data (available <a href="https://www.bikeshare.com/data/">here</a>). The cities in the set are Atlanta, Boston, Chicago, Los Angeles, Philadelphia, San Francisco, NYC, and Washington DC. While the data is collected in similar forms for each market, there are differences for every city. Differences include what time periods the local markets use to publish, column names, units for "Durations", how distances are measured, and the inclusion of hubs. Some cities changed what data is reported from one time period to the next, so I had to take care with changing columns and data units as well.</span>

<span style='color:#3b748a'>I made one initial notebook (EDA_ATL.ipynb) to do preliminary exploration of the data. I wanted to learn more about datetime (start and stop), timedelta (duration), and the other data. From that, I created 6+ (still in progress) notebooks to clean and standardize the data from the past year. While most of these notebooks are the same, there are differences in column names, units, and data because of the difference in data collection and reporting. Each notebook works to read in original data files and transform them them a standard. Unfortunately, some of the datasets were too big to work with at first, so I had to take a two-step process to break them down. The result from each 'clean' notebook is a csv file of Sept 2017-July 2018 bike trip data that is standardized across cities. The cleaned data is in trips_all.csv for each city, but some of these files are too big to push to GitHub.</span>

<span style='color:#3b748a'>I then worked to collect daily weather data for the eight cities for the past year. I used BeautifulSoup to scrape Weather Underground. I had some obstacles, but managed to get the data into csv files. (<a href="http://gobbledygoon.com/2018/10/scraping-weather-data/">Scraping weather data blog post</a>). The scraped data is in weather.csv for each city.</span>

<span style='color:#3b748a'>For my first model, I look at each city one at a time. I read in the bike trip data and the weather data for that city. After some transforming of the data using a lovely groupby, I ran my special Pipeline to determine predictions to the question: "For a specified city, predict the # of bike trips for a day given the city, week, day of the week, and weather."</span>

<span style='color:#3b748a'>I have tuned these regression models, and Gradient Boost (with almost the same parameter) works well for most cities. The 6th (LA) is not working well; perhaps weather isn't as interesting there. I have not yet tried NYC and DC, but if I hope to try that soon.</span>

<span style='color:#3b748a'>I have many ideas to try out, including new data explorations, EDA, plots, a longer range for some cities, other questions to ask, and so on. Having gotten only a few hours a sleep a night for the past week or two, I think the only thing holding me back from pursuing all of my ideas is TIME!</span>

<hr>

### <span style='color:#3b748a'>This is currently incorrect! I discovered an issue in Weather Underground data and will need to rerun these tests!</span>

|     |	Random Forest |	Gradient Boost |    Train     |    Test      |
| :-: | :-----------: | :------------: | :----------: | :----------: |
| ATL |	              |       320      | 0.7056930574 | 0.7099148434 |
| BOS |	              |       330      | 0.8921235442 | 0.912888659  |
| CHI |	              |       327      | 0.9036899262 | 0.9633247151 |
| LA  |	      19      |                | 0.3501235837 | 0.5420167779 |
| PHL |	              |       326      | 0.862638606  | 0.8861347894 |
| SF  |       27      |                | 0.8599703952 | 0.8773532568 |
