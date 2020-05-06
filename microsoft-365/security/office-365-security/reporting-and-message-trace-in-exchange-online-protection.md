---
title: Rapportering och meddelandespårning i Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om rapporter och felsökningsverktyg som är tillgängliga för Microsoft Exchange Online Protection -administratörer (EOP).
ms.openlocfilehash: 44b4223b4310a2de1d90f99f8a7af23cc6054f94
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034386"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Rapportering och meddelandespårning i Exchange Online Protection

Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att fastställa organisationens övergripande status och hälsa. Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till de avsedda mottagarna) och granskningsrapporter som hjälper dig att uppfylla efterlevnadskraven.

## <a name="usage-reports"></a>Användningsrapporter

**Aktivitet för Microsoft 365 grupper:** Visa information om antalet Microsoft 365-grupper som skapas och används.

**E-postaktivitet**: Visa information om antalet meddelanden som skickas, tas emot och läss i hela organisationen och av specifika användare.

**Användning av e-postappar**: Visa information om de e-postappar som används. Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.

**Postlådeanvändning**: Visa information om lagring som används, kvotförbrukning, artikelantal och senaste aktivitet (skicka eller läsa aktivitet) för postlådor.

Mer information finns i följande resurser:

- [Microsoft 365-rapporter i administrationscentret – Microsoft 365-grupper](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporter i administrationscentret – e-postaktivitet](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporter i administrationscentret – användning av e-postappar](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporter i administrationscentret – användning av postlåda](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Säkerhetsrapporter & efterlevnad i microsoft 365-administrationscentret

Dessa förbättrade rapporter ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattande information och möjligheten att öka detaljnivån för mer information.

**Advanced Threat Protection (ATP):** Visa information om säkra länkar och säkra bilagor som ingår i ATP.

**EOP**: Visa information om identifiering av skadlig programvara, förfalskad e-post, skräppostidentifieringar och e-postflöde till och från din organisation.

[Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Skapa programmatiskt rapporter som är tillgängliga i Microsoft 365-administrationscentret med hjälp av Microsoft Graph. Se undertopikerna för [användningsrapporter för Arbeta med Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Skapa programmatiskt rapporter. Se [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="message-trace"></a>Meddelandespårning

Följer e-postmeddelanden när de färdas via EOP. Du kan avgöra om ett e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten. Den visar också vilka åtgärder som vidtogs på meddelandet innan det nådde sin slutliga status.

Du kan använda den här informationen för att effektivt svara på användarens frågor, felsöka problem med e-postflödet, validera principändringar och minska behovet av att kontakta teknisk support för att få hjälp.

Se [Spåra ett e-postmeddelande](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Granskningsloggning

Spårar specifika ändringar som gjorts av administratörer i organisationen. Dessa rapporter kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem. Se [Granskningsrapporter i EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapportering och meddelandespårning datatillgänglighet och svarstid

I följande tabell beskrivs när EOP-rapportering och meddelandespårningsdata är tillgängliga och hur länge.

||||
|:-----|:-----|:-----|
|**Rapporttyp**|**Tillgängliga data för (tillbakablicksperiod)**|**Latens**|
|Sammanfattningsrapporter för e-postskydd|90 dagar|Aggregering av meddelandedata är mestadels klar inom 24-48 timmar. Vissa mindre inkrementella aggregerade ändringar kan förekomma i upp till 5 dagar.|
|Informationsrapporter för e-postskydd|90 dagar|För detaljdata som är mindre än 7 dagar gamla ska data visas inom 24 timmar men kanske inte vara klara förrän 48 timmar. Vissa mindre inkrementella ändringar kan förekomma i upp till 5 dagar. <br/><br/> Om du vill visa detaljerade rapporter för meddelanden som är större än 7 dagar gamla kan resultatet ta upp till några timmar.|
|Data för meddelandespårning|90 dagar|När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla ska meddelandena visas inom 5-30 minuter.<br/><br/> När du kör en meddelandespårning för meddelanden som är längre än 7 dagar gamla kan resultatet ta upp till några timmar.|

> [!NOTE]
> Datatillgänglighet och svarstid är desamma oavsett om de begärs via Microsoft 365 admin center eller fjärr PowerShell.
