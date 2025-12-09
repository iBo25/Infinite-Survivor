⚔️ Infinite Survivor (2D Roguelite Survival)
"시작부터 끝까지 멈추지 않는 액션! 20분간 쏟아지는 몬스터 웨이브 속에서 생존하라."

Unity로 개발한 2D 탑다운 로그라이트 서바이벌 게임입니다. Vampire Survivors와 Brotato의 핵심 재미 요소를 분석하여, **끊김 없는 몰입감(Seamless Experience)**과 데이터 주도적(Data-Driven) 설계를 목표로 개발되었습니다.

🎮 게임 개요 (Game Overview)
장르: 2D Action Roguelite

엔진: Unity 2022

목표: 20분 동안 끊임없이 몰려오는 몬스터들로부터 생존하고 최종 보스를 처치.

핵심 루프: 전투 → 경험치 획득 → 즉시 레벨업(스킬 선택) → 빌드 구축 → 생존

✨ 핵심 기능 (Key Features)
1. 데이터 주도 설계 (ScriptableObject 활용)
하드코딩을 배제하고 ScriptableObject를 적극 활용하여, 컴파일 없이 데이터 수정만으로 게임 밸런스를 조절할 수 있는 유연한 구조를 구축했습니다.

WeaponData: 무기별 기본 스탯, 투사체 프리팹, 레벨별 강화 수치 관리.

StatUpgradeData: 공격력, 쿨타임, 이속 등 다양한 스탯의 성장 수치와 희귀도(Rarity) 관리.

2. 타임라인 스폰 시스템 (Spawn Timeline)
단순 반복 웨이브가 아닌, 시간 흐름에 따른 정교한 연출을 위해 타임라인 기반 스폰 시스템을 구현했습니다.

MobSpawner에서 시간대별(Trigger Time) 이벤트를 리스트로 관리.

특정 시간에 대량 스폰, 중간 보스 등장, 패턴 변화 등을 타임라인으로 제어.

플레이어 위치 기반 동적 스폰 위치 계산 (안전 반경 제외 알고리즘).

3. 끊김 없는 인게임 레벨업 (Seamless Level Up)
게임의 흐름을 끊는 별도의 상점 씬(Scene) 이동을 제거하고, 전투의 연속성을 유지했습니다.

레벨업 시 Time.timeScale을 조절하여 즉시 팝업 UI 표시.

가중치 랜덤 시스템(Weighted Random): 희귀도에 따라 스킬 등장 확률 차등 적용.

스마트 필터링: 이미 마스터(Max Level)한 스킬은 선택지에서 자동 제외 및 대체 보상(체력 회복) 제공.

4. 최적화 및 시스템
Physics Layer Matrix: 몬스터끼리는 밀어내고, 플레이어는 통과하도록 물리 레이어 충돌 최적화.

Y-Sorting: 2D 탑다운 시점에서의 자연스러운 원근감을 위한 스프라이트 정렬 처리.

🛠️ 기술 스택 (Tech Stack)
Language: C#

Engine: Unity

Design Pattern: Singleton (Manager Classes), Component-Based Architecture
