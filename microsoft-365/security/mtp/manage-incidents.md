---
title: Hantera ärenden i Microsoft 365 Defender
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, varningar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930636"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Hantera ärenden i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Det är viktigt att hantera incidenter för att säkerställa att hoten är inneslutna och hanteras. I Microsoft 365 Defender har du tillgång till att hantera incidenter på enheter, användare och postlådor. 


Du kan hantera incidenter genom att välja en incident i **kön Incidenter.** 

Du kan redigera namnet på en händelse, lösa den, ange klassificering och avgörande. Du kan också tilldela incidenten till dig själv, lägga till incidenttaggar och kommentarer.

I fall där du under en undersökning vill flytta aviseringar från en händelse till en annan kan du också göra det från fliken Aviseringar, vilket innebär att en större eller mindre incident skapas som inkluderar alla relevanta aviseringar.

## <a name="edit-incident-name"></a>Redigera incidentnamn
Incidenter tilldelas automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

Du kan ändra incidentnamnet så att det bättre överensstämmer med de namngivningskonventioner du föredrar.

> [!NOTE]
> Incidenter som fanns innan den automatiska namnefunktionen för incidenter distribuerades behåller sitt namn.



## <a name="assign-incidents"></a>Tilldela ärenden
Om en incident ännu inte har tilldelats kan du välja Tilldela till **mig** för att tilldela incidenten till dig själv. Då förutsätts ägarskap till inte bara incidenten, utan även alla aviseringar som är kopplade till den.

## <a name="set-status-and-classification"></a>Ange status och klassificering
### <a name="incident-status"></a>Incidentstatus
Du kan kategorisera incidenter (som **aktiva** **eller lösta)** genom att ändra deras status allt eftersom undersökningen fortskrider. På så sätt kan du organisera och hantera hur din grupp kan svara på incidenter.

Din SOC-analytiker kan till exempel granska dagens brådskande **aktiva** ärenden och bestämma att de ska tilldelas till hon själv för undersökning.

Alternativt kan din SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats. När du löser en händelse stängs automatiskt alla aviseringar som är en del av incidenten och är fortfarande öppna. 

### <a name="classification-and-determination"></a>Klassificering och avgörande
Du kan välja att inte ange någon klassificering eller att ange om en incident är sann eller falsk. På så sätt kan teamet se mönster och lära sig av dem. 

## <a name="add-comments"></a>Lägga till kommentarer
Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar som gjorts i den.

När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.

Tillagda kommentarer visas direkt i fönstret.

## <a name="add-incident-tags"></a>Lägga till incidenttaggar
Du kan lägga till anpassade taggar för ett incidenter, till exempel för att flagga en grupp ärenden med gemensamma egenskaper. Du kan senare filtrera ärendekön för alla incidenter som innehåller en specifik tagg.
