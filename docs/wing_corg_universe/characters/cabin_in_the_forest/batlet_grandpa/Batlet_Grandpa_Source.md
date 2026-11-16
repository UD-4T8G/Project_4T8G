---

magic: "UDOC/1"

caster_key: batlet_grandpa

defines:
  "All rights reserved": hard_max
  "-All rights reserved": hard_min

values:
  max_hp_default: All rights reserved
  dps_default: All rights reserved
  movement_speed_default: All rights reserved
  attack_speed_default: All rights reserved
  projectile_aoe_default: All rights reserved
  projectile_range_default: All rights reserved
  projectile_speed_default: All rights reserved

actions:
  body:
    tags: [ KNJ-BDHWBDEM ]
    parts:
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: max_hp }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: max_hp }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: dps }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: dps }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: movement_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: movement_speed }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: attack_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: attack_speed }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_aoe }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_aoe }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_range }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_range }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_speed }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        duration: All rights reserved
        tick: 1
        factor: All rights reserved
        effect: { stat: projectile_speed }

sequences:
  body_slam:
    steps:
      - { action: body, windup: 0, recovery: 0, repeat: All rights reserved }

---
