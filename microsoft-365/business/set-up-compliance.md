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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Avancerat skydd mot hot och skydda känsliga data.
ms.openlocfilehash: 8144bcebe8a0cdf28a5e092f592362922ccbdd48
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288754"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="42335-103">Ställa in efterlevnadsfunktioner</span><span class="sxs-lookup"><span data-stu-id="42335-103">Set up compliance features</span></span>

<span data-ttu-id="42335-104">Din Microsoft 365-verksamhet levereras med funktioner som skyddar dina data och enheter och hjälper dig att skydda dina och kundernas känsliga information.</span><span class="sxs-lookup"><span data-stu-id="42335-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="42335-105">Konfigurera DLP-funktioner</span><span class="sxs-lookup"><span data-stu-id="42335-105">Set up DLP features</span></span>

<span data-ttu-id="42335-106">Se [skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) för ett exempel på hur du ställer in en princip för att skydda mot personligt identifierbar information (PII).</span><span class="sxs-lookup"><span data-stu-id="42335-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="42335-107">DLP levereras med många färdiga att använda principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="42335-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="42335-108">Till exempel Australien Financial data, Kanada personuppgifter Act, amerikanska finansiella data, etc. Se [vad DLP-principmallarna innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) för en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="42335-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="42335-109">Alla dessa mallar kan aktiveras liknande den PII mall exempel.</span><span class="sxs-lookup"><span data-stu-id="42335-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="42335-110">Konfigurera e-postlagring med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="42335-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="42335-111">**Exchange Online arkivering** licens funktioner bidra till att upprätthålla efterlevnad och reglerande standarder genom att bevara e-innehåll för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="42335-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="42335-112">Det bidrar också till att minska risken i händelse av en rättegång och ger ett sätt att återskapa data efter en säkerhetsöverträdelse, eller när du behöver återskapa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="42335-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="42335-113">Du kan använda bevarande av juridiska tvister för att bevara allt innehåll i en användare eller använda loggperiodsprinciper för att anpassa vad du vill bevara.</span><span class="sxs-lookup"><span data-stu-id="42335-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="42335-114">**Rättstvist håller:** Du kan bevara allt postlådeinnehåll inklusive borttagna objekt genom att placera en användares hela postlåda i rättstvist håller.</span><span class="sxs-lookup"><span data-stu-id="42335-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="42335-115">Om du vill placera en postlåda i rättstvist håller du i administratörscenter:</span><span class="sxs-lookup"><span data-stu-id="42335-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="42335-116">Gå till **användare** \> **aktiva användare**i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="42335-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="42335-117">Välj en användare vars postlåda du vill placera på rättstvist håller och i fönstret användare expandera **e-postinställningar** och bredvid **fler inställningar** väljer **Redigera Exchange-egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="42335-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="42335-118">På sidan postlådesida för användaren väljer du \* \* Postlådefunktioner \* \* i det vänstra navigeringsfältet och väljer sedan **Aktivera** länk under **rättstvist håller**.</span><span class="sxs-lookup"><span data-stu-id="42335-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="42335-119">I dialogrutan **rättstvist håller** du kan ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig spärr.</span><span class="sxs-lookup"><span data-stu-id="42335-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="42335-120">Du kan också lägga till anteckningar och dirigera brev låde ägaren till en webbplats som du kanske måste förklara mer om bevarande av \> rätts **tvister.**</span><span class="sxs-lookup"><span data-stu-id="42335-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="42335-121">**Retention:** Du kan aktivera anpassade bevarandeprinciper, till exempel för att bevara under en viss tid eller ta bort innehåll permanent i slutet av kvarhållningsperioden.</span><span class="sxs-lookup"><span data-stu-id="42335-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="42335-122">Mer information finns [i Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="42335-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="42335-123">Konfigurera Azure information Protection-funktioner</span><span class="sxs-lookup"><span data-stu-id="42335-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="42335-124">Azure information Protection (AIP) hjälper dig att klassificera och eventuellt skydda dina dokument och e-postmeddelanden genom att använda etiketter.</span><span class="sxs-lookup"><span data-stu-id="42335-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="42335-125">Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom att använda en kombination där användare ges rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="42335-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="42335-126">I Outlook på webben kan du använda följande inbyggda etiketter och begränsningar i din e-post:</span><span class="sxs-lookup"><span data-stu-id="42335-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="42335-127">**Vidarebefordra inte**: mottagarna kan läsa meddelandet, men de kan inte vidarebefordra, skriva ut eller kopiera innehåll</span><span class="sxs-lookup"><span data-stu-id="42335-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="42335-128">**Kryptera**: hela meddelandet krypteras.</span><span class="sxs-lookup"><span data-stu-id="42335-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="42335-129">Mottagarna måste bekräfta sin identitet innan de får åtkomst till krypterat innehåll och kan inte ta bort kryptering.</span><span class="sxs-lookup"><span data-stu-id="42335-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="42335-130">**Konfidentiellt**: ger medarbetarna i organisationen fullständig behörighet till e-postinnehåll och bifogade filer, men inte till personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="42335-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="42335-131">Data ägare kan spåra och återkalla innehåll när som helst.</span><span class="sxs-lookup"><span data-stu-id="42335-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="42335-132">**Mycket konfidentiell**: den här begränsningen kan tillämpas på mycket konfidentiella data, vilket gör det möjligt för anställda att visa, redigera och svara, men inte vidarebefordra, skriva ut eller kopiera data.</span><span class="sxs-lookup"><span data-stu-id="42335-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="42335-133">Data ägare kan spåra och återkalla innehåll när som helst.</span><span class="sxs-lookup"><span data-stu-id="42335-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="42335-134">Kontrollera att Azure information Protection är aktiverad</span><span class="sxs-lookup"><span data-stu-id="42335-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="42335-135">Så här kontrollerar du att AIP är aktiverat:</span><span class="sxs-lookup"><span data-stu-id="42335-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="42335-136">Logga in på [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="42335-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="42335-137">Välj **alla tjänster** och skriv in *Azure information Protection* i **sökrutan**.</span><span class="sxs-lookup"><span data-stu-id="42335-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="42335-138">När resultatet visas klickar du på Start bredvid **Azure information Protection** för att göra det till en favorit och lätt att hitta senare.</span><span class="sxs-lookup"><span data-stu-id="42335-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="42335-139">Välj **Azure information Protection** \> **Protection-aktivering** och kontrollera att status är inställt på aktiverad.</span><span class="sxs-lookup"><span data-stu-id="42335-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="42335-140">Visa Azure information Protection-principen och standardetiketter</span><span class="sxs-lookup"><span data-stu-id="42335-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="42335-141">Så här visar och ändrar du de befintliga etiketterna:</span><span class="sxs-lookup"><span data-stu-id="42335-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="42335-142">På den Azure information Protection-instrumentpanelen, Välj **klassificeringar** \> **Etiketter**.</span><span class="sxs-lookup"><span data-stu-id="42335-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="42335-143">![Standard etiketter för Azure information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="42335-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="42335-144">Du kan välja vilken etikett som helst för att visa alternativ, du kan ändra visningsnamn, färger, etc.</span><span class="sxs-lookup"><span data-stu-id="42335-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="42335-145">Se [ändra och skapa nya etiketter](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) om du vill skapa egna.</span><span class="sxs-lookup"><span data-stu-id="42335-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="42335-146">Installera Azure information Protection-klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="42335-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="42335-147">Så här installerar du AIP-klienten manuellt:</span><span class="sxs-lookup"><span data-stu-id="42335-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="42335-148">Hämta **Azinfoprotection. exe** från [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="42335-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="42335-149">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **skydda** är tillgängligt på fliken **Start** .</span><span class="sxs-lookup"><span data-stu-id="42335-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="42335-150">![Fliken skydd i ett Word-dokument.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="42335-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="42335-151">Mer information finns [i installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="42335-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
