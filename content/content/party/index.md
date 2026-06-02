---
publish: true
title: The Party
created: 2026-05-29T08:50:54.791-04:00
modified: 2026-06-02T08:23:00.412-04:00
published: 2026-06-02T08:23:00.412-04:00
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
        - file.folder == "content/party"
        - file.tags.contains("Category/Player")
    order:
      - file.name
      - Player
      - level
      - Class
      - char_race
      - pasperc
      - Resistances
      - char_phobia
      - darkvision
    sort:
      - property: level
        direction: ASC
    columnSize:
      file.name: 167
      note.level: 101
      note.Class: 93
      note.pasperc: 159
      note.char_phobia: 284
      note.darkvision: 168

```
