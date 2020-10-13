---
title: Hantera incidenter i skydd mot Microsoft Threat
description: Lär dig hur du tilldelar, uppdaterar status
keywords: incident, incidenter, aviseringar, korrelerade notifieringar, tilldela, uppdatera, status, hantera, klassificering, Microsoft, 365, m365
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c599343233e7e29589bc4e3d1cda01da505b16f1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430567"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Hantera incidenter i skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



Det är viktigt att hantera incidenter för att säkerställa att hoten är placerade och riktade. I Microsoft Threat Protection har du åtkomst till hantering av incidenter på enheter, användare och post lådor. 


Du kan hantera incidenter genom att välja en incident från **kön med incidenter**. 

Du kan redigera namnet på en olycka, lösa det och ange dess klassificering och analys. Du kan också koppla dig själv, lägga till incident märkningar och kommentarer.

I de fall där du skulle vilja flytta aviseringar från en incident till en annan kan du även göra det på fliken aviseringar och på så sätt skapa en större eller mindre olycka som innehåller alla relevanta aviseringar.

## <a name="edit-incident-name"></a>Redigera incident namn
Incidenter tilldelas automatiskt ett namn baserat på notifieringsregler, till exempel antalet slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier. Då kan du snabbt förstå omfattningen av incidenten.

Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*

Du kan ändra namnet på incidenten så att det passar bättre.

> [!NOTE]
> Incidenter som fanns före lanseringen av funktionen för automatisk anmälan av tillbud behåller sitt namn.



## <a name="assign-incidents"></a>Koppla incidenter
Om en olycka ännu inte har tilldelats kan du välja **tilldela till mig** för att koppla dig själv. Detta innebär att ägandet av inte bara är det som är associerat med den.

## <a name="set-status-and-classification"></a>Ange status och klassificering
### <a name="incident-status"></a>Incident status
Du kan kategorisera incidenter (som **aktiva**eller **stängda**) genom att ändra deras status allteftersom undersökningen fortskrider. Det hjälper dig att organisera och hantera hur ditt team kan reagera på händelser.

Ditt SOC analytiker kan till exempel granska brådskande **aktiva** tillbud för dagen och besluta att tilldela dem själv för undersökning.

Alternativt kan SOC analytiker ställa in händelsen som **löst** om incidenten har åtgärd ATS. När du löser ett samtal stängs alla aviseringar som är en del av incidenten och fortfarande öppen. 

### <a name="classification-and-determination"></a>Klassificering och bestämning
Du kan välja att inte ange en klassificering eller välja om en incident är sann eller falsk. Om du gör det kan teamet se mönster och lära sig mer om dem. 

## <a name="add-comments"></a>Lägga till kommentarer
Du kan lägga till kommentarer och Visa historiska händelser om en olycka för att se tidigare gjorda ändringar.

När en ändring eller kommentar görs i en avisering sparas den i avsnittet kommentarer och historik.

Tillagda kommentarer visas direkt i fönstret.

## <a name="add-incident-tags"></a>Lägga till incident koder
Du kan lägga till egna taggar till en olycka, till exempel för att flagga en grupp med incidenter med gemensamma egenskaper. Du kan senare filtrera händelse kön för alla händelser som innehåller en viss tagg.
