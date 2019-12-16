# kubernetes-study

```
docker build . -t kubernetes-study
docker run -p 5000:5000 kubernetes-study
```

```
awsudo -u stats kubectl create sa fluent-bit
```

## Trouble Shooting

eksctl 로 cluster 를 생성했다면 자동으로 되지만, 아니라면 update-kubeconfig 가 필요하다.

```
awsudo -u stats aws eks update-kubeconfig --name kubernetes-study
```

apply 가 안되서 보니까 kubectl client version 문제였다. 
brew upgrade 해도 client version 이 그대로였는데, 
brew 로 설치한게 아니라 다른 binary 가 경로에 잡히고 있었다. 
/usr/local/bin/kubectl 을 제거한 뒤 brew 로 설치한 kubectl 을 연결한다.

```
brew link kubectl
```
