# Transition from paper scoring to EBC

The old paper system of rally scoring involves entrants keeping track of bonus claims on paper and having those details captured into the scoring system on return to rally HQ.

Electronic Bonus Claiming (EBC) involves entrants submitting individual bonus claim using email throughout the rally. Claims are updated into the scoring system during the rally and subject to a final reconciliation process only on return to rally HQ.

## Entrants are "users"

Rally entrants should be treated as "users" of the system. This means that making things easy for them is a priority. They should not be expected to have expert digital skills, they are motorcyclists, not computer experts. System **requirements** should be kept to a minimum so :-

- accept any size photo
- don't require specific photo filenames
- don't require specific photo formats
- don't require specific lettercases in bonus codes
- don't require specific punctuation, just use spaces
- accept common punctuation such as ',' between fields, ':' or '.' between hours and minutes
- don't ask for "difficult" information

As users, they also need to be given confidence that the system works as it should. This means :-

- they must be able to practise using the system in advance of a rally
- they must know that checks are built into the scoring procedures to detect and correct failures
- the rules must permit correction of technical failures such as email not transmitted

## Rally team are "experts"

The rally team is responsible for the administration of the rally including scoring. At least one of them must understand the technicalities involved in EBC both at the receiving end and at the smartphone end.

The rally book must :-

- spell out **exactly** how to submit bonus claims
- spell out what to do for common "what ifs" including when to call for advice
- provide basic guidance on photo sizes (small but not too small is better than large)
- explain the process for scorecard reconcilation on return to rally HQ

The rally team must :-

- test the scoring system before starting the rally
- check that the scoring system is cleared of testing before starting the rally
- set the scoring options ready for live scoring
- organise themselves to ensure that all eventualities are covered
- establish procedures for reviewing scorecards against claims against emails

## Email processing

### Entrant's smartphone

1. construct bonus claim
2. click [send]
3. before bonus claim time windows close, check for untransmitted emails in outbox

If an email fails to transmit (stuck in 'outbox') try until success :-

1. move to area with adequate signal
2. switch WiFi off/on
3. delete the outbox message, recreate the message and try again
4. delete the outbox message, clear the app's cache, restart the device, recreate the message and try again
5. before bonus claim time window closes, call rally team to report unable to send with specific bonus numbers


### Rally team

1. judge claims in the EBC queue
2. check for/manually process discarded claims in the email account
3. periodically review one or more scorecards against the claims log/email account
4. periodically review that all entrants are actually scoring

## Check-in procedure

On return to rally HQ each entrant should be shown/given a simple list of bonus claims received (not judged). He should check that the list is correct.

If any are missing (not created, [send] not clicked or [send] clicked but not transmitted) and still within the bonus submission timeframe, use "Entrant's smartphone" procedure above to submit now.

If any are missing ([send] clicked but not transmitted) but now out of time and were notified as above, submit them now.

Once claims list is agreed entrant can be given his scorecard. Any rejections can be discussed with rally team but see "Not Negotiable" below. The scorecard must be signed by the entrant to indicate his acceptance of the score.

## Not Negotiable

Bonus claims are not negotiable in the traditional sense. They are judged by the rally team according to the rules and specifications in the rally book. Either the claim complies and is successful or it does not comply and is rejected for non-compliance. If a review finds that a claim has been wrongly judged the scorecard can be updated and recalculated.

The traditional haggling at the scoring table involving supplying improved photos, missing receipts or "*please, it's only a small error*" are expressly disallowed.


## Frequently Asked Questions

### Confirmation of email receipt

Some people express a desire for positive confirmation that an email they've sent has been received by the rally team. 

There are some email-specific automatic ways to report back involving "delivery receipts" and "read receipts". These are not useful because they are sent automatically by various bits of mail-processing software and do not rely on any component of the rally system actually receiving the email correctly. They are an indication of delivery only, they are not authoritative.

