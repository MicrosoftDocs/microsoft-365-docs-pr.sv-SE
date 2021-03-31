---
title: Lokalisera användarupplevelsen
description: Så här lokaliserar du enheter för användare
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446047"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="d6ecf-104">Lokalisera användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="d6ecf-104">Localize the user experience</span></span>

<span data-ttu-id="d6ecf-105">Användare av Microsoft Managed Desktop-enheter kan välja vilket språk de vill ha antingen under installationen (eller efteråt).</span><span class="sxs-lookup"><span data-stu-id="d6ecf-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="d6ecf-106">Under installationen (när installationen är slut)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="d6ecf-107">När installationen är slutförd kan användarna välja ett språk.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="d6ecf-108">Det här valet påverkar följande attribut:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="d6ecf-109">Språkfunktioner i Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="d6ecf-110">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-110">Display language</span></span>
    - <span data-ttu-id="d6ecf-111">Tangentbordsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-111">Keyboard language</span></span>
    - <span data-ttu-id="d6ecf-112">Språkrelaterade funktioner på begäran</span><span class="sxs-lookup"><span data-stu-id="d6ecf-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="d6ecf-113">Språkfunktioner i Microsoft 365 Apps för företag:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="d6ecf-114">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-114">Display language</span></span>
    - <span data-ttu-id="d6ecf-115">Språkverktyg</span><span class="sxs-lookup"><span data-stu-id="d6ecf-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="d6ecf-116">Användarna kan bara få språkrelaterade funktioner på begäran genom att välja språk under installationen.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="d6ecf-117">När installationen är slutförd</span><span class="sxs-lookup"><span data-stu-id="d6ecf-117">After completing setup</span></span>

<span data-ttu-id="d6ecf-118">Användarna kan när som helst välja språk för Windows 10- och Microsoft 365-appar för företag när som helst efter att installationen är klar.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="d6ecf-119">Mer specifikt:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-119">Specifically:</span></span>

- <span data-ttu-id="d6ecf-120">Språkfunktioner i Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="d6ecf-121">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-121">Display language</span></span>
    - <span data-ttu-id="d6ecf-122">Tangentbordsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-122">Keyboard language</span></span>

- <span data-ttu-id="d6ecf-123">Språkfunktioner i Microsoft 365 Apps för företag:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="d6ecf-124">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="d6ecf-124">Display language</span></span>
    - <span data-ttu-id="d6ecf-125">Språkverktyg</span><span class="sxs-lookup"><span data-stu-id="d6ecf-125">Proofing and authoring tools</span></span>

