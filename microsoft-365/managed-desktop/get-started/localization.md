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
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023267"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="9070c-104">Lokalisera användarupplevelsen</span><span class="sxs-lookup"><span data-stu-id="9070c-104">Localize the user experience</span></span>

<span data-ttu-id="9070c-105">Användare av Microsoft Hanterat skrivbord-enheter kan välja vilket språk de vill ha antingen under installationen (eller efteråt).</span><span class="sxs-lookup"><span data-stu-id="9070c-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="9070c-106">Under installationen (när installationen är slut)</span><span class="sxs-lookup"><span data-stu-id="9070c-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="9070c-107">När installationen är slutförd kan användarna välja ett språk.</span><span class="sxs-lookup"><span data-stu-id="9070c-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="9070c-108">Det här valet påverkar följande attribut:</span><span class="sxs-lookup"><span data-stu-id="9070c-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="9070c-109">Windows 10 språkfunktioner:</span><span class="sxs-lookup"><span data-stu-id="9070c-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="9070c-110">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-110">Display language</span></span>
    - <span data-ttu-id="9070c-111">Tangentbordsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-111">Keyboard language</span></span>
    - <span data-ttu-id="9070c-112">Språkrelaterade funktioner på begäran</span><span class="sxs-lookup"><span data-stu-id="9070c-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="9070c-113">Microsoft 365 Språkfunktioner för Appar för företag:</span><span class="sxs-lookup"><span data-stu-id="9070c-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="9070c-114">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-114">Display language</span></span>
    - <span data-ttu-id="9070c-115">Språkverktyg</span><span class="sxs-lookup"><span data-stu-id="9070c-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="9070c-116">Användarna kan bara få språkrelaterade funktioner på begäran genom att välja språk under installationen.</span><span class="sxs-lookup"><span data-stu-id="9070c-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="9070c-117">När installationen är slutförd</span><span class="sxs-lookup"><span data-stu-id="9070c-117">After completing setup</span></span>

<span data-ttu-id="9070c-118">Användarna kan välja språk för de olika Windows 10 och Microsoft 365 för företag när som helst efter att installationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9070c-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="9070c-119">Mer specifikt:</span><span class="sxs-lookup"><span data-stu-id="9070c-119">Specifically:</span></span>

- <span data-ttu-id="9070c-120">Windows 10 språkfunktioner:</span><span class="sxs-lookup"><span data-stu-id="9070c-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="9070c-121">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-121">Display language</span></span>
    - <span data-ttu-id="9070c-122">Tangentbordsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-122">Keyboard language</span></span>

- <span data-ttu-id="9070c-123">Microsoft 365 Språkfunktioner för Appar för företag:</span><span class="sxs-lookup"><span data-stu-id="9070c-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="9070c-124">Visningsspråk</span><span class="sxs-lookup"><span data-stu-id="9070c-124">Display language</span></span>
    - <span data-ttu-id="9070c-125">Språkverktyg</span><span class="sxs-lookup"><span data-stu-id="9070c-125">Proofing and authoring tools</span></span>

