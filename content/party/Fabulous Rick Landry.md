---
publish: true
aliases:
  - MGG
title: Fabulous Rick Landry
created: 2026-05-22T09:55:52.186-04:00
modified: 2026-06-01T13:11:04.186-04:00
published: 2026-06-01T13:11:04.186-04:00
tags:
  - Category/Player
socialImage: FabulousRickLandry.png
draft: false
NoteIcon: player
Player: MGG
Role: Player
Class:
  - Bard
Race:
  - Gnome
level: 1
hp: 9
max_hp: 9
ac: 13
modifier: 2
pasperc: 15
darkvision: 60
Status: Active
PlayerKnownLanguages:
  - Common
  - Dwarvish
  - Elvish
Resistances:
Immunity:
group_standing: Member
char_race: Gnome
char_gender: Male
char_status: Alive
char_phobia: Mysophobia (Dirt/Germs)
char_age: Adult
char_items: []
Connected_Groups:
  - "[[FMPc]]"
parents:
  - Mother
partner:
children:
allies:
  - Claire Ich Al-ErRoar
  - Kexik
  - Palmer A. Neean
  - Zavran Moonshadow
enemies:
siblings:
obsidianUIMode: preview
MyContainer:
image: FabulousRickLandry.png
token: token-FabulousRickLandry.png
---

![[assets/players/FabulousRickLandry.png|right lp|400]]

# Description

This is the persons description.

# Inventory

The following items belong to Fabulous Rick Landry.

Items: `INPUT[inlineListSuggester(optionQuery(#Category/Quest)):char_items]`

# Connections

Is the person linked to any groups or quests?

Quests: `INPUT[inlineListSuggester(optionQuery(#Category/Quest)):Connected_Quests]`

Groups: `INPUT[inlineListSuggester(optionQuery(#Category/Group)):Connected_Groups]`

# Character Sheet

```custom-frames
frame: DDB-FabulousRickLandry
style: height: 1070px;
```

# Relationships

List important relationships here.

````dataviewjs
var parents = dv.current().parents ?? [];
var children = dv.current().children ?? [];
var enemies = dv.current().enemies ?? [];
var allies = dv.current().allies ?? [];
var siblings = dv.current().siblings ?? [];
var current = dv.current().file.name;
var partner = dv.current().partner ?? [];

dv.paragraph("```mermaid\nflowchart LR\n" +
  // Parents with internal-link on individual nodes only
  (parents.length > 0 ? parents.map((parent, index) => `P${index + 1}[${parent}]:::internal-link\nP${index + 1} --> Current\n`).join('') : '') +
  
  // Current node
  `Current[${current}]\n` +
  
  // Partner group node (no internal-link applied)
  (partner.length > 0 ? `PT[Partner]\nCurrent --> PT\n` : '') +
  
  // Individual partners with internal-link
  (partner.length > 0 ? partner.map((p, index) => `PT${index + 1}[${p}]:::internal-link\nPT --> PT${index + 1}\n`).join('') : '') +

  // Children group node (no internal-link applied)
  (children.length > 0 ? `C[Children]\nCurrent --> C\n${children.map((child, index) => `C${index + 1}[${child}]:::internal-link\nC --> C${index + 1}\n`).join('')}` : '') +

  // Siblings group node (no internal-link applied)
  (siblings.length > 0 ? `S[Siblings]\nCurrent --> S\n${siblings.map((sibling, index) => `S${index + 1}[${sibling}]:::internal-link\nS --> S${index + 1}\n`).join('')}` : '') +

  // Enemies group node (no internal-link applied)
  (enemies.length > 0 ? `E[Enemies]\nCurrent --> E\n${enemies.map((enemy, index) => `E${index + 1}[${enemy}]:::internal-link\nE --> E${index + 1}\n`).join('')}` : '') +

  // Allies group node (no internal-link applied)
  (allies.length > 0 ? `A[Allies]\nCurrent --> A\n${allies.map((ally, index) => `A${index + 1}[${ally}]:::internal-link\nA --> A${index + 1}\n`).join('')}` : '') +

  // Styling: Apply internal-link only to individual nodes, not group nodes
  `class ${parents.length > 0 ? parents.map((_, index) => `P${index + 1},`).join('') : ''}Current${children.length > 0 ? children.map((_, index) => `C${index + 1},`).join('') : ''}${siblings.length > 0 ? siblings.map((_, index) => `S${index + 1},`).join('') : ''}${enemies.length > 0 ? enemies.map((_, index) => `E${index + 1},`).join('') : ''}${allies.length > 0 ? allies.map((_, index) => `A${index + 1},`).join('') : ''} internal-link;`
)
````

> [!NOTE]- Relationship Config - Enter name of People Notes
> `BUTTON[button_person]` Nodes will link to notes of the same name.
>
> | Parents    | Partner    | Children |
> | --- | --- | --- |
> | `INPUT[list:parents]`    | `INPUT[list:partner]`    | `INPUT[list:children]`  |
>
> | Siblings    | Enemies    | Allies |
> | --- | --- | --- |
> | `INPUT[list:siblings]`    | `INPUT[list:enemies]`    | `INPUT[list:allies]`  |
