---
title: Microsoft 365 Technology-kontroller
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller en översikt över de verktyg och teknologier som används av Microsoft för teknik kontroll i Microsoft 365.
ms.openlocfilehash: 66faac9c045dd9b6f6c0c7ea29ca1570e3ad8e19
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332706"
---
# <a name="microsoft-365-technology-controls"></a>Microsoft 365 Technology-kontroller 

Microsoft använder flera verktyg och teknologier för att kontrol lera, hantera och granska åtkomst till kunddata i sina online tjänster. Dessa gäller för Exchange Online, SharePoint Online, låsning och kund lås, multifaktorautentisering med mera. Yammer använder liknande kontroller som beskrivs i [Enterprise Access-kontroller för Yammer](microsoft-365-yammer-enterprise-access-controls.md).

Microsoft 365-tekniker har ingen ständig åtkomst till Microsoft 365-kunddata. Tekniker måste gå igenom godkännande processen för Microsoft för att få till gång till kunddata för tjänste åtgärder. Om kundernas licenser för funktionen för kund låsning för Exchange Online och SharePoint Online krävs kund godkännande. Efter godkännande har tjänst-specifika administratörs konton just nu i sin egen åtkomst för uppgifter som krävs av tjänst förfrågan.

## <a name="lockbox-and-customer-lockbox"></a>Låsning av och kund lås

Trots detta kan en kund begära hjälp från Microsoft som visar kund innehåll till en Microsoft-tekniker. För att styra åtkomsten till Exchange Online använder Microsoft ett Access-kontrollpanelen som kallas för låsning. Innan någon Microsoft-ingenjör ansluter till alla Exchange Online-eller SharePoint online-system eller-data, måste de skicka en åtkomstbegäran med lås. Alla tjänst förfrågningar för Exchange Online och SharePoint Online hanteras av det säkra systemet. Med både lås-och kund lås kan all godkänd åtkomst spåras till en unik användare och gör det möjligt för ingenjörerna att hantera kunddata.

> [!NOTE]
> Exchange Online innehåller alla Skype för företag-data som lagras i användar post lådor. Skype för företag-täckning inkluderar inte inspelningar av Skype-möte eller innehåll som laddas upp till möten av användare. SharePoint Online innehåller OneDrive för företag.

I säkerhets processen behandlas förfrågningar om behörigheter som gör det möjligt för ingenjörer för tekniker att utföra drift och administrativa funktioner i tjänsten. Tekniker skickar förfrågningar via låst och en Microsoft-chef måste godkänna begäran innan teknikern kan komma åt kunddata. Efter chefens godkännande har teknikern tidsbegränsat och begränsad åtkomst till kunddata för att fungera på kundens problem.

Med Customer lock for Microsoft 365 kan du uppfylla kraven på efterlevnad om du behöver anvisningar för explicit åtkomst godkännande. Detta är ett krav för vissa efterföljandekrav, till exempel FedRAMP och HIPAA. Med Customer lock-filmeddelandet får du ett godkännande och ger dig möjlighet att kontrol lera godkännandet av Microsoft Access till ditt Exchange Online-eller SharePoint Online-innehåll för tjänste åtgärder.

I den sällsynta förekomsten när en Microsoft service-tekniker behöver åtkomst till dina data, ger du endast åtkomst till de data som krävs för att lösa problemet och under en begränsad tid. Om du nekar en åtkomstbegäran har Microsoft-teknik inte till gång till ditt innehåll och kan inte slutföra tjänst åtgärderna. Om du godkänner begäran har Microsoft-tekniker begränsad till gång till innehållet genom övervakade och begränsade hanterings gränssnitt.