<span data-ttu-id="9070c-126">Om du vill [göra språk](#supported-languages) som stöds för Microsoft 365-program för företag tillgängliga för användarna att installera lägger du till användarna i gruppen **Modern Office-Language_Packs.**</span><span class="sxs-lookup"><span data-stu-id="9070c-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="9070c-127">Språken är tillgängliga i Intune-företagsportal.</span><span class="sxs-lookup"><span data-stu-id="9070c-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="9070c-128">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="9070c-128">Supported languages</span></span>

<span data-ttu-id="9070c-129">För nya enheter måste tillverkaren tillhandahålla enhetsbilder som innehåller de språk du behöver.</span><span class="sxs-lookup"><span data-stu-id="9070c-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="9070c-130">Om tillverkarens bild innehåller andra språk än de som anges i listan med språk som stöds stöds detta fortfarande av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9070c-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="9070c-131">Om du återanvänder befintliga enheter kan du behöva kontakta din Microsoft-kontorepresentant för att skaffa lämpliga bilder.</span><span class="sxs-lookup"><span data-stu-id="9070c-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="9070c-132">Mer information finns i [Enhetsbilder](../service-description/device-images.md).</span><span class="sxs-lookup"><span data-stu-id="9070c-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="9070c-133">Den [universella](../service-description/device-images.md#universal-image) bilden som tillhandahålls Microsoft Hanterat skrivbord inkluderar dessa språk och för Windows 10:</span><span class="sxs-lookup"><span data-stu-id="9070c-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="9070c-134">Arabiska</span><span class="sxs-lookup"><span data-stu-id="9070c-134">Arabic</span></span>
- <span data-ttu-id="9070c-135">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="9070c-135">Bulgarian</span></span>
- <span data-ttu-id="9070c-136">Chinese Simplified</span><span class="sxs-lookup"><span data-stu-id="9070c-136">Chinese Simplified</span></span>
- <span data-ttu-id="9070c-137">Chinese Traditional</span><span class="sxs-lookup"><span data-stu-id="9070c-137">Chinese Traditional</span></span>
- <span data-ttu-id="9070c-138">Croatian</span><span class="sxs-lookup"><span data-stu-id="9070c-138">Croatian</span></span>
- <span data-ttu-id="9070c-139">Czech</span><span class="sxs-lookup"><span data-stu-id="9070c-139">Czech</span></span>
- <span data-ttu-id="9070c-140">Danish</span><span class="sxs-lookup"><span data-stu-id="9070c-140">Danish</span></span>  
- <span data-ttu-id="9070c-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="9070c-141">Dutch</span></span>  
- <span data-ttu-id="9070c-142">Engelska (USA, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="9070c-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="9070c-143">Estonian</span><span class="sxs-lookup"><span data-stu-id="9070c-143">Estonian</span></span>
- <span data-ttu-id="9070c-144">Finnish</span><span class="sxs-lookup"><span data-stu-id="9070c-144">Finnish</span></span> 
- <span data-ttu-id="9070c-145">Franska (Frankrike, Kanada)</span><span class="sxs-lookup"><span data-stu-id="9070c-145">French (France, Canada)</span></span>
- <span data-ttu-id="9070c-146">German</span><span class="sxs-lookup"><span data-stu-id="9070c-146">German</span></span>
- <span data-ttu-id="9070c-147">Greek</span><span class="sxs-lookup"><span data-stu-id="9070c-147">Greek</span></span>
- <span data-ttu-id="9070c-148">Hebrew</span><span class="sxs-lookup"><span data-stu-id="9070c-148">Hebrew</span></span>
- <span data-ttu-id="9070c-149">Hungarian</span><span class="sxs-lookup"><span data-stu-id="9070c-149">Hungarian</span></span>
- <span data-ttu-id="9070c-150">Indonesian</span><span class="sxs-lookup"><span data-stu-id="9070c-150">Indonesian</span></span>
- <span data-ttu-id="9070c-151">Italian</span><span class="sxs-lookup"><span data-stu-id="9070c-151">Italian</span></span>
- <span data-ttu-id="9070c-152">Japanska</span><span class="sxs-lookup"><span data-stu-id="9070c-152">Japanese</span></span>
- <span data-ttu-id="9070c-153">Koreanska</span><span class="sxs-lookup"><span data-stu-id="9070c-153">Korean</span></span>
- <span data-ttu-id="9070c-154">Latvian</span><span class="sxs-lookup"><span data-stu-id="9070c-154">Latvian</span></span>
- <span data-ttu-id="9070c-155">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="9070c-155">Lithuanian</span></span>
- <span data-ttu-id="9070c-156">Norska (bokmål)</span><span class="sxs-lookup"><span data-stu-id="9070c-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="9070c-157">Polish</span><span class="sxs-lookup"><span data-stu-id="9070c-157">Polish</span></span>
- <span data-ttu-id="9070c-158">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="9070c-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="9070c-159">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="9070c-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="9070c-160">Romanian</span><span class="sxs-lookup"><span data-stu-id="9070c-160">Romanian</span></span>
- <span data-ttu-id="9070c-161">Russian</span><span class="sxs-lookup"><span data-stu-id="9070c-161">Russian</span></span> 
- <span data-ttu-id="9070c-162">Serbiska (latinskt alfabet)</span><span class="sxs-lookup"><span data-stu-id="9070c-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="9070c-163">Slovak</span><span class="sxs-lookup"><span data-stu-id="9070c-163">Slovak</span></span>
- <span data-ttu-id="9070c-164">Slovenian</span><span class="sxs-lookup"><span data-stu-id="9070c-164">Slovenian</span></span>
- <span data-ttu-id="9070c-165">Spanska (Spanien, Mexiko)</span><span class="sxs-lookup"><span data-stu-id="9070c-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="9070c-166">Swedish</span><span class="sxs-lookup"><span data-stu-id="9070c-166">Swedish</span></span>
- <span data-ttu-id="9070c-167">Thai</span><span class="sxs-lookup"><span data-stu-id="9070c-167">Thai</span></span>
- <span data-ttu-id="9070c-168">Turkish</span><span class="sxs-lookup"><span data-stu-id="9070c-168">Turkish</span></span>
- <span data-ttu-id="9070c-169">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="9070c-169">Ukrainian</span></span>
- <span data-ttu-id="9070c-170">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="9070c-170">Vietnamese</span></span>

<span data-ttu-id="9070c-171">Microsoft 365 Apparna för företag kan ha stöd för en något annorlunda lista.</span><span class="sxs-lookup"><span data-stu-id="9070c-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="9070c-172">Om dina användare behöver ett annat språk än de som anges här kan du arkivera en [supportbegäran](../working-with-managed-desktop/admin-support.md) med hjälp av [administrationsportalen.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="9070c-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="9070c-173">Språk för support och åtgärder</span><span class="sxs-lookup"><span data-stu-id="9070c-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="9070c-174">Användarsupport</span><span class="sxs-lookup"><span data-stu-id="9070c-174">User support</span></span>
<span data-ttu-id="9070c-175">Microsoft Hanterat skrivbord har endast stöd på engelska.</span><span class="sxs-lookup"><span data-stu-id="9070c-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="9070c-176">Om användarna väljer ett annat språk i Få hjälp-appen får de support från de allmänna Microsoft-supportkanalerna, i stället för direkt från Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="9070c-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="9070c-177">Mer information finns i [Få hjälp för användare.](../working-with-managed-desktop/end-user-support.md)</span><span class="sxs-lookup"><span data-stu-id="9070c-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="9070c-178">Om dina användare behöver stöd på andra språk måste du tillhandahålla det via supportkällor som inte finns från Microsoft eller från din egen organisation.</span><span class="sxs-lookup"><span data-stu-id="9070c-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="9070c-179">Administratörsstöd och -åtgärder</span><span class="sxs-lookup"><span data-stu-id="9070c-179">Admin support and operations</span></span>
<span data-ttu-id="9070c-180">Microsoft Hanterat skrivbord administratörssupport på engelska.</span><span class="sxs-lookup"><span data-stu-id="9070c-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="9070c-181">Det omfattar administrationsportalen och all kommunikation med Microsoft Hanterat skrivbord åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9070c-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="9070c-182">Du bör förutsätta att alla administratörsrelaterade interaktioner och gränssnitt kommer att vara på engelska, om inget annat anges.</span><span class="sxs-lookup"><span data-stu-id="9070c-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


