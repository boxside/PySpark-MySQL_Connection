```python
from pyspark.sql import SparkSession
# May take awhile locally
spark = SparkSession.builder.appName("Mysql").getOrCreate()
```


```python
sql = """(SELECT * FROM ovo.scd_mst_user_dummy) foo"""
url_st="jdbc:mysql://localhost:3306/mysql"
driver_st="com.mysql.jdbc.Driver"
username="root"
passkey="#######"
```


```python
df = spark.read.format("jdbc").options(url=url_st,driver=driver_st,dbtable=sql,user=username,password=passkey)\
.load()

df.show()
```

    +-------+------------+---------+-----------+--------------------+-----------+------+--------------------+
    |user_id|   full_name|nick_name|      phone|               email|nationality|gender|timestamp_registered|
    +-------+------------+---------+-----------+--------------------+-----------+------+--------------------+
    |0001203|MIMIN SUKAES|   MIMIN |80181482501|miminsukaes123@gm...|        WNI|Female| 2016-10-21 08:35:29|
    |0001294|MAHDA JANNAT|   MAHDA |80178247301|mahdajannat123@gm...|        WNI|Female| 2016-10-27 08:26:16|
    |0001326|GEMILANG BAG|   GEMILA|80112894101|gemilangbag123@gm...|        WNI|  Male| 2016-10-29 10:40:39|
    |0001450| NANA TRIANA|   NANA T|80110727901|nanatriana123@gma...|        WNI|  Male| 2016-11-05 13:16:45|
    |0001715| EMA MAYLISA|   EMA MA|80116337301|emamaylisa123@gma...|        WNI|Female| 2016-11-18 20:18:21|
    |0001835|HARY HERI YA|   HARY H|80128287701|haryheriya123@gma...|        WNI|  Male| 2016-11-22 13:11:47|
    |0001839|TETTY ROYANI|   TETTY |80160573701|tettyroyani123@gm...|        WNI|Female| 2016-11-22 15:23:21|
    |0002050|DEBBY YURIPA|   DEBBY |80198063801|debbyyuripa123@gm...|        WNI|Female| 2016-11-28 10:41:21|
    |0002555|FERDY SYARIF|   FERDY |80195225801|ferdysyarif123@gm...|        WNI|  Male| 2016-12-10 22:58:51|
    |0002619|HENDRA KUSNI|   HENDRA|80191199701|hendrakusni123@gm...|        WNI|  Male| 2016-12-12 16:07:30|
    |0002715| AGEM SUGEMA|   AGEM S|80112354401|agemsugema123@gma...|        WNI|  Male| 2016-12-14 18:11:41|
    |0003397|FITRIA HANDA|   FITRIA|80152021601|fitriahanda123@gm...|        WNI|Female| 2017-01-01 07:14:10|
    |0003801|ARRIE KRISTI|   ARRIE |80140871901|arriekristi123@gm...|        WNI|  MALE| 2017-01-10 14:18:02|
    |0004049|SYAFIRA DALI|   SYAFIR|80116003801|syafiradali123@gm...|        WNI|Female| 2017-01-15 14:45:26|
    |0004165|MUHAMMAD YUD|   MUHAMM|80118115601|muhammadyud123@gm...|        WNI|  Male| 2017-01-18 19:35:44|
    |0004277|DODY SETIA P|   DODY S|80148689901|dodysetiap123@gma...|        WNI|  Male| 2017-01-21 19:19:00|
    |0004347|SARAH LAUREN|   SARAH |80193960301|sarahlauren123@gm...|        WNI|Female| 2017-01-23 17:39:46|
    |0006847|RUDI FEBRIAN|   RUDI F|80187646301|rudifebrian123@gm...|        WNI|  Male| 2017-02-12 13:47:50|
    |0007527|BELLA FARENC|   BELLA |80160838801|bellafarenc123@gm...|        WNI|Female| 2017-02-28 14:59:15|
    |0007698|    CHRISHAN|   CHRISH|80119279601|chrishan123@gmail...|        WNI|  Male| 2017-03-04 14:56:46|
    +-------+------------+---------+-----------+--------------------+-----------+------+--------------------+
    only showing top 20 rows
    
    


```python

```
