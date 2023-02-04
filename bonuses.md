# ScoreMaster Bonus and Combo details
This is the reference for data needed by bonus and combo records in the ScoreMaster database.

## Bonus record
Fieldname  | Datatype | Description
---        | ---      | ---
BonusID    | string   | Unique code for this record. Uppercase letters and digits only with optional trailing '-'. (RE = [A-Z0-9]+-?)
BriefDesc  | string   | Title or description of this bonus. Must not be blank. Appears on scorecards, may contain simple HTML.
Compulsory | integer  | 0 = optional bonus. 1 = compulsory bonus. Failure to score compulsory bonus is DNF.
Leg        | integer  | Available in which leg or legs. 0 = all legs otherwise leg number only.
Flags      | string   | Possibly empty collection of flags as:- <ul><li>A - Alert, read the notes</li><li>B - Bike in photo</li><li>D - Daylight only</li><li>F - Face in photo</li><li>N - nighttime only</li><li>R - restricted access</li><li>T - receipt needed</li></ul>
Notes      | string   | Scoring notes. **Important to scoring**. eg: "*Photo the red side, not the blue side*". Shown to rally staff during scoring.
Waffle     | string   | Info not critical to scoring, maybe parking guidance, historical notes, etc. Used in rally book generation.
Points     | integer  | Number of points value of the bonus. Variable values use 0.
Cat1..Cat9 | integer  | 1 to 9 category values. Refer to the documentation for compound scoring.
RestMinutes| integer  | Number of minutes of rest scored by this bonus.
Question   | string   | Needed in some rallies for basic or extra points.
Answer     | string   | Needed in some rallies for basic or extra points.
Coords     | string   | Geographical location of bonus. This can be blank or use any format. This field is not used in ScoreMaster but is maintained for use with other utilities which generate rally books or GPX files.

## Combo record
Fieldname  | Datatype | Description
---        | ---      | ---
BonusID    | string   | Unique code for this record. Uppercase/lowercase letters and digits only. (RE = [A-Za-z0-9]+)
BriefDesc  | string   | Title or description of this combo. Must not be blank. Appears on scorecards, may contain simple HTML.
Compulsory | integer  | 0 = optional combo. 1 = compulsory combo. Failure to score compulsory combo is DNF.
Leg        | integer  | Available in which leg or legs. 0 = all legs otherwise leg number only.
Bonuses    | string   | Comma-separated list of underlying BonusIDs.
MinTicks   | integer  | Minimum number of underlying bonuses to score. 0 = all must be scored.
ScorePoints| string   | Single integer or comma-separated list of integers for values from MinTicks upwards
Cat1..Cat9 | integer  | 1 to 9 category values. Refer to the documentation for compound scoring.


