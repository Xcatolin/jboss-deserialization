# JBoss Insecure Deserialization to RCE via CVE-2017-12149.
JBoss Insecure Deserialization - RCE Exploitation Lab.


The idea here is to setup a lab with an old JBoss version (<7.0) in order to exploit the vulnerability.

We can use Docker to facilitate all the process. For this, we're gonna need an Oracle JDK rpm package, that's because JBoss 6.0.0 final works with a JDK 6 runtime. We're also gonna need the Dockerfile present in the repository, and obviously Docker installed on the system. Just make sure to have all files in the same directory.

1. Clone this repository with `git clone https://github.com/Xcatolin/jboss-deserialization`
2. Download the [jdk-6u45-linux-x64.rpm.bin](https://www.oracle.com/java/technologies/javase-java-archive-javase6-downloads.html#jdk-6u45-oth-JPR) package and move it into the same directory as the Dockerfile (you can use an temporary e-mail address to register)
3. Build the image with `docker build -t docker build -t Xcatolin/jboss-deserialization .`
4. Run the image with `docker run -it -p 8080:8080 Xcatolin/jboss-deserialization`
5. Click [here](http://localhost:8080) to validate if it worked, you should see the JBoss main page


## References
* [ovanekem/docker-jboss-6.0.0.final](https://github.com/ovanekem/docker-jboss-6.0.0.final)
