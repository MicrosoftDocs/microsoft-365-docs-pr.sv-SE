---
title: Referensinformation om principtips för dataförlustskydd
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: Lär dig hur du lägger till ett principtips i en DLP-princip (Data Loss Prevention) om att de arbetar med innehåll som står i konflikt med en DLP-princip.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086765"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Referensinformation om principtips för dataförlustskydd

Tips för DLP-Outlook i Web Access stöds för alla villkor, undantag och åtgärder som är tillämpliga för Exchange-arbetsbelastningar i en DLP-princip, förutom följande:

**Villkor:**

- Sender Is
- Sender Domain Is
- Mottagaren är medlem i
- Sidhuvudet innehåller ord eller fraser
- Sidhuvud matchar mönster
- Dokumentstorlek är lika med eller större än
- Meddelandetypen är
- Meddelandets prioritet är
- Innehållsteckenuppsättning innehåller ord
- Ämne eller brödtext innehåller ord eller fraser
- Mönster för ämne eller brödtext
- Innehållsteckenuppsättning innehåller ord
- Innehåll tas emot från
- Har avsändaren åsidosättt principtipset
- Meddelandestorlek är lika med eller större än
- Sender AD-attributet innehåller ord eller fraser
- Ad-sender-attributet matchar mönster
- Dokumentinnehållet innehåller ord eller fraser
- Dokumentinnehåll matchar mönster

**Åtgärder:**

- Vidarebefordra meddelandet för godkännande till avsändarens chef
- Vidarebefordra meddelandet för godkännande till vissa godkännare
- Omdirigera meddelandet till specifika användare
- Lägga till mottagare i Rutan Till
- Lägga till mottagare i rutan Kopia
- Lägga till mottagare i rutan Hemlig kopia
- Lägga till avsändarens chef som mottagare
- Lägga till HTML-ansvarsfriskrivning
- Förbereda ämnet för e-post
- Ta bort meddelandekryptering och rättighetsskydd i O365

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 och senare har stöd för att visa principtips för bara vissa villkor och undantag

I Outlook 2013 och senare stöds för närvarande policytips för principer som inte innehåller några villkor eller undantag från nedanstående villkor och motsvarande undantag:

- Innehållet innehåller (fungerar endast för typer av känslig information. Känslighetsetiketter stöds inte)
- Innehåll delas

Observera att alla villkor fungerar för e-postmeddelanden som Outlook i klientappen, där de matchar innehåll och tillämpar skyddsåtgärder på innehåll. Men det går inte att visa principtips för användare för villkor som används utöver de som nämns ovan.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 och senare samt Office-program på skrivbordet som visar principtips för endast vissa typer av känslig information

Följande är en lista över de in alltid använda typer av känslig information som identifieras för visning av DLP-principtips i Outlook på skrivbordet (2013 och senare) och Office-program (Word, Excel, PowerPoint) på skrivbordet:

