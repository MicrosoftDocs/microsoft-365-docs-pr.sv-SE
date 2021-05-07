---
title: Det här innehåller DLP-principmallarna
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Läs om vilka DLP-principmallar (data loss prevention) som finns Office 365 säkerhets- & säkerhets- och efterlevnadscenter.
ms.openlocfilehash: afcc641e6e868c1988f6b30a286c082e960d056c
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162915"
---
# <a name="what-the-dlp-policy-templates-include"></a>Det här innehåller DLP-principmallarna

I dataförlustskydd (DLP) i Säkerhetsefterlevnadscenter finns färdiga policymallar som uppfyller vanliga efterlevnadskrav, till exempel för att hjälpa dig att skydda känslig information enligt &amp; U.S. Health Insurance Act (HIPAA), U.S. Gramm-Leach-Bliley Act (GLBA) eller U.S. Act. Det här avsnittet innehåller alla principmallar, vilka typer av känslig information de letar efter och vilka standardvillkor och åtgärder som gäller. I det här avsnittet får du ingen detaljerad information om hur varje principmall är konfigurerad. I stället visas information i det här avsnittet så att du kan avgöra vilken mall som är den bästa utgångspunkten för ditt scenario. Kom ihåg att du kan anpassa de här principmallarna efter dina specifika behov.
  
