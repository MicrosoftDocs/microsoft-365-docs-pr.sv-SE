---
title: Omdirigering av konton Office 365 Säkerhets- och efterlevnadscenter till det nya Microsoft 365 Defender
description: Hur du omdirigerar från Defender för Office 365 att Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Komma igång med Microsoft 365 Defender, omdirigering av säkerhetscenter
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842531"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Omdirigera konton från Säkerhets- Office 365 Säkerhets- och efterlevnadscenter till Defender Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender
- Defender förr Office 365

Den här artikeln förklarar hur du dirigerar konton till Microsoft 365 Defender genom att aktivera automatisk omdirigering från det tidigare säkerhets- och efterlevnadscentret för Office 365 (protection.office.com) till Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>Vad du kan förvänta dig
När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 Security and Compliance (protection.office.com) automatiskt till Microsoft 365 Defender ( https://security.microsoft.com) .  

Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

När automatisk omdirigering är aktiverad dirigeras användarna till Microsoft 365 Defender när de använder säkerhetsfunktionerna i Office 365 Säkerhets- och efterlevnadscenter.

De omfattar funktioner i avsnittet Hothantering och instrumentpanelen och rapporterna för hantering av hot. Objekt i säkerhets- Office 365 säkerhets- och efterlevnadscentret som inte är relaterade till säkerhet omdirigeras inte till Microsoft 365 Defender.

Efterlevnadsrelaterade objekt finns i Microsoft 365 efterlevnadscenter, och e-postflödesrelaterade objekt finns Exchange administrationscenter.

Alla andra funktioner, oavsett om de är efterlevnadsrelaterade eller funktioner som fungerar för båda, påverkas inte av omdirigering. Office 365 säkerhetsvarningar visas i både Defender Microsoft 365 och Säkerhets- och efterlevnadscenter för Office 365, utan omdirigering.  

### <a name="set-up-portal-redirection"></a>Konfigurera portalomdirigering
Om du vill börja dirigera konton till Microsoft 365 Defender på security.microsoft.com:

1. Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory.
2. [Logga in](https://security.microsoft.com/) på Microsoft 365 Defender.
3. Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**  
4. Ändra inställningen för automatisk omdirigering till **På**.
5. Klicka **på Aktivera** om du vill använda automatisk omdirigering Microsoft 365 Defender.

> [!NOTE]
> När omdirigering har aktiverats matas konton i aktiva sessioner medan den här inställningen används inte från sessionen och dirigeras bara till Microsoft 365 Defender när den aktuella sessionen avslutas och loggar in igen.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?
Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Defender vill vi höra mer om det med hjälp av feedback-alternativet för portalen. Om du har stött på problem med omdirigering får du gärna meddela oss.

Så här återgår du till den tidigare portalen:

1. [Logga in](https://security.microsoft.com/) på Microsoft 365 Defender som global administratör eller med ett konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.

2. Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**   

3. Ändra inställningen för automatisk omdirigering till **Av**.

4. Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.

Den här inställningen kan aktiveras igen när som helst.

När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.

## <a name="related-information"></a>Relaterad information
- [Microsoft 365 Defender-översikt](overview-security-center.md)
- [Microsoft Defender för slutpunkt i Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder](https://www.microsoft.com/security/blog/?p=91813) 
- [Infografik av XDR kontra SIEM](https://afrait.com/blog/xdr-versus-siem/) 
- [Nya Defender](https://afrait.com/blog/the-new-defender/) 
- [Om Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsofts säkerhetsportaler och administrationscenter](portals.md)
