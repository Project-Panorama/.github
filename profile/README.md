# ⛸️ Project: Frozen Stage (가제)
> Unreal Engine 5 기반 버추얼 휴먼 피겨 스케이팅 시네마틱 프로젝트

## 📂 Repositories
- 🎨 **Art Source:** [Panorama_ArtSource 바로가기](https://github.com/Project-Panorama/Panorama_ArtSource)
- 🎬 **Unreal Project:** [Panorama_UE5 바로가기](https://github.com/Project-Panorama/Panorama_UE5)
- 📚 **Tech Posting:** [Tech Posting 바로가기]([https://github.com/mi-iron/TechPosting})

<details open>
<summary><h2>🎥 Part 1. Cinematic Production </h2></summary>

### 1. Visual Concept & Storytelling
> **"차가운 빙판 밑에서 헤엄치던 물고기가, 하늘을 나는 요정이 되기까지"**

* **Theme:** `Magical Transformation`, `Dreamy Forest`, `Ice & Light`
* **Music:** 태연 - **"인사 (Panorama)"** (Edited Ver.)
* **Key Assets:**
    * 🧜‍♀️ **Character:** 피겨 스케이팅 선수 $\rightarrow$ 숲의 요정 (의상/헤어 체인지)
    * 🐠 **Mascot:** **'베타(Betta)' 물고기** (빙판 아래 $\rightarrow$ 하늘 위로 비상)
    * 🌿 **Environment:** 차가운 아이스링크 $\rightarrow$ 생명이 피어나는 신비로운 숲

### 2. Mood & Tone (Color Palette)
| Stage | Tone | Color Code | Atmosphere |
| :--- | :--- | :--- | :--- |
| **Stage A (Reality)** | **Cold & Lonely** | 🧊 `#003366` (Deep Blue) | 차가운 빙판, 핀 조명, 관중석의 은은한 응원봉(Light Stick) |
| **Transition** | **Magical** | ✨ `#00FFFF` (Neon Cyan) | 버블(Bubble) 파티클, 빛가루, 의상 변신 이펙트 |
| **Stage B (Fantasy)** | **Warm & Alive** | 🌿 `#44AA00` (Forest Green) | 자라나는 나무와 풀, 따스한 햇살, 흩날리는 긴 머리 |

### 3. Shot List (Sequence Plan)
| Shot | Time | Camera Work | Action & VFX | Asset Ref |
| :---: | :---: | :--- | :--- | :--- |
| **S01** | 00:00 | Static (Wide) | 어두운 링크장, 주인공 위로 **Pin Spot** 조명 하나만 켜짐.| `Pin_Spot_01` |
| **S02** | 00:00 | Dolly In (Close-up) | **스케이트 날(Skates_A)**이 빙판을 가르는 클로즈업.| `Main_Skates_A` |
| **S03** | 00:00 | Tracking (Low) | 빙판 아래로 **물고기(Mascot_Fish_A)**들이 떼를 지어 주인공을 따라옴. 물고기 마리수와 **응원봉(Light_Stick)**의 개수가 점차 늘어남.| `Mascot_Fish_A` `Ice_Link` `Light_Stick`|
| **S04** | 00:00 | **Arc Rotate (Slow)** | **[하이라이트]** 트리플 악셀 점프! **거품(Env_Change)**효과와 함께 **숲(Forest)**으로 배경 전환. | `Env_Change_FX` `Forest_Skybox` |
| **S05** | 00:00 | Follow (Mid) | 착지 순간, 바닥에서 **꽃과 풀(Flower)**이 자라남. 간주 파트에서 **의상(Dress_B)**과 **헤어(Hair_B)**가 화려하게 변함.| `Main_Dress_B` `Main_Hair_B` |
| **S06** | 00:00 | Crane Up (Full) | 기존 배경으로 다시 돌아오고 엔딩 포즈. 로고 크레딧. | `2D_Title_Logo` |

### 4. Technical Art Strategy
이 시네마틱의 핵심 기술 목표는 **"자연스러운 에셋 교체(Swap)"**와 **"환경 변화 연출"**입니다.

* **Dress Swap:** 점프의 정점(Apex)에서 블루프린트 이벤트를 통해 `Dress_A` $\rightarrow$ `Dress_B`로 교체. (프레임 단위 정교함 필요)
* **Groom Binding:** 머리카락이 `Hair_A`(단정함)에서 `Hair_B`(긴 머리 흩날림)로 바뀔 때 물리 시뮬레이션(Physics)이 튀지 않도록 초기화.
* **Material Transition:** `Ice_Link` 쉐이더가 `Dissolve` 되면서 아래의 `Grass` 쉐이더가 드러나도록 머티리얼 인스턴스 제어.
* **Niagara FX:** 스케이트 날의 움직임에 반응하는 `Snow_Spray`와 변신 순간의 `Magic_Dust` 파티클 최적화.
</details>
<details>
<summary><h2>🛠️ Part 2. Engineering & Pipeline </h2></summary>

## 1. 프로젝트 개요
- **기간:** 202X.XX.XX ~ 202X.XX.XX (4주)
- **인원:** 6명
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


## 🙋‍♀️ 팀 구성
| Unit | Role | Members | Key Tasks |
| :--- | :--- | :--- | :--- |
| **A (Art)** | Char & Costume | @Member1, @Member2 | 메인 캐릭터, 의상 2종 제작 |
| **B (Env)** | Level & Light | @Member3, @Member4 | 아이스링크 구현, 조명, VFX |
| **C (Tech)** | Anim & Pipeline | **@TA(본인)**, @Member5 | 리깅, 물리(Cloth), 깃허브 관리 |

## 📆 주차별 계획 (Roadmap)
- [x] **Week 1:** 기획, 깃허브 Organization 세팅, 더미(Dummy) 영상 제작
- [ ] **Week 2:** 캐릭터/배경 모델링, 애니메이션 리타기팅 R&D
- [ ] **Week 3:** 모델 교체(Swap), 물리 시뮬레이션(Cloth) 적용, 페이셜 연동
- [ ] **Week 4:** 룩뎁(Lookdev), 폴리싱, 최종 렌더링



