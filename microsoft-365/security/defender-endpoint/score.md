---
title: Poängmetoder och egenskaper
description: Hämtar organisationens exponeringsresultat, enhet säkra poäng och exponeringsresultat per enhetsgrupp
keywords: apis, graph api, api som stöds, poäng, exponeringspoäng, enhet säker poäng, exponeringsresultat efter enhetsgrupp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 72dacca8529b54b082590d911f03aaa86bfe9097
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200167"
---
# <a name="score-resource-type"></a>Resurstyp för poäng

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metoder

Metod |Returtyp |Beskrivning
:---|:---|:---
[Få exponeringsresultat](get-exposure-score.md) | [Poäng](score.md) | Få exponeringsresultatet för organisationen.
[Få enhet säker poäng](get-device-secure-score.md) | [Poäng](score.md) | Skaffa organisationens enhets säkra poäng.
[Lista över exponeringsresultat per enhetsgrupp](get-machine-group-exposure-score.md)| [Poäng](score.md) | Lista resultat efter enhetsgrupp.

## <a name="properties"></a>Egenskaper

Egenskap |  Skriv    |   Beskrivning
:---|:---|:---
Poäng | Double | Det aktuella resultatet.
Tid | DateTime | Datum och tid då anropet till API:et gjordes.
RbacGroupName | Sträng | Enhetens gruppnamn.
