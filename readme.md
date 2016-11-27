#JUnitXmlFormatter

This repository contains an `AntXmlRunListener`, based on the one
contained in [Schmant](http://schmant.sourceforge.net/).  This
RunListener can be used to generate JUnit XML reports which can be
read by various integration servers and development tools.

The code here was forked from
[Barry Pitman’s repository](https://github.com/barrypitman/JUnitXmlFormatter),
and is used under the terms of the respective licences (GPLv2 or
later, Apache).

*Programmatic Usage*:
```java
// default constructor will look for system property "org.schmant.task.junit4.target", with path to output XML file.
AntXmlRunListener runListener = new AntXmlRunListener()

// or you can set the output stream
runListener.setOutputStream(new FileOutputStream(new File("file_name.xml")));

// then you need to configure the RunListener to be used by JUnit, depending on your setup. Have a look at
// org.junit.runner.JUnitCore as well as uk.ac.gold.doc.junitXmlFormatter.Runner
```

*Commandline usage*:
```bash
# Run the test mypackage.Suite1, using uk.ac.gold.doc.junitXmlFormatter.Runner#main(String...) to run the tests
java -cp test-jar-with-dependencies.jar -Dorg.schmant.task.junit4.target=junit_report.xml uk.ac.gold.doc.junitXmlFormatter.Runner mypackage.Suite1
```




