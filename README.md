# 보행 안전 향상을 위한 AI 기반 SafeRoute 추천 기술 설계
Open source design projects

1인 가구의 증가와 예측 불가능한 범죄에 대한 사회적 불안감이 커지는 지금, 기존의 '가장 빠른 길' 안내는 더 이상 충분하지 않습니다. SafeRoute는 최단 경로라는 단일 가치를 넘어, 사용자의 **'안전'**을 최우선으로 고려하는 새로운 차원의 경로 안내 시스템입니다.

"가장 빠른 길이 잠재적으로 가장 위험한 길이 될 수 있는 정보의 비대칭 문제"를 해결하는 것을 목표로 합니다.

<p align="center">
<img src="https://www.google.com/search?q=https://i.imgur.com/8a6P4f6.png" alt="SafeRoute UI" width="400"/>
</p>

<그림 1: '최단 경로'와 '안심 경로' 비교 시각화 예시>

🎯 주요 기능 (Key Features)

데이터의 다차원적 융합

단순히 CCTV 개수만 세는 것을 넘어, 공공 안전 인프라(CCTV, 가로등) 데이터와 실제 범죄 통계 데이터를 AI로 종합 분석합니다.

객관적인 안전도 정량화

AI가 융합된 데이터를 기반으로 각 경로의 위험 요소를 분석하고, 안전 점수(Safety Score) 라는 객관적인 지표를 산출하여 제시합니다.

능동적 경로 추천 및 비교

사용자에게 기존의 '최단 경로'와 데이터로 검증된 '안심 경로'를 시각적으로 비교하여 제시합니다.

예상 시간, 거리뿐만 아니라 안전 점수, 경유 CCTV 개수 등 명확한 근거를 함께 제공하여 주체적인 의사결정을 돕습니다.

🛠️ 기술 스택 (Tech Stack)

구분

기술

역할

프론트엔드

Flutter, Mapbox

크로스플랫폼 앱 개발 및 지도 시각화

백엔드

FastAPI (Python), GNN Model

API 서버 구축 및 AI 기반 안전 점수 계산

데이터베이스

PostGIS, Neo4j

공간 데이터 저장/처리 및 경로 탐색 최적화

🏗️ 시스템 아키텍처 (System Architecture)

본 시스템은 3-Tier 아키텍처로 설계되어 각 계층이 명확한 역할을 수행합니다.

<p align="center">
<img src="https://www.google.com/search?q=https://i.imgur.com/rNl9V2B.png" alt="System Architecture" width="700"/>
</p>

<그림 2: '세이프루트' 시스템의 3-Tier 아키텍처 및 데이터 흐름>

프론트엔드 (모바일 앱): 사용자로부터 경로 요청을 받아 백엔드로 전달하고, 받은 결과를 지도 위에 시각화합니다.

백엔드 (FastAPI 서버): 시스템의 두뇌 역할을 하며, 데이터베이스와 AI 모델을 총괄하여 최적의 경로를 계산합니다.

데이터베이스 (PostGIS, Neo4j): 시스템의 근간이 되는 공간 데이터와 경로 데이터를 저장하고 관리합니다.

🚀 개발 로드맵 (Development Roadmap)

자세한 개발 계획은 **프로젝트 제안서**]를 참고해주세요.

[x] Phase 1: 핵심 로직 구현 및 데이터 파이프라인 구축

[x] 데이터 수집 및 전처리 모듈 구현

[x] PostGIS 데이터베이스 스키마 설계

[ ] 베이스라인 안전 점수 알고리즘 개발

[ ] Phase 2: API 서버 구축 및 MVP 프론트엔드 구현

[ ] /route API 엔드포인트 개발

[ ] 지도 시각화 및 경로 렌더링 기능 구현

[ ] 인터랙티브 컨트롤 UI (안전 가중치 슬라이더) 구현

[ ] Phase 3: AI 모델 통합 및 기능 고도화

[ ] GNN 모델 학습 파이프라인 구축 및 서빙

[ ] 실제 범죄 데이터 통합 로직 구현

[ ] 크라우드소싱(사용자 제보) 기능 구현

🏁 시작하기 (Getting Started)

프로젝트를 로컬 환경에서 실행하는 방법입니다.

# 1. 저장소 복제
git clone [https://github.com/your-username/SafeRoute.git](https://github.com/your-username/SafeRoute.git)

# 2. 백엔드 서버 실행
cd SafeRoute/backend
pip install -r requirements.txt
uvicorn main:app --reload

# 3. 프론트엔드 앱 실행
cd ../frontend
flutter pub get
flutter run
