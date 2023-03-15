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
--kind=test \
--resource=true \
--controller=true
```