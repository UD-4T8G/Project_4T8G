---

magic: "UDOC/1"

caster_key: characters_template

entities:
  main:
    values:
      max_hp_default: 10000
      damage_default: 100
      movement_speed_default: 100
      attack_speed_default: 100

applies:
  apply1:
    caster: main
    targets: [ enemy ]
    dest: current_hp
    holder: main
    source: damage
    ratio: -100
    fixed: false
  apply2:
    caster: main
    targets: [ enemy ]
    dest: movement_speed_change
    holder: target
    source: lost_hp
    ratio: -1

places:
  place1:
    tick_default: 0
    count_default: 100
    factor_default: 0
    action: action1_projectile
  place2:
    tick_default: 1000
    count_default: 500
    factor_default: 0
    action: action2_projectile

actions:
  action1:
    projectile_aoe_default: 0
    projectile_duration_default: 0
    projectile_speed_default: 0
    on_hit: null
    on_impact: place1
    tags: []
    applies: null
  action1_projectile:
    projectile_aoe_default: 100
    projectile_duration_default: 100
    projectile_speed_default: 100
    on_hit: null
    on_impact: null
    tags: []
    applies:
      - apply1
  action2:
    projectile_aoe_default: 0
    projectile_duration_default: 0
    projectile_speed_default: 0
    on_hit: null
    on_impact: place2
    tags: []
    applies: null
  action2_projectile:
    projectile_aoe_default: 100
    projectile_duration_default: 100
    projectile_speed_default: 100
    on_hit: null
    on_impact: null
    tags: []
    applies:
      - apply2

sequences:
  sequence1:
    steps:
      - action: action1
        windup: 500
        recovery: 250
        repeat_default: 100
      - action: action2
        windup: 250
        recovery: 500
        repeat_default: 100

---
