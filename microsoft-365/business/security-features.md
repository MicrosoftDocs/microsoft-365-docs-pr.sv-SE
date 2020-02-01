---
title: Säkerhets- och efterlevnadsfunktioner för Microsoft 365 Business
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Lär dig mer om säkerhetsfunktionerna som medföljer Microsoft 365 Business.
ms.openlocfilehash: 0e1823374ec1843b6caa3f080393ca013302bf72
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593434"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Säkerhets- och efterlevnadsfunktioner för Microsoft 365 Business

Microsoft 365 Business erbjuder förenklade säkerhetsfunktioner för att skydda dina data på datorer, telefoner och surfplattor.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Säkerhetsfunktioner för Microsoft 365 Business-administrationscenter

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Du kan hantera många av säkerhetsfunktionerna i Microsoft 365 Business i administrationscentret, vilket ger dig ett förenklat sätt att aktivera eller inaktivera dessa funktioner. I administrationscentret kan du göra följande:
  
- [Ange inställningar för programhantering för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md) . 
    
    Dessa inställningar inkluderar att ta bort filer från en inaktiv enhet efter en viss period, kryptera arbetsfiler, som kräver att användarna anger en PIN-kod och så vidare.
    
- [Ange inställningar för programskydd för Windows 10-enheter](protection-settings-for-windows-10-devices.md) . 
    
    Dessa inställningar kan tillämpas på företagsdata på både företagsägda eller personligt ägda enheter.
    
- [Ange enhetsskyddsinställningar för Windows 10-enheter](protection-settings-for-windows-10-pcs.md) . 
    
    Du kan aktivera [BitLocker-kryptering](https://go.microsoft.com/fwlink/p/?linkid=871405) för att skydda data om en enhet försvinner eller blir stulen och aktivera [Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) för att ge avancerat skydd mot ransomware. 
    
- [Ta bort företagsdata från enheter](remove-company-data.md)
    
    Du kan fjärrrensa företagsdata om en enhet försvinner, blir stulen eller en anställd lämnar ditt företag.
    
- [Återställ Windows 10-enheter till fabriksinställningarna](reset-devices-to-factory-settings.md) . 
    
    Du kan återställa alla Windows 10-enheter som har enhetsskyddsinställningar som tillämpas på dem.
    
## <a name="additional-security-features"></a>Ytterligare säkerhetsfunktioner 

Avancerade funktioner i Microsoft 365 Business är tillgängliga för att skydda ditt företag mot cyberhot och skydda känslig information.
  
- **[Avancerat hotskydd för Office 365](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) hjälper till att skydda ditt företag mot sofistikerade nätfiske och ransomware-attacker som utformats för att äventyra medarbetar- eller kundinformation. Funktioner inkluderar:
    
  - Sofistikerad genomsökning av bifogade filer och AI-drivna analyser för att upptäcka och ignorera farliga meddelanden.
    
  - Automatiska kontroller av länkar i e-post för att bedöma om de är en del av ett nätfiskeschema. Detta håller dig säker från att komma åt osäkra webbplatser.

- **[De fullständiga funktionerna för Intune i Azure-portalen](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Med åtkomst till Intune-administrationscentret i Azure-portalen kan du ställa in ytterligare säkerhetsfunktioner, till exempel hantering av MacOS-enheter, iPhone och Android-enheter, tillsammans med avancerad enhetshantering för Windows, som inte är tillgängliga via Microsoft 365 Företagsadministratörscenter.
- **Samma [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) som Azure AD P1-plan**


    Villkorlig åtkomst kan skydda din organisation från inloggningsrisk, komma åt försök från ett oväntat nätverk eller språk, komma åt försök från riskfyllda enhetstyper och så vidare. Principer för villkorlig åtkomst tillämpas efter att den första autentiseringen har slutförts och den använder signaler från den första autentiseringshändelsen för att avgöra om åtkomstförsöket ska godkännas, nekas eller om mer bevis (till exempel en andra form av identifiering) krävs.

    De funktioner för villkorlig åtkomst som ingår är:

    - Åtkomst baserat på användarnamn, grupp och roll
    - Åtkomst [baserat på en app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Åtkomst baserad på plats](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  endast tillåta åtkomst från betrodda IP-intervall eller specifika länder 
    - Kräv MFA för åtkomst
    - Blockera åtkomst till appar som använder [äldre autentiseringBlock](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication) access to apps that use legacy authentication
    - Kräv appar tp använd [Intune app skydd](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Anpassad autentisering som MFA med tredjepartsleverantörer, till exempel DUO.
   
    Andra funktioner:
    - [Återställning av lösenord för självbetjäplikting](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) för hybrid Azure ADSelf-service password reset for hybrid Azure AD
    
## <a name="compliance-features"></a>Kompatibilitetsfunktioner

Din Microsoft 365 Business-prenumeration innehåller funktioner som hjälper dig att upprätthålla efterlevnads- och regelstandarder.

- Översikt över principer för **[dataförlustförebyggande](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Du kan ställa in DLP för att automatiskt identifiera känslig information, till exempel kreditkortsnummer, personnummer och så vidare, för att förhindra att de oavsiktligt delar utanför företaget.
    
- **[Exchange Online - arkivering](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online-arkiveringslicens gör det möjligt att enkelt arkivera meddelanden med kontinuerlig säkerhetskopiering av data. Den lagrar alla en användares e-postmeddelanden, inklusive borttagna objekt, om de behövs senare för upptäckt eller återställning. Dessutom kan du använda olika bevarandeprinciper för att bevara e-postdata för rättstvister, eDiscovery eller för att uppfylla efterlevnadskraven.
    
- **[Markera som känsligt](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business innehåller alla funktioner i [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Med den här planen kan du skapa **känslighetsetiketter** som gör att du kan styra åtkomsten till känslig information i e-post och dokument, med kontroller som "Vidarebefordra inte" och "Kopiera inte". Du kan också klassificera känslig information som "Konfidentiell" och ange hur sekretessbelagd information kan delas utanför och inom företaget. Kryptering av företagsklass är lätt att tillämpa för e-post och dokument för att hålla din information privat. Du kan också installera Azure Information Protection-klienten tillägg för Office-appar. Mer information finns i [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Installera **AzInfoProtection_UL.exe**för känslighetsetiketter .

Du kan hantera dessa &amp; funktioner i säkerhetskompatibilitetscentret och Administrationscenter för Intune. Med tiden läggs de förenklade kontrollerna till i administrationscentret för Microsoft 365 Business.
  
    
## <a name="faq"></a>Vanliga frågor och svar

 ### <a name="are-these-security-features-available-in-all-markets"></a>Är dessa säkerhetsfunktioner tillgängliga på alla marknader?
  
Ja, dessa funktioner är tillgängliga på alla marknader där Microsoft 365 Business säljs.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hur hittar jag &amp; säkerhetskompatibilitetscentret?
  
1. [Logga in på Microsoft 365 Business](https://portal.microsoft.com/) med hjälp av dina administratörsuppgifter. 
    
2. Leta reda på **Administrationscenter** i den vänstra naven och expandera den. 
    
    ![Välj Administrationscenter i det vänstra navi administrationscentret för Microsoft 365.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Välj ** &amp; Säkerhetsefterlevnad** för &amp; att gå till säkerhetsefterlevnadscenter.
