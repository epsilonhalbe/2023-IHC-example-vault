---
tags:
  - presentation
  - Obsidian
links: "[[Timelines]]"
date: 2023-12-02
nested: 
  deeper: 
    delving-deeper:
      Moria
---
# Obsidian for GMs and Players

by Martin Heuschober

---
# What is obsidian?

--
- a very powerful note-taking app using [markdown](https://commonmark.org/help/tutorial/) to format notes, allowing you to externalise your brain into a computer.
+ It organises stuff by `folders`, `#tags` and <code>&lsqb;&lsqb;links&rsqb;&rsqb;</code>. Which give you the power to retrieve information when you need it.
+ it has a bunch of built-in and thousands of community plugins, that make it infinitely more useful.

--
# How does this apply to me

--
- Are you writing session notes?
- You want to learn a new game system or remember some rules that always slip your mind?
- You want to schedule/remember the next game sessions?
- Track locations in maps
- Want to quickly create an (N)PC for an upcoming game?

--
## As a player

- Do you want to keep track of your character's progression/status?
- You want to be able to find what you wrote down 20 sessions ago?

--
## As a GM

--
- You want to create a scenario/campaign and need help with
   - Researching
   - Gathering resources
   - Remember rules
   - Dump ideas/hooks
   - Connect Locations/NPCs/PCs/Items etc.
- You are running a campaign and want to keep session notes?
- Need to remember when you scheduled sessions?

---
# Installing obsidian

--
## https://obsidian.md/

Obsidian is available for all major platforms and you can just follow the
installation instructions.

--
## A word about license/payment
If you use obsidian commercially: It is free to use for single person companies
or non-profit organizations.

This company is a small startup founded by two people, now run by eight, if you
enjoy the product consider getting a catalyst license or use their sync/publish
services, if you can afford it.

--
## A word about security

Your data is secure on your harddrive
- Your data is not in any cloud (unless you put it there)
- The sync plugin will encrypt the data over the wire and noone but you has access to your data
- Make backups of your data!
- If you use their publish plugin - the data will be on the internet (d'uh)

This makes sharing your data a little bit more complicated than on cloud based services.

--
## Nomenclature

 - **Markdown**: Formatting language used to format notes
 - **Vault**: fancy name for the folder you put your notes in
 - **Frontmatter** a.k.a. **Properties**: metadata at the top of each note
 - **Orphan note**: note without links to or from
 - **Command Palette**: the standard bindings are `Ctrl/Cmd+P`, I rebound it to `Ctrl/Cmd + <space>`
 
--
## [Example vault](https://github.com/epsilonhalbe/obsidian-workshop-example)
![[download this vault.png]]

--
![[open new vault.png]]

--
![[do you trust me.png]]

--
## Use YouTube and Google
People using Obsidian have an urge to share their experience (as you can tell).

*I don't know if we're just the kind of people obsidian attracts or if obsidian has some inherent juice that makes that happen. For me and what I can see many others say it is the experience of finally having a system that fits my brain.*

<span style="font-size: 0.5em;">N.B.: Tiago Forte assumes there are other types of people as well that collect in a different way - [see this video](https://www.youtube.com/watch?v=f3dDVtJ2sec)</span>

---
# Obsidian flavoured markdown

--
## What is markdown?

a formatting language that allows you to write text in **bold**, *italics*, lists, headlines, quotes,  ==highlight==, ~~strikethrough~~, underline
<!-- element class="fragment" -->
```markdown
**bold** __bold__
*italics* _italics_
==highlight==
~~strikethrough~~
```
<!-- element class="fragment" -->

--
## Headlines and tags

```markdown
# level 1
## level 2
### level 3
#### level 4
##### level 5
###### level 6
#tags <- note no space
```
<!-- element class="fragment" -->

--
## How to format an ordered list

```
- list item 1
+ list item 2
* list item 3
* [ ] checklist is also good
```

--
just don't mix the bullets in the same list (I try to use a different symbol for nested lists, but that is not necessary)

--
```markdown
- first 
   + first nested
   + second nested
- second
```

--
## How to format an ordered list

```
1. list item 1
1. list item 2
```

--
## How to insert links

- `[Illusion Horror Con 20203](https://www.theillusionhorrorcon.events/)`
- <code>&lsqb;&lsqb;internal link|alt text&rsqb;&rsqb;</code>
- <code>&lsqb;&lsqb;internal link#headline|alt text&rsqb;&rsqb;</code>

--
## Images, internal links, pdfs
You can copy paste images which get translated to files in your attachments folder (if set) and you can put pdfs in it as well and even link to certain pages.

--
<pre class="code-wrapper">
<code class="markdown hljs">!&lsqb;&lsqb;imagefile.png|200x300&rsqb;&rsqb;
!&lsqb;alt text&rsqb;(imagefile.png)
![[pdffile.pdf?page=10]]
</code>
</pre>

--
![[Pasted image 20231202182238.png|200]]

--
## Quotes ...

```text
> quotes start with a `>`
```

> quote me on that

--
## ... and callouts
<pre class="code-wrapper">
<code class="markdown hljs"
> &lsqb;!info&rsqb; callouts
</code>
</pre>

> [!info] more at [Obsidian Help](https://help.obsidian.md/Editing+and+formatting/Callouts)

---
# Keeping track of a character
Or at least how I keep track of one

--
## Creating a new note from a template

open the command palette and search for 
![[new from template.png]]

--
## Frontmatter

Frontmatter or Properties is the stuff at the top of the file they start and end with `---` and are formatted in something called YAML.

This is metadata that you can add to your files, which add for searchability and can even be used for automation.

--
```yaml
text: text
date: 2023-12-02
flag: true
number: 0
list1:
  - "a"
  - "b"
  - 1
list2: [ "a", "b", "c" ]
link: "[[[[link]]]]"
```

--
## Links
> [! info] Links are cheap! Don't hesitate to create "potential notes"

Links are the backbone of obsidian (any good note-taking app I'd say).

---
# Creating a session log
You can simply start by adding to the character you created

--
## Extracting a note
and then decide to extract that into a new note by `marking up` + `right click` and `extract into new note`.

--
## Recording session notes

Obsidian has an integrated audio recorder - so you can record session notes, but that is not very helpful. But there is a community plugin "Whisper" - that allows you to dictate and transcribe, thanks to the AI overlords

--
1. Go to https://platform.openai.com and sign up
2. add [billing information](https://platform.openai.com/account/billing/payment-methods)
3. set [a usage limit](https://platform.openai.com/account/limits)
4. generate an [api key](https://platform.openai.com/api-keys)
5. and go to the Plugin's options page to store the key

Just be aware the whisper plugin stores the key in 
`myvault/.obsidian/plugins/whisper/data.json`

--
![[Pasted image 20231124015947.png]]

--
## Searching for information
You can search for text, tag, path or just follow links, or you can use the graph view to narrow down on a few notes. 

---
# Creating a campaign

--
## Keep track of new ideas


--
## Gathering ideas
 1. Check your vault for existing ideas
 2. Always check your vault first for ideas
 3. Create a new canvas
 4. Place your ideas there and connect them

--
## Sorting ideas
Create a canvas
 
![[Pasted image 20231124020951.png]]

or via the command palette.

--
## Creating a timeline

Using April's Automatic Timeline Plugin

Every note that has the following fields in the frontmatter:
```

---
fc-date: 1998-08-05
fc-end: 1998-09-05
---
```


--
## Creating an NPC

--
# Running a campaign

--
## Reminders

I like the day planner plugin 
- [ ] HH:MM - HH:MM 

--
## Session prep

- As the alexandrian said - prep situations not plot
   - I do that on an a4 sheet of paper or my remarkable
- embed playlists `![](https://)`
- embed images/maps/pdfs `![`

--
## Expanding notes

--
# General advice

 - Update your plugins regularly - this is 3rd party software that is of "varying" quality
 - avoid plugins that haven't been updated in a long time
 - make regular backups of your vault
 - learn more about plugins and the capabilities/improvements of obsidian
   this is a tool you're potentially using a lot, so investing a bit of time regularly pays off
 - tidy up your notes regularly, you keep your place where you live clean - use the same reasoning for your "second brain"


--
## Go to the community plugin section and 
