# JavaHerokuProcfile

Java application (with Procfile) showing how to deploy on Heroku. 

See Medium article [Java on Heroku: Common Pitfalls and Mistakes](https://medium.com/geekculture/java-on-heroku-common-pitfalls-and-mistakes-40f8ea32f104)

Clone and mirror this repository
```
git clone --bare https://github.com/gcatanese/javaHerokuProcfile.git
cd javaHerokuProcfile
git push --mirror https://github.com/{my_username}/javaHerokuProcfile.git
cd ..
cd javaHerokuProcfile
```

Create a new Heroku application via the Heroku Dashboard or using the Heroku CLI
```
heroku apps:create javaherokuprocfile --region=eu
```
Deploy
```
git push heroku main
```

### Local library

Deploy the local library in the file-based repository
```
mvn deploy:deploy-file -Durl=file:repo/ -Dfile=lib/simpleLib-0.0.1-SNAPSHOT.jar -DgroupId=com.perosa 
 -DartifactId=simpleLib -Dpackaging=jar -Dversion=0.0.1-SNAPSHOT
```

**Note**: the local library is already installed in the project (see `repo` folder)