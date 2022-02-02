# 🏠프로젝트 개요
![logo](https://user-images.githubusercontent.com/69866091/152042620-36f7eb57-6d89-4dbd-9a8d-7bb7b0bfd19a.png)

> 마을변호사 제도의 사용 방법을 안내하고 변호사 검색을 통한 무료 법률 상담 신청, 사이버법률상담 등을 제공하는 웹 서비스입니다. </br>

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
|• 메인 페이지 <br> • 상담 예약 신청 목록 |• 사용자 로그인 </br> • 변호사 검색 </br> • 사이버법률상담 |• 변호사 로그인 </br> • 상담 예약 신청 페이지 </br> • 사이버법률상담
<br/>


# 🏠기능 구현 사항

프로그램은 프롬프트에서 주어진 명령어를 수행하는 프로세스와 지정한 디렉토리의 파일 변경 상태를 모니터링하는 프로세스로 나뉘어지고, 모니터링 프로그램은 디몬 프로세스로 구현하였습니다. 


## 함수 간 Call Graph
![제목 없음](https://user-images.githubusercontent.com/69866091/151962868-cf01e944-a0f5-4dc7-93d0-222db2a7a5ae.png)

  
## 함수 기능별 흐름도
![main](https://user-images.githubusercontent.com/69866091/152007369-565eff88-a5f1-4235-8c7f-08be58de03e8.png)

- int ssu_daemon(void); <br/>
데몬 프로세스를 생성하여 파일의 삭제, 생성, 수정을 모니터링하며 log를 남기는 함수

![ssu_daemon](https://user-images.githubusercontent.com/69866091/152003543-1dae7f51-251a-48a3-948c-eecdb4f38523.png)

- void cmd_delete(char *filename, char endtime[ ], char buf[ ]); <br/>
프롬프트에서 입력받은 파일이 지정한 디렉토리에 존재하는지 확인한 후, endtime을 입력 받았는지의 유무에 따라 trash 디렉토리를 생성하고, 삭제 동작을 수행하는 함수

![cmd_delete](https://user-images.githubusercontent.com/69866091/152003550-34ae1976-6bcf-459c-a1a2-717c76275f87.png)

- void calculate_infofile_size(void); <br/>
info 파일의 크기를 계산하는 함수

![calculate](https://user-images.githubusercontent.com/69866091/152005981-58bb192c-8164-42df-81ce-d90c1d7a08ff.png)

- void delete_oldfile(off_t infofile_size); <br/>
info 파일에 저장된 삭제 시간을 기준으로 파일을 비교하여 삭제 시간이 가장 오래된 파일을 찾고, 해당 파일을 삭제하는 함수

![delete_oldfile](https://user-images.githubusercontent.com/69866091/152006085-8ae3c8cf-362e-4081-bf3f-548994d3e8f9.png)

- void cmd_recover(char *filename, char buf[ ]); <br/>
프롬프트에서 입력받은 파일이 trash 디렉토리에 존재하는지 확인 후, 파일을 원래 경로로 복구하고 info 파일을 삭제하는 함수

![recover](https://user-images.githubusercontent.com/69866091/152006231-aaa307a0-ac09-4709-b7e3-df02100d679b.png)
<br/>
<br/>


# 🏠결과 화면
