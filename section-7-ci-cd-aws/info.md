# Continous integration and deployment with aws

Step

a. Travis CI
1. Create github repo, put project folder inside. Repo name = docker-react
2. Sign in to travis ci with github sign in
3. Open settings, search repo docker-react.
4. Enable ci cd by toggle

b. AWS EBS

1. Create new ebs apps
2. Fill 

```
application name = docker-react
```
3. Create a new web apps, fill

```sh
Application name = docker-react
Platform = docker
Application code = sample application
```

4. Create .travis.yml
5. Fill .travis.yml

c. IAM

1. Choose users
2. Add users
3. Fill username
4. Choose programmatic access and aws management console
5. Attach existing policies, choose full access for elasticbeanstalk
6. After success user, copy access key id, secret access key, and password

d. Travis CI

1. Open repo docker-react, click setting
2. Add new env with access key and secret access key