---
title: Hantera Microsoft Defender för slutpunktsincidenter
description: Hantera ärenden genom att tilldela den, uppdatera dess status eller ange dess klassificering.
keywords: incidenter, hantera, tilldela, status, klassificering, sant meddelande, falsk avisering
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: abb538972b48f8790286c0a546eecdd69fc83fb5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862145"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Hantera Microsoft Defender för slutpunktsincidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Hantering av incidenter är en viktig del av varje cybersäkerhetsåtgärd. Du kan hantera incidenter genom att välja en incident **i kön Incidenter** eller **i fönstret Incidenthantering.** 


Om du väljer en incident **i kön Incidenter** visas **fönstret Incidenthantering** där du kan öppna incidentsidan för mer information.


![Bild av hanteringsfönstret för incidenter](images/atp-incidents-mgt-pane-updated.png)

Du kan tilldela incidenter till dig själv, ändra status och klassificering, byta namn på eller kommentera dem för att hålla reda på förloppet.

> [!TIP]
> För att du snabbt ska kunna se fler incidentnamn genereras incidentnamn automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.
>
> Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*
>
> Incidenter som tidigare fanns före automatisk namngivning för incidenter behåller sina namn.
>


![Bild på informationssidan om incidenter](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Tilldela ärenden
Om en incident inte har tilldelats ännu kan du välja Tilldela **till mig och** tilldela incidenten till dig själv. När du gör det förutsätts att du äger inte bara händelsen utan även alla aviseringar som hör till den.

## <a name="set-status-and-classification"></a>Ange status och klassificering
### <a name="incident-status"></a>Incidentstatus
Du kan kategorisera incidenter (som **Aktiva** eller **lösta**) genom att ändra deras status allt eftersom undersökningen fortskrider. På så sätt kan du organisera och hantera hur ditt team kan svara på incidenter.

Din SOC-analytiker kan till  exempel granska brådskande aktiva incidenter för dagen och bestämma sig för att tilldela dem till sig själv för undersökning.

Alternativt kan soc-analytikern ange incidenten som **Löst** om incidenten har åtgärdats. 

### <a name="classification"></a>Klassificering
Du kan välja att inte ange någon klassificering eller att ange om incidenten är sann eller falsk. Det gör det lättare för teamet att se mönster och lära sig av dem.

### <a name="add-comments"></a>Lägga till kommentarer
Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar i den.

När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.

Tillagda kommentarer visas direkt i fönstret.



## <a name="related-topics"></a>Relaterade ämnen
- [Incidentkö](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Visa och ordna incidentkö](view-incidents-queue.md)
- [Undersöka incidenter](investigate-incidents.md)
