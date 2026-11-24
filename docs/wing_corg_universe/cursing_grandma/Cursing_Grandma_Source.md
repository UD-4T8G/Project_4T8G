---

magic: "UDOC/1"

caster_key: cursing_grandma

defines:
  "4T8G": hard_max
  "-4T8G": hard_min

entities:
  cursing_grandma:
    values:
      max_hp_default: "4T8G"
      damage_default: "4T8G"
      movement_speed_default: "4T8G"
      attack_speed_default: "4T8G"

applies:
  mhk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: max_hp_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  mhk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: max_hp_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  dk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: damage_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  dk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: damage_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  msk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: movement_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  msk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: movement_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  tk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: tick_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  tk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: tick_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  ck1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: count_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  ck2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: count_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  fk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: factor_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  fk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: factor_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  pak1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: projectile_aoe_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  pak2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: projectile_aoe_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  pdk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: projectile_duration_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  pdk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: projectile_duration_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  psk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: projectile_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  psk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: projectile_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  ask1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: attack_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  ask2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: attack_speed_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"
  rk1:
    caster: cursing_grandma
    targets: [ ally ]
    dest: repeat_change
    holder: cursing_grandma
    source: damage
    ratio: "4T8G"
  rk2:
    caster: cursing_grandma
    targets: [ enemy ]
    dest: repeat_change
    holder: cursing_grandma
    source: damage
    ratio: "-4T8G"

places:
  error:
    tick_default: "4T8G"
    count_default: "4T8G"
    factor_default: "4T8G"
    action: body_slam

actions:
  body_slam:
    projectile_aoe_default: "4T8G"
    projectile_duration_default: "4T8G"
    projectile_speed_default: "4T8G"
    on_hit: error
    on_impact: error
    tags: [ KNJ-BDHWBDEM ]
    applies:
      - mhk1
      - mhk2
      - dk1
      - dk2
      - msk1
      - msk2
      - ask1
      - ask2
      - tk1
      - tk2
      - ck1
      - ck2
      - fk1
      - fk2
      - pak1
      - pak2
      - pdk1
      - pdk2
      - psk1
      - psk2
      - rk1
      - rk2

sequences:
  sequence1:
    steps:
      - action: body_slam
        windup: 0
        recovery: 0
        repeat_default: "4T8G"

---
