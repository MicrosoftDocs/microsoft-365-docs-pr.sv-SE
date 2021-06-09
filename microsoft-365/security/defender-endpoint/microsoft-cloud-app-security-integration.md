---
title: Översikt över integrering med Microsoft Cloud App Security
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
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844748"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security i Översikt över Defender för slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) är en omfattande lösning som ger insyn i molnappar och -tjänster genom att du kan kontrollera och begränsa åtkomsten till molnappar, samtidigt som du tvingar efterlevnadskrav för data som lagras i molnet. Mer information finns i [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Den här funktionen är tillgänglig [](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) med en E5-Enterprise Mobility + Security på enheter med Windows 10 version 1809 eller senare.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender för slutpunkts- och Cloud App Security integrering 

Cloud App Security identifieringen förlitar sig på att molntrafikloggar vidarebefordras till den från företagets brandvägg och proxyservrar. Microsoft Defender för Endpoint integreras med Cloud App Security genom att samla in och vidarebefordra alla nätverksaktiviteter i molnappen, vilket ger enastående synlighet för användning av molnappen. Övervakningsfunktionerna är inbyggda i enheten, vilket ger fullständig täckning av nätverksaktivitet.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


Integreringen innehåller följande stora förbättringar av den befintliga Cloud App Security identifieringen: 

- Tillgängligt överallt – Eftersom nätverksaktiviteten samlas in direkt från slutpunkten är den tillgänglig oavsett var enheten finns, på eller utanför företagsnätverket, eftersom den inte längre är beroende av trafik som dirigeras genom företagsbrandväggen eller proxyservrarna. 

- Fungerar utan konfiguration krävs – vidarebefordra molntrafikloggar för att Cloud App Security brandväggs- och proxyserverkonfiguration. Det krävs ingen konfiguration Cloud App Security Defender för Slutpunkt och Cloud App Security. Det är bara att slå Microsoft Defender Säkerhetscenter i inställningarna så är du redo. 

- Enhetskontext – Molntrafikloggar saknar enhetskontext. Defender för slutpunktsnätverksaktivitet rapporteras med enhetskontexten (vilken enhet som kom åt molnappen) så att du kan förstå exakt var (enhet) nätverksaktiviteten utfördes, utöver vem (användaren) som utförde den. 

Mer information om molnidentifiering finns i [Arbeta med identifierade appar.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Relaterat ämne

- [Konfigurera integration av Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
