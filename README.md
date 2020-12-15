# projectilework
     Steps to Begin With Apache Spark.

Step 1: Ensure if Java is installed on your system
Before installing Spark, Java is a must-have for your system. The following command will verify the version of Java installed on your system:
Step 2:Install the IntelijIdea for the purpose of handling the spark with scala.
Step 3:Add the shortcut to the desktop .
Step 4:Open the desktop launcher of Intelijidea and make the further options so as to maintain the progress of whole criterion
Step 5:Add the sbt of required functionalities like scala,spark,delta lake,kafka and build these in build.sbt and then refresh the project so as to update the required libraries to the intelijidea.

Step 6:You can start building your project .
Software Requirements:
●Spark version: 3.0+
●Kafka Version: deployed dependencies
●Delta Lake Version: 0.7.0
●Scala version: Specific to Spark version

 					About Task 1:
-> I was suppose to convert csv given file to a json format .

I took csv file that was given to us as an input and then by using Sparksession firstly started the code and afterwards:
import org.apache.spark.sql.{SaveMode, SparkSession}
Savemode is for overwrite mode  while writing or saving anything.


.appname is for purpose of taking a name for file.
.master is for the purpose of cluster
.getorceate()is for the purpose of making sparksession if not made
-> read the csv file with spark.read.option(“header”,true/false)
header-> is for the purpose to take a heading in the file we will gonna be writing  header .
-> .show file is for showing the dataframe we have got from csv file
then moreover 
.write file comes into consideration for the purpose of making the files copied in computer memory it can be of differen types
like:::     .write.csv/.json/.parquet etc.
for the purpose of saving the files in csv format json format and parquet format.




                                About Task 2:
(a).Apply the specified transformationsI took csv file that was given to us as an input and then by using Sparksession firstly started the code and afterwards:
.appname is for purpose of taking a name for file.
.master is for the purpose of cluster
.getorceate()is for the purpose of making sparksession if not made
-> read the csv file with spark.read.option(“header”,true/false)
header-> is for the purpose to take a heading in the file we will gonna be writing  header .
-> .show file is for showing the dataframe we have got from csv file
then moreover 
.write file comes into consideration for the purpose of making the files copied in computer memory it can be of differen types
like:::     .write.csv/.json/.parquet etc.
for the purpose of saving the files in csv format json format and parquet format.
(These are the transformations.)
1.Add processing_date and processing_time_utc.
2.Add ‘Xenonstack’ as company name.
3.Add ‘10min’ as data_source.
4.Set timestamp_utc as end_timestamp_utc.
5.Create start_timestamp_utc as end_timestamp_utc - 10 min.
6.Unpivot the columns other than timestamp_utc, start_timestamp_utc,
end_timestamp_utc, processing_date, processing_time_utc, turbine_id, company_name
and data_source into singal_code and signal_value.
(b).Write the Data into Open Delta lake format.

------------------------------------------------------------------------------------------------------------------------
What I have done.

import org.apache.spark.sql.functions.{col,current_timestamp, lit}
Have imported few reasonable and required libraries like import org.apache.spark.sql.functions.{expr, hour, minute, second}
import org.apache.spark.sql.{SaveMode, SparkSession}
import org.apache.spark.sql.functions.{col, current_date, current_timestamp, from_utc_timestamp, lit, map_values, to_timestamp, to_utc_timestamp}

For whole transformation have done the following part:
We need to achieve the whole so for that we have added 2 columns with specific formatting i.e. used for the purpose of adding the new columns in the current dataframe .(.withcolumn("",lit()))is used to add column.
.withincolumnrename("","")used to rename the columns.
.selectexpr()used to write sql expressions in dataframe

Instead of saving it to parquet file save it to .delta format to get the whole of how to manage and rollback the all comits we have made.

































