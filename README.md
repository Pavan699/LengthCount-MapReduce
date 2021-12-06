# LengthCount-MapReduce
Basic Length Count of words in file by using map reduce
Steps :-
$ start-all.sh
$ hdfs dfs -mkdir /LengthCount
$ hdfs dfs -ls /
$ hdfs dfs -copyFromLocal /home/pavan-linux/WordFile /LengthCount
$ hdfs dfs -cat /LengthCount/WordFile/HadoopInfo

$ hadoop jar 
/home/pavan-linux/hadoop-3.2.2/share/hadoop/tools/lib/hadoop-streaming-3.2.2.jar 
-file /home/pavan-linux/WordFile/Mapper.py -mapper 'python3 Mapper.py' -file 
/home/pavan-linux/WordFile/Reducer.py -reducer 'python3 Reducer.py' -input 
/LengthCount/WordFile/HadoopInfo -output /LengthCount/WordFile/output

$ hdfs dfs -cat /LengthCount/WordFile/output/part-00000
