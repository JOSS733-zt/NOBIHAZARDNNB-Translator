# Nobihazard NNB-Translation 사용 설명

제작: JOSS ｜ 단일 exe ｜ 설치 불필요

## 지원 엔진

| 엔진 | 데이터 | 방식 |
|---|---|---|
| RPG Maker MV / MZ | `data\*.json` | 데이터 적용 또는 비교 플러그인 설치 |
| RPG Maker XP | `Data\*.rxdata` | 직접 적용 |
| RPG Maker VX | `Data\*.rvdata` | 직접 적용 |
| RPG Maker VX Ace | `Data\*.rvdata2` | 직접 적용 |

2000 / 2003(`.ldb`)은 지원하지 않습니다.

## 세 단계

1. **① 게임 선택** — `www` / `data` / `Data` 가 있는 폴더를 고르고 **게임 인식**
2. **② 번역 설정** — 엔진 선택 → **엔진 테스트** → **③ 구역 선택**
3. **텍스트 스캔** → **번역 시작** → **게임에 적용** (먼저 자동 백업)

## 번역 엔진 (모두 키 불필요)

| 엔진 | 설명 |
|---|---|
| Microsoft (기본) | `cn.bing.com`, 중국 본토에서 직결; 제한되면 동시 실행을 1로 |
| MyMemory | 중국 본토 직결, 하루 약 5000자; `[[0]]` 토큰을 가장 잘 보존 |
| Google 무료 | 중국 본토에서는 프록시 필요 |

## 구역

체크한 구역만 스캔·번역합니다: 맵 이벤트 / 맵 이름 / 공통 이벤트 / 아이템 / 스킬 / 무기 / 방어구 / 액터 / 상태·적 / 적 그룹 / 시스템 / 기타.

체크를 해제한 행은 표에서 숨겨지고 번역되지 않습니다.

## 파일 위치

```
<게임 폴더>
├── translate\cache_<언어>.json   이어서 번역 캐시
├── translate\glossary.txt        사용자 용어
├── translate\대조표_*.html       원문/번역 대조표
└── translate\backup_*\           적용 전 백업
```

MV/MZ 는 추가로 `data\TranslatePlus\` 와 `js\plugins\TranslatePlus.js` 를 사용합니다.

## 자주 묻는 질문

- **실행 직후 종료** — exe 옆의 `startup.log` / `crash.log` 확인
- **인식 안 됨** — `data` / `Data` 가 있는 폴더 선택, `Game.rgss3a` 는 먼저 압축 해제
- **"빈 응답"** — 제한 중. 동시 실행을 1로 하고 몇 분 대기
- **상태 "검토"** — 제어 코드가 사라짐. 번역 셀을 직접 수정
- **중국어가 □로 표시** (XP/VX/VA) — `Fonts\` 의 폰트 교체
- **이름 / 언어 변경** — `nnb.ini` 의 `name=` / `lang=`

## 라이선스

MIT. 영구 무료, 결제나 인증 없음. 게임 리소스는 포함하지 않습니다.
