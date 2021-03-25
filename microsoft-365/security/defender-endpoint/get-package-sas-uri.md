---
title: Hämta SAS URI API för paket
description: Använd detta API för att få en URI som gör att du kan ladda ned ett undersökningspaket.
keywords: apis, graph api, API som stöds, hämta paket, sas, uri
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b410168f77266a95e2bb74e0c9514ab950840100
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198287"
---
# <a name="get-package-sas-uri-api"></a><span data-ttu-id="5c311-104">Hämta SAS URI API för paket</span><span class="sxs-lookup"><span data-stu-id="5c311-104">Get package SAS URI API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c311-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5c311-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5c311-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5c311-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c311-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5c311-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="5c311-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c311-108">API description</span></span>
<span data-ttu-id="5c311-109">Hämta en URI som tillåter nedladdning av ett [undersökningspaket.](collect-investigation-package.md)</span><span class="sxs-lookup"><span data-stu-id="5c311-109">Get a URI that allows downloading of an [Investigation package](collect-investigation-package.md).</span></span>


## <a name="permissions"></a><span data-ttu-id="5c311-110">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5c311-110">Permissions</span></span>
<span data-ttu-id="5c311-111">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="5c311-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c311-112">Mer information, inklusive hur du väljer behörigheter, finns i Använda [ATP-API:er för Microsoft Defender](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5c311-112">To learn more, including how to choose permissions, see [Use Microsoft Defender ATP APIs](apis-intro.md)</span></span>

<span data-ttu-id="5c311-113">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="5c311-113">Permission type</span></span> |   <span data-ttu-id="5c311-114">Behörighet</span><span class="sxs-lookup"><span data-stu-id="5c311-114">Permission</span></span>  |   <span data-ttu-id="5c311-115">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="5c311-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5c311-116">Program</span><span class="sxs-lookup"><span data-stu-id="5c311-116">Application</span></span> |   <span data-ttu-id="5c311-117">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5c311-117">Machine.CollectForensics</span></span> |  <span data-ttu-id="5c311-118">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="5c311-118">'Collect forensics'</span></span>
<span data-ttu-id="5c311-119">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5c311-119">Delegated (work or school account)</span></span> | <span data-ttu-id="5c311-120">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5c311-120">Machine.CollectForensics</span></span> | <span data-ttu-id="5c311-121">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="5c311-121">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="5c311-122">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="5c311-122">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5c311-123">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="5c311-123">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5c311-124">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="5c311-124">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5c311-125">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5c311-125">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action id}/getPackageUri
```

## <a name="request-headers"></a><span data-ttu-id="5c311-126">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="5c311-126">Request headers</span></span>

<span data-ttu-id="5c311-127">Namn</span><span class="sxs-lookup"><span data-stu-id="5c311-127">Name</span></span> | <span data-ttu-id="5c311-128">Skriv</span><span class="sxs-lookup"><span data-stu-id="5c311-128">Type</span></span> | <span data-ttu-id="5c311-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c311-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c311-130">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5c311-130">Authorization</span></span> | <span data-ttu-id="5c311-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="5c311-131">String</span></span> | <span data-ttu-id="5c311-132">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5c311-132">Bearer {token}.</span></span> <span data-ttu-id="5c311-133">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5c311-133">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5c311-134">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="5c311-134">Request body</span></span>
<span data-ttu-id="5c311-135">Tom</span><span class="sxs-lookup"><span data-stu-id="5c311-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5c311-136">Svar</span><span class="sxs-lookup"><span data-stu-id="5c311-136">Response</span></span>
<span data-ttu-id="5c311-137">Om det lyckas returnerar den här metoden 200, OK-svarskod med objekt som innehåller länken till paketet i parametern "värde".</span><span class="sxs-lookup"><span data-stu-id="5c311-137">If successful, this method returns 200, Ok response code with object that holds the link to the package in the “value” parameter.</span></span> <span data-ttu-id="5c311-138">Den här länken är giltig under en mycket kort tid och bör användas direkt för att ladda ned paketet till en lokal lagring.</span><span class="sxs-lookup"><span data-stu-id="5c311-138">This link is valid for a very short time and should be used immediately for downloading the package to a local storage.</span></span>


## <a name="example"></a><span data-ttu-id="5c311-139">Exempel</span><span class="sxs-lookup"><span data-stu-id="5c311-139">Example</span></span>

<span data-ttu-id="5c311-140">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="5c311-140">**Request**</span></span>

<span data-ttu-id="5c311-141">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="5c311-141">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/7327b54fd718525cbca07dacde913b5ac3c85673/GetPackageUri

```

