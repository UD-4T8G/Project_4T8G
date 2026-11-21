---

magic: "UDOC/1"

caster_key: characters_template

values:
  max_hp_default: 10000
  damage_default: 100
  movement_speed_default: 100
  attack_speed_default: 100
  projectile_aoe_default: 100
  projectile_range_default: 100
  projectile_speed_default: 100

actions:
  action1:
    tags: []
    parts:
      - caster: characters_template
        targets: [ enemy ]
        ratio: -100
        tick: 0
        count: 1
        factor: 100
        apply: { dest: current_hp, holder: characters_template, source: damage, fixed: false }
      - caster: characters_template
        targets: [ enemy ]
        ratio: -100
        tick: 100
        count: 5
        factor: 100
        apply: { dest: movement_speed_change, holder: target, source: lost_hp }

sequences:
  sequence1:
    steps:
      - { action: action1, windup: 50, recovery: 50, repeat: 1 }

---
