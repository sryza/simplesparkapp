Simple Spark Application
==============

A simple Spark application that counts the occurrence of each word in a corpus and then counts the
occurrence of each character in the most popular words.  Includes the same program implemented in
Java and Scala.

To make a jar:

    mvn package

To run from a gateway node in a CDH5 cluster:

    spark-submit --class com.cloudera.sparkwordcount.SparkWordCount --master local \
      target/sparkwordcount-0.0.1-SNAPSHOT.jar <input file> 2

This will run the application in a single local process.  If the cluster is running a Spark standalone
cluster manager, you can replace "--master local" with "--master spark://`<master host>`:`<master port>`".

If the cluster is running YARN, you can replace "--master local" with "--master yarn".

