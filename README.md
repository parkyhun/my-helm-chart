
## 나만의 helm chart 를 만들고 github pages 로 배포해보자

### 작성한 chart 가 잘 실행되는지 확인해 보자

```bash
# docs 폴더 준비하기
mkdir -p docs
# 우리가 만든 chart 를 압축해서 docs/ 폴더안에 저장
helm package charts/helm01_member -d docs/
# index.yaml 파일을 docs/ 폴더에 생성하기
helm repo index docs/ --url https://나의github아이디.github.io/저장소이름/
helm repo index docs/ --url https://yy9976com.github.io/my-helm-chart/

git add ./docs
git commit -m "release: member-app chart v1.0.0 package"
git push 
```

### push 후에 github 에 pages 에 관련된 설정 을 1번만 해주면 다음부터는 자동으로 pages 에 반영된다 

### 우리가 만든 helm chart 저장소를 사용해보기

```bash

helm repo add my-repo https://parkyhun.github.io/my-helm-chart/
# helm 저장소 목록 확인
helm repo ls
# 업데이트 확인
helm repo update
# 저장소에 어떤 chart 들이 있는지 검색 
helm search repo my-repo
NAME                    CHART VERSION   APP VERSION     DESCRIPTION               
my-repo/member-app      0.1.0           1.0.0.          fastapi member application

# github pages 에서 내려 받은 helm chart 를 배포해보기
helm install member-release my-repo/member-app -n helm01 --create-namespace 

```