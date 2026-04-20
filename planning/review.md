# aichemist — Review (2026-04-11)

## 1. 커밋 톤이 주장을 일관되게 지지하는가?

**판정: 일관됨 (커밋 2개, 단방향).**

```
fed0167 Initial commit: Burning Lead for Gold                       (2026-04-03)
08743e0 gitignore: exclude CLAUDE.md and .claude/                   (2026-04-08)
```

- 본 작품(LaTeX 365줄, manuscript 346줄, references 261줄, 빌드 PDF 243KB)이 단일 커밋으로 등장. *그 후 손대지 않음*. 2번째 커밋은 메타파일 정리만.
- 약점: 이전에 어떻게 진화했는지 git footprint 부재. *왜* AGI → AGS로 reframe했는지의 사고 전환은 main.tex 본문 안에서만 추적 가능.
- 강점: 단일 commit이지만 *내부 일관성*이 매우 높음. abstract → §1 furnace metaphor → §2 homology → §3 furnace material costs → §4 chemistry transition → §5 AGS → §6 notation → §7 dilemma → §8 conclusion. 각 절이 정확히 같은 framing(alchemy ↔ AGI; chemistry ↔ AGS; 비유가 아닌 *material architecture*)을 반복.
- 자기인식: §5.2 "we do not claim that AGI is impossible in principle"라는 *유보 조항*을 명시. §7.1 "the scaling counterargument"로 강한 반론까지 수용. §7.2 "the risk of neo-mysticism"으로 자기 framework의 한계까지 탐사. position paper로서 매우 성숙한 톤.
- TODO.md(2026-04-04)는 paper가 *이미 정리된 후* 별도로 작성됨. 5개 실험 제안 중 0개 진행.

## 2. 부가 서비스 품질

**판정: 부가 서비스 0개. position paper 단독.**

레포 내용:
- `paper/main.tex` (365 lines), `paper/manuscript.md` (346 lines, markdown 버전 동일 내용), `paper/references.bib` (261 lines)
- 이미 빌드된 `main.pdf` (243KB) — 즉 컴파일 검증 완료
- `TODO.md` — 향후 실험 제안 (0% 구현)

특징:
- AGS notation(L·V·R·D·H, ε_hallucination, ΔE, ΔW)이라는 새로운 표기 체계를 *제안*하지만 그것을 *표현·검증할 수 있는 구현체*는 없음.
- §6에서 인용하는 Gamma/CHAM/HOCL/Bond-Calculus 등 40년 전통의 chemical computation 형식을 connect하는 *코드 라이브러리*도 없음.
- 즉 핵심 contribution이 "notation 제안"인데 그 notation을 시연할 *예제 시스템*조차 manuscript 안의 toy formula 한두 개뿐.

## 3. 고도화 가능 파트

