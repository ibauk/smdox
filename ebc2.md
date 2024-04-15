# EBC reliability

I am aware that *still* some distrust of emailed scoring exists and am consequently offering this more detailed explanation of how things work, and sometimes don't.

I have had a technical (developing, testing, debugging) involvement with email over the last 50 years, a technical (dtd) involvement with EBC over the last six years, multiple devices, multiple apps, multiple servers, multiple networks, multiple countries. I speak with some authority on this topic BUT you should not rely on my authority. Please feel free to consult other experts (not the Facebook variety) and conduct your own experiments.

## On your phone
Most recently I have been using a 2024 Samsung Galaxy S24+ smartphone running Android and with the Gmail app acting as my email client. Other devices and apps will vary in detail from my descriptions here but the principles will be the same on any modern device.

The bonus claim process begins with taking a photo on the phone. Examine the captured image, make sure it's a good image, share using email, select the rally address.

At this point, the claim exists in the Gmail folder 'Drafts'. It will remain in that folder while I complete the claim until I either delete it or click 'Send'. This is true even if my phone loses power or reboots.

When I click 'Send', the message is moved to the Gmail folder 'Outbox'. It will remain in that folder until transmission is successful or I delete the email.

If transmission of the email succeeds, the message is moved to the Gmail folder 'Sent'. It will remain in that folder unless I delete it.

## Transmission
Clicking 'Send' causes the phone to attempt to connect (cell, wifi) to a suitable network server in order to transmit the email.

Transmission can fail for one of several reasons:-

- Locality/terrain: 
        there is no signal available to carry messages. This might be a temporary or permanent situation.
- Weather:
        very wet or windy conditions can affect signal.
- Network access configuration: 
        transport might be denied by a carrier for access plan reasons, eg. roaming or authentication.
- Flight mode activated:
        all external signals blocked by the device.

In almost all cases, moving to a better area or activating the right settings will cause automatic transmission of outstanding messages.

## Mailbox reception
The final step before being accessed by ScoreMaster is the arrival of messages into the designated mailbox, a server living in the cloud. The process of travelling from your phone to arriving in the mailbox can take anywhere from a few seconds to several hours but messages are almost always delivered very quickly, hence the widespread misconception that email is instantaneous.

100 years ago, anyone could send emails, as anyone, to anyone, without discrimination by using British Telecom's open relay server. That led to the era of SPAM and phishing which in turn led to ever increasing layers of what I shall call antispam protocols. The nerds among you will be aware of SPF, DKIM, DMARC, etc as well as the various implementations of algorithms based on the works of Thomas Bayes.

The use of these protocols can lead to the non-delivery of your emails or the non-receipt of emails by certain servers. These interruptions can be permanent or temporary. Permanent interruptions require you (or your ISP) to take some corrective action but will cause problems for you well beyond a mere failed bonus claim.

Protocol based interruptions result in emails being diverted to a junk folder or in some cases being silently rejected altogether.

These issues are unlikely to affect bonus claims if entrants have successfully submitted anything before.

## ScoreMaster reception
ScoreMaster automatically monitors its designated mailbox looking for bonus claims throughout the rally.

When new mail is available, it is examined for a valid claim line (rider, bonus, odo time). For the nerds, a valid claim line matches the regular expression (\w+)\s+([\w\-]+\-?)\s+(\d+)\s+([\d:\.\-\+TZ]+)\s*(.*)

Anything not having a valid claim line is left unread in the mailbox and will be ignored by ScoreMaster.

Valid claims where the rider number does not match the sender's email address are also left unread in the mailbox. This is to ensure that claims from one entrant do not interfere with the claims of another.

Successfully retrieved claims are presented to the scoring team for judging.

## End of rally
Entrants returning to rally HQ are advised to check their phones before completing check-in. Anything stuck in the Outbox should be transmitted before check-in but fear not!

In almost all cases, the claims registered in ScoreMaster will match (after check-in and any catch up) the claims submitted by the entrant. Where claims are missing from ScoreMaster, the entrant's phone can be examined and claims accepted based on its contents. The test is "has a claim been raised and 'sent'", even if transmission failed or mailbox reception failed. Typically this test means looking in the Outbox for unsent items.

## Summary
It's true that email can fail. That doesn't matter because what matters is that a good bonus claim will be taken into account by the scoring team, if necessary by direct examination of the originating phone.

In the early days of EBC failures were more prevalent and caused more problems but several things have improved since then leading to a very robust scoring mechanism now. Since 2018 improvements have been made in:-
- Email systems and protocols themselves.
- Network availability and reliability.
- Smartphone technology.
- Bonus claim structure and redundancy.
- Scoring protocols.
- Understanding of modes of failure and remedies.

In short, EBC is a robust, simple and efficient mechanism for scoring rallies and we should focus on how well it works rather than the rare cases where it needs help.
