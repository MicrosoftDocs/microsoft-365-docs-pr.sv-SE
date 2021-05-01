---
title: Microsoft 365 Business Premium säkerhets- och efterlevnadsfunktioner
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Läs mer om de säkerhetsfunktioner som följer Microsoft 365 Business Premium för att skydda dina data på datorer, telefoner och surfplattor.
ms.openlocfilehash: 974204e100d3228f78406aca4acce67a889b08c3
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113475"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium säkerhets- och efterlevnadsfunktioner

Microsoft 365 Business Premium erbjuder förenklade säkerhetsfunktioner för att skydda dina data på datorer, telefoner och surfplattor.
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 säkerhetsfunktioner i administrationscentret

Du kan hantera många av de Microsoft 365 Business Premium säkerhetsfunktionerna i administrationscentret, vilket ger dig ett förenklat sätt att aktivera eller inaktivera dessa funktioner. I administrationscentret kan du göra följande:
  
- [Ange programhanteringsinställningar för Android- eller iOS-enheter.](app-protection-settings-for-android-and-ios.md) 
    
    De här inställningarna omfattar att ta bort filer från en inaktiv enhet efter en viss tidsperiod, kryptera arbetsfiler, kräva att användarna anger en PIN-kod och så vidare.
    
- [Ange programskyddsinställningar för Windows 10 enheter](protection-settings-for-windows-10-devices.md) . 
    
    De här inställningarna kan tillämpas på företagsdata på både företagsägda och personligt ägda enheter.
    
- [Ange inställningar för enhetsskydd för Windows 10 enheter](protection-settings-for-windows-10-pcs.md) . 
    
    Du kan aktivera [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions) kryptering för att skydda data i händelse av att en enhet försvinner eller blir stulen, och aktivera [Windows Exploit Guard](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) för att ge avancerat skydd mot utpressningstrojaner. 
    
- [Ta bort företagsdata från enheter](remove-company-data.md)
    
    Du kan fjärrensa företagsdata om en enhet försvinner, blir stulen eller om en anställd lämnar företaget.
    
- [Återställ Windows 10 till fabriksinställningarna](reset-devices-to-factory-settings.md) . 
    
    Du kan återställa Windows 10 enheter som har enhetsskyddsinställningar tillämpade på dem.
    
## <a name="additional-security-features"></a>Ytterligare säkerhetsfunktioner 

Avancerade funktioner i Microsoft 365 Business Premium är tillgängliga för att skydda ditt företag mot cyberhot och skydda känslig information.
  
