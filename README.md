# mait knowledge base

mait 제품의 회의록 · 기획 · 문의를 정리하고 질문에 답하는 자기유지 위키.
[Karpathy LLM Wiki 패턴](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) 기반.

## 어떻게 쓰나

1. **새 자료 들어왔을 때** — 파일을 `raw/YYYY-MM-DD-<slug>.md`로 떨군 뒤 에이전트(Claude Code / Codex)에게:
   > raw에 새 회의록 정리해줘
2. **기능/결정 궁금할 때** — 그냥 묻는다:
   > 팀 룸 기능 어떻게 동작해?
   > 지난 주 회의에서 결정된 거 뭐야?
3. **위키 정합성 점검** —
   > 위키 한번 정리해줘

## 디렉터리

- `raw/` — 원본 자료 (수정 금지)
- `wiki/` — 에이전트가 정리한 큐레이션 마크다운
- `output/` — 일회성 생성물 (Q&A 답변, 리포트)

자세한 워크플로우와 컨벤션은 [AGENTS.md](AGENTS.md) 참고.
