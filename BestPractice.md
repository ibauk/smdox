# IBA Rally Administration - Best Practice

## Overview

IBA rallies should be fun for everyone involved, riders and rally team alike. That thought should guide the rally team in all aspects of running the rally. In general, riders should be given the benefit of the doubt when judging bonus claims and failures of technology should be overcome and remedied in favour of competitors.

Some IBA rallies are intended to be tough challenges for experienced competitors and in those judging decisions should be more strictly determined and excuses should be frequently accepted.

This guide is aimed at rally teams in the hope of reducing the length of the learning curve for new team members.

## Rally team roles

Let's start with who's who and what does everyone do:

### Rally designer
- Designs the rally including bonus selection and scoring strategies.
- Produces the rally book.

### Rally master
- Organiser of the rally, in charge of its execution.

### Rally master/Rally designer
- Might be either one or two individuals.
- Disclose/explain the rally theme and scoring calculations in start of rally presentation.
- Set policies for rally team processes.
- Final interviews with entrants after scoring.
- Certificate presentations after rally.

### Administrator
- Maintain overall administration of the rally including scoring, data collection and certificate production.

### Scoring judges
- Decide individual bonus claims as presented in ScoreMaster.

### Chief judge
- Ultimate arbiter of bonus claims. This would usually be the rally master unless he's also the rally designer. (The rally designer is the only person who knows what he meant. Everyone else must rely on what's written in the rally book.)


## Auditing / testing / training

Everyone wants the rally to run smoothly but that won't happen all by itself. Everyone makes mistakes, technology fails. Assuming that things are going or will go well will not guarantee that outcome so, at every stage, train the staff, test that things are the way they should be and keep track of who's done what.

### Before the rally

At least four weeks before the rally begins, key rally team members should familiarise themselves with the operation of ScoreMaster

At least three weeks before the rally begins, ScoreMaster is set to test mode so that riders can practise submitting bonus claims. Verify that it is working

At least one week before the rally begins, at least two independent reviews should be conducted to:-

- Compare the rally book contents with the standard rally rules
- Compare the rally book bonus descriptions with those held in the ScoreMaster database
- Compare the rally book bonus photos with those shown by ScoreMaster
- Compare the rally book bonus locations with those held in the GPX file
- Compare the rally book combo descriptions with those held in the ScoreMaster database

At least two days before the rally begins, ScoreMaster is set to live mode; *notbefore*: is set to rally start date; testing data cleared out

### During the rally

As riders arrive for sign-in, confirm the email address they will be using for bonus claiming. Check that the ScoreMaster Entrant number is the same as the flag given to the rider. Check that everyone signed-in is actually in the ScoreMaster database.

1. When all riders have left after check-out:

- Check that emails are being received into ScoreMaster
- Check that emails are being received from all riders. Is everyone's email address being recognised? Are email Subject: lines being formatted correctly?

2. Several hours before the end of the rally, 

- repeat the above checks then, compare each of the top six scorecards with emails from that rider, looking for missed emails or incorrect sequencing. Follow up with the bottom three scorecards.

- Cross-check all rejected claims. Use the filter dropdown on the Claims Log for a list of rejected claims.

- Check the arithmetic on at least two scorecards.

3. When all scorecards have been signed off, review top four scorecards and bottom two, **before printing certificates.**

## Key Procedures

These satisfy the 'training' requrements, everyone should know what they are supposed to do and not be left to guess. Don't assume that people who have done it before will do it correctly this time.

### Rally team briefing
To ensure that everyone involved properly understands their roles and has sufficient knowledge and skill to execute them reliably. To explain policies with respect to:-

- claim judging - aim to accept or aim to reject?
- claim rectification - prompt rider, quietly fix or reject claim?
- contact with entrants - don't discuss other people's claims or scores; don't negotiate judging decisions; don't make frivolous calls to riders.

### Rider briefing
To ensure that everyone (including rally team) understands the design of the rally, understands Electronic Bonus Claiming (EBC) including judging standards.

### Novice briefing
To ensure that novices understand what a rally is, what is expected of them, what is not expected of them.


### Check-out procedure, in the carpark
One or more rally team members will record odo readings at start. In some cases, they might also get riders to submit a bonus claim for odo start, confirming that everything works from the outset.

