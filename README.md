# maven-safe-haven

Hi Unjars (short for unjargoners),<br>
Hopefully, you are coming over from my blog post on [Why Maven?](http://blog.balajeetm.com/blog/2017/02/14/why-maven/) and [Maven-Safe-Haven](http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/). If not, do visit them and get back here so you can easily connect the dots.

In this sample project I've created a project structure as below

![projectStructure](/assets/projectStructure.png)

Its a [multi module maven project](https://maven.apache.org/guides/mini/guide-multiple-modules.html), consisting of
* maven-safe-haven - The parent
* lib-b - Child Module dependent on [json-mystique](http://github.balajeetm.com/json-mystique)
* lib-a - Child Module dependent on lib-b and [json-mystique](http://github.balajeetm.com/json-mystique)

Now, if you recollect our discussion on my [blog](http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/), we were discussing conflict resolution and picked a scenario as below

![Conlict-Resolution](http://blog.balajeetm.com/assets/2017-02-17/ConflictResolution.png)


Basic maven tutorial - http://blog.balajeetm.com/blog/2017/02/17/maven-safe-haven/
