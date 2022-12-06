# Empowering Rallymasters - scoring methods & penalties

ScoreMaster provides automatic processing for the scoring methods and penalties described below. If you wish to make use of a scoring mechanism not included here, please speak to Bob. This is not meant to be a complete specification of the methods described. If you need the full nerdy details, speak to Bob.

This document is not concerned with *bonus claim* methods, only with the arithmetic involved in calculating a score.

This document is also not concerned with policy matters (somebody else can worry about that), it merely details what's practicable using the facilities provided.

## Some definitions
**Points**
: A points value is an integer (whole number), fractions are not allowed. In general a points value can be positive or negative.

**Bonus code**
: A unique identifier comprising letters and digits only. Spaces and punctuation are forbidden. All letters must be uppercase. 

As far as the system is concerned, bonus codes are alphanumeric even when they are all numeric. In order to keep them presented in the "correct" sequence they should all contain the same number of digits. Use leading '0's to pad the codes or start from, say, 11 or 111 instead of 1.

It is not necessary (or perhaps even desirable) that bonuses should be coded with some sequence and you certainly don't need to include any kind of serial number. Each bonus is unique as far as the system is concerned and each code stands alone. The only sequence that matters is the way they're presented on scorecards and in maintenance lists. Use your imagination: codes should be short (entrants will need to type them) but can be anything (uppercase) that you choose.

**Combo code**
: A unique identifier as with an ordinary bonus code. Letters may be upper or lowercase but AA23 is the same as aa23, Aa23 and aA23.

---

## Simple bonus points
Each bonus scores a specific number of points.

## Variable bonus points
Each bonus specifies a default value (which might be zero or even negative). At claim time the actual value of the bonus must be entered manually. This might be used for example when a bonus includes a clock face or a varying number of flags. This facility should be used sparingly as it has a significant impact on scoring efficiency.

## Simple combination bonus
A combination bonus (combo) specifies a list of underlying bonuses (which might include some* other combos). Each combo scores a specific, fixed, number of points. This is in addition to the scores of the underlying bonuses. Combos are claimed automatically, entrants don't need to claim them separately.

*Any combos included as underlying bonuses must be coded alphanumerically lower than the current combo code. Combo "A12" cannot depend on combo "A13" or "B1".

## Variable combination bonus
A variable combo specifies a minimum number of underlying bonuses (rather than 'all' for a simple combo). Each combo scores a specific number of points depending on the number of underlying bonuses scored between the minimum and all. A simple example:-

Combo *CLUBS* has underlying bonuses *MANU*,*CHELSEA*,*ARSENAL*,*RANGERS*,*ROVERS*. The combo will be scored if at least three underlying bonuses are scored. The value of the combo is 100, 200 or 600 points. 


## Questions & answers
Ordinary bonuses may have associated questions which allow for the award of additional points when correctly answered. The question/answer will be worth a fixed number of points, the value being set for the rally as a whole rather than for individual bonuses. The extra points are only awarded if the underlying bonus claim succeeds.

---

## Complex methods
Complex methods involve from one to nine sets of categories which are specified for each bonus or combo. Common sets are *Country*, *County*, *Industry*, *Building type*, etc.  For example, an ordinary bonus *F01* might specify *Country*=France, *Industry*=Cycling, *Building*=Shed.

In general, the idea is to generate a score using groups of bonuses rather than individual bonuses. Typically, the first relevant bonus is unaffected by the complex method but two or more will be.

Complex methods can be applied at three levels:- those which affect the individual bonus scores; those which reward sequences of bonuses collected; those which reward or punish collections of bonuses. Methods at each level can be combined both with the basic bonus scores and other levels.

### Individual bonus scores
Basic bonus scores can be modified by either the number of bonuses scored within a category (*Country* = *France* for example) or the number of categories having at least one bonus scored within a set (number of counties visited within a country).

The classic example of this method is the 2017 Brit Butt Rally in which the value of any bonus depended on the number of bonuses scored within a county. The first bonus was worth one point, the second two points, the third four points, the fourth eight points and so on.

