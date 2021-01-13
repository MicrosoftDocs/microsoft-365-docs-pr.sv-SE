---
title: Microsoft 365 Business Premium-funktioner för säkerhet och efterlevnad
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Lär dig mer om de säkerhetsfunktioner som medföljer Microsoft 365 Business Premium för att skydda dina data på datorer, telefoner och surfplattor.
ms.openlocfilehash: b7fdd3d7fa25c23ee49ae82aa037588d8fba61a1
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840398"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium-funktioner för säkerhet och efterlevnad

Microsoft 365 Business Premium erbjuder enkla säkerhetsfunktioner som hjälper dig att skydda dina data på PC, telefoner och surfplattor.
    
## <a name="microsoft-365-admin-center-security-features"></a>Säkerhets funktioner för Microsoft 365 Admin Center

Du kan hantera många av Microsoft 365 Business Premium-säkerhetsfunktionerna i administrations centret, som ger dig ett förenklat sätt att aktivera och inaktivera funktionerna. I Admin Center kan du göra följande:
  
- [Ange inställningar för program hantering för Android eller iOS-enheter](app-protection-settings-for-android-and-ios.md) . 
    
    De här inställningarna inkluderar borttagning av filer från en inaktiv enhet efter en viss tids period, kryptering av arbetsfiler, som kräver att användarna ställer in en PIN-kod och så vidare.
    
- [Ange program skydds inställningar för Windows 10-enheter](protection-settings-for-windows-10-devices.md) . 
    
    De här inställningarna kan tillämpas på företags data på både ägda och ägda enheter.
    
- [Ange inställningar för enhets skydd för Windows 10-enheter](protection-settings-for-windows-10-pcs.md) . 
    
    Du kan aktivera [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -kryptering för att skydda data i händelse av att en enhet försvinner eller blir stulen och aktivera [Windows sårbarhets skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) för att ge Avancerat skydd mot utpressnings tro janheten. 
    
- [Ta bort företagsdata från enheter](remove-company-data.md)
    
    Du kan rensa företags data från en fjärrdator om en enhet går förlorad, blir stulen eller en anställd lämnar företaget.
    
- [Återställa Windows 10-enheter till fabriks inställningarna](reset-devices-to-factory-settings.md) . 
    
    Du kan återställa alla Windows 10-enheter som har inställningar för enhets skydd.
    
## <a name="additional-security-features"></a>Ytterligare säkerhetsfunktioner 

Avancerade funktioner i Microsoft 365 Business Premium är tillgängliga för att skydda ditt företag mot cyberhot och skydda känslig information.
  
- **[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Microsoft Defender för Office 365 hjälper dig att skydda ditt företag mot avancerade nätfiske och utpressnings tro Jan attack som är avsedda att äventyra informationen om anställda eller kunder. Funktioner:
    
  - Avancerad bilage genomsökning och AI-drivna analys för att upptäcka och ignorera farliga meddelanden.
    
  - Automatisk sökning efter länkar i e-post för att utvärdera om de ingår i ett nät fiske schema. Det skyddar dig från att komma åt osäkra webbplatser.

- **[Alla funktioner i Intune i Azure-portalen](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Om du har åtkomst till administrations centret för Intune i Azure-portalen kan du konfigurera ytterligare säkerhetsfunktioner, till exempel hantering av MacOS-enheter, iPhone och Android-enheter, tillsammans med avancerad enhets hantering för Windows, som inte är tillgängliga via Microsoft 365 Admin Center.
- **Samma [villkorsstyrda åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) som Azure AD Premium P1-abonnemang**


    Villkorsstyrd åtkomst kan hjälpa till att skydda din organisation från att logga in, åtkomst försök från ett oväntat nätverk eller nationella inställningar, åtkomst försök från riskfyllda enhets typer och så vidare. Principer för villkorsstyrd åtkomst tillämpas efter att den första kontrollen är klar och använder signaler från den första autentiseringsprocessen-händelsen för att avgöra om den försökta åtkomsten ska godkännas, nekas eller om mer bevis (till exempel en andra form av identifiering) krävs.

    Funktionerna för villkorsstyrd åtkomst ingår:

    - Åtkomst baserat på användar namn, grupp och roll
    - Åtkomst [baserat på en app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Åtkomst baserat på plats](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Tillåt endast åtkomst från betrodda IP-adressintervall eller specifika länder 
    - Kräv MFA för åtkomst
    - Blockera åtkomst till program som använder [äldre](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Kräv att appar ska använda [Intune App Protection](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Anpassad verifikation som MFA med leverantörer från tredje part, till exempel DUO.
   
    Andra funktioner:
    - [Självbetjäning för återställning av lösen ord](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) för Azure AD
    
## <a name="compliance-features"></a>Funktioner för efterlevnad

Ditt Microsoft 365 Business Premium-abonnemang innehåller funktioner som hjälper dig att upprätthålla efterlevnad och myndighets standarder.

- **[Översikt över principer för skydd mot data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP). 
    
    Du kan ställa in DLP så att känslig information identifieras automatiskt, till exempel kreditkorts nummer, person nummer och så vidare, för att förhindra att de oavsiktligt delar utanför företaget.
    
- **[Exchange Online - arkivering](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Med en licens för Exchange Online kan meddelanden enkelt arkiveras med kontinuerlig säkerhets kopiering av data. Alla användares e-postmeddelanden lagras, inklusive borttagna objekt, ifall de behövs senare för identifiering eller återställning. Dessutom kan du använda olika principer för bevarande för att bevara e-postdata för rätts tvister, eDiscovery eller för att uppfylla efterföljandekrav.
    
- **[Känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium innehåller alla funktioner i [Azure information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Med det här abonnemanget kan du skapa **känslighets etiketter** som låter dig kontrol lera åtkomsten till känslig information i e-post och dokument, med kontroller som "Vidarekoppla inte" och "Kopiera inte". Du kan också klassificera känslig information som "konfidentiell" och ange hur sekretessbelagda uppgifter kan delas utanför och inom företaget. Det är enkelt att använda kryptering med e-post och dokument för att hålla informationen hemlig. Du kan också installera tilläggsprogrammet Azure information Protection-klient för Office-appar. Mer information finns i artikeln om [enhetlig märknings klient för Azure information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). För känslighets etiketter installerar du **AzInfoProtection_UL.exe**.

Du kan hantera de här funktionerna i säkerhetsrelaterade &amp; Center och i administrations centret för Intune. Över tiden kommer de förenklade kontrollerna att läggas till i administrations centret för Microsoft 365.
  
    
## <a name="faq"></a>Vanliga frågor och svar

 ### <a name="are-these-security-features-available-in-all-markets"></a>Finns de här säkerhetsfunktionerna på alla marknader?
  
Ja, de här funktionerna är tillgängliga på alla marknader där Microsoft 365 Business Premium säljs.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Hur hittar jag säkerhetsrelaterade &amp; Center?
  
1. [Logga in på Microsoft 365 Business Premium](https://portal.microsoft.com/) med dina administratörs uppgifter. 
    
2. I det vänstra navigerings fältet går du till **administrations Center** och expanderar det. 
    
    ![I det vänstra navigerings fältet i administrations centret för Microsoft 365 väljer du administrations Center.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Välj **&amp; säkerhetskompatibilitet** för att gå till säkerhetsrelaterade &amp; Center.
