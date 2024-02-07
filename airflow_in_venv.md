### 가상환경 생성

- pip install virtualenv 
- python3 -m virtualenv venv

### 가상환경 세팅 (의존성 세팅)

- export AIRFLOW_HOME=~/airflow

- AIRFLOW_VERSION=2.8.1

- PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)"

- CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

- pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"

### db 초기화
- 버전이 달라 init이 아님
- airflow db migrate 
- db 생성 예제
"
airflow users create \
    --username gen2 \
    --firstname Peter \
    --lastname Parker \
    --role Admin \
    --email spiderman@superhero.org
"
- 비밀번호는 너무 간단하게 생성하면 생성 안 된다.

### airflow 구동
- nohup airflow webser --port 8080 & ; 백그라운드 실행

### scheduler 구동
- nohup airflow scheduler &

### 실행 중인 포트와 pid 확인
- sudo netstat -ntpl
- sudo kill -9 [pid]

### 실행중인 프로세스 찾기 
- sudo ps -ef | grep [프로그램이름]

### 해당 이름이 들어간 프로세스 전부 종료
- sudo pkill -f [이름] 

