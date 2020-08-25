---
title: Program övervakning & rapportering-säkerhets Center
description: Lär dig mer om hur du får mer insikt i moln programmet i din organisation. Inkluderar olika typer av appar, deras risk nivå och aviseringar.
keywords: säkerhet, skadlig program vara, Microsoft 365, M365, säkerhets Center, övervaka, rapport, appar
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f370a537b9355a99b90f21faab5eda75d7f84cdf
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866855"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Program övervakning och rapportering i säkerhets Center för Microsoft 365

Rapporterna visar mer information om hur molnappar används i din organisation. Inkluderar olika typer av appar, deras risk nivå och aviseringar.

## <a name="monitor-email-accounts-at-risk"></a>Övervaka e-postkonton

**E-postskydd** visar e-postkonton med risk. Du kan välja ett konto att undersöka i Microsoft Defender säkerhets Center.

![E-postskydd](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Övervaka program behörigheter som beviljats av användare

**Cloud App-säkerhet – appar för OAuth-appar** som identifieras av Cloud App Security som har beviljats behörigheter av användare. Cloud App Security-risk katalogen inkluderar över 16 000-program som utvärderas med över 70-riskfaktorer.

Riskfaktorerna börjar med allmän information, till exempel program utgivaren. Därefter flyttas den till säkerhets åtgärder och kontroller, till exempel om appen stöder kryptering på andra eller om det finns en Gransknings logg för användar aktivitet.

![Cloud App-säkerhet för OAuth-appar](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Övervaka användar konton för moln program

**Cloud App-konton för gransknings** listor konton som kan behöva åtgärdas.

![Cloud App-konton för gransknings kort](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Förstå vilka molnappar som används

**Upptäckta moln program (kategorier)** visar vilka typer av program som används i din organisation. Den länkar till moln identifierings instrument panelen i Cloud App Security. Mer information finns i [snabb start: arbeta med upptäckta appar](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Kategori kort för identifierade molnappar](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Övervaka var användare kommer åt molnappar

**Cloud App Activity locations** visar var användarna kan komma åt molnappar.

![Moln programs aktivitets plats kort](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Övervaka hälsa för infrastruktur arbets belastningar

**Infrastruktur hälsa** visar hälso status varningar för infrastruktur arbets belastning i Azure Security Center.

Med Azure Security Center får du enhetlig säkerhets hantering och Avancerat skydd för lokala och moln arbets belastningar. Du kan samla in, söka efter och analysera säkerhets data från olika källor, bland annat brand väggar och andra partner lösningar.

Mer information finns i [dokumentationen för Azure säkerhets Center](https://docs.microsoft.com/azure/security-center/).

![Infrastruktur hälso kort](../../media/infrastructure-health.png)
