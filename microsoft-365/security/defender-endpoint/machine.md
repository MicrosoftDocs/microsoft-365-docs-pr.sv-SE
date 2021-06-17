---
title: Maskinresurstyp
description: Läs mer om metoderna och egenskaperna för resurstypen Maskin i Microsoft Defender för Slutpunkt.
keywords: apis, API som stöds, skaffa, datorer
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5ca147c9e69168b2f15aa69bba8728567b782fa9
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984466"
---
# <a name="machine-resource-type"></a>Maskinresurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metoder

Metod|Returtyp |Beskrivning
:---|:---|:---
[Maskinlista](get-machines.md) | [maskinsamling](machine.md) | Lista med [maskinenheter](machine.md) i organisationen.
[Skaffa dator](get-machine-by-id.md) | [dator](machine.md) | Skaffa en [dator](machine.md) efter dess identitet.
[Bli inloggad med användare](get-machine-log-on-users.md) | [användarsamling](user.md) | Hämta den uppsättning [användare](user.md) som loggade in på [datorn.](machine.md)
[Få relaterade aviseringar](get-machine-related-alerts.md) | [aviseringssamling](alerts.md) | Få den uppsättning [aviseringsenheter](alerts.md) som ställdes på [datorn.](machine.md)
[Skaffa installerad programvara](get-installed-software.md) | [programvarusamling](software.md) | Hämtar en samling installerad programvara som är relaterad till ett visst dator-ID.
[Hämta upptäckta sårbarheter](get-discovered-vulnerabilities.md) | [sårbarhetssamling](vulnerability.md) | Hämtar en samling av identifierade svagheter i samband med ett visst maskin-ID.
[Hämta säkerhetsrekommendationer](get-security-recommendations.md) | [samling med rekommendation](recommendation.md) | Hämtar en samling säkerhetsrekommendationer som är relaterade till ett visst dator-ID.
[Lägga till eller ta bort maskintaggar](add-or-remove-machine-tags.md) | [dator](machine.md) | Lägga till eller ta bort tagg till en viss dator.
[Hitta maskiner efter IP](find-machines-by-ip.md) | [maskinsamling](machine.md) | Hitta datorer som kan se med IP.
[Hitta maskiner efter tagg](find-machines-by-tag.md) | [maskinsamling](machine.md) | Hitta datorer efter [Tagg.](machine-tags.md)
[Hämta saknade KB:er](get-missing-kbs-machine.md) | KB-samling | Visa en lista över saknade KB som är kopplade till dator-ID:t
[Ange enhetsvärde](set-device-value.md)| [maskinsamling](machine.md) | Ange [värdet för en enhet](tvm-assign-device-value.md).
[Uppdatera dator](update-machine-method.md) |[maskinsamling](machine.md) | Hämta uppdateringsstatus för en dator.

## <a name="properties"></a>Egenskaper

Egenskap |   Typ   |   Beskrivning
:---|:---|:---
id | Sträng | [datoridentitet.](machine.md)
computerDnsName | Sträng | [fullständigt](machine.md) kvalificerat namn.
firstSeen | DateTimeOffset | Första datum och tid då [datorn observerades](machine.md) av Microsoft Defender för Endpoint.
lastSeen | DateTimeOffset |Tid och datum för rapporten om senast mottagna fullständiga enheter. En enhet skickar vanligtvis en fullständig rapport en gång per dygn.
osPlatform | Sträng | Operativsystemsplattform.
osProcessor | Sträng | Operativsystemsprocessor. Använd egenskapen osArchitecture i stället.
version | Sträng | Operativsystemsversion.
osBuild | Nullbar long | Versionsnummer för operativsystem.
lastIpAddress | Sträng | Senaste IP på lokal NIC på [datorn.](machine.md)
lastExternalIpAddress | Sträng | Senaste IP-adress där [datorn](machine.md) kom åt Internet.
healthStatus | Uppräkning | [status för](machine.md) datorns hälsa. Möjliga värden är: "Aktiv", "Inaktiv", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" och "Unknown". 
rbacGroupName | Sträng | Datorgruppnamn.
riskScore | Nullbar uppräkning | Riskpoäng enligt Microsoft Defender för Endpoint. Möjliga värden är: "Inget", "Informational", "Låg", "Medel" och "Hög".
exponeringStreck | Nullbar uppräkning | [Exponeringsresultat](tvm-exposure-score.md) enligt Microsoft Defender för Endpoint. Möjliga värden är: "Inget", "Låg", "Medel" och "Hög".
aadDeviceId | Nullbar representation Guid | AAD-enhets-ID [(när datorn](machine.md) är AAD ansluten).
machineTags | Strängsamling | Uppsättning [maskintaggar.](machine.md)
exposureLevel | Nullbar uppräkning | Exponeringsnivån enligt Microsoft Defender för Endpoint. Möjliga värden är: "Inget", "Låg", "Medel" och "Hög".
deviceValue | Nullbar uppräkning | Enhetens [värde.](tvm-assign-device-value.md) Möjliga värden är: "Normal", "Låg" och "Hög".
ipAddresses | IpAddress-samling | Uppsättning ***IpAddress-objekt.*** Se [Hämta machines API.](get-machines.md)
osArchitecture | Sträng | Operativsystemsarkitektur. Möjliga värden är: "32-bitars", "64-bitars". Använd den här egenskapen i stället för osProcessor.


