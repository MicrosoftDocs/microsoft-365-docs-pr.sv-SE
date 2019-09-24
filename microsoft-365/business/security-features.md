---
title: Microsoft 365 funktioner för Företagssäkerhet och efterlevnad
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Lär dig mer om säkerhetsfunktioner som följer med Microsoft 365 Business.
ms.openlocfilehash: 6b8fc215b95913e1beef3a3715119b947a7af406
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37121167"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 funktioner för Företagssäkerhet och efterlevnad

Microsoft 365 Business erbjuder förenklade säkerhetsfunktioner som hjälper dig att skydda dina data på datorer, mobiler och surfplattor.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Säkerhets funktioner i Microsoft 365 Business Admin Center

[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Du kan hantera många av funktionerna i Microsoft 365 Business Security i administratörscenter, vilket ger dig ett förenklat sätt att aktivera eller inaktivera dessa funktioner. I administratörscenter kan du göra följande:
  
  
- [Ange inställningar för programhantering för Android-eller iOS-enheter](app-protection-settings-for-android-and-ios.md) . 
    
    Dessa inställningar inkluderar att ta bort filer från en inaktiv enhet efter en viss period, kryptera arbetsfiler, kräva att användare ange en PIN-kod, etc.
    
- [Ange inställningar för programskydd för Windows 10-enheter](protection-settings-for-windows-10-devices.md) . 
    
    Dessa inställningar kan tillämpas på företagsdata på både företagsägda eller personligt ägda enheter.
    
- [Ange inställningar för enhetsskydd för Windows 10-enheter](protection-settings-for-windows-10-pcs.md) . 
    
    Du kan aktivera [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -kryptering för att skydda data om en enhet tappas bort eller stjäls och aktivera [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) för att tillhandahålla Avancerat skydd mot ransomware. 
    
- [Ta bort företagsdata från enheter](remove-company-data.md)
    
    Du kan fjärrensa företagsdata om en enhet förloras, stjäls eller om en medarbetare lämnar företaget.
    
- [Återställ Windows 10-enheter till fabriksinställningarna](reset-devices-to-factory-settings.md) . 
    
    Du kan återställa alla Windows 10-enheter som har inställningar för enhetsskydd som tillämpas på dem.
    
## <a name="additional-security-features"></a>Ytterligare säkerhetsfunktioner 

Avancerade funktioner i Microsoft 365 Business är tillgängliga för att hjälpa dig att skydda ditt företag mot cyberhot och skydda känslig information.
  
- **[Office 365 Avancerat skydd mot hot](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) hjälper till att skydda ditt företag mot sofistikerade phishing-och Ransomware-attacker för att kompromettera medarbetar-eller kundinformation. Funktioner inkluderar:
    
  - Sofistikerad skanning av bilagor och AI-driven analys för att upptäcka och ignorera farliga meddelanden.
    
  - Automatisk kontroll av länkar i e-post för att bedöma om de är en del av ett phishing-system. Detta håller dig säker från att komma åt osäkra webbplatser.

- **[Alla funktioner i Intune i Azure Portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Åtkomst till Intune administratörscenter i Azure-portalen kan du ställa in ytterligare säkerhetsfunktioner, till exempel hantering av MacOS-enheter, iPhone och Android-enheter tillsammans med avancerad enhetshantering för Windows, som inte är tillgängliga via Microsoft 365 Business administratörscenter.
- **Samma [villkorlig åtkomst](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview) som Azure AD P1-plan**

    Villkorlig åtkomst kan bidra till att skydda din organisation från inloggningsrisk, åtkomstförsök från ett oväntat nätverk eller nationella inställningar, åtkomstförsök utgör riskfyllda enhetstyper och så vidare. Principer för villkorlig åtkomst tillämpas när den första autentiseringen har slutförts och använder signaler från den första autentiseringshändelsen för att avgöra om försök till åtkomst ska godkännas, neka eller f mer bevis (till exempel andra form av identifiering) är Krävs.

    De funktioner för villkorlig åtkomst som ingår är:

    - Åtkomst baserat på användarnamn, grupp och roll
    - Åtkomst [baserat på en app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Åtkomst baserat på plats](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Tillåt endast åtkomst från betrodda IP-adressintervall eller specifika länder 
    - Kräv MFA för åtkomst
    - Blockera åtkomst till appar som använder [äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Kräv appar TP Använd [Intunes Appskydd](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Anpassad autentisering som MFA med tredjepartsleverantörer, till exempel DUO.
   
    Andra funktioner:
    - [Självbetjäning för återställning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) för Hybrid Azure AD
    
## <a name="compliance-features"></a>Efterlevnadsfunktioner

Din Microsoft 365 Business-prenumeration innehåller funktioner som hjälper dig att upprätthålla efterlevnad och lagstadgade standarder.

- **[Översikt över policyer för dataförlustskydd](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Du kan ställa in att DLP automatiskt ska identifiera känslig information, som kreditkortsnummer, personnummer etc. för att förhindra oavsiktlig delning utanför företaget.
    
- **[Exchange Online - arkivering](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Med Exchange Online-Arkiveringslicens kan meddelanden enkelt arkiveras med kontinuerlig säkerhetskopiering. Den lagrar alla användares e-postmeddelanden, inklusive borttagna objekt, om de behövs senare för upptäckt eller återställning. Dessutom kan du använda olika bevarandeprinciper för att bevara e-data för rättstvister håller, eDiscovery eller för att uppfylla efterlevnadskrav.
    
- **[Azure information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    Informationsskydd hjälper dig att kontrollera åtkomsten till känslig information i e-post och dokument med kontroller som "vidarebefordra inte" och "Kopiera inte". Du kan också klassificera känslig information som "konfidentiell" och ange hur sekretessbelagd information kan delas utanför och inom företaget. Kryptering i företagsklass är lätt att använda för e-post och dokument för att hålla din information privat. Microsoft 365 Business innehåller alla funktioner i [Azure information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Du kan också installera Azure information Protection-klienttillägget för Office-appar. Mer information finns i [Azure information Protection-klientens Administratörsguide](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).

Du kan hantera dessa funktioner i säkerhets &amp; regelefterlevnadscenter och Intune administratörscenter. Med tiden kommer de förenklade kontrollerna att läggas till i Microsoft 365 Business Admin Center.
  
    
## <a name="faq"></a>Vanliga frågor och svar

 ### <a name="are-these-security-features-available-in-all-markets"></a>Är säkerhets funktionerna tillgängliga på alla marknader?
  
Ja, dessa funktioner är tillgängliga på alla marknader där Microsoft 365 Business säljs.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hur hittar jag säkerhets &amp; regelefterlevnadscentret?
  
1. [Logga in på Microsoft 365 Business](https://portal.microsoft.com/) med administratörsautentiseringsuppgifter. 
    
2. Leta upp **Administrationscenter** i det vänstra navigeringsfältet och expandera det. 
    
    ![I det vänstra navigeringsfältet i Microsoft 365 administratörscenter väljer du Administrationscenter.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Välj **säkerhetsefterlevnad &amp; ** att gå till &amp; Security regelefterlevnadscenter.