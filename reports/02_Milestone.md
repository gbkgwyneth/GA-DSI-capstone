## <span style="color:#37535e">Milestone 2: Problem Statement, EDA and Dataset</span>

<ul>
    <li><b><span style='color:#3b748a'>Articulates the main goal of your project (your problem statement)</span></b></li>
    <span style='color:#3b748a'>For this project, I plan to use trip data from the Relay Bike Share program to
        predict how best to rebalance bicycles each morning in order to reduce often a rack is empty as well as to potentially balance the usage of any given bike.</span>
    <li><b><span style='color:#3b748a'>Outlines your proposed methods and models</span></b></li>
    <span style='color:#3b748a'>In order to calculate the number of bicycles at a hub, I will need to take the ride data and create "observation" data for a hub. Once I have observation data, I can use a regression model to predict approximately how empty a rack will get during a day.</span>    
    <li><b><span style='color:#3b748a'>Defines the risks &amp; assumptions of your data</span></b></li>
    <span style='color:#3b748a'>One of the risks is that I will not have enough data to make accurate predictions.</span>
    <li><b><span style='color:#3b748a'>Documents your data source</span></b></li>
    <span style='color:#3b748a'>The data source is the data from the <a href="http://relaybikeshare.com/system-data"><span style='color:#3b748a'>Relay System data</span></a>.</span>
    <li><b><span style='color:#3b748a'>Performs &amp; summarizes preliminary EDA of your data</span></b></li>
    <span style='color:#3b748a'>I have begun looking at the data and cleaning it in the EDA and clean* notebooks in the code directory.</span>
</ul>

### <span style='color:#3b748a'>Planning</span>
<ul>
    <li> <span style='color:#3b748a'><b>Oct 2:</b> Inital pass at cleaning bike data, including some plots.</span></li>
    <li> <span style='color:#3b748a'><b>Oct 4:</b> Inital pass at cleaning weather data, including some plots.</span></li>
    <li> <span style='color:#3b748a'><b>Oct 9:</b> Feature building.</span></li>
    <li> <span style='color:#3b748a'><b>Oct 14:</b> Modeling.</span></li>
    <li> <span style='color:#3b748a'><b>Oct 19:</b> Interpreting results.</span></li>
</ul>

### <span style='color:#3b748a'>Data Guidelines</span>
<span style='color:#3b748a'>What should you thinking about and looking for as you collect your capstone data?</span>
<ul>
    <li><b><span style='color:#3b748a'>Source and format your data</span></b></li>
    <li><b><span style='color:#3b748a'>Have a way to save data locally (e.g., SQL or CSV), especially if scraping from the web or collecting from an API.</span></b></li>
    <li><b><span style='color:#3b748a'>Perform initial cleaning and munging.</span></b></li>
    <span style='color:#3b748a'>The data source is the data from the <a href="http://relaybikeshare.com/system-data">Relay System data</a>. I have downloaded the data and begun to explore and clean the data.</span>
    <li><b><span style='color:#3b748a'>Create a data dictionary to accompany your data.</span></b></li>
        <span style='color:#3b748a'>Started in Step 2 above.</span>
    <li><b><span style='color:#3b748a'>Organize your data relevant to your project goals.</span></b></li>
    <span style='color:#3b748a'>I have started to consider ideas of how to transform the data into the data I need in order to model the problem.</span>
    <li><b><span style='color:#3b748a'>Write functions to automatically clean and munge data as necessary.</span></b></li>
    <span style='color:#3b748a'>I have started to write functions to clean data and will expand them and write more as I proceed.</span>
    <li><b><span style='color:#3b748a'>Take copious notes, for both others and yourself, describing your assumptions and approach.</span></b></li>
</ul>

### <span style='color:#3b748a'>EDA Guidelines</span>
<span style='color:#3b748a'>Identify the data types you are working with.</span>
<ul>
    <li><b><span style='color:#3b748a'>Examine the distributions of your data, numerically and/or visually.</span></b></li>
    <span style='color:#3b748a'>I've looked at which hubs get the most use and at which bikes have logged the most miles each month.</span>
    <li><b><span style='color:#3b748a'>Identify outliers.</span></b></li>
    <span style='color:#3b748a'>So far I haven't seen any outliers. I have seen trips that are trivial, however.</span>
    <li><b><span style='color:#3b748a'>Identify missing data and look for patterns of missing data.
        </span></b></li>
        <span style='color:#3b748a'>In looking at the missing data, I see that I will need to consider how to model bikes that are not returned to hubs. I also need to account for bikes that are possibly moved by the Relay team as well.</span>
    <li><b><span style='color:#3b748a'>Describe how your EDA will inform your modeling decisions and process.
</span></b></li>
        <span style='color:#3b748a'>As I explore the data further, this will change how I develop new features.</span>
</ul>
