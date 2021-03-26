---
title: Hantera incidenter i Microsoft 365 Defender
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, aviseringar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3edc7e52e93bc08d46536a520bf57735983f493b
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222629"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Hantera incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Det är viktigt att hantera incidenter för att säkerställa att hoten finns och hanteras. I Microsoft 365 Defender har du åtkomst till att hantera incidenter på enheter, användare och postlådor. 


Du kan hantera incidenter genom att välja en incident från **kön Incidenter.** 

Du kan redigera namnet på en händelse, lösa den, ange dess klassificering och avgörande. Du kan också tilldela incidenten till dig själv, lägga till incidenttaggar och kommentarer.

I fall där du medan du undersöker vill flytta aviseringar från en händelse till en annan kan du också göra det från fliken Aviseringar, vilket innebär att en större eller mindre händelse som inkluderar alla relevanta aviseringar skapas.

## <a name="edit-incident-name"></a>Redigera incidentens namn
Incidenter tilldelas automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

Du kan ändra incidentnamnet så att det bättre överensstämmer med dina föredragna namngivningskonventioner.

> [!NOTE]
> Incidenter som fanns innan de automatiska namnnamnen för incidenter distribuerades kommer att behålla sitt namn.



## <a name="assign-incidents"></a>Tilldela ärenden
Om en incident ännu inte har tilldelats kan du välja Tilldela **till mig** och tilldela incidenten till dig själv. När du gör det förutsätts att du äger inte bara händelsen utan även alla aviseringar som hör till den.

## <a name="set-status-and-classification"></a>Ange status och klassificering
### <a name="incident-status"></a>Incidentstatus
Du kan kategorisera incidenter (som **Aktiva** eller **lösta**) genom att ändra deras status allt eftersom undersökningen fortskrider. På så sätt kan du organisera och hantera hur ditt team kan svara på incidenter.

Din SOC-analytiker kan till  exempel granska brådskande aktiva incidenter för dagen och bestämma sig för att tilldela dem till själv för undersökning.

Alternativt kan SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats. När du löser en händelse stängs automatiskt alla aviseringar som är en del av incidenten och är fortfarande öppna. 

### <a name="classification-and-determination"></a>Klassificering och determination
Du kan välja att inte ange någon klassificering eller att ange om incidenten är sann eller falsk. Det gör det lättare för teamet att se mönster och lära sig av dem. 

## <a name="add-comments"></a>Lägga till kommentarer
Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar i den.

När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.

Tillagda kommentarer visas direkt i fönstret.

## <a name="add-incident-tags"></a>Lägg till incidenttaggar
Du kan lägga till anpassade taggar för en händelse, till exempel för att flagga en grupp med incidenter med en gemensam egenskap. Du kan senare filtrera incidentkön för alla ärenden som innehåller en viss tagg.
