---
sidebar_position: 2
---

# 개발 설계

TODO: 일단 notion에서 대충 가져옴. 나중에 구조화하고 정리해야함

- 데이터 모델 설계
- firebase rules

## 해결해야할 문제

2021/05

TODO: 체크리스트로 바꾸고, 고려가 끝난 사항은 선긋기/ 체크 처리

- 사용자가 새로이 등록한 화장실 마커
  - 무엇으로 구분해야하나? Geopoint로 하면 수치가 살짝 어긋나는 경우 같은 장소인데 다른 장소로 인식될 수 있다. 어떻게 해결할 것인가?
- 카카오 API의 정보를 Migration해야하나?
  - 카카오 API 사용할 시: 요청 > 다시 DB에 등록 > 범위 query 요청으로 DB에서 가져옴
- 개방 화장실 데이터가 엄청 정확하지 않음.

  - 공공 데이터 필요한 정보 추려서 FirebaseDB에 등록?
  - [https://www.data.go.kr/data/15012892/standard.do](https://www.data.go.kr/data/15012892/standard.do)

- geoPoint 범위 쿼리로 화장실 데이터를 가져온다
- 가져온 데이터를 마커로 표시한다.
- 마커를 선택하면 화장실의 id를 이용하여 나머지 리뷰에 담긴 정보를 가져온다.
  - 화장실 자체의 정보
    - 장애인 화장실 여부 등? 이미 있는 데이터를 사용할 것인지? 그런 경우 리뷰에서 가져오는게 아님?
      - 있음 체크 값 증가만 하도록? 있다고 한 사람
      - 비밀번호 있음
    - 만약 신규 등록되는 화장실은 어떤식으로 할 것인지?
  - 리뷰의 정보
    - 점수
- 리뷰를 등록한다.
  - 화장실에 대한 데이터 Update? 한번만 가능? 음...
  - 리뷰에 대한 데이터만 Update?
- 지역 쿼리

  - [https://github.com/MichaelSolati/geofirestore-js](https://github.com/MichaelSolati/geofirestore-js)
  - [https://stackoverflow.com/questions/46630507/how-to-run-a-geo-nearby-query-with-firestore#comment93286256_46920982](https://stackoverflow.com/questions/46630507/how-to-run-a-geo-nearby-query-with-firestore#comment93286256_46920982)

- firebase 이용해서 전체 조회해서 계산해야하는 데이터 처리를 어떤식으로 하는지?