높은 우선순위:
1. **AGS notation parser/validator** — `L·V_2·R·D·H` 같은 표현식을 LARK/PEG로 파싱하고 검증하는 ~200줄 Python 라이브러리. 핵심 contribution을 *실행 가능*하게 만든다. 이것 하나만 있으면 paper의 무게가 비약적으로 증가.
2. **AGS-SMILES 형식 명세** — §6.5에서 제안만 한 `L[T>T]`, `T[L,L]>T` 같은 isomer notation을 BNF/EBNF로 1쪽 명세화. SMILES community(RDKit, OpenSMILES)와 직접 비교 가능한 spec.
3. **AGS 사례 카탈로그 (실험 #2)** — 의료/농업/에너지/교육/도시 5개 도메인에서 *실제 운영 중인* AI 파이프라인을 AGS notation으로 표기. position paper에 부속된 case-study companion.
4. **AGI Goalpost Movement 그래프 (실험 #1)** — 2015-2026 AI 리더 발언에서 AGI 도착 예측 시점 추출 → 2D plot. 본 paper §2.2의 가장 강력한 실증적 지지가 될 단일 figure. 이미지 1개로 reviewer 호감도 +1.
5. **CHAM operational semantics 부속 — AGS reaction을 CHAM 규칙으로 1개라도 형식화 (작은 worked example)**. §6.7에서 CHAM과 AGS notation의 연결을 주장만 하고 있다. 1쪽짜리 Appendix면 충분.

중간 우선순위:
6. **에너지 stoichiometry 정량화 (실험 #3)** — "동일 문제에 대한 AGI vs AGS 시나리오 비교"를 에너지(kWh)·물(gal)·탄소(t CO2)로 산출. 정책 발표용 1쪽 brief.
7. **Adjacent proposals (§5.3) 비교표** — ACI/ODI/SGI/AGI Society/Evans2025 5개 비교 매트릭스. 현재 텍스트만으로 한 줄씩 다루고 있어 가독성 떨어짐.
8. **§7.1의 scaling counterargument를 별도 짧은 noted/response 섹션으로 강화** — 현재는 강력한 반론을 받아치는 데 한 단락. reviewer가 첫 round에서 이걸 짚을 가능성이 매우 높음.

낮은 우선순위:
9. AGS notation을 PlantUML/Graphviz로 렌더링하는 시각화 도구.
10. main.tex의 빌드 산출물(.aux, .bbl, .log, .out, .blg)이 git에 들어가 있음 → `.gitignore`에 LaTeX intermediate 추가 (현재 89B `.gitignore`는 `CLAUDE.md`만 제외).

## 4. 학술적 / 시장 가치 (글로벌, 2026-04-11 기준)

### 학술적 가치: **중상위 (working paper 기준 상위 ~20%, single paper로 한정 시 상위 ~30%)**

타이밍:
- 2026 1분기는 "AI bubble" 담론이 정점에 가까워지는 시점. Goldman Sachs/Sequoia 회의론, Sam Altman의 물 사용 발언(2026-02), Sora 셧다운(2026-03-24) 모두 직전.
- "alchemy-AI" 비유는 Dreyfus 1965 / Rahimi 2017이 이미 다뤘기 때문에 *완전히 새로운 이야기*는 아님. 하지만 본 논문의 *재해석*("methodological rigor가 아니라 material architecture가 핵심")은 새롭다.

차별점:
- **AGS = Artificial General Society**라는 명명이 지금까지 unoccupied (paper §5.3에서 직접 검증). 인용 가능한 새 용어. naming-rights 가치.
- **chemical notation system** (L·V·R·D·H, balanced equation with ε terms)이 paper 대부분 페이지에서 가장 독창적인 contribution. 단순 비유가 아니라 *epistemic tool*이라는 주장.
- **40년 chemical computation 전통과의 연결** (Gamma/CHAM/HOCL/Bond-Calculus/Chemical Organization Theory) — 이 brigde를 academic position paper에서 처음 시도. CS theory rev와 sociotech rev 양쪽에서 호기심 유발 가능.
- §5.3의 adjacent proposals(ACI/ODI/SGI/AGI Society/Evans2025) 정리가 양호. *이미 존재하는* 인접 개념과의 차별화 작업이 잘 돼 있다.

위험:
- **Position paper / essay**는 학술 임팩트의 변동성이 큼. *Communications of the ACM*, *Issues in Science and Technology*, *AI & Society*, *Big Data & Society*, *Patterns* (Cell)의 perspective 트랙이 자연 후보. 거절률 60-70%.
- **Independent researcher 단독 저자**(Jiyeon Yoon) — 이 분야는 명성 가중치가 높음. Critical AI 서클(Crawford, Bender, Gebru)이나 UCS/Climate Tech 진영의 endorsement 없이는 wide pickup 어려움.
- Notation 제안이 *실행 가능 라이브러리* 부재로 형식 모델로 인정받기 어려움. CHAM과 직접 비교당하면 형식성 부족이 드러남.
- 5개 TODO 실험이 모두 *paper와 별개로 후속 작업이 필요*하다는 것은 곧, *현재 paper만으로는 결정적 evidence가 없다*는 뜻.

(venue-fit 분석 및 게재 전망은 submission 시점에 `submissions/<venue>/NOTES.md`로 분리.)

### 시장 가치: **중상위 (담론 형성/정책 자문에서 강함)**

- **정책 think-tank**: AI Now Institute, CEPR, Brookings, OECD AI Observatory가 즉시 인용 가능한 framing. AI sustainability/equity 담론에 새 vocabulary 제공.
- **언론**: "Burning lead for gold", "AGI is alchemy", "From AGI to AGS"는 1줄 헤드라인 가치 매우 높음. WIRED, MIT Tech Review, The Atlantic이 좋아할 톤. WSJ/FT의 conventional 회의론 기사와 차별화됨.
- **컨설팅**: Carbon-aware AI / sustainable AI 자문. AGS notation을 enterprise architecture 도구로 패키징 가능.
- **교육**: AI ethics 수업의 필수 reading 가능성. Dreyfus 1965, Rahimi 2017, Crawford 2021 *Atlas of AI*에 이어지는 reading list로 적합.
- 한계: notation을 *팔* 수 있는 product화 경로가 불명. 실제 enterprise tool(Anthropic/OpenAI/Google ADK)이 이미 자기 spec language를 가지고 있어 시장 진입이 어려움.

### 종합 평점 (2026-04-11)

| 축 | 점수 | 코멘트 |
|---|---|---|
| Originality of framing | 8/10 | "material architecture" 재해석 + AGS naming |
| Literature integration | 9/10 | 40년 chemical computation 전통 연결이 결정타 |
| Empirical contribution | 1/10 | 0개. 통계 인용도 모두 secondary |
| Internal coherence | 10/10 | 단일 비유가 8개 절에서 흔들림 없음 |
| Self-criticism discipline | 9/10 | scaling counterargument + neo-mysticism까지 자수 |
| Repo health | 4/10 | 1 main commit, build artifacts 포함, no service |
| Timing | 9/10 | bubble 담론 정점 직전 |
| **Overall (position paper)** | **6.8/10** | "결정타가 부족한 잘 쓰인 essay" |

핵심 격언: **"이 paper는 1개의 figure(goalpost movement plot)와 1개의 작은 parser/validator만 있으면 7.5+로 점프한다."** AGS notation을 *실제로 작동시키는* 50줄짜리 Python lib가 가장 큰 ROI. 그것 없이는 "또 하나의 잘 쓰인 essay"로 분류될 위험이 크다.
