---
title: Spåra din Microsoft säkra Poäng historik och uppfylla målen
description: Få insikter i aktiviteter som påverkat din Microsoft säkra poäng. Upptäck trender och ställa in mål.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, säkerhets poäng, Microsoft 365 säkerhets Center, förbättrings åtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738049"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Spåra din Microsoft säkra Poäng historik och uppfylla målen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure score](microsoft-secure-score.md) är ett mått på en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder. Den finns https://security.microsoft.com/securescore i [säkerhets Center för Microsoft 365](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Få information som har påverkat poängen

Visa ett diagram över din organisations poäng över tiden på fliken **Historik** .

Under diagrammet visas en lista över alla åtgärder som utförs under det valda tidsintervallet och deras attribut, till exempel resulterande Poäng och kategori. Du kan anpassa ett datum intervall och filtrera efter kategori.

![Aktivitets historik](../../media/secure-score/secure-score-history-activity.png)

Om du väljer förbättrings åtgärden som är kopplad till en aktivitet visas den utfällbara åtgärden fullständig förbättring.

Om du vill visa all historik för den specifika förbättrings åtgärden väljer du länken historik i utfälld.

![Åtgärds historik för förbättring](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Upptäck trender och ställa in mål

På fliken **mått & trender** finns det flera diagram för att du ska få mer insyn i trender och ställa in mål. Du kan ange datum intervall för hela sidan av visualiseringar. Visualiseringarna inkluderar:

* **Din säkra Poäng zon** – anpassad baserat på organisationens mål och definitioner av bra, OK och dåliga poäng områden.
* **Regressions trend** – en tids linje med punkter som har regressed på grund av ändringar av konfiguration, användare eller enhet.  
* **Jämförelse trend** – hur din organisations säkra Poäng jämförs med andra med över tiden. I den här vyn kan du inkludera rader som representerar medelvärdet av organisationer med liknande antal och en anpassad jämförelse vy som du kan ange.
* **Trend** -och tids linje för att acceptera riskerna.
* **Poäng ändringar** -antalet poäng uppnåddes, Points regressed och ändrade Poäng i angivet datum intervall.

### <a name="compare-your-score-to-organizations-like-yours"></a>Jämför poängen med dina organisationer som dina

Det finns två platser för att se hur poängen jämförs med organisationer som liknar dig. I båda diagrammen kan du välja **Hantera jämförelser** för att visa och redigera din organisations information. Du kan också skapa en anpassad jämförelse utifrån bransch, organisationens storlek, licenser och regioner.

#### <a name="comparison-bar-chart"></a>Jämförelse stapeldiagram

Jämförelse fönstret är fliken **Översikt** . Hovra över diagrammet för att Visa poängen och poängen. Jämförelse data är anonymiserad så vi vet inte exakt vilka andra innehavare är i blandningen.

![Stapeldiagram med likartad Poäng](../../media/secure-score/secure-score-comparison-bar.png)

- **Organisationer** som du vill: ett genomsnittligt antal andra innehavare (förutsatt att vi har minst fem eller fler klient organisationer) som uppfyller följande kriterier:
    1. Samma bransch
    2. Samma organisations storlek
    3. Alla regioner
    4. Microsoft-produkter som används är 80% liknande
    5. Affärs möjlighet (högsta poäng som kan uppnås genom aktuell licens) inom 20% från klient organisationen

- **Anpassad jämförelse**: måste ställas in genom att välja **Hantera jämförelse** utifrån följande kriterier:
    1. Valda branscher
    2. Vald organisations storlek
    3. Markerade regioner
    4. Valda licenser
    5. Microsoft-produkter som används är 80% liknande
    6. Affärs möjlighet (högsta poäng som kan uppnås genom aktuell licens) inom 20% från klient organisationen

Om du har gjort en anpassad markering men resultatet har färre än fem andra klient organisationer som vi kan jämföra med visas "inte tillgängligt på grund av begränsat data".

#### <a name="comparison-trend"></a>Jämförelse trend

På fliken **mått & trender** kan du se hur organisationens säkra Poäng jämförs med andra med över tiden.

![Linje diagram med en liknande organisations resultat över tid](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem kan du meddela oss genom att publicera det i [säkerhets-, integritets &](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar communityn och ger hjälp.

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsofts säkra Poäng](microsoft-secure-score.md)
- [Utvärdera säkerhets genom övergå molnet](microsoft-secure-score-improvement-actions.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Nyheter](microsoft-secure-score-whats-new.md)
