# Spark 2 Notes
```
- sc.addFiles("test.txt") to load files from local:  SparkContext.addFile()
	- import org.apache.spark.SparkFiles;
	- sc.textFile(SparkFiles.get("spam.data"))
- Creating hive context
	- import org.apache.spark.{SparkConf, SparkContext}
	- import org.apache.spark.sql._
	- import org.apache.spark.sql.hive.HiveContext
	- //val sc = new SparkContext(conf)
	- val hiveContext = new HiveContext(sc)
	- import hiveContext.implicits._
	- import hiveContext.sql
- // for file where json objects are in single lines
	- val customers = sqlContext.jsonFile("customers.json")
- For Multilines file
	- val jsonRDD = sc.wholeTextFiles("baby_names.json").map(x => x._2)
	- val namesJson = sqlContext.read.json(jsonRDD)
```