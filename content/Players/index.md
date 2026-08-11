---
publish: true
aliases:
  - Short Supply
title: Short Supply
created: 2026-06-04T15:06:29.555-04:00
modified: 2026-07-30T13:45:52.097-04:00
published: 2026-07-30T13:45:52.097-04:00
banner: content/assets/banners/group-of-characters-standing-by-a-camp-fire-image_2874370.png
banner-display: cover
banner-height: 350
banner-x: 50
banner-y: 45
pixel-banner-flag-color: bee
banner-fade: -20
banner-radius: 0
---

```base
properties:
  file.name:
    displayName: Name
  note.char_race:
    displayName: Race
  note.char_gender:
    displayName: Gender
  note.level:
    displayName: Level
  note.pasperc:
    displayName: Passive Perception
  note.ac:
    displayName: AC
  note.max_hp:
    displayName: Max HP
  note.darkvision:
    displayName: Darkvision (ft)
  note.char_phobia:
    displayName: Phobia
views:
  - type: table
    name: Table
    filters:
      and:
        - file.tags.contains("Category/Player")
        - Status != "Inactive"
    order:
      - file.name
      - char_race
      - Class
      - Subclass
      - Resistances
      - pasperc
      - darkvision
      - char_phobia
    sort:
      - property: file.name
        direction: ASC
    columnSize:
      file.name: 167
      note.Class: 93
      note.Resistances: 137
      note.pasperc: 203
      note.darkvision: 168
      note.char_phobia: 284

```
