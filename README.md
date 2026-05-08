# ✈️ 영업 대시보드

GitHub Pages로 배포되는 항공 영업 데이터 대시보드입니다.  
**엑셀 파일만 교체하면 대시보드가 자동으로 업데이트됩니다.**

---

## 📁 파일 구조

```
dashboard/
├── index.html          ← 대시보드 메인 파일 (수정 불필요)
├── data/
│   └── 대쉬보드.xlsx   ← ✅ 이 파일만 교체하면 됨
└── README.md
```

---

## 🚀 GitHub Pages 배포 방법

### 1단계: GitHub 리포지토리 생성
1. GitHub에서 새 리포지토리 생성 (예: `sales-dashboard`)
2. **Public** 또는 **Private** 선택 (Pages는 Public 권장)

### 2단계: 파일 업로드
```bash
git init
git add .
git commit -m "Initial dashboard"
git branch -M main
git remote add origin https://github.com/[사용자명]/[리포지토리명].git
git push -u origin main
```

### 3단계: GitHub Pages 활성화
1. 리포지토리 **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / **/ (root)**
4. **Save** 클릭
5. 몇 분 후 `https://[사용자명].github.io/[리포지토리명]/` 접속 가능

---

## 🔄 데이터 업데이트 방법

### 방법 A: GitHub 웹 UI (권장 - 코딩 불필요)
1. 리포지토리에서 `data/대쉬보드.xlsx` 클릭
2. 우측 상단 **연필 아이콘(Edit)** → **Upload file** 선택
3. 새 엑셀 파일 드래그 앤 드롭
4. **Commit changes** 클릭
5. **1~2분 후** 대시보드 자동 갱신 ✅

### 방법 B: Git 커맨드
```bash
# 새 파일로 교체 후
cp 새파일.xlsx data/대쉬보드.xlsx
git add data/대쉬보드.xlsx
git commit -m "데이터 업데이트 $(date +%Y-%m-%d)"
git push
```

---

## ⚠️ 주의사항

- 엑셀 파일명은 반드시 `대쉬보드.xlsx` 유지
- 컬럼 구조 변경 시 `index.html` 내 컬럼명 수정 필요
- 필수 컬럼: `년월`, `Line`, `노선`, `발매-년월`, `Class Type`, `발매건수`, `발매수입`, `FSC`, `시점(MONTH)`

---

## 📊 대시보드 기능

| 기능 | 설명 |
|------|------|
| KPI 카드 | 총 발매수입 / 발매건수 / 평균운임 / FSC |
| 노선별 수입 | 바 차트로 카테고리별 매출 비교 |
| 노선 구성 비율 | 도넛 차트로 노선 비중 표시 |
| 발매월별 추이 | 선형 차트로 월별 트렌드 |
| Group vs Individual | 구분별 수입 비중 |
| 발매시점별 건수 | 당월/1개월/2개월/3개월/그외 분포 |
| TOP 20 노선 | 수입 기준 상위 노선 테이블 |
| 월 필터 | 기준월(년월)별 데이터 필터링 |
