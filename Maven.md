Maven manage dependencies for you.

Maven Project:

1. pom.xml:

   1. in the dependcies part you specify hte dependcies you want

   2. GroupId - com.daniowang

   3. ArtifactID - demo

   4. Package - com.danio.demo.web <- this combines both the groupId and ArtifactIB together to form the package name.

      Every time you asks for a dependency, it would first go to the local repository. If the code is not in the local repository, it would then go the remote repository.