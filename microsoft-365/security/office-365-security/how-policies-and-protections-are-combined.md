---
title: Så här kombineras policyer och skydd när post rödflaggas
description: Beskriver vilka principer och skydd som gäller när e-post stöter på flera skydd och genomsöks av flera former av identifiering. Vilka policyer gäller och vilka åtgärder som ska vidtas, när e-post är markerat skadlig kod, skräppost, skräppost, nätfiske och bulk av EOP och/eller ATP.
keywords: säkerhet, skadlig kod, Microsoft 365, M365, säkerhetscenter, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 03/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c6b3fcc931aa396187eb81d0db495f77877f667b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806798"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Vilken princip gäller när flera skyddsmetoder och identifieringssökningar körs på din e-post

Eventuellt kan din inkommande e-post flaggas av flera former av skydd (till exempel både EOP *och* ATP) och flera upptäcktsgenomsökningar (t.ex. skräppost *och* nätfiske). Detta är möjligt eftersom det finns ATP-policyer för nätfiske för ATP-kunder och EOP-policyer mot nätfiske för EOP-kunder. Detta innebär också att meddelandet kan navigera flera upptäcktsgenomsökningar för skadlig kod, nätfiske och användarpersonifiering, till exempel. Med tanke på all denna verksamhet kan det råda viss förvirring om vilken politik som gäller.

I allmänhet identifieras en princip som tillämpas på ett meddelande i **x-forefront-antispam-rapporthuvudet** i egenskapen **CAT (Kategori).** Om du har flera anti-phishing-principer gäller den som har högsta prioritet.

Policyerna nedan gäller för _alla organisationer_.

|Prioritet |Politik  |Kategori  |Där hanterad |
|---------|---------|---------|---------|
|1     | Malware      | MALW (malw)      | Policy för skadlig kod   |
|2     | Phishing     | Phsh (phsh)     | Konfigurera principer för skräppostfilter     |
|3     | Högt förtroende spam      | HSPM (HSPM)        | Konfigurera principer för skräppostfilter        |
|4     | Kapning        | Spolat        | Anti-phishing politik, falska intelligens        |
|5     | Spam         | Spm         | Konfigurera principer för skräppostfilter         |
|6     | Bulk         | Bulk        | Konfigurera principer för skräppostfilter         |

Dessutom gäller dessa principer för _organisationer med ATP_.

|Prioritet |Politik  |Kategori  |Där hanterad |
|---------|---------|---------|---------|
|7     | Domänpersonifiering         | DIMP (DIMP)         | Konfigurera Office 365 ATP-policyer för nätfiske och nätfiske        |
|8     | Personifiering för användare        | UIMP         | Konfigurera Office 365 ATP-policyer för nätfiske och nätfiske         |

Om du till exempel har två principer med sina respektive prioriteringar:

|Politik  |Prioritet  |Personifiering av användare/domän  |Anti-spoofing  |
|---------|---------|---------|---------|
|A     | 1        | På        |Av         |
|B     | 2        | Av        | På        |

Om ett meddelande identifieras som både _personifiering_ och _förfalskning_ av användare (se anti-förfalskning i tabellen ovan) och samma uppsättning användare som är begränsade till princip A är begränsad till princip B, flaggas meddelandet och behandlas som en _parodi_. Ingen åtgärd tillämpas dock eftersom även om förfalskning körs med högre prioritet (4) än User Impersonation (8), är Anti-förfalskning avstängd.

Tänk på att administratörer kan skapa en prioriterad lista med principer (se prioritetsfältet ovan), men bara en princip kommer att köras och tillämpa dess åtgärder. Det innebär att en användare i både princip A och B kommer att ha principen med högre prioritet (A är #1) och meddelandet filtreras inte igenom några ytterligare principer. Om anti-spoofiing är avstängd, kommer inga åtgärder att köras.

Eftersom det finns en potential att ha många grupper av användare i många principer kan det vara hoove administratörer att överväga att använda färre principer med fler funktioner. Det är också viktigt att vara säker på att alla användare omfattas av en övergripande politik.

Om du vill att andra typer av nätfiskeprinciper ska gälla måste du justera inställningarna för vem de olika principerna gäller för.



