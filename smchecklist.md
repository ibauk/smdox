# ScoreMaster rally readiness checklist

## Entrants
### [Rally setup & config] [Entrants] [Full Entrant records]
Check that ALL the entrant records are loaded and that the email field contains the email address(es) they will use for claim submission.


## Certificates
### [Rally setup & config] [Edit certificate content]
Check that the certificate has the correct images and Rallymaster name.

## EBC
### [Rally setup & config] [Rally parameters] [Show advanced] [EBC]

#### dontrun
 
The *dontrun* flag must be set true. If emails are being received but not appearing in ScoreMaster, check this setting.

#### matchemail

The *matchemail* flag must be set true. If set to false, rider numbers won't be compared to email addresses so cross-claiming can occur.

#### heic2jpg

The *heic2jpg* setting specifies the shell command used to convert HEIC format images into JPG format. This is an important setting and may well vary from host to host.
Do not guess the value, it must be the exact, case-sensitive, shell command, perhaps with a full path specification.

#### testmode

The *testmode* flag must be set false otherwise the system is in test mode and scoring will not be possible.

## Settings
### [Rally setup & config] [Rally parameters] [Show advanced] [Settings]

#### Bonus questions
If the rally includes even one bonus question/answer, the flag *useBonusQuestions* must be set to "true" and *valBonusQuestions* has the number of points to be awarded.

#### Percentage penalty
If percentage penalties are to be used then the flag *usePercentPenalty* must be set to "true" and *valPercentPenalty* has the percentage to be applied.

#### autoFinisher
If a definite check-in process is used, this flag must be set to "false".

---
ScoreMaster v3.3.5 | Revised 2025-04-30

