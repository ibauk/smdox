# ScoreMaster Mobile App

This contains outline specifications for a mobile app to be used in connection with the ScoreMaster rally administration software.

Version: 0.3 - Jun 2025

## Audience
Initially, this is aimed at the developers of ScoreMaster and the mobile app. At some point it might also include Rallymasters.

## Background
ScoreMaster is the adopted standard rally administration system used by rally teams throughout UK and continental Europe. Rally entrants currently make use of any email app to submit bonus claims in a standard format. The mobile app (MA) is being developed in order to replace the use of standard email apps in order to bring enhanced experiences to both rally entrants and rally teams.

## Entrant enhancements
Using the MA should
- ensure that all bonus claims are correctly coded and formed
- reduce keystrokes required to make bonus claims
- take care of background transmission
- keep adequate logs of claim submissions
- send images in JPG format rather than HEIC, etc

Using the MA could
- calculate daylight/nightime for each bonus using local sunrise/sunset times
- generate odo readings using GPS
- preselect current bonus using GPS

## Rally team enhancements
Using the MA should
- ensure that all bonus claims are correctly coded and formed
- implement offline review of claim history at rally end interviews

## Alternative transports
From a technical perspective, the current email transport mechanism is a one-way, fire and forget solution. Alternative mechanisms should adopt the same approach. Proof of claim submission can be established using local claim logs at rally end interviews. Entrants should not be encouraged to rely on instant proof of submission or reception of claims.

Transports such as FTP and REST must cater for temporary unavailability of servers as well as signal. They might also not be suitable for certain rallies where a known public-facing IP or domain is unavailable. For example, running ScoreMaster on a standard hotel guest network is practicable using email for claims processing but, without the use of a public server, accepting FTP or REST claims would not.

## ScoreMaster datapacket to MA
For each rally, or rally leg, ScoreMaster will create a datapacket for use with the MA. The packet will be in JSON format containing a single rally specification record and multiple bonus records.

How it would be transferred to each MA has yet to be decided.

### Rally specification record
Fieldname  | Datatype | Description
---        | ---      | ---
RallyTitle | string   | The name of the rally, eg "BBR23"
Starttime  | datetime | The official rally start time (see Datetime below)
Finishtime | datetime | The official rally finish time
MaxHours   | integer  | The maximum hours available before DNF
Timezone   | string   | Rally timezone, signed hours offset from UTC
NumLegs    | integer  | The number of legs comprising this rally
CurrentLeg | integer  | The number of the currently active leg
Email      | string   | The destination address for bonus claims
ClaimHost  | ipspec   | The *protocol*, *domain or ip address*, *port* used in place of email (or blank)
Resubmits  | integer  | <ul><li>0 - bonus reclaims unlimited</li><li>1 - bonus reclaims ok until next bonus claimed</li></ul>

### Bonus record
Fieldname  | Datatype | Description
---        | ---      | ---
BonusID    | string   | Unique code for this record. RE = [A-Z0-9]+-?
BriefDesc  | string   | Title of this bonus
Flags      | string   | Possibly empty collection of flags as:- <ul><li>A - Alert, read the notes</li><li>B - Bike in photo</li><li>D - Daylight only</li><li>F - Face in photo</li><li>N - nighttime only</li><li>R - restricted access</li><li>T - receipt needed</li></ul>
Notes      | string   | Scoring notes. Important to scoring. eg: Photo the red side, not the blue side
Waffle     | string   | Info not critical to scoring, maybe parking guidance, historical notes, etc
Points     | integer  | Number of points value of the bonus. Variable values use 0
Question   | string   | Needed for basic or extra points
Coords     | string   | Geographical location of bonus


### Datetime
Timestamps will be presented in ISO8601/RFC3339 format as follows:-

*yyyy-mm-dd*T*hh:mm:ss*Z or *yyyy-mm-dd*T*hh:mm:ss*±*hh*:00

### Sample JSON datapacket
{
    "Rally": {
        "RallyTitle": "Invictus23",
        "Starttime": "2023-05-13T09:00:00+01:00",
        "Finishtime": "2023-05-13T17:00:00+01.00",
        "MaxHours": 8,
        "Timezone": "+01",
        "NumLegs": 1,
        "CurrentLeg": 1,
        "Email": "ibaukebc@gmail.com",
        "ClaimHost": "ftp://77.68.55.111:5454",
        "Resubmits": 1
    },
    "bonuses": [
        {
            "BonusID": "A1",
            "BriefDesc": "Woldson castle",
            "Flags": "",
            "Notes": "Must include drawbridge",
            "Waffle": "Park round the back",
            "Points": 600,
            "Question": "",
            "Coords": ""
        },
        {
            "BonusID": "A2",
            "BriefDesc": "Maidstone station",
            "Flags": "FBD",
            "Notes": "",
            "Waffle": "First railway station in Kent (1899)",
            "Points": 1200,
            "Question": "",
            "Coords": ""
        }
    ]
}

## Mobile device customization
On each mobile device, customization will come from the datapacket exported from ScoreMaster and from input by the user. Manual input will include *EntrantID*, *EmailAddress*, *RiderName*. These fields are used to validate claim submissions regardless of the transport mechanism in use.
