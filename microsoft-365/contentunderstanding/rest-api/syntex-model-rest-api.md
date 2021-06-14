---
title: REST API för SharePoint Syntex-dokumentets tolkningsmodell
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Översikt över REST API för SharePoint Syntex-dokumentets förståelsemodell.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908095"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>REST API för SharePoint Syntex-dokumentets tolkningsmodell

Du kan använda REST-gränssnittet i SharePoint för att skapa en dokumenttolkningsmodell, använda eller ta bort modellen i ett eller flera bibliotek och hämta eller uppdatera information om modellen. 

SharePoint Onlines (samt SharePoint 2016 och senare lokalt) REST-tjänst har stöd för att kombinera flera förfrågningar till ett enda anrop till tjänsten genom att använda frågealternativet OData $batch. 

Mer information och länkar till kodexempel finns i [Gör batchbegäranden med REST API:er](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar kontrollerar du att du är bekant med följande:

- [Lär känna REST-tjänsten för SharePoint](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [Slutföra grundläggande åtgärder med hjälp av REST-slutpunkter för SharePoint](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST-kommandon

Följande REST-kommandon är tillgängliga när du arbetar med Syntex dokumenttolkningsmodeller:

- [Create model](rest-createmodel-method.md) – Skapar en modell och dess associerade innehållstyp.
- [GetByUniqueId](rest-getbyuniqueid-method.md) – Hämtar eller uppdaterar information om en SharePoint Syntex dokumenttolkningsmodell.
- [GetByTitle](rest-getbytitle-method.md) – Hämtar eller uppdaterar information om en SharePoint Syntex dokumenttolkningsmodell genom att använda modellrubriken.
- [Apply model](rest-applymodel-method.md) – använder (eller synkroniserar) en tränad dokumenttolkningsmodell till ett eller flera bibliotek.
- [Get model and library information](rest-getmodelandlibraryinfo.md) – Hämtar information om en modell och biblioteket där den tillämpas.
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en SharePoint Syntex dokumenttolkningsmodell.
- [BatchDelete](rest-batchdelete-method.md) – Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.
- [Create classification request](rest-createclassificationrequest.md) – Skapar en begäran om att klassificera en viss fil eller filer med hjälp av den tillämpade modellen.

## <a name="scenarios"></a>Scenarier

Observera följande scenarioexempel som inte är intuitiva från metodnamnet. Mer information finns i varje artikel.

Med metoden “create model” skapas bara modellobjektet och dess associerade innehållstyp. Du måste först träna modellen i innehållscentret innan den kan användas i ett bibliotek.

Metoden “apply model” används för att konfigurera modellen för målbiblioteket för att klassificera dokument och extrahera ytterligare information. Det här API:t stöder också masstillämpning av modellen på flera bibliotek.

Med metoden “remove model” tas modellen bara bort från ett eller flera bibliotek där den tillämpats tidigare. Om du vill ta bort modellen måste den först tas bort från alla bibliotek där den tillämpats.


## <a name="see-also"></a>Se även

[Översikt för dokumenttolkning](../document-understanding-overview.md)

