# aiforme — AI 에이전트 마스터 저장소

다라미(JH)님의 콘텐츠 자동화 SaaS 기획·개발 워크플로우를 위한 AI 에이전트 시스템 프롬프트와 지식 파일 마스터 보관소입니다.

Claude Projects와 Google Gemini Gems 양쪽에서 같은 에이전트를 운영하기 위해, 이 저장소를 **단일 마스터(Single Source of Truth)**로 두고 두 플랫폼에 동기화합니다.

---

## 📂 저장소 구조

```
aiforme/
├── README.md                    이 파일 (운영 가이드)
├── CHANGELOG.md                 변경 이력
│
├── prompts/                     시스템 프롬프트 마스터
│   ├── 01_planner_ara.md        기획 - 아라 팀장 ✅
│   ├── 02_designer.md           설계 (예정)
│   ├── 03_developer.md          개발 (예정)
│   ├── 04_source_manager.md     소스관리 (예정)
│   ├── 05_deployer.md           배포 (예정)
│   ├── 06_launcher.md           출시 (예정)
│   └── 07_maintainer.md         유지보수 (예정)
│
├── knowledge/                   지식 파일 마스터
│   ├── _template.md             지식 파일 작성 템플릿
│   ├── market_trends_*.md       시장 트렌드 (월 1회 갱신)
│   └── competitor_*.md          경쟁사 분석 (분기 1회 갱신)
│
├── handoff_format/              단계 간 전달 양식
│   └── handoff_template.md      표준 산출물 양식
│
└── images/                      페르소나 표정 이미지
    └── ara_*.png                (이미 사용 중)
```

---

## 🎯 운영 원칙

### 1. GitHub은 마스터, 플랫폼은 실행 환경

이 저장소가 진실의 원본입니다. Claude Projects와 Gemini Gems의 시스템 프롬프트는 **이 저장소에서 복사된 사본**일 뿐입니다. 수정이 필요하면 **반드시 여기서 먼저** 수정한 뒤 양 플랫폼에 동기화합니다.

### 2. 한 곳 수정 → 양쪽 동기화

```
[GitHub 마스터 수정]
        ↓
   [Claude Projects 갱신]
        ↓
   [Gemini Gems 갱신]
        ↓
   [CHANGELOG 기록]
```

### 3. 시스템 프롬프트는 안정적으로

시스템 프롬프트는 자주 바꾸지 않습니다. 한 번 만들면 보통 3~6개월 유지합니다. 자주 바뀌는 것은 `knowledge/` 폴더의 자료 파일입니다.

---

## 🔄 동기화 워크플로우

### 시스템 프롬프트 변경 시

1. `prompts/XX.md` 수정 → commit & push
2. `CHANGELOG.md`에 변경 내용 + 날짜 기록
3. Claude Projects의 프로젝트 지침 갱신
4. Gemini Gems의 지침 갱신
5. 양쪽에서 첫 인사 테스트로 작동 확인

### 지식 파일 업데이트 시 (월 1회 권장)

1. `knowledge/` 폴더에 신규 파일 추가 또는 기존 파일 갱신
2. 파일명에 갱신 날짜 반영 (예: `market_trends_2026-04.md`)
3. Claude Projects의 Knowledge에 신규 파일 업로드 + 구버전 삭제
4. Gemini Gems의 Knowledge에 신규 파일 업로드 + 구버전 삭제
5. `CHANGELOG.md`에 기록

---

## ✅ 동기화 체크리스트

### 시스템 프롬프트 변경 시
- [ ] GitHub에서 `prompts/XX.md` 수정 + commit
- [ ] `CHANGELOG.md`에 변경 내용 + 날짜 기록
- [ ] Claude Projects 프로젝트 지침 갱신
- [ ] Gemini Gems 지침 갱신
- [ ] 양쪽에서 첫 인사 테스트로 작동 확인

### 지식 파일 업데이트 시 (월 1회)
- [ ] `knowledge/` 폴더 자료 갱신
- [ ] 파일명에 갱신 날짜 반영
- [ ] Claude Projects Knowledge 갱신
- [ ] Gemini Gems Knowledge 갱신
- [ ] `CHANGELOG.md` 기록

---

## 🤖 에이전트 7단계 개요

| 단계 | 에이전트 | 페르소나 | 상태 |
|------|---------|---------|------|
| 1. 기획 | 아라 팀장 | 츤데레 콘텐츠 기획자 | ✅ 완료 |
| 2. 설계 | 미정 | 미정 | ⏳ 예정 |
| 3. 개발 | 미정 | 미정 | ⏳ 예정 |
| 4. 소스관리 | 미정 | 미정 | ⏳ 예정 |
| 5. 배포 | 미정 | 미정 | ⏳ 예정 |
| 6. 출시 | 미정 | 미정 | ⏳ 예정 |
| 7. 유지보수 | 미정 | 미정 | ⏳ 예정 |

각 에이전트는 독립적으로 작동하며, 단계 간 산출물은 `handoff_format/handoff_template.md`의 표준 양식으로 전달합니다.

---

## 🔗 플랫폼별 적용 위치

| 플랫폼 | 시스템 프롬프트 위치 | 지식 파일 위치 |
|-------|------------------|---------------|
| **Claude Projects** | 프로젝트 지침 (Custom Instructions) | 프로젝트 지식 (Knowledge) |
| **Gemini Gems** | 지침 (Instructions) | 지식 (Knowledge) |

---

## ⚙️ 플랫폼 차이 메모

| 항목 | Claude Projects | Gemini Gems |
|------|---------------|-------------|
| 시스템 프롬프트 글자 수 | 매우 넉넉 | 비교적 넉넉 |
| 이미지 렌더링 | ✅ 안정적 | ⚠️ 불안정 → 이모지 대체 |
| 페르소나 유지력 | ★★★★★ | ★★★★ (유지 블록으로 보강) |
| 검색 | 웹 검색 | Google 검색 (한국어 강함) |
| 추천 용도 | 본인 작업 / 깊은 분석 | 빠른 검색 / 한국 시장 |

시스템 프롬프트의 `0-4. 플랫폼 적응` 블록이 두 플랫폼의 차이를 자동으로 흡수합니다.

---

## 📝 라이선스

이 저장소는 다라미(JH)님 개인의 워크플로우 자료입니다. 외부 공유 시에는 별도 안내합니다.
