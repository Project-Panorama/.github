# ⛸️ Project: Frozen Stage (가제)
> Unreal Engine 5 기반 버추얼 휴먼 피겨 스케이팅 시네마틱 프로젝트

## 📂 Repositories
- 🎨 **Art Source:** [Panorama_ArtSource 바로가기](https://github.com/Project-Panorama/Panorama_ArtSource)
- 🎬 **Unreal Project:** [Panorama_UE5 바로가기](https://github.com/Project-Panorama/Panorama_UE5)

<details open>
<summary><h2>🎥 Part 1. Cinematic Production </h2></summary>

## 1. Visual Concept (Mood)
- **Theme:** `Ethereal`, `Cold but Passionate`, `Cyberpunk Ice`
- **Color Palette:**
  - 🧊 **Base:** Deep Blue (#003366) - 차가운 빙판
  - ✨ **Highlight:** Neon Cyan (#00FFFF) - 스케이트 날의 궤적
  - 🔥 **Accent:** Warm Orange (#FFAA00) - 주인공의 열정(조명)
- **Reference:** 김연아 'Danse Macabre', K/DA 뮤직비디오

## 2. Cinematography Strategy (Camera)
언리얼 엔진의 **Cine Camera Actor**를 활용하여 다음과 같은 연출을 목표로 함.
- **Dynamic Tracking:** 스케이트 날을 로우 앵글(Low Angle)로 따라가는 샷.
- **Dolly Zoom:** 점프 착지 순간 배경이 멀어지는 효과로 긴장감 고조.
- **Depth of Field (DoF):** 배경을 흐리게 처리(Bokeh)하여 캐릭터 표정에 집중.

## 3. Shot List (Sequence Plan)
| Shot | Time | Camera Work | Action | Audio |
| :---: | :---: | :--- | :--- | :--- |
| **S01** | 00:00 | Static (Wide) | 텅 빈 빙판, 조명이 하나씩 켜짐 | 빙판 긁는 소리 (SFX) |
| **S02** | 00:05 | Dolly In (Close-up) | 캐릭터의 떨리는 손끝 -> 눈빛 클로즈업 | 숨소리 + 잔잔한 피아노 |
| **S03** | 00:15 | **Tracking (Fast)** | 빙판을 박차고 나가는 질주 (스피드감) | 음악 템포 상승 (Crescendo) |
| **S04** | 00:30 | Arc Rotate (Slo-mo) | **트리플 악셀 점프 (하이라이트)** | 음악 일시 정지 (Silence) |
| **S05** | 00:45 | Handheld | 착지 후 거친 숨을 몰아쉬며 미소 | 관중 환호성 + 엔딩 곡 |

## 4. Lighting & Atmosphere
- **Lumen Global Illumination:** 실시간 반사광을 통해 얼음의 질감 극대화.
- **Volumetric Fog:** 경기장의 웅장함과 공기 중의 먼지 입자 표현.
- **Post Process:** `Bloom` 효과를 강화하여 몽환적인 분위기 연출.

</details>

<br>

<details>
<summary><h2>🛠️ Part 2. Engineering & Pipeline </h2></summary>

## 1. 프로젝트 개요
- **기간:** 202X.XX.XX ~ 202X.XX.XX (4주)
- **인원:** 6명 (Team Panorama)
- **목표:** 블렌더-언리얼 병렬 파이프라인을 구축하여 고품질의 3D 피겨 스케이팅 숏폼 영상(60s) 제작
- **핵심 기술:** Chaos Cloth Simulation, IK Retargeting, Live Link Face

## 2. 기획 의도
기존의 오프라인 렌더링 방식이 아닌, **언리얼 엔진의 리얼타임 렌더링**을 활용하여 제작 시간을 단축하고 수정이 용이한 파이프라인을 경험한다. 특히 피겨 스케이팅의 역동적인 동작과 의상(치마)의 물리적 움직임을 **Chaos Cloth**로 구현하는 데 기술적 초점을 둔다.

## 3. 기술 스택 (Tech Stack)
| Category | Tool | Usage |
| :--- | :--- | :--- |
| **Engine** | Unreal Engine 5.3 | 메인 씬 구성, 라이팅, 렌더링 |
| **Modeling** | Blender 4.0 | 캐릭터, 의상, 배경 모델링 |
| **VCS** | GitHub + Git LFS | 프로젝트 버전 관리 및 협업 |
| **Animation** | Mixamo / Control Rig | 기본 동작 및 리타기팅 수정 |

## 4. 파이프라인 (Pipeline Workflow)
> **Dummy Workflow 전략 채택:** 모델링 완성을 기다리지 않고 더미(Dummy) 데이터로 병렬 작업 수행
1. **Art Team:** Mixamo 뼈대 기반 모델링 & 텍스처링 (Blender)
2. **Tech Team:** 더미 캐릭터로 애니메이션 시퀀스 & 카메라 연출 (UE5)
3. **Integration:** 최종 모델 Swap 및 웨이트/물리 보정 (TA)

</details>


## 팀 구성
| Unit | Role | Members | Key Tasks |
| :--- | :--- | :--- | :--- |
| **A (Art)** | Char & Costume | @Member1, @Member2 | 메인 캐릭터, 의상 2종 제작 |
| **B (Env)** | Level & Light | @Member3, @Member4 | 아이스링크 구현, 조명, VFX |
| **C (Tech)** | Anim & Pipeline | **@TA(본인)**, @Member5 | 리깅, 물리(Cloth), 깃허브 관리 |

## 주차별 계획 (Roadmap)
- [x] **Week 1:** 기획, 깃허브 Organization 세팅, 더미(Dummy) 영상 제작
- [ ] **Week 2:** 캐릭터/배경 모델링, 애니메이션 리타기팅 R&D
- [ ] **Week 3:** 모델 교체(Swap), 물리 시뮬레이션(Cloth) 적용, 페이셜 연동
- [ ] **Week 4:** 룩뎁(Lookdev), 폴리싱, 최종 렌더링



