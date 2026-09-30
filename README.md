<img width="508" height="252" alt="title_logo" src="https://github.com/user-attachments/assets/6629d62f-83b2-4e3e-866e-65dedafb3400" />

# CreatorEngine — for <a>Kori The Spritail</a> Project

<h1 align="center">
<img src="https://github.com/user-attachments/assets/052ee7f2-f02f-4c9f-9eb3-43673b9c4fe2" alt="Creator Engine" height="150">
</h1>

## 프로젝트 보존 안내

이 저장소는 게임인재원 졸업작품 **Kori The Spritail** 제작에 사용된 CreatorEngine의 **레거시 보존본**입니다.

졸업작품 개발 버전을 기반으로 하며, 프로젝트 종료 이후 일부 수정이 포함되어 있어 **졸업작품 제출 당시의 코드와 완전히 동일하지는 않습니다.** 당시의 구현에 가까운 코드와 공동 개발 기록을 보존하고 참조할 수 있도록, 이후의 리팩토링 및 신규 개발과 분리하여 별도 저장소로 유지합니다.

현재 진행 중인 엔진 리팩토링과 신규 개발은 **[29thnight/CreatorEngine](https://github.com/29thnight/CreatorEngine)** 저장소에서 이어집니다. 이 저장소에서는 새로운 기능 개발이나 구조 리팩토링을 진행하지 않으며, 기여 내역 확인과 안내 정리 후 **읽기 전용 아카이브로 전환할 예정**입니다.

## 공동 개발 참여자 및 주요 기여

아래는 프로젝트 당시의 역할과 보존된 커밋 이력에서 확인한 주요 작업을 함께 정리한 것입니다. **세부·추가 작업에는 다른 팀원이 작성한 코드의 수정·확장·연동도 포함되며, 해당 시스템 전체를 한 사람이 단독 구현했다는 뜻은 아닙니다.**

| 참여자 | 프로젝트 역할 | 주요 담당 | 커밋 이력에서 확인한 세부·추가 작업 |
| --- | --- | --- | --- |
| [29thnight](https://github.com/29thnight) | 엔진 개발자 | 엔진 구조 설계 및 구현, 렌더러 API 작성 | ImGui 에디터·씬 편집, 모델 에셋 로딩, 리플렉션·YAML 직렬화, C++ DLL 스크립트 핫로드, 코루틴 관리 |
| [joker1092](https://github.com/joker1092) | 프로그래밍 팀장 · 물리 개발자 | 물리 구조 구현, BT 구조 구현, 지형 렌더링·물리 구조 구현 | AI 블랙보드·FSM 기반 구조, BT 시각화·편집 UI, Sweep/Overlap 물리 쿼리, 보스 패턴의 애니메이션·이펙트 연동 |
| [zmalqp123](https://github.com/zmalqp123) | 그래픽스 개발자 | 렌더 후처리 추가 구현, 셰이더 구현 및 확장 | SSGI·PBR 개선, 데칼·물 셰이더·수면 SSR, Tween, 몬스터 스포너, 아시스 행동 및 물리 충돌 처리 보완 |
| [SongSeHwan](https://github.com/SongSeHwan) | 게임 로직 메인 개발자 | 입력 시스템 작성, 애니메이션 이벤트·FSM 구조 구현, 게임 로직 개발 | 게임패드 진동 개선, 검기 발사체, 플레이 데이터·CSV 연동, 씬별 BGM 제어, 보스 사망·클리어 이벤트 |
| [matstar33](https://github.com/matstar33) | 이펙트 시스템 개발자 | 이펙트 시스템 구현 | 파티클 모듈 및 메시·빌보드 렌더 모듈 확장, 이펙트별 셰이더·렌더 상태 설정, 스프라이트 애니메이션 개선, 크기·일시정지 제어, 전투 이펙트·프리팹 |

> **기여 기록의 범위**: 담당 영역은 프로젝트 참여자의 설명을 기준으로 하고, 세부·추가 작업은 작성자별 커밋 로그와 대표 변경 내용을 참고해 보강했습니다. 전체 작업을 빠짐없이 나열한 목록은 아니며, 커밋 메시지만으로 식별하기 어려운 공동 작업이나 누락된 항목이 있을 수 있습니다. 또한 보존본에는 후속 수정이 포함되므로, 모든 항목이 졸업작품 제출 시점에 동일한 상태였다는 의미는 아닙니다. 누락·오기가 있다면 아래의 기존 참여자 안내에 따라 정정을 요청해 주세요.

<details>
<summary><strong>기여 내역 확인에 참고한 대표 커밋</strong></summary>

아래 링크는 각 항목의 작업 기록을 확인하기 위한 대표 사례입니다. 커밋 수나 변경량으로 기여도를 순위화하지 않으며, 수정·확장 기록을 해당 시스템의 최초 구현 기록으로 간주하지 않습니다.

### 29thnight — 엔진·에디터 기반

- 에디터·씬 계층/검사기 및 콜백 유틸리티: [씬 편집·Delegate 관련 작업](https://github.com/29thnight/CreatorEngine-Legacy/commit/32450ad0147de364492397a1252843abf99a2fcb)
- 콘텐츠 로딩·직렬화: [모델 에셋 로딩](https://github.com/29thnight/CreatorEngine-Legacy/commit/10c8e7e82a55f49f1ac8ef8c7d844db45445ccff), [메타데이터·YAML 직렬화](https://github.com/29thnight/CreatorEngine-Legacy/commit/110512289ca4af6472ec2890e5d888d5e13add81)
- 스크립트 실행 기반: [HotLoadSystem 및 Dynamic_CPP 도입](https://github.com/29thnight/CreatorEngine-Legacy/commit/a4b7b573e8c37dee18c3ec5a377f811bca19dce1), [MSBuild 빌드·로그 연동 개선](https://github.com/29thnight/CreatorEngine-Legacy/commit/bd739168af23b9a2ff1692c92518d447bebf1af6)
- 런타임 유틸리티: [코루틴 관리 기능](https://github.com/29thnight/CreatorEngine-Legacy/commit/e00d8d7353e8bb279f283f5bd808019572bbcd21)

### joker1092 — 물리·AI·지형

- AI 기반 구조: [FSM·Blackboard 프레임워크](https://github.com/29thnight/CreatorEngine-Legacy/commit/22e507cb151f1bdad94da1b41178284acd1d0439), [BT 시각화·편집 UI 관련 작업](https://github.com/29thnight/CreatorEngine-Legacy/commit/4dfd208b7742d6f631f12263900900026ba14c60)
- 물리 쿼리·편집 정보: [Box/Sphere/Capsule Sweep·Overlap](https://github.com/29thnight/CreatorEngine-Legacy/commit/faf1fef59741f6bf45dbe05ed704fe2a249a2a8a), [콜라이더 속성 정보](https://github.com/29thnight/CreatorEngine-Legacy/commit/03ed51d5a878479add7333b4fb4e72ae7c222b71)
- 지형 및 게임 연동: [지형 추가·제거 처리 수정](https://github.com/29thnight/CreatorEngine-Legacy/commit/e41c4b9677dce88b053d8b9548ebf49105fa9d06), [보스 패턴·애니메이션 연동](https://github.com/29thnight/CreatorEngine-Legacy/commit/5edafc092848faecc767fb351fbcaedcc27fddaf), [보스 이펙트 연동](https://github.com/29thnight/CreatorEngine-Legacy/commit/c907753b55cac1763869852a3e4edcaf4ac9d8f9)

### zmalqp123 — 그래픽스·게임 연동

- 렌더링·셰이더: [PBR·SSGI 필터링 개선](https://github.com/29thnight/CreatorEngine-Legacy/commit/ac3432814d1aa3d9ee4895da4aabeee0b9dcee61), [데칼 추가·SSGI 수정](https://github.com/29thnight/CreatorEngine-Legacy/commit/f99305efb38eab01fcf4cf034c5b3e0ee518f1ba), [물 셰이더](https://github.com/29thnight/CreatorEngine-Legacy/commit/97ced5871ed2075d7bceb569066547b9ce7cd668), [수면 SSR·오브젝트 그라데이션](https://github.com/29thnight/CreatorEngine-Legacy/commit/10e97b2480f3d3789bcbc21765effd18698f8a80)
- 보간 및 연출 기반: [TweenManager 도입](https://github.com/29thnight/CreatorEngine-Legacy/commit/4e56edfb17119ee694c8f51b50e61369e9345f0f), [Tween·그림자·지형 렌더링 보완](https://github.com/29thnight/CreatorEngine-Legacy/commit/35acf60278ca7ac76a63e5c42c1bfe3908f2bd3a)
- 게임 로직 연동: [몬스터 스포너·프리팹](https://github.com/29thnight/CreatorEngine-Legacy/commit/8beed8fa2d1538531b00c19be14d72119bc24b4f), [아시스의 몬스터 회피·콜라이더 변경](https://github.com/29thnight/CreatorEngine-Legacy/commit/75cb6803b1de3d5d618bee77579430bf4c958ba7)
- 물리 연동 보완: [캐릭터 컨트롤러 간 충돌 검사](https://github.com/29thnight/CreatorEngine-Legacy/commit/afd492d49e68d925ee4bf6f2e8eb81c8a7ba6379), [트리거 충돌 매트릭스 처리](https://github.com/29thnight/CreatorEngine-Legacy/commit/e132e7347dcdcb5ecb27ae5c6b3afe0d86ea0c6b)

### SongSeHwan — 입력·애니메이션·게임 로직

- 입력 및 전투: [게임패드 진동 개선·검기 발사체 추가](https://github.com/29thnight/CreatorEngine-Legacy/commit/1c45de30e9f6d365dbf2bac4de9abba37966ab2d)
- 플레이 데이터·사운드: [PlayData·SoundName 추가 및 CSVLoader 수정](https://github.com/29thnight/CreatorEngine-Legacy/commit/89a91c2f502c9b535849776b0057c32db4cf543f), [씬별 BGMController](https://github.com/29thnight/CreatorEngine-Legacy/commit/ad6439752a952d2f2f3271dd248fe48b0cda40d6)
- 게임 진행 및 연출: [TimeScale·보스 사망·클리어 이벤트](https://github.com/29thnight/CreatorEngine-Legacy/commit/94621fcab3e319bdf2fdf0b86fe0f7c6a18db3cb), [애니메이션 잡 참조 방식·피격 이펙트 연동 수정](https://github.com/29thnight/CreatorEngine-Legacy/commit/55561a5cf22ee40d23ee0b66ea7555a7dc308f77)

### matstar33 — 이펙트 시스템·콘텐츠

- 파티클 모듈: [생성·이동·색상 모듈 관련 작업](https://github.com/29thnight/CreatorEngine-Legacy/commit/c63855796f77d08745e967b54a4202fec5e6e56b), [이펙트 크기 제어·메시 파티클 리팩토링](https://github.com/29thnight/CreatorEngine-Legacy/commit/8293bec5c58c70830ae23c6473dca84b846bf235), [일시정지 기능](https://github.com/29thnight/CreatorEngine-Legacy/commit/3fb83e398a3d651ad91d10d4238334cadb4bee5c)
- 렌더 모듈 확장: [이펙트별 셰이더·렌더 상태 설정 및 스프라이트 애니메이션 개선](https://github.com/29thnight/CreatorEngine-Legacy/commit/9cd5aed089b8f63bbbed1d8e77423f901f0afc8e)
- 게임용 이펙트·프리팹: [회복 이펙트](https://github.com/29thnight/CreatorEngine-Legacy/commit/c46fbe3f5ec40789d42a5ec4a839e6a6faeb4ad1), [차징 근거리 공격 이펙트](https://github.com/29thnight/CreatorEngine-Legacy/commit/462ad5011f071bda0770a56628a28e440920fa89), [무기 교체 이펙트·프리팹](https://github.com/29thnight/CreatorEngine-Legacy/commit/25ced4b61a9eeada4bf6993d5777bcc30d788543)

</details>

---

플랫폼 : Windows

주요 API : WinAPI, DX11

개발 언어 : C++ 20

외부 종속 라이브러리 : DX11, Imgui, Assimp, DirextXTK, nlohmann-json, PhysX, imguizmo, spdlog, pugixml, magic-enum, yaml-cpp, efsw, meshoptimizer, boost-uuid, mimalloc, LZ4

## CreatorEngine 기술 스택 및 라이브러리 개요

CreatorEngine은 Windows 기반 DX11 렌더링 파이프라인과 C++20 모듈형 런타임을 중심으로 구축된 인하우스 게임/툴 엔진입니다. 엔진은 실시간 에디터, 런타임 빌드 파이프라인, 스크립트 핫리로드 등 제작 파이프라인 전반을 아우르는 기능을 제공합니다.

<a href="https://www.youtube.com/watch?v=W75M6eNZhf0">
  <img
    src="https://github.com/user-attachments/assets/8eb2e961-ec65-457b-b90b-1f17bb39c18f"
    alt="스크린샷 2025-10-26 213538"
    width="1917"
    height="1108"
  />
</a>

### 플랫폼 & 언어 타깃
- **운영 체제**: Win32/Win64 환경을 대상으로 하며, 엔진 엔트리 포인트에서 WinAPI 창 관리·메시지 루프와 DX11 초기화를 수행합니다.
- **언어 표준**: 솔루션 전역이 C++20 표준(`stdcpp20`)으로 설정되어 현대적 STL과 템플릿 기능을 활용합니다.
- **빌드 도구**: Visual Studio/MSBuild를 통해 여러 모듈을 동시에 구성하며, 런타임에서는 MSBuild를 호출해 스크립트 DLL을 재빌드할 수 있습니다.

### 렌더링 & 에디터 파이프라인
#### DirectX 11 기반 그래픽스 계층
- **디바이스 관리**: `DeviceResourceManager` 싱글턴이 DX11 디바이스, 컨텍스트, 렌더타겟 및 뷰포트 상태를 중앙집중식으로 관리합니다.
- **셰이더/버퍼 유틸리티**: 상수 버퍼 생성, 샘플러 생성, 드로우 콜 카운트 추적 등의 래퍼가 제공되어 낮은 수준의 DX11 API 호출을 단순화합니다.

#### 에디터 UI & 씬 편집
- **ImGui 기반 에디터**: 엔진은 Dear ImGui 컨텍스트를 구성하고 Win32/DX11 백엔드를 초기화하여 도킹 레이아웃, 스타일링, 멀티 뷰포트 옵션을 활성화합니다.
- **기즈모 조작**: SceneView 윈도우는 ImGuizmo를 사용해 이동·회전·스케일 조작, 스냅, 기즈모 모드 전환을 제공하며, ImGui 도킹 공간에 통합됩니다.
- **로깅 오버레이**: spdlog 기반 로깅 시스템이 파일/메모리 싱크를 묶어 에디터 HUD에 로그를 노출하고, 필터링·색상화를 지원합니다.

#### 콘텐츠 파이프라인
- **모델 임포트**: Assimp를 통해 FBX 등 3D 자산을 읽어 들이고, 스켈레톤/애니메이션/콜라이더 생성 여부를 설정 값으로 제어합니다.
- **지오메트리 최적화**: meshoptimizer를 활용해 LOD 리덕션, 캐시 최적화, 오버드로우 감소 등을 수행하여 렌더 효율을 높입니다.
- **DirectXTK 유틸리티**: SpriteBatch, SaveToDDS/HDR 등 DirectXTK 구성요소를 이용해 UI, 텍스처 캡처, 포스트 프로세싱 파이프라인을 구현합니다.

### 런타임 시스템
#### 물리 시뮬레이션
- NVIDIA PhysX를 통합해 필터 셰이더, 쿼리 필터 콜백, CPU 디스패처 생성, CUDA 컨텍스트 초기화 등 고급 물리 설정을 구성합니다.

#### 오디오 엔진
- FMOD 스튜디오 런타임을 초기화하고, 채널 그룹·볼륨·스트리밍 버퍼·3D 리스너 구성 등을 포함한 사운드 매니저를 제공합니다.

#### 스크립팅 & 핫리로드
~~- **Mono/C# 연동**: 게임 오브젝트에 Mono 기반 스크립트 컴포넌트를 부착하고, 수명 주기를 C++에서 관리합니다.~~
- **핫리로드 파이프라인**: 런타임에서 MSBuild를 호출해 스크립트 솔루션(`Dynamic_CPP`)을 빌드하고, DLL을 재로딩하여 새로운 스크립트를 자동 반영합니다.

### 데이터, 메타 & 직렬화
- **JSON 직렬화**: nlohmann::json을 사용해 파티클 이펙트, 렌더 모듈, 벡터 타입 등을 직렬화/역직렬화합니다.
- **YAML 설정**: 엔진 환경설정과 프로젝트 메타데이터는 yaml-cpp 기반 싱글턴에서 관리하며, MSBuild 경로 등 개발자 옵션을 노출합니다.
- **XML 처리**: 스크립트 핫로드 시스템은 pugixml을 포함해 외부 메타 데이터를 파싱하고 빌드 파이프라인과 연계합니다.
- **자산 메타 감시**: efsw 파일 감시기를 통해 메타 파일 생성/삭제를 감지하고, 누락된 `.meta` 파일을 자동 생성합니다.
- **자산 GUID**: boost::uuids 기반 `FileGuid` 타입이 자산 경로에 대한 안정적인 식별자를 생성·역직렬화합니다.

### 메모리 & 인프라 유틸리티
- **커스텀 메모리 관리**: mimalloc 오버라이드를 포함한 DLL 래퍼를 통해 커스텀 할당/해제를 노출합니다.
- **팩 파일 시스템**: `Paklib` 헤더는 LZ4 압축 훅, AES-256-CTR 암호화, SHA-256 무결성 검사를 갖춘 패키징 런타임을 제공합니다.
- **열거형 리플렉션**: magic_enum을 이용해 런타임 열거형 이름/값 테이블을 생성하고 리플렉션 레지스트리에 등록합니다.

### 프로젝트 모듈 구성
CreatorEngine은 복수의 Visual Studio 프로젝트로 분리되어 있으며, 렌더링(`RenderEngine`), 물리(`Physics`), 스크립트 바인더(`ScriptBinder`), 공용 유틸리티(`Utility_Framework`) 등이 각각 DLL/정적 라이브러리로 빌드됩니다. 엔진 부트스트랩(`EngineEntry`)은 이러한 모듈을 초기화하고, 렌더 루프·사운드 업데이트·스크립트 재빌드 트리거 등 주요 시스템을 조율합니다.

---

이 문서의 기술 설명은 보존된 레거시 버전의 구조와 외부 라이브러리 사용 현황을 이해하기 위한 참고 자료입니다. 현재 개발 중인 CreatorEngine의 구조나 지원 범위와는 구분하여 읽어 주세요.

## 기존 참여자 안내 — 아카이브 전환 예정

기존에 안내한 레거시 저장소 분리에 이어, **졸업작품 관련 코드와 공동 개발 기록을 보존하기 위해 이 저장소를 읽기 전용 아카이브로 전환할 예정**입니다. 이후의 엔진 리팩토링과 신규 개발은 [CreatorEngine](https://github.com/29thnight/CreatorEngine) 저장소에서 진행합니다.

아카이브는 저장소를 삭제하거나 팀원들의 작업을 비공개로 전환하는 조치가 아닙니다. 공개 열람과 포크는 계속 가능하지만, 아카이브 이후에는 이 저장소에 직접 커밋하거나 이슈·PR을 새로 작성하는 등의 변경 작업을 할 수 없습니다. 자세한 동작은 [GitHub의 저장소 아카이브 안내](https://docs.github.com/en/repositories/archiving-a-github-repository/archiving-repositories)를 참고해 주세요.

**담당 영역이나 기여 내역에 누락·오기가 있거나, 포트폴리오에서 참조할 코드·설명에 정정할 내용이 있다면 아카이브 전에 기존 협업 연락 채널을 통해 29thnight에게 알려 주세요.** 관련 파일이나 커밋을 함께 전달해 주시면 확인 후 기록에 반영하겠습니다. 아카이브 이후에 발견한 기록상의 정정 사항도 기존 연락 채널로 전달해 주세요.

이 안내는 공동 작업의 기록을 이후의 개발과 구분하여 보존하기 위한 것이며, 기여 표에 적히지 않은 작업이나 다른 참여자의 기여를 배제하려는 목적이 아닙니다.
