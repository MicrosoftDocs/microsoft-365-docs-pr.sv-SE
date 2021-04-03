---
title: Öka skydd mot hot för Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579963"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="112d0-103">Konfigurera funktioner för efterlevnad</span><span class="sxs-lookup"><span data-stu-id="112d0-103">Set up compliance features</span></span>

<span data-ttu-id="112d0-104">Din Microsoft 365 Business Premium levereras med funktioner som skyddar dina data och enheter och hjälper dig att hålla din och dina kunders känsliga information säker.</span><span class="sxs-lookup"><span data-stu-id="112d0-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="112d0-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="112d0-105">Set up DLP features</span></span>

<span data-ttu-id="112d0-106">Se [Skapa en DLP-princip från](../compliance/create-a-dlp-policy-from-a-template.md) en mall för ett exempel på hur du skapar en princip för att skydda mot skydd mot förlust av personuppgifter.</span><span class="sxs-lookup"><span data-stu-id="112d0-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="112d0-107">DLP innehåller många färdiga principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="112d0-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="112d0-108">Till exempel Australia Financial Data, Canada Personal Information Act, U.S. Financial Data och så vidare.</span><span class="sxs-lookup"><span data-stu-id="112d0-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="112d0-109">Se [Vad DLP-principmallarna innehåller](../compliance/what-the-dlp-policy-templates-include.md) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="112d0-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="112d0-110">Alla mallar kan aktiveras ungefär som i exemplet med pii-mallar.</span><span class="sxs-lookup"><span data-stu-id="112d0-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="112d0-111">Konfigurera e-postbevarande med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="112d0-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="112d0-112">**Exchange Online-licensfunktioner hjälper till** att bevara efterlevnads- och regelstandarder genom att bevara e-postinnehållet för e-dataidentifiering.</span><span class="sxs-lookup"><span data-stu-id="112d0-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="112d0-113">Det hjälper också till att minska risken om det finns en sekretess, och det är ett sätt att återställa data efter en säkerhetsöverträdelse eller när du behöver återställa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="112d0-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="112d0-114">Du kan använda bevarande av juridiska skäl för att bevara allt innehåll för en användare, eller använda bevarandeprinciper för att anpassa vad du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="112d0-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="112d0-115">**Bevarande av juridiska skäl:** Du kan bevara allt innehåll i postlådan, inklusive borttagna objekt, genom att sätta en användares hela postlåda i bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="112d0-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="112d0-116">Så här placerar du en postlåda i bevarande av juridiska skäl i administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="112d0-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="112d0-117">I det vänstra navigeringsfältet går du till **Användare** \> **aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="112d0-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="112d0-118">Välj en användare vars postlåda du vill skapa bevarande av juridiska skäl för.</span><span class="sxs-lookup"><span data-stu-id="112d0-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="112d0-119">I användarfönstret expanderar du **E-postinställningar** och bredvid **Fler inställningar** väljer du **Redigera Exchange-egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="112d0-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="112d0-120">På användarens postlådesida väljer du \*\* postlådefunktioner \*\*  i det vänstra navigeringsfältet och väljer sedan länken Aktivera under Bevarande av juridiska **skäl.**</span><span class="sxs-lookup"><span data-stu-id="112d0-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="112d0-121">I dialogrutan **Bevarande av juridiska** skäl kan du ange varaktigheten för bevarande av juridiska skäl i fältet Bevarande av juridiska **skäl.**</span><span class="sxs-lookup"><span data-stu-id="112d0-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="112d0-122">Lämna fältet tomt om du vill ha ett oändligt utrymme.</span><span class="sxs-lookup"><span data-stu-id="112d0-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="112d0-123">Du kan också lägga till anteckningar och dirigera postlådans ägare till en webbplats som du kan behöva förklara mer om bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="112d0-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="112d0-124">\>**Spara**.</span><span class="sxs-lookup"><span data-stu-id="112d0-124">\> **Save**.</span></span>
    
<span data-ttu-id="112d0-125">**Bevarande:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="112d0-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="112d0-126">Mer information finns i Översikt [över bevarandeprinciper.](../compliance/retention.md)</span><span class="sxs-lookup"><span data-stu-id="112d0-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="112d0-127">Konfigurera känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="112d0-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="112d0-128">Känslighetsetiketter följer med Azure Information Protection (AIP) abonnemang 1 och hjälper dig att klassificera, och om du vill, skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="112d0-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="112d0-129">Etiketter kan tillämpas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom en kombination där användarna får rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="112d0-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="112d0-130">Om du vill konfigurera känslighetsetiketter, visa [och hantera känslighetsetiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="112d0-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="112d0-131">Installera Azure Information Protection-klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="112d0-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="112d0-132">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="112d0-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="112d0-133">Ladda **AzinfoProtection_UL.exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="112d0-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="112d0-134">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och kontrollera att **alternativet Känslighet** är tillgängligt på **fliken** Start.</span><span class="sxs-lookup"><span data-stu-id="112d0-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="112d0-135">![Nedrullningsrutan för fliken Skydd i ett Word-dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="112d0-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="112d0-136">Mer information finns i [Installera klienten.](/azure/information-protection/infoprotect-tutorial-step3)</span><span class="sxs-lookup"><span data-stu-id="112d0-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>