<span data-ttu-id="5c311-142">**Svar**</span><span class="sxs-lookup"><span data-stu-id="5c311-142">**Response**</span></span>

<span data-ttu-id="5c311-143">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="5c311-143">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "\"https://userrequests-us.securitycenter.windows.com:443/safedownload/WDATP_Investigation_Package.zip?token=gbDyj7y%2fbWGAZjn2sFiZXlliBTXOCVG7yiJ6mXNaQ9pLByC2Wxeno9mENsPFP3xMk5l%2bZiJXjLvqAyNEzUNROxoM2I1er9dxzfVeBsxSmclJjPsAx%2btiNyxSz1Ax%2b5jaT5cL5bZg%2b8wgbwY9urXbTpGjAKh6FB1e%2b0ypcWkPm8UkfOwsmtC%2biZJ2%2bPqnkkeQk7SKMNoAvmh9%2fcqDIPKXGIBjMa0D9auzypOqd8bQXp7p2BnLSH136BxST8n9IHR4PILvRjAYW9kvtHkBpBitfydAsUW4g2oDZSPN3kCLBOoo1C4w4Lkc9Bc3GNU2IW6dfB7SHcp7G9p4BDkeJl3VuDs6esCaeBorpn9FKJ%2fXo7o9pdcI0hUPZ6Ds9hiPpwPUtz5J29CBE3QAopCK%2fsWlf6OW2WyXsrNRSnF1tVE5H3wXpREzuhD7S4AIA3OIEZKzC4jIPLeMu%2bazZU9xGwuc3gICOaokbwMJiZTqcUuK%2fV9YdBdjdg8wJ16NDU96Pl6%2fgew2KYuk6Wo7ZuHotgHI1abcsvdlpe4AvixDbqcRJthsg2PpLRaFLm5av44UGkeK6TJpFvxUn%2f9fg6Zk5yM1KUTHb8XGmutoCM8U9er6AzXZlY0gGc3D3bQOg41EJZkEZLyUEbk1hXJB36ku2%2bW01cG71t7MxMBYz7%2bdXobxpdo%3d%3bRWS%2bCeoDfTyDcfH5pkCg6hYDmCOPr%2fHYQuaUWUBNVnXURYkdyOzVHqp%2fe%2f1BNyPdVoVkpQHpz1pPS3b5g9h7IMmNKCk5gFq5m2nPx6kk9EYtzx8Ndoa2m9Yj%2bSaf8zIFke86YnfQL4AYewsnQNJJh4wc%2bXxGlBq7axDcoiOdX91rKzVicH3GSBkFoLFAKoegWWsF%2fEDZcVpF%2fXUA1K8HvB6dwyfy4y0sAqnNPxYTQ97mG7yHhxPt4Pe9YF2UPPAJVuEf8LNlQ%2bWHC9%2f7msF6UUI4%2fca%2ftpjFs%2fSNeRE8%2fyQj21TI8YTF1SowvaJuDc1ivEoeopNNGG%2bGI%2fX0SckaVxU9Hdkh0zbydSlT5SZwbSwescs0IpzECitBbaLUz4aT8KTs8T0lvx8D7Te3wVsKAJ1r3iFMQZrlk%2bS1WW8rvac7oHRx2HKURn1v7fDIQWgJr9aNsNlFz4fLJ50T2qSHuuepkLVbe93Va072aMGhvr09WVKoTpAf1j2bcFZZU6Za5PxI32mr0k90FgiYFJ1F%2f1vRDrGwvWVWUkR3Z33m4g0gHa52W1FMxQY0TJIwbovD6FaSNDx7xhKZSd5IJ7r6P91Gez49PaZRcAZPjd%2bfbul3JNm1VqQPTLohT7wa0ymRiXpSST74xtFzuEBzNSNATdbngj3%2fwV4JesTjZjIj5Dc%3d%3blumqauVlFuuO8MQffZgs0tLJ4Fq6fpeozPTdDf8Ll6XLegi079%2b4mSPFjTK0y6eohstxdoOdom2wAHiZwk0u4KLKmRkfYOdT1wHY79qKoBQ3ZDHFTys9V%2fcwKGl%2bl8IenWDutHygn5IcA1y7GTZj4g%3d%3d\""
}


```
