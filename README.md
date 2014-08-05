sonar-docker
============

Dockerfile to create [SonarQube](http://www.sonarqube.org/) 4.4 server with existing MySQL server.


### Normal container
Use the `Dockerfile` to build an image. Run the container with environment variables, `DB_USERNAME`, `DB_PASSWORD` and `DB_URL`. A database `sonar` should be created first on the MySQL server.

Example command line to run:

```bash
docker run -i -t -e DB_USERNAME=sonar -e DB_PASSWORD=password -e DB_URL=mysqlserver:3306 -p 80:9000 <Image ID>
```

Then you can access `http://localhost` to use Sonar.

### AWS Elastic Beanstalk

If you want to run SonarQube on [AWS Elastic Beanstalk](http://aws.amazon.com/elasticbeanstalk/), you need to specify values of environment variables `DB_USERNAME`, `DB_PASSWORD` and `DB_URL` in Beanstalk console. Refer to [here](http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker.container.console.html) for more details.

It's better that package the `Dockerfile` and `Dockerrun.aws.json` in a zip file and use it.