Åtgärder som utförs av support teknikern loggas för gransknings ändamål och är tillgängliga via [API för hanterings aktiviteten för Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) och [säkerhets-och efterlevnadsprinciper](https://protection.office.com/).

>[!NOTE]
> Det går att komma åt kund i [Microsoft 365 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) som ett tilläggsprogram. Mer information finns i [Microsoft 365 Customer Lockes-begäranden](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2).

## <a name="just-in-time-access"></a>Direkt åtkomst

Microsoft använder JIT-principen (just-in-Time) för Microsoft 365 för att minska risken för manipulering av obehöriga intrång och laterala attacker. JIT tar bort permanent administrativ åtkomst till tjänster och ersätter avrop med möjligheten att på begäran kunna utöka dem till dem. Om du tar bort beständiga åtkomst rättigheter från administratörer är det bara att ange autentiseringsuppgifter när de behövs och minskar riskerna för att stjäla autentiseringsuppgifter.

Modellen med JIT-åtkomst kräver att ingenjörerna begär utökade privilegier under en begränsad tid för att utföra administrativa uppgifter. Dessutom använder tekniker tillfälliga konton som har skapats med dator-genererade komplexa lösen ord och endast tilldelade de roller som gör det möjligt för dem att utföra nödvändiga uppgifter. Den administrativa åtkomst som beviljats av låsning är till exempel tidsbunden och hur lång tid åtkomst som ges beror på den begärda rollen. En ingenjör anger den tid som krävs för att få åtkomst till det säkra systemet. Låsnings systemet nekar förfrågningar när den begärda tiden överskrider den maximalt tillåtna tiden för höjningen. Efter förfallo datum tas administrativ åtkomst bort och det tillfälliga kontot upphör.

Vid godkännande och godkänd för åtkomst får tekniker ett engångs administratörs lösen ord som genereras av auktoriserings systemet. Nya lösen ord skapas varje gång en begäran om förhöjd åtkomst godkänns. Lösen ordet kopieras till ett lösen ord som är säkert, är skilt från ingenjörs uppgifterna för Microsofts företags miljö och är bra för den godkända upphöjda Access-sessionen.

## <a name="constrained-management-interfaces"></a>Gränssnitt för begränsning av begränsningar

Tekniker använder två hanterings gränssnitt för att utföra administrativa uppgifter: fjärr skrivbord via säkra Terminal Service gateways (TSGs) och Remote PowerShell. I dessa hanterings gränssnitt kan program varu principer och åtkomst kontroller hantera viktiga begränsningar för vilka program som körs och vilka kommandon och cmdlets som är tillgängliga.

Microsoft 365-servrar begränsar samtidiga sessioner till en session administratör för enskilda tjänster per server. TSGs tillåter endast en enda samtidig session för användare och tillåter inte flera sessioner. Med en enda session per server kan TSGs tillåta att administratörer för Microsoft 365-tjänsten ansluter till flera servrar samtidigt så att administratörer effektivt kan utföra sina uppgifter. Service team administratörer har ingen behörighet till TSGs själva. TSG används endast för att tillämpa multifaktorautentisering (MFA) och krypterings krav. När Service team administratören ansluter till en specifik server via en TSG, använder den specifika servern en sessionsgräns per administratör.

Användnings begränsningar och anslutnings-och konfigurations krav för Microsoft 365-personal upprättas av grup principer för Active Directory. Dessa principer innehåller följande egenskaper:

- TSGs Använd endast [FIPS](https://www.microsoft.com/TrustCenter/Compliance/FIPS) 140-2-verifierade kryptering.
- TSG sessioner från och med 30 minuters inaktivitet.
- TSG sessioner loggas ut automatiskt efter 24 timmar.

Anslutningar till TSGs kräver också MFA med ett separat fysiskt smartkort och ett konto skilt från ingenjörens Microsoft företags autentiseringsuppgifter. Tekniker ges olika smartkort för olika plattformar och hemligheter för att hantera autentisering. TSGs Använd Active Directory-grupprinciper för att styra vem som kan logga in på fjärrservrar, antalet tillåtna sessioner och inställningar för inaktivitet. Ytterligare principer begränsa åtkomst till tillåtna program och begränsa Internet åtkomst.

Utöver fjärråtkomst med speciellt konfigurerade TSGs tillåter Exchange Online användare med rollen service ingenjörs åtgärder för att komma åt vissa administrativa funktioner på produktions servrar med hjälp av Remote PowerShell. För att göra detta måste användaren vara behörig för skrivskyddad åtkomst till Microsoft 365-produktions miljön. Behörighets höjning är aktive rad på samma sätt som den är aktive rad för TSGs med hjälp av processen.

För fjärråtkomst har varje datacenter en belastningsutjämnad virtuell IP-adress som fungerar som en enskild åtkomst punkt. De tillgängliga cmdlets för fjärr-PowerShell är baserade på behörighets nivån som identifieras i åtkomst begärndet under autentiseringsprocessen. Dessa cmdletar tillhandahåller den enda administrativa funktionalitet som användarna ansluter med den här metoden. Fjärrpowershell begränsar vilka kommandon som är tillgängliga för teknikern och är baserat på åtkomst nivån som bearbetas via processen. Till exempel i Exchange Online kan get-postlådan vara tillgänglig, men det går inte att ange-post lådan.
