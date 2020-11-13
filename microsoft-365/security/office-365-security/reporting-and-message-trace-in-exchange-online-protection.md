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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln lär du dig mer om rapporter och fel söknings verktyg som är tillgängliga för Microsoft Exchange Online Protection (EOP)-administratörer.
ms.openlocfilehash: 856e99e55e6b67d1d22a30e2f55f60857eb4fe75
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020897"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rapportering och meddelande spårning i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det många olika rapporter i EOP som hjälper dig att avgöra den övergripande statusen och tillståndet för din organisation. Det finns också verktyg som hjälper dig att felsöka specifika händelser (till exempel ett meddelande som inte kommer till dess avsedda mottagare) och gransknings rapporter med krav på efterlevnad.

## <a name="usage-reports"></a>Användnings rapporter

**Aktivitet i microsoft 365-grupper** : Visa information om antalet Microsoft 365-grupper som har skapats och använts.

**E-postaktivitet** : Visa information om antalet meddelanden som skickas, tas emot och läses i hela organisationen och av specifika användare.

**Användning av e-postprogram** : Visa information om de e-postappar som används. Detta inkluderar totalt antal anslutningar för varje app och den version av Outlook som är ansluten.

**Användning av post låda** : Visa information om använt lagrings utrymme för kvot, antal objekt och senaste aktivitet (skicka eller läsa aktivitet) för post lådor.

Mer information finns i följande resurser:

- [Microsoft 365-rapporter i administrations Center – Microsoft 365-grupper](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Microsoft 365-rapporter i administrations Center – e-postaktivitet](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Microsoft 365-rapporter i administrations Center – användning av e-postprogram](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Microsoft 365-rapporter i administrations Center – använde brev Låde användning](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Säkerhets & rapporter om efterlevnad i administrations centret för Microsoft 365

De här förbättrade rapporterna ger en interaktiv rapport upplevelse för EOP-administratörer, som innehåller sammanfattnings information och möjlighet att detaljgranska ned för mer information.

**Defender för office 365** : Visa information om säkra länkar och säkra bifogade filer som ingår i Microsoft Defender för Office 365.

**EOP** : Visa information om identifiering av skadlig program vara, falsk e-post, skräp identifiering och e-postflöde till och från din organisation.

[Visa rapporter för Defender för Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Anpassade rapporter med Microsoft Graph

Program mässigt skapa rapporter som är tillgängliga i administrations centret med Microsoft Graph. Mer information finns i [Översikt över Microsoft Graph](https://docs.microsoft.com/graph/overview) och [arbeta med användnings rapporterna för Office 365 i Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="message-trace"></a>Meddelande spårning

Följer e-postmeddelanden när de går genom EOP. Du kan bestämma om ett e-postmeddelande har tagits emot, nekats, uppskjuts eller levererats av tjänsten. Det visar också vilka åtgärder som vidtogs innan meddelandet nådde sin slutliga status.

Du kan använda den här informationen för att effektivt besvara användarnas frågor, felsöka e-postflöden, validera princip ändringar och minska behovet av att kontakta teknisk support för att få hjälp.

Se [meddelande spårning i säkerhets & Compliance Center](message-trace-scc.md).

## <a name="audit-logging"></a>Gransknings loggning

Spårar specifika ändringar som gjorts av administratörer till din organisation. Dessa rapporter kan hjälpa dig att felsöka konfigurations problem eller hitta orsaken till problem med säkerhet eller efterlevnad. Se [granska rapporter i EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Tillgänglighet och svars tid för rapportering och spårning av meddelanden

I följande tabell beskrivs när EOP rapporter och spårnings data för meddelanden är tillgängliga och hur länge.

****

|Rapport typ|Tillgängliga data för (se bakgrunds perioden)|Borttagning|
|---|---|---|
|Sammanfattnings rapporter för e-postskydd|90 dagar|Meddelande data agg regering är mest komplett inom 24-48 timmar. Vissa mindre stegvisa sammanlagda ändringar kan uppkomma i upp till fem dagar.|
|Informations rapporter för e-postskydd|90 dagar|För detalj uppgifter som är mindre än 7 dagar gamla bör data visas inom 24 timmar, men inte förrän 48 timmar. Vissa mindre stegvisa ändringar kan uppstå i upp till fem dagar. <p> Om du vill visa detalj rapporter för meddelanden som är äldre än 7 dagar gamla kan resultatet ta upp till några timmar.|
|Meddelande spårnings data|90 dagar|När du kör en meddelande spårning för meddelanden som är mindre än 7 dagar gamla visas meddelandena inom 5-30 minuter.<p> När du kör en meddelande spårning för meddelanden som är äldre än 7 dagar sedan kan resultatet ta upp till några timmar.|
|

> [!NOTE]
> Data tillgänglighet och svars tid är desamma om de begärs via administrations centret eller Remote PowerShell.
