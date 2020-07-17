---
title: Öka hotskyddet för Microsoft 365 Business Premium
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Konfigurera efterlevnadsfunktioner för att förhindra dataförlust och skydda din och dina kunders känsliga information.
ms.openlocfilehash: 18886ff3a0ba5e99e63c70ef083d7a69c75bac91
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785841"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a7d17-103">Konfigurera funktioner för efterlevnad</span><span class="sxs-lookup"><span data-stu-id="a7d17-103">Set up compliance features</span></span>

<span data-ttu-id="a7d17-104">Din Microsoft 365 Business Premium levereras med funktioner för att skydda dina data och enheter och hjälper dig att skydda din och dina kunders känsliga information.</span><span class="sxs-lookup"><span data-stu-id="a7d17-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a7d17-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="a7d17-105">Set up DLP features</span></span>

<span data-ttu-id="a7d17-106">Se [Skapa en DLP-princip från en mall](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII).</span><span class="sxs-lookup"><span data-stu-id="a7d17-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a7d17-107">DLP levereras med många färdiga principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="a7d17-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a7d17-108">Till exempel, Australien Financial Data, Canada Personal Information Act, AMERIKANSKA finansiella data, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="a7d17-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="a7d17-109">Se [Vad DLP-principmallarna innehåller](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="a7d17-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="a7d17-110">Alla dessa mallar kan aktiveras på samma sätt som pii-mallexemplet.</span><span class="sxs-lookup"><span data-stu-id="a7d17-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a7d17-111">Konfigurera lagring av e-post med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="a7d17-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a7d17-112">**Exchange Online Archiving** licensfunktioner bidra till att upprätthålla efterlevnad och reglerande standarder genom att bevara e-postinnehåll för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a7d17-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a7d17-113">Det bidrar också till att minska risken om det finns en rättegång, och ger ett sätt att återställa data efter en säkerhetsöverträdelse eller när du behöver återställa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="a7d17-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="a7d17-114">Du kan använda bevarande av rättstvister för att bevara allt innehåll för en användare eller använda bevarandeprinciper för att anpassa det du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="a7d17-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a7d17-115">**Rättstvister håller:** Du kan bevara allt postlådeinnehåll, inklusive borttagna objekt genom att spärra en användares hela postlåda.</span><span class="sxs-lookup"><span data-stu-id="a7d17-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a7d17-116">Så här placerar du en postlåda i bevarandet av rättstvister i administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="a7d17-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a7d17-117">Gå till Aktiva användare i den vänstra **navigeringsfältet** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="a7d17-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a7d17-118">Välj en användare vars postlåda du vill placera i bevarandet av rättstvister.</span><span class="sxs-lookup"><span data-stu-id="a7d17-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="a7d17-119">I användarfönstret expanderar du **E-postinställningar och**bredvid **Fler inställningar**väljer du **Redigera Exchange-egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="a7d17-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a7d17-120">På postlådesidan för användaren väljer du \*\* postlådefunktioner \*\* på den vänstra navigeringsfältet och väljer sedan länken **Aktivera** under **Bevarande av juridiska skäl**.</span><span class="sxs-lookup"><span data-stu-id="a7d17-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a7d17-121">I dialogrutan **bevarande av rättstvister** kan du ange varaktigheten för bevarande av rättstvister i fältet **Bevarande av juridiska skäl.**</span><span class="sxs-lookup"><span data-stu-id="a7d17-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="a7d17-122">Lämna fältet tomt om du vill placera ett oändligt grepp.</span><span class="sxs-lookup"><span data-stu-id="a7d17-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a7d17-123">Du kan också lägga till anteckningar och dirigera postlådans ägare till en webbplats som du kanske måste förklara mer om bevarandet av rättstvister.</span><span class="sxs-lookup"><span data-stu-id="a7d17-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="a7d17-124">\>**Spara**.</span><span class="sxs-lookup"><span data-stu-id="a7d17-124">\> **Save**.</span></span>
    
<span data-ttu-id="a7d17-125">**Lagring:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="a7d17-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a7d17-126">Mer information finns i [Översikt över bevarandeprinciper](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span><span class="sxs-lookup"><span data-stu-id="a7d17-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="a7d17-127">Ställ in känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="a7d17-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="a7d17-128">Känslighetsetiketter levereras med Azure Information Protection (AIP) Plan 1 och hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="a7d17-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a7d17-129">Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användarna får rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="a7d17-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a7d17-130">Om du vill ställa in Känslighetsetiketter visar du [skapa och hantera känslighetsetiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="a7d17-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a7d17-131">Installera Azure Information Protection-klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="a7d17-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a7d17-132">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="a7d17-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a7d17-133">Ladda ner **AzinfoProtection_UL.exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a7d17-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a7d17-134">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **Känslighet** är tillgängligt på fliken **Start.**</span><span class="sxs-lookup"><span data-stu-id="a7d17-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="a7d17-135">![Listruta på fliken Skydd i ett Word-dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="a7d17-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="a7d17-136">Mer information finns i [Installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="a7d17-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
