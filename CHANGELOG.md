# Changelog

이 저장소의 모든 주요 변경사항을 이 파일에 기록합니다.
형식: [날짜] 영역 - 변경 내용

---

## [2026-04-26] 저장소 초기 구축

### Added
- 저장소 폴더 구조 생성 (`prompts/`, `knowledge/`, `handoff_format/`)
- `README.md` 작성 (운영 가이드)
- `prompts/01_planner_ara.md` 작성 — 기획 에이전트 '아라 팀장' 시스템 프롬프트 (통용 풀버전)
  - 페르소나: 츤데레 콘텐츠 기획자
  - 핵심 역량: 문제 정의, 페르소나 모델링, 경쟁사 매트릭스, 기술 타당성, 리스크 관리
  - 검증 7원칙 + 트렌드 안전장치 포함
  - `0-4. 플랫폼 적응 및 페르소나 유지` 블록 신설 (Claude/Gemini 통용)
- `handoff_format/handoff_template.md` 작성 — 단계 간 산출물 전달 표준 양식
- `knowledge/_template.md` 작성 — 지식 파일 작성 템플릿

### Plan (다음 작업 예정)
- `prompts/02_designer.md` — 설계 에이전트
- `prompts/03_developer.md` — 개발 에이전트
- `knowledge/market_trends_*.md` — 첫 트렌드 자료 정리
