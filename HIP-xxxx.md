# HIP-xxxx : Time Locked UPDATE transactions

```
Number:  HIP-xxxx
Title:   Time Locked UPDATE transactions
Type:    Standards Track
Status:  Draft
Authors: Evan Botello (@evbots)
Created: 2021-04-13
```

## Abstract


## Motivation

Handshake provides TLD owners with absolute discretion over name resource records. If a TLD owner chooses to open up a TLD to second level domains (SLDs), those SLD owners may want assurances about the state of resource records on the TLD over a period of time. To date, the models for managing SLD registrations have taken two forms:

* TLD owners that can change the resource records at will that take effect immediately.
* TLD owners that have [permanently locked](https://hnsnetwork.com/names/badass) the TLD to never allow updates.

A third possibility is proposed here that would provide a flexibile model for both sets of stakeholders: TLD owners and SLD owners. At a high level, a time locked UPDATE transaction would take the following form:

* TLD is transferred to a locking script where an arbitrary time lock is expressed as a block number (for example: 500,000 blocks or roughly 9.5 years).
* When a TLD owner wants to change the records in the name root zone, a first UPDATE transaction is sent that signals to everyone how the resource records will change. For example, adding a new TXT record.
* After the specified time period (for example, 500,000 blocks or 9.5 years), a second UPDATE transaction is sent that effectively finalizes the change in resource records. The only change allowed to records is the change specified in the first transaction.

This would allow TLDs to be effectively upgradable, while respecting a contract that both stakeholders (TLD and SLD owners) opt-in to. This model would provide flexibility for SLD owners to evaluate the risk of a decision to register an SLD. TLD owners that set a shorter time periods (months or days) for UPDATE locks would present different risks than TLD owners that set longer time periods (10 or 50 years for example). This model allows TLDs to have different risk tradeoffs. In the future, SLD owners might want to migrate the management of their SLDs to some different scheme (blockchain, DNS server, or otherwise). This model would provide a way to achieve this using a contract that stakeholders agree to in advance. 

## Specification


## Implementation

