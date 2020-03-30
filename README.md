# Proposal for a National Antibody ID
To minimize the spread of infectious diseaes, a central database and PKI (Public Key Infrastructure) ecosystem could instaneouly and non-invasively check an individual's known health status. The ID system can be thought of as a boarding pass as used for airline passengers with extra guarantees of privacy, authenticity and flexibility. Individuals would present their health "boarding pass" when entering buildings, sensitive areas (nursing homes, dental appointments, meeting with leaders) or other large gatherings.

## Goals
- Quckly and cleary indicate if an individual is cleared to pass a physical security checkpoint
- Varying levels of verification as required by venue
- Don't reveal unecesary PHI or PII to ANY party, including the health authority
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

The technical details of managing private keys can be complex and are important to get right. A major existing PKI participant like DigiCert, Microsoft or Google should assist health authorities in their PKI infrasturcutre and security practices.

### Trust Challenges
- How does the health authority trust HCPs?
- How do patients trust HCPs and how can they fix their health record?
- How can third-parties trust barcodes?

## Issuance
**Basic Scenario:** An patient obtains a temporary ID token from a CDC portal or mobile app. The patient visits his healthcare provider for a test of antibodies to a specific disease in his body and provides token to HCP. The patient's doctor and/or testing laboratory submit the test results to the CDC database along with the patient's token. The patient can then download the pertient aspects of their heath record as a barcode in their app or print to paper. A business wishing to certify that all of it's employees are immune and non-contagious can scan their employee's barcordes prior to each day of work, verifying test result status and validity.

**Other Scenarios:** 
- A business can protect employees from each other and customers when working in close proximity.
- Concert/movie/shopping/transportation venues can protect their employees and customers
- POTUS can screen individuals before meeting them in person
- Sexual partners can verify each other's STD test results before being intimate

## Barcode Verification
Even though generating a digitally-signed barcode is fairly straighforward, preventing someone from copying this barcode and giving it to a friend for impersonation is a real threat. How can we ensure each barcode is associated with the true owner? Airports address this in their barcodes using a 2nd factor of identification. A TSA agent compares a physical identification card with the barcode data. A similar multi-factor approach needs to be used here as well, but there are other options to physical ID cards:

1. **Physical ID**: verify a physical identification card matches what is in the barcode (same as TSA). This is somewhat tedious for agents and may be possible to spoof the physical ID. May require patient to register more PII with the health authority than they are comfortable with. 
2. **SMS/Cell**: Patient can register a phone number with the CDC. The security screening agent can call or sms the number. This is possibly more tedious than option 1, limited to cell phone security levels, and an individual could give his device to another person temporarily. 
3. **Push Notifications**: A mobile app used for retrieving the barcode could also receive push notifications. Similar to option 2, but removes weak link of cell providers.
4. **Location fencing**: enforce restrictions on reasonable location changes. E.g. an individual could not be scanned in NY and LA within 4 hrs of each other, and not be scanned at any two different buildings in less than five minutes. 
5. **Shared Biometric**: An employer can indepently manage biometric verification like fingerprint, voiceprint, or facial recognition. We prefer not to create a national biometric database. 
6. **Private Biometric**: If a mobile OS can guarantee a biometric reading like finger or facial recognition belong to only one person, then a subject's device can also perform biometric identification and send a result or hash to a brokering service. As currently implemented, most mobile device technologies such as Apple's TouchID or FaceID technically allow fingers and faces from multiple subjects.

## Privacy
Provide as little information as you want to CDC

## Extensibility
The Antibody ID should be generic enough to contain the known status of any health condition. 

## Format
The health certificate boarding pass is a 2D barcode of base64-encoded plaintext data. It should contain the following fields:
- Salted and hashed UID of patient
- Issue Date (timestamp)
- Health 
- Signer
- Signature (SHA-256 hash)

## Incentives
## Auditing
## Technology Alternatives
- Can a distributed infrastructure like blockchain solve this problem better?

