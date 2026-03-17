# 리니지 클래식 공략 도용 검사기

인벤 리니지 클래식 팁 게시판의 게시물 URL을 입력하면, Google Gemini AI가 같은 게시판의 다른 게시물과 비교하여 도용 의심 여부를 분석해주는 도구입니다.

## 배포 방법 (GitHub Pages)

### 1단계 — GitHub 리포지토리 생성

1. [github.com/new](https://github.com/new) 에서 새 리포지토리를 만듭니다
2. 리포지토리 이름: `linc_copychecker`
3. **Public**으로 설정 (GitHub Pages 무료 사용 조건)
4. `README.md` 추가 체크박스는 해제

### 2단계 — 파일 업로드

방법 A — 브라우저에서 바로 업로드:
1. 생성된 리포지토리 페이지에서 **"uploading an existing file"** 클릭
2. `index.html` 파일을 드래그하여 업로드
3. **Commit changes** 클릭

방법 B — Git 커맨드:
```bash
git clone https://github.com/YOUR_USERNAME/lineage-checker
cd lineage-checker
# index.html을 이 폴더에 복사한 후
git add index.html
git commit -m "Add plagiarism checker"
git push
```

### 3단계 — GitHub Pages 활성화

1. 리포지토리 상단 **Settings** 탭 클릭
2. 왼쪽 사이드바 **Pages** 클릭
3. Source: **Deploy from a branch** 선택
4. Branch: **main**, 폴더: **/ (root)** 선택
5. **Save** 클릭
6. 약 1~2분 후 `https://blackhandkr.github.io/linc_copychecker` 로 접속 가능

---

## 사용 방법

### API 키 발급 (최초 1회, 팀원 각자)

1. [Google AI Studio](https://aistudio.google.com/app/apikey) 접속
2. 구글 계정(구글 워크스페이스)으로 로그인
3. **Create API key** 클릭 → 키 복사
4. 도구 접속 후 API 키 입력란에 붙여넣기
5. 키는 본인 브라우저에만 저장됨 (서버·코드에 저장 안 됨)

### 분석 방법

1. 배포 URL 접속
2. API 키 설정 (최초 1회)
3. 의심되는 게시물의 인벤 URL 붙여넣기
4. **분석하기** 클릭 → 20~40초 대기
5. 판정 결과 및 유사 게시물 확인

---

## 판정 기준

| 등급 | 유사도 | 설명 |
|------|--------|------|
| 도용 의심 높음 | 80% 이상 | 핵심 내용이 거의 그대로 복사된 경우 |
| 부분 유사 의심 | 50~79% | 구조나 전략이 매우 비슷한 경우 |
| 유사도 낮음 | 30~49% | 주제만 비슷하고 독창적 내용 있음 |
| 도용 없음 | 30% 미만 | 독창적인 공략으로 판단 |

> AI 분석 결과는 참고용입니다. 최종 판단은 운영진이 원문을 직접 비교해 결정하세요.

---

## 주의사항

- **API 키 보안**: 팀원들이 각자 자신의 API 키를 발급받아 사용하세요. 키를 공유하지 마세요.
- **분석 범위**: 검색 엔진에 색인된 게시물만 비교 가능합니다. 최근 24시간 내 게시물은 누락될 수 있습니다.
- **무료 한도**: Google AI Studio 무료 티어는 분당 15회, 일 1,500회 요청 한도가 있습니다.
