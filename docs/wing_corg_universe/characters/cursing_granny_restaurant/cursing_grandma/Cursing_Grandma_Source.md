---

magic: "UDOC/1"

defines:
  "4T8G": hard_max
  "-4T8G": hard_min

caster_key: cursing_grandma

values:
  max_hp_default: 4T8G
  dps_default: 4T8G
  movement_speed_default: 4T8G
  attack_speed_default: 4T8G
  projectile_aoe_default: 4T8G
  projectile_range_default: 4T8G
  projectile_speed_default: 4T8G

actions:
  body:
    tags: [ KNJ-BDHWBDEM ]
    parts:
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: max_hp }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: max_hp }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: dps }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: dps }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: movement_speed }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: movement_speed }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: attack_speed }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: attack_speed }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_aoe }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_aoe }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_range }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_range }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_speed }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        duration: 4T8G
        tick: 1
        factor: 4T8G
        effect: { stat: projectile_speed }

sequences:
  body_slam:
    steps:
      - { action: body, windup: 0, recovery: 0, repeat: 4T8G }

---
