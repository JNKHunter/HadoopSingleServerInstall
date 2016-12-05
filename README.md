# HadoopSingleServerInstall

Install Hadoop on a single server or dev box. Finish by testing an example MapReduce program.

## Step 1 - Install Java

```
sudo apt-get update
```

```
sudo apt-get install default-jdk
```

Verify Java install

```
java -version
```

## Step 2 - Install Hadoop

Go to Hadoop releases page
[http://hadoop.apache.org/releases.html]

Click on the binary of the release tarball you'd like to use. On the next page copy the link of the download mirror.

Download to a directory on your computer:
```
wget http://apache.mirrors.tds.net/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz
```

Optional: Run a check using the SHA-256 checksum provided

Untar the archive
```
tar -xzvf hadoop-2.7.3.tar.gz
```

Move the extracted files into /usr/local
```
sudo mv hadoop-2.7.3 /usr/local/hadoop
```
## Step 3 - Configure Hadoop
Open hadoop-env.sh

```
sudo vim /usr/local/hadoop/etc/hadoop/hadoop-env.sh
```

Set the value for JAVA_HOME
```
export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")
```

Note: This value of JAVA_HOME will override any environment variable you may have set in ~/.bash_profile or ~/.bash_rc

You can alternatively set a static link (rather than a dynamic link using readlink | sed).

Step 4 - Run Hadoop

Test hadoop:
```
/usr/local/hadoop/bin/hadoop
```

Step 5 - Run an example mapreduce job
```
mkdir ~/input
cp /usr/local/hadoop/etc/hadoop/*.xml ~/input
```

```
/usr/local/hadoop/bin/hadoop jar /usr/local/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.3.jar grep ~/input ~/grep_example 'principal[.]*'
```


