# ScoreMaster Mobile App

This contains outline specifications for a mobile app to be used in connection with the ScoreMaster rally administration software.

## Audience
Initially, this is aimed at the developers of ScoreMaster and the mobile app. At some point it might also include Rallymasters.

## Background
ScoreMaster is, as at January 2023, the adopted standard rally administration system used by rally teams throughout UK and continental Europe. Rally entrants currently make use of any email app to submit bonus claims in a standard format. The mobile app (MA) is being developed in order to replace the use of standard email apps in order to bring enhanced experiences to both rally entrants and rally teams.

## Entrant enhancements
Using the MA should
- ensure that all bonus claims are correctly coded and formed
- reduce keystrokes required to make bonus claims


## Rally team enhancements
Using the MA should
- ensure that all bonus claims are correctly coded and formed
- implement offline review of claim history at rally end interviews

## ScoreMaster datapacket to MA
For each rally, or rally leg, ScoreMaster will create a datapacket for use with the MA. The packet will be in JSON format containing a single rally specification record and multiple bonus records.

### Rally specification record
Fieldname  | Datatype | Description
---        | ---      | ---
RallyTitle | string   | The name of the rally, eg "BBR23"
Starttime  | datetime | The official rally start time (see Datetime below)
Finishtime | datetime | The official rally finish time
MaxHours   | integer  | The maximum hours available before DNF
Timezone   | ±integer | Rally timezone, signed hours offset from UTC
NumLegs    | integer  | The number of legs comprising this rally
CurrentLeg | integer  | The number of the currently active leg
Email      | string   | The destination address for bonus claims
ClaimHost  | ipspec   | The *protocol*, *domain or ip address*, *port* used in place of email

### Bonus record
Fieldname  | Datatype | Description
---        | ---      | ---
BonusID    | string   | Unique code for this record. RE = [A-Z0-9]+-?
BriefDesc  | string   | Title of this bonus
Flags      | string   | Possible empty collection of flags as:- <ul><li>A - Alert, read the notes</li><li>B - Bike in photo</li><li>D - Daylight only</li><li>F - Face in photo</li><li>N - nighttime only</li><li>R - restricted access</li><li>T - receipt needed</li></ul>
Notes      | string   | Scoring notes. Important to scoring. eg: Photo the red side, not the blue side
Waffle     | string   | Info not critical to scoring, maybe parking guidance, historical notes, etc
Points     | integer  | Number of points value of the bonus. Variable values use 0
Question   | string   | Needed for basic or extra points
Coords     | string   | Geographical location of bonus

### Datetime
Timestamps will be presented in ISO8601/RFC3339 format as follows:-

*yyyy-mm-dd*T*hh:mm:ss*Z or *yyyy-mm-dd*T*hh:mm:ss*±*hh*:00