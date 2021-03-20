---
title: Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365
description: Hur du omdirigerar konton och sessioner från Defender för Slutpunkt till Säkerhetscenter för Microsoft 365.
keywords: Microsoft 365 Säkerhetscenter, Komma igång med Microsoft 365 säkerhetscenter, omdirigering av säkerhetscenter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bdad55a98dba868d45ecea383ba379108ee5305a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906764"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**
- Microsoft 365 Defender
- Defender för Endpoint

I enlighet med Microsofts övergripande metod för skydd mot hot med SIEM och utökad identifiering och svar (XDR) har vi namnrebranderat Microsoft Defender Advanced Threat Protection som Microsoft Defender för Endpoint och enhetligt det till en enda integrerad portal – Microsoft 365 säkerhetscenter.

I den här guiden förklaras hur du dirigerar konton till Microsoft 365 säkerhetscenter genom att aktivera automatisk omdirigering från den tidigare Microsoft Defender för Endpoint-portalen (securitycenter.windows.com eller securitycenter.microsoft.com) till Microsoft 365-portalen för säkerhetscenter (security.microsoft.com).

> [!NOTE]
> Microsoft Defender för slutpunkt i Säkerhetscenter i Microsoft 365 har stöd för att bevilja åtkomst till tjänstleverantörer av hanterade säkerhetstjänster [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) på samma sätt som åtkomst beviljas i [Microsoft Defender säkerhetscenter.](./mssp-access.md)

## <a name="what-to-expect"></a>Vad du kan förvänta dig
När automatisk omdirigering har aktiverats dirigeras konton med åtkomst till den tidigare Microsoft Defender för Slutpunktsportalen i securitycenter.windows.com eller securitycenter.microsoft.com automatiskt till Säkerhetscenter-portalen för Microsoft 365 security.microsoft.com.
 
Läs mer om vad som har ändrats: [Microsoft Defender för Endpoint i Säkerhetscenter för Microsoft 365.](microsoft-365-security-center-mde.md)

Det inkluderar omdirigering för direkt åtkomst till den tidigare portalen via webbläsare, inklusive länkar som pekar mot den tidigare securitycenter.windows.com-portalen – till exempel länkar i e-postmeddelanden och länkar som returneras av SIEM API-anrop.  

 Externa länkar från e-postaviseringar eller SIEM-API:er innehåller för närvarande länkar till båda portalerna. När omdirigering har aktiverats pekar båda länkarna på Säkerhetscenter för Microsoft 365 tills den gamla länken tas bort. Vi rekommenderar att du använder den nya länken som pekar till Microsoft 365 Säkerhetscenter.

Se tabellen nedan för mer information om länkar och routning.
## <a name="siem-api-routing"></a>SIEM API-routning

|**Egenskap**  |**Mål när omdirigering är AV**  |**Mål när omdirigering är PÅ** | 
|---------|---------|---------|
| LinkToWDATP | Aviseringssida i securitycenter.windows.com | Aviseringssida i security.microsoft.com  |
| IncidentLinkToWDATP | Incidentsida i securitycenter.windows.com  | Incidentsida i security.microsoft.com  |
| LinkToMTP | Aviseringssida i security.microsoft.com | Aviseringssida i security.microsoft.com  |
| IncidentLinkToMTP | Incidentsida i security.microsoft.com  | Incidentsida i security.microsoft.com  

## <a name="email-alert-notifications"></a>E-postaviseringar

|**Egenskap**  |**Mål när omdirigering är AV**  |**Mål när omdirigering är PÅ** |
|---------|---------|---------|
| Aviseringssida  | Aviseringssida i securitycenter.windows.com  | Aviseringssida i security.microsoft.com  |
| Incidentsida  |Incidentsida i securitycenter.windows.com  | Incidentsida i security.microsoft.com  
| Aviseringssida i säkerhetscenterportalen | Aviseringssida i security.microsoft.com | Aviseringssida i security.microsoft.com | 
| Incidentsida i säkerhetscenterportalen | Incidentsida i security.microsoft.com  | Incidentsida i security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>När får detta effekt? 
När den är aktiverad kan uppdateringen börja gälla nästan omedelbart för vissa konton. Men omdirigeringen kan ta längre tid att sprida till alla konton i organisationen. Konton i aktiva sessioner medan den här inställningen används matas inte ut från deras session och kommer bara att dirigeras till Microsoft 365-säkerhetscentret efter att den aktuella sessionen avslutas och loggas in igen.  

### <a name="set-up-portal-redirection"></a>Konfigurera portalomdirigering
Så här börjar du dirigera konton till Säkerhetscenter för Microsoft 365:
1. Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory 

2. [Logga in](https://security.microsoft.com/) på Säkerhetscenter för Microsoft 365.

3. Gå till **Inställningar**  >  **Slutpunkter**  >  **Allmän**  >  **portalomdirigering eller** [klicka här](https://security.microsoft.com/preferences2/portal_redirection).  

4. Ändra inställningen för automatisk omdirigering till **På**.

5. Klicka **på Aktivera** om du vill använda automatisk omdirigering på Microsoft 365 Säkerhetscenter-portalen.

>[!IMPORTANT]
>Aktivering av den här inställningen avbryts inte aktiva användarsessioner. Konton som befinner sig i en aktiv session medan den här inställningen används dirigeras endast till Säkerhetscenter för Microsoft 365 när de avslutar den aktuella sessionen och loggar in igen.

>[!NOTE]
>Du måste vara global administratör eller ha säkerhetsadministratörsbehörighet i Azure Active Directory för att aktivera eller inaktivera den här inställningen.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?
Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Säkerhetscenter-portalen vill vi höra det. Om du har stött på problem med omdirigering rekommenderar vi att du berättar det för oss med hjälp av formuläret för att skicka feedback.

Så här återgår du till den tidigare Microsoft Defender för Endpoint-portalen:

1. [Logga in](https://security.microsoft.com/) på Microsoft 365 Säkerhetscenter som global administratör eller använd och konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.

2. Gå till **Inställningar**  >  **Slutpunkter**  >  **Allmän**  >  **portalomdirigering** [eller öppna sidan här](https://security.microsoft.com/preferences2/portal_redirection).  

3. Ändra inställningen för automatisk omdirigering till **Av**.

4. Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.

Den här inställningen kan aktiveras igen när som helst. 

När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com. 

## <a name="related-information"></a>Relaterad information
- [Microsoft 365 Säkerhetscenter översikt](overview-security-center.md)
- [Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografik av XDR kontra SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Nya Defender](https://afrait.com/blog/the-new-defender/) 
- [Om Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsofts säkerhetsportaler och administrationscenter](portals.md)