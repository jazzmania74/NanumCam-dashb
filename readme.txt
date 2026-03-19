나눔캠퍼스 마케팅 인사이트 대시보드
=======================

배포 URL: https://jazzmania74.github.io/NanumCam-dashb/NanumCam-dashb.html
GitHub: https://github.com/jazzmania74/NanumCam-dashb

GA4 데이터를 기반으로 온라인 교육 플랫폼(나눔캠퍼스) 트래픽을 분석하고
Claude AI가 마케팅 인사이트 및 액션 플랜을 자동 생성하는 대시보드입니다.

파일 구조:
- NanumCam-dashb.html : 메인 대시보드 (프론트엔드 단일 파일)
- Code.gs : Google Apps Script 백엔드 (GA4 API + Search Console 연동)
- NanumCam-dashb-bd.gsheet : Google Sheets 데이터베이스 (.gitignore 제외)
- 나눔캠퍼스_홈페이지_구조_참조문서.md : 페이지 URL-제목 매핑 참조 문서

주요 기능:
1. KPI 카드 6개: 세션수, 활성 사용자, 새 사용자, 참여율, 평균 체류시간, 사용자당 조회수
2. 전주 대비 증감률 표시 (상승/하락 색상)
3. 최근 1주 방문자 & 페이지뷰 추이 (라인 차트)
4. 시간대별 방문 분석 (바 차트)
5. 기기별 분포 (도넛 차트: Mobile/Desktop/Tablet)
6. 많이 방문한 페이지 Top 20 (테이블 + 비율 바)
7. 유입 사이트 Top 15 (가로 바 차트, 채널별 대표색)
8. 신규 vs 재방문자 (도넛 차트)
9. 지역별 방문자 (가로 바 차트)
10. 유입 검색어 Top 20 (Google Search Console 연동)
11. 페이지별 평균 체류시간 Top 20 (바 + 색상 분류)
12. AI 마케팅 인사이트 & 어드바이스 (Claude API 실시간 분석)

페이지 제목 매핑 시스템:
GA4에서 넘어오는 JSP 경로를 한글 페이지 이름으로 자동 변환합니다.

- pageNames: 기본 경로 매핑 (36개)
  /classroom/index.jsp → 나의 강의실(과정현황)
  /classroom/viewer.jsp → 강의 수강(동영상)
  /course/course_list.jsp → 수강신청(전체과정)
  /course/course_view.jsp → 교육과정 상세
  /mypage/index.jsp → 마이페이지
  /member/login.jsp → 로그인
  /order/payment.jsp → 결제
  등

- pageCodeNames: ?code= 파라미터 매핑 (12개)
  greeting → 인사말, notice → 공지사항, faq → 자주하는질문
  privacy → 개인정보처리방침, refund → 환불규정 등

- courseNames: ?id= 교육과정 ID 매핑 (6개)
  197315 → Claude Cowork 기초 실전
  195140 → B2B 마케팅 Level 1 | 구조와 이해
  195139 → B2B 마케팅 Level 2 | 전략과 설계
  195138 → B2B 마케팅 Level 3 | 실행과 성과
  194684 → 기업강사를 위한 실전 AI 활용 과정
  186444 → 비즈니스 모델 캔버스

- categoryNames: ?cid= 카테고리 ID 매핑 (10개)
  118600 → 마케팅, 120388 → B2B마케팅, 118601 → AI 실무, 118602 → 기획력 등

기술:
- 프론트엔드: HTML/CSS/JS (단일 파일), Pretendard 폰트
- 차트: Chart.js 4.4.7
- AI 분석: Claude API (claude-sonnet-4-20250514)
- 백엔드: Google Apps Script (GA4 Analytics Data API + Search Console API)
- 데이터 통신: JSONP callback
- 배포: GitHub Pages

변경 이력:
- 2026-03-20: 페이지 제목 매핑 대폭 확장 (홈페이지 구조 참조문서 기반)
  - pageNames 36개 JSP 경로 한글 매핑
  - pageCodeNames ?code= 파라미터 12개 매핑
  - courseNames 교육과정 ID 6개 매핑
  - categoryNames 카테고리 ID 10개 매핑
  - getPageName() 함수 개선: ?id=, ?code=, ?cid= 쿼리 파라미터 자동 파싱

제작: 김종혁 (나눔경영컨설팅)
