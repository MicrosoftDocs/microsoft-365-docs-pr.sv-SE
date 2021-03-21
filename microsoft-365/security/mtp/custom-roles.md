---
title: Anpassade roller för rollbaserad åtkomstkontroll
description: Lär dig hur du hanterar anpassade roller i Säkerhetscenter för Microsoft 365
keywords: åtkomst, behörigheter, MTP, Microsoft Threat Protection, M365, säkerhet, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, omfattning, omfattning, RBAC, rollbaserad åtkomst, anpassad rollerbaserad åtkomst, rollbaserad autentisering, RBAC i MDO, roller, rollgrupper, behörighetsarv, mer begränsade behörigheter
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928934"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- Microsoft 365 Defender
 
Det finns två typer av roller som kan användas för att komma åt Microsoft 365 Defender:
- **Globala Azure Active Directory-roller (AD)**
- **Anpassade roller**

Åtkomst till Microsoft 365 Defender kan hanteras gemensamt med hjälp av [globala roller i Azure Active Directory (AAD)](mtp-permissions.md)

Om du behöver mer flexibilitet och kontroll över åtkomsten till specifika produktdata kan du även hantera Microsoft 365 Defender-åtkomst genom att skapa anpassade roller via respektive säkerhetsportal.  

En anpassad roll som skapats via Microsoft Defender för Endpoint skulle till exempel ge åtkomst till relevanta produktdata, inklusive Slutpunktsdata i Säkerhetscenter för Microsoft 365. På samma sätt ger en anpassad roll som skapats via Microsoft Defender för Office 365 åtkomst till relevanta produktdata, till exempel e-& och samarbetsdata i Säkerhetscenter för Microsoft 365.

Användare med befintliga anpassade roller kan komma åt data i Microsoft 365 säkerhetscenter enligt deras befintliga behörigheter för arbetsbelastning utan ytterligare konfiguration krävs.

## <a name="create-and-manage-custom-roles"></a>Skapa och hantera anpassade roller
Anpassade roller och behörigheter kan skapas och hanteras individuellt via följande säkerhetsportaler: 

- Microsoft Defender för slutpunkt – [Redigera roller i Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender för Office 365 – [behörigheter i säkerhets- & säkerhets- och efterlevnadscenter](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [Hantera administratörsåtkomst](/cloud-app-security/manage-admins)

Varje anpassad roll som skapas via en enskild portal ger tillgång till data i relevant produktportal. Till exempel tillåter en anpassad roll som skapats via Microsoft Defender för Endpoint endast åtkomst till Defender för slutpunktsdata.

> [!TIP]
> Behörigheter och roller kan också nås via Säkerhetscenter för Microsoft 365 genom att välja Behörigheter & roller i navigeringsfönstret. Åtkomst till Microsoft Cloud App Security (MCAS) hanteras via MCAS-portalen och styr även åtkomsten till Microsoft Defender för identitet.  Se [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Anpassade roller som skapats i Microsoft Cloud App Security har även åtkomst till Microsoft Defender för identitetsdata. Användare med användargruppsadministratör eller App-/instansadministratörEr för Microsoft Cloud App-säkerhetsroller kan inte komma åt data om Microsoft Cloud App Security via Säkerhetscenter för Microsoft 365.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Hantera behörigheter och roller i Säkerhetscenter för Microsoft 365
Behörigheter och roller kan också hanteras i Säkerhetscenter för Microsoft 365:

1. Logga in på Säkerhetscenter för Microsoft 365 security.microsoft.com.
2. I navigeringsfönstret väljer du Behörigheter **& roller**.
3. Under rubriken **Behörigheter** väljer du **Roller**.

> [!NOTE]
> Det här gäller endast Defender för Office 365 och Defender för Endpoint. Åtkomst till andra arbetsbelastningar måste göras i relevanta portaler.


## <a name="required-roles-and-permissions"></a>Roller och behörigheter som krävs
I följande tabell beskrivs de roller och behörigheter som krävs för att få åtkomst till varje enhetlig upplevelse i varje arbetsfördelning. Roller som har definierats i tabellen nedan refererar till anpassade roller i enskilda portaler och är inte anslutna till globala roller i Azure AD, även om de har liknande namn.

> [!NOTE]
> Hantering av incidenter kräver behörighet för hantering av alla produkter som är en del av incidenten.
 
| **En av följande roller krävs för Microsoft 365 Defender**  | **En av följande roller krävs för Defender för Slutpunkt**  | **En av följande roller krävs för Defender för Office 365** | **En av följande roller krävs för Cloud App Security** | 
|---------|---------|---------|---------|
| Visa undersökningsdata: <ul><li>Aviseringssida</li> <li>Kön Aviseringar</li> <li>Incidenter</li>  <li>Incidentkö</li> <li>Åtgärdscenter</li></ul>| Visa datasäkerhetsåtgärder | <ul><li>Endast visa Hantera aviseringar </li> <li>Organisationskonfiguration</li><li>Granskningsloggar</li> <li>Visningsbaserade granskningsloggar</li> <li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li></ul>  | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Visa data om du vill ta del av dina data | Visa datasäkerhetsåtgärder | <ul><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li> <li>Endast visa-mottagare</li> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Hantera aviseringar och incidenter | Undersökning av aviseringar | <ul><li>Hantera aviseringar</li> <li>Säkerhetsadministratör</li> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li></ul> |
| Åtgärdscenteråtgärd | Aktiva åtgärdsåtgärder – säkerhetsåtgärder | Sök och rensa | |
| Ställa in anpassade identifieringar | Hantera säkerhetsinställningar |<ul><li>Hantera aviseringar</li> <li>Säkerhetsadministratör</li></ul> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Hotanalys | Information om aviseringar och incidenter: <ul><li>Visa datasäkerhetsåtgärder</li></ul>Minskningar av TVM:<ul><li>Visa data – hantering av hot och sårbarhet</li></ul> | Information om aviseringar och incidenter:<ul> <li>Endast visa Hantera aviseringar</li> <li>Hantera aviseringar</li> <li>Organisationskonfiguration</li><li>Granskningsloggar</li> <li>Visningsbaserade granskningsloggar</li><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li> </ul> Förhindrade e-postförsök: <ul><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li> | Inte tillgängligt för MCAS- eller MDI-användare |

Om du till exempel vill visa letar efter data från Microsoft Defender för Endpoint krävs behörigheten Visa datasäkerhetsåtgärder.  

För att kunna visa data på visning från Microsoft Defender för Office 365 behöver användarna på samma sätt en av följande roller:  

- Visa datasäkerhetsåtgärder
- Säkerhetsläsare
- Säkerhetsadministratör
- Endast visa-mottagare

## <a name="related-topics"></a>Relaterade ämnen
- [Hantera åtkomst till Microsoft 365 Defender](mtp-permissions.md)
- [Hantera administratörsåtkomst för MCAS](/cloud-app-security/manage-admins)