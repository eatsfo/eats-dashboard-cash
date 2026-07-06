# 이 저장소 = 외식사업부 대시보드 "현금" 페이지 (Claude Code 자동 지침)

이 저장소는 `index.html` 하나가 전부다. 이걸 고쳐서 push하면 약 1분 뒤 **https://cash.eats-board.com** 에 자동 반영된다(Cloudflare 자동배포).
담당자는 **코딩 초보**이므로 매 단계 쉽게 설명하고, 담당자가 **"깃허브에 올려줘"**라고 하면 알아서 `git add·commit·push` 한다.

## 🎨 디자인 = Apple 테마 (반드시 이 토큰만 사용)
회사 메인 대시보드와 **똑같은 애플 스타일**로 통일한다. 새로 만들거나 고칠 때 **아래 토큰·규칙을 반드시 따른다.** (index.html의 `:root`에 이미 들어 있음 — 그대로 쓴다.)

**색 토큰**
- 배경 `#edeff3` · 카드 `#ffffff` · 표헤더 `#f5f5f7` · 잉크 `#1d1d1f` · 보조 `#6e6e73` · 옅음 `#86868b` · hairline `#e0e0e0`
- **강조·링크·활성 = 단일 Action Blue `#0066cc`** (연배경 `#e8f1fc`). 🚫 인디고(`#4f46e5`)·보라·슬레이트 액센트 금지.
- 신호등(의미색만): 초록 `#16a34a`/`#15803d`, 빨강 `#dc2626`/`#b91c1c`, 주황 `#d97706`.

**규칙**
- 카드/패널: `#fff` + `1px solid #e0e0e0` + `border-radius:18px` + **그림자 없음(box-shadow 금지)**.
- 표 헤더: 배경 `#f5f5f7` + 잉크 글자 + `font-weight:600`.
- 버튼·칩·태그: 알약 `border-radius:9999px`.
- 숫자 셀: `font-variant-numeric:tabular-nums`.
- 폰트: `-apple-system,'SF Pro Text','Inter',system-ui,'Pretendard','Malgun Gothic',sans-serif`.
- 결론/인사이트 박스(`.insight`): 배경 `#f4f8fc` + `1px #e3eaf2` + `radius:12px`. 🚫 좌측 컬러바·비대칭 라운드 금지.
- **옛 색(인디고 `#4f46e5`, 슬레이트 `#0f172a`/`#64748b`/`#f8fafc`/`#eef0fe`/`#e7e9fb`/`#cbd5e1` 등)이 이미 있으면 위 애플 토큰으로 바꾼다.**

## 📊 내용 = 재무팀답게
숫자만 나열하지 말고, 각 표·지표 밑에 **"그래서 무엇을 결정해야 하는지" 결론 한 줄(💡)**을 붙인다. 금액영향(월/연 X억)·시한이 드러나면 더 좋다.

## 담당 페이지 (2026-07-06 확장 — 한 저장소에 여러 페이지)
이 저장소는 이제 **6개 페이지**를 담습니다. 파일별 주제 (메인 대시보드 사이드바에 연결됨):
- `index.html` = 현금·씨드머니 · `invest.html` = 투자심의 · `rotc.html` = ROTC · `debt.html` = 차입금 · `interest.html` = 금융이자 · `working.html` = 운전자본
파일을 추가·수정하고 push하면 `cash.eats-board.com/<파일명>`으로 자동 배포됩니다. 파일명은 바꾸지 마세요(메인 대시보드가 이 이름으로 연결).
