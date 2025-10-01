# Peppol implementation guide for the construction industry (Engineer‑to‑Order precast concrete)

This document provides guidance for implementing **Peppol Catalogue** and **Ordering/Order Response** (plus Advanced Despatch/Receipt Advice placeholder) for the Finnish construction industry, with a focus on **engineer‑to‑order (ETO) precast concrete**.

> **Note:** This guide does not change general Peppol BIS rules. When something is not stated here, refer to the official Peppol BIS documentation (e.g., rules for currencies, dates, times, decimals, code lists). It is forbidden to repurpose elements for uses other than their intended meaning.

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

**Peppol** is a network and set of specifications for structured electronic business transactions. It uses the *four‑corner model*, allowing end users to choose any Access Point (service provider) and connect once to exchange documents with all other end users on the network.

Peppol is **not** a procurement system, portal, or ERP. It enables interconnection of systems and provides a shared digital language globally.

This implementation guide focuses on **data needs specific to Finnish ETO precast concrete**. General Peppol rules still apply; consult the Peppol BIS documentation for anything not covered here (e.g., currencies, dates, times, decimals, code lists).

---

## 2. Change management

This implementation guide was created jointly by **BETK** project representatives and the **Peppol Authority of Finland (State Treasury)**.

For questions or updates, contact **State Treasury**: `peppol@valtiokonttori.fi`. The State Treasury will convene relevant industry representatives for updates.

---

## 3. Covered Business Interoperability Specifications

This guide covers three Peppol BIS processes:

* **BIS Catalogue with response**
* **BIS Ordering**
* **BIS Advanced Despatch Advice with Receipt Advice**

### 3.1 BIS Catalogue with response

Covers *Catalogue* and *Catalogue Response* transactions. The receiver **must** respond to each Catalogue with a Catalogue Response (received/accepted/rejected).

> Peppol transaction syntaxes: **T19** (Catalogue), **T58** (Catalogue Response).


### 3.2 BIS Ordering

Covers *Order* and *Order Response* transactions. The supplier **must** respond to each Order with an Order Response (received/accepted/declined/partially accepted). Delivery dates can be added to the response.

> Peppol transaction syntaxes: **T01** (Order), **T76** (Order Response).

### 3.3 BIS Advanced Despatch Advice with Receipt Advice

*Tämä täytetään lomakauden jälkeen.*

---

## 4. Catalogue (T19) – implementation details

The full syntax is defined on the Peppol website. This guide adds no new elements—follow all general Peppol rules and intended element semantics.

### 4.1 Document header level

* **`cbc:ID`** – Catalogue identifier (mandatory).
* **`cbc:ActionCode`** – First issue/replacement/line update/deletion. Use values from *Catalogue Action code, header level (OpenPeppol)*. If omitted, the catalogue fully replaces the source catalogue.
* **`cbc:Name`** – Optional human‑readable catalogue name.
* **`cbc:IssueDate`** – Catalogue issue date (YYYY‑MM‑DD) (mandatory).
* **`cbc:VersionID`** – Version tracking for updates.
* **`cac:ValidityPeriod`** – Time period during which the catalogue is valid (mandatory). Use `cbc:StartDate`, `cbc:EndDate` (dates) and time as HH:MM:SS where applicable.
* **`cac:ReferencedContract`** – Reference to the contract; invoicing terms are agreed in the contract.
* **`cac:SourceCatalogueReference/cbc:ID`** – Reference to previous version; important for updates and change tracking.
* **`cac:TradingTerms/cbc:Information`** – General payment conditions.

### 4.2 Parties

> **Electronic addresses (`cbc:EndpointID`)**
>
> Use the mandatory `@schemeID` with EndpointID. For Finnish organisations, EndpointID is usually **OVT** with scheme **0216**. GLN is also possible with scheme **0088**.

| `cbc:EndpointID` | `@schemeID` | Notes                                                                                                                            |
| ---------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `003712345678`   | `0216`      | Finnish EDI identifier (OVT). Structure: `0037` (fixed) + Business ID (Y‑tunnus, no dash) + optional 1–5 internal alphanumerics. |
| `6412345678901`  | `0088`      | GLN (Global Location Number), administered by GS1.                                                                               |

