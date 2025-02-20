# 9주차 성능 최적화 과제

## 기본 과제: 프론트엔드 배포 파이프 라인

### 개요

사진
GitHub Actions에 워크플로우를 작성해 다음과 같이 배포가 진행되도록 합니다.

(사전작업: Ubuntu 최신 버전 설치)

1. Checkout 액션을 사용해 코드 내려받기
2. `npm ci` 명령어로 프로젝트 의존성 설치
3. `npm run build` 명령어로 Next.js 프로젝트 빌드
4. AWS 자격 증명 구성
5. 빌드된 파일을 S3 버킷에 동기화
6. CloudFront 캐시 무효화

### 인프라 환경 구현 과정

1. git repo 구현
2. next.js 프로젝트 생성
3. Amazon S3 bucket 생성 및 폴더 업로드
4. Amazon Cloudfront와 S3 연동하여 배포
5. Amazon IAM 권한 정책 설정
6. git repo 환경 변수 추가 등록

```bash
 AWS_ACCESS_KEY_ID : aws IAM public accesskey
 AWS_SECRET_ACCESS_KEY : aws IAM private accesskey
 AWS_REGION : AWS region
 S3_BUCKET_NAME : s3 버킷 이름
 CLOUDFRONT_DISTRIBUTION_ID : CloudFront 배포 ID
```

### 주요 링크

- S3 버킷 웹사이트 엔드포인트: http://performance-juyoung.s3-website-us-east-1.amazonaws.com/
- CloudFrount 배포 도메인 이름: https://dy7o03uuc4sgv.cloudfront.net/

## 주요 개념

### GitHub Actions과 CI/CD 도구

#### GitHub Actions

"GitHub Actions는 개발의 효율성을 높이는데 사용합니다."

- 용도 및 정의
  GitHub Actions는 GitHub의 자동화 도구입니다. 단순한 것에서 복잡한 워크 플로우를 구축하여 소프트웨어 개발을 자동화하는데 사용됩니다.

- 특징

1. 개발, 테스트, 배포 등의 워크플로우를 깃헙 저장소 내에서 직접 관리할 수 있다.
2. yaml 파일을 활용하여 워크플로우를 쉽게 설정할 수 있다.
3. 외부 도구를 관리하거나 추가적인 인프라 설정이 필요 없다.
4. 다양한 플랫폼 지원 (Linux, Windows, macOS).
5. Github Free는 한달에 2000분 사용 가능하다.
6. 다양한 이벤트에 따라 실행하는 워크 플로우가 특징

#### CI/CD란?

- 정의
  CI(Continuous Integration) & CD(Continuose Delivery or Deployment)의 준말

- 용도
  CI : 레포지토리 내의 코드 변경 사항에 대해 자동으로 테스트 실행 하는데 사용, 즉 문제를 빠르게 발견해서 더 안정적으로 개발할 수 있게 도와준다.
  CD : 코드 변경 사항이 실제 배포 환경에 자동으로 배포

- 구성
  CI : 주로 PR이 Open 상태이거나 Synchronize될 경우 트리거
  CD : PR이 merge될 경우 트리거

### S3와 스토리지

### CloudFront와 CDN

### 캐시 무효화(Cache Invalidation)

### Repository secret과 환경변수

## 심화 과제: CDN 최적화 보고서 작성
