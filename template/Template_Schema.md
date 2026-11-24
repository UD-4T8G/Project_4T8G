---

magic: "UDOC/1"

limits: { hard_min: -2147483648, hard_max: 2147483647 }

caster_key:
  default: null

defines:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: integer | enum [ hard_min, hard_max ]

schema:
  max_hp_default:
    kind: stored
    unit: point
  max_hp_change:
    kind: delta
    unit: percent
  max_hp:
    kind: state
    unit: point
  current_hp:
    kind: state
    unit: point
  lost_hp:
    kind: state
    unit: point

  damage_default:
    kind: stored
    unit: point
  damage_change:
    kind: delta
    unit: percent
  damage:
    kind: state
    unit: point

  movement_speed_default:
    kind: stored
    unit: point
  movement_speed_change:
    kind: delta
    unit: percent
  movement_speed:
    kind: state
    unit: point

  tick_default:
    kind: stored
    unit: point
  tick_change:
    kind: delta
    unit: percent
  tick:
    kind: state
    unit: point

  count_default:
    kind: stored
    unit: point
  count_change:
    kind: delta
    unit: percent
  count:
    kind: state
    unit: point

  factor_default:
    kind: stored
    unit: point
  factor_change:
    kind: delta
    unit: percent
  factor:
    kind: state
    unit: point

  projectile_aoe_default:
    kind: stored
    unit: point
  projectile_aoe_change:
    kind: delta
    unit: percent
  projectile_aoe:
    kind: state
    unit: point

  projectile_duration_default:
    kind: stored
    unit: point
  projectile_duration_change:
    kind: delta
    unit: percent
  projectile_duration:
    kind: state
    unit: point

  projectile_speed_default:
    kind: stored
    unit: point
  projectile_speed_change:
    kind: delta
    unit: percent
  projectile_speed:
    kind: state
    unit: point

  attack_speed_default:
    kind: stored
    unit: point
  attack_speed_change:
    kind: delta
    unit: percent
  attack_speed:
    kind: state
    unit: point

  repeat_default:
    kind: stored
    unit: point
  repeat_change:
    kind: delta
    unit: percent
  repeat:
    kind: state
    unit: point

entities:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: object
    properties:
      values:
        type: object
        default: null
        properties:
          max_hp_default:
            type: integer
            unit: point
            minimum: 0
            default: 0
          damage_default:
            type: integer
            unit: point
            minimum: 0
            default: 0
          movement_speed_default:
            type: integer
            unit: point
            minimum: 0
            default: 0
          attack_speed_default:
            type: integer
            unit: point
            minimum: 0
            default: 0

applies:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: object
    properties:
      caster:
        type: string
        default: null
      targets:
        type: array
        default: null
        items:
          type: enum
          values: [ ally, enemy ]
      dest:
        type: string
        default: null
      holder:
        type: string
        default: null
      source:
        type: string
        default: null
      ratio:
        type: integer
        unit: percent
        default: 100
      fixed:
        type: boolean
        default: false

places:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: object
    properties:
      tick_default:
        type: integer
        unit: point
        minimum: 0
        default: 0
      count_default:
        type: integer
        unit: point
        minimum: 100
        default: 100
      factor_default:
        type: integer
        unit: point
        default: 0
      action:
        type: string
        default: null

actions:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: object
    properties:
      projectile_aoe_default:
        type: integer
        unit: point
        minimum: 0
        default: 0
      projectile_duration_default:
        type: integer
        unit: point
        minimum: 0
        default: 0
      projectile_speed_default:
        type: integer
        unit: point
        minimum: 0
        default: 0
      tags:
        type: array
        items:
          type: string
      applies:
        type: array
        items:
          type: string
      on_hit:
        type: string
      on_impact:
        type: string

sequences:
  type: map
  key_pattern: "^[A-Za-z0-9_-]+$"
  value:
    type: object
    properties:
      steps:
        type: array
        min_items: 1
        default: null
        items:
          type: object
          properties:
            action:
              type: string
              default: null
            windup:
              type: integer
              unit: point
              minimum: 0
              default: 0
            recovery:
              type: integer
              unit: point
              minimum: 0
              default: 0
            repeat_default:
              type: integer
              unit: point
              minimum: 100
              default: 100

---

* magic
  - 문서 형식 식별자
* caster_key
  - 런타임 caster 태그의 접두사
* defines
  - 문서 내 재사용할 상수 명칭 매핑 테이블
  - `limits` 범위 내의 정수 리터럴 또는 `hard_min`, `hard_max` 키워드 허용
  - 정의되지 않은 키를 참조하거나 순환 참조 시 검증 실패
  - 파싱 전처리 단계에서 모든 `integer` 필드의 명칭을 실제 정수로 치환한 뒤 타입 및 `minimum`/`limits` 검증 수행
* **caster**
  - 시전자 태그 항목
  - 런타임에서 `caster_key#(고유ID)` 형식으로 발급
  - 문서에 직접 기입한 값은 런타임 테스트 전용 고정 태그
  - 배치된 actions의 능력치는 배치 시점에 새로 스냅샷을 생성
  - 배치된 actions의 캐스팅 위치는 배치된 지점, 방향은 투사체의 진행 방향
* **unit**
  - 모든 숫자는 **point (%p), percent (%)** 스타일로 표기
  - 모든 시간은 **1ms 당 1%p** 스타일로 표기
    + 시간 0은 생략이 아닌 즉시 처리
  - 모든 횟수는 **1회 당 100%p** 스타일로 표기