#### 4.2.1 Provider Party (seller)

* **`cac:ProviderParty`** issues the catalogue and acts as the seller. (*Seller Supplier Party* is not applicable: in this use case the seller is always the issuer.)
* **`cbc:EndpointID`** – Seller’s Peppol address with `@schemeID` (mandatory).
* **`cac:PartyIdentification/cbc:ID`** – Internal ID understood by buyer and/or seller (e.g., factory GLN). `@schemeID` optional.
* **`cac:PostalAddress`** – Company address (e.g., HQ), *not* delivery address.
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Official company name.
* **`cac:PartyLegalEntity/cbc:CompanyID`** – Business Identity Code (Y‑tunnus). If using ISO 6523 ICD, scheme `0212` for Finnish Business Identity Code.
* **`cac:PartyLegalEntity/cac:RegistrationAddress`** – City and country of registration (`cbc:CityName`; `cac:Country/cbc:IdentificationCode`).

**Example – Provider Party**

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

* **`cac:ReceiverParty`** receives the catalogue and acts as the buyer. (*Buyer Supplier Party* is not applicable: the buyer is always the receiver.)
* **`cbc:EndpointID`** – Buyer’s Peppol address with `@schemeID` (mandatory).
* **`cac:PartyIdentification/cbc:ID`** – Internal ID (e.g., construction site GLN). `@schemeID` optional.
* **`cac:PostalAddress`** – Company (HQ) address, not delivery address.
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Official company name.
* **`cac:PartyLegalEntity/cbc:CompanyID`** – Business Identity Code (Y‑tunnus).
* **`cac:PartyLegalEntity/cac:RegistrationAddress`** – Registration city and country.

**Example – Receiver Party**

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

