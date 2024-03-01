# 1.2.0.1

## Release Notes

**Release Version**: 1.2.0.1 

**Upgrade From**: 1.2.0

**Release Date**: 4th March, 2024

This 1.2.0.1 release comprises of all features which have been released as beta release and few major fixes as requested by the countries. This release focuses on testability, usability, and security.

Domain Specific Language (DSL) Automation scripts, which are part of this release, enable platform testing. Also, few security related issues are resolved.

One of the major highlights of this patch release is the print stage. The print stage, now re-named as **Credential Requester Stage**, additionally manages the initiation of credential requests tailored to partner-specific information needs.  

Click [here](https://docs.mosip.io/1.2.0/modules/registration-processor#stages-and-services) to know more about Credential Requestor Stage.

Versioning of Mock Services is revised. Hence, the Mock Service version is changed from v 1.2.0.1-B4 to v 1.0. Additionally, there are a few changes implemented in Mock ABIS.

To know more about bug fixes and enhancements, refer [here](../1.2.0.1/enhancements-1.2.0.1.md).

**Major Areas of Work**

* Credential Requestor Stage
* Introduction of Handles in ID Repository
* Enabling password-based authentication in IDA
* Functional bug fixes
* Security bug fixes
* DSL Automation
* Performance fixes
* Sonar bug fixes

## Repository Released

| **Repositories**            | **Tags Released**                                                                    |
| --------------------------- | ------------------------------------------------------------------------------------ |
| bio-utils                   | .                                                                                    |
| commons                     | .                                                                                    |
| mosip-openid-bridge         | .                                                                                    |
| biosdk-client               | .                                                                                    |
| biosdk-services             | .                                                                                    |
| audit-manager               | .                                                                                    |
| keymanager                  | .                                                                                    |
| khazana                     | .                                                                                    |
| packet-manager              | .                                                                                    |
| admin-services              | .                                                                                    |
| id-repository               | .                                                                                    |
| pre-registration            | .                                                                                    |
| id-authentication           | .                                                                                    |
| registration                | .                                                                                    |
| resident-services           | .                                                                                    |
| registration-client         | .                                                                                    |
| partner-management-services | .                                                                                    |
| print                       | .                                                                                    |
| websub                      | .                                                                                    |
| durian                      | .                                                                                    |
| mosip-config                | .                                                                                    |
| mosip-mock-services         | .                                                                                    |
| migration-utility           | .                                                                                    |
| mosip-functional-tests      | .                                                                                    |
| converters                  | .                                                                                    |
| keyclock                    | .                                                                                    |
| reporting                   | .                                                                                    |
| mosip-ref-impl              | .                                                                                    |
| artifactory-ref-impl        | .                                                                                    |
| mosip/mock-smtp-sms         | .                                                                                    |
| mosip-functional-tests      | .                                                                                    |
| mosip-helm                  | .                                                                                    |
| mosip-infra                 | .                                                                                    |
| K8s-infra                   | .                                                                                    |

## Documentation

* Functional test report
* [Known Issues](https://mosip.atlassian.net/browse/MOSIP-29944?jql=labels%20%3D%20Known_Issue_1.2.0.1) 