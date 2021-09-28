# Vaccine-Certificates

By Richard Nelson

The current state (as of September 2021) of COVID-19 vaccine certificates in Australia is complex to follow:
- The federal "certificates" available through the immunisation history, the PDF certificates (available through Medicare and the Express Plus Medicare apps), the display of certificates in the apps are all unverifiable and easily forged.
- The federal government has announced a national implementation tied to passports, but only intended for international travel
- Various states have committed to implementing verifiable certificates, but it's unclear how state travellers will not be confused. The ACT have said they will not implement one as part of a check-in application.

Service NSW announced they will be implementing vaccine status as part of the COVID Check-In functionality in the ServiceNSW application. This means that while it may be a good user experience to begin with, in-app vaccine status could be largely tied with check-in and contact tracing efforts which may be not particularly useful when COVID-19 becomes endemic.

Fortunately the [EU have been forward thinking](https://github.com/eu-digital-green-certificates/dgc-overview), and have a solution that fulfills various needs. They use well understood private/public key mechanisms to sign vaccination, test and recovery data for use in a certificate that can be scanned with "verifier" apps. The solution works offline, and with paper certificates. The verifier apps load the public keys of various state's health authorities and can very quickly determine if a certificate contains data that fulfills the rules of an individual nation. This allows for travel, and verification within countries.

The EU, and various individual countries, have open sourced large amounts of full implementation, documentation, technical specifications that Australia could easily build upon.

As proof of a workable solution, [code has been written](https://github.com/wabzqem/vaxproxy) that converts the vaccine data JSON as given to the Medicare Plus Express application into a signed QR code compatible with the EU system. The signing of the data is done by the "vaxproxy" code, outside of Medicare, so while it is a provable concept the current implementation could not be trusted by the EU system. This code has further been integrated into a [iOS and macOS application](https://github.com/wabzqem/CovidCertificate-App-iOS) that logs in to myGov, received applicable medicare claimants and retrieves the signed QR code for each individual. These QR codes are verifiable using the applicable public key (a verifier app with this is provided), cannot be forged, and can only be produced by a user with real immunisation data, because the vaxproxy only signs certificates for those who are truly vaccinated.

These QR codes can be loaded into an existing COVID-19 Wallet application, and can be verified with existing Verifier applications. Because the public key associated with the signatures is not trusted by the EU, minor changes to these applications are required for proper signature verification. If the Australian government integrated with the EU trust network, *no changes to these applications would be necessary* to have end-to-end functionality for Australians. Cost of implementation would be minimal, given the amount of open-source work that could be built upo.