- ABA-routningsnummer
- Argentina National Identity (DNI) Number
- Bank Account Number för Australien
- Australiens medicinska kontonummer
- Australia Passport Number
- Australiens skattenummer
- Autentiseringsnyckel för Azure DocumentDB  
- Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng  
- Azure IoT-anslutningssträng  
- Lösenord för Inställning av Azure-publicering  
- Azure Redis Cache-anslutningssträng  
- Azure SAS  
- Azure Service Bus-anslutningssträng  
- Azure Storage Kontonyckel  
- Azure Storage Kontonyckel (allmän)  
- Belgiens nationalnummer
- Brasilien CPF-nummer
- Brazil Legal Entity Number (CNPJ)
- Brazil National ID Card (RG)
- Bank Account Number för Kanada
- Kanadas driver's License Number
- Kanada Hälsotjänst Kanada
- Canada Passport Number
- Canada Personal Health Identification Number (PHIN)
- Canada Social Insurance Number
- Chile Identity Card Number
- China Resident Identity Card (Folkrepubliken Kina) Nummer
- Kreditkortsnummer
- Kroatiens identitetskortsnummer  
- Kroatiens OIB-nummer (Personal Identification)  
- Tjeckiska Personliga identitetsnummer  
- Danmarks personliga id-nummer
- Tvingande Enforcement Agency (DEA) Number
- Betalkortsnummer (EU)
- EU:s körkortsnummer  
- EU National Identification Number  
- EU Passport Number  
- SOCIAL SECURITY Number (SSN) eller motsvarande ID  
- EU:s skatteidentifieringsnummer (TIN)  
- Finlands national-ID
- Finland Passport Number
- Frankrikes licensnummer
- France National ID Card (CNI)
- France Passport Number
- France Social Security Number (INSEE)
- Tyskt körkortsnummer
- Tyska Passport Number
- Id Card Number för Tyskland
- Greklands national-ID-kort  
- Hong Kong Identity Card (HKID)-nummer
- Indiens permanenta kontonummer (PAN)
- India Unique Identification (Aadhaar) Number
- Indonesia Identity Card-nummer (KTP)
- International Banking Account Number (IBAN)
- Internationell klassificering av avnärende (ICD-10-CM)  
- Internationell klassificering av tidsklassificering (ICD-9-CM)  
- IP-adress
- Ireland Personal Public Service -nummer (PPS) 
- Israels bankkontonummer
- Israels national-ID
- Italiens licensnummer
- Japan Bank Account Number
- Japan Driver's License Number
- Japan Passport Number
- Invånarregistreringsnummer för Japan
- Japan Social Insurance Number (SIN)
- Japanska Residence Card Number
- Malaysia Identity Card Number
- Nederländska medborgares servicenummer (BSN)  
- New Zealand Ministry of Health Number
- Norges identitetsnummer  
- Philippines Unified Multi-Purpose ID Number
- Polens identitetskort
- Polens National ID (PESEL)
- Polen-pass
- Portugal, kreditkortsnummer
- Saudiarabiens national-ID
- Singapore National Registration Identity Card (NRIC) Number
- South Africa Identification Number  
- Sydkoreas invånarregistreringsnummer
- Spain Social Security Number (SSN)
- SQL Server Anslutningssträng  
- National ID för Sverige
- Sverige Passport Number
- SWIFT-kod
- Taiwan National ID
- Taiwan Passport Number
- Taiwan Resident Certificate (ARC/TARC)
- Identifieringskod för thailändska
- Turkiska National Identification Number
- Storbritannien Driver's License Number
- Storbritannien E-nummer för att samla in
- Storbritannien National Hälsotjänst Number
- Storbritannien National Insurance Number (NINO)
- U.S. / Storbritannien Passport Number
- U.S. Bank Account Number
- U.S. Driver's License Number
- U.S. Individual Taxpayer Identification Number (ITIN)
- U.S. Social Security Number (SSN)

Observera att anpassade typer av känslig information även stöds för DLP-principtips, utöver de för in visna typerna av känslig information.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Dataförlustskydd på slutpunktsenheter har stöd för principtips för endast vissa typer av känslig information

Listan över inringningstyper för känslig information som identifieras i dokument som lagras på slutpunktsenheter är följande:

