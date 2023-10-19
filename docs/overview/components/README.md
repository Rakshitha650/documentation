# Components

The image below is a block diagram of the e-Signet comprising various components along with the different layers and external systems.

![](\_images/component-diagram.png)

### Relying Party System

[Relying Party](../../glossary.md#relying-party) Systems depend on identity providers, such as e-Signet, to authenticate and verify the identities of users before granting them access to protected resources or services.&#x20;

Clients utilizing OpenID Connect within the OAuth 2.0 framework are commonly referred to as Relying Parties (RPs).

In the case of VC issuance, they are simply OAuth 2.0 clients. To ensure enhanced security, e-Signet exclusively supports confidential clients.

### Digital Wallet

[Digital Wallets](../../glossary.md#digital-id-wallet) are software-based platforms used to securely store and share the certified credentials of the wallet holder. These credentials are verified claims about the individual, typically certified by the identification system.

The e-Signet VCI service offers a feature that allows the issuance of verifiable credentials to any digital wallet that adheres to the OpenID4VCI protocol.

### **e-Signet UI**

This is the user interface component of e-Signet, developed using React JS. Its main functionality is to handle user authentication and obtain user consent. e-Signet UI seamlessly integrates with the UI REST endpoints provided by **esignet-service**.

* One notable feature of e-Signet UI is its support for multiple languages.
* e-Signet UI also offers QR code-based login with support for multiple digital wallets.
* In addition, e-Signet UI is compatible with MOSIP SBI 2.0 for biometrics capture.
* Furthermore, e-Signet UI provides flag-based captcha validation for OTP login.
* Lastly, the landing page of e-Signet UI showcases the available _.well-know_ endpoints.

{% hint style="info" %}
FAQs

* How can we enable multiple digital wallet support?
* How do we configure the expected quality score, timeouts, and number of bio attributes to be captured?
* How can we enable or disable the captcha?
{% endhint %}

### **e-Signet Service**

This service is the primary backend Spring Java application that incorporates various layers and integrates with other components mentioned on this page.

1. **Core components**: The e-Signet core library is used to manage core service interfaces, constants, exceptions, validators, and utility methods.
2. **Service layer**: This layer represents the implementation of the interfaces defined in the e-Signet core library. Each protocol implementation is a separate service, such as the complete OIDC protocol implementation being part of the oidc-service and VCI protocol implementations residing in the vci-service.
   * Service modules utilize caching to enhance transaction access and update speeds, as well as to prevent the need for persistent storage of transaction details.
   * Persistent storage is only used for OIDC client registration details.
   * Kafka is employed to support asynchronous operations during wallet-based logins.
3. **Rest APIs**: The e-Signet-service module exposes REST endpoints for the functionality implemented in the service layer modules.
4. **Key Manager**
   * Key Manager is used for secure key management and cryptography functionalities required by the e-Signet service component.
   * It can be integrated with an HSM (Hardware Security Module) for the secure storage of keys.
   * Typically, Key Manager is run as a service, but it is used as a library in the e-Signet Service to minimize the effort of managing extra containers.
   * It depends upon the Data layer for maintaining the metadata on keys.
5. **Plugins**: Integration points with external systems are designed to be pluggable, allowing easy integration with any ID system. The pluggable integration points are as follows:
   * **Authenticator** - for identity verification
   * **VCIssuancePlugin** - for constructing Verifiable Credentials (VCs)
   * **AuditPlugin** - for auditing all events
   * **CaptchaValidator** - for captcha validation

{% hint style="info" %}
All plugin interfaces are defined in the esignet-integration-api module.
{% endhint %}

### **Identification System (ID system)**

This system refers to any operational or fundamental identification system that houses the user's demographic and biometric details (if applicable). It could be a database or a system equipped with suitable mechanisms to facilitate identity verification and the sharing of verified user data.