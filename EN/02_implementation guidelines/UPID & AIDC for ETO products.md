# Implementation guideline for unique product identification and data carrier interoperability

**Engineer-To-Order Construction products**  
>Publisher: Rakennusteollisuus ry\
>Release: 27.6.2025  
Versio: 1.3  
Status: Released



## Document information
<details> 
<Summary>Log of changes</Summary>
 
| **Release**| **Date of change**| **Changed by**  |**Summary of change**                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 1.0        | 2024-12-10        |TAla             | Document released                              |
| 1.1        | 2024-12-16        |TAla             | Added missing information and corrected typos  |
| 1.2        | 2025-01-09        |TAla             | Added missing information and corrected typos  |
| 1.3        | 2025-06-17        |TAla             | Corrected typos                                |
</details>

<details> 
<Summary>Contributors</Summary>

| **Name**            | **Organisation**               |
|---------------------|--------------------------------|
| Teemu Alaluusua     | Aalto-yliopisto                |
| Juuso Autiosalo     | Aalto-yliopisto                |
| Petri Leppänen      | GS1 Finland Oy                 | 
| Tom Partanen        | Consolis Parma Oy              |
| Eetu Lahtinen       | Consolis Parma Oy              |
| Janne Kihula        | Rakennustuoteteollisuus RTT ry |
| Veijo Artoma        | Consolis Parma Oy              |
| Kari Turunen        | Lujabetoni Oy                  |
| Ville Retulainen    | Lujabetoni Oy                  |
| Markku Räisänen     | Betset Oy                      |
| Otto Alhava         | Fira Oy                        |
| Tuomas Kekki        | Fira Oy                        |
| Hannes Ilveskoski   | Fira Oy                        |
| Antti Pekkala       | Fira Oy                        |
| Ari Törrönen        | NCC Suomi Oy                   |
| Riku Laiho          | NCC Suomi Oy                   |
| Arto Nieminen       | NCC Suomi Oy                   |
| Janne Makkonen      | Consti                         |
| Ville Siikaoja      | YIT                            |
| Lassi Saari         | YIT                            |
| Klaus Turhanen      | RFID Lab Finland ry            |
| Janne Raitaniemi    | Riffid Oy                      |
| Juha Porkka         | Nordic ID Oyj                  |
| Sami Saari          | Rakennustieto Oy               |
| Teemu Rantanen      | Rakennustieto Oy               |
</details>

## 1 Background
Unique Product Identification (UPID) and Automatic Identification and Data Capture (AIDC) carriers for construction products are key components of digitalization in the real estate and construction sector. Standardized, interoperable, and globally adopted methods for product identification and data capture ensure consistent and reliable information exchange among stakeholders, regardless of their role in the supply chain.

The supply chain management standards developed by GS1, such as the GTIN product identifier combined with the EAN barcode, enable consistent information exchange between different stakeholders. The GTIN product identifier allows the identification of any trade item that can be priced, ordered, or invoiced at any stage of the supply chain, where predefined information needs to be retrieved.

In the retail sector, products have been identified using GTIN codes and machine-readable 1D EAN barcodes for over 50 years. This proven practice has now become established for Make-To-Stock (MTS) construction products as well. However, in the Finnish construction industry, Engineer-To-Order (ETO) products are widely utilized, and the methods for their identification and recognition have not yet been standardized.

The identification of construction products is critical from the perspective of information exchange, as the lifespan of these products is typically long, with some remaining in active use for over 100 years. The rapid development of new materials, along with the growing importance of sustainability and the circular economy, has increased the need to manage construction products and their properties throughout their lifecycle.

## 2 Purpose of this guideline
This implementation guideline has been created as part of the Confederation of Finnish Construction Industries RT's (Rakennusteollisuus RT) development project on product information and supply chain digitalization, led by the BETK working group. The primary goal of the development project is to advance the methods for managing the construction industry's product supply chain, transitioning from manual and unstructured information exchange to fully structured and machine-readable data exchange. This document is continuously updated and further developed based on findings from the ongoing development efforts of Rakennusteollisuus RT.

The implementation guideline focuses on the product identification and data capture required for the digitalization of the supply chain. It outlines a model for applying open GS1 standards to manage the supply chain of Engineer-to-Order (ETO) construction products, using precast concrete elements as an example.

GS1 is conducting international standardization work related to the identification of Engineer-to-Order and Made-to-Order products. As this guideline was created while the standardization process is ongoing, it may be updated as necessary to align with finalized standards.

## 3 SGTIN product identification of construction products
Unique Product Identification (UPID) is a prerequisite for the digitalization of the supply chain, regardless of the manufacturing logic of the products. For precast concrete elements, product identification has been designed to scale by leveraging an open, product-group-independent, and international standard. The GTIN code, compliant with GS1 standards, is a widely used solution for product identification across various industries. Its application was selected as the foundation for identifying Engineer-To-Order (ETO) products, such as precast concrete elements, within this project.

