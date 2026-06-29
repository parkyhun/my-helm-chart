# member-releasc 라는 이름으로 배포하겠다 네임스페이스는 helm01 
helm install member-releasc ./helm01_member -n helm01 --create-namespace

# 삭제하는 방법
helm uninstall member-releasc -n helm01