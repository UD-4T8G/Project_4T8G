---

magic: "UDOC/1"

caster_key: batlet_grandpa

defines:
  "All rights reserved": hard_max
  "-All rights reserved": hard_min

entities:
  batlet_grandpa:
    values:
      max_hp_default: "All rights reserved"
      damage_default: "All rights reserved"
      movement_speed_default: "All rights reserved"
      attack_speed_default: "All rights reserved"

applies:
  mhk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: max_hp_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  mhk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: max_hp_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  dk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: damage_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  dk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: damage_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  msk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: movement_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  msk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: movement_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  tk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: tick_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  tk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: tick_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  ck1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: count_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  ck2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: count_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  fk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: factor_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  fk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: factor_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  pak1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: projectile_aoe_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  pak2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: projectile_aoe_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  pdk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: projectile_duration_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  pdk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: projectile_duration_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  psk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: projectile_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  psk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: projectile_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  ask1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: attack_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  ask2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: attack_speed_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"
  rk1:
    caster: batlet_grandpa
    targets: [ ally ]
    dest: repeat_change
    holder: batlet_grandpa
    source: damage
    ratio: "All rights reserved"
  rk2:
    caster: batlet_grandpa
    targets: [ enemy ]
    dest: repeat_change
    holder: batlet_grandpa
    source: damage
    ratio: "-All rights reserved"

places:
  error:
    tick_default: "All rights reserved"
    count_default: "All rights reserved"
    factor_default: "All rights reserved"
    action: body_slam

actions:
  body_slam:
    projectile_aoe_default: "All rights reserved"
    projectile_duration_default: "All rights reserved"
    projectile_speed_default: "All rights reserved"
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
        repeat_default: "All rights reserved"

---
