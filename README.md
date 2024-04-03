# joins-in-spark
create two data frames and then join the two data frames based on the id
person = spark.createDataFrame([
  (0, "Bill Chambers", 0, [100]),
  (1, "Matei Zaharia", 1, [500, 250, 100]),
  (2, "Michael Armbrust", 1, [250, 100])]).toDF("id", "name", "graduate_program", "spark_status

  dataframe2 :
  graduateProgram = spark.createDataFrame([

  (0, "Masters", "School of Information", "UC Berkeley"),
  (2, "Masters", "EECS", "UC Berkeley"),
  (1, "Ph.D.", "EECS", "UC Berkeley")]).toDF("id", "degree", "department", "school")

![image](https://github.com/srimanth496/joins-in-spark/assets/84217751/9ef8ec61-d2bb-4941-8fbd-b7e2f649c6a4)

perform inner join operation 
joinExpression = person["graduate_program"] == graduateProgram['id']
person.join(graduateProgram, joinExpression).show()

outerjoin in spark
joinType = "outer"
person.join(graduateProgram, joinExpression, joinType).show()
