---
title: Öka hotet mot skyddet för Microsoft 365 Business Premium
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
description: Konfigurera kompatibla funktioner för att förhindra förlust av data och hålla dina kunder känslig information.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841182"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="70fa0-103">Konfigurera funktioner för efterlevnad</span><span class="sxs-lookup"><span data-stu-id="70fa0-103">Set up compliance features</span></span>

<span data-ttu-id="70fa0-104">Ditt Microsoft 365 Business Premium innehåller funktioner för att skydda dina data och enheter och hjälper dig att hålla dina kunder känslig information.</span><span class="sxs-lookup"><span data-stu-id="70fa0-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="70fa0-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="70fa0-105">Set up DLP features</span></span>

<span data-ttu-id="70fa0-106">Se [skapa en DLP-princip från en mall](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) för ett exempel på hur du konfigurerar en princip som skyddar mot att skydda person uppgifter.</span><span class="sxs-lookup"><span data-stu-id="70fa0-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="70fa0-107">DLP innehåller många färdiga principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="70fa0-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="70fa0-108">Till exempel, ekonomiska data för Australien, privat person uppgifter och så vidare.</span><span class="sxs-lookup"><span data-stu-id="70fa0-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="70fa0-109">Se [vad mallarna för DLP-principer innehåller](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="70fa0-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="70fa0-110">Alla de här mallarna kan aktive ras på liknande sätt som i mallen PII.</span><span class="sxs-lookup"><span data-stu-id="70fa0-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="70fa0-111">Konfigurera e-postlagring med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="70fa0-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="70fa0-112">Licenser för **Exchange Online-arkivering** hjälper till att upprätthålla efterlevnad och myndighets standarder genom att bevara e-postinnehåll för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="70fa0-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="70fa0-113">Den minskar också risken för att du har en rättegång och ger ett sätt att återställa data efter en säkerhets överträdelse eller när du behöver återställa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="70fa0-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="70fa0-114">Du kan använda behållning för att bevara all en användares innehåll eller använda bevarande principer för att anpassa vad du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="70fa0-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="70fa0-115">**Rättsliga undantag:** Du kan bevara allt innehåll i post lådan inklusive borttagna objekt genom att ange användarens hela post låda.</span><span class="sxs-lookup"><span data-stu-id="70fa0-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="70fa0-116">Om du vill placera en post låda på en arbets grupp i administrations centret:</span><span class="sxs-lookup"><span data-stu-id="70fa0-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="70fa0-117">I det vänstra navigerings fältet går du till **användare** \> **aktiva användare** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-117">In the left nav, go to **Users** \> **Active users** .</span></span>
    
2. <span data-ttu-id="70fa0-118">Välj en användare vars post låda du vill använda i en beställnings plats.</span><span class="sxs-lookup"><span data-stu-id="70fa0-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="70fa0-119">I fönstret användare expanderar du **Inställningar för e-post** och bredvid **fler inställningar** väljer du **Redigera Exchange-egenskaper** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-119">In the user pane, expand **Mail settings** , and next to **More settings** , choose **Edit Exchange properties** .</span></span>
    
3. <span data-ttu-id="70fa0-120">På sidan med post lådan för användaren väljer du \* \* Mailbox features \* \* i det vänstra navigerings fältet och väljer sedan länken **Aktivera** under **rättsliga undantag** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold** .</span></span>
    
4. <span data-ttu-id="70fa0-121">I dialog rutan **tvist undantag** kan du ange arbets tidens varaktighet i fältet **varaktighet** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="70fa0-122">Lämna fältet tomt om du vill sätta ett oändligt undantag.</span><span class="sxs-lookup"><span data-stu-id="70fa0-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="70fa0-123">Du kan också lägga till anteckningar och direkt skicka post lådans ägare till en webbplats.</span><span class="sxs-lookup"><span data-stu-id="70fa0-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="70fa0-124">\>**Spara** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-124">\> **Save** .</span></span>
    
<span data-ttu-id="70fa0-125">**Bevarande:** Du kan aktivera anpassade bevarande principer, till exempel för att bevara en viss tid eller ta bort innehåll permanent i slutet av lagrings perioden.</span><span class="sxs-lookup"><span data-stu-id="70fa0-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="70fa0-126">Mer information finns i [Översikt över bevarande principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span><span class="sxs-lookup"><span data-stu-id="70fa0-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="70fa0-127">Ange känslighets etiketter</span><span class="sxs-lookup"><span data-stu-id="70fa0-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="70fa0-128">Känslighets etiketter levereras med Azure information Protection (AIP) plan 1, och du kan skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="70fa0-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="70fa0-129">Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare, eller genom att använda en kombination där användarna får rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="70fa0-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="70fa0-130">Om du vill ställa in känslighets etiketter kan du läsa [skapa och hantera video med känslighets etiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="70fa0-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="70fa0-131">Installera Azure information Protection client manuellt</span><span class="sxs-lookup"><span data-stu-id="70fa0-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="70fa0-132">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="70fa0-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="70fa0-133">Ladda ned **AzinfoProtection_UL.exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="70fa0-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="70fa0-134">Du kan kontrol lera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **känslighet** finns på fliken **Start** .</span><span class="sxs-lookup"><span data-stu-id="70fa0-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="70fa0-135">![List rutan skydd i ett Word-dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="70fa0-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="70fa0-136">Mer information finns i [Installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="70fa0-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
