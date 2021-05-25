---
title: Omdirigera konton från Microsoft Defender för Office 365 till det nya Microsoft 365 säkerhetscentret
description: Hur du omdirigerar från Defender för Office 365 till Microsoft 365 säkerhetscenter.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2a4b122b3ef3a1ddaf61d8f9373bec3e721db177
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651386"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Omdirigera konton från Microsoft Defender för Office 365 till Microsoft 365 säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender
- Defender förr Office 365

Den här artikeln förklarar hur du dirigerar konton till säkerhetscentret i Microsoft 365 genom att aktivera automatisk omdirigering från det tidigare Säkerhets- och efterlevnadscentret för Microsoft (protection.office.com eller securitycenter.microsoft.com) till säkerhetscentret i Microsoft 365 (security.microsoft.com).

## <a name="what-to-expect"></a>Vad du kan förvänta dig
När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 Security and Compliance (protection.office.com) automatiskt till säkerhetscentret i Microsoft 365 ( https://security.microsoft.com) .  

Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Microsoft 365 säkerhetscenter](microsoft-365-security-center-mdo.md).

När automatisk omdirigering är aktiverat dirigeras användarna till Microsoft 365 säkerhetscenter när de använder säkerhetsfunktionerna i Office 365 Säkerhets- och efterlevnadscenter.

De omfattar funktioner i avsnittet Hothantering och instrumentpanelen och rapporterna för hantering av hot. Objekt i Office 365 säkerhets- och efterlevnadscenter som inte är relaterade till säkerhet omdirigeras inte till Microsoft 365 säkerhetscenter.

Efterlevnadsrelaterade objekt finns i Microsoft 365 efterlevnadscenter, och e-postflödesrelaterade objekt finns Exchange administrationscenter.

Alla andra funktioner, oavsett om de är efterlevnadsrelaterade eller funktioner som fungerar för båda, påverkas inte av omdirigering. Office 365 säkerhetsvarningar visas i både säkerhetscentret Microsoft 365 säkerhetscentret och säkerhets- Office 365, utan omdirigering.  

### <a name="set-up-portal-redirection"></a>Konfigurera portalomdirigering
Så här börjar du dirigera konton Microsoft 365 säkerhetscentret på security.microsoft.com:

1. Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory.
2. [Logga in](https://security.microsoft.com/) på Microsoft 365 säkerhetscenter.
3. Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**  
4. Ändra inställningen för automatisk omdirigering till **På**.
5. Klicka **på Aktivera** om du vill använda automatisk omdirigering Microsoft 365 säkerhetscenterportalen.

> [!NOTE]
> När omdirigering har aktiverats matas konton i aktiva sessioner medan den här inställningen används inte från sessionen och dirigeras bara till säkerhetscentret i Microsoft 365 när den aktuella sessionen avslutas och loggar in igen.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?
Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 säkerhetscenter-portalen vill vi höra om det med hjälp av feedback-alternativet för portalen. Om du har stött på problem med omdirigering får du gärna meddela oss.

Så här återgår du till den tidigare portalen:

1. [Logga in](https://security.microsoft.com/) på säkerhetscentret Microsoft 365 global administratör eller använd och konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.

2. Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**   

3. Ändra inställningen för automatisk omdirigering till **Av**.

4. Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.

Den här inställningen kan aktiveras igen när som helst.

När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.

## <a name="related-information"></a>Relaterad information
- [Microsoft 365 Säkerhetscenter översikt](overview-security-center.md)
- [Microsoft Defender för Slutpunkt i Microsoft 365 säkerhetscenter](microsoft-365-security-center-mde.md)
- [Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografik av XDR kontra SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Nya Defender](https://afrait.com/blog/the-new-defender/) 
- [Om Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsofts säkerhetsportaler och administrationscenter](portals.md)
