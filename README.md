# React Native + Python 연동 프로젝트

React Native로 UI를 만들고, Python Flask 서버로 카운터 로직을 처리하는 앱입니다.

## 설정 방법

### 1. Python 서버 설정

```bash
# Python 가상환경 생성 (선택사항)
python3 -m venv venv
source venv/bin/activate  # macOS/Linux
# 또는
venv\Scripts\activate  # Windows

# 필요한 패키지 설치
pip install -r requirements.txt

# Python 서버 실행
python server.py
```

서버가 `http://localhost:5000`에서 실행됩니다.

### 2. React Native 앱 실행

**중요**: iOS 시뮬레이터에서 실행하는 경우, `localhost` 대신 컴퓨터의 로컬 IP 주소를 사용해야 합니다.

1. 컴퓨터의 로컬 IP 주소 확인:
   ```bash
   # macOS/Linux
   ifconfig | grep "inet " | grep -v 127.0.0.1
   
   # 또는
   ipconfig getifaddr en0
   ```

2. `app/index.tsx` 파일에서 `API_URL`을 수정:
   ```typescript
   // 예: 컴퓨터 IP가 192.168.1.100인 경우
   const API_URL = 'http://192.168.1.100:5000/api';
   ```

3. Expo 앱 실행:
   ```bash
   npm start
   ```

## 구조

- **React Native (`app/index.tsx`)**: UI만 담당 (버튼, 텍스트 표시)
- **Python (`server.py`)**: 카운터 로직 처리 (증가, 초기화)

## API 엔드포인트

- `GET /api/counter`: 현재 카운터 값 조회
- `POST /api/counter/increment`: 카운터 1 증가
- `POST /api/counter/reset`: 카운터 0으로 초기화




