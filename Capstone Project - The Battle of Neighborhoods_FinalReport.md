# Analysis of the Neighborhoods in San Jose, California for Starting a new Restaurant

## *Capstone Project - The Battle of Neighborhoods:*

***

## 1. Introduction

San Jose, California, located in the center of Silicon Valley, is the largest city in Northern California by both population and area. With an estimated 2019 population of 1,021,795, it is the  third-most populous city in California (after Los Angeles and San Diego) and the tenth-most populous in the United States. Located in the center of the Santa Clara Valley, on the southern shore of San Francisco Bay, San Jose covers an area of 179.97 square miles.

The large concentration of high-technology engineering, computer and microprocessor companies around San Jose has led the area to be known as Silicon Valley. And this also led the San Jose has a large variety of immigrations and different kind of restaurant across all the city. The diversity of the population of the city has also brought in a vast diversity in food. To start a new restaurant, it is very import to do a careful analysis of the neighborhoods in San Jose and find the best area, which is the main topic in this project and also the business problem we will solve.

## 2. Business Problem

Our client is an investor and entrepreneur who is plan to start a new restaurant in San Jose. He approached us to study the neighborhoods in San Jose and suggest a location of area which would be in best interest of the business. Our goal is to extract and analysis the data of all the neighborhoods of San Jose, using machine learning techniques and provide a suggestion of locate to start a new restaurant.

## 3. Data

The following data is required for this project. We will divide it in to below sections.

### 3.1 Neighborhood Data

The neighborhood data includes all the neighborhood name. This information can be easily find in the [wikipedia page](https://en.wikipedia.org/wiki/Category:Neighborhoods_in_San_Jose,_California). 

![Ndata](.\Figures\Figure1.PNG)

### 3.2 Geographical Coordinates

We will use the Geopy library in python to get all the geographical information. The geographical coordinates is very important for map plotting during the project. Here is the example data after pulling out all the geographical coordinates.

![GData](.\Figures\Figure2.PNG)

We can also plot the neighborhood on the map:

![Gmap](.\Figures\Figure3.PNG)

### 3.3 Venue Data

The venue data will be pulled from the FourSquare API. The main query type we will use is explore. And the result information will be used for data clustering. Here is an example of the Venue data for one neighborhood.

![VData](.\Figures\Figure4.PNG)

## 4. Methodology

### 4.1 Feature Extraction

With the help our Foursquare API, we can extract the feature the feature of each neighborhood. First, we create a function and looped it to all the neighborhood to get the explore result. The Foursquare API will feedback us a list of interesting venues. 

![7](.\Figures\F7.PNG)

Second, we can group the venues by neighborhood. This can be done by using one-hot encoding. That is, if a venue belongs to a neighborhood, we will assign the frequency to the corresponding row and venue's column. We do this for all the neighborhood and we can get a matrix like below:

![8](.\Figures\F8.PNG)

Third, with the data above, we can create another data frame that will represent the most common venue in each neighborhood. The matrix is like below:

![F9](.\Figures\F9.PNG)

When we reach here, we have complete all the data preparation for the data clustering.

### 4.2 Unsupervised Machine Learning

We will use K-means to do the unsupervised machine learning to cluster the neighborhood to different group, which have some special features. For the number K, we will use the K-mean model to loop through different k and get the number of k vs Silhouette score plot. Then we can decide which K to use with the highest Silhouette score. The result is in below:

![F5](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\Figure5.PNG)

## 5. Results

The clustering model clusters the neighborhoods in San Jose and also provides a label. We can merge the label result into the most common venue matrix in chapter 4.1. Then we can see the features of each cluster. The below is the map plot of the clustering

![F6](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\Figure6.PNG)

And for each cluster, the first cluster:

![F10](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\F10.PNG)

Second cluster:

![F11](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\F12.PNG)

Third cluster:

![13](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\F13.PNG)

Forth cluster:

![14](C:\Users\tommy\Desktop\OnWorking\Coursera\IBMDataScience\Capstone_Project\Coursera_Capstone\Figures\F14.PNG)

## 6. Discussion

The cluster result shows San Jose city is a kind of 'average' city. The first cluster contains most of the neighborhoods. And all the neighborhoods in the first cluster has at least one kind of restaurant in its most  3 common venue. And the rest venues with high degree is coffee shop, grocery store, mall and so on. It indicates that the shopping trend is very high in this kind of neighborhood. The overall conclusion is that cluster one is the most suitable one for starting a restaurant. Within a close look at the neighborhoods, we recommend Alviso, Berryessa, Burbank, Downtown Histroic District, Downtown San Jose, East San Jose, Evergreen and South San Jose.

The second cluster is actually not very suitable for the restaurant since most interesting venues in this area are construction and landscaping company, music store and nail salon. 

The third cluster is also not very suitable for the restaurant since the interesting venues are recreation center and nail salon. It has some restaurant but the most common venues are not showing the neighborhood has large trend on shopping and dining.

The fourth cluster also not suitable for restaurant since the most common venues are baseball field, accessories store, music venue and so on. All of the venues has no relation ship with restaurant at all.

## 7. Conclusion

In this project, the neighborhoods of San Jose, California has been successfully analyzed and we use the result to determine the best place to start a new restaurant. Based on the analysis result, the neighborhoods in cluster one are recommend. However, since the cluster one contains a large number of neighborhoods, a more detailed analysis can also conducted based on the interest of stake holders and investors.





## Notes:

The repo for this project is: [https://github.com/ArizonaTea/Coursera_Capstone](https://github.com/ArizonaTea/Coursera_Capstone)

