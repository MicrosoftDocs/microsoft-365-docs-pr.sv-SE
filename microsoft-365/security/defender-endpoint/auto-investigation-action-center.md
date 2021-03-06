---
title: Besök Åtgärdscenter för att se åtgärder
description: Använd åtgärdscenter för att visa information och resultat efter en automatiserad undersökning
keywords: åtgärd, center, autoir, automatiserad, undersökning, svar, åtgärd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844916"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Besök Åtgärdscenter för att se åtgärder

Under och efter en automatiserad undersökning identifieras åtgärdsåtgärder för identifiering av hot. Beroende på det specifika hot och hur [Microsoft Defender](/windows/security/threat-protection) för Slutpunkt har konfigurerats för din organisation vidtas vissa åtgärder automatiskt och andra kräver godkännande. Om du är en del av organisationens säkerhetsåtgärdsteam kan du visa väntande och [slutförda](manage-auto-investigation.md#remediation-actions) åtgärder i **Åtgärdscenter.** 


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NY!) Ett enhetligt åtgärdscenter


Vi är glada att kunna presentera ett nytt, enhetligt åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ()!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Åtgärdscenter Microsoft 365 säkerhetscenter":::

I följande tabell jämförs det nya, enhetliga Åtgärdscenter med föregående Åtgärdscenter.

|Det nya, enhetliga åtgärdscentret  |Föregående åtgärdscenter  |
|---------|---------|
|Visar väntande och slutförda åtgärder för enheter och e-post på en plats <br/>([Microsoft Defender för Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender för [Office 365](/microsoft-365/security/office-365-security/office-365-atp))|Visar väntande och slutförda åtgärder för enheter <br/> ([Endast Microsoft Defender för slutpunkt)](microsoft-defender-endpoint.md)   |
|Finns på:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Finns på:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| I Microsoft 365 säkerhetscenter väljer du **Åtgärdscenter**. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigera till Åtgärdscenter Microsoft 365 säkerhetscenter"::: | I Microsoft Defender Säkerhetscenter väljer du **Automatiserade undersökningar**  >  **Åtgärdscenter**. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigera till Åtgärdscenter från Microsoft Defender Säkerhetscenter":::  |

I det enhetliga åtgärdscentret samlas åtgärdsåtgärder i Defender för Endpoint och Defender för Office 365. Den definierar ett gemensamt språk för alla åtgärder och ger en enhetlig undersökningsupplevelse. 

Du kan använda det enhetliga åtgärdscentret om du har rätt behörigheter och en eller flera av följande prenumerationer:
- [Defender för Endpoint](microsoft-defender-endpoint.md)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Mer information finns i [Krav](/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Använda Åtgärdscenter

Så här kommer du till det enhetliga åtgärdscentret i det Microsoft 365 säkerhetscentret:
1. Gå till Microsoft 365 ( ) [https://security.microsoft.com](https://security.microsoft.com) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.** 

När du besöker Åtgärdscenter visas två flikar: **Väntande åtgärder** och **Historik.** I följande tabell sammanfattas det du ser på varje flik:

|Tabb  |Beskrivning  |
|---------|---------|
|**Väntande**     | Visar en lista över åtgärder som kräver uppmärksamhet. Du kan godkänna eller avvisa åtgärder en i taget eller markera flera åtgärder om de har samma typ av åtgärd (till exempel **karantänfil).** <br/>**TIPS:** Se till att granska och godkänna [(eller avvisa)](manage-auto-investigation.md) väntande åtgärder så snart som möjligt så att automatiserade undersökningar kan slutföras i tid. |
|**Historik**     | Fungerar som en granskningslogg för åtgärder som har vidtagits, till exempel: <br/>- Åtgärdsåtgärder som har vidtagits genom automatiska undersökningar <br>- Åtgärdsåtgärder som har godkänts av teamet för säkerhetsåtgärder  <br/>- Kommandon som körts och åtgärdsåtgärder som tillämpats under Live Response-sessioner  <br/>- Åtgärdsåtgärder som har vidtagits av skyddsfunktioner för hot i Microsoft Defender Antivirus  <p>Gör det enkelt att ångra vissa åtgärder (se [Ångra slutförda åtgärder).](manage-auto-investigation.md#undo-completed-actions)       |

Du kan anpassa, sortera, filtrera och exportera data i Åtgärdscenter.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Kolumner och filter i Åtgärdscenter":::

- Välj en kolumnrubrik om du vill sortera posterna i stigande eller fallande ordning.
- Använd filtret för tidsperiod för att visa data för den senaste dagen, veckan, 30 dagar eller 6 månader.
- Välj de kolumner som du vill visa.
- Ange hur många objekt som ska ingå på varje sida med data.
- Använd filter för att visa endast de objekt som du vill se.
- Välj **Exportera** om du vill exportera resultaten till en .csv fil. 

## <a name="next-steps"></a>Nästa steg

- [Visa och godkänna reparationsåtgärder](manage-auto-investigation.md)
- [Se den interaktiva guiden: Undersöka och åtgärda hot med Microsoft Defender för Slutpunkt](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Se även

- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
