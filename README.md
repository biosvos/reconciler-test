# operator sdk 초기화
```bash
go mod init github.com/biosvos/reconciler-test
operator-sdk init --domain github.com
```
> github.com/biosvos/reconciler-test 는 적절히 바꿔야 한다.

# resource 추가
```bash
operator-sdk create api \
--group=test \
--version=v1 \
--kind=Test \
--resource=true \
--controller=true
```

# resource 구조체 변경
[test resource](api/v1/test_types.go)에서 구조체 변경
```bash
make manifests
```

# controller 변경
[test controller](controllers/test_controller.go) 변경

# operator 실행
```bash
make install
make run
```

# resource 생성
```bash
kubectl apply -f example/test.yaml
```

# resource 확인
```bash
kubectl get -f example/test.yaml -o yaml
```

# 가설
[가설 1](hypothesis1.md)