* **`cac:CatalogueLine/cbc:ID`** – Identifier of the catalogue line.
* **`cac:CatalogueLine/cbc:ActionCode`** – `Add`, `Update`, `Delete` (Catalogue Action code, line level – OpenPeppol).
* **`cac:CatalogueLine/cbc:OrderableIndicator`** – Whether the line is orderable (`true`/`false`, default `true`; Boolean indicator – OpenPeppol).
* **`cac:CatalogueLine/cbc:OrderableUnit`** – Unit of measure for the orderable unit. Use **UN/ECE Rec 20/21 (prefixed X)**. See [Attachment A](#attachment-a-quantityunitcode-usage) for shortlist.
* **`cac:CatalogueLine/cbc:ContentUnitQuantity`** – Quantity inside an orderable package; `@unitCode` mandatory (UN/ECE Rec 20/21). See Attachment A.
* **`cac:CatalogueLine/cbc:OrderQuantityIncrementNumeric`** – Order increments (default 1 for concrete elements).
* **`cac:CatalogueLine/cbc:MinimumOrderQuantity`**, **`.../cbc:MaximumOrderQuantity`** – Minimum/maximum orderable quantities; `@unitCode` mandatory. For unique items use value `1`.
* **`cac:CatalogueLine/cbc:WarrantyInformation`** – Warranty information (optional).
* **`cac:CatalogueLine/cbc:PackLevelCode`** – Packaging level: `CU` (Base Unit), `DU` (Pallet), `TU` (Case), `HN` (Handling Unit); *GS1 7009* (mandatory codelist).
* **`cac:CatalogueLine/cac:LineValidityPeriod`** – Validity period (`cbc:StartDate`, `cbc:EndDate`). Use for promotional prices, discontinuations, etc.
* **`cac:CatalogueLine/cac:ItemComparison`** – Price per quantity (optional; typically not used for precast elements).
* **`cac:CatalogueLine/cac:RequiredItemLocationQuantity`** – Price and lead‑time dependent information (optional; typically not used for precast elements).

  * **`.../cbc:LeadTimeMeasure`** – Time from order to availability; `@unitCode` mandatory (UN/ECE Rec 20/21), e.g., `DAY`, `HUR`.
  * **`cbc:MinimumQuantity`**, **`cbc:MaximumQuantity`** – Thresholds for the price; `@unitCode` mandatory.
  * **`cac:ApplicableTerritoryAddress`** – Address to which the price applies.
  * **`cac:Price`** – Price per base unit; **`cbc:PriceAmount`** and **`cbc:BaseQuantity`**; **`cac:ValidityPeriod`** for price validity.

**Simple price example**

```xml
<cac:Price>
  <cbc:PriceAmount currencyID="EUR">100</cbc:PriceAmount>
  <cbc:BaseQuantity unitCode="EA">1</cbc:BaseQuantity>
</cac:Price>
```

**Item information (`cac:Item`)**

* **`cbc:Description`** – General description (precast: *Yleisnimi*).
* **`cbc:PackQuantity`** – Not used for precast elements (used for MTS items). `@unitCode` mandatory (UN/ECE Rec 20/21). See Attachment A.
* **`cbc:Name`** – Item name (e.g., *Väliseinä* for precast element type).
* **`cac:BuyersItemIdentification/cbc:ID`** – GUID/UUID for the element.
* **`cac:ManufacturersItemIdentification/cbc:ID`** – Element code.
* **`cac:StandardItemIdentification/cbc:ID`** – GTIN or SGTIN. `@schemeID` mandatory: `0160` (GTIN), `0209` (SGTIN).
* **`cac:ItemSpecificationDocumentReference`** – Additional documents (e.g., links to production drawings). Use `cbc:DocumentTypeCode` value **`6`** (Product specification report).
* **`cac:OriginCountry/cbc:IdentificationCode`** – Origin country (`FI`, `SE`; ISO 3166‑1 alpha‑2).
* **`cac:TransactionConditions/cbc:ActionCode`** – `CT` to indicate contracted item; `NON_RETURNABLE` for non‑returnable.
* **`cac:ClassifiedTaxCategory`** – VAT category (not relevant for precast use case).
* **`cac:AdditionalItemProperty`** – Multiple properties; see [Attachment B](#attachment-b-additionalitemproperty-usage). Use agreed names consistently.
* **`cac:ItemInstance/cbc:BestBeforeDate`** – Best before date (if applicable); **`.../cac:LotIdentification/cbc:LotNumberID`** for lot ID.
* **`cac:Certificate`** – Certificate info (e.g., environmental).
* **`cac:Dimension`** – Dimensions of the product:

  * **`cbc:AttributeID`** (mandatory) – Attribute code from *UNCL6313* (e.g., `LN` length, `HT` height).
  * **`cbc:Measure`** with mandatory `@unitCode` – Use `MMT` (mm) for length/height/width; `KGM` for weight.
  * **`cbc:Description`** – Optional detail (e.g., whether length is gross/net). Use values from [Attachment C](#attachment-c-dimension-descriptions) where applicable.

---

## 5. Catalogue Response (T58)

A simple transaction to inform the sender whether their catalogue has been **accepted**, **rejected**, or **acknowledged**.

### 5.1 Document header level

* **`cbc:ID`** – Identifier of the catalogue response.
* **`cbc:IssueDate`**, **`cbc:IssueTime`** – Date (mandatory) and time of issuance.
* **`cbc:Note`** – Free text for additional info not placed elsewhere.

### 5.2 Parties

#### 5.2.1 Sender Party

* **`cbc:EndpointID`** – Sender’s Peppol address with `@schemeID` (mandatory). See the table in [4.2 Parties](#42-parties).
* **`cac:PartyIdentification/cbc:ID`** – Identifies the sender (e.g., Business Identity Code or internal ID). `@schemeID` optional; for Finnish BIC use `0212`.
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Legal name of the sender.

#### 5.2.2 Receiver Party

* **`cbc:EndpointID`** – Receiver’s Peppol address with `@schemeID` (mandatory). See the table in [4.2 Parties](#42-parties).
* **`cac:PartyIdentification/cbc:ID`** – Identifies the receiver (e.g., Business Identity Code or internal ID). `@schemeID` optional; for Finnish BIC use `0212`.
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Legal name of the receiver.

### 5.3 Document response

* **`cac:Response/cbc:ResponseCode`** – Use *Application Response type code (UNCL4343 subset)*: `AB` (Acknowledgement), `AP` (Accepted), `RE` (Rejected).

### 5.4 Referencing the original catalogue

* **`cac:DocumentReference/cbc:ID`** – Original catalogue ID being responded to.
* **`cbc:VersionID`** – If prior updates exist.

---

## 6. Order (T01)

The full syntax is on the Peppol website. This guide adds no new elements—follow all Peppol rules.

### 6.1 Document header level

* **`cbc:ID`** – Identifier of the order.
* **`cbc:SalesOrderID`** – Reference to the seller’s sales order (optional).
* **`cbc:IssueDate`**, **`cbc:IssueTime`** – Order date (mandatory) and time. Date format **YYYY‑MM‑DD**; time **HH:MM:SS**.
* **`cbc:OrderTypeCode`** – Order type from *UNCL1001 subset*. Default **220** (Order). Others by prior agreement.
* **`cbc:Note`** – Free text for information without explicit place.
* **`cbc:DocumentCurrencyCode`** – Default currency (ISO 4217), e.g., **EUR**.
* **`cbc:CustomerReference`** – Buyer reference (appears on invoice).
* **`cbc:AccountingCost`** – Buyer’s reference for automated booking (project/account), to be repeated in invoice.
* **`cac:ValidityPeriod/cbc:EndDate`** – End date by which the seller must respond (mandatory).

**References**

* **`cac:QuotationDocumentReference/cbc:ID`** – Quotation referenced.
* **`cac:OrderDocumentReference/cbc:ID`** – Previous (rejected) order being replaced.
* **`cac:OriginatorDocumentReference/cbc:ID`** – Buyer’s internal requisition.
* **`cac:CatalogueReference/cbc:ID`** – Catalogue referenced (especially important for precast elements).
* **`cac:AdditionalDocumentReference`** – Attach document or reference via URI.
* **`cac:Contract/cbc:ID`** – Contract reference.
* **`cac:ProjectReference/cbc:ID`** – Project/site identifier (construction site ID in precast case).

### 6.2 Parties

#### 6.2.1 Buyer Customer Party

* **`cbc:EndpointID`** – Buyer’s electronic address with `@schemeID` (mandatory; typically OVT `0216`, or GLN `0088`).
* **`cac:PartyIdentification/cbc:ID`** – Buyer GLN (optional `@schemeID`; for GLN use `0088`).
* **`cac:PartyName/cbc:Name`** – Trading name (not necessarily official name).
* **`cac:PostalAddress`** – Buyer address (HQ, not delivery).
* **`cac:PartyTaxScheme/cbc:CompanyID`** – VAT ID (Finland: `FI` + Business ID without dash). `cac:TaxScheme/cbc:ID` should be `VAT`.
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Official legal name.
* **`cac:PartyLegalEntity/cbc:CompanyID`** – Business Identity Code (Finland scheme `0212`).
* **`cac:PartyLegalEntity/cac:RegistrationAddress/cbc:CityName`** and **`.../cac:Country/cbc:IdentificationCode`** (e.g., `FI`).
* **`cac:Contact`** – Contact details: `cbc:Name`, `cbc:Telephone`, `cbc:ElectronicMail`.

#### 6.2.2 Seller Supplier Party

* **`cbc:EndpointID`** – Seller’s electronic address with `@schemeID` (mandatory; typically OVT `0216`, or GLN `0088`).
* **`cac:PartyIdentification/cbc:ID`** – Seller GLN (optional `@schemeID`; for GLN use `0088`).
* **`cac:PartyName/cbc:Name`** – Trading name.
* **`cac:PostalAddress`** – Seller address (HQ, not delivery).
* **`cac:PartyLegalEntity/cbc:RegistrationName`** – Official legal name.
* **`cac:PartyLegalEntity/cbc:CompanyID`** – Business Identity Code (Finland scheme `0212`).
* **`cac:PartyLegalEntity/cac:RegistrationAddress`** – Registration city and country (`FI`).
* **`cac:Contact`** – Contact details: `cbc:Name`, `cbc:Telephone`, `cbc:ElectronicMail`.

> *Originator Customer Party* and *Accounting Customer Party* are not covered by this guide.

### 6.3 Delivery

*(“Jos rivitasolla on osoite, käytetään sitä. Muuten voidaan käyttää otsikkoa.”)*

Delivery can be stated at **order (header)** level or **order line** level.

* Use **header level** for **pre‑packed loads**.
* Use **line level** for **non‑pre‑packed loads**.

**Header‑level delivery**

* **`cac:DeliveryLocation/cbc:ID`** – Identifier of the delivery address (e.g., construction site GLN). `@schemeID` optional; for GLN use `0088` (ISO 6523 ICD codes).
* **`cac:DeliveryLocation/cbc:Name`** – Name of the delivery location (site name or sub‑location).
* **`cac:DeliveryLocation/cac:Address`** – Delivery address structure.
* **`cac:RequestedDeliveryPeriod`** – `cbc:StartDate`, `cbc:StartTime`, `cbc:EndDate`, `cbc:EndTime`. If it is a single day, set Start and End to the same date. **Dates:** `DD‑MM‑YYYY`; **Time:** `HH:MM:SS`. For multiple delivery slots, use `cbc:Note` (Peppol doesn’t currently support multiple slots).
* **`cac:DeliveryParty`** – Not covered (buyer is expected to be the delivery recipient).
* **`cac:Shipment/cbc:ShippingPriorityLevelCode`** – Priority (use *UNCL4219* Transport service priority code).
* **`cac:Shipment/cac:TransportHandlingUnit/cbc:ShippingMarks`** – SSCC printed on the handling unit (header level).
* **`cac:DeliveryTerms`** – Incoterms.

*Payment terms and monetary totals are not covered (precast use case excludes prices).*

### 6.4 Order line level

* **`cbc:Note`** – Free text (e.g., multiple delivery time slots if needed).
* **`cbc:ID`** – Identifier of the order line.
* **`cbc:Quantity`** – Quantity ordered. `@unitCode` **mandatory** (see Attachment A for common units).
* **`cbc:PartialDeliveryIndicator`** – Whether partial deliveries are allowed. Default `true`; for precast, use `false`.
* **`cbc:AccountingCost`** – Reference to be repeated on invoice (e.g., instalment reference).
* **`cac:Delivery`** – Use line‑level delivery for elements not part of pre‑made deliveries.

  * **`cbc:ID`** – Delivery location identifier (e.g., site GLN or internal sub‑location). `@schemeID` optional (`0088` for GLN). *Address details at line level are currently not supported; a request has been made to OpenPeppol to add them.*
  * **`cac:RequestedDeliveryPeriod`** – Same rules as header level (dates `DD‑MM‑YYYY`; time `HH:MM:SS`; single day = same Start/End; multiple slots via `cbc:Note`).

*Price details are not covered for precast.*

### 6.5 Item information on the order line

* **`cac:Item/cbc:Description`** – “General name” of the precast element.
* **`cac:Item/cbc:Name`** – Type of the precast element.
* **`cac:BuyersItemIdentification/cbc:ID`** – GUID of the element.
* **`cac:ManufacturersItemIdentification/cbc:ID`** – Identifier including element type provided by manufacturer.
* **`cac:StandardItemIdentification/cbc:ID`** – GTIN (`0160`) or SGTIN (`0209`) with mandatory `@schemeID` (ISO 6523 ICD list).
* **`cac:ItemSpecificationDocumentReference/cbc:ID`** – Identifier of the drawing number.
* **`cac:AdditionalItemProperty`** – Multiple uses; see [Attachment B](#attachment-b-additionalitemproperty-usage). Use the agreed texts to enable automation.

---

## 7. Order Response (T76)

The full syntax is on the Peppol website. This guide adds no new elements—follow all Peppol rules.

### 7.1 Document header level

* **`cbc:ID`** – Identifier of the order response.
* **`cbc:SalesOrderID`** – Seller’s sales order reference.
* **`cbc:IssueDate`**, **`cbc:IssueTime`** – Issue date (mandatory) and time (YYYY‑MM‑DD; HH:MM:SS).
* **`cbc:OrderResponseCode`** – Use *UNCL4343 subset*: `AP` (Accepted), `RE` (Rejected), `CA` (Conditionally accepted), `AB` (Message acknowledgement).

  * `AP`/`RE`: No line‑level information (whole order accepted/rejected).
  * `CA`/`AB`: All order response lines are sent.
* **`cbc:Note`** – Free text (e.g., reason for rejection).
* **`cbc:DocumentCurrencyCode`** – ISO 4217 (e.g., `EUR`).
* **`cbc:CustomerReference`** – For routing in purchasing system (defined by buyer, provided by seller in response).
* **`cac:OrderReference/cbc:ID`** – Reference to the original order.

### 7.2 Parties

* **Seller Supplier Party**

  * **`cbc:EndpointID`** with `@schemeID` (mandatory; typically OVT `0216` or GLN `0088`).
  * **`cac:PartyIdentification/cbc:ID`** – Internal ID (e.g., factory GLN). `@schemeID` optional.
  * **`cac:PartyLegalEntity/cbc:RegistrationName`** – Legal name.
* **Buyer Customer Party**

  * **`cbc:EndpointID`** with `@schemeID` (mandatory; typically OVT `0216` or GLN `0088`).
  * **`cac:PartyIdentification/cbc:ID`** – Internal ID. `@schemeID` optional.
  * **`cac:PartyLegalEntity/cbc:RegistrationName`** – Legal name.

### 7.3 Delivery

* **`cac:Delivery/cac:PromisedDeliveryPeriod`** – Confirmed delivery period: `cbc:StartDate`, `cbc:StartTime`, `cbc:EndDate`, `cbc:EndTime`. Single day = same Start/End. Format `DD‑MM‑YYYY` and `HH:MM:SS`.

  * Can be at **document level** (use for pre‑packed loads) or **line level** (use for non‑pre‑packed loads).
  * Multiple time slots via `cbc:Note` (multiple slots not currently supported in Peppol structures).

### 7.4 Order response lines

* **Included only when `cbc:OrderResponseCode` = `AB` (acknowledged) or `CA` (conditionally accepted).**
* **`cbc:ID`** – Order response line ID.
* **`cbc:Note`** – Additional information (e.g., clarification of supplier’s decision).
* **`cbc:LineStatusCode`** – Use *UNCL1229 Action code*:

  * `1` Added
  * `3` Changed
  * `5` Accepted without amendment
  * `7` Not accepted
  * `42` Already delivered
* **`cbc:Quantity`** – Quantity supplier promises to deliver; `@unitCode` mandatory (see Attachment A).
* **`cbc:MaximumBackorderQuantity`** – If backorder allowed by agreement, state quantity to be delivered later.
* **`cac:Delivery/cac:PromisedDeliveryPeriod`** – Confirmed period (see formats above). Prefer **line level** for non‑pre‑packed loads.
* **`cac:Price`** – Not used in precast case; for other products, use `cbc:PriceAmount` and `cbc:BaseQuantity`.
* **Item details (restricted vs Order)**

  * **`cac:Item/cbc:Name`** – Element name (e.g., *Väliseinä*).
  * **`cac:Item/cac:BuyersItemIdentification/cbc:ID`** – GUID/UUID.
  * **`cac:Item/cac:StandardItemIdentification/cbc:ID`** – GTIN/SGTIN with `@schemeID` (`0209` SGTIN, `0160` GTIN).
* **`cac:SellerSubstitutedLineItem`** – Not covered by this guide.
* **`cac:OrderLineReference/cbc:LineID`** – **Mandatory**: link to the corresponding order line.

---

## Attachment A: Quantity/@unitCode usage

Use **UN/ECE Recommendation 20** (including **Rec 21** codes, prefixed with **X**) for unit codes. The following shortlist is recommended for the concrete element supply chain. For possible expansion, consider the Swedish shortlist first.

| `cbc:Quantity/@unitCode` | English description | Finnish     | Swedish      | Notes                                                                          |
| ------------------------ | ------------------- | ----------- | ------------ | ------------------------------------------------------------------------------ |
| C62                      | one                 | kappale     | styck        | Use `EA` when *writing* messages; `C62` *should be understood* when receiving. |
| H87                      | piece               | kappale     | styck        | Use `EA` when *writing* messages; `H87` *should be understood* when receiving. |
| EA                       | each                | kappale     | styck        | Preferred code for messages.                                                   |
| KGM                      | kilogram            | kilogramma  | kilogram     |                                                                                |
| MTK                      | square metre        | neliömetri  | kvadratmeter |                                                                                |
| MTQ                      | cubic metre         | kuutiometri | kubikmeter   |                                                                                |
| MTR                      | metre               | metri       | meter        |                                                                                |

---

## Attachment B: AdditionalItemProperty usage

Use the following **`cac:AdditionalItemProperty`** names and values consistently to enable automated processing. (Examples shown where available.)

| `cbc:Name`                   | `cbc:Value (Example)`                                                               | Description | Finnish description             |
| ---------------------------- | ----------------------------------------------------------------------------------- | ----------- | ------------------------------- |
| Name of the building         | *Rakennuksen nimi*                                                                  |             |                                 |
| Building block name          | *Rakennuslohkon nimi*                                                               |             |                                 |
| Floor name                   | *Kerroksen nimi*                                                                    |             |                                 |
| Installation block 1         | *Asennuslohko 1*                                                                    |             |                                 |
| Installation block 2         | *Asennuslohko 2*                                                                    |             |                                 |
| Installation block 3         | *Asennuslohko 3*                                                                    |             |                                 |
| Stairwell                    | *Rappu*                                                                             |             |                                 |
| Space/Room                   | *Tila*                                                                              |             |                                 |
| Planned factory casting date |                                                                                     |             | *Suunniteltu tehtaan valupäivä* |
| Planned delivery date        |                                                                                     |             | *Suunniteltu toimituspäivä*     |
| MTO – Variation Number       |                                                                                     |             |                                 |
| Data carrier                 | *RFID:n tunnus*                                                                     |             |                                 |
| CO₂ / ESG                    | *Hiilidioksidiekvivalentti*                                                         |             |                                 |
| Assembly type                | *BETONIELEMENTTI / PAIKALLAVALU / TERÄSKOKOONPANO / PUUKOKOONPANO / MUU KOKOONPANO* |             |                                 |
| Contracted item              | `True` / `False`                                                                    |             |                                 |
| **Kääntökivi**               |                                                                                     |             |                                 |

> Fill in exact descriptions and controlled values as agreed by the parties. Keep naming **identical** across documents.

---

## Attachment C: Dimension descriptions

| `AttributeID` | Explanation      | Unit of measure | Description (Finnish) |
| ------------- | ---------------- | --------------- | --------------------- |
| HT            | Height dimension | MMT             | Maksimikorkeus        |
| HT            | Height dimension | MMT             | Betoniosan korkeus    |
| WD            | Width dimension  | MMT             | Maksimi paksuus       |
| WD            | Width dimension  | MMT             | Betoniosan paksuus    |
| LN            | Length           | MMT             | Maksimipituus         |
| LN            | Length           | MMT             | Betoniosan pituus     |
| GW            | Gross Weight     | KGM             | Bruttopaino           |

---

## Example files

Example XML files can be downloaded **here**. The examples include **X** scenarios.

> *(Insert links or references to the example files repository/location.)*
