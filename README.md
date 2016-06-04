# mavenprofiles
Sample project to demonstrate maven profiles usage</br></br>
Most of the times a project will have different build flavours, dev, test, staging or prod. Depending on a build flavour the deployment params
will vary most of the times e.g when in dev mode your db URL will most likely be localhost and in prod it could be an external IP.
</br></br> At the same time, when running your integration tests, you don't want to run them against your production db because tests fixtures
could be the db data which is cleaned up before and after tests execution.
</br></br>Keeping in mind the fact that app constants that change based on the build environment should be saved in the .properties files,
and dynamically injected (filtered) in the app resource files, (in this case am referring to a spring framework app) having maven profiles
simplifies this task in that passing -P <profile> to the build command automatically sets the right params and seamlessly. 


<b>Building the project</b></br></br>
mvn clean compile -P test </br></br>
Use -P option to set the current build profile. By default dev profile is active.
