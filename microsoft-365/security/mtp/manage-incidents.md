---
title: Hantera incidenter i Microsoft Threat Protection
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, varningar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808134"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Hantera incidenter i Microsoft Threat Protection

**Gäller:**
- Microsofts hotskydd



Hanteringen av incidenter är avgörande för att säkerställa att hoten begränsas och åtgärdas. I Microsoft Threat Protection har du åtkomst till hantering av incidenter på enheter, användare och postlådor. 


Du kan hantera incidenter genom att välja en incident från **kön Incidenter**. 

Du kan redigera namnet på en incident, lösa den, ange dess klassificering och bestämning. Du kan också tilldela händelsen till dig själv, lägga till incidenttaggar och kommentarer.

I de fall där du under utredningen vill flytta aviseringar från en incident till en annan kan du också göra det från fliken Aviseringar, vilket skapar en större eller mindre incident som innehåller alla relevanta aviseringar.

## <a name="edit-incident-name"></a>Redigera incidentnamn
Som standard tilldelas en incident ett nummer. Du kan ändra incidentnamnet så att det stämmer överens med den namngivningskonvention som du föredrar.
 
## <a name="assign-incidents"></a>Tilldela incidenter
Om en incident ännu inte har tilldelats kan du välja **Tilldela mig** för att tilldela händelsen till dig själv. Detta förutsätter ägandet av inte bara händelsen, men också alla varningar i samband med den.

## <a name="set-status-and-classification"></a>Ange status och klassificering
### <a name="incident-status"></a>Status för incident
Du kan kategorisera incidenter (som **Aktiv**eller **Löst)** genom att ändra deras status under utredningens gång. Detta hjälper dig att organisera och hantera hur ditt team kan svara på incidenter.

Till exempel kan din SOC-analytiker granska de brådskande **aktiva** incidenter för dagen och besluta att tilldela dem till sig själv för undersökning.

Alternativt kan din SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats. Om du löser en incident stängs alla aviseringar som ingår i incidenten automatiskt. 

### <a name="classification-and-determination"></a>Klassificering och bestämning
Du kan välja att inte ange en klassificering eller bestämma dig för att ange om en incident är sann eller falsk. Detta hjälper teamet att se mönster och lära av dem. 

## <a name="add-comments"></a>Lägga till kommentarer
Du kan lägga till kommentarer och visa historiska händelser om en incident för att se tidigare ändringar som gjorts i den.

När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.

Tillagda kommentarer visas direkt i fönstret.

## <a name="add-incident-tags"></a>Lägga till incidenttaggar
Du kan lägga till anpassade taggar i en incident, till exempel för att flagga en grupp incidenter med gemensamma egenskaper. Du kan senare filtrera incidentkön för alla incidenter som innehåller en specifik tagg.

