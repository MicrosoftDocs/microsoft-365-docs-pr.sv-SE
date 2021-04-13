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
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691280"
---
# <a name="device-profiles"></a>Enhetsprofiler

Du kan tilldela olika förinställt konfigurationer ("enhetsprofiler") till enheter, som var och en är optimerad för specifika typer av användare. Det finns tre enhetsprofiler:

- Standard
- Känsliga data
- Power user

Du kan se enhetsprofiler som en del av en hierarki över konfigurationsalternativ för enheter.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Enhetskonfigurationer visas som en pyramid. Beskrivning följer":::

I grunden har alla Microsoft Managed Desktop-enheter en grund som innehåller en standardbaslinje för säkerhet, efterlevnadsprinciper, inställningar och grupper för Windows Update. Om du vill arbeta med Microsoft Managed Desktop måste alla enheter innehålla alla dessa element, som inte kan ändras av administratörer utan en begäran om Microsoft Managed Desktop.

Enhetsprofiler visas på nästa högre nivå. Alla Microsoft Managed Desktop-enheter måste ha en (och endast en) tilldelad profil. Administratörer kan välja vilken profil en enhet ska tilldelas.

Det finns fler anpassningar på en [ännu högre nivå.](customizing.md) Varje enhet kan ha en eller flera anpassningar (eller ingen). De kan antingen ändra ett lager på lägre nivå (enhetsprofiler eller grundkonfigurationen) eller vara en helt ny begäran som ligger ovanpå standardkonfigurationen.

Högst upp finns dina egna ändringar, till exempel nätverksinformation eller program. En enhet kan ha flera av dessa ändringar, som inte hanteras eller blockeras av Microsoft Managed Desktop.


## <a name="device-profile-details"></a>Profilinformation för enhet

I följande tabell sammanfattas inställningarna och deras standardvärden för varje inställning som konfigurerats efter enhetsprofiler. (Bakom kulisserna konfigureras de här inställningarna med OMA-URIs med hjälp av anpassade konfigurationsprofiler i Microsoft Endpoint Manager.)

| Funktion | Känsliga data | Power User | Standard |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Blockera extern lagring**                                                                                                                               | Ja                       | Ja                   | Nej                   |
| **[Molnblocksnivå](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Högsta                      | Högsta                  | Högsta                 |
| **Inaktivera Microsoft-konton**                                                                                                                           | Ja                       | Ja                   | Nej                   |
| **Inaktivera personlig OneDrive**                                                                                                                            | Ja                       | Ja                   | Nej                   |
| **Växla till ett säkert skrivbord för höjd**                                                                                                               | Nej                        | Ja                   | Nej                   |
| **Microsoft Defender för endpoint-enhetstagg**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **Administratör på enheten?**                                                                                                                                 | Nej                        | Ja                   | Nej                   |
| **Autopilot-profil**                                                                                                                                     | MMD Standard               | MMD Power User         | MMD Standard          |
| **AppLocker**                                                                                                                                            | Ja                       | Nej                    | Nej                   |
| **Blockera offentlig lagring**                                                                                                                                   | Ja                       | Ja                   | Nej                   |

Varje enhetsprofil omfattar även följande objekt:

- En Azure Active Directory-enhetsgrupp (Dynamic Membership) (AAD)
- En statisk medlemskapsgrupp för AAD-enhet
- En konfigurationsprofil för Microsoft Endpoint Manager

> [!IMPORTANT]
> Ändra inte medlemskapet i de här grupperna direkt. Använd gränssnittet enligt beskrivningen i [Omtilldela profiler](../working-with-managed-desktop/change-device-profile.md).

## <a name="limitations"></a>Begränsningar

Du kan begära undantag från enhetsprofiler och deras information på samma sätt som du skulle göra med andra policyer. Kom ihåg att du bara kan ha en av varje enhetsprofil i din Azure Active Directory-organisation ("klientorganisation"). Du kan till exempel inte begära att profilen för känsliga dataenhet inaktiverar AppLocker för endast en del användare. Alla enheter med profilen Känslig information måste ha samma konfiguration.

Varje enhet kan bara ha en profil. Om en viss enhet används av fler än en användare får alla användare på enheten samma konfiguration.
