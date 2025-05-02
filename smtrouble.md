# Rally troubleshooting


When things go wrong during a rally, fixing the scores is the priority, not fixing the software. Making sure that the rally has been configured correctly in ScoreMaster before the start of the rally is obviously better than fixing it halfway through but stuff happens.

## Rebuild scorecards
The utility "Rebuild scorecards" is a valuable weapon in your toolkit and can be used to fix multiple error conditions. The procedure offers two options:

1. Fully rebuild scorecards | Reapply decided claims only | Process unapplied claims only.
2. Entrant numbers.

Option 1 should always use "Fully rebuild scorecards", the other options are deprecated.

Option 2 can be used to rebuild all or some of the entrants' scorecards.

CAUTION: This procedure has the ability to overwrite final odo readings in the circumstance that one or more hugely wrong odo readings exist in claim records. Check and correct those before using this procedure.

## Bonus points value wrong
If the points value of a bonus is found to be incorrect, it can be corrected in one of two ways:

1. Change the points value using the field shown in the bonus list.
2. Change the points value using the field shown in the "Details" page for the affected bonus.

In either case, claims for the affected bonus will use the new value from the point of change onwards. If method 1 is used, existing claims will be unaffected and will continue to show the old value.

If method 2 is used, and the fixed/variable flag shows fixed, existing claims will be updated to use the new points value. Scorecards must be rebuilt to reflect the changes, use the utility "Rebuild scorecards" to update individual or all scorecards.


## Odo reading way out of line
Odo readings during the rally are taken from the information supplied with the bonus claims and where incorrect readings are supplied sometimes that can have a noticeable effect on mileage shown in rankings and on the associated certificate.

The erroneous reading can be corrected by editing the claim via the claim log. In most cases that will be enough to correct the problem. In a few cases it will also be necessary to edit the entrant record itself and manually set the "Odo @ rally finish" setting.


## Photos missing from bonus claims
In most cases, photos supplied as part of a bonus claim will appear automatically in ScoreMaster. Where they don't appear it can be for one of three reasons:

1. No photo was supplied with the claim.
2. The technical format of the email prevents auto-extraction.
3. The photo can't be converted to a standard image format.

It is quite normal for entrants to forget to attach a photo to the claim and where that's the case no action by the rally team is needed. It is always worth checking the email itself to ensure that it's not merely that ScoreMaster can't access the photo. Photos found in the email should be treated as though they appeared in ScoreMaster and the claim should be judged accordingly.

Where one particular entrant is affected by missing claims, reasons 2 and/or 3 is the likely explanation and the emails should be preserved for investigation after the rally.

## Claims missing from ScoreMaster
Bonus claims are emailed by entrants and ScoreMaster periodically polls the mailbox looking for new claims. If none are found, it might be that one of the settings in the EBC section of Rally Parameters is not set correctly. Inspect that section and correct the settings. Claim extraction should continue straight away.

Only unread emails are considered by the software. Where a small number of claims is missing, the mailbox should be inspected for emails marked as having been read. If a missing claim is identified, change its status to unread and it'll be processed in the normal way.

Only emails with a correctly formatted Subject line are considered by the software. The line might actually be the first line of the body rather than the Subject field itself but that's ok. It is possible for the rally team to correct the Subject line in the mailbox in rallies where such assistance is permissible. Forward the defective email to the scoring mailbox and use the "Edit Subject" function before clicking Send.

## Combo wrongly configured
Fix the configuration. Run the utility "Rebuild scorecards".
