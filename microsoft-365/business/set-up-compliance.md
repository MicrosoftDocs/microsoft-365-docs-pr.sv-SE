---
title: Öka skyddet mot hot för Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Ställ in efterlevnadsfunktioner för att förhindra dataförlust och etikettkänsliga data.
ms.openlocfilehash: 5213c55f4a8ce0e223896f1b960847714d6d06cb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031424"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="a6359-103">Ställa in efterlevnadsfunktioner</span><span class="sxs-lookup"><span data-stu-id="a6359-103">Set up compliance features</span></span>

<span data-ttu-id="a6359-104">Din Microsoft 365-verksamhet levereras med funktioner som skyddar dina data och enheter och hjälper dig att skydda dina och kundernas känsliga information.</span><span class="sxs-lookup"><span data-stu-id="a6359-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="a6359-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="a6359-105">Set up DLP features</span></span>

<span data-ttu-id="a6359-106">Se [skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII).</span><span class="sxs-lookup"><span data-stu-id="a6359-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="a6359-107">DLP levereras med många färdiga att använda principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="a6359-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="a6359-108">Till exempel Australien Financial data, Kanada personuppgifter Act, amerikanska finansiella data, etc. Se [vad DLP-principmallarna innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="a6359-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="a6359-109">Alla dessa mallar kan aktiveras liknande den PII mall exempel.</span><span class="sxs-lookup"><span data-stu-id="a6359-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="a6359-110">Konfigurera e-postlagring med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="a6359-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="a6359-111">**Exchange Online arkivering** licens funktioner bidra till att upprätthålla efterlevnad och reglerande standarder genom att bevara e-innehåll för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a6359-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="a6359-112">Det bidrar också till att minska risken i händelse av en rättegång och ger ett sätt att återskapa data efter en säkerhetsöverträdelse, eller när du behöver återskapa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="a6359-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="a6359-113">Du kan använda bevarande av juridiska tvister för att bevara allt innehåll i en användare eller använda loggperiodsprinciper för att anpassa vad du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="a6359-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="a6359-114">**Rättstvist håller:** Du kan bevara allt postlådeinnehåll inklusive borttagna objekt genom att placera en användares hela postlåda i rättstvist håller.</span><span class="sxs-lookup"><span data-stu-id="a6359-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="a6359-115">Om du vill placera en postlåda i rättstvist håller du i administratörscenter:</span><span class="sxs-lookup"><span data-stu-id="a6359-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="a6359-116">Gå till **användare** \> **aktiva användare**i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="a6359-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="a6359-117">Välj en användare vars postlåda du vill placera på rättstvist håller och i fönstret användare expandera **e-postinställningar** och bredvid **fler inställningar** väljer **Redigera Exchange-egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="a6359-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="a6359-118">På sidan postlådesida för användaren väljer du \* \* Postlådefunktioner \* \* i det vänstra navigeringsfältet och väljer sedan **Aktivera** länk under **rättstvist håller**.</span><span class="sxs-lookup"><span data-stu-id="a6359-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="a6359-119">I dialogrutan **rättstvist håller** du kan ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig spärr.</span><span class="sxs-lookup"><span data-stu-id="a6359-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="a6359-120">Du kan också lägga till anteckningar och dirigera brev låde ägaren till en webbplats som du kanske måste förklara mer om bevarande av \> rätts **tvister.**</span><span class="sxs-lookup"><span data-stu-id="a6359-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="a6359-121">**Retention:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="a6359-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="a6359-122">Mer information finns [i Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="a6359-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="a6359-123">Ställ in känslighets etiketter</span><span class="sxs-lookup"><span data-stu-id="a6359-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="a6359-124">Känslighets etiketter levereras med Azure information Protection (AIP) plan 1 och hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="a6359-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="a6359-125">Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användare ges rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="a6359-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="a6359-126">Om du vill ställa in känslighets etiketter, Visa [skapa och hantera känslighets etiketter](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="a6359-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="a6359-127">Installera Azure information Protection-klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="a6359-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="a6359-128">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="a6359-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="a6359-129">Hämta **AzinfoProtection_UL. exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a6359-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="a6359-130">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **känslighet** är tillgängligt på fliken **Start** .</span><span class="sxs-lookup"><span data-stu-id="a6359-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="a6359-131">![Fliken skydd i ett Word-dokument.](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="a6359-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="a6359-132">Mer information finns [i installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="a6359-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
