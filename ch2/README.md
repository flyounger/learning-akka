CHAPTER2
========
This chapter demonstrates using akka to talk over the network to remote services. It extends on the simple examples from chapter 1, and builds a second component to talk to the code we had previously built over the network.

Inventory
---------
- futures-examples-java - demonstrate working with futures (based on ch1 example)
- futures-examples-scala - demonstrate working with futures (based on ch1 example)
- akkademy-db-client-java - client that talks to akkademy-db-java		
- akkademy-db-client-scala - client that talks akkademy-db-scala
- akkademy-db-java - simple remote key value store
- akkademy-db-scala - simple remote key value store

Preparation
-----------

Before attempting to work with the akkademy-db-client-* projects, you'll need to publish the akkademy-db-java and/or akkademy-db-server projects. Change into their root folder and then execute the "publish-local" target:

    cd akkademy-db-java
    activator publish-local

    cd akkademy-db-scala
    activator publish-local

The client projects depend on those artifacts for the messages.
You can run the database by changing in the folder and executing the "run" target:

    cd akkademy-db-java
    activator run

    cd akkademy-db-scala
    activator run

The appropriate database must be running for the akkademy-db-client-* tests to run

Running the Tests
-----------------

Most of the actual example logic is demonstated in unit tests rather than in a main. This is to make it faster to work with the example code as you can just run test suites as you make changes.

### futures-examples-java 

#### FIXME/Preparation Workaround 
NOTE: There is a bug in the scala-java8-compat lib that is fixed in 0.6.0.
0.6.0 is not released at the moment so you'd need to change the build.sbt to use 0.6.0-SNAPSHOT and then checkout the library 

    git clone https://github.com/scala/scala-java8-compat.git

and run 

    activator publish-local

When the library is published, this will not need to be done and the code will simply work at which point in time this comment should be removed!

The unit test for this project demonstrates numerous ways of working with futures. It's a good project to play around in!

To run the tests, execute the test target:

    cd futures-examples-java
    activator test

### futures-examples-scala 

The unit test for this project demonstrates numerous ways of working with future
s. It's a good project to play around in!

To run the tests, execute the test target:

    cd futures-examples-java
    activator test

### akkademy-db-client-java 
The tests in this project will attempt to talk over the network to the running instance of akkademy db (see preparation for instructions on starting the db.) 

With akkademy-db-java running, execute the "test" target

    cd akkademy-db-client-java
    activator test

You should see the following output:

    [info] Passed: Total 2, Failed 0, Errors 0, Passed 2
    [success] Total time: 4 s, completed 2-Dec-2015 2:36:28 AM

### akkademy-db-client-scala 
The tests in this project will attempt to talk over the network to the running instance of akkademy db (see preparation for instructions on starting the db.)

With akkademy-db-scala running, execute the "test" target

    cd akkademy-db-client-scala
    activator test

You should see the following output:

    [info] SClientIntegrationSpec:
    [info] akkademyDbClient
    [info] - should set a value
    [info] Run completed in 1 second, 417 milliseconds.
    [info] Total number of tests run: 1
    [info] Suites: completed 1, aborted 0
    [info] Tests: succeeded 1, failed 0, canceled 0, ignored 0, pending 0
