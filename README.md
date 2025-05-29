# OpenSearch 실행 및 관리 가이드

## 1. OpenSearch 컨테이너 실행하기

```bash
# 도커 컴포즈로 컨테이너를 백그라운드 실행 (터미널 로그 차지하지 않음)
docker compose up -d
-d 옵션은 detached 모드로 실행한다는 뜻입니다.

즉, 백그라운드에서 실행되어 터미널을 차지하지 않고 명령어를 바로 입력할 수 있습니다.
```

## 2. OpenSearch 컨테이너 중지 및 삭제
# 컨테이너 및 네트워크만 삭제
docker compose down

# 컨테이너, 네트워크, 볼륨(데이터)까지 모두 삭제하여 완전 초기화
docker compose down -v

## 3. OpenSearch 접속 테스트

# 인증 없이 (보안 플러그인 비활성화 시)
curl -u  -XGET 'http://localhost:9200'

# 인증 필요 시 (admin 사용자 예시)
curl -u admin:Brandi2025# -XGET 'http://localhost:9200'

## 4. 컨테이너 로그 확인
docker logs opensearch
