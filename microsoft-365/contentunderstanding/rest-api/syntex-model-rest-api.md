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
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904317"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="928ca-103">REST API för SharePoint Syntex-dokumentets tolkningsmodell</span><span class="sxs-lookup"><span data-stu-id="928ca-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="928ca-104">Du kan använda REST-gränssnittet i SharePoint för att skapa en dokumenttolkningsmodell, använda eller ta bort modellen i ett eller flera bibliotek och hämta eller uppdatera information om modellen.</span><span class="sxs-lookup"><span data-stu-id="928ca-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="928ca-105">SharePoint Onlines (samt SharePoint 2016 och senare lokalt) REST-tjänst har stöd för att kombinera flera förfrågningar till ett enda anrop till tjänsten genom att använda frågealternativet OData $batch.</span><span class="sxs-lookup"><span data-stu-id="928ca-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="928ca-106">Mer information och länkar till kodexempel finns i [Gör batchbegäranden med REST API:er](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span><span class="sxs-lookup"><span data-stu-id="928ca-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="928ca-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="928ca-107">Prerequisites</span></span>

<span data-ttu-id="928ca-108">Innan du börjar kontrollerar du att du är bekant med följande:</span><span class="sxs-lookup"><span data-stu-id="928ca-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="928ca-109">Lär känna REST-tjänsten för SharePoint</span><span class="sxs-lookup"><span data-stu-id="928ca-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="928ca-110">Slutföra grundläggande åtgärder med hjälp av REST-slutpunkter för SharePoint</span><span class="sxs-lookup"><span data-stu-id="928ca-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="928ca-111">REST-kommandon</span><span class="sxs-lookup"><span data-stu-id="928ca-111">REST commands</span></span>

<span data-ttu-id="928ca-112">Följande REST-kommandon är tillgängliga när du arbetar med Syntex dokumenttolkningsmodeller:</span><span class="sxs-lookup"><span data-stu-id="928ca-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="928ca-113">[Create model](rest-createmodel-method.md) – Skapar en modell och dess associerade innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="928ca-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="928ca-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Hämtar eller uppdaterar information om en SharePoint Syntex dokumenttolkningsmodell.</span><span class="sxs-lookup"><span data-stu-id="928ca-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="928ca-115">[GetByTitle](rest-getbytitle-method.md) – Hämtar eller uppdaterar information om en SharePoint Syntex dokumenttolkningsmodell genom att använda modellrubriken.</span><span class="sxs-lookup"><span data-stu-id="928ca-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="928ca-116">[Apply model](rest-applymodel-method.md) – använder (eller synkroniserar) en tränad dokumenttolkningsmodell till ett eller flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="928ca-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="928ca-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Hämtar information om en modell och biblioteket där den tillämpas.</span><span class="sxs-lookup"><span data-stu-id="928ca-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="928ca-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en SharePoint Syntex dokumenttolkningsmodell.</span><span class="sxs-lookup"><span data-stu-id="928ca-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="928ca-119">[BatchDelete](rest-batchdelete-method.md) – Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="928ca-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="928ca-120">[Create classification request](rest-createclassificationrequest.md) – Skapar en begäran om att klassificera en viss fil eller filer med hjälp av den tillämpade modellen.</span><span class="sxs-lookup"><span data-stu-id="928ca-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="928ca-121">Scenarier</span><span class="sxs-lookup"><span data-stu-id="928ca-121">Scenarios</span></span>

<span data-ttu-id="928ca-122">Observera följande scenarioexempel som inte är intuitiva från metodnamnet.</span><span class="sxs-lookup"><span data-stu-id="928ca-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="928ca-123">Mer information finns i varje artikel.</span><span class="sxs-lookup"><span data-stu-id="928ca-123">For more information, see each article.</span></span>

<span data-ttu-id="928ca-124">Med metoden “create model” skapas bara modellobjektet och dess associerade innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="928ca-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="928ca-125">Du måste först träna modellen i innehållscentret innan den kan användas i ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="928ca-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="928ca-126">Metoden “apply model” används för att konfigurera modellen för målbiblioteket för att klassificera dokument och extrahera ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="928ca-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="928ca-127">Det här API:t stöder också masstillämpning av modellen på flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="928ca-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="928ca-128">Med metoden “remove model” tas modellen bara bort från ett eller flera bibliotek där den tillämpats tidigare.</span><span class="sxs-lookup"><span data-stu-id="928ca-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="928ca-129">Om du vill ta bort modellen måste den först tas bort från alla bibliotek där den tillämpats.</span><span class="sxs-lookup"><span data-stu-id="928ca-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="928ca-130">Se även</span><span class="sxs-lookup"><span data-stu-id="928ca-130">See also</span></span>

[<span data-ttu-id="928ca-131">Översikt för dokumenttolkning</span><span class="sxs-lookup"><span data-stu-id="928ca-131">Document understanding overview</span></span>](../document-understanding-overview.md)

