---
title: Spåra din Microsoft Secure Score-historik och uppfylla mål
description: Få inblick i aktiviteter som har påverkat ditt Microsoft Secure Score. Upptäck trender och ange mål.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925678"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Spåra din Microsoft Secure Score-historik och uppfylla mål

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score](microsoft-secure-score.md) är ett mått på en organisations säkerhetssäkerhet, med ett högre tal som anger fler förbättringsåtgärder som vidtas. Den finns på Microsoft https://security.microsoft.com/securescore [365 säkerhetscenter.](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Få insikter i aktivitet som har påverkat ditt resultat

Visa ett diagram över organisationens poäng över tid på **fliken** Historik.

Under diagrammet visas en lista över alla åtgärder som vidtas i det valda tidsperioden och deras attribut, till exempel resulterande punkter och kategori. Du kan anpassa ett datumintervall och filtrera efter kategori.

![Aktivitetshistorik](../../media/secure-score/secure-score-history-activity.png)

Om du väljer den förbättringsåtgärd som är kopplad till en aktivitet visas den fullständiga utfällningen av förbättringsåtgärden.

Om du vill visa all historik för den specifika förbättringsåtgärden väljer du historiklänken i den utfäll du vill visa.

![Åtgärdshistorik för förbättring](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Upptäck trender och ange mål

I fliken **& trender** finns det flera grafer och diagram som ger dig bättre insyn i trender och sätta upp mål. Du kan ange datumintervallet för hela sidan med visualiseringar. Visualiseringarna omfattar:

* **Din zon för säker** poäng – anpassad baserat på organisationens mål och definitioner av bra, okej och dåliga poängintervall.
* **Regressionstrend** – En tidslinje med punkter som har regrerats på grund av konfiguration, användare eller enhetsändringar.  
* **Jämförelsetrend** – Hur organisationens Secure Score står sig jämfört med andras över tid. Den här vyn kan innehålla rader som representerar medelvärdet för organisationer med liknande antal platser och en anpassad jämförelsevy som du kan ange.
* **Riskacceptanstrend** – Tidslinje för förbättringsåtgärder som markerats som "accepterad risk".
* **Poängändringar** – Antalet poäng som har uppnåtts, poäng som har regrerats och ändringar av poängen i det angivna datumintervallet.

### <a name="compare-your-score-to-organizations-like-yours"></a>Jämför resultatet med organisationer som ditt

Det finns två platser där du kan jämföra resultaten med organisationer som liknar dig. I båda diagrammen kan du **välja Hantera jämförelser** för att visa och redigera organisationens information. Du kan också skapa en anpassad jämförelse baserat på bransch, organisationens storlek, licenser och regioner.

#### <a name="comparison-bar-chart"></a>Stapeldiagram med jämförelse

Jämförelsestapeldiagrammet är **fliken** Översikt. Hovra över diagrammet för att visa möjligheten att poäng och poäng. Jämförelsedata anonymiseras så vi vet inte exakt vilka andra klientorganisationar som finns i mixen.

![Stapeldiagram över organisationens resultat](../../media/secure-score/secure-score-comparison-bar.png)

- **Organisationer som din –** en genomsnittlig poäng för andra klientorganisationer (förutsatt att vi har minst fem eller fler klientorganisationer att jämföra) som uppfyller följande kriterier:
    1. Samma bransch
    2. Samma organisationsstorlek
    3. Alla regioner
    4. Microsoft-produkter som används liknar 80 %
    5. Affärsmöjlighet (max poäng som kan uppnås med aktuell licens) inom ett intervall på 20 % från klientorganisationen

- **Anpassad jämförelse:** du måste ställa in genom att **välja Hantera** jämförelse baserat på följande villkor:
    1. Valda bransch(er)
    2. Valda organisationsstorlekar
    3. Valda områden
    4. Valda licenser
    5. Microsoft-produkter som används liknar 80 %
    6. Affärsmöjlighet (max poäng som kan uppnås med aktuell licens) inom ett intervall på 20 % från klientorganisationen

Om du har gjort ett anpassat val, men resultatet har färre än fem andra klientorganisationar som vi kan jämföra med, visas "Inte tillgängligt på grund av begränsade data".

#### <a name="comparison-trend"></a>Jämförelsetrend

I fliken & trender kan du se hur **organisationens** Secure Score står sig jämfört med andras över tid.

![Linjediagram över organisationens resultat över tid](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har problem kan du meddela oss genom att publicera i [communityn för säkerhet, & efterlevnad.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Vi övervakar communityn och hjälper till.

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsoft Secure Score](microsoft-secure-score.md)
- [Utvärdera säkerhets genom övergå molnet](microsoft-secure-score-improvement-actions.md)
- [Kommer snart](microsoft-secure-score-whats-coming.md)
- [Nyheter](microsoft-secure-score-whats-new.md)
