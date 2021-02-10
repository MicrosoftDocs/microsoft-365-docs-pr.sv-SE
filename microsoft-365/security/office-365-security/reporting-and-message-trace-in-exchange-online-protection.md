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
description: I den här artikeln får du lära dig mer om rapporter och felsökningsverktyg som är tillgängliga för Microsoft Exchange Online Protection-administratörer (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166681"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportering och meddelandespårning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor erbjuder EOP många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och status. Det finns även verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter för att hjälpa dig med efterlevnadskraven.

## <a name="usage-reports"></a>Användningsrapporter

**Aktivitet i Microsoft 365-grupper:** Visa information om antalet Microsoft 365-grupper som skapas och används.

**E-postaktivitet:** Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.

**Användning av e-postprogram:** Visa information om de e-postprogram som används. Det inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.

**Postlådeanvändning:** Visa information om använt lagringsutrymme, kvotanvändning, antal objekt och senaste aktivitet (skicka eller läs aktivitet) för postlådor.

Mer information finns i följande resurser:

- [Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporter i administrationscentret – E-postaktivitet](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporter i administrationscentret – Användning av e-postprogram](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporter i administrationscenter – Postlådeanvändning](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Säkerhets- & efterlevnadsrapporter i administrationscentret för Microsoft 365

De här förbättrade rapporterna ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattningsinformation, och möjlighet att öka detaljgranskningen för mer information.

**Defender för Office 365:** Visa information om säkra länkar och säkra bifogade filer som ingår i Microsoft Defender för Office 365.

**EOP:** Visa information om identifiering av skadlig programvara, förfalskning, identifiering av skräppost och e-postflöde till och från organisationen.

[Visa rapporter för Defender för Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Programmässigt skapa rapporter som är tillgängliga i administrationscentret med hjälp av Microsoft Graph. Mer information finns i Översikt [över Microsoft Graph och](https://docs.microsoft.com/graph/overview) hur du arbetar med Office [365-användningsrapporter i Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Meddelandespårning

Följer e-postmeddelanden när de färdas genom EOP. Du kan avgöra om ett e-postmeddelande har tagits emot, avvisats, skjutits upp eller levererats av tjänsten. Det visar också vilka åtgärder som har vidtagits för meddelandet innan det nått sin slutgiltiga status.

Du kan använda den här informationen för att effektivt besvara användarnas frågor, felsöka problem med e-postflödet, verifiera principändringar och förbättra behovet av att kontakta teknisk support för att få hjälp.

Visa [meddelandespårning i Säkerhets- & Efterlevnadscenter.](message-trace-scc.md)

## <a name="audit-logging"></a>Granskningsloggning

Spårar specifika ändringar som gjorts av administratörer i organisationen. De här rapporterna kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem. Se [granskningsrapporter i EOP.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapportering och meddelandespårning, datatillgänglighet och svarstid

I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.

****

|Rapporttyp|Tillgängliga data för (tillbaka back-period)|Svarstid|
|---|---|---|
|Sammanfattningsrapporter om e-postskydd|90 dagar|Aggregering av meddelandedata är mest fullständig inom 24–48 timmar. Några mindre stegvisa sammantagna ändringar kan inträffa i upp till 5 dagar.|
|Detaljrapporter om e-postskydd|90 dagar|För detaljerad information som är mindre än 7 dagar gammal bör data visas inom 24 timmar men kan inte vara fullständiga förrän 48 timmar. Några mindre stegvisa ändringar kan inträffa i upp till 5 dagar. <p> Om du vill visa detaljrapporter för meddelanden som är äldre än 7 dagar kan det ta upp till några timmar.|
|Meddelandespårningsdata|90 dagar|När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla bör meddelandena visas inom 5–30 minuter.<p> När du kör en meddelandespårning för meddelanden som är äldre än sju dagar kan det ta upp till några timmar.|
|

> [!NOTE]
> Datatillgänglighet och svarstid är desamma oavsett om de begärs via administrationscentret eller fjärr-PowerShell.
