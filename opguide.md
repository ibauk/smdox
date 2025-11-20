# ScoreMaster Operations Guide

This guide tells rally team members everything they need to know when running a rally scored using ScoreMaster. The only prerequisites are an understanding of how IBA rallies work and familiarity with the contents of the rally book.

---
## STARTING THE RALLY

### Confirming status

The first order of business is to ensure that the scoring system has been configured correctly, that all entrant details have been entered correctly and that all rally team members understand how to do stuff.

The configuration should have been thoroughly checked well before the start of the rally but check again:

- Email configuration
- Certificate contents
- Entrants all showing DNS
- Teams setup
- Test data all cleared out

If necessary, choose option 1 of "Reset the database" under "Here be dragons" to clear out any test data.

### Check-out

## DURING THE RALLY

### Processing new claims EBC

New claims appear automatically in the queue to be processed. Selecting a claim for inspection displays a screen showing two photos side-by-side, details of the claim and buttons to record your decision. The photos compare the one submitted with the claim with the one shown in the rally book.

Possible decisions are:- ACCEPT, REJECT with reason, EXCLUDE. [See "Judging decisions" below](#judging-decisions)

It is possible to correct the odo reading and/or the claim time if necessary and you can also record relevant notes about the claim.


### Processing new claims non-EBC

The "Judge incoming claims" button displays a form asking for entrant number, bonus code and decision. There is also a space to record notes about the claim.

Possible decisions are:- ACCEPT, REJECT with reason, EXCLUDE. [See "Judging decisions" below](#judging-decisions)


### Revisiting processed claims

If a claim needs to be revisited, the associated scorecard will be recalculated automatically.

### Updating bonus properties

Have any claims been processed for this bonus yet? If no then just modify whatever you want and don't worry about it.

If claims have been processed and you will change the points value of the bonus, you must choose between changing the value for new claims only or updating existing claims also. This choice will be offered by the system if you change a bonus with existing claims.  This only affects bonuses with a fixed value; variable points bonuses are unaffected.

If existing claims are updated, you should also run the procedure "Recalculate scorecards" button under "Here be dragons".

### Updating rules

If one of the complex rules must be updated during the rally it will be necessary to recalculate all scorecards. This can be achieved using the "Recalculate scorecards" button under "Here be dragons".

##  FINISHING THE RALLY

### Check-in

Check-in marks the end of the rally for riders. Before collecting odo readings, each rider should be asked to check that all emails are sent correctly so that taking the odo reading marks the exact end of the rally and the rider can relax. The later interview to confirm the score will normally be uneventful but, if emailed claims are missing, the rider's phone should be checked and any claims "sent" but not transmitted or received by us should be accepted at that point.

### Confirming status

When all entrants have been interviewed and have agreed their scorecards, before printing certificates or announcing results, conduct a review:

- Do "Current rankings" look sensible?
- Any outstanding emails?


### Printing certificates

### Exporting results

Options are available to export Finishers only. Two formats are supported: CSV suitable for input to a spreadsheet and JSON suitable for uploading to the IBAUK database.

# Judging decisions

<p>You are asked to assess the bonus claim by comparing it against the specific requirements. Is it a good photo? Is the face in the photo? etc</p>
<p>Specific bonus requirements are shown including icons indicating "Alert", "Bike in photo", "Daylight only", "Face in photo", "Night only", "Restricted hours/access" and "Receipt/ticket required"</p>
<p><strong>Accept good claim</strong> awards the points and other benefits of the claim</p>
<p><strong>Leave undecided</strong> does not judge the claim but returns it to the end of the queue</p>
<p>Other responses apart from "Exclude claim" <strong>reject the claim</strong> for the stated reason. The claim and reason for rejection will appear on the scorecard. This is the normal method of rejecting claims and should be used in preference to excluding the claim.</p>
<p><strong>Exclude claim</strong> excludes the claim from scoring altogether. It should only rarely be used as nothing will appear on the scorecard. It is intended for use with claims which are not judgeable as opposed to those which can be accepted or rejected.</p>
<p>Clicking the info line after '@' will make odo reading and claim time editable</p>
