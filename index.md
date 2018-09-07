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
> Of course you should choose traits that are more or less in line with your race. Playing an orc
> with the »tiny« advantage might be a bit weird, but on the other hand, it could lead to some cool back story
> stuff.
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
* `PER:10` skills with scores of 10 + PER:10 + WIL:10 + 1d10.

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
but often at the cost of one or more penalties.



**①**:
You take 1 extra point of strain when you take a surge action.

**②**:
You take 2 extra points of strain when you take a surge action.

**③**:
You take 3 extra points of strain when you take a surge action.

**④**:
You take 4 extra points of strain when you take a surge action.

**ⓜ**:
You cannot cast magical spells while wearing this armor or shield.

**ⓢ**:
Your movement rate is decreased by 1.

Armor properties and requirements stack.
> **Example**:
> In order to wear a heavy shield and a scale mail,
> you will need an athletics score of 45+20 = 65, and
> take 3 extra points of strain damage when you take surge actions.
> On the other hand, you also get a total of (5 + 2) 7
> extra hit points.


| Armor | Cost | HP | Athletics | Properties  |
|-------|:----:|:--:|:---------:|-------------|
{%- for item in site.data.armors %}
{{  item.name }}                              |
{{- item.cost }}                              |
{{- item.hp }}                                |
{{- item.athletics }}                         |
{{- item.properties  | join: '&nbsp;' }}      |
{%- endfor %}

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

> **A gang of thieves try to sneak past a squad of guards**:
> Each thief rolls stealth and each guard all rolls PER.
> The side with fewest failures win. Coinflip breaks ties.

**The 01-rule**:
Whenever you roll a 01 on a roll, you always succeed, even if the test
is *hard* or *opposed*.

**The 100-rule**:
A roll of 100 on the d100 is always a failure, even if the test is *easy*
or *opposed*.

**The 95-rule**:
No matter how high your skill score is or which circumstantial advantages
you may have, your target number can never be higher than 95.

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
from strenuous activity such as taking Surge Actions or using Powers.
Such damage reduces your current number of HP. If you reach zero HP, you go
unconscious, and  you die if you reach -10 HP.

> **Example** A character with AGI 51, TOU 28, and WIL 42 will have
> 10 + 5 + 2 + 4 = 21 hit points.

> **Note**: Wearing armor will increase your HPs. See the [equipment list](#armors)
> to find out how much your HP maximum is increased.

**Attack Rolls**:
To attack someone, you make a skill test to see if you strike the target.
Use the applicable skill: Melee Combat or Ranged Combat for physical attack,
and Witchcraft or Thaumaturgy for magical attacks.

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
During each round you can take an »action« such as move, attack, use a power, etc.
This is called your Main Actions.

**Surge Actions**:
When you have taken your main action you may choose to take one or even two Surge Actions.
Surge Actions are just like Main Actions except that they are strenuous.
Taking a surge action drains 1d4 of your HP.
Wearing heavy armors and shields increase the strain of taking surge actions.

See the [equipment list]({{ '/rulebook/equipment/' | prepend: site.baseurl }})
for more info about additional strain incurred by wearing heavy armor.

{:.noscreen}
Take a look at the equipment list (a separate document) for more information about
strain incurred when wearing heavy armor.

Below is a list of possible actions.

{% for action in site.data.actions %}
**{{ action.name }}**:
{{ action.description }}
{% if action.example %}
> {{ action.example }}
{% endif %}
{% endfor %}


Magic
-----
If you have the skills Witchcraft or Thaumaturgy, you can
cast magical spells.

**Memorization**:
A magic user can only have a certain number of spells memorized
at any given time. The number of spells memorized is equal to the
relevant skill score divided by 10.

> **Example**:
> A character with Witchcraft 56 and Thaumaturgy 21 can
> Memorize 5 Witchcraft spells and 2 Thaumaturgy spells.

**Casting spells**:
To cast a memorized spell, you make a Standard Test for the relevant
skill (Witchcraft or Thaumaturgy). If the test succeeds, the
spell takes effect, and you suffer strain.

**Casting non-memorized spells**:
A character *can* cast spells that they have not memorized.
Doing so, she must succeed a *hard* test for the relevant skill.
And she suffers 1d6 extra strain damage. The character
suffers strain damage *even if the spell fails*.

**Strain**:
The number of HP drained after successfully casting a spell
depends on how powerful the spell is.
The strain occurs *after* the spell was cast.
This means that you can successfully cast a spell and
then fall unconscious by the strain it caused.
You do not suffer any strain damage if you fail to cast your spell.

**Healing**:
You do not regenerate and cannot be healed *in any way* for an hour after
successfully casting a spell.

**Tiers**:
Spells are divided into tiers from 1 to 6. Tier 1 spells are very easy to cast,
whereas tier 6 spells are difficult to cast and require a lot of strain.
You cannot cast spells of tiers where your skill score is too low.

> **Example**:
> Casting a tier 4 Thaumaturgy spell requires that you have at least 50 in
> the Thaumaturgy skill. It also means that you suffer 1d8 after successfully
> casting the spell (if memorized).

| Tier | Strain | Skill Score |
|:----:|:------:|:-----------:|
|  1   |   0    |     ≥20     |
|  2   |  1d4   |     ≥30     |
|  3   |  1d6   |     ≥40     |
|  4   |  1d8   |     ≥50     |
|  5   |  1d10  |     ≥60     |
|  6   |  1d12  |     ≥70     |

**Duration**:
Unless specified, all non-instantaneous and non-permanent spells
fade away at the *end* of the *next* round.
You can keep the spell from ending by using an action the action next round to Concentrate on that spell,
which will keep it going for another round, where you are free to Concentrate on that spell again.
Outside combat, you can maintain a single spell and still do simple tasks such
as walking, talking, etc. People who know you might notice that you are distracted though.

> **Note**:
> My reasons for using this type of concentration is to require spell casters to do nothing
> but concentrating to keep a spell going. They can of course take surge actions to
> move, cast more spells, or even concentrate on more spells. But this will of course be
> extremely draining.

**Range**:
Unless otherwise specified, powers can reach any target within
the caster's line of sight and that the caster can realistically make out.

### Spells

{% for power in site.data.powers %}

**{{ power.name }}** *
{{- power.tiers | join: ', ' -}}
{%- if power.tags -%}
, {{ power.tags | join: ', ' -}}
{%- endif -%}
*
<br>
{{ power.description }}

{% endfor %}

Advancement
-----------

Characters advance by gaining and spending advancement points (AP).
The GM chooses when APs awards are handed out.
Each player should be awarded around 5 to 20 APs per hour of good roleplaying.

{% assign advances = site.data.advancement | sort: 'name' %}
{% for item in advances %}
**{{ item.name }}**:
{{ item.description }}
{% if item.remark %}
> {{ item.remark }}
{% endif %}
{% endfor %}
