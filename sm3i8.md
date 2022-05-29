# Internationalisation

ScoreMaster has been developed and written in English, originally for the purpose of administering rallies in England. It has been increasingly used outside of England so adapting for an international audience is now important.

For this purpose we need to consider three audiences: the configurer, the user and rally entrants.

The configurer is the individual who configures ScoreMaster for a particular rally. The user (or users) is the individual operating the scoring system during the rally. The rally entrants need only be concerned with certain documents produced by the system including certificates, score explanations and claim schedules.

Options for configurers are: read English and/or customise the two literals files (below).

The users will need to cope with whatever system the configurer has supplied.

Rally entrants should be treated as "innocent victims" of the system so for them all documents need to be understandable without further translation.

## Translateable literals
All wording used in the software is contained in one of two files: *customvars.php* and *custom.js* and these are easily translated. Be aware that these contain actual program code. Use only a plain text editor (notepad, notepad++, nano, etc) and be careful to maintain the correct syntax for anything you change.

The sole drawback of this approach is that the translated files might get out of sync with the updated originals.

## Certificates
Everything in the certificates given to entrants is fully customiseable, including translation, using the WYSIWYG editor built into ScoreMaster.

## Score explanations
These documents include three sets of literals apart from the bonus details:-


### Fixed (not translateable) literals
Without updating the two literals files, these words are not easily translateable but are well-known terms and, we hope, won't really need to be translated.

DNF, DNS, finisher, hrs, kilometres, km/h, miles, mins, mph, points, total.


### DNF reasons

It is expected that possible causes of DNF would be spelled out in the rally book so these "explanations" don't need to be fully explicit.

| Condition         | Format                               | Notes/examples
| ---               | ---                                  | ---
| TOO FEW POINTS    | points < *n*                         | DNF: points < 1000
| TOO FEW MILES     | miles < *n* \| kilometres < *n*>     | DNF: miles < 350
| TOO MANY MILES    | miles > *n* \| kilometres > *n*>     | DNF: kilometres > 2000
| FINISHED TOO LATE | *time* > *time*                      | Check-in time vs DNF time 
| MISSED COMPULSORY | &#8265; *bonus description* [*code*] | DNF: &#8265; Grenoble [27]
| HIT MUST NOT      | &#8264; *bonus description* [*code*] | DNF: &#8264; Lost flag [LF]
| CATEGORY RULE     | *axis*: n[*cat*] &lt; \| &#8805; *n* | DNF: Country: n < 5 <br> DNF: County[Yorkshire] n < 3
| SPEEDING          | *speed* > *n*                        | DNF: 73 km/h > 70 

### Claim rejection

If a bonus claim is rejected it is shown with an 'X' in place of a score and with a second line explaining the rejection.

!! - *reason*

The possible reasons are held in the Rally Parameters and are fully translateable.

## Schedule of claims
A brief document entitled "Schedule of claims received" is shown to entrants at the end of an EBC rally, listing the bonus claims received by the rally team for that entrant. Apart from the title there are two further literals: "Number of claims received" and "Number of bonuses claimed". The document has value during a short period of time at the end of a rally and forms part of a conversation between entrant and rally team. Once accepted, it is immediately replaced with a score explanation as above.

The three literals can be overridden by adding name/value pairs in [Rally parameters][Settings]. Note that the settings collection is in [JSON standard format](https://www.json.org) and care must be taken to maintain its validity. The new pairs are:-

"clgHeader": "Schedule of claims received", "clgClaimsCount": "Number of claims received", "clgBonusCount": "Number of bonuses claimed"

