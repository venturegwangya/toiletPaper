---
sidebar_position: 1
---

# 기여하는 법

대똥여지도 개발 가이드

## 개발 프로세스

- [깃허브 프로젝트 페이지로 이슈 상태 관리](https://github.com/venturegwangya/toiletMap/projects)를 합니다.
- 프로젝트 칸반 `할일 목록`에 진행해야할 이슈가 없다면 노트를 생성합니다. 노트의 더보기(...) 메뉴를 이용하여 이슈로 변환합니다.
- 진행할 이슈를 `진행중`으로 옮깁니다. 필요하다면 자신을 assign합니다.
- 기본적으로 다음 브랜치 전략를 따릅니다.
  - `main`은 배포용 브랜치입니다.
  - `develop`은 개발용 브랜치입니다. 개발시에는 여기서 시작합니다.
  - 이슈를 진행할때는 `develop` 브랜치에서 `feature/#이슈번호` 브랜치를 생성하여 진행해주세요.
  - `feature/#이슈번호`의 개발사항을 반영하고 싶을 때는 Pull Request(PR)를 생성하고 `develop`으로 병합을 시도합니다.
  - PR의 내용은 다음을 따라주세요. (템를릿에도 설명이 되어있습니다.)
    - resolves #이슈번호, fix #이슈번호 를 입력하여 병합시 이슈가 종료되게 합니다.
    - 위를 작성하지 않은 경우, 완료된 이슈는 직접 닫아주세요
    - 진행한 내용을 간략히 설명해주세요.

## 로컬 개발

로컬에서 개발하기 위해서 다음을 참조합니다.

- `yarn` 의존성 설치 후 `yarn start`로 개발을 시작합니다.
- 로컬에서 firebase관련 기능 및 데이터를 사용하기 위해 다음이 필요합니다.
  - firebase 로컬 에뮬레이터 개발환경 설치(최초 설치시)
    - `firebase-cli` 설치 [참조](https://firebase.google.com/docs/cli#mac-linux-npm)
    - [자바 1.8 이상](https://www.java.com/ko/download/) 설치
    - `firebase init emulators`
      - existing project를 선택하고
      - Auth와 firestore 설치한다. 포트값은 기본값 그대로 사용. (추후 더 상세히 업데이트)
- 이후에는 `yarn local-server`를 통해 firebase 로컬 에뮬레이터 실행하여 로컬 환경에서 firebase 기능을 사용할 수 있습니다.
