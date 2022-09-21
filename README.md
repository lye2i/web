# 🏠프로젝트 개요
![logo](https://user-images.githubusercontent.com/69866091/152042620-36f7eb57-6d89-4dbd-9a8d-7bb7b0bfd19a.png)

> 마을변호사 제도의 이용 방법을 안내하고 변호사 검색을 통한 무료 법률 상담 신청, 사이버법률상담 등을 제공하는 웹 서비스입니다. </br>

변호사 검색 시, 마을 변호사 배정 현황을 파악하기 위해 [**공공데이터포털**](https://www.data.go.kr/) 의 open API를 사용하였습니다.
</br>
</br>

## 개발 배경
마을변호사 제도란, 지역의 마을변호사로 위촉된 변호사가 일상에서 발생하는 마을 주민들의 법률문제를 무료로 상담해주고 필요한 법적 절차를 안내하는 서비스입니다.
기존의 마을변호사 제도 이용 방식은 다음과 같습니다.

1. 각 지역의 홈페이지에서 '우리 동네 정기 상담일’ 메뉴를 활용하여 담당 마을변호사 상담일 확인
2. 주민센터에 방문하여 법률상담카드 작성 후, 제출
3. 혹은, 해당 지역 주민센터에 직접 전화로 상담 접수

이는 각 지역 홈페이지에서 마을 변호사 관련 페이지로의 접근이 어렵고 동사무소, 주민센터를 통해 상담이 접수되므로 이용이 불편하다는 단점이 있습니다.
또한 마을변호사 제도의 홍보효과가 미미하다는 한계점을 지니고 있습니다.

따라서 마을변호사 제도 및 사용 방법을 안내하고 변호사 검색을 통한 무료 법률 상담 신청, 사이버법률상담 기능을 제공하는 웹 서비스(이하  &nbsp; `우리 마을 변호사`)를 제안하게 되었습니다.


## 주요 기능
- 변호사 검색
- 상담 예약 신청
- 사이버법률상담
- 마을변호사 소식

## API
[**공공데이터포털**](https://www.data.go.kr/)
- 법무부_마을변호사 지역별 배정 현황
- 법무부_마을변호사 제도 홍보동영상

## 팀원 및 역할분담
|[@rlagksql219](https://github.com/rlagksql219)|[lye2i](https://github.com/lye2i)|[@y78462](https://github.com/y78462)|
|------|----|----|
|• 메인 페이지 <br> • 상담 신청 게시판 |• 사용자 로그인 </br> • 변호사 검색 </br> • 사이버법률상담 |• 변호사 로그인 </br> • 상담 예약 신청 페이지 </br> • 사이버법률상담
<br/>


# 🏠프론트엔드 기능 구현 사항
페이지 간 데이터 전송 시, `HTML5` form 태그 GET 방식을 이용하여 프론트엔드를 개발하였습니다.

>  ✨[demo video](https://youtu.be/7f7WY5o7R0Y)<br/>

## 주요 기능
- **회원가입**

- **사용자 로그인 & 변호사 로그인**
    - 사용자 로그인 메인 페이지와 변호사 로그인 메인 페이지 별도 구성
         - 변호사 로그인 메인 페이지에 '상담 신청 게시판' 메뉴 추가

- **변호사 검색**
    - `Javascript`를 이용하여 select box에 동적으로 옵션 추가
    - `Javascript`를 이용하여 테이블 동적 생성

- **상담 예약 신청**
    - `HTML5` 상담 신청 시, 실명 사용을 위해 input 태그 readonly 속성 이용
    -  `Web Storage`의 localStorage를 이용하여 데이터 저장

- **상담 신청 게시판**
   - `Javascript`를 이용하여 테이블 동적 생성
   - 동적으로 생성한 table에 row 단위로 클릭 리스너가 동작하도록 `jquery` 이용
   - `Web Storage`의 localStorage를 이용하여 데이터 저장

- **사이버법률상담**
   - `Web Storage`의 localStorage를 이용하여 데이터 저장

- **이용 안내**
   - 시민법률사무소 지도

- **마을변호사 소식**
   - `HTML5` iframe 태그로 마을변호사 블로그 페이지 불러옴

- **자주 묻는 질문 Q&A**
   - 애니메이션으로 구현

## task 목록
![image01](https://user-images.githubusercontent.com/69866091/152188737-7e0e9cff-7758-49a2-8af6-f0d546444a0f.png)


# 🏠결과 화면

### ✨메인 페이지
![1 메인 페이지](https://user-images.githubusercontent.com/69866091/152214705-14322e6a-5cdb-44e1-8f3c-c8d13d4aa732.gif)

### ✨회원가입
![2 회원가입](https://user-images.githubusercontent.com/69866091/152214715-b78c6a03-9715-4c2e-8617-3e05bf857f95.gif)

### ✨사용자 로그인
![3 사용자 로그인](https://user-images.githubusercontent.com/69866091/152214728-cf68fda2-ddfa-45a8-8a7d-8dc5a050a09e.gif)

### ✨변호사 로그인
![4 변호사 로그인](https://user-images.githubusercontent.com/69866091/152216658-ea350084-bae4-4df1-b165-88c22a897fef.gif)

### ✨변호사 검색
![5 변호사 검색](https://user-images.githubusercontent.com/69866091/152214788-69dfe74a-e175-414b-99ae-75e1859b62ac.gif)

### ✨상담 예약 신청
![6 상담 예약 신청](https://user-images.githubusercontent.com/69866091/152217000-81007e75-9d3c-4ed2-a3ec-9b32ecc3c9cc.gif)

### ✨상담 신청 게시판
![7 상담신청 게시판](https://user-images.githubusercontent.com/69866091/152214836-12ef98ca-91e7-49e6-9bef-a04b5393b090.gif)

### ✨사이버법률상담 신청
![8 사이버법률상담 신청](https://user-images.githubusercontent.com/69866091/152216723-8e4eec60-5f80-4688-9b40-b74435e55edf.gif)

### ✨사이버법률상담 답변
![9 사이버법률상담 답변](https://user-images.githubusercontent.com/69866091/152214893-ae832fbe-9ed5-4297-b2b0-93dd47b38b35.gif)

### ✨사이버법률상담 목록
![10 사이버법률상담 목록](https://user-images.githubusercontent.com/69866091/152214914-41fc02b1-5fc7-45e6-8a2f-54589a1e6413.gif)

### ✨이용 안내
![11 이용 안내](https://user-images.githubusercontent.com/69866091/152214934-b2218745-1a2a-4785-8c29-37c9fac8f3da.gif)

### ✨시민법률사무소 지도
![12 시민법률사무소 지도](https://user-images.githubusercontent.com/69866091/152214968-4ce09097-0737-4add-881a-4b0b18610eec.gif)

### ✨마을변호사 소식
![13 마을변호사 소식](https://user-images.githubusercontent.com/69866091/152214978-2de3c474-7622-476e-bdcf-9fd85a28f3bf.gif)

### ✨자주 묻는 질문 Q&A
![14 자주 묻는 질문 Q A](https://user-images.githubusercontent.com/69866091/152215050-5affa814-2389-446f-9267-929c5d898c1c.gif)


