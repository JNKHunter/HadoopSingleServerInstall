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

Click on the binary of the release tarball you'd like. On the next page copy the link of the download mirror.

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

