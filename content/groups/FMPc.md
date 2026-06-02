---
publish: true
title: Fabulous Mystical Prophecies
created: 2026-05-29T08:49:42.464-04:00
modified: 2026-06-02T01:38:31.486-04:00
published: 2026-06-02T01:38:31.486-04:00
tags:
  - Category/Group
socialImage: Template_Group_Placeholder.png
draft: false
MyContainer:
  - "[[Barovia|Barovia]]"
MyCategory: Artisan Guild
image: Template_Group_Placeholder.png
obsidianUIMode: preview
leader:
officers:
members:
  - Fabulous Rick Landry
  - Zavran Moonshadow
  - Claire Ich Al-ErRoar
initiates:
  - Kexik
faction: Fabulous Mystical Prophecies
primary_contact:
  - - Fabulous Rick Landry
benefits:
  - standing: 1
    reward: What do they get at level 1?
  - standing: 2
    reward: What do they get at level 2?
  - standing: 3
    reward: What do they get at level 3?
---

![[assets/FMPlogo.png|center lp|400]]

# People

The following people are members of this group.

```base
properties:
  file.name:
    displayName: Group
  note.char_race:
    displayName: Race
  note.char_gender:
    displayName: Gender
  note.pasperc:
    displayName: Passive Perception
  note.group_standing:
    displayName: Group Standing
  note.char_phobia:
    displayName: Phobia
  note.darkvision:
    displayName: Darkvision (ft)
views:
  - type: cards
    name: Group Members - Cards
    filters:
      and:
        - file.folder == "content/party"
        - list(Connected_Groups).contains(this)
    order:
      - file.name
      - char_race
      - Class
      - darkvision
      - pasperc
      - Languages
      - char_phobia
      - group_standing
    sort:
      - property: group_standing
        direction: DESC
    image: note.image
  - type: table
    name: Group Members - Table
    filters:
      and:
        - file.folder == "party"
        - list(Connected_Groups).contains(this)
    order:
      - file.name
    sort: []
    columnSize:
      file.name: 182

```

# History

The companions Rick “Fabulous” Landry, Zavran Moonshadow, and Claire Ich Al-ErRoar met 6 years ago under deeply questionable circumstances inside Baldur’s Gate — specifically, while hiding in the same overturned cheese cart after an angry Duke accused them of “weaponized public embarrassment.”

The incident began with Rick.

A young Gnomish bard with few coin to his name, but a wardrobe worth more than most farmlands, had arrived in Baldur’s Gate intending to debut his newest musical masterpiece: **_Songs to Woo the Dangerous or Dead._**

Unfortunately, during the tavern performance, Rick's magical melody accidentally serenaded the Duke’s wife, three city guards, and what later turned out to be the duke’s horse.

Once the Duke caught wind, guards stormed the tavern, with Rick dramatically leaping onto a table and shouting “You cannot arrest art!” before immediately tripping over a forgotten chamber pot and falling out a window.

Outside, he landed directly on Zavran.

A middle aged Rimekin wizard known locally for flashy illusions and complete disregard for common sense, was in the middle of performing his best magical act, **_“Hide The Mystra”_** for a crowd of unimpressed children.

As Rick collided with The wizard, the spell malfunctioned, causing the nearby chicken stall to explode into flame.

Chaos spread instantly.

While Rick and Zavran fled through the market district pursued by flaming chickens and furious guards, they crashed into Claire — a Tiefling cleric whose true divine gift was not healing, but promotion.

Claire had already hung 400 posters around town advertising herself as:

“CLAIRE THE MIRACULOUS — HEALINGS, BLESSINGS, PROPHETIC NIGHTMARE READINGS, REASONABLE RATES.”

She saw the flaming chickens, the screaming crowd, and immediately recognized opportunity.

“Wait,” Claire said, pointing dramatically. “This isn’t a disaster.”

The magic went haywire, as a chicken exploded behind them.

“This is branding!”

The three escaped together by hiding inside a traveling cheese wagon for two days.

During that time, Rick discovered Zavran’s illusions made his stage performances look incredible, while Claire proved disturbingly good at convincing people that near-fatal accidents were “part of the experience.”

Thus was born:

**_“The Fabulous Mystical Prophecies”_** or **_FMP_** for short.

Their act quickly became infamous across the realm.

Rick sang power ballads while standing atop moving wagons.

Zavran filled the stage with illusions of dragons, flaming chickens, and occasionally duplicate Ricks because “the audience deserves more Rick.”

Claire traveled ahead to every town posting advertisements such as:

“ONE NIGHT ONLY!\
Romance! Magic! Danger!\
POSSIBLY DEATH!”

Attendance was never better, with their next act ahead – Daggerford!

# Goals

> [!NOTE]+ Public Goals
>
> - Achieve This
> - Achieve That

> [!NOTE]- Private Goals
>
> - Achieve This
> - Achieve That

# Hierarchy

````dataviewjs
// 1) Grab your frontmatter arrays
const leader    = dv.current().leader    ?? null;
const officers  = dv.current().officers  ?? [];
const members   = dv.current().members   ?? [];
const initiates = dv.current().initiates ?? [];

// 2) Render the Mermaid diagram
dv.paragraph(
  "```mermaid\nflowchart LR\n" +

  // Leader node
  (leader
    ? `L[${leader}]:::internal-link\n`
    : "") +

  // Officers group
  (officers.length > 0
    ? `OG[Officers]\nL --> OG\n` +
      officers.map((o,i) =>
        `O${i+1}[${o}]:::internal-link\nOG --> O${i+1}\n`
      ).join("")
    : "") +

  // Members group
  (members.length > 0
    ? `MG[Members]\n${officers.length ? "OG" : "L"} --> MG\n` +
      members.map((m,i) =>
        `M${i+1}[${m}]:::internal-link\nMG --> M${i+1}\n`
      ).join("")
    : "") +

  // Initiates group
  (initiates.length > 0
    ? `IG[Initiates]\n${members.length ? "MG" : (officers.length ? "OG" : "L")} --> IG\n` +
      initiates.map((n,i) =>
        `I${i+1}[${n}]:::internal-link\nIG --> I${i+1}\n`
      ).join("")
    : "") +

  "```"
)
````

> [!NOTE]- Relationship Config - Enter name of People Notes
> | Leader    | Officers    |
> | --- | --- |
> | `INPUT[list:leader]`    | `INPUT[list:officers]`    |
>
> | Members    | Initiates    |
> | --- | --- |
> | `INPUT[list:members]`    | `INPUT[list:initiates]`    |

# Enemies/Allies

**Enemies:** `INPUT[inlineListSuggester(optionQuery(#Category/Group),optionQuery(#Category/People)):MyEnemies]`

**Allies:** `INPUT[inlineListSuggester(optionQuery(#Category/Group),optionQuery(#Category/People)):MyAllies]`

# Services

Services offered.

> [!NOTE]+ Public Services
> | Item   | Cost | Weight |
> | ------ | ---- | ------ |
> | Service 1 | 1gp  | L      |
> | Service 2 | 1cp  | -      |

> [!NOTE]- Member Services
> | Item   | Cost | Weight |
> | ------ | ---- | ------ |
> | Service 1 | 1gp  | L      |
> | Service 2 | 1cp  | -      |
