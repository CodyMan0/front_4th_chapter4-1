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

- GitHub Actions과 CI/CD 도구: \***\*\_\*\***
- S3와 스토리지: \***\*\_\*\***g
- CloudFront와 CDN: \***\*\_\*\***
- 캐시 무효화(Cache Invalidation): \***\*\_\*\***
- Repository secret과 환경변수: \***\*\_\*\***

## 심화 과제: CDN 최적화 보고서 작성
