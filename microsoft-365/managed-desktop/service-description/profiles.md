---
title: Förstå enhetsprofiler
description: De olika profiler som administratörer kan tilldela till enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842008"
---
# <a name="device-profiles"></a>Enhetsprofiler

Du kan tilldela olika förinställt konfigurationer ("enhetsprofiler") till enheter, som var och en är optimerad för specifika typer av användare. Det finns tre enhetsprofiler:

- Standard
- Känsliga data
- Power user

Du kan se enhetsprofiler som en del av en hierarki över konfigurationsalternativ för enheter.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Enhetskonfigurationer visas som en pyramid. Beskrivning följer":::

På ett grundläggande sätt Microsoft Hanterat skrivbord alla enheter en grund som innehåller en standardsäkerhetsbaslinje, efterlevnadsprinciper, Windows uppdatera inställningar och grupper. Om du Microsoft Hanterat skrivbord arbeta med en enhet måste alla enheter innehålla alla dessa element, som inte kan ändras av administratörer utan en begäran att Microsoft Hanterat skrivbord.

Enhetsprofiler visas på nästa högre nivå. Varje Microsoft Hanterat skrivbord enhet måste ha en (och endast en) tilldelad profil. Administratörer kan välja vilken profil en enhet ska tilldelas.

Det finns fler anpassningar på en [ännu högre nivå.](customizing.md) Varje enhet kan ha en eller flera anpassningar (eller ingen). De kan antingen ändra ett lager på lägre nivå (enhetsprofiler eller grundkonfigurationen) eller vara en helt ny begäran som ligger ovanpå standardkonfigurationen.

Högst upp finns dina egna ändringar, till exempel nätverksinformation eller program. En enhet kan ha flera av dessa ändringar, som inte hanteras eller blockeras av Microsoft Hanterat skrivbord.


## <a name="device-profile-details"></a>Profilinformation för enhet

I följande tabell sammanfattas inställningarna och deras standardvärden för varje inställning som konfigurerats efter enhetsprofiler. (Bakom kulisserna konfigureras de här inställningarna med OMA-URIs av anpassade konfigurationsprofiler i Microsoft Endpoint Manager.)

<br>

****

|Funktion|Känsliga data|Power User|Standard|
|---|:---:|:---:|:---:|
|**Blockera externa Storage**|Ja|Ja|Nej|
|**[Molnblocksnivå](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|Högsta|Högsta|Högsta|
|**Inaktivera Microsoft-konton**|Ja|Ja|Nej|
|**Inaktivera personliga OneDrive**|Ja|Ja|Nej|
|**Växla till ett säkert skrivbord för höjd**|Nej|Ja|Nej|
|**Microsoft Defender för endpoint-enhetstagg**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**Administratör på enheten?**|Nej|Ja|Nej|
|**Autopilot-profil**|MMD Standard|MMD Power User|MMD Standard|
|**AppLocker**|Ja|Nej|Nej|
|**Blockera offentlig lagring**|Ja|Ja|Nej|
|

Varje enhetsprofil omfattar även följande objekt:

- En AAD-Azure Active Directory (dynamiskt medlemskap)
- En statisk medlemskapsgrupp för AAD-enhet
- En Microsoft Endpoint Manager konfigurationsprofil

> [!IMPORTANT]
> Ändra inte medlemskapet i de här grupperna direkt. Använd gränssnittet enligt beskrivningen i [Omtilldela profiler](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Begränsningar

Du kan begära undantag från enhetsprofiler och deras information på samma sätt som du skulle göra med andra policyer. Kom ihåg att du bara kan ha en av varje enhetsprofil i din Azure Active Directory organisation ("klientorganisation"). Du kan till exempel inte begära att profilen för känsliga dataenhet inaktiverar AppLocker för endast en del användare. Alla enheter med profilen Känslig information måste ha samma konfiguration.

Varje enhet kan bara ha en profil. Om en viss enhet används av fler än en användare får alla användare på enheten samma konfiguration.
