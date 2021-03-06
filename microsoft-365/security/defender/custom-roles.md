---
title: Anpassade roller för rollbaserad åtkomstkontroll
description: Lär dig hur du hanterar anpassade roller Microsoft 365 säkerhetscenter
keywords: åtkomst, behörigheter, Microsoft 365 Defender, M365, säkerhet, MCAS, Cloud App Security, Microsoft Defender för Slutpunkt, omfattning, omfattning, RBAC, rollbaserad åtkomst, anpassad rollbaserad åtkomst, rollbaserad autentisering, RBAC i MDO, roller, rollgrupper, behörighetsarv, mer begränsade behörigheter
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9dfa9f113c0a7d57360c2da6105cbfa07fcf6a99
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935695"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Anpassade roller i rollbaserad åtkomstkontroll för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- Microsoft 365 Defender
 
Det finns två typer av roller som kan användas för att komma åt Microsoft 365 Defender:
- **Ad-Azure Active Directory (Global Azure Active Directory)**
- **Anpassade roller**

Åtkomst till Microsoft 365 Defender kan hanteras gemensamt med hjälp av [globala roller i Azure Active Directory (AAD)](m365d-permissions.md)

Om du behöver mer flexibilitet och kontroll över åtkomsten till specifika produktdata kan Microsoft 365 Defender-åtkomst också hanteras genom att anpassade roller skapas via respektive säkerhetsportal.  

En anpassad roll som skapats via Microsoft Defender för Endpoint skulle till exempel ge åtkomst till relevanta produktdata, inklusive slutpunktsdata i Microsoft 365 säkerhetscenter. På samma sätt ger en anpassad roll som skapats via Microsoft Defender för Office 365 åtkomst till relevanta produktdata, till exempel e-& och samarbetsdata i säkerhetscentret i Microsoft 365.

Användare med befintliga anpassade roller kan komma åt data i säkerhetscentret i Microsoft 365 enlighet med deras befintliga behörigheter för arbetsbelastning utan ytterligare konfiguration.

## <a name="create-and-manage-custom-roles"></a>Skapa och hantera anpassade roller
Anpassade roller och behörigheter kan skapas och hanteras individuellt via följande säkerhetsportaler: 

- Microsoft Defender för slutpunkt – [Redigera roller i Microsoft Defender för Slutpunkt](../defender-endpoint/user-roles.md)
- Microsoft Defender för Office 365 – [behörigheter i Säkerhets- & Säkerhets- och efterlevnadscenter](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [Hantera administratörsåtkomst](/cloud-app-security/manage-admins)

Varje anpassad roll som skapas via en enskild portal ger tillgång till data i relevant produktportal. Till exempel tillåter en anpassad roll som skapats via Microsoft Defender för Endpoint endast åtkomst till Defender för slutpunktsdata.

> [!TIP]
> Behörigheter och roller kan också nås via säkerhetscentret i Microsoft 365 genom att välja Behörigheter & roller i navigeringsfönstret. Åtkomst till Microsoft Cloud App Security (MCAS) hanteras via MCAS-portalen och styr även åtkomsten till Microsoft Defender för identitet.  Se [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Anpassade roller som Microsoft Cloud App Security har även åtkomst till Microsoft Defender för identitetsdata. Användare med användargruppsadministratör eller app-/instansadministratörsroller Microsoft Cloud App Security inte kan komma åt data Microsoft Cloud App Security via säkerhetscentret i Microsoft 365 instans.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Hantera behörigheter och roller i Microsoft 365 Säkerhetscenter
Behörigheter och roller kan också hanteras i Microsoft 365 säkerhetscenter:

1. Logga in på Microsoft 365 säkerhetscenter på security.microsoft.com.
2. I navigeringsfönstret väljer du Behörigheter **& roller**.
3. Under rubriken **Behörigheter** väljer du **Roller**.

> [!NOTE]
> Detta gäller endast Defender för Office 365 och Defender för Slutpunkt. Åtkomst till andra arbetsbelastningar måste göras i relevanta portaler.


## <a name="required-roles-and-permissions"></a>Roller och behörigheter som krävs
I följande tabell beskrivs de roller och behörigheter som krävs för att få åtkomst till varje enhetlig upplevelse i varje arbetsfördelning. Roller som har definierats i tabellen nedan refererar till anpassade roller i enskilda portaler och är inte anslutna till globala roller i Azure AD, även om de har liknande namn.

> [!NOTE]
> Hantering av incidenter kräver behörighet för hantering av alla produkter som är en del av incidenten.
 
| **En av följande roller krävs för att Microsoft 365 Defender**  | **En av följande roller krävs för Defender för Slutpunkt**  | **En av följande roller krävs för Defender för Office 365** | **En av följande roller krävs för Cloud App Security** | 
|---------|---------|---------|---------|
| Visa undersökningsdata: <ul><li>Aviseringssida</li> <li>Varningskö</li> <li>Incidenter</li>  <li>Incidentkö</li> <li>Åtgärdscenter</li></ul>| Visa datasäkerhetsåtgärder | <ul><li>Endast visa Hantera aviseringar </li> <li>Organisationskonfiguration</li><li>Granskningsloggar</li> <li>Visningsbaserade granskningsloggar</li> <li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li></ul>  | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Visa data om du vill ta del av dina data | Visa datasäkerhetsåtgärder | <ul><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li> <li>Endast visa-mottagare</li> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Hantera aviseringar och incidenter | Undersökning av aviseringar | <ul><li>Hantera varningar</li> <li>Säkerhetsadministratör</li> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li></ul> |
| Åtgärdscenteråtgärd | Aktiva åtgärdsåtgärder – säkerhetsåtgärder | Sök och rensa | |
| Ställa in anpassade identifieringar | Hantera säkerhetsinställningar |<ul><li>Hantera varningar</li> <li>Säkerhetsadministratör</li></ul> | <ul><li>Global administratör</li> <li>Säkerhetsadministratör</li> <li>Efterlevnadsadministratör</li> <li>Säkerhetsoperatör</li> <li>Säkerhetsläsare</li> <li>Global läsare</li></ul> |
| Analys av hot | Information om aviseringar och incidenter: <ul><li>Visa datasäkerhetsåtgärder</li></ul>Minskningar av TVM:<ul><li>Visa data – hot och hantering av säkerhetsrisker</li></ul> | Information om aviseringar och incidenter:<ul> <li>Endast visa Hantera aviseringar</li> <li>Hantera varningar</li> <li>Organisationskonfiguration</li><li>Granskningsloggar</li> <li>Visningsbaserade granskningsloggar</li><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li> </ul> Förhindrade e-postförsök: <ul><li>Säkerhetsläsare</li> <li>Säkerhetsadministratör</li><li>Endast visa-mottagare</li> | Inte tillgängligt för MCAS- eller MDI-användare |

Om du till exempel vill visa letar efter data från Microsoft Defender för Endpoint krävs behörigheten Visa datasäkerhetsåtgärder.  

För att kunna visa data på visning från Microsoft Defender Office 365 behöver användarna en av följande roller:  

- Visa datasäkerhetsåtgärder
- Säkerhetsläsare
- Säkerhetsadministratör
- Endast visa-mottagare

## <a name="related-topics"></a>Relaterade ämnen
- [Hantera åtkomst till Microsoft 365 Defender](m365d-permissions.md)
- [Hantera administratörsåtkomst för MCAS](/cloud-app-security/manage-admins)
