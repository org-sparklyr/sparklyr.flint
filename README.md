This is the maven artifact repository for [sparklyr.flint](https://github.com/r-spark/sparklyr.flint).
It contains customized builds of the [Flint](https://databricks.com/blog/2018/09/11/introducing-flint-a-time-series-library-for-apache-spark.html) time series library.


Steps for adding a new maven artifact to this repo:

1. Checkout the maven2 branch:

```
git checkout --track origin/maven2 -b maven2
```

2. Copy the jar file to ./build/libs/"${LOCAL_FILENAME}"
3. Run the following and check-in the generated changes

```
  mvn install:install-file \
    -DgroupId=org.sparklyr \
    -DartifactId="${ARTIFACT_ID}" \
    -Dversion="{VERSION}" \
    -Dfile=./build/libs/"${LOCAL_FILENAME}" \
    -Dpackaging=jar \
    -DlocalRepositoryPath=. \
    -DcreateChecksum=true \
    -DgeneratePom=true
```
