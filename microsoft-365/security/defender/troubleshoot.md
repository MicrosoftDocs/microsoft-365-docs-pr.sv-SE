---
title: Felsöka Microsoft 365 Defender-tjänsten
description: Hitta lösningar och lösningar på kända problem Microsoft 365 Defender
keywords: felsöka Microsoft 365 Defender, felsöka, Microsoft Defender för identitet, problem, tillägg, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782747"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Felsöka Microsoft 365 Defender-tjänsten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

I det här avsnittet behandlas problem som kan uppstå när du använder Microsoft 365 Defender-tjänsten.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Jag ser inte Microsoft 365 Defender-innehåll

Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Om det finns sökfunktioner i portalen, måste du kontrollera att klientorganisationen har rätt licenser.

Mer information finns i [Krav](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender för identitetsaviseringar visas inte i Microsoft 365 Defender-incidenterna

Om du har Microsoft Defender för identitet distribuerat i din miljö men du inte ser Defender för identitetsaviseringar som en del av Microsoft 365 Defender-incidenter måste du se till att Microsoft Cloud App Security och Defender för identitetsintegrering är aktiverade.

Mer information finns i [Microsoft Defender för identitetsintegrering.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Var finns inställningssidan för att aktivera tjänsten?

Om du vill Microsoft 365 du på Defender **Inställningar** åtkomst via navigeringsfönstret i Microsoft 365 Säkerhetscenter. Det här navigeringsobjektet visas bara om du har nödvändiga [behörigheter och licenser.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Hur skapar jag ett undantag för min fil/URL?

En falsk positiv inställning är en fil eller URL som identifieras som skadlig men inte är ett hot. Du kan skapa indikatorer och definiera undantag för att häva blockeringen och tillåta vissa filer/URL-adresser. Se [Adress: falska positiva/negativa i Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