Traditionally, GTIN codes have been used to identify Make-To-Stock (MTS) products, where all identical items are assigned the same GTIN. By combining a GTIN code with a serial number, a unique identifier is created that allows identical products to be distinguished from one another. This combination is known as the SGTIN (Serialized Global Trade Item Number).

Precast concrete elements are inherently Make-To-Order (MTO) and Engineer-To-Order (ETO) products, meaning their identification using GTIN codes differs fundamentally from that of Make-To-Stock (MTS) products. While it is possible to assign a unique GTIN code to each individual precast element, the BETK working group has opted to use the GS1 standard with a three-level identification model (as shown in Figure 1). In this model the GTIN code identifies a specific base product type from a specific manufacturer. The Made-To-Order (MTO) variant number distinguishes a particular variant of the base product. The serial number uniquely identifies identical units of the same variant.

Thus, a GTIN alone does not uniquely identify a specific product but rather represents a general category of possible product variations that may be manufactured based on the order.


![eng_Kuva1](https://github.com/user-attachments/assets/215e3983-26a9-4685-b42b-ea079cbd948e)


###### Figure 1.  Hierarchical levels of product identification for more precise identification

### 3.1 Using GS1 application identifiers to identify ETO products  
GS1 Application Identifiers (AI) are numeric prefixes used in barcodes and EPC/RFID tags to define the meaning and format of data elements. The use of AIs enables the differentiation of various data elements within barcodes or EPC/RFID tags. The GS1 standard includes over 100 application identifiers. Each AI is typically a two-, three-, or four-digit number. A comprehensive list of all GS1 Application Identifiers is available on the GS1 website:https://ref.gs1.org/ai/.

The following GS1 Application Identifiers (AIs) have been identified as necessary to meet the minimum data requirements for the identification of precast concrete elements:  
• ```(03) MTO GTIN```: Global Trade Item Number – identifies the base product type.  
• ```(242) Made-to-Order Variation Number```: Distinguishes a specific variant of the base product.  
• ```(21) Serial Number```: Uniquely identifies individual units of the same variant.  

The GS1 standard does not currently provide specific GS1 Application Identifiers (AIs) for the National Element Classification number, GUID, or Domain Name. Therefore, the BETK project has decided to use the following application identifiers for including this data in information carriers:  
• ```(91) Company Internal Information```  
• ```(92) Company Internal Information```  
• ```(99) Company Internal Information```  

GS1 AIs starting with the digit 9 are reserved for company-specific or internal use and should only be applied when there is no official GS1 Application Identifier defined for the particular data element. This approach ensures flexibility while adhering to GS1 standards for data structuring.

Note! At the time of this guideline's publication, the handling of domain names in RFID tags is under review within GS1's international standard development process. The forthcoming standard may differ from the solution presented here, and this guidance will be updated accordingly once the standard is finalized.

For optical recognition (e.g., QR codes), the inclusion of this information follows the procedure outlined in the GS1 Digital Link URI Syntax 1.5.0 standard.

###### Table 1. Minimum data requirements to be included in the information carrier (2D DataMatrix Barcode or EPC/RFID Tag)

| GS1 Application Identifier (AI)     | Example                      |
|-------------------------------------|------------------------------|
|(03) MTO GTIN                        | <code>06400001000247</code>  |
|(242) Made-To-Order variation number | <code>123456</code>          |
|(21) Serial number                   | <code>12345678910</code>     | 

###### Table 2. Identification Data to be Included in the Data Carrier (2D DataMatrix Barcode or EPC/RFID Tag). Note: For optical recognition
(e.g., QR codes), the inclusion of the domain name follows the procedure outlined in the GS1 Digital Link URI Syntax 1.5.0 standard.

| GS1 Application Identifier (AI) | Definition      | Example                                          |
|---------------------------------|-----------------|---------------------------------------------------|
| (91)                            | Elementtitunnus | <code>V1001</code>                                |
| (92)                            | GUID            | <code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code> |
| (99)                            | Domain Name     | <code>id.rt.fi </code>                            |

### 3.2 GS1 Company Prefix
The GS1 Company Prefix is a unique numeric sequence assigned to companies globally by the GS1 organization. This prefix is specific to each company and cannot be used by any other entity or for generating other numeric sequences. The GS1 Company Prefix is utilized in many standardized identification methods, such as barcodes and RFID tags, and serves as the basis for creating GTIN, GLN, and SSCC codes.

In Finland, GS1 Company Prefixes are issued by GS1 Finland, and they can be ordered from the GS1 Finland online store. When selecting the appropriate GS1 Company Prefix, it is important to consider the number of GTIN codes needed. Assistance in determining this can be obtained from GS1 Finland's customer service.

### 3.3 GTIN code generation
Creating GTIN codes requires a company to have a GS1 Company Prefix (GCP). GTIN codes enable the unique identification of products at the base product level.

A GTIN code begins with the GS1 Company Prefix, which can range from 7 to 11 digits in length for prefixes issued by GS1 Finland. Following the company prefix, 1 to 6 digits can be defined by the company, where the use of sequential numbering is recommended. The number of digits available for customization depends on the length of the company prefix. The last digit, the 13th digit, is a check digit calculated using the first 12 digits with the Modulo 10 algorithm. To calculate the check digit, tools such as the GS1 Finland Check Digit Calculator can be used: https://gs1.fi/fi/tarkistusnumerolaskuri

###### Table 3. Structure of a GTIN Code

| GS1 Application Identifier (AI) | GS1 Company Prefix ---> <--- Item number  | Check digit   |
|--------------------|--------------------------------------------------------|---------------|
| (03)               |  <ins>0</ins> N1 N2 N3 N4 N5 N6 N7 N8 N9 N10 N11 N12   | N13           |
 
In barcodes and RFID tags, the Application Identifier (AI) used to express the GTIN is <code>(03)</code>. GS1's international standard development is currently addressing the identification of Make-To-Order (MTO) and Engineer-To-Order (ETO) products. This standardization effort may result in changes to how GTINs are expressed for such products. This guideline will be updated accordingly once the standard is finalized.

Note: The longest version of a GTIN is 14 characters. GTINs shorter than 14 characters are padded with leading zeros to reach the 14-character length. A GTIN cannot exceed 14 characters.

GS1 Finland provides its company prefix customers with access to the GS1 Registry service for generating GTIN codes. By creating GTIN codes through the GS1 Registry service, companies can ensure that the codes are formatted correctly.

### 3.4 Identification of product variations
In the identification of variations in precast concrete elements, a variation number (Made-to-Order variation number) is combined with the GTIN code as an additional identifier. The variation number allows for identifying elements that are identical to one another. In other words, when multiple elements with the same technical specifications are manufactured at once, they all share the same combination of GTIN code and variation number.

In barcodes and RFID tags, the Application Identifier (242) is used to express the variation number. According to the GS1 standard, the variation number is numeric, variable in length, and up to six digits long.

###### Table 4. Structure of the MTO Variation Number

| GS1 Application Identifier (AI) | Made-to-Order variation number |
|---------------------------------|--------------------------------|
| (242)                           | N1 ----variable length--->N6  |

### 3.5 Serial number
By combining a GTIN code (or a combination of a GTIN code and a variation number) with serial numbering, it is possible to uniquely identify and distinguish identical elements from one another. The GS1 Application Identifier <code>(21)</code> indicates that the data field contains the serial number.

According to the GS1 standard, the serial number is alphanumeric and up to 20 characters long. Note: The selected RFID tag may impose restrictions on the length of the serial number and the use of alphabetic characters, so it is advisable to verify these limitations with the RFID solution provider.
###### Table 5. Structure of the Serial number

| GS1 Application Identifier (AI) | Serial number                  |
|---------------------------------|--------------------------------|
| (21)                            | X1 ----variable length--->X20 |

### 3.6 National element classification number
Manufacturers' Unique Product Identification (UPID) designated for a precast concrete element, which is easily readable by humans and may include information such as the element type or installation level. The national element classification number does not need to be globally unique.

###### Table 6. National element classification number structure

| GS1 Application Identifier (AI) | National element classification number structure|
|---------------------------------|-------------------------------------------------|
| (91)                            | X1 ----variable length--->X20                   |

### 3.7 GUID
Globally Unique Identifier (GUID), also known as Universally Unique Identifier (UUID), is a globally unique alphanumeric code combination that can be assigned by modeling software or other means to ensure uniqueness.

###### Table 7. GUID code structure

| GS1 Application Identifier (AI) | GUID                                 |
|---------------------------------|--------------------------------------|
| (92)                            | xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |

### 3.8 Domain Name
By combining a Domain Name with other identification information, additional details about a specific product can be retrieved over the internet using a URL, provided the information supplier has implemented this feature and continues to maintain its availability.


###### Table 8. Structure of a Domain Name. * Note: In optical recognition (e.g., QR codes), the inclusion of this information follows the procedure outlined in the GS1 Digital Link URI Syntax 1.5.0 standard.

| GS1 Application Identifier (AI) | Domain Name                                                                    |
|---------------------------------|--------------------------------------------------------------------------------|
|(99)                             |<subdomain.><domain.toplevel-domain> Where <subdomain.> can appear 0 to n times.|

This document defines two methods for combining a Domain Name with other identification information to form a URL. The resulting URL conforms to the GS1 Digital Link standard or the IEC 61406 standard. 

#### 3.8.1 Generating a GS1 Digital Link URL
**GS1 Digital Link** is a GS1 standard for automatic identification and data capture (AIDC) that specifies how a domain name can be used to assign a URL to a product. However, GS1 has not yet defined how a domain name can be written into an RFID tag to specify GS1 Digital Link at an individual level. (This specification is under development at GS1, but for now, BETK follows its own method.)


According to the BETK application guideline, GS1 Digital Link is formed as follows:  
**Identification Level 1:** ```https://<Domain Name>/03/<MTO GTIN>```  
**Identification Level 2:** ```https://<Domain Name>/03/<MTO GTIN>/242/<MTO variant number>```  
**Identification Level 3:** ```https://<Domain Name>/03/<MTO GTIN>/242/<MTO variant number>/21/<serial number>```  
**Level 3 without a variant number:** ```https://<Domain Name>/03/<MTO GTIN>/21/<serial number>```  
For the last case, an example URL is: https://id.rt.fi/01/06400001000247/21/12345678910  
More details about the GS1 Digital Link standard can be found in Section 4.3 of this guideline.

#### 3.8.2 Generation of the IEC 61406 Identification Link URL
Additionally, a URL based on a GUID identifier can be defined in accordance with the IEC 61406 Identification Link standard as follows:

```https://<Domain Name>/<GUID>```  

For example, this results in: <code>https://id.rt.fi/ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code>

## 4 Automatic identification and data capture
In addition to Unique Product Identification (UPID), suitable Automatic Identification and Data Capture (AIDC) technology must be selected to enable machine readability and facilitate the digitalization of supply chain management. When selecting AIDC technology, the requirements set by the intended use and environmental conditions must be considered. GS1 Data Carriers for automatic identification and data capture (AIDC) can store varying amounts of information to meet the needs of different business processes and trade requirements. The data encoded into GS1 data carriers not only uniquely identify products at all levels of the Product Identification Hierarchy but also provide access to product information and visibility into product movements within the supply chain.  

To convey the minimum data requirements for the product identification of precast concrete elements, the implementation guideline recommends at least adding a 2D code based on optical recognition to the product label during manufacturing. According to the GS1 standard, the options for this are a GS1 DataMatrix code or a QR code with data content compliant with the GS1 Digital Link standard. Alongside the 2D code used on the product label, machine-readable data carriers based on RFID technology can also be utilized, either on the product label or embedded into the precast concrete element. Figure 1 illustrates the use and marking of data carriers for precast concrete elements.

This implementation guideline describes product identification using the GS1 DataMatrix code, which is suitable for the use cases defined by the BETK working group. As an alternative, the QR code compliant with the GS1 Digital Link standard is also briefly introduced, and additional information about its potential applications can be obtained from GS1 Finland, if needed.  

![2025-06-25_eng_Kuva1](https://github.com/user-attachments/assets/ae613273-30f1-420a-a237-4efdf57d800e)

###### Figure 2. Automatic identification and data capture via GS1 Data Carriers
The most efficient AIDC carrier for precast concrete elements has been found to be a passive EPC/RFID Gen-2 UHF tag, which enables the identification number of the element to be read effectively from several meters away without a direct line of sight to the tag itself.

### 4.1 EPC/RFID Gen2 UHF -tag
This implementation guideline is based on the EPC/RFID Gen2 Radio Protocol, which defines the physical data transmission between an RFID chip and an RFID reader, using commands to control the RFID reader's interaction with RFID tags. The EPC/RFID Gen2 protocol is an ISO standard and includes various functionalities, such as security features and extended user memory.

GS1 has published the TDS (Tag Data Standard), which specifies how GS1 identification keys, such as SGTIN, are
incorporated into EPC Gen2 RFID tags for remote reading. The TDS standard is openly available to everyone and
is already widely used for RFID identification across various industries.

In product identification, the required data is embedded into EPC Gen2 RFID tags in accordance with the TDS standard, using the necessary GS1 Application Identifiers (AIs). Data encoding utilizes the tag's EPC memory and, as needed, the User memory.

The EPC memory is designed to store the EPC code, which is a unique identifier for the item based on the GS1 standard. In the identification of precast concrete elements, the SGTIN code of the element is encoded in the EPC memory. This enables the quick reading of the element's unique identification number.

User memory is used when additional information is required on the RFID tag beyond what the EPC memory can accommodate. In the BETK project, it has been identified that additional data, such as the Made-to-Order Variation Number, the element identifier used for classifying elements, and the GUID created by the design software, needs to be included in the tag. The following tables describes Structure of GTIN and SGTIN in 2D Barcodes and EPC/RFID Gen 2V2 RFID Tags

###### Table 9. EPC Binary Encoding Schemes Use and Their Restrictions. The applicable method is determined by the required number of numeric or alphanumeric characters.

<html>
<table>
    <thead>
        <tr>             
           <th>EPC Scheme</th>
           <th>EPC-binary Coding Scheme</th>
           <th>EPC + Filter Bit Count</th>
           <th>Inclues Filter Value</th>
           <th>Serial number limitation</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">sgtin</td>
            <td>sgtin-96</td>
            <td>96</td>
            <td>Yes</td>
            <td>Numeric-only, no leading zeros, decimal value must be less than 2³⁸ (i.e., decimal value less than or equal to 274,877,906,943)..</td>
        </tr>
        <tr>
            <td>sgtin-198</td>
            <td>198</td>
            <td>Yes</td>
            <td>All values permitted by GS1 General Specifications (up to 20 alphanumeric characters).</td>
        </tr>
    </tbody>
</table>
</html>

###### Table 10. Applicable Method: SGTIN-96. The SGTIN-96 encoding method is commonly used. However, the TDS 2.1 (EPC Tag Data Standard) also includes other encoding methods, such as SGTIN-198, which can be utilized if there is a need for longer serial numbers or serial numbers that include both letters and numbers.

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">Data structure SGTIN-96</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>EPC SGTIN-96</b></td>
            <td><b>Value</b></td>
            <td><b>Comment</b></td>
        </tr>
        <tr>
            <td>Header</td>
            <td><code>48</code></td>
            <td>Number for SGTIN-96</td>
        </tr>
      <tr>
            <td>Filter value</td>
            <td><code>0</code></td>
            <td>0 = Applicable Value for a Product Not Scanned at Point-of-Sale</td>
        </tr>
         <tr>
            <td rowspan="6">Partition</td>
            <td rowspan="6"><code>1</code>,<code>2</code>,<code>3</code>,<code>4</code>,<code>5</code>or<code>6</code></td>
            <td>
              1 = GS1 GCP of 11 digits and 2 digits in item number + indicator                                        
            </td>
        </tr>
        <tr>
            <td>2 = GS1 GCP of 10 digits and 3 digits in item number + indicator </td>
        </tr>
       <tr>
            <td>3 = GS1 GCP of 9 digits and 4 digits in item number + indicator</td>
        </tr>
       <tr>
            <td>4 = GS1 GCP of 8 digits and 5 digits in item number + indicator</td>
        </tr>
        <tr>
            <td>5 = GS1 GCP of 7 digits and 6 digits in item number + indicator</td>
        </tr>
        <tr>
            <td> 6 = GS1 GCP of 6 digits and 7 digits in item number + indicator</td>
        </tr>
         <tr>
          <td>GS1 Company Prefix (GS1 GCP)</td>
          <td><code>N…11</code></td>
          <td>GS1 GCP: 6,7,8,9,10 or 11 digits</td>
         </tr>
        <tr>
          <td>Item number</td>
          <td><code>N…7</code></td>
          <td>Depending on the number of digits in GS1 GCP. 1–7 digits</td>
        </tr>
         <tr>
          <td>Serial number </td>
          <td><code>N…12</code></td>
          <td>Up to 12 digits (hiqhest allowable value = 274 877 906 943) A fixed number of digits is chosen for serial number, it must not be 12 digits. You choose as many as needed. Leading zero is not allowed</td>
        </tr>
    </tbody>
</table>
</html>

**Example of data string in an EPC / Gen2 RFID chip**  
RFID Tag EPC Memory Bank Contents (hexadecimal): ```301586A004000602DFDC1C3E```  
EPC Tag URI: ```urn:epc:tag:sgtin-96:0.6400001.000024.12345678910```  

**Data Structure Breakdown**  
**1. URN Prefix**  
Value: ```urn:epc:id```  
Description: Specifies that this is a Uniform Resource Identifier (URI).  
**2. EPC Scheme**  
Value: ```sgtin-96```  
Description: Indicates the GS1 Identification Key used in this case (Serialized Global Trade Item Number with 96-bit encoding).  
**3. Filter Value**  
Value: ```0```  
Description: Filter value indicating "product not scanned at the point-of-sale."  
**4. GS1 Company Prefix**  
Value: ```6400001```  
Description: Identifies the company issuing the product.  
**5. Indicator and Item Reference Number**  
Value: ```000024```  
Description: Combines the indicator digit and the item reference number for the specific product.  
**6. Serial Number**  
Value: ```12345678910```  
Description: Uniquely identifies the specific instance of the product.  

**Additional Notes**  
>**Partition Value**   
Determines where the separator ```( . )``` is placed to divide the GS1 Company Prefix and the Item Reference
Number. The last separator ```( . )``` in the URI distinguishes the GTIN (Global Trade Item Number) from the
serial number.\  

>**Check Digit**  
Not included in the EPC code stored in the RFID tag.\  

**User Memory Section**
Additional information can be stored in the User Memory of the RFID chip as Application Identifiers (AIs):

###### Table 11. Additional information on the use of concrete elements

<html>
<table>
    <thead>
        <tr>            
            <th>GS1 Application Identifier (AI)</th>
            <th>Definition</th>
            <th>Value (example)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>(91) Internal</td>
            <td>Element classification</td>
            <td><code>V1001</code></td>
        </tr>
         <tr>
            <td>(92) Internal</td>
            <td>GUID</td>
            <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code></td>
        </tr>
        <tr>
            <td>(99) Internal</td>
            <td>Domain name</td>
            <td><code>id.rt.fi</code></td>
        </tr>
     </tbody>
</table>
</html>

**Implementing RFID Tags**  
For programming RFID tags, it is recommended to collaborate with companies specializing in identification solutions. A list of such solution providers can be found on the GS1 Partner Page and the RFID Lab Finland Association website.

#### 4.1.1 Use of RFID symbol
When using RFID technology for automatic product identification, it is essential to ensure that the RFID tag symbol is included on product labels and production plans. The symbol must comply with standards, be easily recognizable, and be positioned in a way that clearly indicates the location and use of RFID tags.

###### Table 12. General RFID symbol (ISO 7000-3010). <sup>[1]</sup> <sup>[2]</sup> <sup>[3]</sup>

<html>
    <tbody>
        <tr>
         <table>
 <th rowspan="4">
<img width="300" alt="RFID-symbol" src="https://github.com/user-attachments/assets/5c9d4d49-e5d6-4bac-a66f-c77a9731fce9"/>
               </th>
         <th>RFID symbol</th>
        </tr>
        <tr>
            <td>The ISO 7000-3010 standard's freely available general RFID symbol is recommended for use as the RFID tag symbol. The use of this symbol must comply with the requirements of the ISO/IEC 29160:2020 standard, especially when the symbol is used to indicate the location of RFID tags.  </td>
        </tr>
        <tr>
            <th>Size</th>
        </tr>
         <tr>
            <td>The RFID tag symbol (ISO 7000-3010) should have a minimum size of 5 × 5 mm, with a 1 mm clear zone surrounding it. When the RFID tag symbol is presented in low contrast, it must be sufficiently large to ensure it is easily recognizable under typical operating conditions. </td>
        </tr>
    </tbody>
</table>
</html>

**Utilizing RFID Symbols on Precast Concrete Elements**  
The RFID symbol must be positioned so that it is easily visible to those trying to locate or read the actual RFID tag. The use of an RFID symbol is recommended in precast concrete production drawings to indicate the location of RFID tags (example illustrated in Annex 1). The use of the RFID tag shall be indicated by the RFID tag symbol and the type of tag used and the location information shall be included in the product catalogue of the precast concrete element.

**Placing the RFID Tag to the Physical Product**  
The readability of RFID tagged objects is affected by several factors, such as the RFID chip, the RFID antenna and the encapsulation (the whole RFID tag). The environment in which the RFID tag is read has a significant impact on readability. For example, an environment with many metal objects can detune and reflect RFID signals, while liquids tend to absorb them, both of which can interfere with the performance of RFID systems.

There are different types of RFID tags on the market, suitable for different uses. RFID tags can be used in a precast concrete environment, embedded in the precast concrete, on the surface of the precast concrete, or as part of a product label to be attached to precast concrete. When cast into a precast concrete element, the readability of the RFID tag is affected by the material surrounding it, so the RFID tag chosen should be such that it can be read through the surrounding concrete to a sufficient depth. The product label formed by the external applicator should include a note on the use of the RFID tag and a specification as to whether the tag is located on the tab itself or cast inside the element. The benefits of using RFID are based on automated reading events and the resulting transaction path. In simple terms, a read event is when a reader detects a specific RFID tag.


### 4.2 GS1 DataMatrix barcode
GS1 DataMatrix is a two-dimensional barcode developed by GS1 that can be printed as a square or rectangular symbol consisting of individual dots or squares. The GS1 DataMatrix can contain a larger amount of data than a traditional linear barcode. Up to 3116 numeric characters or 2335 alphanumeric characters can be encoded. GS1 application codes allow the GS1 DataMatrix to include many different types of data, such as minimum data requirements for specified concrete elements. A camera-based scanner is required to read the GS1 DataMatrix.

###### Table 13. Example of a GS1 DataMatrix code containing information requirements for precast concrete elements

<html>
<table>
   <tbody>
         <tr>  
         <th rowspan="7"><img width="110" alt="2025-06-23_Kuva2" src="https://github.com/user-attachments/assets/ce285bc2-6cfd-4abf-80c2-090c914afd56" />
         </th>   
         <th colspan="2">Example information content</th>
        </tr>
         <tr>
            <td><b>GS1 Application Identifier (AI)</b></td>
            <td><b>Value (example)</b></td>
        </tr>
        <tr>
            <td>(03) = MTO GTIN</td>
            <td><code>06400001000247</code></td>
        </tr>
         <tr>
            <td>(242) = MTO variation number</td>
          <td><code>123456</code></td>
        </tr>
        <tr>
            <td>(21) = Serial number</td>
            <td><code>12345678910</code></td>
        </tr>
       <tr>
            <td>(91) = Internal (element classification)</td>
            <td><code>V1001</code></td>
        </tr>
       <tr>
            <td>(92) = Internal (GUID)</td>
            <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code></td>
        </tr>
    </tbody>
</table>
</html>

**GS1 DataMatrix -tunnisteen koko ja laatu**   
The physical size of a barcode varies according to the amount of data it contains. The resolution (X-dimension) of the barcode shall be a minimum of 0,38 mm and a maximum of 0,45 mm. The quality of the GS1 2D barcodes used for marking shall meet the requirements of ISO/IEC 15415. This will ensure their legibility.

It is advisable to contact a company or companies specialising in identification solutions for the printing of the markings. Companies offering identification solutions are listed on the GS1 partner page.

### 4.3 GS1 Digital Link QR code  
If the tag is intended to not only enable identification and carry data but also communicate with the consumer/user via a smartphone or similar device, a QR code compliant with the GS1 Digital Link standard can be used. Unlike a regular QR code, the data content of this code is defined by the GS1 standard. The standard ensures that the codes and the information they contain are structurally consistent, making them interoperable across different systems and stakeholders, as well as readable and interpretable by barcode scanners.

A QR code containing a GS1 Digital Link URI serves two purposes: 

>**1. Offline Product Identification and data capture**
It can be used without an internet connection to identify and data capture the product via barcode scanners, just like traditional EAN barcodes. The product is identified using the GTIN code included in the QR code, as specified by the GS1 standard, along with additional required information such as the MTO variation number and serial number.

>**2. Online Interaction**
It can be used like any other QR code to direct the user of a smartphone or similar device to online content. Various applications can also perform other actions and display different content based on the same QR code scan.

The GS1 Digital Link URI incorporates GS1 Application Identifiers for embedding data. The example below shows
a GS1 Digital Link URI formed to include the minimum data requirements presented in the table

###### Table 14. The QR code in the example contains the information shown in the table in GS1 Digital Link URI format: https://id.rt.fi/01/06400001000247/242/123456/21/12345678910

<html>
<table>
    <tbody>
        <tr>            
          <th rowspan="5"><img width="110" alt="QR-koodi_Kuva1" src="https://github.com/user-attachments/assets/22a88262-4a5f-469a-bd88-95fa37559281" />
            </th>   
         <th colspan="2">Example information content</th>
        </tr>
        <tr>
            <td><b>GS1 Application Identifier (AI)</b></td>
            <td><b>Value (example)</b></td>
        </tr>
        <tr>
            <td>(03) = MTO GTIN</td>
            <td><code>06400001000247</code></td>
        </tr>
         <tr>
            <td>(242) = MTO variation number</td>
          <td><code>123456</code></td>
        </tr>
        <tr>
            <td>(21) = Serial number</td>
            <td><code> 12345678910</code> </td>
        </tr>
    </tbody>
</table>
</html>

**Example Purpose and Recommendations for GS1 Digital Link QR Codes**  
The purpose of the example is solely to demonstrate the structure of the data content. It uses a fictional Domain Name <code>id.rt.fi</code>, so when scanned with a smartphone camera, the example code does not direct to any actual content. 

As a general recommendation, the GS1 Digital Link URI included in the QR code should not point directly to a live webpage's URL. Instead, it is recommended to set up a redirection from this address to the desired content to be displayed through the code.

The Domain Name in a GS1 Digital Link URI can be any Domain Name, as it does not affect the product's identification or recognition. The Domain Name determines where the person scanning the QR code will be directed online. Therefore, it is possible to use the Domain Name of a service provider in the code. However, it is important to be aware that this may lead to a vendor lock-in situation, where changing the service provider would require replacing the codes printed on the products due to the change in the Domain Name.

**Recommended Approach: Using a Subdomain for Product Identification**  
It is recommended to use the company's own Domain Name in the QR code. This allows the company to redirect it, if needed, to content hosted under the service provider's Domain Name. A preferred practice is to create a dedicated Subdomain under the main Domain Name for product identification purposes.

A Subdomain is a separate section of the main Domain Name, used alongside the main domain for specific purposes. Using a Subdomain in QR codes ensures the permanence and independence of the URLs used for product identification from the structure of the main website. This approach adds flexibility to the maintenance of the company's website, as updates to the main website do not require changes to the links embedded in the QR codes. The codes can always be redirected to the updated target pages.

**Examples of Subdomain Usage**
The Subdomain can be based on the company's main domain or its various brand domains.  
For example:

```company-x.fi``` -> ```id.company-x.fi```  

```brand-x.fi``` -> ```id.brand-x.fi```  

The shorter the GS1 Digital Link URI, the smaller the QR code containing it can be.

**Further Information**  
The use of the GS1 Digital Link standard is described in greater detail in the following GS1 standards:  
https://ref.gs1.org/standards/digital-link/uri-syntax/  
https://ref.gs1.org/standards/resolver/

## Terms and definitions

<html>
<table>
    <tbody>
        <tr>            
          <td>Applicator</td>
          <td>A device that prints and applies an RFID tag to a product</td>
        </tr>
        <tr>
           <td>Electronic Product Code, EPC</td>
          <td>See EPC Tag Data Standard ISO/IEC 15962 <sup>[7]</sup></td>
        </tr>
        <tr>
          <td>EPC-memory</td>
          <td>The memory of an RFID tag where the EPC is written, serving as the tag's primary memory</td>
        </tr>
         <tr>
          <td>Engineer-To-Order, ETO </td>
          <td>Engineer-To-Order (ETO) refers to a manufacturing logic where products are designed and engineered to meet specific customer orders</td>
        </tr>
        <tr>
          <td>GS1 DataMatrix</td>
          <td>A GS1-compliant 2D code that can encode more information than a traditional EAN barcode. Complies with ISO/IEC 16022</td>
        </tr>
           <tr>
          <td>GS1 Application Identifier, AI</td>
          <td>GS1 Application Identifiers (AI) are 2- to 4-digit codes used in GS1-128, GS1 DataMatrix, and GS1 DataBar barcodes, as well as in EPC/RFID tags</td>
        </tr>
         <tr>
          <td>Global Trade Item Number, GTIN</td>
          <td>Global Trade Item Number (GTIN) is a GS1 product identification standard. <sup>[8]</sup> <sup>[9]</sup></td>
        </tr>
        <tr>
          <td>GUID</td>
          <td>Globally Unique Identifier (GUID) is a unique identifier assigned to each part by a modeling program or generated by other means. It is also known as a Universally Unique Identifier (UUID). <sup>[10]</sup> <sup>[11]</sup></td>
        </tr>
           <tr>
          <td>Make-To-Order, MTO</td>
          <td>Make-To-Order or Made-To-Order (MTO) refers to demand-driven production where products are manufactured based on customer orders, using predefined product designs</td>
        </tr>
         <tr>
          <td>Radio Frequency Identificatio, RFID</td>
          <td>Automatic Identification and Data Capture (AIDC) carrier that consists of a microchip, which stores and processes data, and an antenna, which transmits and receives signals</td>
        </tr>
        <tr>
          <td>Serial Global Trade Item Number, SGTIN</td>
          <td>A combination of a GTIN code and a serial number that allows identical product units to be distinguished from one another</td>
        </tr>
     <tr>
          <td>User memory</td>
          <td>A section of an RFID tag's memory that can be used to store additional, user-defined data beyond the standard identification information. This memory is typically writable and customizable to meet specific application needs</td>
        </tr>
     <tr>
          <td>UHF Tag</td>
          <td>Ultra-high-frequency RFID tag operating within the 850–960 MHz range, commonly used for longrange and high-speed data transfer applications</td>
        </tr>
     <tr>
          <td>Uniform Resource Identifier, URI</td>
          <td>is an identifier for information located on a network. A URL is always a URI, but a URI is not necessarily a URL. For example: <code>https://rt.fi</code> tai <code>urn:ISBN:952-9842-34-1</code></td>
        </tr>
     <tr>
          <td>Uniform Resource Locator, URL</td>
          <td>URL  includes the necessary information for retrieving the resource, such as the protocol (e.g., HTTPS) and the server. For example: <code>https://rt.fi</code></td>
        </tr>
     <tr>
          <td>Domain Name</td>
          <td>A domain name is a string of characters that is mapped to a specific IP address or server on the internet. For example: <code>www.iso.org</code></td>
        </tr>
    </tbody>
</table>
</html>


## References
**[1]** GS1 (2022), Recommendation for the use of EPC and ISO RFID symbols   

**[2]** ISO/IEC 29160:2020, Information technology — Radio frequency identification. Available: https://www.iso.org  

**[3]** ISO 7000-3010:2020, RFID-tag. Available: https://www.iso.org/obp/ui#iso:grs:7000:3010 

**[4]** GS1 (2023), GTIN Management Guideline for Construction Products. Available: https://www.gs1.org/standards/gtin-management-guideline-construction-products/current-standard#2-GTIN-Management-Rule-examples-for-construction-products+2-2-Declared-formulation-or-functionality.  

**[5]** GS1 (2024), GS1 Application Identifiers. Available: https://ref.gs1.org/ai/. 

**[6]** GS1 Norway (2018), Guideline for Unique identification of products with SGTIN (serialized GTIN). Labelling with GS1Datamatrix barcode and tagging with EPC / RFID Gen 2 UHF RFID tags. 

**[7]** ISO/IEC 15962:2022, EPC Tag Data Standard. Available: https://ref.gs1.org/ai/. 

**[8]** ISO/IEC 15459-6:2014 - Unique identification

**[9]** ISO/IEC 6523-1:2023: - Information technology – Structure for the identification of organizations and organization parts

**[10]** ISO/IEC 11578:1996 Information technology - Open Systems Interconnection - Remote Procedure Call (RPC)

**[11]** ISO/IEC 9834-8:2014 - Information technology

## Annex 1
![RFID asemointi eng_3](https://github.com/user-attachments/assets/28703611-f01b-4721-930a-d60a53179d4a)

