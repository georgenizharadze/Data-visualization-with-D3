## Summary

This visualization explores the results of a particular segment of Britain's electricity market. The Short-term Operating Reserve (STOR) market serves the purpose of making stand-by power generation capacity available to cover, at a short notice (20 min to 240 min), possible electricity shortfalls. STOR auctions are run approximately once per quarter. There are two types of participants in the market, so-called Balancing and Non-Balancing ones. The former are usually conventional, fossil-fuel power plants and the latter - more flexible resources, such as demand-side response. The visualization explores the relative pricing and sizes of the cleared bids of the two types of players and shows that **the Balancing type are generally priced higher in terms of both availability and utilization prices and also tend to come in bigger MW sizes**. 


## Design

The two main parameters for bidding in the tenders are (i) Utilization price and (ii) Availability price. Therefore, I decided to put these variables on X and Y axis, respectively. I believe that a scatterplot along these two dimensions conveys well the relative positions of various bids. Additionally, I decided to encode Balancing vs. Non-Balancing type and the size of the physical plant behind the bid. The former is a qualitative variable, hence I decided to encode it with colors. The latter is a continuous variable, therefore, I encoded it with circle area. I made sure that the area, not the radius, corresponded with the actual size. 

I decided to display four charts at once, each corresponding to a tender round, as I wanted to show that the higher price, larger size pattern for the Balancing type assets was consistent across the tenders. Also, looking at the tender charts separately allows the viewer to gauge the relative liquidity of the different tender rounds, e.g. Tender Round 28 was clearly most liquid, with the highest number of cleared bids. 

I decided to put the legend at the bottom of overall charts area. This is more economical, as the horizontal space is quite constrained with the four charts and placing the legend on the left-hand side would have made squeezed the horizontal area even further. 

After the feedback (see next section), I made the following design modifications:

* Focused on the cleared bids only, to make a very clear distinction between Balancing and Non-Balancing types and crystallize the key point of the former ones being higher priced and larger size. 
* Added grid lines for easier visual perception of price levels. 
* Added an introductory paragraph to the chart, to give the viewer the context and highlight the key message. 
* Spotted and corrected an error in the `scaleRadius` function, setting the lower bound of the `domain` and `range` to zero, as opposed to the minimum value in the data. This improved the visualization and helped better accentuate the key message.  
* Changed the coloring of the Season buttons, highlighting the clicked one. 




## Feedback 

Feedback1: 

_Looking at your web link, I like the format of your graphs and the way you can select them by season. From a use perspective, they can be difficult to read when there are many circles and they overlap, especially without any gridlines for reference. National Grid might say they do present their data in a lot of detail, including graphically already eg the STOR Market information reports. I think you’d have to show and explain how your presentation of this data is better and provides additional benefits._

Feedback2:

_I like the interactivity by seasons and the way you have broken data by tender rounds. You may want to crystallize the main idea, the key takeaway, more effectively._

Feedback 3:

_A lot of useful information in these plots. I recommend that you focus on one or two key messages._


## Resources 

The data was sourced from the tender reports on [Britain's National Grid web site](http://www2.nationalgrid.com/UK/Industry-information/Electricity-transmission-operational-data/Report-explorer/Services-Reports/), consolidated and processed into a machine-readable csv file. 


