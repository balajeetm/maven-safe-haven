# maven-safe-haven

Hi Unjars (short for unjargoners),<br>
Hopefully, you are coming over from my blog post on [Why Maven?](http://blog.balajeetm.com/blog/2017/02/14/why-maven/) and [Maven-Safe-Haven](http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/). If not, do visit them and get back here so you can easily connect the dots.

In this sample project I've created a project structure as below

![projectStructure](/assets/projectStructure.png)

Its a [multi module maven project](https://maven.apache.org/guides/mini/guide-multiple-modules.html), consisting of
* maven-safe-haven - The parent
* lib-b - Child Module dependent on [gson-utils](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.balajeetm.mystique%22%20AND%20a%3A%22gson-utils%22), a library from [json-mystique](http://github.balajeetm.com/json-mystique)
* lib-a - Child Module dependent on lib-b and [gson-utils](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.balajeetm.mystique%22%20AND%20a%3A%22gson-utils%22), a library from [json-mystique](http://github.balajeetm.com/json-mystique)

Now, if you recollect our discussion on my [blog](http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/), we were discussing conflict resolution and picked a scenario as below

![Conflict-Resolution](http://blog.balajeetm.com/assets/2017-02-17/ConflictResolution.png)

The library names used their was generic. Considering the current project structure, the updated scenario would like below with explicit library names and versions

![ConflictResolution](/assets/conflictResolution.png)

For simplicity, the maven projects are packaged as poms and not jars, since we are more interested in understanding maven's conflict resolution rather than any core functionality.<br>
Great then, let's start grinding, shall we?

## Guide to verify conflict resolution

* **Step 1**<br>
Import the project in some IDE (Eclipse, STS, etc)

* **Step 2**<br>
Open the [pom.xml](https://github.com/balajeetm/maven-safe-haven/blob/master/lib-a/pom.xml) of lib-a module

* **Step 3**<br>
Choose the Dependency Hierarchy Tab in STS/Eclipse.<br>
>**Note** - Alternatively, you can run the maven command "mvn dependency:tree" and see the maven dependency tree on the console. The UI look is much better and easier to understand, so I'm going ahead and using the STS UI

The dependency Hierarchy Tab will be as below. The left pane shows the dependency hierarchy and the right pane shows the final resolved jars with versions in the classpath

![Dependency Hierarchy Button](/assets/dependencyHierarchy.png)

* **Step 4**<br>
On the top right corner, type lib-b in the filter checkbox. You will see the tab updated as below. This is straight forward. No magic here. There is only one version lib-b, so the version 0.0.1 is shown

![lib-a](/assets/lib-a.png)

* **Step5**
Now filter for gson-utils. The dependency tab will be updated as below

![gson-utils](/assets/gson-utils.png)


Basic maven tutorial - http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/
