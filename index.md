---
layout: post
---

Welcome to KAOS.
This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).
You are free to share and adapt this material for any purpose, including commercially,
as long as you give attribution.

Hack the rules,
use common sense,
round fractions down (if you want),
and *Have Fun!*.

Characters
==========

Make sure you are familiar and comfortable with the
KAOS rules before you start building your character.

Attributes
----------
There are six attributes that quantify a KAOS character:

**Strength** (STR),
**Agility** (AGI),
**Toughness** (TOU),
<br>
**Perception** (PER),
**Willpower** (WIL),
and **Charisma** (CHA).

To create your character, roll d4+d6+d8+d10+d10+d12+d20 for each attribute.
This is now your character; maybe the group will let you re-roll or rearrange
your scores if you buy dinner!

When we append a `:10` to an attribute's name (for instance `STR:10`), it means that we want the value of that
attribute, divided by 10. We use these `:10`'s throughout these rules.
>
> **Example**:
> A character with a STR of 42 and an AGI of 39 would have a STR:10 of 4 and a AGI:10 of 3.

Traits
------
Having chosen your attribute scores, the second thing to choose is your traits.
Choose two advantages and one disadvantage.
Consult the lists below for inspiration and make up your own to suit your campaign and style of play.

> **Note**:
> By utilizing advantages and disadvantages, we eliminate the traditional race-selection,
> and subsequent tweaking via feats, sub-races, backgrounds, etc.
> Of course you should choose traits that are more or less in line with your race; playing an orc
> with the »tiny« advantage might be a bit weird, but on the other hand, it could lead to some cool back story
> stuff; maybe the orc was cursed by a god, or manipulated by a powerful mage while still in the womb.
>
> If you want more powerful players, you could use three advantages and one or two disadvantages.

### Advantages

{% assign advantages = site.data.advantages | sort: 'name' %}
{% for item in advantages %}
**{{ item.name}}**:
{{ item.description }}
{% if item.remark %}
> {{ item.remark }}
{% endif %}

{% endfor %}

### Disadvantages
{% assign disadvantages = site.data.disadvantages | sort: 'name' %}

{% for item in disadvantages %}
**{{ item.name}}**:
{{ item.description }}
{% if item.remark %}
> {{ item.remark }}
{% endif %}
{% endfor %}


Skills
------

The third thing to do is to choose your skill scores.
You have:
* 1 skill with a score of 20 + WIL + 1d6.
* 1 skill with a score of 10 + PER + 1d6.
* 1 skill with the same score as an attribute of your choice.
* `PER:10` skills with scores of 10 + PER:10 + WIL:10 + 1d6.

{% assign skills = site.data.skills | sort: 'name' %}
{% for item in skills %}
**{{ item.name}}**:
{{ item.description }}
{% if item.remark %}
> {{ item.remark }}
{% endif %}
{% endfor %}


Equipment
---------

You have CHA · 5 gold pieces (GP) with which to purchase your starting equipment.
No matter how many GP you use, you will begin play with CHA gold pieces.

### Armors

Wearing armors and shields will increase your number of hit points,
but they have athletics requirements, and often come with a number of penalties.


| Armor | Cost | HP | Ath. | Notes            |
|-------|:----:|:--:|:-----|------------------|
{%- for item in site.data.armors %}
{{  item.name }}                              |
{{- item.cost }}                              |
{{- item.hp }}                                |
{{- item.athletics }}                         |
{{- item.properties  | join: '&nbsp;' }}      |
{%- endfor %}

`①/②/③/④`:
You take 1, 2, 3, or 4 extra points of strain when you take a surge action.

`ⓜ`:
You can cast magical spells if all pieces of armor worn have the `ⓜ`-symbol.

`ⓢ`:
Your movement rate is decreased by 1.

Armor properties and requirements stack.
> **Example**:
> In order to wear a heavy shield and a scale mail,
> you will need an athletics score of 45+20 = 65, and
> take 3 extra points of strain damage when you take surge actions.
> On the other hand, you also get a total of (5 + 2) 7
> extra hit points.

### Weapons

**H**: The number of hands needed to wield this weapon.

**Range: *x***: This is a missile weapon that has a range of *x* squares.

