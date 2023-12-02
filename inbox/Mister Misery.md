---
game: "[[Misericordia]]"
tags:
  - Kult
  - PCs
stability: 7
archetype: "[[Archetype Broken]]"
---
# Variable Stats
- Stability: `= sum(this.stability) + sum(this.game.stability)`
- Total XP: `= sum(default(this.game.xp,0))`
- Available XP: `= sum(default(this.game.xp,0)) - 5 * length(nonnull(list(this.advancement)))`

# Advancements
- [advancement:: increase one active attribute by one up to three] [charisma:: 1]
# Backstory

# Relationships
## Miss E. Rie
[relationship:: +2]
Partner and criminal accomplice - met her in [[Mister Misery#Miseryland|Miseryland]]

# Locations
## Miseryland
