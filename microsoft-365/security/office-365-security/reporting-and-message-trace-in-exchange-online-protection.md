---
title: Rapportering och meddelandespårning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om rapporter och felsökningsverktyg som är tillgängliga Microsoft Exchange Online Protection (EOP) administratörer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054374"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportering och meddelandespårning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, erbjuder EOP många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och hälsa. Det finns även verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter för att uppfylla efterlevnadskraven.

## <a name="usage-reports"></a>Användningsrapporter

- **Microsoft 365 gruppaktivitet**: Visa information om antalet Microsoft 365 grupper som skapas och används. Mer information finns i [Microsoft 365 rapporter i administrationscentret – Microsoft 365 grupper.](../../admin/activity-reports/office-365-groups.md)
- **E-postaktivitet:** Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare. Mer information finns i Microsoft 365 [i administrationscentret – E-postaktivitet.](../../admin/activity-reports/email-activity.md)
- **Användning av e-postprogram:** Visa information om vilka e-postprogram som används. Det här inkluderar det totala antalet anslutningar för varje app och de versioner Outlook som ansluter. Mer information finns i artikeln Microsoft 365 [i administrationscentret – Användning av e-postprogram.](../../admin/activity-reports/email-apps-usage.md)
- **Postlådeanvändning:** Visa information om använt lagringsutrymme, kvotanvändning, antal objekt och senaste aktivitet (skicka eller läsaktivitet) för postlådor. Mer information finns i [Microsoft 365 i administrationscentret – Postlådeanvändning.](../../admin/activity-reports/mailbox-usage.md)

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Säkerhetsrapporter i Microsoft 365 Defender-portalen

De här förbättrade rapporterna ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattningsinformation och möjlighet att granska nedåt för mer information.

- **Defender för Office 365:** Visa information om Valv och länkar Valv Bifogade filer som ingår i Microsoft Defender för Office 365. Mer information finns i [Visa Defender för Office 365 i Microsoft 365 Defender portal.](view-reports-for-mdo.md)
- **EOP:** Visa information om identifiering av skadlig programvara, förfalskning, identifiering av skräppost och e-postflöde till och från organisationen. Mer information finns i Visa [säkerhetsrapporter för e-post i Microsoft 365 Defender portal](view-email-security-reports.md).

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Programmässigt skapa rapporter som är tillgängliga i administrationscentret med hjälp av Microsoft Graph. Mer information finns i Översikt [över Microsoft-Graph](/graph/overview) och [Arbeta med Office 365 användningsrapporter i Microsoft Graph.](/graph/api/resources/report)

## <a name="message-trace"></a>Meddelandespårning

Följer upp e-postmeddelanden när de färdas genom EOP. Du kan avgöra om ett e-postmeddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.

Du kan använda den här informationen för att effektivt besvara användarnas frågor, felsöka problem i e-postflödet, verifiera principändringar och förbättra behovet av att kontakta teknisk support för att få hjälp.

Läs [Meddelandespårning i Microsoft 365 Defender portalen](message-trace-scc.md).

## <a name="audit-logging"></a>Granskningsloggning

Spårar specifika ändringar som gjorts av administratörer i organisationen. De här rapporterna kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem. Se [Granskningsrapporter i Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapportering och meddelandespårning av datatillgänglighet och svarstid

I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.

<br>

****

|Rapporttyp|Tillgängliga data för (bakåtperiod)|Svarstid|
|---|---|---|
|Sammanfattningsrapporter om e-postskydd|90 dagar|Aggregeringen för meddelandedata slutförs oftast inom 24–48 timmar. Vissa mindre stegvisa sammantagna ändringar kan inträffa i upp till 5 dagar.|
|Detaljrapporter om e-postskydd|90 dagar|För detaljdata som är mindre än 7 dagar gamla bör data visas inom 24 timmar men kan vara fullständiga till 48 timmar. Vissa mindre stegvisa ändringar kan inträffa i upp till 5 dagar. <p> Om du vill visa detaljrapporter för meddelanden som är äldre än 7 dagar kan resultatet ta upp till några timmar.|
|Meddelandespårningsdata|90 dagar|När du kör en meddelandespårning för meddelanden som är äldre än sju dagar bör meddelandena visas inom 5–30 minuter.<p> När du kör en meddelandespårning för meddelanden som är äldre än sju dagar kan resultatet ta upp till några timmar.|
|

> [!NOTE]
> Datatillgänglighet och svarstid är samma oavsett om begärs via administrationscentret eller fjärr-PowerShell.
