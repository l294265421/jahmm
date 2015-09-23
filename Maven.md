# Introduction #

`Jahmm` uses the Maven build tool.  The URL of Jahmm's Maven repository is:
http://jahmm.googlecode.com/svn/repo

You might want to include:
```
        <repository>
          <id>Jahmm</id>
          <name>Jahmm HMM library repository</name>
          <url>http://jahmm.googlecode.com/svn/repo</url>
        </repository>
```
in your `settings.xml` or `pom.xml` file.

If your project depends on Jahmm, add a dependency tag to your project's pom.xml `dependencies` section  file:
```
      <dependency>
        <groupId>be.ac.ulg.montefiore.run.jahmm</groupId>
        <artifactId>jahmm</artifactId>
        <version>0.6.2</version>
      </dependency>
```



---


# Don't read this #

This explains how to release a new version of `Jahmm`.  You should not read this.

The "mvn release:prepare/release:perform" doesn't work in this setup (some svn operation is not permitted on the Google SVN setup).  To do it by hand:

Modify the pom.xml file:
- remove SNAPSHOT
- replace svn string with something like
> 

&lt;connection&gt;

scm:svn:https://jahmm.googlecode.com/svn/tags/release-0.6.2

&lt;/connection&gt;


- svn commit -m "release setup"
- deploy to the remote repository.  The -Prelease tag builds javadoc and sources
> mvn -Prelease deploy
- svn tag (don't forget to change the version nb):
> svn copy https://jahmm.googlecode.com/svn/trunk https://jahmm.googlecode.com/svn/tags/release-0.6.2 -m "Tagging the 0.6.2 release"
- switch to next version nb in both pom.xml and build.xml
- svn commit -m "updated for next development cycle"
- to deploy the javadoc directory; If the '0.6.2' directory contains the javadoc:
> > svn import -m "add javadoc" 0.6.2 https://jahmm.googlecode.com/svn/javadoc/0.6.2