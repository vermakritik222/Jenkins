
```powershell
docker image build -t custom-jenkins-docker .
```

```powershell
docker run -it -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v jenkins_home:/var/jenkins_home custom-jenkins-docker
```