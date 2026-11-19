---

magic: "UDOC/1"

meta:
  required: [ magic, caster_key, values ]

limits: { hard_min: -2147483648, hard_max: 2147483647 }

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

  attack_speed_default:
    kind: stored
    unit: point
  attack_speed_change:
    kind: delta
    unit: percent
  attack_speed:
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

  projectile_range_default:
    kind: stored
    unit: point
  projectile_range_change:
    kind: delta
    unit: percent
  projectile_range:
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

payload:
  type: object
  required: [ caster, targets, ratio, tick, count, factor, apply ]
  properties:
    caster:
      type: string
    targets:
      type: array
      items:
        type: enum
        values: [ ally, enemy ]
    ratio:
      type: integer
      unit: percent
    tick:
      type: integer
      unit: point
      minimum: 0
    count:
      type: integer
      minimum: 1
    factor:
      type: integer
      unit: percent
      minimum: 1
    apply:
      type: object
      required: [ dest, holder, source ]
      properties:
        dest: { type: string }
        holder: { type: string }
        source: { type: string }
        fixed:
          type: boolean
          default: false

actions:
  type: map
  key_pattern: "^[a-z][a-z0-9_]*$"
  value:
    type: object
    required: [ parts ]
    properties:
      tags:
        type: array
        items: { type: string }
      parts:
        type: array
        min_items: 1
        items: { type: payload }

sequences:
  type: map
  key_pattern: "^[a-z][a-z0-9_]*$"
  value:
    type: object
    required: [ steps ]
    properties:
      steps:
        type: array
        min_items: 1
        items:
          type: object
          required: [ action ]
          properties:
            action:
              type: string
            windup:
              type: integer
              unit: point
              minimum: 0
            recovery:
              type: integer
              unit: point
              minimum: 0
            repeat:
              type: integer
              minimum: 1

---

* **meta**
  - magic
    + 문서 형식 식별자
  - caster_key
    + 런타임 caster 태그의 접두사
  - values
    + stored 데이터가 저장된 항목
    + 불변 자료형 사용(생성 후 변경 불가, 중첩 요소도 동일)
* **unit**
  - 모든 숫자는 **point (%p), percent (%)** 스타일로 표기
  - 모든 지속시간은 **1초 당 100%p**로 표기
* **kind**
  - stored는 기본 능력치의 magic_number를 기입하는 정적 point 항목
  - delta는 능력치 변동 목록 dest의 최종 연산값을 나타내는 동적 percent 항목
  - state는 stored와 delta의 최종 연산값을 나타내는 동적 point 항목
* current_hp
  - 런타임 동적 항목
* lost_hp
  - max_hp - current_hp
* **caster**
  - 시전자 태그 항목
  - 런타임에서 `caster_key#(고유ID)` 형식으로 발급
  - 문서에 직접 기입한 값은 런타임 테스트 전용 고정 태그
* **ratio**
  - dest에 적용할 source 증폭량 delta 수치 항목
  - 음수 허용
* **tick**
  - 적용 간격 수치 항목
  - 타수와 무관한 단일 타격 안의 지속 효과 간격
  - delta dest 능력치에 0 사용 시 최소 단위로 적용
* **count**
  - tick 발동 횟수 항목
* **factor**
  - tick 당 ratio 변동 delta 곱연산 수치 항목
  - 첫 tick 부터 적용
* **apply**
  - 스냅샷 능력치 탑다운 적용
  - dest
    + 수치 변동 대상 범용 능력치 항목
  - holder
    + source를 불러올 target 항목
    + target은 적중 대상의 런타임 확정 예약어
  - source
    + holder의 모든 state 능력치 항목
  - fixed
    + state dest 능력치 전용
    + change 무시 여부 항목
* dest
  - state
    + current_hp
  - delta
    + *_change
* **actions**
  - 스킬명을 키로 하는 스킬 목록 항목
  - 스킬명은 소문자 스네이크 케이스
  - 스킬 단위는 다단히트가 아닌 단일 타격
  - tags
    + action 단위 속성 라벨
    + 동일 단위 parts 간 공유
  - parts
    + 단일 타격을 구성하는 payload 객체 나열 목록
* **sequences**
  - 점사명을 키로 하는 점사 목록 항목
  - 점사명은 소문자 스네이크 케이스
  - steps
    + 점사를 구성하는 step 나열 목록
    + 위에서 아래로 순서대로 진행
  - action
    + 해당 step에서 호출할 actions 항목명
    + actions에 없는 이름은 검증 실패
  - windup
    + step 시작부터 타격이 들어가기까지의 지연 수치 항목
    + 생략 시 0
  - recovery
    + 타격 이후 다음 step 시작까지의 지연 수치 항목
    + 생략 시 0, 마지막 step은 점사 종료까지의 지연
  - repeat
    + 해당 step 반복 횟수 항목
    + 생략 시 1
