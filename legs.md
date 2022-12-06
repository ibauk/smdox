# Multi-leg rallies

Most rallies are single-leg affairs but multi-leg rallies are also catered for as described below. Let's begin with a discussion about rally timings.

## Rally time windows
Each rally formally begins at the *Rally Start Time* (RST) and ends at the *Rally Finish Time* (RFT). Nobody can start earlier than the RST and anyone not finished by RFT is DNF (Did Not Finish). Time periods within the overall RST-RFT can be specified as incurring penalties short of DNF. For example it's common to encourage early finishes by imposing a penalty of, say, 100 points per minute for the last hour of the rally. Multiple such periods can be specified for a single rally.

### Entrant time windows
In order to cater for staggered starts, each rally also specifies a *Maximum Rally Hours* (MRH) parameter. This is used to set time windows, still within RST-RFT, for each rally entrant. *Entrant Start Time* (EST) is the actual start time of a particular entrant and that entrant's *Entrant Finish Time* (EFT) is calculated to be min(EST+MRH,RFT). 

A 12 hour rally could be specified as RST=0600, RFT=2000, MRH=12. *Maximum Entrant Hours* (MEH) is the Maximum hours available to an individual entrant. This would allow entrants these windows:-

Entrant | ESH  | EFT  | MEH
------- | ---  | ---  | ---
Bob     | 0600 | 1800 | 12
Suzy    | 0700 | 1900 | 12
Linda   | 0800 | 2000 | 12
Donald  | 0900 | 2000 | 11
Rupert  | 1000 | 2000 | 10

### Leg time windows
Legs follow the same pattern. For a single leg rally the leg time window is the rally time window, RST-RFT. Multiple legs must fit within the overall time window but need not fill it completely.

Each leg has an associated *Leg Start Time* (LST), *Leg Finish Time* (LFT) and *Maximum Leg Hours* (MLH)

Given a rally specified as RST=MonW1, RFT=FriW2, a two leg rally could be specified to avoid the weekend for example:-

Leg |  LST  |  LFT
--- | ----- | -----
 1  | MonW1 | FriW1
 2  | MonW2 | FriW2

### Time based DNF
Logic dictates that an entrant failing to finish by the relevant RFT, EFT or LFT is DNF but, firstly, that will only happen automatically where the *autoLateDNF* flag is set for a particular rally and, secondly, failure to complete a particular leg can result in some lesser penalty.

## About legs
A leg can be thought of as a rally within a rally. Legs have their own time windows as we've seen above. It is normal to produce a score sheet for a leg but not a certificate. The score sheet for leg 1 is identical to the score sheet for a single leg rally but for subsequent legs the position is not so clear.

Leg 2 can be viewed entirely by itself or it can be viewed as a continuation of the rally. The differences between the two approaches need not be substantial.

Leg totals: TotalPointsBF, RestMinutesBF, CorrectedMilesBF