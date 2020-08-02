# TPO project in Python
This is a pure Python project to calculate various Market profile related operations in python and visualize them interactively with the help of plotly and dash components. 
The motivation behind this project is to feed price distribution (TPOs with alphabets) and other visual cues to convolution neural networks and see if NN learns from the visualization. Therefore this project will be heavy with all the visual cues, colours and different shapes. 
While working on the project realized that it is possible to use this entire framework for regular charting as well. 

Okay, let's get started.
## Dependencies
pip install plotly (update if previously installed)

pip install dash (update if previously installed)

pip install pandas

Finally, download all the files or clone this repo as zip and extract in local folder.

## Steps for live chart

1. Open tpo_project.py from the folder in python editor

2. Run the code

3. In the console, you will see the message something like Running on http://127.0.0.1:8050/ copy the server address your console printed and paste it in your browser

4. That's it, you will get the TPO chart in browser with sample file provided in the folder.

5. About sample file: There is live.txt file in the folder. Add data manually and you should see new updated price in the chart. 

6. Marker shows the last closing price. The market color changes to green if price >= POC else it is red.

7. If the test runs successfully replace live and historical data with your desired data feed.

8. Stop the server by pressing ctrl + c in the console.

## For static chart

Simply run static_tpo.py and chart will open in your browser

## Important

1. Match data format and headers exactly with given sample file.

2. It is not necessary to have the same data source for historical and live data as long as the format matches. It wouldn't matter even if symbol name is different, or there is price overlap the algorithm will drop the duplicate entries automatically.
2. Algorithm uses historical data for generating context. In tpo_project.py at the start, there is 'avglen' parameter. That number should be lower or equal to the sample size of your historical data. If you have 31 days of historical data then use avglen = 30

3. Make sure your historical file is up to date, especially entries representing day 1 and day 2. The algorithm automatically calculates session time and Initial Balance period using that info. IB is of 60 minutes. It assumes you have 1-minute data. I haven't tested on daily data. 

4. If your live feed is of 1 minute instead of a tick, you may want to increase the refresh time 'refresh_int' which is set to default 1 second.

5. Chart update will not work until live file gets at least 30 minutes worth of data. To remove the limitation reduce frequency-time 'freq' from default 30 to 5 minutes or lower. But it will affect TPO chart calculations. So if possible don't change the parameter.


## How to read TPO chart generated by our algo and related resources

![How to read TPO chart generated by our algo-1](https://user-images.githubusercontent.com/28746824/89121455-a7b87a00-d4dc-11ea-9df1-6bc1bf897ac6.png)

![How to read charts. Hover menu -2](https://user-images.githubusercontent.com/28746824/89114961-af0d6280-d49f-11ea-8b27-baffa44c7451.png)

![How to read the charts: square boxes -3](https://user-images.githubusercontent.com/28746824/89114065-37870580-d496-11ea-99c0-a6a208441a44.png)

Highly reccomend Mind over Markets by Jim Dalton

CBOT Market Profile handbook (it is 13 mb pdf file)  https://t.co/L8DfNkLNi5?amp=1

