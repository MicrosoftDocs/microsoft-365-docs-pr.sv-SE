---
title: Microsoft Defender för slutpunktssvars-API:er som stöds
description: Läs mer om specifika svarsrelaterade Microsoft Defender för Endpoint API-anrop.
keywords: response apis, graph api, stöds apis, aktör, aviseringar, enhet, användare, domän, ip, fil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933775"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="27276-104">Microsoft Defender för slutpunktsfråge-API:er som stöds</span><span class="sxs-lookup"><span data-stu-id="27276-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="27276-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="27276-105">**Applies to:**</span></span>
- [<span data-ttu-id="27276-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="27276-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="27276-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="27276-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="27276-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="27276-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="27276-109">Läs mer om vilka svarsrelaterade API-anrop som stöds som du kan köra och information om till exempel rubriker för begäran och förväntat svar från samtalen.</span><span class="sxs-lookup"><span data-stu-id="27276-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="27276-110">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="27276-110">In this section</span></span>
<span data-ttu-id="27276-111">Ämne</span><span class="sxs-lookup"><span data-stu-id="27276-111">Topic</span></span> | <span data-ttu-id="27276-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="27276-112">Description</span></span>
:---|:---
<span data-ttu-id="27276-113">Samla in undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="27276-113">Collect investigation package</span></span> | <span data-ttu-id="27276-114">Kör detta API för att samla in ett undersökningspaket från en enhet.</span><span class="sxs-lookup"><span data-stu-id="27276-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="27276-115">Identifiera enhet</span><span class="sxs-lookup"><span data-stu-id="27276-115">Isolate device</span></span> | <span data-ttu-id="27276-116">Kör detta API för att isolera en enhet från nätverket.</span><span class="sxs-lookup"><span data-stu-id="27276-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="27276-117">Ta bortisolera enhet</span><span class="sxs-lookup"><span data-stu-id="27276-117">Unisolate device</span></span> | <span data-ttu-id="27276-118">Ta bort en enhet från isolation.</span><span class="sxs-lookup"><span data-stu-id="27276-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="27276-119">Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="27276-119">Restrict code execution</span></span> | <span data-ttu-id="27276-120">Kör detta API för att innehålla en attack genom att stoppa skadliga processer.</span><span class="sxs-lookup"><span data-stu-id="27276-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="27276-121">Du kan också låsa en enhet och förhindra att efterföljande försök till potentiellt skadliga program körs.</span><span class="sxs-lookup"><span data-stu-id="27276-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="27276-122">Obegränsad kodkörning</span><span class="sxs-lookup"><span data-stu-id="27276-122">Unrestrict code execution</span></span> | <span data-ttu-id="27276-123">Kör detta för att återställa begränsningen för programprincipen när du har kontrollerat att den komprometterade enheten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="27276-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="27276-124">Kör antivirusgenomsökning</span><span class="sxs-lookup"><span data-stu-id="27276-124">Run antivirus scan</span></span> | <span data-ttu-id="27276-125">Starta en antivirussökning på distans för att identifiera och åtgärda skadlig programvara som kan finnas på en komprometterad enhet.</span><span class="sxs-lookup"><span data-stu-id="27276-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="27276-126">Stoppa och placera filen i karantän</span><span class="sxs-lookup"><span data-stu-id="27276-126">Stop and quarantine file</span></span> |  <span data-ttu-id="27276-127">Kör det här anropet för att sluta köra processer, sätta filer i karantän och ta bort beständiga funktioner, till exempel registernycklar.</span><span class="sxs-lookup"><span data-stu-id="27276-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="27276-128">Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="27276-128">Request sample</span></span> | <span data-ttu-id="27276-129">Kör det här anropet för att begära ett exempel på en fil från en viss enhet.</span><span class="sxs-lookup"><span data-stu-id="27276-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="27276-130">Filen samlas in från enheten och laddas upp till ett säkert lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="27276-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="27276-131">Blockera fil</span><span class="sxs-lookup"><span data-stu-id="27276-131">Block file</span></span> | <span data-ttu-id="27276-132">Kör det här API:t för att förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="27276-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="27276-133">Ta bort blockering av fil</span><span class="sxs-lookup"><span data-stu-id="27276-133">Unblock file</span></span> | <span data-ttu-id="27276-134">Tillåt att en fil körs i organisationen med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="27276-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="27276-135">Hämta SAS URI för paket</span><span class="sxs-lookup"><span data-stu-id="27276-135">Get package SAS URI</span></span> | <span data-ttu-id="27276-136">Kör detta API för att få en URI som gör att du kan ladda ned ett undersökningspaket.</span><span class="sxs-lookup"><span data-stu-id="27276-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="27276-137">Skaffa MachineAction-objekt</span><span class="sxs-lookup"><span data-stu-id="27276-137">Get MachineAction object</span></span> | <span data-ttu-id="27276-138">Kör detta API för att få MachineAction-objekt.</span><span class="sxs-lookup"><span data-stu-id="27276-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="27276-139">Skaffa MachineActions-samlingen</span><span class="sxs-lookup"><span data-stu-id="27276-139">Get MachineActions collection</span></span> | <span data-ttu-id="27276-140">Kör detta för att få MachineAction-samlingen.</span><span class="sxs-lookup"><span data-stu-id="27276-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="27276-141">Skaffa FileActions-samlingen</span><span class="sxs-lookup"><span data-stu-id="27276-141">Get FileActions collection</span></span> | <span data-ttu-id="27276-142">Kör detta API för att få FileActions-samlingen.</span><span class="sxs-lookup"><span data-stu-id="27276-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="27276-143">Skaffa FileMachineAction-objekt</span><span class="sxs-lookup"><span data-stu-id="27276-143">Get FileMachineAction object</span></span> | <span data-ttu-id="27276-144">Kör detta API för att få FileMachineAction-objekt.</span><span class="sxs-lookup"><span data-stu-id="27276-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="27276-145">Hämta FileMachineActions-samlingen</span><span class="sxs-lookup"><span data-stu-id="27276-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="27276-146">Kör detta API för att få FileMachineAction-samlingen.</span><span class="sxs-lookup"><span data-stu-id="27276-146">Run this API to get FileMachineAction collection.</span></span>
