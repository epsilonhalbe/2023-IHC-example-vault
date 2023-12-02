---
title: John Smith
date: 2023-12-02
template: "[[kult.aware.pc]]"
template_version: 1
tags:
  - Kult
  - PCs
  - TTRPGs
game: "[[KULT - Pocahontas]]"
game_system: "[[Kult divinity lost (system)]]"
name: 
pronouns: []
archetype: 
dark_secret: |
  multiline text
  for longer stuff
disadvantages: []
advantages: []
stability: 10
fortitude:
reflexes:
willpower:
charisma:
coolness:
intuition:
perception: 
reason: 
soul: 
violence: 
---

# Stats
```dataviewjs
let charsheet = dv.current().file
let log = dv.page(dv.parse(charsheet.frontmatter.game).path)
let advancements = charsheet.tasks.where(t => t.checked && t.advancement)
let woundPenalty = log.file.tasks.where(t => !t.checked && t.serious_wound).length ? 1 : 0
                 + log.file.tasks.where(t => !t.checked && t.critical_wound).length ? 1 : 0 
let stabilityChanges = dv.array(dv.page(dv.parse(charsheet.frontmatter.game).path).stability).values.filter(x => x !== undefined).reduce((a,b) => a + b, 0)
let xp = (charsheet.frontmatter.xp ?? 0 /* if there was some starting xp */) + (log.xp ?? []).reduce((a,b) => a+b, 0)
let stability = (() => {
  let moderate = {disadvantage: -1}
  let serious = {disadvantage: -2, willpower: -1}
  let critical = {disadvantage: -3, willpower: -2, soul: 1}
  switch(charsheet.frontmatter.stability ) {
     case 10: return {status: "composed"}
     case 9: return {status: "uneasy", ...moderate}
     case 8: return {status: "unfocused", ...moderate}
     case 7: return {status: "shaken", ...serious}
     case 6: return {status: "distressed", ...serious}
     case 5: return {status: "neurotic", ...serious}
     case 4: return {status: "anxious", ...critical}
     case 3: return {status: "irrational", ...critical}
     case 2: return {status: "unhinged", ...critical}
     case 1: return {status: "broken"};
  }
})()
let stats = {
  "General": {
     stability: stability.status,
     disadvantage: stability.disadvantage ?? 0
  },
  "Passive attributes": {
     fortitude: charsheet.frontmatter.fortitude + advancements.fortitude.values.reduce((a,b) => a+b, 0) - woundPenalty,
     willpower: charsheet.frontmatter.willpower + advancements.willpower.values.reduce((a,b) => a+b, 0) + (stability.willpower ?? 0) - woundPenalty,
     reflexes: charsheet.frontmatter.reflexes + advancements.reflexes.values.reduce((a,b) => a+b, 0) - woundPenalty
  },
  "Active attributes": {
     charisma: charsheet.frontmatter.charisma + advancements.charisma.values.reduce((a,b) => a+b, 0) - woundPenalty,
     coolness: charsheet.frontmatter.coolness + advancements.coolness.values.reduce((a,b) => a+b, 0) - woundPenalty,
     intuition: charsheet.frontmatter.intuition + advancements.intuition.values.reduce((a,b) => a+b, 0) - woundPenalty,
     perception: charsheet.frontmatter.perception + advancements.perception.values.reduce((a,b) => a+b, 0) - woundPenalty,
     reason: charsheet.frontmatter.reason + advancements.reason.values.reduce((a,b) => a+b, 0) - woundPenalty,
     soul: charsheet.frontmatter.soul + advancements.soul.values.reduce((a,b) => a+b, 0) + (stability.soul ?? 0) - woundPenalty,
     violence: charsheet.frontmatter.violence + advancements.violence.values.reduce((a,b) => a+b, 0) - woundPenalty
  },
  "Advancement": {
    XP: xp,
    "available advancements": xp / 5 - charsheet.tasks.where(t => t.checked && t.advancement).length
  },
}
for (const [category, entries] of Object.entries(stats)) {
  dv.header(2, category)
  dv.list(Object.entries(entries).map(([k,v]) => `**${k}:** ${v}`))
}
```


```dataviewjs
let charsheet = dv.current().file
let log = dv.page(dv.parse(charsheet.frontmatter.game).path)
let advancements = charsheet.tasks.where(t => t.checked && t.advancement)
let section = {
  "Serious wounds": log.file.tasks.where(t => !t.checked && t.serious_wound),
  "Critical wounds": log.file.tasks.where(t => !t.checked && t.critical_wound)
}

for (const [category, entries] of Object.entries(section)) {
  dv.header(2, category)
  if (entries.length > 0) dv.taskList(entries, false)
}
```
 > [!info] You can at most sustain 4 serious wounds, every additional wound becomes critical. And one critical wound, any additional critical wound means death.",

```dataviewjs
let charsheet = dv.current().file
let log = dv.page(dv.parse(charsheet.frontmatter.game).path)
let advancements = charsheet.tasks.where(t => t.checked && t.advancement)
let section = {
  "Advantages": charsheet.frontmatter.advantages.concat(advancements.advantage.values ?? []),
  "Disadvantages": charsheet.frontmatter.disadvantages.concat(log.disadvantage ?? []),
}

for (const [category, entries] of Object.entries(section)) {
  dv.header(2, category)
  if (entries.length > 0) dv.list(entries, true)
}
```
# Advancements
## Aware advancements
add upgraded attributes in the form `[<attribute name>:: 1]` and advantages `[advantage:: "[[link to advantage]]"`
- [ ] [advancement:: increase one active attribute by 1 up to 3]
- [ ] [advancement:: increase one active attribute by 1 up to 3]
- [ ] [advancement:: increase one active attribute by 1 up to 3]
- [ ] [advancement:: increase one active attribute by 1 up to 3]
- [ ] [advancement:: increase one active attribute by 1 up to 3]
- [ ] [advancement:: increase one passive attribute by 1 up to 3]
- [ ] [advancement:: increase one passive attribute by 1 up to 3]
- [ ] [advancement:: increase any attribute by 1 up to 4]
- [ ] [advancement:: select a new advantage from your archetype]
- [ ] [advancement:: select a new advantage from your archetype]
- [ ] [advancement:: select a new advantage from your archetype]

## After 5 advancements you may also choose
- [ ] [advancement:: increase any attribute by 1 up to 4]
- [ ] [advancement:: increase any attribute by 1 up to 4]
- [ ] [advancement:: select a new advantage from any aware archetype]
- [ ] [advancement:: select a new advantage from any aware archetype]
- [ ] [advancement:: End your character's story arc as you see fit, and create a new Aware character, who starts with 2 advancements]
- [ ] [advancement:: Replace your current Archetype with another Aware Archetype, and erase one of your starting 3 advantages]
## After 10 advancements you may also choose
- [ ] [advancement:: Advance your character to an Enlightened Archetype]

# Backstory
# Relationships