- ABA-routningsnummer 
- Argentina National Identity (DNI) Number 
- Bank Account Number för Australien 
- Australiens medicinska kontonummer 
- Australia Passport Number 
- Australiens skattenummer 
- Australiensiska företagsnummer 
- Australiensiska företags nummer 
- Österrikes registreringsnummer 
- Österrike-identitetskort 
- Österrike Passport Number 
- Österrike, social security number 
- Österrike skatteidentifieringsnummer 
- Österrike , momsregistreringsnummer 
- Autentiseringsnyckel för Azure DocumentDB 
- Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng 
- Azure IoT-anslutningssträng 
- Lösenord för Inställning av Azure-publicering 
- Azure Redis Cache-anslutningssträng 
- Azure SAS 
- Azure Service Bus-anslutningssträng 
- Azure Storage Kontonyckel 
- Azure Storage Kontonyckel (allmän) 
- Belgien Driver's License Number 
- Belgiens nationalnummer 
- Belgien Passport Number 
- Belgium Value Added Tax Number 
- Brasilien CPF-nummer 
- Brazil Legal Entity Number (CNPJ) 
- Brazil National ID Card (RG) 
- Bulgariens registreringsnummer 
- Bulgarien Passport Number 
- Bulgariens enhetliga civilnummer 
- Bank Account Number för Kanada 
- Kanadas driver's License Number 
- Kanada Hälsotjänst Kanada 
- Canada Passport Number 
- Canada Personal Health Identification Number (PHIN) 
- Canada Social Insurance Number 
- Chile Identity Card Number 
- China Resident Identity Card (Folkrepubliken Kina) Nummer 
- Kreditkortsnummer 
- Kroatiens licensnummer 
- Kroatiens identitetskortsnummer 
- Kroatiens National ID-kortnummer 
- Kroatien Passport Number 
- Kroatiens OIB-nummer (Personal Identification) 
- CSCAN-AZURE0060 Azure Storage signatur för delad åtkomst 
- CSCAN-GENERAL0140 allmän symmetrisk nyckel 
- Cyperns drivrutinslicensnummer 
- Cypern-identitetskort 
- Cypern Passport Number 
- Cyperns skatteidentifieringsnummer 
- Tjeckiska driver's License Number 
- Tjeckiska Personliga identitetsnummer 
- Tjeckien Passport Number 
- Danmarks körkortsnummer 
- Danmark Passport Number 
- Danmarks personliga id-nummer 
- Tvingande Enforcement Agency (DEA) Number 
- Estlands licensnummer 
- Estland Passport Number 
- Estland – personidentifieringskod 
- Betalkortsnummer (EU) 
- EU:s körkortsnummer 
- EU National Identification Number 
- EU Passport Number 
- SOCIAL SECURITY Number (SSN) eller motsvarande ID 
- EU:s skatteidentifieringsnummer (TIN) 
- Finland Driver's License Number 
- Finland European Health Insurance Number 
- Finlands national-ID 
- Finland Passport Number 
- Frankrikes licensnummer 
- France Health Insurance Number 
- France National ID Card (CNI) 
- France Passport Number 
- France Social Security Number (INSEE) 
- France Tax Identification Number (numéro SPI.) 
- France Value Added Tax Number 
- Tyskt körkortsnummer 
- Tyska Passport Number 
- Id Card Number för Tyskland 
- Tysklands skatteidentifieringsnummer 
- Värdeskattenummer för Tyskland 
- Greklands körkortsnummer 
- Greklands national-ID-kort 
- Greklands passnummer 
- Greklands social securitynummer (AMKA) 
- Grekiska skatteidentifieringsnummer 
- Hong Kong Identity Card (HKID)-nummer 
- Ungerska social security number (TAD) 
- Ungerska nummer med moms 
- Ungerns registreringsnummer 
- Ungern Passport Number 
- Ungerns personliga id-nummer 
- Ungerns skatteidentifieringsnummer 
- Indiens permanenta kontonummer (PAN) 
- India Unique Identification (Aadhaar) Number 
- Indonesia Identity Card-nummer (KTP) 
- International Banking Account Number (IBAN) 
- Internationell klassificering av avnärende (ICD-10-CM) 
- Internationell klassificering av tidsklassificering (ICD-9-CM) 
- IP-adress 
- Ireland Driver's License Number 
- Ireland Passport Number 
- Ireland Personal Public Service -nummer (PPS) 
- Israels bankkontonummer 
- Israels national-ID 
- Italiens licensnummer 
- Italiens räkenskapskod 
- Italy Passport Number 
- Italy Value Added Tax Number 
- Japan Bank Account Number 
- Japan Driver's License Number 
- Japan Passport Number 
- Invånarregistreringsnummer för Japan 
- Japan Social Insurance Number (SIN) 
- Japanska My Number Corporate 
- Japanska, Mitt nummer Personligt 
- Japanska Residence Card Number 
- Lettlands drivrutinslicensnummer 
- Lettlands passport number 
- Personlig kod för Lettland 
- Litauens licensnummer 
- Litauen Passport Number 
- Litauen – personlig kod 
- Luxemburg-drivrutinens licensnummer 
- Luxemburg National Identification Number (naturliga personer) 
- Luxemburg National Identification Number (icke-naturliga personer) 
- Luxemburg Passport Number 
- Malaysia Identity Card Number 
- Malta Driver's License Number 
- Malta-identitetskortsnummer 
- Malta Passport Number 
- Maltas skattenummer 
- Nederländska medborgares servicenummer (BSN) 
- Nederländska driver's License Number 
- Nederländerna Passport Number 
- Nederländska skatteidentifieringsnummer 
- Nederländska värdeskattenummer 
- Bankkontonummer för Nya Zeeland 
- New Zealand Driver License Number 
- New Zealand Inland Revenue number 
- New Zealand Ministry of Health Number 
- New Zealand Social Enl. Nummer 
- Norges identitetsnummer 
- Philippines Unified Multi-Purpose ID Number 
- Polens licensnummer 
- Polens identitetskort 
- Polens National ID (PESEL) 
- Polen-pass 
- Polens skatteidentifieringsnummer 
- Polska REGON-nummer 
- Portugal, kreditkortsnummer 
- Portugal Driver's License Number 
- Portugal Passport Number 
- Portugals skatteidentifieringsnummer 
- Rumäniens registreringsnummer 
- Rumänien Passport Number 
- Rumäniens personliga numeriska kod (CNP) 
- Ryska passnummer (inrikes) 
- Ryska Passport Number (internationellt) 
- Saudiarabiens national-ID 
- Singapore National Registration Identity Card (NRIC) Number 
- Slovakiens licensnummer 
- Slovakien Passport Number 
- Slovakiens personliga nummer 
- Sloveniens körkortsnummer 
- Slovenien Passport Number 
- Sloveniens skatteidentifieringsnummer 
- Slovenska unik master number 
- South Africa Identification Number 
- Sydkoreas invånarregistreringsnummer 
- Spanien DNI 
- Spaniens licensnummer 
- Spain Passport Number 
- Spain Social Security Number (SSN) 
- Spaniens skatteidentifieringsnummer 
- SQL Server Anslutningssträng 
- Sverige driver's License Number 
- National ID för Sverige 
- Sverige Passport Number 
- Skatteidentifieringsnummer i Sverige 
- SWIFT-kod 
- Swiss Social Security Number AHV 
- Taiwan National ID 
- Taiwan Passport Number 
- Taiwan Resident Certificate (ARC/TARC) 
- Identifieringskod för thailändska 
- Turkiska National Identification Number 
- Storbritannien Driver's License Number 
- Storbritannien E-nummer för att samla in 
- Storbritannien National Hälsotjänst Number 
- Storbritannien National Insurance Number (NINO) 
- Storbritannien Unique Taxpayer-referensnummer 
- U.S. / Storbritannien Passport Number 
- U.S. Bank Account Number 
- U.S. Driver's License Number 
- U.S. Individual Taxpayer Identification Number (ITIN) 
- U.S. Social Security Number (SSN) 
- Ukraina Passport Number (inrikes) 
- Ukraina Passport Number (internationellt) 
 
