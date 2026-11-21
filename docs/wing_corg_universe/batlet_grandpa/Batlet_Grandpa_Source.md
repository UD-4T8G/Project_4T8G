---

magic: "UDOC/1"

caster_key: batlet_grandpa

defines:
  "All rights reserved": hard_max
  "-All rights reserved": hard_min

values:
  max_hp_default: All rights reserved
  damage_default: All rights reserved
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
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: max_hp_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: max_hp_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: damage_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: damage_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: movement_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: movement_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: attack_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: attack_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_aoe_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_aoe_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_range_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_range_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: projectile_speed_change, holder: batlet_grandpa, source: damage }
      - caster: batlet_grandpa
        targets: [ ally ]
        ratio: All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: current_hp, holder: batlet_grandpa, source: damage, fixed: true }
      - caster: batlet_grandpa
        targets: [ enemy ]
        ratio: -All rights reserved
        tick: 0
        count: All rights reserved
        factor: All rights reserved
        apply: { dest: current_hp, holder: batlet_grandpa, source: damage, fixed: true }

sequences:
  body_slam:
    steps:
      - { action: body, windup: 0, recovery: 0, repeat: All rights reserved }

---
