---
title: Undersökning av & – Microsoft Defender för Office 365 abonnemang 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Läs mer om funktionerna för undersökning av hot och svar i Microsoft Defender för Office 365 plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0a9ff9c06f7e97d6f74c901c156bfae6c9eb91d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083710"
---
# <a name="threat-investigation-and-response"></a>Undersökning och svar på hot

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)


Med funktionerna för undersökning av hot och svar i [Microsoft Defender för Office 365](defender-for-office-365.md) kan säkerhetsanalytiker och administratörer skydda organisationens Microsoft 365 för företagsanvändare genom att:

- Göra det enkelt att identifiera, övervaka och förstå cyberattacker
- Hjälper dig att snabbt hantera hot i Exchange Online, SharePoint Online, OneDrive för företag och Microsoft Teams
- Tillhandahålla insikter och kunskaper för att hjälpa säkerhetsåtgärder förhindra cyberattacker mot organisationen
- Använda automatisk [undersökning och svar i Office 365](automated-investigation-response-office.md) för kritiska e-postbaserade hot

Funktioner för undersökning av hot och svar ger insikter i hot och relaterade svarsåtgärder som är tillgängliga i Microsoft 365 Defender portalen. De här insikterna kan hjälpa organisationens säkerhetsteam att skydda användare från e-post- eller filbaserade attacker. Funktionerna hjälper till att övervaka signaler och samla in data från flera källor, till exempel användaraktivitet, autentisering, e-post, komprometterade datorer och säkerhetstillbud. Beslutsfattare och ditt säkerhetsteam kan använda den här informationen för att förstå och reagera på hot mot organisationen och skydda din immateriella egendom.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Bekanta dig med undersökning av hot och svarsverktyg

Funktionerna för undersökning av hot och svar surface Microsoft 365 Defender-portalen, som en uppsättning verktyg och svarsarbetsflöden, inklusive följande:

- [Explorer](#explorer)
- [Incidenter](#incidents)
- [Utbildning av attack simulering](attack-simulation-training.md)
- [Automatiska undersökningar och svar](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorer

Använd [Utforskaren (och](threat-explorer.md) identifieringar i realtid) för att analysera hot, se mängden attacker över tid och analysera data efter hotfamiljer, attackersinfrastruktur och mycket mer. Utforskaren (kallas även Threat Explorer) är startpunkten för alla säkerhetsanalytikers arbetsflöde för undersökning.

![Hotutforskaren](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Om du vill visa och använda den här rapporten går Microsoft 365 Defender e-postportalen i **Utforskaren för & samarbete.**  >  

### <a name="incidents"></a>Incidenter

Använd listan Incidenter (kallas även Undersökningar) om du vill se en lista över säkerhetsincidenter för flyg. Incidenter används för att spåra hot som misstänkta e-postmeddelanden och för ytterligare undersökning och åtgärd.

![Lista över aktuella hotincidenter i Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Om du vill visa en lista över aktuella incidenter för organisationen går du Microsoft 365 Defender i &  >  **incidenter**.

![Välj Granskning av hothantering i & säkerhets- och \> efterlevnadscenter](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulation-training"></a>Utbildning av attack simulering

Använd utbildning för att skapa och köra realistiska cyberattacker i organisationen och identifiera sårbara personer innan en verklig cyberattacker påverkar ditt företag. Mer information finns i Simulera [nätfiskeangrepp](attack-simulation-training.md).

Om du vill visa och använda den här funktionen i Microsoft 365 Defender-portalen går du till **E-& om samarbete** Attack  >  **simuleringsutbildning**.

### <a name="automated-investigation-and-response"></a>Automatiska undersökningar och svar

Använd funktioner för automatisk undersökning och svar (AIR) för att spara tid och arbete för att korrelera innehåll, enheter och personer som riskerar från hot i organisationen. AIR-processer kan börja när vissa aviseringar utlöses eller när de startas av ditt team för säkerhetsåtgärder. Mer information finns i [automatiserad undersökning och svar i Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widgetar för hotinformation

Som en del av Microsoft Defender för Office 365 plan 2-erbjudandet kan säkerhetsanalytiker granska information om ett känt hot. Det är användbart för att avgöra om det finns ytterligare preventativa åtgärder/steg som kan vidtas för att skydda användarna.

![Säkerhetstrender som visar information om de senaste hoten](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Hur får vi de här funktionerna?

Microsoft 365 funktioner för undersökning av hot och svar ingår i Microsoft Defender för Office 365 abonnemang 2, som ingår i Enterprise E5 eller som ett tillägg till vissa prenumerationer. Mer information finns i [Defender för Office 365 abonnemang 1 och abonnemang 2.](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="required-roles-and-permissions"></a>Roller och behörigheter som krävs

Microsoft Defender för Office 365 använder rollbaserad åtkomstkontroll. Behörigheter tilldelas via vissa roller i Azure Active Directory, Administrationscenter för Microsoft 365 och Microsoft 365 Defender portal.

> [!TIP]
> Även om vissa roller, till exempel säkerhetsadministratör, kan tilldelas i Microsoft 365 Defender-portalen kan du använda antingen Administrationscenter för Microsoft 365 eller Azure Active Directory stället. Mer information om roller, rollgrupper och behörigheter finns i följande resurser:
>
> - [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md)
> - [Administratörens rollbehörigheter i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

<br>

****

|Aktivitet|Roller och behörigheter|
|---|---|
|Använd instrumentpanelen för & Sårbarhetshantering (eller den nya [säkerhetspanelen)](security-dashboard.md) <p> Visa information om de senaste eller aktuella hoten|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhetsadministratör**</li><li>**Säkerhetsläsare**</li></ul> <p> De här rollerna kan tilldelas i Azure Active Directory ( <https://portal.azure.com> ) eller i Administrationscenter för Microsoft 365 ( <https://admin.microsoft.com> ).|
|Använd [Utforskaren (och identifieringar i realtid) för](threat-explorer.md) att analysera hot|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhetsadministratör**</li><li>**Säkerhetsläsare**</li></ul> <p> De här rollerna kan tilldelas i Azure Active Directory ( <https://portal.azure.com> ) eller i Administrationscenter för Microsoft 365 ( <https://admin.microsoft.com> ).|
|Visa incidenter (kallas även undersökningar) <p> Lägga till e-postmeddelanden till ett problem|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhetsadministratör**</li><li>**Säkerhetsläsare**</li></ul> <p> De här rollerna kan tilldelas i Azure Active Directory ( <https://portal.azure.com> ) eller i Administrationscenter för Microsoft 365 ( <https://admin.microsoft.com> ).|
|Utlösa e-poståtgärder i ett incident <p> Hitta och ta bort misstänkta e-postmeddelanden|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhetsadministratör** plus **rollen Sök och** rensning</li></ul> <p> Rollerna **Global administratör** **och Säkerhetsadministratör** kan tilldelas i antingen Azure Active Directory ( <https://portal.azure.com> ) eller i Administrationscenter för Microsoft 365 ( <https://admin.microsoft.com> ). <p> Rollen **Sök och rensning måste** vara tilldelad i rollerna **e& och samarbete** i Microsoft 36 Defender-portalen ( <https://security.microsoft.com> ).|
|Integrera Microsoft Defender för Office 365 abonnemang 2 med Microsoft Defender för Slutpunkt <p> Integrera Microsoft Defender för Office 365 abonnemang 2 med en SIEM-server|Antingen **global administratör** eller **säkerhetsadministratörsroll** som tilldelats i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Administrationscenter för Microsoft 365 ( <https://admin.microsoft.com> ). <p> --- **plus** --- <p> En lämplig roll tilldelad i ytterligare program (till [exempel Microsoft Defender Säkerhetscenter](/windows/security/threat-protection/microsoft-defender-atp/user-roles) eller SIEM-servern).|
|

## <a name="next-steps"></a>Nästa steg

- [Lär dig mer om hotspårningar – nytt och värt att uppmärksamma](threat-trackers.md)
- [Hitta och undersöka skadlig e-post som har Office 365 (undersökning av hot och svar)](investigate-malicious-email-that-was-delivered.md)
- [Integrera Office 365 undersökning av hot och svar med Microsoft Defender för Slutpunkt](integrate-office-365-ti-with-mde.md)
- [Simulera en nätfiskeattack](attack-simulation-training.md)
