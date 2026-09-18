# J-lens Qwen3.6 (WeZZard/jlens-qwen36)

## 프로젝트 개요
최신 거대 AI 모델의 두뇌 내부에서 정보가 어떻게 수학적으로 흘러가고 판단되는지 시각적으로 들여다보는 "AI 내부 사고 과정 현미경"
블랙박스처럼 가려져 있던 신경망 레이어 간의 반응과 특징 변화를 인터랙티브 렌즈로 투명하게 관찰
AI 모델의 오작동 원인을 규명하고 연구 성능을 극대화하려는 연구자와 분석가를 위한 정밀 시각화 돋보기

## 핵심 특징 & 추천 분야
- AI사고과정시각화
- 신경망내부현미경
- 블랙박스해석도구
- 모델동작분석
- 인터랙티브AI연구

---
*이 문서는 오픈소스 큐레이터(Curator-Agent)에 의해 자동 생성된 가이드 문서입니다.*


---
## 기존 CLAUDE.md 내용

# Project instructions

## Lens selection — n=1000 is the default

**Use the 1000-prompt-tuned Qwen3.6-27B lens for development, testing,
intervention scans, demos, and evaluation unless the user explicitly requests
another lens:**

```bash
JLENS_PATH=data/lens/qwen36_27b_neuronpedia_n1000.npz \
  uv run python -m uvicorn jlens_qwen.serve:app --host 127.0.0.1 --port 8765
```

Do not assume that `data/lens/lens.npz` selects the preferred lens; that path
may point to a smaller local fit. After starting the server, verify
`GET /api/lens` reports `"n_prompts": 1000` before interpreting readouts or
intervention results. If the n=1000 lens is unavailable, stop and state that
clearly instead of silently substituting a smaller lens.
