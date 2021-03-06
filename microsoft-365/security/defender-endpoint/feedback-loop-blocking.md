---
title: Blockering av feedbackslinga
description: Blockering av feedbackslingor, även kallat snabbt skydd, är en del av funktioner för blockering och inneslutning i Microsoft Defender för Endpoint
keywords: beteendeblockering, snabbt skydd, feedbackblockering, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842464"
---
# <a name="feedback-loop-blocking"></a>Blockering av feedbackslinga

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Översikt

Blockering av feedbackslingor, även kallat snabbt [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) skydd, är en komponent i funktioner för beteendeblockering och inneslutning i [Microsoft Defender för Slutpunkt.](/windows/security/threat-protection/) Med blockering av feedbackslinga skyddas enheter i organisationen bättre mot attacker. 

## <a name="how-feedback-loop-blocking-works"></a>Så här fungerar blockering av feedbackslingar

När ett misstänkt beteende eller en fil identifieras, till exempel [av Microsoft Defender Antivirus,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)skickas information om artefakten till flera klassificerare. Den snabba skyddslingsmotorn inspekterar och korrelerar informationen med andra signaler för att komma till ett beslut om huruvida en fil ska blockeras. Det går snabbt att kontrollera och klassificera artefakter. Det leder till snabb blockering av bekräftad skadlig programvara och skyddar hela ekosystemet. 

Med snabbt skydd på plats kan en attack stoppas på en enhet, andra enheter i organisationen och enheter i andra organisationer eftersom en attack försöker bredda fothoppet.


## <a name="configuring-feedback-loop-blocking"></a>Konfigurera blockering av feedbackslinga

Om din organisation använder Defender för Endpoint är blockering av feedbackslinga aktiverad som standard. Ett snabbt skydd sker emellertid genom en kombination av Defender för Endpoint-funktioner, funktioner för maskininlärningsskydd och signaldelning mellan Microsofts säkerhetstjänster. Kontrollera att följande funktioner i Defender för Slutpunkt är aktiverade och konfigurerade:

- [Microsoft Defender för slutpunktsbaslinjer](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Enheter som finns i Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR i blockläge](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Minskning av attackytan](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Nästa generations skydd](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Relaterade artiklar

- [Beteendeblockering och inneslutning](behavioral-blocking-containment.md)

- [(Blogg) Beteendeblockering och inneslutning: Omvandla fiberoptisk till skydd](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Användbara Microsoft Defender för Slutpunkt-resurser](/microsoft-365/security/defender-endpoint/helpful-resources)
