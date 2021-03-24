---
title: Omdirigera konton från Microsoft Defender för Office 365 till det nya säkerhetscentret för Microsoft 365
description: Omdirigera från Defender för Office 365 till Microsoft 365 Säkerhetscenter.
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072681"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Omdirigera konton från Microsoft Defender för Office 365 till Säkerhetscenter för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender
- Defender förr Office 365

I den här artikeln förklaras hur du dirigerar konton till Microsoft 365 säkerhetscenter genom att aktivera automatisk omdirigering från Microsofts tidigare säkerhets- och efterlevnadscenter (protection.office.com eller securitycenter.microsoft.com) till Microsoft 365 säkerhetscenter (security.microsoft.com).

>[!NOTE]
> Funktionen för portalomdirigering är endast tillgänglig för Office 365 E5 och Microsoft Defender för Office P2-kunder

## <a name="what-to-expect"></a>Vad du kan förvänta dig
När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 säkerhet och efterlevnad (protection.office.com) automatiskt till Säkerhetscenter för Microsoft 365 https://security.microsoft.com) (.  

Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Säkerhetscenter för Microsoft 365.](microsoft-365-security-center-mdo.md)

När automatisk omdirigering är aktiverat dirigeras användarna till Säkerhetscenter för Microsoft 365 när de använder säkerhetsfunktioner i Säkerhets- och efterlevnadscenter för Office 365.

De omfattar funktioner i avsnittet Hothantering och instrumentpanelen och rapporterna för hantering av hot. Objekt i Säkerhets- och efterlevnadscenter för Office 365 som inte är relaterade till säkerhet omdirigeras inte till Säkerhetscenter för Microsoft 365.

Efterlevnadsrelaterade objekt finns i Efterlevnadscenter för Microsoft 365, och e-postflödesrelaterade objekt finns i administrationscentret för Exchange.

Alla andra funktioner, oavsett om de är efterlevnadsrelaterade eller funktioner som fungerar för båda, påverkas inte av omdirigering. Office 365-säkerhetsvarningar visas i både Microsoft 365 säkerhetscenter och Office 365 Säkerhets- och efterlevnadscenter, utan omdirigering.  

### <a name="set-up-portal-redirection"></a>Konfigurera portalomdirigering
Så här börjar du dirigera konton till Säkerhetscenter för Microsoft 365 security.microsoft.com:

1. Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory.
2. [Logga in](https://security.microsoft.com/) på Säkerhetscenter för Microsoft 365.
3. Gå till **Inställningar**  >  **E-& omdirigering till**  >  **samarbetsportalen.**  
4. Ändra inställningen för automatisk omdirigering till **På**.
5. Klicka **på Aktivera** om du vill använda automatisk omdirigering på Microsoft 365 Säkerhetscenter-portalen.

> [!NOTE]
> När omdirigering har aktiverats matas konton i aktiva sessioner medan den här inställningen används inte från sessionen och dirigeras bara till Säkerhetscenter för Microsoft 365 när den aktuella sessionen avslutas och loggar in igen.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan jag använda den tidigare portalen igen?
Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Säkerhetscenter-portalen vill vi höra om det med hjälp av alternativet för portalfeedback. Om du har stött på problem med omdirigering rekommenderar vi att du når ut till din PM-kompis direkt via privat förhandsgranskning eller berättar det via formuläret för att skicka feedback.

Så här återgår du till den tidigare portalen:

1. [Logga in](https://security.microsoft.com/) på Microsoft 365 Säkerhetscenter som global administratör eller använd och konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.

2. Gå till **Inställningar**  >  **Slutpunkter**  >  **allmän**  >  **portalomdirigering**.  

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