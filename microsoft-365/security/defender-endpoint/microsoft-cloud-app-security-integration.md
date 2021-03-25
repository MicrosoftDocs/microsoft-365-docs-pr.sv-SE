---
title: Översikt över integrering av Microsoft Cloud App-säkerhet
ms.reviewer: ''
description: Microsoft Defender för Endpoint integreras med Cloud App Security genom att vidarebefordra alla nätverksaktiviteter i molnet.
keywords: moln, app, nätverk, synlighet, användning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074329"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Översikt över Microsoft Cloud App Security i Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) är en omfattande lösning som ger insyn i molnappar och -tjänster genom att kontrollera och begränsa åtkomsten till molnappar, samtidigt som efterlevnadskraven för data som lagras i molnet upprätthålls. Mer information finns i [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter med Windows 10 version 1809 eller senare.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender för slutpunkts- och molnappens säkerhetsintegrering 

Identifiering av Molnappsäkerhet förlitar sig på att molntrafikloggar vidarebefordras till den från företagets brandvägg och proxyservrar. Microsoft Defender för Endpoint integreras med Cloud App Security genom att samla in och vidarebefordra alla nätverksaktiviteter i molnet, vilket ger enastående synlighet till användning av molnappen. Övervakningsfunktionerna är inbyggda i enheten, vilket ger fullständig täckning av nätverksaktivitet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


Integreringen innehåller följande större förbättringar av den befintliga Cloud App Security-identifieringen: 

- Tillgängligt överallt – Eftersom nätverksaktiviteten samlas in direkt från slutpunkten är den tillgänglig oavsett var enheten finns, på eller utanför företagsnätverket, eftersom den inte längre är beroende av trafik som dirigeras genom företagsbrandväggen eller proxyservrarna. 

- Fungerar utan att konfiguration krävs – Vidarebefordra molntrafikloggar till Cloud App Security kräver brandväggs- och proxyserverkonfiguration. Det krävs ingen konfiguration med Defender för slutpunkts- och molnappens säkerhetsintegrering. Det är bara att slå på den i inställningarna för Microsoft Defender Säkerhetscenter så är du redo. 

- Enhetskontext – Molntrafikloggar saknar enhetskontext. Defender för slutpunktsnätverksaktivitet rapporteras med enhetskontexten (vilken enhet som kom åt molnappen) så att du kan förstå exakt var (enhet) nätverksaktiviteten utfördes, utöver vem (användaren) som utförde den. 

Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Relaterade ämnen

- [Konfigurera Microsoft Cloud App-säkerhetsintegrering](microsoft-cloud-app-security-config.md)
