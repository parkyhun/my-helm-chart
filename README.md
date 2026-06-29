
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
```