* **kind**
  - stored는 기본 능력치의 magic_number를 기입하는 정적 point 항목
  - delta는 능력치 변동 목록 dest의 최종 연산값을 나타내는 동적 percent 항목
  - state는 stored와 delta의 최종 연산값을 나타내는 동적 point 항목
  - 적용된 모든 능력치는 캐스팅 시기의 스냅샷으로 고정
* **default**
  - null은 필수 기입 항목
  - default 항목에 값이 있을 경우 생략 시 해당 값으로 적용
  - default 항목이 없을 경우 생략 시 미적용
  - 선택 항목에 null 기입 시 생략으로 처리
* current_hp
  - 런타임 동적 항목
* lost_hp
  - max_hp - current_hp
* **entities**
  - 개체명을 키로 하는 개체 목록 항목
  - 주인과 소환수는 같은 깊이에 배치하고 주종 관계는 런타임에서 정의
  - values
    + 개체 단위 stored 데이터가 저장된 항목
    + 불변 자료형 사용
  - applies의 caster와 holder는 entities의 개체명 또는 target 예약어
* **applies**
  - caster, holder 항목의 value는 entities에 없을 경우(target 제외) 검증 실패
  - dest
    + 수치 변동 대상 범용 능력치 항목
  - holder
    + source를 불러올 target 항목
    + target은 적중 대상의 런타임 확정 예약어
  - source
    + holder의 모든 state 능력치 항목
    + tick, count, factor, repeat는 holder가 가장 최근 실행한 계산값
    + holder가 실행한 적이 없으면 0
  - ratio
    + dest에 적용할 source 증폭량 delta 수치 항목
    + 음수 허용
  - fixed
    + state dest 능력치 전용
    + change 무시 여부 항목
* dest
  - state
    + current_hp
  - delta
    + *_change
* **places**
  - **tick_default**
    + 배치 간격 수치 항목
    + tick 능력치 연동
    + tick 능력치 1%p 당 1ms
    + 생략 시 0
  - **count_default**
    + 배치 횟수 항목
    + count 능력치 연동
    + count 능력치 100%p 당 1회
    + 100%p 단위 미만 시 내림
    + 생략 시 100
  - **factor_default**
    + 배치 순번 당 ratio 변동 수치 항목
    + 배치 순번마다 배치된 action applies의 ratio에 합산
    + 첫 번째 배치부터 발동
    + factor 능력치 연동
    + 음수 허용
    + 생략 시 0
  - action
    + actions 지속 효과 항목
    + actions에 존재하지 않는 이름은 검증 실패
    + 순환 참조는 **SIGKILL 각오하고** 사용
  - 첫 배치는 tick 0이면 즉시, 아니면 tick 경과 후 발동
* **actions**
  - 스킬명을 키로 하는 스킬 목록 항목
  - 스킬명은 소문자 스네이크 케이스 권장
  - 스킬 단위는 다단히트가 아닌 단일 타격
  - on_hit, on_impact 항목의 value는 places에 없을 경우 검증 실패
  - applies 항목의 value는 applies에 없을 경우 검증 실패
  - projectile movement and destruction
    + 투사체 이동 거리는 `projectile_duration * projectile_speed` 방식으로 결정
    + 생성 즉시 적중 판정 후 파괴 검사 수행(projectile_duration이 0일 경우에도 적중 판정 수행)
    + 각 투사체는 독립적인 벡터를 지니고 타겟 당 한 번만 적중 가능
  - **projectile_aoe_default**
    + projectile_aoe 능력치 연동
  - **projectile_duration_default**
    + projectile_duration 능력치 연동
  - **projectile_speed_default**
    + projectile_speed 능력치 연동
  - on_hit
    + 적중 시 발동하는 places 항목
    + 적중 시점의 타겟 위치에 배치
  - on_impact
    + 착탄 시 발동하는 places 항목
    + 적중에 무관한 투사체 파괴 지점에 배치
  - tags
    + actions 단위 속성 라벨
    + 동일 단위 applies 간 공유
  - applies
    + 단일 타격을 구성하는 applies 객체 나열 목록
    + 생략 시 투사체가 applies 효과를 발동하지 않음(도발 표현 등을 위해 사용)
  - 각 action 객체는 독립적인 on_hit와 on_impact를 보유(부모의 능력치와 무관)
* **sequences**
  - 점사명을 키로 하는 점사 목록 항목
  - 점사명은 소문자 스네이크 케이스 권장
  - steps
    + 점사를 구성하는 step 나열 목록
    + 위에서 아래로 순서대로 진행
  - action
    + 해당 step에서 호출할 actions 항목명
    + actions에 없는 이름은 검증 실패
  - windup
    + step 시작부터 타격이 들어가기까지의 지연 수치 항목
    + attack_speed 능력치 연동
    + 생략 시 0
  - recovery
    + 타격 이후 다음 step 시작까지의 지연 수치 항목
    + attack_speed 능력치 연동
    + 생략 시 0
    + 마지막 step은 점사 종료까지의 지연
  - repeat_default
    + 해당 step의 windup, actions, recovery 전체 반복 횟수 항목
    + repeat 능력치 100%p 당 1회
    + 100%p 단위 미만 시 내림
    + 생략 시 100
