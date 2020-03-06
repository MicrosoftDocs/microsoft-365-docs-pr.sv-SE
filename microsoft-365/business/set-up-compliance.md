---
title: Öka hotskyddet för Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
description: Konfigurera efterlevnadsfunktioner för att förhindra dataförlust och skydda dina och dina kunders känsliga information.
ms.openlocfilehash: 4c8efc4ca96f2db7bc4d1592ad3fdc85dfb6b3b5
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550066"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="fc627-103">Konfigurera efterlevnadsfunktioner</span><span class="sxs-lookup"><span data-stu-id="fc627-103">Set up compliance features</span></span>

<span data-ttu-id="fc627-104">Microsoft 365 Business levereras med funktioner för att skydda dina data och enheter och hjälpa dig att skydda dina och dina kunders känsliga information.</span><span class="sxs-lookup"><span data-stu-id="fc627-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="fc627-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="fc627-105">Set up DLP features</span></span>

<span data-ttu-id="fc627-106">Se [Skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII).</span><span class="sxs-lookup"><span data-stu-id="fc627-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="fc627-107">DLP levereras med många färdiga att använda principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="fc627-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="fc627-108">Till exempel Australia Financial Data, Canada Personal Information Act, Us Financial Data och så vidare.</span><span class="sxs-lookup"><span data-stu-id="fc627-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="fc627-109">Se [Vad DLP-principmallarna innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="fc627-109">See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="fc627-110">Alla dessa mallar kan aktiveras på samma sätt som exempel på PII-mall.</span><span class="sxs-lookup"><span data-stu-id="fc627-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="fc627-111">Konfigurera e-postlagring med Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="fc627-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="fc627-112">**Licensfunktioner för Exchange Online Archiving** hjälper till att upprätthålla efterlevnads- och regelstandarder genom att bevara e-postinnehåll för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="fc627-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="fc627-113">Det bidrar också till att minska risken om det finns en rättegång, och ger ett sätt att återställa data efter en säkerhetsöverträdelse eller när du behöver återställa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="fc627-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="fc627-114">Du kan använda rättstvistspärr för att bevara allt innehåll för en användare eller använda bevarandeprinciper för att anpassa det du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="fc627-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="fc627-115">**Rättstvister håller:** Du kan bevara allt postlådeinnehåll, inklusive borttagna objekt genom att spärra en användares hela postlåda.</span><span class="sxs-lookup"><span data-stu-id="fc627-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="fc627-116">Så här placerar du en postlåda på spärrning i administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="fc627-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="fc627-117">I vänster nav går du till **användare** \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="fc627-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="fc627-118">Välj en användare vars postlåda du vill spärra.</span><span class="sxs-lookup"><span data-stu-id="fc627-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="fc627-119">Expandera **E-postinställningar**och **välj**Redigera Exchange-egenskaper i användarfönstret och välj **Redigera Exchange-egenskaper**i användarfönstret.</span><span class="sxs-lookup"><span data-stu-id="fc627-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="fc627-120">På postlådan satt du \*\* postlådefunktioner \*\* till vänster nav och väljer sedan länken **Aktivera** under **Håll i rättstvister**.</span><span class="sxs-lookup"><span data-stu-id="fc627-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="fc627-121">I dialogrutan **Förrättningsspärr** kan du ange varaktigheten för rättstvisthållning i fältet **Varaktighet för juridiska rättigheter.**</span><span class="sxs-lookup"><span data-stu-id="fc627-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="fc627-122">Lämna fältet tomt om du vill placera en oändlig spärr.</span><span class="sxs-lookup"><span data-stu-id="fc627-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="fc627-123">Du kan också lägga till anteckningar och dirigera postlådeägaren till en webbplats som du kanske måste förklara mer om rättstvisten.</span><span class="sxs-lookup"><span data-stu-id="fc627-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="fc627-124">\>**Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc627-124">\> **Save**.</span></span>
    
<span data-ttu-id="fc627-125">**Kvarhållning:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="fc627-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="fc627-126">Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="fc627-126">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="fc627-127">Ställ in känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="fc627-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="fc627-128">Känslighetsetiketter levereras med Azure Information Protection (AIP) Plan 1 och hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="fc627-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="fc627-129">Etiketter kan tillämpas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användarna får rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="fc627-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="fc627-130">Om du vill ställa in känslighetsetiketter visar du [video med och hanterar känslighetsetiketter.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="fc627-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="fc627-131">Installera Azure Information Protection-klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="fc627-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="fc627-132">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="fc627-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="fc627-133">Ladda ner **AzinfoProtection_UL.exe** från [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="fc627-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="fc627-134">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att **alternativet Känslighet** är tillgängligt på fliken **Start.**</span><span class="sxs-lookup"><span data-stu-id="fc627-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="fc627-135">![Fliken Skyddsflik i ett Word-dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="fc627-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="fc627-136">Mer information finns [i Installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="fc627-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
