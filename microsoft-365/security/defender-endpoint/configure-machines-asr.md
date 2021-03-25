---
title: Optimera ASR-regeldistribution och identifiering
description: Optimera ASR-reglerna (attack surface reduction) för att identifiera och förhindra vanliga sårbarheter för skadlig programvara.
keywords: onboard, Intune-hantering, MDATP, WDATP, Microsoft Defender, Windows Defender, avancerat skydd mot hot, minska attackytan, ASR, säkerhetsbaslinje
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5ce39bb3ff0bf3eea4ac4e89c554de43499b15f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165483"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Optimera ASR-regeldistribution och identifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).

[ASR-regler (Attack Surface Reduction) identifierar](./attack-surface-reduction.md) och förhindrar vanliga sårbarheter från skadlig programvara. De styr när och hur potentiellt skadlig kod kan köras. De kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar fil, blockera Win32 API-anrop från Office-makron och blockera processer som körs från USB-enheter.

![Kortet Attackyta](images/secconmgmt_asr_card.png)<br>
*Kortet Attackyta*

Kortet *för hantering av attackytor* är en startpunkt för verktyg i Microsoft 365 säkerhetscenter som du kan använda för att:

* Förstå hur ASR-regler för närvarande distribueras i organisationen.
* Granska ASR-identifieringar och identifiera möjliga felaktiga identifieringar.
* Analysera effekterna av undantag och generera listan med filsökvägar som ska undantas.

Välj **Gå till regler för övervakning av attackytor**& i > för minskning av  >  **attackytor > Lägg till undantag**. Därifrån kan du gå till andra avsnitt i Säkerhetscenter för Microsoft 365.

![Fliken Lägg till undantag på sidan För att minska attackytan i Microsoft 365 Säkerhetscenter](images/secconmgmt_asr_m365exlusions.png)<br>
Fliken ***Lägg till undantag** på sidan För att minska attackytan i Microsoft 365 Säkerhetscenter*

> [!NOTE]
> För att komma åt Microsoft 365 säkerhetscenter behöver du en Microsoft 365 E3- eller E5-licens och ett konto som har vissa roller i Azure Active Directory. [Läs om licenser och behörigheter som krävs.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Mer information om distribution av ASR-regler i Säkerhetscenter för Microsoft 365 finns i Övervaka och hantera distribution och identifiering av [ASR-regler.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**Relaterade ämnen**

* [Kontrollera att dina enheter är korrekt konfigurerade](configure-machines.md)
* [Få enheter skickade till Microsoft Defender för Endpoint](configure-machines-onboarding.md)
* [Övervaka efterlevnad av Microsoft Defender för slutpunktens säkerhetsbaslinje](configure-machines-security-baseline.md)
