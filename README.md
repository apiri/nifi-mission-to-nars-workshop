![Apache NiFi logo](http://nifi.apache.org/images/niFi-logo-horizontal.png "Apache NiFi")
# _Mission to NARs_ Apache NiFi Workshop
Thursday, 12 May, 2016

_These instructions are available at: https://github.com/apiri/nifi-mission-to-nars-workshop/blob/master/README.md_

**Note:** Feel free to [open an issue on the GitHub repository](https://github.com/apiri/nifi-mission-to-nars-workshop/issues) with any questions or points that may be unclear!

******

# What should I do before arriving?
Due to possible network congestion, the following items will help us ensure we can maximize our time during the workshop.

## 1. Acquire a copy of Apache NiFi (.tar.gz or .zip) - 0.6.1
- tar.gz file - https://www.apache.org/dyn/closer.lua?path=/nifi/0.6.1/nifi-0.6.1-bin.tar.gz
- .zip file   - https://www.apache.org/dyn/closer.lua?path=/nifi/0.6.1/nifi-0.6.1-bin.zip

## 2. Establish Development Environment
Creating custom components in NiFi requires only two dependencies, Java JDK and Maven.  We will additionally require Git to make use of a sample repository.

- **Java SDK (Version 7+ required)**
  - Do I need it?

    Execute `javac -version`.  If an error message about the command not being found or the response shows `javac 1.X.Y_ZZ` has X being less than 7, then JDK version 7 or later must be installed.
  - Install

    Available for download via: [http://www.oracle.com/technetwork/java/javase/overview/index.html](http://www.oracle.com/technetwork/java/javase/overview/index.html)

    _Linux_: OpenJDK versions 7+ are also supported and available

- **Maven (requires version 3.1.0+)**
  - Do I need it?

    Execute `mvn -version`.  If an error message about the command not being found or the response shows `Apache Maven 3.X.Y` has X being less than 1, then Maven 3.1.0 or later must be installed.

  - Install

    Available via [http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)

    Also available via homebrew for OS X and various Linux package management systems

- **Git**
  - Do I need it?

    Execute `git --version`.  If an error message about the command not being found then git must be installed.

  - Install
    - _Windows_

      **Executable client**:  [https://git-scm.com/download/linux](https://git-scm.com/download/linux)
    - _OS X_

      A version is bundled with the Mac by default.  A newer version is available via the homebrew ecosystem: [http://brew.sh/](http://brew.sh/)

    - _Linux_
      - **Aptitude based systems (Debian, Ubuntu)**:  `apt-get install git`
      - **Yum based systems (RHEL, CentOS, Fedora)**:  `yum install git`
      - **Other distributions**:  [https://git-scm.com/download/linux](https://git-scm.com/download/linux)


## 3. Check out the sample repository and cache Maven artifacts
* Check out the sample repository
`git clone https://github.com/apiri/nifi-mission-to-nars-workshop.git`
* Change directory to the checked out source
`cd nifi-mission-to-nars-workshop/nars-workshop`
* Perform a Maven build to cache all Maven artifacts
`mvn clean install`

******

# Day of the Workshop

The following are some references we will make use of throughout the course of the presentation.

* CollabEdit Document: http://collabedit.com/4k8fe
* Workshop GitHub Repository: https://github.com/apiri/nifi-mission-to-nars-workshop
* RandomUser.me:  https://randomuser.me/
  * Sample Query (50 Results in CSV Format): http://api.randomuser.me/?results=50&fmt=csv

## Developing Custom Extensions from Archetype
We only need the repository checked out above, but in the case someone wishes to start from nothing, it is possible to generate the project structure above leveraging Maven Archetypes.

### Making use of the [Apache NiFi Maven Archetypes](https://cwiki.apache.org/confluence/display/NIFI/Maven+Projects+for+Extensions)
* **[Processor Bundles](https://cwiki.apache.org/confluence/display/NIFI/Maven+Projects+for+Extensions#MavenProjectsforExtensions-MavenProcessorArchetype)**

Create using

```
mvn archetype:generate
	-DarchetypeGroupId=org.apache.nifi  
	-DarchetypeArtifactId=nifi-processor-bundle-archetype  
	-DarchetypeVersion=0.6.1   
	-DnifiVersion=0.6.1
```

* **[Controller Service Bundles](https://cwiki.apache.org/confluence/display/NIFI/Maven+Projects+for+Extensions#MavenProjectsforExtensions-ControllerServiceProjects)**

Create using

```
mvn archetype:generate
	-DarchetypeGroupId=org.apache.nifi  
	-DarchetypeArtifactId=nifi-service-bundle-archetype  
	-DarchetypeVersion=0.6.1   
	-DnifiVersion=0.6.1
```
