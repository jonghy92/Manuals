# Virtual Env. Setting Manual


__개요:__ <br>
각각 프로젝트 마다 요구하는 library 버전이 다를 수가 있음. 한 pc에  프로젝트를 진행할 때마다 다른 버전을 깔았다 지웠다 할 수는 없다. (동시에 프로젝트를 진행할 수도 있기 때문에...) 따라서 `가상환경(독립된 환경)`을 만들어서 각 프로젝트 환경마다 필요한 라이브러리 버전을 맞춰주면 수월하게 작업을 할 수 있으므로 필수로 알아두어야 한다. `(개인적으로 conda & virtualenv 사용)`

<br>


## 1. virtualenv (Virtual + Environment)
- #### Install : pip install virtualenv 

<br>

#### Window 사용법:
1. 폴더 생성:
    - mkdir [폴더이름]
    - mkdir prj 

<br> 

2. 가상환경 구축:
    - virtualenv [환경이름]
    - virtualenv venv

<br>

3. 가상환경 실행:
    - .\ [환경이름]\Scripts\activate
    - .\venv\Scripts\activate
      - 혹은 Scripts 폴더로 이동 `activate.bat` 입력/실행 

<br>

1. 가상환경 설치된 라이브러리 확인:
    - pip list

<br>

5. 가상환경 라이브러리 설치:
    - pip install [라이브러리 이름] == [버전]
    - pip install pandas
    - pip install pandas == 1.53

<br>

6. 가상환경 종료:
    - deactivate

<br>

7. 가상환경 설치된 libraries 내보내기 | 설치:
   - pip freeze > requirements.txt
   - pip install -r requirements.txt