**Range: M**: This is a melee weapon that can hit opponents in adjacent squares.

**Range: M/*x***: This weapon can be used for melee and ranged combat. It has a range of *x* squares.

**Range: Reach**: This is a melee weapon that can reach opponents two squares away.
<br>

| Weapon | H | Cost | Damage | Range |
|--------|:-:|:----:|:------:|:-----:|
{%- for item in site.data.weapons %}
| {{ item.name -}}
| {{ item.hands -}}
| {{ item.cost -}}
| {{ item.damage -}}
| {{ item.range }}
{%- endfor %}

### Lifestyles

The costs of living outlined below is an indication how how much it would
cost per day to live that given life. It includes everything such as housing,
clothes, food and any type of luxury that might be associated with the
lifestyle such as servants, transportation (sedans, carts, horses, etc.).

{:.nobreak}
{:.goods}
| Lifestyle | Cost |
|-----------|:----:|
{%- for item in site.data.goods.lifestyles %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

### Goods

{:.nobreak}
{:.goods}
| Food | Cost |
|-----------|:----:|
{%- for item in site.data.goods.food %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

{:.nobreak}
{:.goods}
| Clothing | Cost |
|-----------|:----:|
{%- for item in site.data.goods.clothing %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

{:.nobreak}
{:.goods}
| Lodging | Cost |
|-----------|:----:|
{%- for item in site.data.goods.lodging %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

{:.goods}
| Gear      | Cost |
|-----------|:----:|

{%- for item in site.data.goods.gear %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

{:.nobreak}
{:.goods}
| Light Source | Cost |
|--------------|:----:|
{%- for item in site.data.goods.light %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

{:.nobreak}
{:.goods}
| Animal    | Cost |
|-----------|:----:|

{%- for item in site.data.goods.animals %}
| {{ item.name -}}
| {{ item.cost -}}
{%- endfor %}

The Dice and The Game
=====================
To find out if an action succeeds, you roll 1d100 versus a given *target number*.
You succeed if the result of this *test* comes up lower-than or equal to that target number.

**Standard Tests**:
Roll 1d100 vs. the target number.
A target number can be a skill score, an attribute score, or something entirely different
determined by the GM.

**Easy Tests**:
Make two Standard Tests against the target number You succeed if one of the tests succeed.

**Hard Tests**:
Make two Standard Tests against the target number You succeed if both tests succeed.

**Harder and Easier**:
Circumstances can affect the difficulty of tests;
a Standard Test that is made *harder* by circumstances becomes a Hard Test.
Conversely, a Hard Test that is made *easier* becomes a Standard Test.
If both the *harder* and *easier* modifiers apply to the
same test (no matter how many times each modifier applies) the
test remains at its original difficulty level.

**Opposed Tests**:
GM determines the Target Number for each party.
Both parties then roll d100.
If one party beats the target number but the other does not, that party wins.
If it is a tie (i.e. both sides succeeded, or both sides failed), flip a
coin to determine the winner.

> **Note**: The target number does not have to be the same for each party;
> You can pit the Strength of one character against the Agility of another -
> or you can pit one persons Perception against another persons Stealth.

**The 01-rule**:
Whenever you roll a 01 on a roll, you always succeed, even if the test
is *hard* or *opposed*.

**The 100-rule**:
A roll of 100 on the d100 is always a failure, even if the test is *easy*
or *opposed*.

**The 95-rule**:
No matter how high your skill score is or which circumstantial advantages
you may have, your target number can never be higher than 95.

Karma
-----

When your character fails a meaningful roll
(i.e.  one that actually affects the character, party or plot),
she is awarded a karma point. 

You can spend these points to create advantages later in the game.
Most notably, you can spend 2 karma points to make a test *easier*.
You can also spend 3 karma points to reroll a failed test.

A character cannot have more than 10 karma points (this is called the max-karma value).

A character begins every session with 2 karma points (called the karma-reset value),
no matter how many points they accumulated during the previous session.

The GM may The GM can also award karma points to a character if she invokes some
of the character's disadvantages.

> **Note**:
> Karma points are intended to soften the "blow" of missing a roll, as well as adding a
> luck/fate dimension to the game.
> We reset the karma every session to avoid power gaming through the accumulation of karma points.
> It also allows players to refresh their karma without having to fail any checks.
> High powered campaigns might reset the karma to 3 or 4, while more realistic campaigns might reset
> karma to 1 or 0. Some players prefer not to reset at all, possibly imposing upper limits on how many
> karma points a character can have.

Milestones
----------

We use a TV-series analogy to describe the adventuring milestones.

**Sessions**:
are usually 4-hours of game play.
Characters begin every session with exactly 2 karma points,
no matter how many points they accumulated during the previous session.

**Scenes**:
are short sequences within a session. This could be a combat encounter,
a challenging social interaction, or similar.

**Episodes**:
are small adventures or segments of larger adventures.
It usually takes somewhere between 1-3 sessions to complete an episode.
Characters increase the scores of 2 skills by 3 points and one skill by 5 points
at the end of every episode.

**Plotlines**:
span multiple episodes. They may even span multiple seasons.
Multiple plotlines can coexist at the same time.
A plotline could be part of the main adventure path or it could be
a recurring side quest, such as an arch nemisis, that keeps popping up.
Characters increase the scores of one attribute by 5 and another attribute by
3 points ant the end of every plotline.

**Seasons**:
can be considered to be anveture paths. They usually consist of a number of
main plotlines and possibly a number of side-plotlines that do not necessarily
have to be completed.
Characters increase their karma-reset and max-karma by 1 each at the end of every season.

> **Note**:
> It is up to players and GM to decide in advance how often milestones should occur.
>
> The simplest rule is to say that it takes 2-3 sessions to complete an episode, it takes
> 2-3 episodes to complete a plotline, and it takes 2-3 plotlines to complete a season.

Combat
------

There are a number of common terms used in combat:

**Initiative**:
Combat is divided into rounds of about 6 seconds in which combatants act in turn.
At the beginning of each round, each side rolls d100. The side with the highest roll
gets to go first.

**Movement**:
The battle scene is divided into squares about a meter on a side.
Combatants move from square to square like chess pieces.
The number of squares you can move depends on your Movement Rate (MR).

**Hit Points**:
*HP* is how many points of damage you can loose before going unconscious.
Your character has `10` + `AGI:10` + `TOU:10` + `WIL:10` hit points.
You can be damaged by physical attacks against you or by suffering strain
from strenuous activity such as taking Surge Actions or using magic.
Such damage reduces your current number of HP. If you reach zero HP, you go
unconscious, and  you die if you reach -10 HP.

> **Example** A character with AGI 51, TOU 28, and WIL 42 will have
> 10 + 5 + 2 + 4 = 21 hit points.

> **Note**: Wearing armor will increase your HPs. See the [equipment list](#armors)
> to find out how much your HP maximum is increased.

**Attack Rolls**:
To attack someone, you make a skill test to see if you strike the target.
Use the applicable skill: Melee Combat or Ranged Combat for physical attack,
and Arcana for magical attacks.

**Damage Rolls**:
Having successfully struck an opponent you determine how many Hit Points your opponent
looses by rolling the damage dice applicable for your weapon and adding your Damage Bonus.
If you are making a melee attack, the Damage Bonus is `STR:10`.
If you are making a ranged attack, the Damage Bonus is `PER:10`.
Magical attacks do not have a Damage Bonus.

See the [equipment list](#weapons) to find out how much damage your weapon deals.

**Unconsciousness**:
You loose consciousness if you are reduced to 0 Hit Points or lower.

**Death**:
You die if you are reduced to negative 10 HP.

**Natural healing**:
Complete rest, such as sitting or lying down, for 1 hour will replenish 10 HP.

Actions
--------
During each round you can take an »action« such as move, attack, cast a spell, etc.
This is called your Main Action.

**Surge Actions**:
When you have taken your main action you may choose to take one or even two Surge Actions.
Surge Actions are just like Main Actions except that they are strenuous.
Taking a surge action drains 1d4 of your HP.
Wearing heavy armors and shields increase the strain of taking surge actions.

See the [equipment list](#armors)
for more info about additional strain incurred by wearing heavy armor.

Below is a list of possible actions.

{% for action in site.data.actions %}
**{{ action.name }}**:
{{ action.description }}
{% if action.example %}
> {{ action.example }}
{% endif %}
{% endfor %}


Magic
=====

If you have the »Arcana« skill and the »Spellcaster« advantage,
You can only cast magic if you are not wearing armor, or wearing 
armor with the `ⓜ` symbol and have met their Athletics requirements.
If you are wearing armor, you must succeed an Athletics Test
in addition to your Spellcasting test every time you cast a spell.

**Memorization**:
A magic user can only have a certain number of spells memorized
at any given time. The number of spells memorized is equal to the
Arcana skill score divided by 10.

> **Example**:
> A character with Arcana 56 can memorize 5 spells.

**Casting spells**:
To cast a memorized spell, you make an Arcana test.
If the test succeeds, the spell takes effect, and you suffer strain.

**Casting non-memorized spells**:
A character *can* cast spells that they have not memorized.
The character must succeed a *hard* Arcana test and will suffer 1d6 additional strain damage,
*even if the spell fails*.

> **Example**:
> A charcter that casts a non-memorized tier 2 spell will need to roll a *hard*
> Arcana test. If the test succeeds, the spell takes effect and the charcter
> suffers 1d4 + 1d6 damage. If the test fails, the character suffers 1d6 damage.

**Strain**:
The number of HP drained after successfully casting a spell
depends on how powerful the spell is.
The strain occurs *after* the spell was cast.
This means that you can successfully cast a spell and
then fall unconscious by the strain it caused.
You do not suffer any strain damage if you fail to cast your spell.

**Healing**:
You do not regenerate and cannot be healed *in any way* for an hour after
successfully casting a spell or concentrating on a spell.

> **Note**: Casters *can* heal themselves once per hour because the
> healing cooldown only takes effect after casting the spell.

**Tiers**:
Spells are divided into tiers from 1 to 6. Tier 1 spells are very easy to cast,
whereas tier 6 spells are difficult to cast and require a lot of strain.
You cannot cast spells of tiers where your skill score is too low.

> **Example**:
> Casting a tier 4 spell requires that you have at least 50 in
> the Arcana skill. It also means that you suffer 1d8 after successfully
> casting the spell (if memorized).

| Tier | Strain | Skill Score |
|:----:|:------:|:-----------:|
|  1   |   0    |     ≥30     |
|  2   |  1d4   |     ≥30     |
|  3   |  1d6   |     ≥45     |
|  4   |  1d8   |     ≥60     |
|  5   |  1d10  |     ≥75     |
|  6   |  1d12  |     ≥90     |

**Boosting**:
Some spells are *boostable*.
This means that, by spending additional points of strain when casting the spell,
you can increase the given one or more of the spell's aspects such as
duration, damage, range, area of effect, etc.

> **Example**: A spell such as **Healing Touch** has the Boostable tag.
> This means that it costs a single point of strain for each level of boost.
> The spell will heal 1d6 + Bd6 points of damage. Meaning
> that it will heal 1d6 damage, plus an additional 1d6 per level of boost.
> A this a mage can cast the spell with 3 levels of boost, healing 4d6 points
> of damage, and causing the mage 1d4+3 points of strain.

**Duration**:
Unless specified, all non-instantaneous and non-permanent spells
fade away at the *end* of the *next* round.
You can keep the spell from ending by using an action the action next round to Concentrate on that spell,
which will keep it going for another round, where you are free to Concentrate on that spell again.
Outside combat, you can maintain a single spell and still do simple tasks such
as walking, talking, etc. People who know you might notice that you are distracted though.
Spells with fixed durations do not require concentration in any way.

> **Note**:
> My reasons for using this type of concentration is to require spell casters to do nothing
> but concentrating to keep a spell going. They can of course take surge actions to
> move, cast more spells, or even concentrate on more spells. But this will of course be
> extremely draining.

**Range**:
Unless otherwise specified, spells can reach any target within
the caster's line of sight and that the caster can realistically make out.

> **Example**: Targeting a castle 

### Spells

{% assign spells = site.data.spells | sort: 'name' | sort: 'tier' %}

{% for item in spells %}
**{{ item.name }}**:
*Tier {{ item.tags | sort | unshift: item.tier | join: ', '}}*:
{{ item.description }}
{% if item.remark %}
> {{ item.remark }}
{% endif %}

{% endfor %}

