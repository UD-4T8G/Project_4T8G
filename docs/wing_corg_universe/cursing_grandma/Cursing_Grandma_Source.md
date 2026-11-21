---

magic: "UDOC/1"

defines:
  "4T8G": hard_max
  "-4T8G": hard_min

caster_key: cursing_grandma

values:
  max_hp_default: 4T8G
  damage_default: 4T8G
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
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: max_hp_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: max_hp_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: damage_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: damage_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: movement_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: movement_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: attack_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: attack_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_aoe_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_aoe_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_range_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_range_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: projectile_speed_change, holder: cursing_grandma, source: damage }
      - caster: cursing_grandma
        targets: [ ally ]
        ratio: 4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: current_hp, holder: cursing_grandma, source: damage, fixed: true }
      - caster: cursing_grandma
        targets: [ enemy ]
        ratio: -4T8G
        tick: 0
        count: 4T8G
        factor: 4T8G
        apply: { dest: current_hp, holder: cursing_grandma, source: damage, fixed: true }

sequences:
  body_slam:
    steps:
      - { action: body, windup: 0, recovery: 0, repeat: 4T8G }

---
