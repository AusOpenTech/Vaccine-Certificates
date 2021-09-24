# Surveillance is not necessary for secure vaccine passports

[Vanessa Teague](https://thinkingcybersecurity.com/) and
[Yuval Yarom](https://cs.adelaide.edu.au/~yval/)

To be useful, vaccine passports need to meet at least two conditions.  First they should be hard to forge, and second they should be socially acceptable, and in particular, have minimal impact on our privacy and liberties. Fortunately, cryptography offers a solution that is both secure and privacy-friendly. Sadly, this does not seem to be the solution Australia is taking.

## Secure, offline-verifiable vaccine certificates are also easy and cheap

A vaccine passport does not require any kind of online access---a static pdf or printout would suffice, and only require updates when the person gets a booster.
  
The [EU's digital COVID certificate](https://ec.europa.eu/info/live-work-travel-eu/coronavirus-response/safe-covid-19-vaccines-europeans/eu-digital-covid-certificate_en) uses a digital signature in a QR code to prove its authenticity.  The signature makes it hard to forge. If someone needs to verify that it is genuine, they use cryptography to verify the authority's signature offline, **without any need to query the authority that generated the certificate**.  This is extremely important because it means no government server needs to be notified of where, or even whether, that person displayed their vaccine passport.

Richard Nelson's proof-of-concept shows a [simple, offline-verifiable digital certificate](https://github.com/AusOpenTech/Vaccine-Certificates) intended for use in Australia. It took one person a few days, and could be adopted almost immediately by any Australian authority that chose to put their own digital signature on it. 

It is not a shortage of technical skill or lack of resources that inhibits the use of privacy-preserving and secure technologies in Australia.

## Why vaccine certificates should not be linked with QR-code checkin

Unfortunately, the national cabinet has recently [decided that vaccine passports will be integrated into QR-code checkin](https://www.theguardian.com/australia-news/2021/sep/25/vaccine-passports-in-australia-who-will-impose-them-and-how-will-they-work). This is very sad news for privacy in Australia.  For one thing, rather than terminating the QR-code checkin apps and ending ["probably the most extensive surveillance operation Australia has ever seen,"](https://theconversation.com/police-access-to-covid-check-in-data-is-an-affront-to-our-privacy-we-need-stronger-and-more-consistent-rules-in-place-167360) we are instead entangling them with the long-term solution for moving out from the pandemic, thus making them much harder to drop.

Even worse, although no technical details have yet been released, media reports suggest that the checkin apps may query a federally-controlled vaccine database, such as Medicare or the Australian Immunization Register, every time a person checks in. This effectively CC's to federal authorities the huge databases that keep track of our location whenever we check in.

There is also no guarantee that  these privacy-invasive certificates will be hard to forge. 

There is a huge temptation to use data once collected, and mission creep is a known aspect of surveillance databases. It should surprise nobody that the [police](https://www.brisbanetimes.com.au/national/queensland/officer-stood-down-over-incident-that-sparked-check-in-qld-data-access-20210713-p5896p.html) in [some states](https://www.abc.net.au/news/2021-06-15/safewa-app-sparks-urgent-law-change-after-police-access-data/100201340) have accessed the QR-code checkin databases, given that mission creep already occurred for [metadata surveillance databases](https://humanrights.gov.au/about/news/metadata-law-review-makes-key-changes).  [Improved legal protections](https://www.oaic.gov.au/privacy/guidance-and-advice/guidelines-for-state-and-territory-governments-creating-nationally-consistent-requirements-to-collect-personal-information-for-contact-tracing-purposes/) might help, but are unlikely to prevent federal authorities, let alone criminals or foreign intelligence services, from gaining access. The only way to keep a database secure is not to build it in the first place. This is particularly relevant because the COVID checkin database never needed to be built.

## Data minimisation

It was never necessary to upload everyone’s venue checkin data just in case they needed to be traced. Aotearoa-NZ and the UK do the checkin as an automated diary, with automated notifications to the person when an exposure site is found in the person's diary. We could easily have added notification *from* the app *to* government contact tracers if exposure was detected and human contact tracing was deemed necessary.  Like the COVIDSafe App, QR-code-based checkin could easily have been designed not to upload data except when needed.  There was never a justification for just-in-case upload of everyone’s location.

The continuing constant upload of venue checkin locations is unjustified. It never was justified - it was only tolerated as a temporary measure, in the mistaken belief that it was necessary for tracing COVID cases.

Likewise, surveillance-based vaccination passports are unnecessary, and if anything less secure or reliable than the EU model, in which digitally-signed certificates can be verified offline.

## Conclusion: privacy, democracy and national security

Australian democracy has lost on [metadata surveillance](https://auspublaw.org/2020/02/a-window-for-change-why-the-australian-metadata-retention-scheme-lags-behind-the-eu-and-usa/), [military control of cryptography research](https://www1.defence.gov.au/business-industry/export/controls/training-faqs/case-studies/facts-myths), [press-ganging of tech workers for ASIO without a warrant](https://www.inslm.gov.au/reviews-reports/telecommunications-and-other-legislation-amendment-act-2018-related-matters), [account takeover of non-suspects](https://www.aph.gov.au/Parliamentary_Business/Bills_Legislation/Bills_Search_Results/Result?bId=r6623), [Internet censorship](https://theconversation.com/a-new-online-safety-bill-could-allow-censorship-of-anyone-who-engages-with-sexual-content-on-the-internet-154739), and many other things. You might think this is just one more.  But the accumulation matters, and the right to travel freely and associate freely, without either the Australian government or the Chinese government learning your personal habits and social connections, is critical to the future of Australian democracy, whether you think its worst enemies come from the inside or the outside.

If we must have vaccine passports, they must not come with location surveillance.

--------------------------------------

<sub><sup>This article is made available under a Creative Commons license: you are welcome to re-use it as long as you acknowledge the original source.
</sup></sub>