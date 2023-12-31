#   휴대폰의 NFC 기능을 활용한 방명록 프로그램
파이썬과 아두이노간의 시리얼 통신을 기반으로 한 전자 방문록 프로그램입니다.   
파이썬 GUI(tkinter)와 아두이노 rfid 센서를 중심적으로 이용하였습니다.   
RFID 태그나 휴대폰 NFC 기능을 이용하여 아두이노 센서에 태그하면,   
Database에서 방문 정보가 저장이 되고 파이썬 GUI에서 확인해 보실 수 있습니다.   
GUI 프로그램이 실행되는 동시에 thread로 아두이노 보드와 시리얼 통신이 이루어집니다.   
  
### ※ 주의 사항   
'Guest_rfid.ino' 파일을 아두이노에 업로드 해 아두이노 회로에 연결한 후    
전자 방문록 GUI 프로그램을 실행시키면 전자 방문록 프로그램을 이용할 수 있습니다.   
GUI 프로그램을 실행하면, COM 포트 번호를 입력받는 창이 나오므로 
장치관리자에서 확인한 아두이노에 연결한 포트 번호를 입력해주면 시리얼 통신이 정상적으로 이루어집니다.    
또한, exe 파일 실행시 사진 및 음악파일의 경로를 알맞게 위치시켜야 파일이 실행됩니다. (파일 위치를 변경할 때 주의해주세요)   

# 전자 방문록 프로그램
방명록 프로그램으로 이 프로젝트는 아두이노, 파이썬 GUI, 그리고 데이터베이스를 통합하여 개발하였습니다. 
사용자 정보를 효과적으로 기록하고 관리하는 것을 목표로 했습니다. 
프로그램은 특히 이벤트나 행사 현장에서 참가자들의 정보를 간편하게 수집하고 저장하기 위해 설계되었습니다.
## 사용한 모듈 & 라이브러리
#### 파이썬
    1. tkinter: GUI를 구성하기 위해 사용한 모듈입니다.
    2. threading: 여러 이벤트와 동작을 동시에 처리하기 위해 사용한 모듈입니다.
    3. sqlite3: 점수를 저장하기 위해 사용한 Database 모듈입니다.
    4. pyglet: GUI에 폰트를 사용하기 위해 폰트를 추가해주는 모듈입니다.
    5. pillow: 이미지를 처리하기 위해 사용한 라이브러리 입니다.
    6. os: 사진 파일의 위치를 쉽게 지정해주기 위해 사용한 모듈입니다.
    7. pyinstaller: python 파일을 exe 파일로 변환하기 위해서 사용한 라이브러리입니다.
    8. serial: 아두이노와의 시리얼 통신을 위해 사용한 라이브러리입니다.
    (참고 : serial이 아니라 pyserial을 install 해줘야 합니다.)
    9. time: 현재 시간을 받아오기 위해 사용한 모듈입니다.

#### 아두이노
    1. MFRC522: Rfid 센서를 이용하기 위해 사용한 라이브러리입니다.

## 기능   
### 아두이노   
    - RFID 태그를 인식 받습니다.   
    - 태그가 인식되면 LED의 불을 바꿈과 동시에 피에조 부저에서 소리가 나게 합니다.    
    - 시리얼 통신을 통해 RFID 태그 번호를 파이썬 GUI 프로그램에 전달 해 줍니다.   
### 파이썬 GUI 프로그램   
    - 시리얼 통신을 통해 RFID 태그 번호를 전달 받습니다.   
    - 전달 받은 태그 번호를 이용해 회원가입을 할 수 있으며 전자 방명록을 자동 작성할 수 있습니다.   
    - 작성된 전자 방명록을 원하는 방식으로 정렬하여 확인해 볼 수 있습니다.    
### Database
    - 태그 번호를 이용해서 회원 목록을 저장해줍니다.
    - 전자 방문록 내용을 저장해줍니다.
***

***
## 실행사진
<img src="https://github.com/2023-CLASS-2-Creative-ENG-Design/9team/assets/96522559/0926022c-a011-44ac-98c8-ea9a196efe07" alt="메인화면" width="550" height="500"/>
<img src="https://github.com/2023-CLASS-2-Creative-ENG-Design/9team/assets/96522559/335d29d2-4b04-4c5a-9198-23457e8e986f" alt="방명록_2" width="550" height="500"/>
