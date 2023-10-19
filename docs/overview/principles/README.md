# Principles

e-Signet is designed with the architectural principles mentioned below. These architecture principles are core to developing the system's features and greatly influence how and why specific software design patterns are used.

## Open Standards

e-Signet flows open standards such as,

* [OAuth 2.0](https://oauth.net/2/)
* [OpenID Connect](https://openid.net/specs/openid-connect-core-1\_0.html)
* [OpenID4VCI](https://openid.net/specs/openid-4-verifiable-credential-issuance-1\_0.html)
* [IEEE SA P3167 SBI 2.0](https://standards.ieee.org/ieee/3167/10925/)

As e-Signet follows OpenID Connect, it gets a lot of client libraries for integration. Hence, avoid custom code building for integration.

## Data Privacy

* As the user enters the ID directly on the e-Signet page, the relying party does not have to store the ID, which could otherwise be used for profiling in case of data leaks. The relying party gets a privacy-enabled token that is unique to the relying party and the user and is called the PSUT (Partner Specific User Token).
* Sensitive data is protected (not stored or logged in clear form).
* Consent support: the user decides what data can be shared with the relying party.

## No Vendor Lock-in

* e-Signet is vendor-neutral
* Any biometric device compatible with the IEEE P3167 SBI 2.0 specification can connect with e-Signet

## Commodity Computing

e-Signet backend services are designed to run as containers, which do not depend on any specialized hardware or specific cloud solutions. It can run on any general-purpose VM that supports Docker containers. This also helps in avoiding vendor lock-in.

## Secure By Default

* Encryption of data in flight or at rest.
* Integration with trusted applications only.
* Fraud avoidance: association of authentication only with specific transactions
* All data that goes out or that comes in is digitally signed by the respective sender.
* Any data sent to a relying party is encrypted.
* Protection against internal attacks: Every record in DB is protected with integrity.
* Centralized key management.
* All APIs are protected with OAUTH 2.0.