- **[Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    Microsoft Defender för Office 365 skyddar företaget mot avancerade nätfiske- och utpressningstrojaner som är utformade för att avslöja information från anställda eller kunder. Funktionerna omfattar:
    
  - Avancerad genomsökning av bifogade filer och AI-drivna analyser för att identifiera och ta bort skadliga meddelanden.
    
  - Automatiska kontroller av länkar i e-postmeddelanden för att bedöma om de är en del av ett nätfiskeförsök. På så sätt kan du komma åt osäkra webbplatser på ett säkert sätt.

- **[Alla funktioner i Intune i Azure Portal](/mem/intune/fundamentals/what-is-intune)**
    
    Med åtkomst till administrationscentret för Intune i Azure-portalen kan du konfigurera ytterligare säkerhetsfunktioner, till exempel hantering av MacOS-enheter, iPhone- och Android-enheter, tillsammans med avancerad enhetshantering för Windows som inte är tillgängliga via administrationscentret för Microsoft 365.
- **Samma [villkorsstyrda åtkomst](/azure/active-directory/conditional-access/overview) som Azure AD Premium P1-abonnemang**


    Villkorsstyrd åtkomst kan skydda organisationen från inloggningsrisker, åtkomstförsök från ett oväntat nätverk eller språk, åtkomstförsök från riskfyllda enhetstyper och så vidare. Villkorsstyrda åtkomstprinciper tillämpas efter att den första autentiseringen har genomförts, och signaler från den första autentiseringshändelsen används för att avgöra om den försökna åtkomsten ska godkännas, nekas eller om fler bevis (till exempel en andra form av identifiering) krävs.

    De villkorsstyrda åtkomstfunktionerna är:

    - Åtkomst baserat på användarnamn, grupp och roll
    - Access [baserat på ett program](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Access baserat på plats](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  tillåt endast åtkomst från betrodda IP-intervall eller specifika länder 
    - Kräv MFA för åtkomst
    - Blockera åtkomst till program som använder [äldre autentisering](/azure/active-directory/conditional-access/block-legacy-authentication)
    - Kräv att appar använder [Intune-appskydd](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Anpassad autentisering som MFA med tredjepartsleverantörer, till exempel DUO.
   
    Andra funktioner:
    - [Självbetjäning för återställning av](/azure/active-directory/authentication/concept-sspr-customization) lösenord för hybrid-Azure AD
    
## <a name="compliance-features"></a>Efterlevnadsfunktioner

Din Microsoft 365 Business Premium-prenumeration innehåller funktioner som hjälper dig att upprätthålla efterlevnads- och regelstandarder.

- **[Läs mer om skydd mot dataförlust](../compliance/dlp-learn-about-dlp.md))** (DLP). 
    
    Du kan ställa in DLP så att känslig information, t.ex. kreditkortsnummer och personnummer, automatiskt identifieras för att förhindra att de oavsiktligt delar utanför företaget.
    
- **[Exchange Online - arkivering](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online - arkivering-licens gör det enkelt att arkivera meddelanden med kontinuerlig säkerhetskopiering av data. Här lagras alla användares e-postmeddelanden, inklusive borttagna objekt, om de senare behövs för upptäckt eller återställning. Du kan dessutom använda olika bevarandeprinciper för att bevara e-postdata för bevarande av juridiska skäl, eDiscovery eller för att uppfylla efterlevnadskrav.
    
- **[Känslighetsetiketter](../compliance/sensitivity-labels.md)**

   Microsoft 365 Business Premium innehåller alla funktioner i [Azure Information Protection Plan 1.](https://go.microsoft.com/fwlink/p/?linkid=871407) Med den här planen  kan du skapa känslighetsetiketter som gör att du kan styra åtkomsten till känslig information i e-postmeddelanden och dokument med kontroller som "Vidarebefordra inte" och "Kopiera inte". Du kan även klassificera känslig information som "Konfidentiellt" och ange hur klassificerad information kan delas utanför och i företaget. Kryptering i företagsklass är enkel att tillämpa på e-post och dokument för att hålla din information privat. Du kan också installera Azure Information Protection-klient-tillägget för Office program. Mer information finns i [Azure Information Protection Unified Labeling Client](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Under Känslighetsetiketter installerar du **AzInfoProtection_UL.exe**.

Du kan hantera de här funktionerna i &amp; Säkerhetsefterlevnad och administrationscentret för Intune. Med tiden läggs de förenklade kontrollerna till i Microsoft 365 administrationscentret.
  
    
## <a name="faq"></a>Vanliga frågor och svar

 ### <a name="are-these-security-features-available-in-all-markets"></a>Är dessa säkerhetsfunktioner tillgängliga på alla marknader?
  
Ja, dessa funktioner är tillgängliga på alla marknader där Microsoft 365 Business Premium säljs.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hur hittar jag Center för &amp; säkerhetsefterlevnad?
  
1. [Logga in på Microsoft 365 Business Premium](https://portal.microsoft.com/) med dina autentiseringsuppgifter som administratör. 
    
2. I det vänstra navigeringsfältet letar du **reda på Administrationscenter** och expanderar det. 
    
    ![I det vänstra navigeringsfältet i Microsoft 365 väljer du Administrationscenter.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Välj **&amp; Säkerhetsefterlevnad** för att gå till &amp; Säkerhetsefterlevnad.