Relatively complex arithmetic can be used in this method. Speak to Bob if you want to know more.

### Sequences
**Uninterrupted** claiming of a particular category can be used to award extra points. For example, three consecutive farms results in doubling the points awarded for the farm bonuses. The extra points can be either a multiple of the sum of the points scored by the relevant bonuses or a fixed number of extra points. The "uninterrupted" refers to the order of bonus claiming, not the proximity of bonuses within a group. eg. An entrant claims M3, M1, F1, M2: this gives an uninterrupted sequence (US) of two 'M's, not three. Claiming M5, M1, M3, F2 gives a US of three Ms.

### Collection of bonuses
This can be used to award extra points based on the number of bonuses scored within a category or the number of categories scored within a set. The criterion at this stage is simple group membership, order of scoring, etc are not relevant.

This method may also be used to force DNF in the event of too many/not enough categories being scored.

Speak to Bob if you want to know more.

---

## Penalties
Several penalty conditions can be easily penalised by the system. Additionally, arbitrary penalties can be imposed by making use of an extra bonus code. eg. 'ODDSOCKS' = -100 points, 'POLITEVEST' = -100000 points.

### Compulsory bonuses
Any ordinary or combination bonus can be flagged as being compulsory. Failure to score a compulsory bonus results in DNF.

### Minimum points
It is possible to specify a minimum number of points below which entrants would be DNF.

### Percentage points deduction
This is typically used to punish sloppy bonus claims, 10% being the usual figure. The percentage used is defined for the rally as a whole rather than for individual or classes of bonus. It always requires the rally team to tick the box manually. Only one such provision can be defined.

### Distance penalties
Distance travelled can be used to penalise entrants. Two hard limits, not far enough and too far, can be used as DNF triggers. It is also possible to apply a points penalty for travelling too far as either a fixed number of points (> 250 miles = -500 points) or a number of points per mile. 

Each rally has an official unit of distance, either miles or kilometres. Individual odometers will read either miles or kilometres and be converted by the system, if necessary, to the rally unit.  "Points per mile" will actually be points per kilometre in kilometre rallies.

### Time penalties
Each rally runs from the official start time to the official finish time. To allow for staggered starts, that timespan can be longer than the permitted number of hours. (eg. 8 hour rally runs from 0800 to 1800). An entrant finishing after his 8 hours or later than the official finish time is DNF.

Within the rally time window it's possible to impose points penalties, perhaps to encourage early check-in, either as a fixed number of points or as points per minute. Several such windows can be specified with different points values, they need not be confined to the end of the rally.

### Speed penalties
It is possible to impose a fixed points penalty, or DNF, in response to excessive speed. Golly, that's bold eh! Now, before you get all excited:-

- we are not the Police. It's not our job to enforce the law.
- we are not the Police. We don't have wide-ranging legal powers.
- we are not the Police. We don't have massive funding and high-tech infrastructure.

The speed monitored by us is calculated as CorrectedDistance / (Check-in - Check-out - Rest). Distance is calculated using odometer readings, corrected if an odo check ride was performed. Example: Rally starts 0900. Roger records 1 hour rest bonus and checks-in at 1644 having travelled 323 miles. Rally time 7h 44, less rest = 6h 44. (323 / 6h 44) = 47.9mph.

Did that involve any actual speeding? Who knows? Maybe it did, maybe it didn't, that's just not relevant.

## Summary
ScoreMaster has been developed continuously since 2012 and will continue to be developed for many years to come. Its purpose is to ensure that rallies are run smoothly, hopefully without last minute upheavals, and its philosophy is that Rallymasters should be empowered and not restricted by it.

The next major release will include the ability to report, and rank finishers on, points per mile (kilometre) rather than absolute points.

Don't let your imagination be held back because "*it can't do X*". If you dream up a scoring mechanism you'd like to use that's not listed here, speak to Bob.

Version: 2022-07-17 ScoreMaster v3.2