### Check-in procedure, in the carpark
1. Riders are invited to check their records and submit outstanding or corrected claims.
2. Rally team members record final odo readings marking the end of the rider's rally.

### Final interview
Each rider is given a copy of his scorecard and asked to agree its accuracy. This is NOT an opportunity to challenge judging decisions but where claims, including retransmits, are missing from the scorecard but are clearly present on the rider's phone, they should be awarded and the scorecard reprinted for signed agreement.

### Claim judging

The rally master sets the overall policies with respect to claim judging, in particular whether the aim is to seek reasons to reject rather than reasons to accept. 

Individual decisions can choose between "Accept", "Reject" (several variants) or "Exclude". Exclude and Reject are not interchangeable, they are not the same thing. 

Exclude means "excluded from the scoring process" whereas Reject is a scoring decision resulting in no points. As an example, let's consider a case where a rider claims bonus XY twice. The first claim is accepted but the second claim is defective in some way. If the second claim is rejected, it supersedes the first claim and the rider will not score the points. If the second claim is excluded, the first claim is left untouched and the rider scores the points. The choice between Reject and Exclude is not arbitrary. Claims are excluded if they are not scorable because, for example, they refer to a non-existent bonus or are submitted out of time or beyond the number of acceptable claims set for the rally. Excluded claims will or will not appear on scorecards, depending on the rally's settings.


## Electronic Bonus Claiming, EBC

The rally is scored using computer software, ScoreMaster, which receives emails from riders and presents the emailed bonus claims to the rally team for claim judging. The system depends on the riders formatting their emails in a particular way. This is aimed at helping rally team members understand what to do if/when something goes wrong.

The format of the emails is always the same: a Subject: line containing - *RiderNumber* *BonusCode* *Odo* *ClaimTime* - with a single photo attached. The four fields are separated by one or more spaces, no punctuation. The system allows some leeway, multiple photos for example but generally only considers emails which match the pattern.

### Identifying the rider

The rider number from the email is used to fetch a record from the ScoreMaster database. That record will contain one or more email addresses and the sender's address must match one of those addresses otherwise the email will not be accepted in the scoring system. For team members, the system will match the sender's address with any address registered to any team member.

### Bonus code

The bonus code identifies a particular bonus record in the ScoreMaster database. Lettercase is ignored and the claim will be processed even if the bonus code does not match a bonus record.

### Odometers

Odometers are used to record distances ridden in the rally. Such distances are part of the results reported at the end. Apart from the first and final readings, the numbers reported serve a secondary or alternative purpose of helping to ensure that claims are processed and presented in the proper sequence and assisting the rally team in identifying discrepancies in the scoring records.

### Claim time

The significance of actual claim time values varies from rally to rally and bonus to bonus but their relative values are used to control the sequence of claim processing. These values are also useful when identifying discrepancies in the scoring records.

### Monitoring rally mailbox

It is necessary to monitor the rally mailbox during the rally to check for missed claims not present in ScoreMaster. Claims can be missed for three reasons: incorrectly formed Subject: line; incorrect ScoreMaster settings; accidental mailbox interference.

The last needs some explanation. ScoreMaster regularly examines the contents of the mailbox looking for emails which have the status "unread" and "unflagged". It is fairly easy for emails to be marked as "read" in response to the actions of someone monitoring the mailbox and care must be taken to avoid doing so. "Flagged" status usually shows as an asterisk in the email list. It's used by ScoreMaster to mark emails it has positively decided not to process but can also be set by a monitor clicking the asterisk.

### Reprocessing emails

The rally team can cause emails to be reprocessed by manipulating the contents of the rally mailbox. How to manipulate depends on the circumstances:-

#### 1. A valid email has been omitted (not processed) for some reason.

Mark the email as unread. This will cause ScoreMaster to process the email.

#### 2. An email with a defective Subject: line has been left unprocessed.

 Forward the email from the rally mailbox to the rally mailbox, editing the Subject: line while doing so. This will generate a new email which will then be processed in place of the defective one.

 #### 3. An email has been sent from an unregistered address.

As a one-off fix, apply (2) above. The permanent solution is [Rally setup & config] [Entrants] [Full entrant records] then add the email address into the comma-separated list [Entrant email]. Apply (1) above.
