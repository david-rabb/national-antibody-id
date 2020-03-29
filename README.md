# Proposal for a National Antibody ID
To minimize the spread of infectious diseaes, a central database and PKI (Public Key Infrastructure) ecosystem could quickly and non-invasively check an individual's known health status. The ID system can be thought of as a boarding pass as used for airline passengers with extra gaurantees of privacy, authenticity and flexibility. Individuals would present their Antibody ID when entering buildings, sensitive areas (nursing homes, dental appointments, meeting with leaders) or other large gatherings.

## Goals
- [Quckly and cleary indicate if an individual is cleared to pass a physical security checkpoint](#Verification)
- Varying levels of verification as required by venue
- Don't reveal unecesary PHI or PII
- Extendable public fields -- new health conditions or other fields can be added as needed
- Hacking & Spoofing protections
- PKI Rooted by a central health authority
- Revokable
- Printable or Mobile
- Incentives for individuals to use the system


## PKI and the Trust Model
Public key infrastructure is a well-known and standard method for issuing and trusting public key certificates. The most well-known application of PKI is securing connections to websites by only allowing certificates that have been signed by a trusted certificate authority. 

The trust model in this case is that registered healthcare professionals submit test results to a central authority to append to a patient's health record. Individuals can generate an encrypted and signed 2D barcode certificate containing assertions of their health record. Finally, independent third parties (business, venues, other people) can verify patient assertions by scanning the bar codes. 

In the initial release, the PKI can be simple: a central state or federal health authority like the CDC, can maintain one long-term root certificate and rotating intermediate certificates. Later, other entities like hospitals and clinics could be introduced as alternate intermediate authorities. 

The technical details of managing private keys can be complex and are important to get right. A major existing PKI participant like Digicert, Microsoft or Google should assist health authorities in their PKI infrasturcutre and security practices.

### Trust Challenges
- How does the health authority trust HCPs?
- How do patients trust HCPs and how can they fix their health record?
- How can third-parties trust barcodes?

## Issuance
**Scenario:** An patient obtains a temporary ID token from a CDC portal or mobile app. The patient visits his healthcare provider for a test of antibodies to a specific disease in his system and provides token. The patient's doctor and/or testing laboratory submit the test results to the CDC database along with the patient's token. The patient can then download the pertient aspects of their heath record as a barcode in their app or print to paper. A business wishing to certify that all of it's employees are immune and non-contagious can scan their employee's barcordes prior to each day of work, verifying test result status and validity.

## Verification
## Privacy
## Extensibility
## Spoofing
## Format
## Incentives
## Auditing
## Alternatives
- Can a distributed infrastructure like blockchain solve this problem better?

