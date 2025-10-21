# Peppol implementation guide for the construction industry

**Engineer-To-Order Construction products**  
>**Publisher:** Peppol Authority of Finland (State Treasury) & Rakennusteollisuus ry\
>**Release:** 2025-10-01  
**Versio:** 0.9.0  
**Status:** Draft

> [!NOTE]
> This document guides the implementation of the **Peppol Catalogue** and **Ordering/Order Response** (plus Advanced Despatch/Receipt Advice placeholder) for the Finnish construction industry, with a focus on **engineer-to-order (ETO) precast concrete**.
> This guide does not change general Peppol BIS rules. When something is not stated here, refer to the official Peppol BIS documentation (e.g., rules for currencies, dates, times, decimals, code lists). It is forbidden to repurpose elements for uses other than their intended meaning.

---

## Table of contents

* [1. Introduction to Peppol](#1-introduction-to-peppol)
* [2. Change management](#2-change-management)
* [3. Covered Business Interoperability Specifications](#3-covered-business-interoperability-specifications)

  * [3.1 BIS Catalogue with response](#31-bis-catalogue-with-response)
  * [3.2 BIS Ordering](#32-bis-ordering)
  * [3.3 BIS Advanced Despatch Advice with Receipt Advice](#33-bis-advanced-despatch-advice-with-receipt-advice)
* [4. Catalogue (T19) – implementation details](#4-catalogue-t19--implementation-details)

  * [4.1 Document header level](#41-document-header-level)
  * [4.2 Parties](#42-parties)

    * [4.2.1 Provider Party (seller)](#421-provider-party-seller)
    * [4.2.2 Receiver Party (buyer)](#422-receiver-party-buyer)
  * [4.3 Catalogue line level](#43-catalogue-line-level)
* [5. Catalogue Response (T58)](#5-catalogue-response-t58)

  * [5.1 Document header level](#51-document-header-level)
  * [5.2 Parties](#52-parties)

    * [5.2.1 Sender Party](#521-sender-party)
    * [5.2.2 Receiver Party](#522-receiver-party)
  * [5.3 Document response](#53-document-response)
  * [5.4 Referencing the original catalogue](#54-referencing-the-original-catalogue)
* [6. Order (T01)](#6-order-t01)

  * [6.1 Document header level](#61-document-header-level)
  * [6.2 Parties](#62-parties)

    * [6.2.1 Buyer Customer Party](#621-buyer-customer-party)
    * [6.2.2 Seller Supplier Party](#622-seller-supplier-party)
  * [6.3 Delivery](#63-delivery)
  * [6.4 Order line level](#64-order-line-level)
  * [6.5 Item information on the order line](#65-item-information-on-the-order-line)
* [7. Order Response (T76)](#7-order-response-t76)

  * [7.1 Document header level](#71-document-header-level)
  * [7.2 Parties](#72-parties)
  * [7.3 Delivery](#73-delivery)
  * [7.4 Order response lines](#74-order-response-lines)
* [Attachment A: Quantity/@unitCode usage](#attachment-a-quantityunitcode-usage)
* [Attachment B: AdditionalItemProperty usage](#attachment-b-additionalitemproperty-usage)
* [Attachment C: Dimension descriptions](#attachment-c-dimension-descriptions)
* [Example files](#example-files)

---

## 1. Introduction to Peppol

[Peppol](https://peppol.org/) is a network and specification of electronic business transactions. It is used to exchange information between organisations in a structured way. The Peppol network is based on the so-called four corner model. It means that every end-user organisation is free to choose its own Peppol service provider without having to consider which service provider its business partners use. Everyone has to connect just once to a Peppol service provider in order to exchange electronic business documents with all other end users in the Peppol network.

Peppol is not a procurement system, a portal or an ERP. It enables different organisations to connect their information systems and offers a shared digital language for organisations all over the world.
This implementation guide is focused on the data needs of the Finnish construction industry in engineer-to-order precast concrete. Any rules that apply to the usage of Peppol in general are not changed by this document. This document does not cover all possible scenarios. Please refer to the general [Peppol BIS](https://docs.peppol.eu/poacc/upgrade-3/) guidelines if something is not stated here. For example, all currencies, dates, times, decimals and code lists are to be used as instructed in the general Peppol guidelines.

---

## 2. Change management

This implementation guide was created jointly by **BETK** project representatives and the **Peppol Authority of Finland (State Treasury)**.

For questions or updates, contact **State Treasury**: `peppol@valtiokonttori.fi`.  The State Treasury will gather relevant industry representatives for the update process.

---

## 3. Covered Business Interoperability Specifications

This implementation guide covers three Peppol Business Interoperability Specifications (BIS) used in the Peppol network:

* **BIS Catalogue with response**
* **BIS Ordering**
* **BIS Advanced Despatch Advice with Receipt Advice**

---

### 3.1 BIS Catalogue with response

BIS Catalogue with response covers *Catalogue* and *Catalogue Response* transactions. The catalogue receiver **must** respond to each catalogue with the catalogue response transaction. The catalogue response transaction is used to notify the catalogue sender that the receiver has received, accepted or rejected the catalogue.

The syntaxes of the [Peppol Catalogue transaction (T19)](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/tree/) and [Peppol Catalogue Response transaction (T58)](https://docs.peppol.eu/poacc/upgrade-3/syntax/CatalogueResponse/tree/) are covered later in this document.

<img width="2497" height="1675" alt="2025-10-14_Kuva1" src="https://github.com/user-attachments/assets/8444b8a4-bccb-45e5-ad60-a817c8eb2a55" /> <br> Figure. 1


### 3.2 BIS Ordering

[BIS Ordering](https://docs.peppol.eu/poacc/upgrade-3/profiles/28-ordering/) covers order and order response transactions. The supplier must respond to each order with an order response transaction. The order response transaction is used to tell the buyer that the order was received, accepted, declined or accepted partially. Information about delivery dates can be added to the order response.
The syntaxes of the Peppol Order transaction (T01) and Peppol Order Response transaction (T76) are covered later in this document.

The syntaxes of the [Peppol Order transaction (T01)](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/tree/) and [Peppol Order Response transaction (T76)](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/tree/) are covered later in this document.

<img width="3729" height="1674" alt="2025-10-16_Kuva1" src="https://github.com/user-attachments/assets/516ca678-0b62-47f1-9e79-2949d7de3ca1" />  <br> Figure. 2


### 3.3 BIS Advanced Despatch Advice with Receipt Advice


<img width="2578" height="1445" alt="2025-10-14_Kuva3" src="https://github.com/user-attachments/assets/53e529d0-3bc4-4322-81e4-275a553b3a56" />  <br> Figure. 3


> $\color{red}{\textsf{Draft note:}}$ *Tämä täytetään lomakauden jälkeen.*

---

## 4. Catalogue (T19) – implementation details

The whole syntax of the Peppol Catalogue transaction (T19) is covered on the [Peppol website](https://peppol.org). This implementation guide does not add any additional elements to the syntax. All general Peppol rules must be followed. It is forbidden to use an element for a purpose other than what it is intended to be used for. Please refer to the general Peppol guidance if some element is not covered in this implementation guide.

---

### 4.1 Document header level

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is the catalogue identifier, the main identifier for this document. It is a mandatory field.
- [cbc:ActionCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ActionCode/) is used to tell if the catalogue is sent for the first time, it replaces a catalogue entirely, it updates some catalogue lines or if the catalogue is deleted. Use values from the Catalogue Action code, header level (OpenPeppol) codelist. If this field is not in the catalogue, it means that the catalogue fully replaces the source catalogue. 
- [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/) can be used to give the catalogue a name.
- [cbc:IssueDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-IssueDate/) is a mandatory element which is used to convey the issue date of the catalogue. The date must be formatted as YYYY-MM-DD.
- [cbc:VersionID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-VersionID/) is used to keep track of the up-to-date version of the catalogue as there might be updates to the catalogue.
- [cac:ValidityPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ValidityPeriod/) tells the time period when the catalogue is valid and can be used to order. It is a mandatory element. The time must be formatted as HH:MM:SS.
- [cac:ReferencedContract](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReferencedContract/) is used to refer to a contract between the buyer and the seller. This is an important value as the terms of invoicing are agreed in the contract.
- [cac:SourceCatalogueReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-SourceCatalogueReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to refer to the previous version of the catalogue. This is important when making updated to the current version of the catalogue to track changes.
- [cac:TradingTerms](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-TradingTerms/) / [cbc:Information](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-TradingTerms/cbc-Information/) can be used to refer to the general payment conditions

### 4.2 Parties

>  $\color{red}{\textsf{Draft note:}}$ **Electronic addresses (`cbc:EndpointID`)**

#### 4.2.1 Provider Party (seller)

The [cac:ProviderParty](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/) is the one who issues the catalogue and acts as a seller. The syntax also includes the Seller Supplier Party, but that does not apply to the concrete element use case, as the seller is always the one who issues the catalogue.

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic Peppol address of the seller. The [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is mandatory to be used with the EndpointID element. For Finnish organisations the EndpointID is always an OVT code with scheme ID 0216. Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) values:

| cbc:EndpointID | schemeID | Notes |
|--------------------|----------|-------|
| `003712345678`       | `0216`     | SchemeID 0216 stands for Finnish EDI identifier (OVT code). OVT Code structure is:<br>· ‘0037’ is a fixed value<br>· Company ID (Y-tunnus) without the dash mark ‘-’<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| `6412345678901`      | `0088`     | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) can contain an internal ID understood by the buyer and/or seller. This can be for example a GLN of the factory. [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is not mandatory for this field.
- [cac:PostalAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PostalAddress/) and its child elements are used for the Address of the company. This is for example the address of the head quarters building, not the delivery address.
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is used to tell the official name of the company.
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:CompanyID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-CompanyID/) is used for the business identity code (Y-tunnus) of the company.
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cac:RegistrationAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/) / [cbc:CityName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cbc-CityName/) / [cac:Country](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/) / [cbc:IdentificationCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/cbc-IdentificationCode/) structure is used to tell in which city and country the company is officially registered in.

**Example - Provider Party segment**
```xml
<cac:ProviderParty>
  <cbc:EndpointID schemeID="0216">003712345678</cbc:EndpointID>
  <cac:PartyIdentification>
    <cbc:ID schemeID="0088">5790000435944</cbc:ID>
  </cac:PartyIdentification>
  <cac:PostalAddress>
    <cbc:StreetName>Katu 1</cbc:StreetName>
    <cbc:CityName>Helsinki</cbc:CityName>
    <cbc:PostalZone>000500</cbc:PostalZone>
    <cac:Country>
      <cbc:IdentificationCode>FI</cbc:IdentificationCode>
    </cac:Country>
  </cac:PostalAddress>
  <cac:PartyLegalEntity>
    <cbc:RegistrationName>Elementtitehdas Oy</cbc:RegistrationName>
    <cbc:CompanyID schemeID="0212">1234567-8</cbc:CompanyID>
    <cac:RegistrationAddress>
      <cbc:CityName>Helsinki</cbc:CityName>
      <cac:Country>
        <cbc:IdentificationCode>FI</cbc:IdentificationCode>
      </cac:Country>
    </cac:RegistrationAddress>
  </cac:PartyLegalEntity>
</cac:ProviderParty>
```

#### 4.2.2 Receiver Party (buyer)

The [cac:ReceiverParty](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/) is the one who the catalogue is sent to and acts as a buyer. The syntax also includes Buyer Supplier Party, but that does not apply to the concrete element use case as the buyer is always the one who the catalogue is sent to.  
- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic Peppol address of the buyer. The @schemeID is mandatory to be used with the EndpointID element. For Finnish organisations the EndpointID is always an OVT code with scheme ID 0216. Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and @schemeID values:

| cbc:EndpointID | schemeID | Notes |
|----------------|----------|-------|
| `003712345678`   | `0216`     | SchemeID 0216 stands for Finnish EDI identifier (OVT code). OVT Code structure is:<br>· ‘0037’ is a fixed value<br>· Company ID (Y-tunnus) without the dash mark ‘-’<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| `6412345678901`  | `0088`     | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/cac-PartyIdentification/cbc-ID/) can contain an internal ID understood by the buyer and/or seller. For example, this could be a GLN of the construction site. @schemeID is not mandatory for this field.  
- [cac:PostalAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PostalAddress/) and its child elements are used for the Address of the company. For example, this could be the address of the headquarters building, not the delivery address.  
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is used to tell the official name of the company.  
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:CompanyID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-CompanyID/) is used for the business identity code (Y-tunnus) of the company.  
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cac:RegistrationAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/) / [cbc:CityName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cbc-CityName/) / [cac:Country](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/) / [cbc:IdentificationCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/cbc-IdentificationCode/) structure is used to tell in which city and country the company is officially registered in.  

**Example – Receiver Party segment**

```xml
<cac:ReceiverParty>
  <cbc:EndpointID schemeID="0216">003787654321</cbc:EndpointID>
  <cac:PartyIdentification>
    <cbc:ID schemeID="0088">5790000435944</cbc:ID>
  </cac:PartyIdentification>
  <cac:PostalAddress>
    <cbc:StreetName>Tie 1</cbc:StreetName>
    <cbc:CityName>Vantaa</cbc:CityName>
    <cbc:PostalZone>00100</cbc:PostalZone>
    <cac:Country>
      <cbc:IdentificationCode>FI</cbc:IdentificationCode>
    </cac:Country>
  </cac:PostalAddress>
  <cac:PartyLegalEntity>
    <cbc:RegistrationName>Työmaa OY</cbc:RegistrationName>
    <cbc:CompanyID schemeID="0212">8765432-1</cbc:CompanyID>
    <cac:RegistrationAddress>
      <cbc:CityName>Vantaa</cbc:CityName>
      <cac:Country>
        <cbc:IdentificationCode>FI</cbc:IdentificationCode>
      </cac:Country>
    </cac:RegistrationAddress>
  </cac:PartyLegalEntity>
</cac:ReceiverParty>
```

### 4.3 Catalogue line level

**Catalogue Line**

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) identifies each catalogue line.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:ActionCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ActionCode/) is used to tell if the catalogue line is **new**, **updated** or **deleted**.  
  - Possible values: “Add”, “Update” or “Delete”  
  - As stated in the *Catalogue Action code, line level (OpenPeppol)* codelist.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:OrderableIndicator](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-OrderableIndicator/) indicates if the catalogue line can be used for ordering.  
  - Can be used to tell if the item is **out of stock** or otherwise not ready to be ordered.  
  - Values: **true** or **false**, as stated in the *Boolean indicator (OpenPeppol)* codelist.  
  - Default value: **true** (catalogue line is active).  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:OrderableUnit](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-OrderableUnit/) describes the unit of measure for the orderable unit.  
  - Codelist **Recommendation 20**, including **Recommendation 21** codes (prefixed with X, UN/ECE) must be used.  
  - Unit of measure shortlist is defined in *Attachment A*.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:ContentUnitQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-ContentUnitQuantity/) is used if the orderable unit is a **package containing other units**.  
  - Tells how many units the package contains.  
  - [cbc:ContentUnitQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-ContentUnitQuantity/) `@unitCode` is mandatory.  
  - Use **Recommendation 20/21 (X-prefixed)** codes.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:OrderQuantityIncrementNumeric](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-OrderQuantityIncrementNumeric/) tells the increments which can be ordered.  
  - Example: Can half a product be ordered?  
  - For concrete elements, default = **1**.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:MinimumOrderQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-MinimumOrderQuantity/) and [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:MaximumOrderQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-MaximumOrderQuantity/) tell the minimum and maximum amount of items that can be ordered.  
  - `@unitCode` is mandatory.  
  - For unique items, use value **1**.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:WarrantyInformation](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-WarrantyInformation/) can be used for any warranty-related information.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cbc:PackLevelCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cbc-PackLevelCode/) conveys packaging information. Possible values ([GS1 7009 codelist](https://docs.peppol.eu/poacc/upgrade-3/codelist/GS17009/)):  
  - “CU” = Base Unit level  
  - “DU” = Pallet level  
  - “TU” = Case level  
  - “HN” = Handling Unit  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:LineValidityPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/) tree that includes [cbc:StartDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/cbc-StartDate/) and [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/cbc-EndDate/) is used to tell when the catalogue line is valid. The use case can, for example, be a promotional price that expires at a certain point or a product that is discontinued.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:ItemComparison](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-ItemComparison/) tree is used to tell the price per a quantity of unit of measure. For example, how much one kilogram or litre of the product costs. This is a non-mandatory element. In the precast concrete element case, this element is not necessary, as prices are not part of the typical use case. For other products this is a relevant element to be used.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:RequiredItemLocationQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/) tree is used to convey information about the price of the product or if a price is depentant on the lead time when the delivery needs to be made. For precast concrete elements, this element tree is not necessary, as the prices of the products are not part of the typical scenario. For other products, this is a relevant element to be used.  

If the element is used, then the [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:RequiredItemLocationQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/) / [cbc:LeadTimeMeasure](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/cbc-LeadTimeMeasure/) would indicate the time from when the order is placed until the item is available for delivery from the sellers' premises or at the applicable address specified for the price. @unitCode is mandatory to be used with values from the Recommendation 20, including Recommendation 21 codes - prefixed with X (UN/ECE) codelist. “DAY” = day, “HUR” = hour.  
[cbc:MinimumQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/cbc-MinimumQuantity/) and [cbc:MaximumQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/cbc-MaximumQuantity/) with mandatory @unitCodes from the same code list would indicate threshold and maximum quantities for the given price. [cac:ApplicableTerritoryAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/cac-ApplicableTerritoryAddress/) tree tells the address which the price is related to.  

- [cac:Price](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-RequiredItemLocationQuantity/cac-Price/) tree then tells the actual price per base unit and [cac:ValidityPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ValidityPeriod/) tree is used to indicate the validity period of the price.  

All the price elements are non-mandatory. A typical use case could only be that the price is the same regardless of the location. In that case the example XML could look like this:  

```xml
<cac:Price> 
  <cbc:PriceAmount currencyID="EUR">100</cbc:PriceAmount>
  <cbc:BaseQuantity unitCode="EA">1</cbc:BaseQuantity>
</cac:Price>
```

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) tree holds the information about the item in question.

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cbc:Description](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cbc-Description/) is used to provide general description of the item. For precast concrete this is “Yleisnimi”.

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cbc:PackQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cbc-PackQuantity/) is not used for precast concrete elements, but it is relevant for Make-to-Stock products. It is used to tell for example how many boxes are in a pallet. @unitCode is mandatory element with values from the Recommendation 20, including Recommendation 21 codes - prefixed with X (UN/ECE) codelist. Unit of measure shortlist related to this implementation guide is defined in attachment A.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/) is used for the name of the precast concrete element. For example *Väliseinä*.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:BuyersItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/cac-PartyIdentification/cbc-ID/) is used for GUID or UUID for the precast concrete element.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:ManufacturersItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-ManufacturersItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/cac-PartyIdentification/cbc-ID/) is used for the element code.

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:StandardItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-StandardItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ReceiverParty/cac-PartyIdentification/cbc-ID/) is used for GTIN or SGTIN of the precast concrete element. @schemeID is mandatory. Use value `0209` for SGTIN and `0160` for GTIN.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:ItemSpecificationDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-ItemSpecificationDocumentReference/) tree is used to provide additional documents about the product. In the precast concrete element use case these can for example be links to pictures of the precast production drawings. In [cbc:DocumentTypeCode]() use value `6` for Product specification report. 

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:OriginCountry]() / [cbc:IdentificationCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/cbc-IdentificationCode/) can be used to indicate the origin country of the product. Use value `FI` for Finland, `SE` for Sweden. The values must be according to Country codes (ISO 3166-1:Alpha2) codelist.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:TransactionConditions](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-TransactionConditions/) / [cbc:ActionCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ActionCode/) with value `CT` to indicate that the item is contracted. Another possibility is to use `NON_RETURNABLE` value to indicate a non-returnable item.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:ClassifiedTaxCategory]() is used for VAT category codes and percents. Not relevant for precast concrete element use case.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:AdditionalItemProperty](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-AdditionalItemProperty/) tree is used for multiple different types of information. A list of used terms is provided in the Attachment B *AdditionalItemProperty usage*. It is important to use the same names for the values to make sure that all parties know what is being referenced.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:ItemInstance](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-ItemInstance/) / [cbc:BestBeforeDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-ItemInstance/cbc-BestBeforeDate/) can be used if there is a need to indicate a best before date.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:ItemInstance](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-ItemInstance/) / [cbc:BestBeforeDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-ItemInstance/cbc-BestBeforeDate/) / [cac:LotIdentification]() / [cbc:LotNumberID]() is used for production lot identification.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:Certificate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Certificate/) tree can be used to provide information about a certificate related to the product, for example, an environmental certificate.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:Dimension](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/) tree is used for the dimensions of the product.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:Dimension](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/) / [cbc:AttributeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/cbc-AttributeID/) is a mandatory element which indicates which dimension is being referenced. Codelist *Measured attribute code (UNCL6313)* must be used. For example `LN` indicates length and `HT` height dimension.  

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:Dimension](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/) / [cbc:Measure](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/cbc-Measure/) with mandatory @unitCode is used for units of measure for the dimension in question. For length, height and width, use millimeters `MMT` and for weight kilograms `KGM`. 

- [cac:CatalogueLine](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/) / [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/) / [cac:Dimension](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cac-Dimension/) / [cbc:Description](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-Item/cbc-Description/) is used to give more detailed description if applicable. This can for example be a text value that indicates that the length in question is the *Gross length*, meaning the length in transport. Or it can say that it is about the *Net length*, which means that it is the length of the actual product without packaging. For dimension descriptions use values from **Attachment C** if applicable.  


---

## 5. Catalogue Response (T58)

The whole syntax of the **Peppol Catalogue Response transaction (T58)** is covered on the [Peppol website](https://peppol.org).  
This implementation guide does not add any additional elements to the syntax.  

All general Peppol rules must be followed.  
It is forbidden to use an element for some other purpose than what it was intended to be used for.  
Please refer to the general Peppol guidance if some element is not covered in this implementation guide.  

The catalogue response is a simple transaction whose purpose is just to tell the sender of the catalogue if their catalogue has been **accepted**, **rejected** or **acknowledged**.  

---

### 5.1 Document header level

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) identifies the catalogue response.  
- [cbc:IssueDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-IssueDate/) and [cbc:IssueTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-IssueTime/) are used to indicate the date and time of the issuance of the catalogue response.  
  - Only the issue date is mandatory.  
- [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) is a free text element that can be used to convey information relevant to the catalogue response that cannot be placed elsewhere.  

### 5.2 Parties
#### 5.2.1 Sender Party

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic Peppol address of the sender party.  
  - [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is mandatory  
  - For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**  

Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) values:

| [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) | schemeID | Notes |
|--------------------|----------|-------|
| 003712345678       | 0216     | SchemeID 0216 stands for Finnish EDI identifier (OVT code).<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| 6412345678901      | 0088     | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to identify the sender party.  
  - Identifier can be the **Business Identity Code** of the sender company  
  - Or it can be an internal identifier known by the sender and the receiver  
  - [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is not mandatory, but if the identifier is on the **ISO 6523 ICD list**, please use it  
  - Code for Business Identity Code for Finnish companies: `0212`  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is used for the **legal name** of the sender party.  

#### 5.2.2 Receiver Party


- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic Peppol address of the receiver party.  
  - [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is mandatory  
  - For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**  

Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) values:

| [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) | schemeID | Notes |
|--------------------|----------|-------|
| 003712345678       | 0216     | SchemeID 0216 stands for Finnish EDI identifier (OVT code).<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| 6412345678901      | 0088     | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to identify the receiver party.  
  - Identifier can be the **Business Identity Code** of the receiver company  
  - Or it can be an internal identifier known by the sender and the receiver  
  - [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is not mandatory, but if the identifier is on the **ISO 6523 ICD list**, please use it  
  - Code for Business Identity Code for Finnish companies: `0212`  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is used for the **legal name** of the receiver party.  

### 5.3 Document response

- [cac:Response]() / [cbc:ResponseCode]() is used to tell if the catalogue has been **accepted**, **rejected** or **acknowledged**.  
  - *Application Response type code (UNCL4343 Subset)* codelist must be used  
  - **AB = Message acknowledgement**  
  - **AP = Accepted**  
  - **RE = Rejected**  

**Referencing the original catalogue**

- [cac:DocumentReference]() / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used for the **original ID** of the catalogue that the response refers to.  
- [cbc:VersionID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-VersionID/) can be used if there have been prior updates to the catalogue.

---

## 6. Order (T01)

The whole syntax of the **Peppol Order transaction (T01)** is covered on the [Peppol website](https://peppol.org).  
This implementation guide does not add any additional elements to the syntax.  

All general Peppol rules must be followed. It is forbidden to use an element for some other purpose than what it is intended to be used for.  
Please refer to the general Peppol guidance if some element is not covered in this implementation guide.  

---

### 6.1 Document header level

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is the identifier of the order.  
- [cbc:SalesOrderID]() can be used to reference a sales order issued by the seller.  
- [cbc:IssueDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-IssueDate/) and [cbc:IssueTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-IssueTime/) are the date and time when the order is made.  
  - Dates must be formatted as **YYYY-MM-DD**  
  - Times as **HH:MM:SS**  
  - Only the date is mandatory  

- [cbc:OrderTypeCode]() is used to tell what type of order is being made.  
  - Values from the *Order type code (UNCL1001 subset)* list must be used  
  - Default value: **220 = Order**  
  - Other values can be used if agreed beforehand by the parties  

- [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) is used for information or notes that do not have any explicit place on the order message.  
- [cbc:DocumentCurrencyCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cbc-DocumentCurrencyCode/) tells the default currency of the order.  
  - Use `EUR` for Euros  
  - Values from the **ISO 4217 Currency codes** must be used  

- [cbc:CustomerReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-CustomerReference/) is used to reference the buyer of the products or services.  
  - Known also as Buyer Reference  
  - Repeated on the invoice  

- [cbc:AccountingCost](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cbc-AccountingCost/) is used by the buyer to specify a reference that should be repeated in e.g. invoice to enable the buyer to automatically book to the right project or account.  

- [cac:ValidityPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ValidityPeriod/) / [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/cbc-EndDate/) is used to tell the **end date** when the order is valid.  
  - The end date for the time period within which the seller must respond  
  - This is a **mandatory element**  

The order header level includes multiple references to different document types:

- [cac:QuotationDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-QuotationDocumentReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to reference quotations that the order is based on.  
- [cac:OrderDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OriginatorDocumentReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to reference a previous order that was rejected and a new order is issued.  
- [cac:OriginatorDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OriginatorDocumentReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to give a reference to the internal requisition on the buyer site on which the order is based.  
- [cac:CatalogueReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-CatalogueReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to reference the catalogue which the order is based on.  
  - This is especially important in the concrete element case  

Any additional document references can be made using the [cac:AdditionalDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-AdditionalDocumentReference/) tree.  
- A document can be attached or it can be referenced via an URI.  

- [cac:Contract](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Contract/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) references the contract the order is based on.  
- [cac:ProjectReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-ProjectReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is used to reference a project.  
  - In the concrete element case this is the **identifier of the construction site**  

### 6.2 Parties

#### 6.2.1 Buyer Customer Party

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic address of the buyer.  
  - [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/schemeID/) is mandatory  
  - For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**  

Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and  values:

| [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) | schemeID | Notes |
|--------------------|----------|-------|
| 003712345678       | 0216     | SchemeID 0216 stands for Finnish EDI identifier (OVT code).<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| 6412345678901      | 0088     | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) can contain the **GLN of the buyer**.  
  - is not mandatory for this field  
  - If the code is on the **ISO 6523 ICD list**, please use it  
  - Code for GLN: `0088`  

- [cac:PartyName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-SellerSupplierParty/cac-Party/cac-PartyName/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/) is the **trading name** of the party.  
  - It does not have to be an official name registered with the Company ID  

- [cac:PostalAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PostalAddress/) tree contains the **address of the buyer**.  
  - This is e.g. the HQ address, not the delivery address  

- [cac:PartyTaxScheme]() / [cbc:CompanyID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-CompanyID/) contains the buyer’s **VAT identification code** in international format.  
  - For Finnish companies: `FI` + Company ID (Y-tunnus) without the dash mark `-`  
  - [cbc:TaxScheme]() / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) should be `VAT`  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is the official legal name of the buyer.  
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:CompanyID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-CompanyID/) for Finnish companies is the **Business Identity Code**.  
  -  for Business Identity Code on the **ISO 6523 ICD list** is `0212`  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cac:RegistrationAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/) / [cbc:CityName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cbc-CityName/) is the **city** where the company is registered.  
  - [cac:Country](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/) / [cbc:IdentificationCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/cbc-IdentificationCode/) must also be used  
  - For Finland: `FI` (ISO 3166-1 Alpha-2)  

- [cac:Contact](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-BuyerCustomerParty/cac-Party/cac-Contact/) tree includes contact details of the buyer. Possible details:  
  - [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/)  
  - [cbc:Telephone](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-SellerSupplierParty/cac-Party/cac-Contact/cbc-Telephone/)  
  - [cbc:ElectronicMail](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-BuyerCustomerParty/cac-Party/cac-Contact/cbc-ElectronicMail/)  

#### 6.2.2 Seller Supplier Party

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic address of the seller.  
  -  is mandatory  
  - For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**  

Examples of [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) and  values:

| cbc:EndpointID     | schemeID | Notes |
|--------------------|----------|-------|
| `003712345678`     | `0216`   | SchemeID 0216 stands for Finnish EDI identifier (OVT code).<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| `6412345678901`    | `0088`    | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) can contain the **GLN of the seller**.  
  -  is not mandatory  
  - If the code is on the **ISO 6523 ICD list**, please use it  
  - Code for GLN: `0088`  

- [cac:PartyName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-SellerSupplierParty/cac-Party/cac-PartyName/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/) is the **trading name** of the seller.  
- [cac:PostalAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PostalAddress/) tree contains the **address of the seller**.  
  - This is e.g. the HQ address, not the delivery address  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-RegistrationName/) is the official legal name of the seller.  
- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cbc:CompanyID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cbc-CompanyID/) for Finnish companies is the **Business Identity Code**.  
  -  for Business Identity Code on the **ISO 6523 ICD list** is `0212`  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/) / [cac:RegistrationAddress](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/) / [cbc:CityName](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cbc-CityName/) is the **city** where the seller is registered.  
  - [cac:Country](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/) / [cbc:IdentificationCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cac-PartyLegalEntity/cac-RegistrationAddress/cac-Country/cbc-IdentificationCode/) must also be used  
  - For Finland: `FI`  

- [cac:Contact](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-BuyerCustomerParty/cac-Party/cac-Contact/) tree includes contact details of the seller. Possible details:  
  - [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/)  
  - [cbc:Telephone](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-SellerSupplierParty/cac-Party/cac-Contact/cbc-Telephone/)  
  - [cbc:ElectronicMail](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-BuyerCustomerParty/cac-Party/cac-Contact/cbc-ElectronicMail/)  

#### 6.2.3 Other Parties

- Originator Customer Party or Accounting Customer Party are **not covered** by this implementation guide.  


### 6.3 Delivery

*(Jos rivitasolla on osoite, käytetään sitä. Muuten voidaan käyttää otsikkoa)*  

The delivery information can be stated at the whole order level or on the order line level.  
- Use the order header level for **pre-packed-loads**  
- For others **non-pre-packed-loads** use the order line level  

- [cac:DeliveryLocation](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-DeliveryLocation/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is the identifier of the delivery address.  
  - This can be e.g. a **GLN** address of a construction site  
  - is not mandatory  
  - If you use GLN, the code for it is **0088**  
  - Codes from **ISO 6523 ICD list** must be used  

- [cac:DeliveryLocation](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-DeliveryLocation/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-Name/) is the **name** of the delivery location.  
  - E.g. the name of the construction site or a location inside it  

- [cac:DeliveryLocation](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-DeliveryLocation/) / [cac:Address](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-DeliveryLocation/cac-Address/) structure is used for the **delivery address**.  

- The [cac:RequestedDeliveryPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-RequestedDeliveryPeriod/) has:  
  - [cbc:StartDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartDate/)  
  - [cbc:StartTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartTime/)  
  - [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/cbc-EndDate/)  
  - [cbc:EndTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndTime/)  

  If the delivery period is not a range of days, but just one day, please add both the Start and End dates on the same day.  
  - Dates must be formatted as **DD-MM-YYYY**  
  - Times must be formatted as **HH:MM:SS**  

  For multiple delivery slots use the [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) since that functionality is not currently supported by **Peppol**.  

- [cac:DeliveryParty](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-DeliveryParty/) is not covered by this implementation guide as the buyer is always expected to be the one to whom the goods are delivered.  

>  $\color{red}{\textsf{Draft note:}}$ -> DeliveryParty / contact -osio hyödyllinen. Voidaan välittää toimituksen vastaanottajan yhteystiedot. (Buyer -osiossa käytännössä vain tilaajan yhteystiedot


- [cac:Shipment](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-Shipment/) / [cbc:ShippingPriorityLevelCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-Shipment/cbc-ShippingPriorityLevelCode/) can be used to indicate if a shipment is required to be made quickly.  
  - *Transport service priority code (UNCL4219)* codelist must be used  

- [cac:Shipment](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-Shipment/) / [cac:TransportHandlingUnit]() / [cbc:ShippingMarks]() is used for **SSCC information** that is printed on the transport handling unit.  
  - This is on the whole order level
  - Text to be written on shipping labels

- [cac:DeliveryTerms](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-DeliveryTerms/) structure is used for **Incoterms**.  

> [!IMPORTANT]
> Payment terms and monetary totals are not covered by this implementation guide as the **concrete element use case does not include prices**.

### 6.4 Order line level

- [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) is a free-text element that can be used for things that do not have an explicit place elsewhere in the order structure.  
  - This can, for example, be information about delivery time slots if there are multiple.  

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is the identifier of the order line.  

- [cbc:Quantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Quantity/) marks the quantity of items on the order line.  
  - `@unitCode` must be used.  
  - The most used units of measure are listed in *Attachment A*.  

- [cbc:PartialDeliveryIndicator](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cbc-PartialDeliveryIndicator/) is used to tell if the order can be delivered in multiple instances.  
  - The default value is **true**, meaning that it would be allowed.  
  - In the concrete element case, use **false**.  

- [cbc:AccountingCost](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cbc-AccountingCost/) is used for a reference that is wanted to be repeated on the invoice.  
  - This can be for example a reference to the instalment.  

- Use the [cac:Delivery](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Delivery/) structure on the order line level for concrete elements that are not part of pre-made-deliveries.  

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cbc-ID/) is the identifier of the delivery location.  
  - This can for example be a **GLN** of the construction site or a place inside of the construction site.  
  -  is not mandatory, but the code for GLN is **0088**.  
  - A request has been made to **OpenPeppol** to add also delivery address details on order line level. Currently they are not supported.  

- The [cac:RequestedDeliveryPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-Delivery/cac-RequestedDeliveryPeriod/) has:  
  - [cbc:StartDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartDate/)  
  - [cbc:StartTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartTime/)  
  - [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-CatalogueLine/cac-LineValidityPeriod/cbc-EndDate/)  
  - [cbc:EndTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndTime/)  

  If the delivery period is not a range of days, but just one day, please add both the Start and End dates on the same day.  
  - The dates must be formatted as **DD-MM-YYYY**  
  - The time must be formatted as **HH:MM:SS**  

  For multiple delivery slots, use the [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) since that functionality is not currently supported by **Peppol**.  


> [!IMPORTANT]
> Price details are not covered by this implementation guide, as prices are not part of the concrete element use case.



### 6.5 Item information on the order line
- [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/) / [cbc:Description](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cbc-Description/) is the **"General name"** of the precast concrete element.  
- [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cbc-Name/) is the **Type** of the precast concrete element.  
- [cac:BuyersItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/cbc-ID/) is the **GUID** of the concrete element.  
- [cac:ManufacturersItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-ManufacturersItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/cbc-ID/) is the **identifier including the type** of the precast concrete element provided by the manufacturer.  
- [cac:StandardItemIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-StandardItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/cbc-ID/) is the **GTIN** or **SGTIN** of the concrete element.  
  -  is mandatory.  
  - Code for **GTIN** is `0160` and for **SGTIN** is `0209`.  
  - Values from **[ISO 6523 ICD list](https://docs.peppol.eu/poacc/upgrade-3/codelist/ICD/)** must be used.  
- [cac:ItemSpecificationDocumentReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-StandardItemIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-ItemSpecificationDocumentReference/cbc-ID/) is used for referencing the **identifier of the drawing number**.  
- [cac:AdditionalItemProperty](https://docs.peppol.eu/poacc/upgrade-3/syntax/Order/cac-OrderLine/cac-LineItem/cac-Item/cac-AdditionalItemProperty/) structure is used for multiple different use cases.  
  - The list of possible things to be stated here are listed on *[Attachment B](#attachment-b-additionalitemproperty-usage)*.  
  - It is important to use the texts agreed on this implementation guide to make it possible for automating the handling of the information.

---

## 7. Order Response (T76)

The whole syntax of the **Peppol Order Response transaction (T76)** is covered on the [Peppol website](https://peppol.org).  
This implementation guide does not add any additional elements to the syntax.  

All general Peppol rules must be followed. It is forbidden to use an element for some other purpose than what it is intended to be used for.  
Please refer to the general Peppol guidance if some element is not covered in this implementation guide.  

---

### 7.1 Document header level

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-ID/) is used to identify the order response.  
- [cbc:SalesOrderID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-SalesOrderID/) is used to reference a sales order that is issued by the seller.  
- [cbc:IssueDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-IssueDate/) and [cbc:IssueTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-IssueTime/) are used to indicate the time and date when the order response is issued.  
  - Only the issue date is mandatory.  
  - The date must be formatted as **YYYY-MM-DD** and the time as **HH:MM:SS**.  

- [cbc:OrderResponseCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-OrderResponseCode/) indicates if the order has been **Accepted**, **Conditionally accepted**, **Rejected** or **Acknowledged**.  
  - The *Order Response type code (UNCL4343 Subset)* must be used.  
  - **AP = Accepted**  
  - **RE = Rejected**  
  - **CA = Conditionally accepted**  
  - **AB = Message acknowledgement**  

If codes **AP** or **RE** are used, no order response line level information is sent as the order has been accepted or rejected as a whole.  
If code **CA** or **AB** is used, all order response lines are sent.  

- [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) is a free text field that can be used to convey information that can not be stated elsewhere.  
  - This can for example be a reason for the rejection of the order.  

- [cbc:DocumentCurrencyCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-DocumentCurrencyCode/) tells the default currency of the order response.  
  - Values from the **ISO 4217 Currency codes** must be used.  
  - For Euros, use `EUR`.  

- [cbc:CustomerReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-CustomerReference/) is used for routing the transaction correctly in the purchasing system.  
  - The customer reference is defined by the buyer, but provided by the seller in the order response.  

- [cac:OrderReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderReference/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderReference/cbc-ID/) is used to reference the order that is being responded to.


### 7.2 Parties

#### Seller Supplier Party

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cbc-EndpointID/) is used to convey the electronic Peppol address of the Seller Party.  
  The [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cbc-EndpointID/schemeID/) is mandatory to be used with the EndpointID element.  
  For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**.  

Examples of `cbc:EndpointID` and  values:

| cbc:EndpointID     | schemeID | Notes                                                                                                                                                                                                                                                     |
|--------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `003712345678`     | `0216`   | SchemeID 0216 stands for Finnish EDI identifier (OVT code). OVT Code structure is:<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| `6412345678901`    | `0088`   | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1.                                                                                                                                                                               |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cac-PartyIdentification/cbc-ID/) can contain an internal ID understood by the buyer and/or seller.  
  This can be for example a **GLN** of the factory.  
  [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cbc-EndpointID/schemeID/) is not mandatory for this field.  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-SellerSupplierParty/cac-Party/cac-PartyLegalEntity/cbc-RegistrationName/) is the legal name of the seller.  

---

#### Buyer Customer Party

- [cbc:EndpointID](https://docs.peppol.eu/poacc/upgrade-3/syntax/Catalogue/cac-ProviderParty/cbc-EndpointID/) is used to convey the electronic Peppol address of the Buyer Party.  
  The [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cbc-EndpointID/schemeID/) is mandatory to be used with the EndpointID element.  
  For Finnish organisations the EndpointID is always an **OVT code** with scheme ID **0216**.  

Examples of `cbc:EndpointID` and  values:

| cbc:EndpointID | schemeID | Notes |
|----------------|----------|-------|
| `003712345678` | `0216`   | SchemeID 0216 stands for Finnish EDI identifier (OVT code). OVT Code structure is:<br>· `0037` is a fixed value<br>· Company ID (Y-tunnus) without the dash mark `-`<br>· Optional (up to 5) internal numbers or capital letters (A-Z) within the company |
| `6412345678901`| `0088`   | Scheme ID 0088 stands for GLN (Global Location Number) administered by GS1. |

- [cac:PartyIdentification](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/) / [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyIdentification/cbc-ID/) can contain an internal ID understood by the buyer and/or seller.  
  This can be for example a **GLN** of the factory.  
  [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cbc-EndpointID/schemeID/) is not mandatory for this field.  

- [cac:PartyLegalEntity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyLegalEntity/) / [cbc:RegistrationName](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-BuyerCustomerParty/cac-Party/cac-PartyLegalEntity/cbc-RegistrationName/) is the legal name of the buyer.


### 7.3 Delivery

On the order response the seller can confirm the delivery period for the order on the [cac:Delivery](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/) / [cac:PromisedDeliveryPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/) tree.  

The promised delivery period has:  
- [cbc:StartDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartDate/)  
- [cbc:StartTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartTime/)  
- [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndDate/)  
- [cbc:EndTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndTime/)  

If the delivery period is not a range of days, but just one day, please add both Start and End date on the same day.  
The dates must be formatted as **DD-MM-YYYY** and the time as **HH:MM:SS**.  

The delivery period can be for the order header level or on order response line. For pre-packed-loads use the document level delivery periods.  

If there are multiple delivery time slots, use [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-Note/) element for those as multiple delivery slots are not currently supported by **Peppol**.

### 7.4 Order response lines

The lines are only part of the order response if the [cbc:OrderResponseCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cbc-OrderResponseCode/) is **AB = Message acknowledgement** or **CA = Conditionally accepted**.  
On **AP = Accepted** or **RE = Rejected** codes no order response lines are sent as part of the order response.

- [cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-ID/) is the ID of the order response line.  
- [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Note/) can be used to convey information that does not have explicit place in the order response transaction such as clarifications for the suppliers decision on the line.  
- [cbc:LineStatusCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-LineStatusCode/) is used to tell if the order line has been accepted or changed in any way. A code list **[Action code (UNCL1229)](https://docs.peppol.eu/poacc/upgrade-3/codelist/UNCL1229/)** must be used. The possible values are:  
  `1` Order line is added  
  `3` Changed  
  `5` Accepted without amendment  
  `7` Not accepted  
  `42` Already delivered  

- [cbc:Quantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Quantity/) describes the quantity of items that the supplier promises to deliver. For Quantity, unit of measure must be provided in [@unitCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Quantity/unitCode/) element. See *Attachment A* for the usage of [@unitCode](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Quantity/unitCode/).  
- [cbc:MaximumBackorderQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-MaximumBackorderQuantity/) must be agreed by the business parties if backorder is allowed. If it is allowed, this element is used to tell the quantity of the goods that will be delivered at a later date.  

On the order response line level the seller can confirm the delivery period for the order on the [cac:Delivery](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/) / [cac:PromisedDeliveryPeriod](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/cac-PromisedDeliveryPeriod/) tree.  
The promised delivery period has:  
- [cbc:StartDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartDate/)
- [cbc:StartTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-StartTime/) 
- [cbc:EndDate](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndDate/)
- [cbc:EndTime](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Delivery/cac-PromisedDeliveryPeriod/cbc-EndTime/)  

If the delivery period is not a range of days, but just one day, please add both Start and End date on the same day.  
The dates must be formatted as **DD-MM-YYYY** and the time as **HH:MM:SS**.  

The delivery period can be for the whole order or on order response line. For non-pre-packed-loads use the order response line level.  
If there are multiple delivery time slots, use [cbc:Note](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cbc-Note/) element for those as multiple delivery slots are not currently supported by **Peppol** ([Peppol official site](https://peppol.org)).

The price information is not used in the concrete element case, but for other products it can be used in the [cac:Price](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Price/) structure by using:  
- [cbc:PriceAmount](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Price/cbc-PriceAmount/)  
- [cbc:BaseQuantity](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Price/cbc-BaseQuantity/)  

Compared to the order transaction, the item details are more restricted in the order response.  

* [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/) / [cbc:Name](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/cbc-Name/) contains the item name is used for the name of the precast concrete element. For example **Väliseinä**.  
* [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/) / [cac:BuyersItemIdentification/cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/cac-BuyersItemIdentification/) is used for **GUID** or **UUID** for the precast concrete element.  
* [cac:Item](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/) / [cac:StandardItemIdentification/cbc:ID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/cac-StandardItemIdentification/) is used for **GTIN** or **SGTIN** of the precast concrete element. [@schemeID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-LineItem/cac-Item/cac-StandardItemIdentification/cbc-ID/schemeID/) is mandatory.  
  - Use value `0209` for **SGTIN**  
  - Use value `0160` for **GTIN**  

Usage of [cac:SellerSubstitutedLineItem](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-SellerSubstitutedLineItem/) is not covered by this implementation guide.  

[cac:OrderLineReference](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-OrderLineReference/) / [cbc:LineID](https://docs.peppol.eu/poacc/upgrade-3/syntax/OrderResponse/cac-OrderLine/cac-OrderLineReference/cbc-LineID/) is mandatory to be used. It links the order response line to the order line.




---

## Attachment A: Quantity/@unitCode usage
In Peppol, the unit of measure codes must follow UN/ECE’s code list Recommendation 20, including [Recommendation 21 codes – prefixed with X (UN/ECE)](https://docs.peppol.eu/poacc/upgrade-3/codelist/UNECERec20/). As this list is very large, this following subset of that list are the values that are recommended to be used in the concrete element supply chain.

For possible expansion of this list, [see short list in Sweden first.](https://skr.se/download/18.427140af179361c4e462c7c8/1620639375793/SFTI%20Shortlist_UnitsOfMeasureCodes_20191017.pdf)

>  $\color{red}{\textsf{Draft note:}}$ *Use **UN/ECE Recommendation 20** (including **Rec 21** codes, prefixed with **X**) for unit codes. The following shortlist is recommended for the concrete element supply chain. For possible expansion, consider the Swedish shortlist first.*

| cbc:Quantity/@unitCode   | Description in English | Description in Finnish  | Description in Swedish  | Notes                                                                                                                    |
| -------------------------- | ---------------------- | ----------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `C62`                      | one                    | kappale                 | styck                   | Use code value `EA` instead of `C62` when writing messages.<br> <br> `C62` should be understood when receiving messages. |
| `H87`                      | piece                  | kappale                 | styck                   | Use `EA` when *writing* messages; `H87` *should be understood* when receiving.                                           |
| `EA`                       | each                   | kappale                 | styck                   | Preferred code for messages.                                                                                             |
| `KGM`                      | kilogram               | kilogramma              | kilogram                |                                                                                                                          |
| `MTK`                      | square metre           | neliömetri              | kvadratmeter            |                                                                                                                          |
| `MTQ`                      | cubic metre            | kuutiometri             | kubikmeter              |                                                                                                                          |
| `MTR`                      | metre                  | metri                   | meter                   |                                                                                                                          |

---

## Attachment B: AdditionalItemProperty usage

>  $\color{red}{\textsf{Draft note:}}$ *Use the following **`cac:AdditionalItemProperty`** names and values consistently to enable automated processing. (Examples shown where available.)*

| Cbc:Name                                  | Cbc:Value (Example)                                                                                        | Description                                           | Description (Finnish)          |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|--------------------------------|
|                                           |                                                                                                            | $\color{red}{\textsf{Building block name}}$           | Rakennuslohkon nimi            |
|                                           |                                                                                                            | $\color{red}{\textsf{Floor name}}$                    | Kerroksen nimi                 |
|                                           |                                                                                                            | $\color{red}{\textsf{Installation block 1}}$          | Asennuslohko 1                 |
|                                           |                                                                                                            | $\color{red}{\textsf{Installation block 2}}$          | Asennuslohko 2                 |
|                                           |                                                                                                            | $\color{red}{\textsf{Installation block 3}}$          | Asennuslohko 3                 |
|                                           |                                                                                                            | $\color{red}{\textsf{Stairwell}}$                     | Rappu                          |
|                                           |                                                                                                            | $\color{red}{\textsf{Space/Room}}$                    | Tila                           |
|                                           |                                                                                                            | $\color{red}{\textsf{Planned factory casting date}}$  | Suunniteltu tehtaan valupäivä  |
|                                           |                                                                                                            |                                                       | Suunniteltu toimituspäivä      |
|                                           |                                                                                                            |                                                       | MTO – Variation Number         |
|                                           |                                                                                                            | Data carrier                                          | RFID:n tunnus                  |
|                                           |                                                                                                            | Co2 / ESG                                             | Hiilidioksidiekvivalentti      |
|                                           | `BETONILEMENTTI` <br> `PAIKALLAVALU` <br> `TERÄSKOKOONPANO` <br> `PUUKOKOONPANO` <br> `MUU KOKOONPANO`     | $\color{red}{\textsf{Assembly type}}$                 | Kokoonpanon tyyppi             |
|                                           |  `True` / `False`                                                                                          |                                                       | Kääntökivi                     |




>  $\color{red}{\textsf{Draft note:}}$ *Fill in exact descriptions and controlled values as agreed by the parties. Keep naming **identical** across documents.*

---

## Attachment C: Dimension descriptions

| AttributeID     | Explanation      | Unit of measure | Description (Finnish) |
| --------------- | ---------------- | --------------- | --------------------- |
| `HT`            | Height dimension | MMT             | Maksimikorkeus        |
| `HT`            | Height dimension | MMT             | Betoniosan korkeus    |
| `WD`            | Width dimension  | MMT             | Maksimi paksuus       |
| `WD`            | Width dimension  | MMT             | Betoniosan paksuus    |
| `LN`            | Length           | MMT             | Maksimipituus         |
| `LN`            | Length           | MMT             | Betoniosan pituus     |
| `GW`            | Gross Weight     | KGM             | Bruttopaino           |

---

## Example files

Example XML files can be downloaded **here**. The examples include **X** scenarios.

> *(Insert links or references to the example files repository/location.)*
