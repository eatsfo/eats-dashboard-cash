# 디자인 지침 — 대시보드 담당자 페이지 공통 (2026-09-03)

> 이 페이지는 메인 대시보드(board.eats-board.com)에 **iframe으로 박혀서** 보인다.
> 톤이 다르면 한 화면 안에서 바로 티가 나므로 아래를 지킨다.
> 원본 = 메인 저장소 `DESIGN-SYSTEM.md`. 충돌하면 원본이 우선.

## 1. 색 토큰
```css
:root{
  --bg:#f5f5f7;      /* 캔버스(중성 회색) — 종이색으로 바꾸지 말 것 */
  --card:#ffffff;    /* 카드·패널은 흰색 */
  --ink:#1d1d1f;     /* 본문 잉크 */
  --sub:#6e6e73;     /* 보조 텍스트 */
  --line:#e3e2dc;    /* hairline(따뜻한 회색) */
  --line2:#d0cfc8;   /* 강조선 */
  --head:#f4f3ef;    /* 표 헤더 배경 = 종이톤 */
  --navy:#1f3864;    /* 문서 잉크 — 제목·표 헤더 글자·선택된 탭 */
  --accent:#0066cc;  /* Action Blue — 링크·버튼·클릭 가능한 이름 */
}
```

**네이비와 파랑은 역할이 다르다.**
- **네이비 = 읽는 색**: 페이지 제목, 표 헤더 글자, 패널 제목, 선택된 탭 배경
- **파랑 = 누르는 색**: 링크, 액션 버튼, 클릭하면 상세로 가는 매장명

신호색(의미색)은 그대로: 초록 `#15803d` / 빨강 `#c62828` / 주황 `#b45309`.
**슬레이트 계열(`#0f172a` `#64748b` `#f8fafc` 등)·인디고·보라 액센트 금지.**

## 2. 모서리 — 각짐이 기본
- **각짐(0)**: 카드·패널·**버튼·탭·필터칩·검색창·셀렉트**
- **알약(9999px)**: 상태 배지(적자/저수익 같은 판정 딱지)·신호 점·게이지 바만
- 판별: `cursor:pointer`가 붙어 있으면 누르는 것 → 각짐
- 어중간한 8~18px 라운드 금지

## 3. 표 (가장 중요 — 화면의 대부분이 표다)
```css
th{ background:var(--head); color:var(--navy); font-weight:700; font-size:11.5px;
    border:1px solid #ecebe6; padding:4px 3px; }
td{ border:1px solid #ecebe6; font-size:11.5px; padding:4px 3px; }
tbody tr:hover td{ background:#fbfaf6; }
```
- **고밀도**: 본문 11.5px · 셀 padding 4px. 행이 두 줄로 늘어지면 열 폭을 조정한다.
- **숫자는 `font-variant-numeric:tabular-nums`** — 자릿수가 흔들리지 않게.
- **기준선 행**: 중앙값·평균 행을 표 맨 위에 고정하고 `background:#f7f6f2; font-weight:700`.
  숫자 하나만 보면 좋은지 나쁜지 알 수 없다. 비교 대상을 같은 표에 둔다.
- **조건부 틴트**: 기준선 대비 나쁨 `rgba(198,40,40,.09)` · 좋음 `rgba(21,128,61,.09)`.
  색은 옅게 — 숫자가 먼저 읽혀야 한다.
- **매장명 등 클릭 가능한 이름**: `color:var(--accent); font-weight:600; text-align:left`
- **채널·담당자 등 보조 텍스트 열**: `color:var(--sub); text-align:center`
- 긴 텍스트를 표 셀에 넣지 말 것 — 잘린다. 보조행이나 클릭 드릴다운으로.

## 4. 폭
- 본문 컨테이너 `max-width:1100px; margin:0 auto` — 화면이 커져도 늘어나지 않게.
- 넓은 표는 컨테이너에 `overflow-x:auto`를 주고 페이지 자체는 가로 스크롤되지 않게.

## 5. 폰트
```css
font-family:-apple-system,'SF Pro Text','Inter',system-ui,'Pretendard','Malgun Gothic',sans-serif;
```

## 6. 바꾸기 전에
같은 역할의 요소는 **모든 페이지에서 같아야 한다.** 한 곳을 고치면 같은 역할을 하는 나머지도 같이 고친다.
데이터·계산 로직은 이 지침과 무관하다 — **보이는 스타일만** 해당한다.
