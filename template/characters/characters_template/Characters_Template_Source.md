---

magic: "UDOC/1"

caster_key: characters_template

values:
  max_hp_default: 10000
  dps_default: 100
  movement_speed_default: 100
  attack_speed_default: 100
  projectile_aoe_default: 100
  projectile_range_default: 100
  projectile_speed_default: 100

actions:
  template_action_1:
    tags: []
    parts:
      - caster: characters_template
        targets: [ enemy ]
        ratio: -100
        duration: 100
        tick: 100
        factor: 100
        apply: { holder: target, source: max_hp, fixed: false }
      - caster: characters_template
        targets: [ enemy ]
        ratio: -100
        duration: 100
        tick: 100
        factor: 100
        effect: { stat: attack_speed }

sequences:
  template_sequence_1:
    steps:
      - { action: template_action_1, windup: 50, recovery: 50, repeat: 1 }

---