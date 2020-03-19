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
description: Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och hälsa. Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och granska rapporter för att hjälpa till med efterlevnadskraven. I följande tabell beskrivs de rapporter och felsökningsverktyg som är tillgängliga för EOP-administratörer.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810386"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Rapportering och meddelandespårning i Exchange Online Protection

Microsoft Exchange Online Protection (EOP) innehåller många olika rapporter som kan hjälpa dig att avgöra organisationens övergripande status och hälsa. Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och granska rapporter för att hjälpa till med efterlevnadskraven.

## <a name="usage-reports"></a>Användningsrapporter

**Aktivitet för Office 365-grupper**: Visa information om antalet Office 365-grupper som skapas och används.

**E-postaktivitet**: Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.

**Användning av e-postappar**: Visa information om de e-postappar som används. Detta inkluderar det totala antalet anslutningar för varje app och de versioner av Outlook som ansluter.

**Postlådeanvändning**: Visa information om lagring som används, kvotförbrukning, artikelantal och senaste aktivitet (skicka eller läsa aktivitet) för postlådor.

Mer information finns i följande resurser:

- [Office 365-rapporter i administrationscentret – Office 365-grupper](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [Office 365-rapporter i administrationscentret – e-postaktivitet](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [Office 365-rapporter i Administrationscentret – användning av e-postappar](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [Office 365-rapporter i administrationscentret – postlådeanvändning](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Säkerhets- & efterlevnadsrapporter i administrationscentret för Microsoft 365

Dessa förbättrade rapporter ger en interaktiv rapporteringsupplevelse för EOP-administratörer, som innehåller sammanfattande information, och möjligheten att öka detaljnivån för mer information.

**Avancerat hotskydd (ATP):** Visa information om säkra länkar och säkra bilagor som ingår i ATP.

**EOP**: Visa information om upptäcktav skadlig kod, falsk e-post, skräppostidentifieringar och e-postflöde till och från din organisation.

[Visa rapporter för Avancerad hotskydd i Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Skapa programmatiskt rapporter som är tillgängliga i administrationscentret för Microsoft 365 med hjälp av Microsoft Graph. Se underavsnitten [i Användningsrapporter för Arbeta med Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Skapa programmässigt rapporter. Se [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="message-trace"></a>Meddelandespårning

Följer e-postmeddelanden när de färdas via EOP. Du kan avgöra om ett e-postmeddelande togs emot, avvisades, sköts upp eller levererades av tjänsten. Den visar också vilka åtgärder som vidtogs på meddelandet innan det nådde sin slutliga status.

Du kan använda den här informationen för att effektivt svara på användarens frågor, felsöka problem med e-postflödet, validera principändringar och lindra behovet av att kontakta teknisk support för hjälp.

Se [Spåra ett e-postmeddelande](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>Granska loggning

Spårar specifika ändringar som gjorts av administratörer i din organisation. Dessa rapporter kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem. Se [Granskningsrapporter i EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapportering och meddelandespårningsdatatillgänglighet och svarstid

I följande tabell beskrivs när EOP-rapporterings- och meddelandespårningsdata är tillgängliga och hur länge.

||||
|:-----|:-----|:-----|
|**Rapporttyp**|**Tillgängliga data för (tillbakablicksperiod)**|**Latens**|
|Sammanfattningsrapporter för e-postskydd|90 dagar|Meddelandedataaggregering är mestadels klar inom 24-48 timmar. Vissa mindre inkrementella aggregerade ändringar kan inträffa i upp till 5 dagar.|
|Informationsrapporter för e-postskydd|90 dagar|För detaljdata som är kortare än 7 dagar ska data visas inom 24 timmar men kanske inte är fullständiga förrän 48 timmar. Vissa mindre inkrementella ändringar kan inträffa i upp till 5 dagar. <br/><br/> Om du vill visa detaljrapporter för meddelanden som är större än 7 dagar kan det ta upp till några timmar.|
|Meddelandespårningsdata|90 dagar|När du kör en meddelandespårning för meddelanden som är mindre än 7 dagar gamla ska meddelandena visas inom 5-30 minuter.<br/><br/> När du kör en meddelandespårning för meddelanden som är större än 7 dagar kan resultaten ta upp till några timmar.|

> [!NOTE]
> Datatillgänglighet och svarstid är desamma oavsett om de begärs via administrationscentret för Microsoft 365 eller PowerShell.