Some people like to include another address to receive a copy of any emails sent and use the contents of that mailbox to "prove" delivery. Once again, such receipts act as an indication of delivery to the rally team only, they are not authoritative.

Some people rely on the fact that an email has been transferred to their "sent items" folder as proof that the email was sent and therefore received. Indication only, not authoritative.

The only way to provide a reliable receipt is for a member of the rally team to manually send one.  That won't be the end of the story though :-

Email is not instantaneous. We often think it is and mostly it's quite close to instantaneous but it's not reliably instantaneous. How long should an entrant wait for the acknowledgement? Once the waiting period has elapsed, what should he do? If he sends a second email and still doesn't get an acknowledgment, what else should he do?

For these reasons, during a rally no such confirmation should be sought or offered. Entrants should send emails and trust that they will be received correctly unless they have good reason to expect failure. They should check for signs of trouble at key stages but otherwise just get on with the rally.


### Photo sizes, names, format

Smartphones take excellent photos, in part because they shield the user from the technicalities of photography. Generally the process of taking a photo with a smartphone consists of pointing the camera and pressing a button. Focus, exposure, aperture and other details are optimised by the smartphone.

Not all camera apps provide easy ways to alter the size of a photo and those that do use a variety of measures: megapixels, small/medium/large, megabytes, fine, standard, etc. Specifying a particular size, or even a particular limit, to apply to all entrants involves all those entrants developing expertise with their cameras. Entrants are *users*, they shouldn't need to be experts.

Entrants should be encouraged to carry out simple experiments with emailed photos - smaller is generally better - but rally teams should be able to cater for all sizes with only one criterion : "*can I see enough detail to judge the bonus claim?*"

The same reasoning applies to which format (HEIC, JPG, etc) is recorded and what file naming convention is used.


### Why report claim time in the four fields?

In a number of circumstances, knowing the time at which a bonus is claimed is important. Each email includes a timestamp, the email headers include several timestamps and, in many cases, the attached photo will use a timestamp as its file name so why ask for another time?

The time that needs to be captured is the moment the claim is made. In theory, the email's formal "**Date:**" field records that moment but after a lot of testing we know that in practice that's not always the case. The other timestamps in the headers record progress through the mail system but not the moment we need. Even where photo file names contain timestamps, they don't necessarily record the moment we need.

The simplest and most reliable method of capturing the claim time is to include it in the four fields of the claim. In cases of doubt the other timestamps available can be used to investigate/support the accuracy of the time claimed.


### Why might emailed claims not be presented within ScoreMaster?

Correctly formatted bonus claims submitted by email will be fetched automatically by ScoreMaster and included in the list of "EBC claims for judging". Unfortunately, not all claims will be formatted correctly so some will not appear in that list and will have to be inspected in the email system instead. The rally team may or may not impose a penalty for such claims or can even refuse to process them at all, each rally will be different in that respect.

In order to be processed automatically each claim email must have exactly one photo attached and must have the four claim fields in the "**Subject:**" line of the email. Depending on the setting of the "*matchemail*" flag, the email's "from" address must match the one held on the database.

Emails failing these tests are left as "unread" in the mailbox. Emails accepted by ScoreMaster are flagged as "read". This means that anyone looking at the mailbox will easily identify claims which must be handled manually.


### Why restrict email addresses used for bonus claims?

One of the four fields submitted in a bonus claim is the entrant number, uniquely identifying the entrant, so why insist on only using his registered address?

Imagine a situation in which entrant #1 accidentally reports "11" as his number, perhaps as a result of fat finger syndrome, and submits a claim for bonus 27. Unfortunately his claim is rejected as he didn't include his bike in the photo, a requirement of bonus 27. Entrant #11 had already successfully claimed bonus 27 but that claim is now superseded by this new, failed, claim and he loses his points.

If matching email is in force, the wrongly identified claim would be left for the rally team to handle manually and the mismatched credentials could be handled more sensitively.