<span data-ttu-id="d6ecf-126">Om du vill [göra språk som](#supported-languages) stöds för Microsoft 365-program för företag tillgängliga för användarna att installera lägger du till användarna i gruppen Modern **workplace-office-Language_Packs.**</span><span class="sxs-lookup"><span data-stu-id="d6ecf-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="d6ecf-127">Språken blir tillgängliga i Intune-företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="d6ecf-128">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="d6ecf-128">Supported languages</span></span>

<span data-ttu-id="d6ecf-129">För nya enheter måste tillverkaren tillhandahålla enhetsbilder som innehåller de språk du behöver.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="d6ecf-130">Om tillverkarens bild innehåller andra språk än de som anges i listan med språk som stöds stöds detta fortfarande av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="d6ecf-131">Om du återanvänder befintliga enheter kan du behöva kontakta din Microsoft-kontorepresentant för att skaffa lämpliga bilder.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="d6ecf-132">Mer information finns i [Enhetsbilder](../service-description/device-images.md).</span><span class="sxs-lookup"><span data-stu-id="d6ecf-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="d6ecf-133">Den [universella bilden](../service-description/device-images.md#universal-image) som tillhandahålls av Microsoft Managed Desktop inkluderar dessa språk och för Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d6ecf-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="d6ecf-134">Engelska (USA, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-134">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="d6ecf-135">Spanska (Spanien, Mexiko)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-135">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="d6ecf-136">Japanese</span><span class="sxs-lookup"><span data-stu-id="d6ecf-136">Japanese</span></span>
- <span data-ttu-id="d6ecf-137">Franska (Frankrike, Kanada)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-137">French (France, Canada)</span></span>
- <span data-ttu-id="d6ecf-138">German</span><span class="sxs-lookup"><span data-stu-id="d6ecf-138">German</span></span>
- <span data-ttu-id="d6ecf-139">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-139">Portuguese (Brazil)</span></span>
- <span data-ttu-id="d6ecf-140">Italian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-140">Italian</span></span>
- <span data-ttu-id="d6ecf-141">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="d6ecf-141">Chinese Simplified</span></span>
- <span data-ttu-id="d6ecf-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="d6ecf-142">Dutch</span></span>  
- <span data-ttu-id="d6ecf-143">Swedish</span><span class="sxs-lookup"><span data-stu-id="d6ecf-143">Swedish</span></span>
- <span data-ttu-id="d6ecf-144">Danish</span><span class="sxs-lookup"><span data-stu-id="d6ecf-144">Danish</span></span>  
- <span data-ttu-id="d6ecf-145">Finnish</span><span class="sxs-lookup"><span data-stu-id="d6ecf-145">Finnish</span></span> 
- <span data-ttu-id="d6ecf-146">Russian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-146">Russian</span></span> 
- <span data-ttu-id="d6ecf-147">Norska (bokmål)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-147">Norwegian (Bokmal)</span></span>
- <span data-ttu-id="d6ecf-148">Korean</span><span class="sxs-lookup"><span data-stu-id="d6ecf-148">Korean</span></span>
- <span data-ttu-id="d6ecf-149">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="d6ecf-149">Chinese Traditional</span></span>
- <span data-ttu-id="d6ecf-150">Polish</span><span class="sxs-lookup"><span data-stu-id="d6ecf-150">Polish</span></span>
- <span data-ttu-id="d6ecf-151">Turkish</span><span class="sxs-lookup"><span data-stu-id="d6ecf-151">Turkish</span></span>
- <span data-ttu-id="d6ecf-152">Arabiska</span><span class="sxs-lookup"><span data-stu-id="d6ecf-152">Arabic</span></span>
- <span data-ttu-id="d6ecf-153">Hebrew</span><span class="sxs-lookup"><span data-stu-id="d6ecf-153">Hebrew</span></span>
- <span data-ttu-id="d6ecf-154">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-154">Portuguese (Portugal)</span></span>
- <span data-ttu-id="d6ecf-155">Czech</span><span class="sxs-lookup"><span data-stu-id="d6ecf-155">Czech</span></span>
- <span data-ttu-id="d6ecf-156">Hungarian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-156">Hungarian</span></span>
- <span data-ttu-id="d6ecf-157">Thai</span><span class="sxs-lookup"><span data-stu-id="d6ecf-157">Thai</span></span>
- <span data-ttu-id="d6ecf-158">Indonesian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-158">Indonesian</span></span>
- <span data-ttu-id="d6ecf-159">Greek</span><span class="sxs-lookup"><span data-stu-id="d6ecf-159">Greek</span></span>
- <span data-ttu-id="d6ecf-160">Slovak</span><span class="sxs-lookup"><span data-stu-id="d6ecf-160">Slovak</span></span>
- <span data-ttu-id="d6ecf-161">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="d6ecf-161">Vietnamese</span></span>
- <span data-ttu-id="d6ecf-162">Slovenian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-162">Slovenian</span></span>
- <span data-ttu-id="d6ecf-163">Croatian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-163">Croatian</span></span>
- <span data-ttu-id="d6ecf-164">Romanian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-164">Romanian</span></span>
- <span data-ttu-id="d6ecf-165">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-165">Lithuanian</span></span>
- <span data-ttu-id="d6ecf-166">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-166">Bulgarian</span></span>
- <span data-ttu-id="d6ecf-167">Serbiska (latinskt alfabet)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-167">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="d6ecf-168">Latvian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-168">Latvian</span></span>
- <span data-ttu-id="d6ecf-169">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-169">Ukrainian</span></span>
- <span data-ttu-id="d6ecf-170">Estonian</span><span class="sxs-lookup"><span data-stu-id="d6ecf-170">Estonian</span></span>

<span data-ttu-id="d6ecf-171">Microsoft 365 Apps för företag kan ha stöd för en något annorlunda lista.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="d6ecf-172">Om dina användare behöver ett annat språk än de som anges här kan du arkivera en [supportbegäran](../working-with-managed-desktop/admin-support.md) med hjälp av [administrationsportalen.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="d6ecf-173">Språk för support och åtgärder</span><span class="sxs-lookup"><span data-stu-id="d6ecf-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="d6ecf-174">Användarsupport</span><span class="sxs-lookup"><span data-stu-id="d6ecf-174">User support</span></span>
<span data-ttu-id="d6ecf-175">Microsoft Managed Desktop har endast stöd på engelska.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="d6ecf-176">Om användarna väljer ett annat språk i appen Få hjälp får de support från de allmänna Microsoft-supportkanalerna, i stället för att få support direkt från Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="d6ecf-177">Mer information finns i [Få hjälp för användare.](../working-with-managed-desktop/end-user-support.md)</span><span class="sxs-lookup"><span data-stu-id="d6ecf-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="d6ecf-178">Om dina användare behöver stöd på andra språk måste du tillhandahålla det via supportkällor som inte finns från Microsoft eller från din egen organisation.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="d6ecf-179">Administratörsstöd och -åtgärder</span><span class="sxs-lookup"><span data-stu-id="d6ecf-179">Admin support and operations</span></span>
<span data-ttu-id="d6ecf-180">Microsoft Managed Desktop ger administratörssupport endast på engelska.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="d6ecf-181">Det omfattar administrationsportalen och all kommunikation med Microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="d6ecf-182">Du bör förutsätta att alla administratörsrelaterade interaktioner och gränssnitt kommer att vara på engelska, om inget annat anges.</span><span class="sxs-lookup"><span data-stu-id="d6ecf-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


