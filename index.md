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

To create your character, roll d4+d6+d8+d10+d10+d12+d20 (thats right, roll all your 7 dice and add them up)
for each attribute. This is now your character! Maybe the GM will let you roll another if you're whiny about it.

When we append a `:10` to one of the attributes (for instance STR:10), it means that we want the value of that
attribute, divided by 10. We use these `:10` throughout these rules.

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

You get 50 + INT + PER + CHA points to assign to your skils

All skills start at zero, and they all have a **max score**,
which is the maximum allowed score for that skill.

> A character with STR 21 and AGI 15 would be able to increase
> the acrobatics skill up to 36. This would cost 36 skill points.

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

**DP**:
The number of Defense Points you have if wearing this armor.
Defense Points are used to deflect an opponent's attacks.
Shields increase the number of DPs.
You can spend one DP to make a single attack against you
<i>harder</i> or you can spend 3 DP to make an attacker re-roll
their last attack roll.

**MR**:
This is how the armor affects your movement rate.

**Athletics**:
Armors may require you to have a certain score in Athletics - otherwise
your movement rate is reduced by 2 (in addition to any penalties the armor may already impose).
Shields add to your DPs, but also the overall Athletics requirements, movement rate penalties and
strain penalties.

**Strain**:
Is the number of additional points of strain damage you take every time you take a Surge Action.

> **Example 1**: A person wearing Hardened Leather and a Light Shield and an
> AGI of 23 will have a Defense Score of 23÷10+2+1&nbsp;=&nbsp;5,
> and an Athletics requirement of 20+10&nbsp;=&nbsp;30.
> Such a character would take 1d4&nbsp;+&nbsp;1 points of strain damage
> for every surge action taken.

> **Example 2**: A person wearing Chain Mail and a Tower Shield will have
> a Defense Score of 4+3 = 7, a Movement Rate penalty of 1+2&nbsp;=&nbsp;3, and
> an Athletics requirement of 35+20 = 55.
> Such a character would take 1d4&nbsp;+&nbsp;3 points of strain damage
> for every surge action taken.

| Armor | Cost | DPs | MR | Athletics | Strain |
|:------|:----:|:---:|:--:|:---------:|:------:|
{%- for item in site.data.armors %}
{{  item.name }}      |
{{- item.cost }}      |
{{- item.dp }}        |
{{- item.mr }}        |
{{- item.athletics }} |
{{- item.strain }}    |
{%- endfor %}
{%- for item in site.data.shields %}
{{  item.name }}      |
{{- item.cost }}      |
{{- item.dp }}        |
{{- item.mr }}        |
{{- item.athletics }} |
{{- item.strain }}    |
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
In the beginning of every combat, each combatant rolls the *initiative* they use
for the rest of that combat: AGI+1d10.
Each round, each combatant acts in turn in the order of their initiative, from highest to
lowest.

**Movement**:
The battle scene is divided into squares about a meter on a side.
Combatants move from square to square like chess pieces.
The number of squares you can move depends on your Movement Rate (MR).

**Hit Points**:
*HP* is how many points of damage you can loose before going unconscious.
Your character has STR + TOU + WIL hit points.
You can be damaged by physical attacks against you or by suffering strain
from strenuous activity such as taking Surge Actions or using Powers.
Such damage reduces your current number of HP. If you reach zero HP, you go
[unconscious](#unconsciousness), and  you [die](#death) if you reach -30 HP.

**Defense Points**:
*DP* are the number of times per combat (not round) you can try and avoid
non-magical attacks. When an opponent declares that they want to attack you,
but before they actually roll any dice, you can declare that you want to
defend against the attack, making the test [*Harder*](#harder-and-easier).

You can also defend against an attack *after* an attacker has successfully
struck you, but *before* they roll for damage.
This costs 3 DP, and it forces the attacker to re-roll their attack test.

You can also defend against an attack after the attacker has rolled damage.
This costs 5 DP, and it forces the attacker to re-roll both attack and damage.

The number of DPs your character has depends on their AGI and the armor
they're wearing.

**Attack Rolls**:
To attack someone, you make a skill test to see if you strike the target.
Use the applicable skill: Melee Combat or Ranged Combat for physical attack,
and Witchcraft or Thaumaturgy for magical attacks.

**Damage Rolls**:
Having successfully struck an opponent you determine how many Hit Points your opponent
looses by rolling the damage dice applicable for your weapon and adding your Damage Bonus.
If you are making a melee attack, the Damage Bonus is STR÷10.
If you are making a ranged attack, the Damage Bonus is PER÷10.
Magical attacks do not have a Damage Bonus.

See the [equipment list]({{ '/rulebook/equipment/' | prepend: site.baseurl }})
to find out how much damage your weapon deals.

**Unconsciousness**:
You loose consciousness if you are reduced to 0 Hit Points or lower.

**Death**:
You die if you are reduced to negative 30 HP.

**Natural healing**:
Complete rest, such as sitting or lying down, for 1 hour will replenish 10 HP.

Actions
--------
During each round you can take an »action« such as move, attack, use a power, etc.
This is called your Main Actions.

**Surge Actions**:
When you have taken your main action you can choose to take one or two Surge Actions.
Surge Actions are just like Main Actions except that they are strenuous.
Taking a surge action drains 1d4 of your HP.
If you are wearing heavy armor, the strain of taking surge actions may be even higher.

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


Powers
------
Powers are special abilities you can use during the game.
Using powers will drain a number of HP, depending on how
strenuous the power is. There are certain skills that
do nothing except allow you to use powers. These skills
are called Power Skills.
For instance, the Thaumaturgy is a Power Skill; having
a given score in the that skill would grant you the ability
to cast certain Thaumaturgy spells.
Exactly which spells you can cast to depends on the »tier«
of the spell. A tier 1 Thaumaturgy spell requires you to
have a Thaumaturgy score of 15. A Tier 2 spell would require
a skill score of 30, and so on.

The sum of the scores of your Power Skills may never exceed 90.
In other words, having Witchcraft 60 and Thaumaturgy 30 would
be OK because their combined score is exactly 90,
but you would never be able to further increase the scores
of these skills.

**Using powers**:
When you use a power you must first make a Standard Test
for the given Power Skill. If the test succeeds, the power
takes effect and you suffer strain.

**Strain**:
Using powers causes strain damage.
The number of HP drained depends on how strenuous the power is.
The strain occurs *after* the power has taken effect.
This means that you can successfully use a power and
then fall unconscious by the strain it caused.
Conversely, if you fail to use the power, you do not suffer any
strain damage.

**Healing**:
You do not regenerate and cannot be healed *in any way* for an hour after using a power.

**Tiers**:
Powers are divided into tiers from 1 to 6. Tier one powers are the easiest
to use and they drain only a 2 HPs per use.
Tier six powers are very difficult to use and drain 12 HPs per use.
Powers have a Skill Score requirements that must be met in order for
the character to be able to use them.

**Duration**:
Unless specified, all non-instantaneous and non-permanent powers
fade away at the *end* of your *next* turn. If you want to keep the power from fading away,
you must take an action next round to Concentrate on that power, which will keep it going for
another round. Outside combat, you can maintain a single power and still do simple tasks such
as walking, talking, etc. People who know you might notice that you are distracted though.

**Range**:
Unless otherwise specified, powers can reach any target within
the caster's line of sight.

### List of powers

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