Observera att anpassade typer av känslig information också identifieras, utöver de för insmådde typerna av känslig information

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Tips om stödmatris för DLP-principen i Microsoft-appar

|**App och plattform**|**Stöd för DLP-principtips**|**Typer av känslig information som stöds**|**Predikat och åtgärder som stöds**|**Kommentarer**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alla|Delmängd|Se [referens för policytips för skydd mot dataförlust](#data-loss-prevention-policy-tips-reference)|
|**Outlook Win32 (Outlook 2013 och därefter)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Delmängd|Delmängd|Se [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) och senare funktioner med principtips för bara vissa villkor och undantag, [och i Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare samt i Office-program på skrivbordet visas principtips för endast vissa typer av känslig information, information om stöd för typer av känslig information och vilka DLP-villkor och åtgärder som stöds för att visa DLP-principtips på Outlook Win32.|
|**Outlook Mobil (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga|DLP-principtips stöds inte på Outlook mobil|
|**Sharepoint Online/One Drive för företag-webbklient**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alla|Alla SPO/ODB-predikat och åtgärder i DLP||
|**Sharepoint Win32/ One Drive för företag Win32-klient**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga|Tips för DLP-princip stöds inte i Sharepoint- OneDrive-klientprogram på datorn|
|**Word, Excel, PowerPoint webbklient**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alla|Alla SPO/ODB-predikat och åtgärder i DLP|Tips för DLP-princip stöds om dokumentet ligger på SPO- eller ODB-webbappen och DLP-principen redan har stämplats.|
|**Word Excel PowerPoint Mobile klient**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga|Tips för DLP-princip stöds inte i mobilappar för Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Alla|Alla Teams i DLP-principen|Principtips visas när ett meddelande flaggas som "Det här meddelandet har flaggats. Vad kan jag göra?" När användaren klickar på länken kan han eller hon granska de typer av känslig information som upptäckts och åsidosätta eller rapportera ett problem om administratören tillåtit det. Observera att inga principtips visas för filer. När mottagaren försöker komma åt dokumentet kan de få åtkomst nekad om det inte är tillåtet.|
|**Win32-slutpunktsenheter**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Delmängd|Alla endpoint DLP-predikat och åtgärder i DLP-princip|Se [Skydd mot dataförlust i Slutpunkt som stöder principtips för endast vissa typer av känslig information](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac-enheter**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga|Principer för skydd mot dataförlust är i dag inte tillgängliga på Mac-enheter|
|**Molnbaserade appar från tredje part**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga|Policytips för skydd mot dataförlust stöds inte i molnappar från tredje part|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Inga|Inga||
|**Word-, Excel-, PowerPoint Win32-klient**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Delmängd|Delmängd|Se [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare samt stöd för Office-program på stationära datorer med policytips för endast vissa typer av känslig information för listan över typer av känslig information som stöds</br></br>Principtips för WXP-klientprogram fungerar för dokument som lagras på Sharepoint Online- eller One Drive för företag-webbplatser för alla DLP-principer som har exakt nedanstående eller en delmängd villkor eller åtgärder i DLP-principen:</br> <ul><li>Innehållet innehåller typer av känslig information</li><li>Åtkomstomfattning (innehåll delas internt/externt)</li><li>Meddela användare (principtips/användarmeddelanden)</li><li>Blockera alla</li><li>Incidentrapporter</li></ul></br> Om det finns andra villkor eller åtgärder visas inte DLP-principtipset för den principen i skrivbordsapparna i Word, Excel eller PowerPoint.</br>Mer [information finns i Excel, PowerPoint och Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)|
||||||
