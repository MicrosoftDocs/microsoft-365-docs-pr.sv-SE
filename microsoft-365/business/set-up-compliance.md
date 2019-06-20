---
title: Ökat skydd för Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Advanced Threat Protection och skydda känsliga data.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086398"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="89151-103">Ställa in funktioner för regelefterlevnad</span><span class="sxs-lookup"><span data-stu-id="89151-103">Set up compliance features</span></span>

<span data-ttu-id="89151-104">Företaget Microsoft 365 levereras med funktioner för att skydda dina data och enheter och hjälper dig att skydda dig och dina kunder känslig information.</span><span class="sxs-lookup"><span data-stu-id="89151-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="89151-105">Ställa in funktioner för DLP</span><span class="sxs-lookup"><span data-stu-id="89151-105">Set up DLP features</span></span>

<span data-ttu-id="89151-106">Ett exempel på hur du ställer in en princip som skyddar mot personligt identifierbar information (PII) finns i [Skapa en DLP-princip från en mall](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) .</span><span class="sxs-lookup"><span data-stu-id="89151-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="89151-107">DLP levereras med flera färdiga att använda principmallar för många olika språk.</span><span class="sxs-lookup"><span data-stu-id="89151-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="89151-108">Till exempel ekonomiska Data i Australien, Kanada personlig Information Act, amerikanska ekonomiska Data, etc. Se [vad den DLP principmallar innehåller](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) en fullständig lista.</span><span class="sxs-lookup"><span data-stu-id="89151-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="89151-109">Alla dessa mallar kan aktiveras ungefär så PII mall.</span><span class="sxs-lookup"><span data-stu-id="89151-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="89151-110">Ställ in e-lagring med Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="89151-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="89151-111">Funktioner för **Exchange Online-arkivering** licens hjälper upprätthålla överensstämmelse och reglerande normer genom att bevara e innehåll för e-informationsavslöjande.</span><span class="sxs-lookup"><span data-stu-id="89151-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="89151-112">Det hjälper till att minska risken vid en rättegång och ger möjlighet att återskapa data efter ett intrång, eller om du behöver återskapa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="89151-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="89151-113">Du kan använda rättstvist håller för att bevara en användares innehåll eller använda bevarandeprinciper för att anpassa vad du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="89151-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="89151-114">**Rättstvist håller:** Du kan behålla alla innehållet inklusive borttagna objekt genom att infoga hela postlådan för en användare i en rättstvist håller.</span><span class="sxs-lookup"><span data-stu-id="89151-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="89151-115">Om du vill placera håller en postlåda på rättstvist i administratörscenter</span><span class="sxs-lookup"><span data-stu-id="89151-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="89151-116">Gå till **användare** i vänster navigeringsfält \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="89151-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="89151-117">Välj en användare vars postlåda du vill placera på rättstvist håller och expandera **e-postinställningar** i fönstret användare och vid **Fler inställningar** väljer du **Redigera Exchange egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="89151-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="89151-118">Välj på sidan postlåda för användaren \*\* postlåda funktioner \*\* i vänstra navigeringsfältet och välj sedan **Aktivera** länk under **rättstvist håller**.</span><span class="sxs-lookup"><span data-stu-id="89151-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="89151-119">I **rättstvist håller** dialogrutan kan du ange rättstvist håller varaktighet i fältet **rättstvist håller varaktighet** , lämna fältet tomt om du vill placera en oändlig håll.</span><span class="sxs-lookup"><span data-stu-id="89151-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="89151-120">Du kan också lägga till anteckningar och direkt e-rutan ägare till en webbplats som du kan behöva förklara mer om tvisten håller \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="89151-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="89151-121">**Bevarande:** Du kan aktivera anpassade lagringsprinciper, till exempel att bevara under en viss tid eller permanent ta bort innehåll i slutet av loggperioden.</span><span class="sxs-lookup"><span data-stu-id="89151-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="89151-122">Mer information finns i [Översikt över bevarandeprinciper](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="89151-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="89151-123">Ställa in funktioner för informationsskydd i Azure</span><span class="sxs-lookup"><span data-stu-id="89151-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="89151-124">Azure Information skydd (AIP) hjälper dig att klassificera och du kan också skydda dokument och e-post, med hjälp av etiketter.</span><span class="sxs-lookup"><span data-stu-id="89151-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="89151-125">Etiketter kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare eller genom en kombination där användare ges rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="89151-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="89151-126">I Outlook på webben kan du använda följande inbyggda etiketter och begränsningar till din e-post:</span><span class="sxs-lookup"><span data-stu-id="89151-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="89151-127">**Vidarebefordra inte**: mottagarna kan läsa meddelandet, men de kan inte vidarebefordra, skriva ut eller kopiera innehåll</span><span class="sxs-lookup"><span data-stu-id="89151-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="89151-128">**Kryptera**: hela meddelandet är krypterat.</span><span class="sxs-lookup"><span data-stu-id="89151-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="89151-129">Mottagarna måste bekräfta sin identitet innan åtkomst till krypterade innehållet och kan inte ta bort kryptering.</span><span class="sxs-lookup"><span data-stu-id="89151-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="89151-130">**Konfidentiellt**: ger anställda i organisationen fullständig behörighet till e-innehåll och bifogade filer, men inte till personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="89151-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="89151-131">Data kan spåra och återkalla innehåll när som helst.</span><span class="sxs-lookup"><span data-stu-id="89151-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="89151-132">**Mycket konfidentiella**: den här begränsningen kan användas till mycket konfidentiella data, vilket gör att anställda kan visa, redigera och svara, men inte vidarebefordra, skriva ut eller kopiera data.</span><span class="sxs-lookup"><span data-stu-id="89151-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="89151-133">Data kan spåra och återkalla innehåll när som helst.</span><span class="sxs-lookup"><span data-stu-id="89151-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="89151-134">Kontrollera att Azure informationsskydd är aktiverat</span><span class="sxs-lookup"><span data-stu-id="89151-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="89151-135">Kontrollera att AIP är aktiverad:</span><span class="sxs-lookup"><span data-stu-id="89151-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="89151-136">Logga in på [Azure portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="89151-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="89151-137">Markera **alla tjänster** och Skriv i *Azure informationsskydd* i **Sökrutan**.</span><span class="sxs-lookup"><span data-stu-id="89151-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="89151-138">När resultatet visas klickar du på start nästa på **Azure informationsskydd** så att det blir en favorit och lätta att hitta senare.</span><span class="sxs-lookup"><span data-stu-id="89151-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="89151-139">Välj **Azure informationsskydd** \> **skydd aktivering** och gör att den har statusen till aktiverad.</span><span class="sxs-lookup"><span data-stu-id="89151-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="89151-140">Visa Azure informationsskydd princip- och etiketter</span><span class="sxs-lookup"><span data-stu-id="89151-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="89151-141">Om du vill visa och ändra befintliga etiketter:</span><span class="sxs-lookup"><span data-stu-id="89151-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="89151-142">Välj **klassificeringar** på instrumentpanelen Azure informationsskydd \> **etiketter**.</span><span class="sxs-lookup"><span data-stu-id="89151-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="89151-143">![Standardetiketter för informationsskydd i Azure.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="89151-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="89151-144">Du kan välja alla etiketter för att visa alternativ kan du ändra visningsnamnet, färger osv.</span><span class="sxs-lookup"><span data-stu-id="89151-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="89151-145">Se [ändra och skapa nya etiketter](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) om du vill skapa en egen.</span><span class="sxs-lookup"><span data-stu-id="89151-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="89151-146">Installera Azure informationsskydd klienten manuellt</span><span class="sxs-lookup"><span data-stu-id="89151-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="89151-147">Att manuellt installera klienten för AIP:</span><span class="sxs-lookup"><span data-stu-id="89151-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="89151-148">Hämta **AzInfoProtection.exe** från [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="89151-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="89151-149">Du kan kontrollera att installationen fungerade genom att visa ett Word-dokument och se till att alternativet **skydda** är tillgängliga på fliken **Start** .</span><span class="sxs-lookup"><span data-stu-id="89151-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="89151-150">![Fliken skydd listrutan i ett Word-dokument.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="89151-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="89151-151">Mer information finns i [installera klienten](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="89151-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
