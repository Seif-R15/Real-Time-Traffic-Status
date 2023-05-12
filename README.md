# Real-Time-Traffic-Status
# Real Time Traffic-Status Supplied To Rennes Métropole By The Company Autoroutes Traffic.

#  Introduction

A decade ago, it was hard to access timely, accurate traffic data to support applications and services, such as traffic management, mapping and navigation, safety and emergency management, urban planning for smart cities, or location intelligence. Today, real-time traffic data is much more widely available as public datasets and commercial sources. At the same time, there are many more new applications and machine learning algorithms that use real-time traffic data to reduce congestion, guide drivers, and generate new insights for decision makers. 

![Traffic-flow-under-different-types-of-traffic-condition.jpg](attachment:Traffic-flow-under-different-types-of-traffic-condition.jpg)

#  Methods for Collecting The Traffic Status

## 1 - Video Analytics 

![image.png](attachment:image.png)

Many municipalities have deployed closed-circuit television (CCTV) systems for surveillance purposes. These can be used for measuring traffic.

•	Ongoing Cost: For municipalities that have already deployed video analytics systems, there is no extra data collection effort.

•	Coverage: 24/7/365 coverage

## 2-In-Roadway Traffic Flow Sensors

![image.png](attachment:image.png)

There are several types of in-roadway sensors that can be placed on roadways or within the pavement. They are another useful traffic data source.

•	Ongoing Cost: For municipalities that have already invested in sensors, this is an existing data source upon which they can capitalize.

•	Few Privacy Concerns: Sensors can detect vehicles passing over them but do not collect any information about those vehicles.

•	Coverage: 24/7/365

# Describtion of The Data Set

Real-time traffic status. Data supplied to Rennes Métropole by the company Autoroutes Trafic.

These data have a “time limit” of 3 minutes, so it is normal that at 15:30, the most recent data indicates 15:27.

Description of the fields.

•	datetime: the date of the information in ISO 8601 format (https://www.iso.org/iso-8601-date-and-time-format.html)

•	predefinedLocationRerefence: the identifier of the Rennes Métropole section to which the information is attached. The identifier can be suffixed by “_D” and “_G” in the case of a double-way section. The scanning direction of the section is then the meaning “D”, the direction reverses the meaning “G”.

•	averageVehicleSpeed: the average speed of vehicles travelling on the section, kilometre per hour.

•	travelTime: the journey time of the section, in seconds.

•	travelTimeReliability: the reliability of the journey time provided, as a percentage of 0 % to 100 %.

•	trafficStatus: the traffic status on the section, the possible values are:

•	unknown: State unknown

•	FreeFlow: fluid

•	heavy: responsible

•	Congested: congested

•	impossible: traffic not possible

# DataSet Problems (Disadvanteges)

### Before We beign in Analysing this DataSet and Visualise It We Can Deduce THREE Main Problems or Disadvantages :

1-Date Time Column: In the column that should give us a breif description for the time when these record was taken we deduced that it was taken at the same day ,more over at the same second. 
Thus We could'nt make use of this column as there was no variance at all in the time of these record, except to convert it to a much clear format to see the day and the other features

2- Missing Describtions: The Second Problem We have Faced is that there are more than half of the Columns ( Features ) doesn't have any describtion which will surely affect the analyzing process and especialy in the Feature Engineering and in Creating new features. These missing info will also affect the final ML Model accuracy. As there are some features that are not Globaly known as gml_Id or predefinedlocationreference.

3- Missing Features: Despite the missing Describtions of some features there are also some missing features as Type of the vehicles that was recorded, where if we knew the type of veichle we could visualize it for example and see which type of vehicles that causes more  Congested trrafic, thus in the future we could make a model that suggest which route is better depending on your vehicle type.

In the end all these missing values and features ends up in making a not perfect Analysing Process which will eventually affect the ML Model that we could make in the future as to predict the best routs for you ( depending on your vehicle type ) 

# DataSet Advantages

Despite the previous disadvantages that We Faced there were also advantages and the main advantage is the realiabilty of this dataset and how much we can consider it as a Good Real DataSet that can Describe the Real-World situation.

1-Time: As we said these record were taken at the same instanse accross all the Rennes Traffic area and for the first sight we could say that this is a realiabile DataSet from simply seeing the numberr of records (2369) which is infact a very small amount of records considiring that the Rennes population isone of the most densely populated areas in France of 739,974 inhabitants so the trrafic capacity there should be about atleast 10000 records in a day. However Because this DataSet was only taken at the same instanse the number of records are the most perfect fitting number scaled to the real world scenairo.

2-Logic: This Data when Visualizing it We Deduced that at many of our Assumtions it gaved us a True plots for what is logicaly wise plots and Visulas.  

#  Contents  :

  EDA (Exploratory Data Analysis)
  
1-Understanding Data using Data Visualization methods

  Preprocessing

2-Feature Engineering

   - Converting The Date Time from Object To DateTime 64 format
        - Feature Engineering Using String Operation
          - Visualiztions of The New Features
             - Creating New Geospitial Features
             

          
3-Dealing with Outliers

   - Visulaizing The Outliers
      - Replacing Outliers Using The Z-Score
        - Replacing Outliers Using Local Indecies
          - Checking That We Removed The Outliers In Both Cases

4-Dealing with Missing Data
    
   - First : For Numerical Data
      - Checking The Index of The Missing Values
        - Get The Location index for all the NaN Values
          - Dropping Rows of Nan Values
          
   - Second: Categorical Data

5-Encoding Numerical and Categorical Data
  
   - First: Encoding Ordered Data  
     - Encoding Using Label Encoder ( Ordinal Encoder )
   - Second: Encoding Nominal Data 
      - Encoding Using One Hot Encoder
        - Encoding Using Binary Encoder Method
   - Removing Duplicated Columns
   - Preparing DataSet For Feature Scalling

6-Spliting DataSet into Training and Test Set

7-Feature Scalling
