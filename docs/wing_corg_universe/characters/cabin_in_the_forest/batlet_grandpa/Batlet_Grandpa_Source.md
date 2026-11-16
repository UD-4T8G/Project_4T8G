---

magic: "UDOC/1"

caster_key: batlet_grandpa

defines:
  "ALL_RIGHTS_RESERVED": hard_max
  "-ALL_RIGHTS_RESERVED": hard_min

values:
  max_hp_default: ALL_RIGHTS_RESERVED
  dps_default: ALL_RIGHTS_RESERVED
  movement_speed_default: ALL_RIGHTS_RESERVED
  attack_speed_default: ALL_RIGHTS_RESERVED
  projectile_aoe_default: ALL_RIGHTS_RESERVED
  projectile_range_default: ALL_RIGHTS_RESERVED
  projectile_speed_default: ALL_RIGHTS_RESERVED

actions:
  body:
    tags: [ KNJ-BDHWBDEM ]
    parts:
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: max_hp }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: max_hp }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: dps }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: dps }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: movement_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: movement_speed }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: attack_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: attack_speed }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_aoe }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_aoe }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_range }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_range }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -ALL_RIGHTS_RESERVED
        duration: ALL_RIGHTS_RESERVED
        tick: 1
        factor: ALL_RIGHTS_RESERVED
        effect: { stat: projectile_speed }

sequences:
  body_slam:
    steps:
      - { action: body, windup: 0, recovery: 0, repeat: ALL_RIGHTS_RESERVED }

---