## <a name="australia-financial-data"></a>Financial Data för Australien

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Finans i Australien: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Australiens skattefilnummer – Min antal 1, Max antal 9  <br/>  Bank Account Number för Australien – Min count 1, Max count 9  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Finans i Australien: Söka igenom innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Australiens skattefilnummer – min antal 10, max antal val  <br/>  Bank Account Number – Min count 10, Max count any  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Australia Health Records Act (HRIP Act)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|HRIP i Australien: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australiens skattefilnummer – Min antal 1, Max antal 9  <br/>  Australien Medical Account Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Australia HRIP: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australiens skattefilnummer – min antal 10, max antal val  <br/>  Australien Medical Account Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Personlig information (PII) i Australien

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Australiens PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australiens skattefilnummer – Min antal 1, Max antal 9  <br/>  Australien Driver's License Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Australiens PII: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australiens skattefilnummer – min antal 10, max antal val  <br/>  Australiens driver's License Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="australia-privacy-act"></a>Australia Privacy Act

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Sekretess i Australien: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australien Driver's License Number – Min count 1, Max count 9  <br/>  Australien Passport Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Sekretess i Australien: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Australiens driver's License Number – Min count 10, Max count any  <br/>  Australia Passport Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-financial-data"></a>Canada Financial Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Ekonomiska data i Kanada: Söka efter innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Bank Account Number för Kanada – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Ekonomiska data i Kanada: Söka efter innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Bank Account Number för Kanada – Min antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Canada Health Information Act (HIA)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|HIA i Kanada: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Min count 1, Max count 9  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|HIA i Kanada: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Minsta antal 10, Max antal val  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Canada Personal Health Act (PHIPA) – Ontario

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|PHIPA i Kanada: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Min count 1, Max count 9  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|PHIPA i Kanada: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Minsta antal 10, Max antal val  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Canada Personal Health Information Act (PHIA) – Manitoba

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Phia i Kanada: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Phia i Kanada: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Canada Personal Information Protection Act (PIPA)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Pipa i Kanada: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Min count 1, Max count 9  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|PIPA i Kanada: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Canada Passport Number – Minsta antal 10, Max antal val  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Canada Personal Information Protection Act (PIPEDA)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Pipeda i Kanada: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kanadas driver's License Number – Min count 1, Max count 9  <br/>  Bank Account Number för Kanada – Min count 1, Max count 9  <br/>  Canada Passport Number – Min count 1, Max count 9  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Canada PIPEDA: Sök igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kanadas driver's License Number – Min count 10, Max count any  <br/>  Bank Account Number för Kanada – Min antal 10, Max antal val  <br/>  Canada Passport Number – Minsta antal 10, Max antal val  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Personlig information (PII) i Kanada

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Kanadas PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kanadas driver's License Number – Min count 1, Max count 9  <br/>  Bank Account Number för Kanada – Min count 1, Max count 9  <br/>  Canada Passport Number – Min count 1, Max count 9  <br/>  Canada Social Insurance Number – Min count 1, Max count 9  <br/>  Kanada Hälsotjänst – Min antal 1, Max antal 9  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Kanadas PII: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kanadas driver's License Number – Min count 10, Max count any  <br/>  Bank Account Number för Kanada – Min antal 10, Max antal val  <br/>  Canada Passport Number – Minsta antal 10, Max antal val  <br/>  Canada Social Insurance Number – Min count 10, Max count any  <br/>  Kanada Hälsotjänst Tal – Min antal 10, Max antal val  <br/>  Canada Personal Health Identification Number (PHIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="france-data-protection-act"></a>France Data Protection Act

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|France DPA: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  France National ID Card (CNI) – Min count 1, Max count 9  <br/>  France Social Security Number (INSEE) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|France DPA: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  France National ID Card (CNI) – Min count 10, Max count any  <br/>  France Social Security Number (INSEE) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="france-financial-data"></a>France Financial Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|France Financial: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Betalkortsnummer enligt EU – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Ekonomi för Frankrike: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Betalkortsnummer –10 min antal, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>France Personally Identifiable Information (PII) Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|France PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  France Social Security Number (INSEE) – Min count 1, Max count 9  <br/>  France Driver's License Number – Min count 1, Max count 9  <br/>  France Passport Number – Min count 1, Max count 9  <br/>  France National ID Card (CNI) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|France PII: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  France Social Security Number (INSEE) – Min count 10, Max count any  <br/>  France Driver's License Number – Min count 10, Max count any  <br/>  France Passport Number – Minsta antal 10, Max antal val  <br/>  France National ID Card (CNI) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Allmän dataskyddsförordning (GDPR)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Innehåll med låg volym EU-känsligt innehåll hittades  <br/> | Innehållet innehåller känslig information:  <br/>  Betalkortsnummer enligt EU – Min count 1, Max count 9  <br/>  EU-drivrutinens licensnummer – Min count 1, Max count 9  <br/>  EU National Identification Number – Min count 1, Max count 9  <br/>  EU Passport Number – Min count 1, Max count 9  <br/>  Social Security Number (SSN) eller motsvarande ID – Min count 1, Max antal 9  <br/>  EU:s skatteidentifieringsnummer (TIN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka incidentrapporter till administratören  <br/> |
|Hög volym av känsligt EU-innehåll hittades  <br/> | Innehållet innehåller känslig information:  <br/>  Betalkortsnummer enligt EU – Min count 1, Max count 9  <br/>  EU-drivrutinens licensnummer – Min count 1, Max count 9  <br/>  EU National Identification Number – Min count 1, Max count 9  <br/>  EU Passport Number – Min count 1, Max count 9  <br/>  Social Security Number (SSN) eller motsvarande ID – Min count 1, Max antal 9  <br/>  EU:s skatteidentifieringsnummer (TIN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Begränsa åtkomst till innehållet för externa användare  <br/>  Meddela användarna via e-post- och principtips  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapporter till administratören  <br/> |
   
## <a name="germany-financial-data"></a>Germany Financial Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Ekonomiska data i Tyskland: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Betalkortsnummer enligt EU – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Ekonomiska data i Tyskland: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Betalkortsnummer –10 min antal, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Personlig information (PII) i Tyskland

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Tyskland-PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Tyska driver's License Number – Min count 1, Max count 9  <br/>  Tyska Passport Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Tyskland-PII: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Tyska driver's License Number – Min count 10, Max count any  <br/>  Tyska Passport Number – Minsta antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="israel-financial-data"></a>Israels ekonomiska data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Ekonomiska data i Israel: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels bankkontonummer – min antal 1, max antal 9  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Ekonomiska data i Israel: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels bankkontonummer – 10 min antal, max antal val  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Personligt identifierbar information för Israel

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Israels PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels national-ID – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Israels PII: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels national-ID – 10 min antal, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Israels integritetsskydd

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Sekretess i Israel: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels national-ID – Min count 1, Max antal 9  <br/>  Israels bankkontonummer – min antal 1, max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Sekretess i Israel: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Israels national-ID – 10 min antal, max antal val  <br/>  Israels bankkontonummer – 10 min antal, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="japan-financial-data"></a>Japanska ekonomiska data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Finans i Japan: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Japan Bank Account Number – Min count 1, Max count 9  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Finans i Japan: Söka igenom innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Japan Bank Account Number – Min count 10, Max count any  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Personlig information i Japan

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Japan-PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Invånarregistreringsnummer för Japan – min count 1, max antal 9  <br/>  Japan Social Insurance Number (SIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Japan-PII: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Invånarregistreringsnummer i Japan – min count 10, max antal val  <br/>  Japan Social Insurance Number (SIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Japan Protection of Personal Information

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Japans PPI: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Invånarregistreringsnummer för Japan – min count 1, max antal 9  <br/>  Japan Social Insurance Number (SIN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Japans PPI: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Invånarregistreringsnummer i Japan – min count 10, max antal val  <br/>  Japan Social Insurance Number (SIN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>PCI Data Security Standard (PCI DSS)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Y.DSS: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Y.DSS: Söka igenom innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Saudiarabien – lagen om cyberbrott

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Saudiarabien ACC: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  International Banking Account Number (IBAN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Saudiarabien ACC: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  International Banking Account Number (IBAN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Saudiarabiens ekonomiska data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Saudiarabien Financial: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  International Banking Account Number (IBAN) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Saudiarabien Financial: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  International Banking Account Number (IBAN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Personligt identifierbar information från Saudiarabien

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Saudiarabiens PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Saudiarabiens national-ID – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Saudiarabiens PII: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Saudiarabiens national-ID – 10 min antal, max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>Storbritannien Åtkomst till Medical Reports Act

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien AMRA: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Hälsotjänst Number – Min count 1, Max count 9  <br/>  Storbritannien National Insurance Number (NINO) – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien AMRA: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Hälsotjänst Number – Min count 10, Max count any  <br/>  Storbritannien National Insurance Number (NINO) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-data-protection-act"></a>Storbritannien Dataskyddslag

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien DPA: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 1, Max count 9  <br/>  U.S. / Storbritannien Passport Number – Min count 1, Max count 9  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien DPA: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 10, Max count any  <br/>  U.S. / Storbritannien Passport Number – Min count 10, Max count any  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-financial-data"></a>Storbritannien Finansiella data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien Finans: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  Betalkortsnummer enligt EU – Min count 1, Max count 9  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien Finans: Söka igenom innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  Betalkortsnummer –10 min antal, max antal val  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>Storbritannien Personlig information – Online-övningskod (PIOCP)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien PIOCP: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 1, Max count 9  <br/>  Storbritannien National Hälsotjänst Number – Min count 1, Max count 9  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien PIOCP: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 10, Max count any  <br/>  Storbritannien National Hälsotjänst Number – Min count 10, Max count any  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Storbritannien Personligt identifierbar information (PII) Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 1, Max count 9  <br/>  U.S. / Storbritannien Passport Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien PII: Skanna innehåll som delas utanför – stort antal  <br/> | Innehållet innehåller känslig information:  <br/>  Storbritannien National Insurance Number (NINO) – Min count 10, Max count any  <br/>  U.S. / Storbritannien Passport Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>Storbritannien Sekretess och regler för elektronisk kommunikation

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Storbritannien PECR: Söka igenom innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|Storbritannien PECR: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  SWIFT-kod – Min antal 10, Max antal val  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>U.S. Federal Trade Commission (FTC) Consumer Rules

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|AMERIKANSKA FTC-regler: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  U.S. Bank Account Number – Min count 1, Max count 9  <br/>  ABA Routing Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|AMERIKANSKA FTC-regler: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  U.S. Bank Account Number – Min count 10, Max count any  <br/>  ABA Routing Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-financial-data"></a>U.S. Financial Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|U.S. Financial: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  U.S. Bank Account Number – Min count 1, Max count 9  <br/>  ABA Routing Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.S. Financial: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  U.S. Bank Account Number – Min count 10, Max count any  <br/>  ABA Routing Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>U.S. Gramm-Leach-Bliley Act (GLBA)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|U.S. GLBA: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  U.S. Bank Account Number – Min count 1, Max count 9  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 1, Max count 9  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.S. GLBA: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  U.S. Bank Account Number – Min count 10, Max count any  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 10, Max count any  <br/>  U.S. Social Security Number (SSN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>U.S. Health Insurance Act (HIPAA)

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Innehållet matchar U.S. HIPAA  <br/> | Innehåller någon av följande känsliga uppgifter:  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max count any  <br/>  DeA-nummer – Min count 1, Max count any  <br/> **OCH** <br/>  Innehållet innehåller något av följande villkor:  <br/>  Internationella klassificeringar av avnimning (ICD-9-CM) – Min count 1, Max antal  <br/>  Den internationella klassificeringen av första och högsta antal (ICD-10-CM) – Min count 1, Max antal  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
   
## <a name="us-patriot-act"></a>U.S. Patriot Act

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|U.S. Act: Skanna innehåll delat utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  U.S. Bank Account Number – Min count 1, Max count 9  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 1, Max count 9  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.S. Act: Skanna innehåll delat utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  U.S. Bank Account Number – Min count 10, Max count any  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 10, Max count any  <br/>  U.S. Social Security Number (SSN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>U.S. Personally Identifiable Information (PII) Data

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|U.S. PII: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 1, Max count 9  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max antal 9  <br/>  U.S. / Storbritannien Passport Number – Min count 1, Max count 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.S. PII: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  U.S. Individual Taxpayer Identification Number (ITIN) – Min count 10, Max count any  <br/>  U.S. Social Security Number (SSN) – Min count 10, Max count any  <br/>  U.S. / Storbritannien Passport Number – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>U.S. State Breach Notification Laws

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|U.S. State Breach: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 1, max antal 9  <br/>  U.S. Bank Account Number – Min count 1, Max count 9  <br/>  U.S. Driver's License Number – Min count 1, Max count 9  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.S. State Breach: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  Kreditkortsnummer – min antal 10, max antal val  <br/>  U.S. Bank Account Number – Min count 10, Max count any  <br/>  U.S. Driver's License Number – Min count 10, Max count any  <br/>  U.S. Social Security Number (SSN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>U.S. State Social Security Number Confidentiality Laws

|**Regelnamn**|**Villkor  <br/> (inklusive typer av känslig information)**|**Åtgärder**|
|:-----|:-----|:-----|
|Amerikanska SSN-lagar: Skanna innehåll som delas utanför – lågt antal  <br/> | Innehållet innehåller känslig information:  <br/>  U.S. Social Security Number (SSN) – Min count 1, Max antal 9  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> |Skicka ett meddelande  <br/> |
|U.SSN-lagar: Skanna innehåll som delas utanför – högt antal  <br/> | Innehållet innehåller känslig information:  <br/>  U.S. Social Security Number (SSN) – Min count 10, Max count any  <br/>  Innehåll delas med:  <br/>  Personer utanför organisationen  <br/> | Blockera åtkomst till innehåll  <br/>  Skicka ett meddelande  <br/>  Tillåt åsidosättning  <br/>  Kräv justering av affärsrelationer  <br/>  Skicka incidentrapport  <br/> |
   

