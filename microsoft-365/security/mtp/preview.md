---
title: Förhandsgranska funktioner i Microsoft Threat Protection
description: Läs mer om nya funktioner i Microsoft 365-säkerhet
keywords: förhandsgranskning, ny, m365 säkerhet, säkerhet, 365, funktioner
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048273"
---
# <a name="microsoft-threat-protection-preview-features"></a>Förhandsgranskningsfunktioner för Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd


Microsoft Threat Protection-tjänsten uppdateras ständigt för att inkludera nya funktionsförbättringar och funktioner.

Lär dig mer om nya funktioner i förhandsversionen av Microsoft Threat Protection och bli bland de första som provar kommande funktioner genom att aktivera förhandsgranskningsupplevelsen.

Mer information om nya funktioner som är allmänt tillgängliga finns [i Nyheter i Microsoft Threat Protection](whats-new.md).

## <a name="turn-on-preview-features"></a>Aktivera förhandsgranskningsfunktioner
Du får tillgång till kommande funktioner som du kan ge feedback på för att förbättra den övergripande upplevelsen innan funktioner är allmänt tillgängliga.

Aktivera inställningen för förhandsgranskningsupplevelsen så att den är bland de första som kan prova kommande funktioner.

1. Välj **Inställningar**i navigeringsfönstret .

2. Välj **Microsoft Threat Protection**.


3. Välj **Förhandsgranskningsfunktioner**  >  **Aktivera förhandsgranskningsfunktioner**. 

3. Välj **Spara**.

Du vet att du har aktiverat förhandsgranskningsfunktioner när du ser att kryssrutan **Aktivera förhandsgranskningsfunktioner** är markerad. 

## <a name="preview-features"></a>Förhandsgranskningsfunktioner
Följande funktioner och förbättringar är för närvarande tillgängliga vid förhandsversionen:

- **[Schemareferens för portaler](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – information om schematabeller som är tillgängliga direkt i säkerhetscentret. Förutom tabell- och kolumnbeskrivningar innehåller den här referensen information om händelsetyper som stöds `ActionType` (värden) och exempelfrågor.  

- **[Identitets- och apptabeller](advanced-hunting-schema-tables.md)** – få insyn i autentiseringshändelser, Active Directory-frågor och apprelaterad aktivitet med [tabellerna IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)och [AppFileEvents](advanced-hunting-appfileevents-table.md) i det avancerade jaktschemat.

- **[Gå jakt](advanced-hunting-go-hunt.md)** - snabbt pivot från att undersöka en incident för att inspektera en viss händelse, en användare, en enhet eller andra entitetstyper med hjälp av frågebaserade [avancerade jaktfunktioner.](advanced-hunting-overview.md)

- **[FileProfile() funktion](advanced-hunting-fileprofile-function.md)** - använd i dina [avancerade jaktfrågor](advanced-hunting-overview.md) för att införliva omfattande filinformation.
