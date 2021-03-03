---
title: Omdirigera konton från Microsoft Defender för Office 365 till det nya säkerhetscentret för Microsoft 365
description: Så här omdirigerar du från Defender för Office 365 till Säkerhetscenter för Microsoft 365.
keywords: Microsoft 365 säkerhetscenter, Komma igång med Microsoft 365 säkerhetscenter, omdirigering av säkerhetscenter
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
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416828"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Omdirigera konton från Microsoft Defender för Office 365 till Säkerhetscenter för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender
- Defender förr Office 365

I den här artikeln förklaras hur du dirigerar konton till Microsoft 365 säkerhetscenter genom att aktivera automatisk omdirigering från det tidigare Säkerhets- och efterlevnadscentret för Microsoft (protection.office.com eller securitycenter.microsoft.com) till Microsoft 365 säkerhetscenter (security.microsoft.com).

>[!NOTE]
> Funktionen för portalomdirigering är endast tillgänglig för Office 365 E5- och Microsoft Defender för Office P2-kunder

## <a name="what-to-expect"></a>Vad du kan förvänta dig
När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 säkerhet och efterlevnad (protection.office.com) automatiskt till Säkerhetscenter för Microsoft 365 https://security.microsoft.com) (.  

Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Säkerhetscenter för Microsoft 365.](microsoft-365-security-center-mdo.md)

När automatisk omdirigering är aktiverad dirigeras användare till Microsoft 365 säkerhetscenter när de använder säkerhetsfunktionerna i Säkerhets- och efterlevnadscenter för Office 365.

De omfattar funktioner i avsnittet Hantering av hot och instrumentpanelen och rapporterna för hantering av hot. Objekt i Säkerhets- och efterlevnadscenter för Office 365 som inte är relaterade till säkerhet omdirigeras inte till Säkerhetscenter för Microsoft 365.

Efterlevnadsrelaterade objekt finns i Efterlevnadscenter för Microsoft 365 och e-postflödesrelaterade objekt finns i administrationscentret för Exchange.

Alla andra funktioner, oavsett om efterlevnadsrelaterade eller funktioner som båda används, påverkas inte av omdirigeringen. Office 365-säkerhetsvarningar visas i både Säkerhetscenter för Microsoft 365 och Säkerhets- och efterlevnadscenter för Office 365, utan omdirigering.  

### <a name="set-up-portal-redirection"></a>Konfigurera portalomdirigering
Så här börjar du dirigera konton till Säkerhetscenter för Microsoft 365 på security.microsoft.com:

1. Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörighet i Azure Active Directory.
2. [Logga in](https://security.microsoft.com/) på Microsoft 365 säkerhetscenter.
3. Gå till **Inställningar för**  >  **e& för samarbete –**  >  **portalomdirigering.**  
4. Växla inställningen Automatisk omdirigering till **På.**
5. Klicka **på Aktivera** om du vill använda automatisk omdirigering på Microsoft 365 Säkerhetscenter-portalen.

> [!NOTE]
> När omdirigeringen är aktiverad matas inte konton i aktiva sessioner medan den här inställningen används ut från sessionen och dirigeras bara till Säkerhetscenter för Microsoft 365 när den aktuella sessionen avslutas och loggar in igen.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?
Om något inte fungerar för dig eller om det finns något du inte kan slutföra via Microsoft 365 Säkerhetscenter-portalen vill vi höra om det med hjälp av feedback-alternativet för portalen. Om du har stött på problem med omdirigering uppmuntrar vi dig att kontakta din EM-kompis direkt via privat förhandsgranskning eller meddela oss via formuläret för att skicka feedback.

Så här återgår du till den tidigare portalen:

1. [Logga in](https://security.microsoft.com/) på Microsoft 365 säkerhetscenter som global administratör eller använd och konto med behörigheter som säkerhetsadministratör i Azure Active Directory.

2. Navigera till **Inställningar,**  >  **allmän**  >    >  **portalomdirigering.**  

3. Ändra inställningen för automatisk omdirigering till **Av.**

4. Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.

Den här inställningen kan aktiveras igen när som helst.

När det är inaktiverat kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.

## <a name="related-information"></a>Relaterad information
- [Microsoft 365 Säkerhetscenter översikt](overview-security-center.md)
- [Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografik om XDR kontra SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Nya Defender](https://afrait.com/blog/the-new-defender/) 
- [Om Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsofts säkerhetsportaler och administrationscenter](portals.md)