---
title: Öka kvoten för återställningsbara objekt för postlådor i undantag
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: Aktivera arkivpostlådan och aktivera automatiskt expanderande arkivering för att öka storleken på mappen Återställningsbara objekt för en postlåda i Microsoft 365.
ms.openlocfilehash: 47227e066f922a9e4b8bccedaa9573c001194836
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226593"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="849a6-103">Öka kvoten för återställningsbara objekt för postlådor i undantag</span><span class="sxs-lookup"><span data-stu-id="849a6-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="849a6-104">Standardprincipen Exchange med namnet Standardprincip för *MRM*– som automatiskt tillämpas på nya postlådor i Exchange Online innehåller en bevarandetagg med namnet Återställningsbara objekt 14 dagar flytta till arkivering.</span><span class="sxs-lookup"><span data-stu-id="849a6-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="849a6-105">Med den här bevarandetaggen flyttas objekt från mappen Återställningsbara objekt i användarens primära postlåda till mappen Återställningsbara objekt i användarens arkivpostlåda efter att de 14 dagar det gått ut.</span><span class="sxs-lookup"><span data-stu-id="849a6-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="849a6-106">För att det här ska hända måste användarens arkivpostlåda vara aktiverad.</span><span class="sxs-lookup"><span data-stu-id="849a6-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="849a6-107">Om arkivpostlådan inte är aktiverad vidtas ingen åtgärd, vilket innebär att objekt i mappen Återställningsbara objekt för en postlåda som är undantaget inte flyttas till arkivpostlådan efter att de 14 dagar det gått ut.</span><span class="sxs-lookup"><span data-stu-id="849a6-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="849a6-108">Eftersom ingenting tas bort från en postlåda som är förvaring kan det vara så att lagringskvoten för mappen Återställningsbara objekt kan överskridas, särskilt om användarens arkivpostlåda inte är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="849a6-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span>

<span data-ttu-id="849a6-109">För att minska risken att överskrida gränsen ökar lagringskvoten för mappen Återställningsbara objekt automatiskt från 30 GB till 100 GB när ett förvaringsutrymme sätts på en postlåda i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="849a6-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="849a6-110">Om arkivpostlådan är aktiverad ökar även lagringskvoten för mappen Återställningsbara objekt i arkivpostlådan från 30 GB till 100 GB.</span><span class="sxs-lookup"><span data-stu-id="849a6-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="849a6-111">Om den automatiskt expanderande arkiveringsfunktionen i Exchange Online är aktiverad är lagringskvoten för mappen Återställningsbara objekt i användarens arkiv obegränsad.</span><span class="sxs-lookup"><span data-stu-id="849a6-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>

 <span data-ttu-id="849a6-112">I följande tabell sammanfattas lagringskvoten för mappen återställningsbara objekt.</span><span class="sxs-lookup"><span data-stu-id="849a6-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span>

|<span data-ttu-id="849a6-113">**Plats för mappen återställningsbara objekt**</span><span class="sxs-lookup"><span data-stu-id="849a6-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="849a6-114">**Postlådor som inte är på plats**</span><span class="sxs-lookup"><span data-stu-id="849a6-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="849a6-115">**Postlådor på plats**</span><span class="sxs-lookup"><span data-stu-id="849a6-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="849a6-116">Primär postlåda</span><span class="sxs-lookup"><span data-stu-id="849a6-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="849a6-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="849a6-117">30 GB</span></span>  <br/> |<span data-ttu-id="849a6-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="849a6-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="849a6-119">Arkivpostlåda<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="849a6-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="849a6-120">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="849a6-120">Unlimited</span></span>  <br/> |<span data-ttu-id="849a6-121">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="849a6-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="849a6-122">**Total lagringskvot för mappen Återställningsbara objekt**</span><span class="sxs-lookup"><span data-stu-id="849a6-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="849a6-123">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="849a6-123">Unlimited</span></span>  <br/> |<span data-ttu-id="849a6-124">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="849a6-124">Unlimited</span></span>  <br/> |

> [!NOTE]
> <span data-ttu-id="849a6-125"><sup>\*</sup>Den ursprungliga lagringskvoten för arkivpostlådan är 100 GB för användare med en Exchange Online (alternativ 2) licens.</span><span class="sxs-lookup"><span data-stu-id="849a6-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="849a6-126">När automatisk utökad arkivering är aktiverat för arkivering av postlådor ökar lagringskvoten för både arkivpostlådan och mappen Återställningsbara objekt till 110 GB.</span><span class="sxs-lookup"><span data-stu-id="849a6-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="849a6-127">Ytterligare lagringsutrymme för arkivering kommer att tillhandahållas vid behov, vilket resulterar i en obegränsad mängd arkivlagring.</span><span class="sxs-lookup"><span data-stu-id="849a6-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="849a6-128">Mer information om automatiskt expanderande arkivering finns i [Översikt över obegränsat arkivering i Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="849a6-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

<span data-ttu-id="849a6-129">När lagringskvoten för mappen Återställningsbara objekt i den primära postlådan för en postlåda som är i förvaring ligger nära gränsen kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="849a6-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>

- <span data-ttu-id="849a6-130">**Aktivera arkivpostlådan och aktivera automatisk expandering av arkivering.**</span><span class="sxs-lookup"><span data-stu-id="849a6-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="849a6-131">Du kan aktivera en obegränsad lagringskapacitet för mappen återställningsbara objekt genom att helt enkelt aktivera arkivpostlådan och sedan aktivera den automatiskt expanderande arkiveringsfunktionen i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="849a6-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="849a6-132">Det ger 110 GB för mappen Återställningsbara objekt i den primära postlådan och en obegränsad lagringskapacitet för mappen Återställningsbara objekt i användarens arkiv.</span><span class="sxs-lookup"><span data-stu-id="849a6-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="849a6-133">Så här gör [du: Aktivera arkivpostlådor](enable-archive-mailboxes.md) i Säkerhets- & och Aktivera obegränsad [arkivering i Office 365.](enable-unlimited-archiving.md)</span><span class="sxs-lookup"><span data-stu-id="849a6-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="849a6-134">När du har aktiverat arkivet för en postlåda som ligger nära att överskrida lagringskvoten för mappen Återställningsbara objekt kan du köra assistenten för hanterade mappar så att assistenten manuellt bearbetar postlådan så att förfallna objekt flyttas till mappen Återställningsbara objekt i arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="849a6-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="849a6-135">Anvisningar [finns i Steg 4.](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)</span><span class="sxs-lookup"><span data-stu-id="849a6-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="849a6-136">Observera att andra objekt i användarens postlåda kan flyttas till den nya arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="849a6-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="849a6-137">Överväg att berätta för användaren att detta kan hända när du har aktiverar arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="849a6-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span>

- <span data-ttu-id="849a6-138">**Skapa en egen Exchange bevarandeprincip för postlådor som är bevarande.**</span><span class="sxs-lookup"><span data-stu-id="849a6-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="849a6-139">Förutom att aktivera arkivpostlådan och automatiskt expanderande arkivering för postlådor med bevarande av juridiska skäl eller In-Place bevarande kan du också skapa en egen bevarandeprincip för Exchange för postlådor som är bevarande.</span><span class="sxs-lookup"><span data-stu-id="849a6-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="849a6-140">På så sätt kan du tillämpa en bevarandeprincip på andra postlådor än standardprincipen för MRM som används för postlådor som inte är på plats, och du kan använda bevarandetaggar som är avsedda för postlådor som är bevarande.</span><span class="sxs-lookup"><span data-stu-id="849a6-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="849a6-141">Det handlar bland annat om att skapa en ny bevarandetagg för mappen för återställningsbara objekt.</span><span class="sxs-lookup"><span data-stu-id="849a6-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span>

<span data-ttu-id="849a6-142">Resten av det här avsnittet beskriver de stegvisa procedurerna för att skapa en anpassad Exchange för bevarandeprincip för postlådor.</span><span class="sxs-lookup"><span data-stu-id="849a6-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>

[<span data-ttu-id="849a6-143">Steg 1: Skapa en anpassad bevarandetagg för mappen Återställningsbara objekt</span><span class="sxs-lookup"><span data-stu-id="849a6-143">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[<span data-ttu-id="849a6-144">Steg 2: Skapa en Exchange bevarandeprincip för postlådor</span><span class="sxs-lookup"><span data-stu-id="849a6-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="849a6-145">Steg 3: Tillämpa den Exchange bevarandeprincipen på postlådor som är bevarande</span><span class="sxs-lookup"><span data-stu-id="849a6-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="849a6-146">(Valfritt) Steg 4: Kör assistenten för hanterade mappar för att tillämpa de nya bevarandeinställningarna</span><span class="sxs-lookup"><span data-stu-id="849a6-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="849a6-147">Steg 1: Skapa en anpassad bevarandetagg för mappen Återställningsbara objekt</span><span class="sxs-lookup"><span data-stu-id="849a6-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="849a6-148">Det första steget är att skapa en anpassad bevarandetagg (kallas bevarandeprinciptagg eller bevarandeprinciptagg) för mappen återställningsbara objekt.</span><span class="sxs-lookup"><span data-stu-id="849a6-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="849a6-149">Som tidigare förklarats flyttar den här artikeln objekt från mappen Återställningsbara objekt i användarens primära postlåda till mappen Återställningsbara objekt i användarens arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="849a6-150">Du måste använda PowerShell för att skapa en återställningsbar objekt-mapp för mappen Återställningsbara objekt.</span><span class="sxs-lookup"><span data-stu-id="849a6-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="849a6-151">Du kan inte använda Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="849a6-151">You can't use the Exchange admin center (EAC).</span></span>

1. [<span data-ttu-id="849a6-152">Ansluta till Exchange Online med fjärr-PowerShell</span><span class="sxs-lookup"><span data-stu-id="849a6-152">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="849a6-153">Kör följande kommando för att skapa en ny återställningsbar objekt-mapp:</span><span class="sxs-lookup"><span data-stu-id="849a6-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span>

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="849a6-154">Följande kommando skapar till exempel en bevarandeprincipprincip för återställningsbara objekt-mappen med namnet Återställningsbara objekt 30 dagar för postlådor som är bevarande, med en kvarhållningstid på 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="849a6-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="849a6-155">Det innebär att när ett objekt har legat i mappen återställningsbara objekt i 30 dagar flyttas det till mappen Återställningsbara objekt i användarens arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="849a6-156">Vi rekommenderar att kvarhållningstiden (som definieras av parametern  _AgeLimitForRetention)_ för bevarandeprincipobjektet för återställningsbara objekt är densamma som kvarhållningsperioden för borttagna objekt för postlådorna som bevarandeprincipprincipen ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="849a6-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="849a6-157">På så sätt kan användaren återställa borttagna objekt under hela bevarandeperioden innan de flyttas till arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="849a6-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="849a6-158">I exemplet ovan har kvarhållningstiden angetts till 30 dagar utifrån antagandet att bevarandeperioden för borttagna objekt för postlådor också är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="849a6-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="849a6-159">En Exchange Online är konfigurerad att behålla borttagna objekt i 14 dagar som standard.</span><span class="sxs-lookup"><span data-stu-id="849a6-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="849a6-160">Men du kan ändra den här inställningen till högst 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="849a6-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="849a6-161">Mer information finns i Ändra [bevarandetiden för borttagna objekt för en postlåda i Exchange Online](https://www.microsoft.com/?ref=go).</span><span class="sxs-lookup"><span data-stu-id="849a6-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span>

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="849a6-162">Steg 2: Skapa en Exchange bevarandeprincip för postlådor</span><span class="sxs-lookup"><span data-stu-id="849a6-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="849a6-163">Nästa steg är att skapa en ny bevarandeprincip och lägga till bevarandetaggar i den, inklusive bevarandeprinciptaggen för återställningsbara objekt som du skapade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="849a6-163">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1.</span></span> <span data-ttu-id="849a6-164">Den här nya principen kommer att tillämpas på postlådor som är på plats i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="849a6-164">This new policy will be applied to mailboxes on hold in the next step.</span></span>

<span data-ttu-id="849a6-165">Innan du skapar den nya bevarandeprincipen måste du bestämma vilka ytterligare bevarandetaggar du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="849a6-165">Before you create the new retention policy, determine the additional retention tags that you want to add.</span></span> <span data-ttu-id="849a6-166">En lista med de bevarandetaggar som läggs till i standardprincipen för MRM och information om hur du skapar nya bevarandetaggar finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="849a6-166">For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>

- [<span data-ttu-id="849a6-167">Standardprincip för kvarhållning i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="849a6-167">Default Retention Policy in Exchange Online</span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [<span data-ttu-id="849a6-168">Standardmappar med stöd för bevarandeprinciptaggar</span><span class="sxs-lookup"><span data-stu-id="849a6-168">Default folders that support Retention Policy Tags</span></span>](/exchange/security-and-compliance/messaging-records-management/default-folders)

- <span data-ttu-id="849a6-169">Avsnittet "Skapa en bevarandetagg" i avsnittet [Skapa en bevarandeprincip.](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="849a6-169">The "Create a retention tag" section in the [Create a Retention Policy](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) topic.</span></span>

<span data-ttu-id="849a6-170">Du kan använda EAC eller Exchange Online PowerShell för att skapa en bevarandeprincip.</span><span class="sxs-lookup"><span data-stu-id="849a6-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>

### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="849a6-171">Använda EAC för att skapa en bevarandeprincip</span><span class="sxs-lookup"><span data-stu-id="849a6-171">Use the EAC to create a retention policy</span></span>

1. <span data-ttu-id="849a6-172">I EAC går du till **Bevarandeprinciper för** \> **efterlevnadshantering och** klickar sedan på Lägg till  ![ ](../media/ITPro-EAC-AddIcon.gif) ikon.</span><span class="sxs-lookup"><span data-stu-id="849a6-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

2. <span data-ttu-id="849a6-173">Ange **ett namn som** beskriver syftet **med** bevarandeprincipen under Namn på sidan Ny bevarandeprincip. **MRM-princip för postlådor som är på plats.**</span><span class="sxs-lookup"><span data-stu-id="849a6-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span>

3. <span data-ttu-id="849a6-174">Klicka **på Lägg till ikon** under **Bevarandetaggar.** ![ ](../media/ITPro-EAC-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="849a6-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="849a6-175">Markera bevarandetaggen för återställningsbara objekt som du skapade i steg 1 i listan med bevarandetaggar och klicka sedan på Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="849a6-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>

    ![Välj den anpassade bevarandetaggen Återställningsbara objekt](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. <span data-ttu-id="849a6-177">Välj ytterligare bevarandetaggar som du vill lägga till i bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="849a6-177">Select additional retention tags to add to the retention policy.</span></span> <span data-ttu-id="849a6-178">Du kanske till exempel vill lägga till samma taggar som ingår i standardprincipen för MRM.</span><span class="sxs-lookup"><span data-stu-id="849a6-178">For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>

6. <span data-ttu-id="849a6-179">När du är klar med att lägga till bevarandetaggar klickar du på **OK.**</span><span class="sxs-lookup"><span data-stu-id="849a6-179">When you're finished adding retention tags, click **OK**.</span></span>

7. <span data-ttu-id="849a6-180">Klicka **på Spara** för att skapa den nya bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="849a6-180">Click **Save** to create the new retention policy.</span></span>

    <span data-ttu-id="849a6-181">Observera att de bevarandetaggar som är kopplade till bevarandeprincipen visas i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="849a6-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>

    ![Bevarandetaggar som är kopplade till bevarandeprincipen visas i informationsfönstret](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="849a6-183">Använda Exchange Online PowerShell för att skapa en bevarandeprincip</span><span class="sxs-lookup"><span data-stu-id="849a6-183">Use Exchange Online PowerShell to create a retention policy</span></span>

<span data-ttu-id="849a6-184">Kör följande kommando för att skapa en ny bevarandeprincip för postlådor som är bevarande.</span><span class="sxs-lookup"><span data-stu-id="849a6-184">Run the following command to create new retention policy for mailboxes on hold.</span></span>

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="849a6-185">Följande kommando skapar till exempel kvarhållningsprincipen och länkade bevarandetaggar som visas i föregående bild.</span><span class="sxs-lookup"><span data-stu-id="849a6-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="849a6-186">Steg 3: Tillämpa den Exchange bevarandeprincipen på postlådor som är bevarande</span><span class="sxs-lookup"><span data-stu-id="849a6-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="849a6-187">Det sista steget är att tillämpa den nya bevarandeprincip du skapade i steg 2 på postlådor som är bevarande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="849a6-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="849a6-188">Du kan använda EAC eller Exchange Online PowerShell för att tillämpa kvarhållningsprincipen på en enskild postlåda eller flera postlådor.</span><span class="sxs-lookup"><span data-stu-id="849a6-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span>

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="849a6-189">Använda EAC för att tillämpa den nya bevarandeprincipen</span><span class="sxs-lookup"><span data-stu-id="849a6-189">Use the EAC to apply the new retention policy</span></span>

1. <span data-ttu-id="849a6-190">Gå till  >  **Mottagarnas postlådor.**</span><span class="sxs-lookup"><span data-stu-id="849a6-190">Go to **Recipients** > **Mailboxes**.</span></span>

2. <span data-ttu-id="849a6-191">Markera den postlåda som du vill tillämpa bevarandeprincipen på i listvyn och klicka sedan **på** Redigera ![ redigera-ikonen ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="849a6-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

3. <span data-ttu-id="849a6-192">Klicka på **Postlådefunktioner** på **sidan Användarpostlåda.**</span><span class="sxs-lookup"><span data-stu-id="849a6-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>

4. <span data-ttu-id="849a6-193">Välj **den bevarandeprincip** du skapade i steg 2 under Bevarandeprincip och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="849a6-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>

<span data-ttu-id="849a6-194">Du kan också använda EAC för att tillämpa kvarhållningsprincipen på flera postlådor.</span><span class="sxs-lookup"><span data-stu-id="849a6-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>

1. <span data-ttu-id="849a6-195">Gå till  >  **Mottagarnas postlådor.**</span><span class="sxs-lookup"><span data-stu-id="849a6-195">Go to **Recipients** > **Mailboxes**.</span></span>

2. <span data-ttu-id="849a6-196">I listvyn använder du tangenterna Skift eller Ctrl för att markera flera postlådor.</span><span class="sxs-lookup"><span data-stu-id="849a6-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>

3. <span data-ttu-id="849a6-197">Klicka på Fler alternativ i **informationsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="849a6-197">In the details pane, click **More options**.</span></span>

4. <span data-ttu-id="849a6-198">Klicka **på Uppdatera under** **Bevarandeprincip.**</span><span class="sxs-lookup"><span data-stu-id="849a6-198">Under **Retention Policy**, click **Update**.</span></span>

5. <span data-ttu-id="849a6-199">Markera den **bevarandeprincip du** skapade i steg 2 på sidan Mass tilldela bevarandeprincip och klicka sedan på **Spara.**</span><span class="sxs-lookup"><span data-stu-id="849a6-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="849a6-200">Använda Exchange Online PowerShell för att tillämpa den nya bevarandeprincipen</span><span class="sxs-lookup"><span data-stu-id="849a6-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>

<span data-ttu-id="849a6-201">Du kan använda Exchange Online PowerShell för att tillämpa en ny bevarandeprincip på en enda postlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="849a6-202">Men den faktiska kraften hos PowerShell är att du kan använda det för att snabbt identifiera alla postlådor i organisationen som har bevarande av juridiska skäl eller In-Place bevarande, och sedan tillämpa den nya bevarandeprincipen på alla postlådor som är bevarande i ett enda kommando.</span><span class="sxs-lookup"><span data-stu-id="849a6-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="849a6-203">Här är några exempel på hur du Exchange PowerShell för att tillämpa en bevarandeprincip på en eller flera postlådor.</span><span class="sxs-lookup"><span data-stu-id="849a6-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="849a6-204">I alla exempel tillämpas bevarandeprincipen som skapades i steg 2.</span><span class="sxs-lookup"><span data-stu-id="849a6-204">All of the examples apply the retention policy that was created in Step 2.</span></span>

<span data-ttu-id="849a6-205">I det här exemplet tillämpas den nya bevarandeprincipen på Pilar Pinillas postlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="849a6-206">Det här exemplet gäller den nya bevarandeprincipen för alla postlådor i organisationen där bevarande av juridiska skäl används.</span><span class="sxs-lookup"><span data-stu-id="849a6-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="849a6-207">Det här exemplet gäller den nya bevarandeprincipen för alla postlådor i organisationen som finns In-Place bevarande.</span><span class="sxs-lookup"><span data-stu-id="849a6-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="849a6-208">Du kan använda **cmdlet:en Get-Mailbox** för att verifiera att den nya bevarandeprincipen har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="849a6-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span>

<span data-ttu-id="849a6-209">Här är några exempel för att verifiera att kommandona i de tidigare exemplen har tillämpat kvarhållningsprincipen "MRM-princip för postlådor på bevarande" för postlådor med bevarande av juridiska skäl och postlådor In-Place bevarande.</span><span class="sxs-lookup"><span data-stu-id="849a6-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="849a6-210">(Valfritt) Steg 4: Kör assistenten för hanterade mappar för att tillämpa de nya bevarandeinställningarna</span><span class="sxs-lookup"><span data-stu-id="849a6-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="849a6-211">När du har tillämpat den nya Exchange-bevarandeprincipen på postlådor som är bevarande kan det ta upp till 7 dagar i Exchange Online för assistenten för hanterade mappar att bearbeta postlådorna med inställningarna i den nya bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="849a6-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="849a6-212">I stället för att vänta på att assistenten för hanterade mappar körs kan du använda cmdleten **Start-ManagedFolderAssistant** till att manuellt utlösa assistenten att bearbeta postlådorna som du tillämpade den nya bevarandeprincipen på.</span><span class="sxs-lookup"><span data-stu-id="849a6-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span>

<span data-ttu-id="849a6-213">Kör följande kommando för att starta assistenten för hanterade mappar för Pilar Pinillas postlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="849a6-214">Kör följande kommandon för att starta assistenten för hanterade mappar för alla postlådor som är i följd.</span><span class="sxs-lookup"><span data-stu-id="849a6-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="849a6-215">Mer information</span><span class="sxs-lookup"><span data-stu-id="849a6-215">More information</span></span>

- <span data-ttu-id="849a6-216">När du har aktiverar en användares arkivpostlåda kan du berätta för användaren att andra objekt i användarens postlåda (inte bara objekt i mappen Återställningsbara objekt) kan flyttas till arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="849a6-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="849a6-217">Det beror på att standardprincipen för MRM som har tilldelats till Exchange Online-postlådor innehåller en bevarandetagg (med namnet Standard 2 år flytta till arkiv) som flyttar objekt till arkivpostlådan två år efter datumet då objektet levererades till postlådan eller skapades av användaren.</span><span class="sxs-lookup"><span data-stu-id="849a6-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="849a6-218">Mer information finns i [Standardprincip för bevarande i Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="849a6-218">For more information, see [Default Retention Policy in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span></span>

- <span data-ttu-id="849a6-219">När du har aktiverar en användares arkivpostlåda kan du även berätta för användaren att de kan återställa borttagna objekt i mappen Återställningsbara objekt i deras arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="849a6-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="849a6-220">Det kan de göra i Outlook  genom att välja mappen Borttaget i arkivpostlådan och sedan klicka på Återställ borttagna objekt från **servern** på **fliken** Start. Mer information om hur du återställer borttagna objekt finns i [Återskapa borttagna objekt i Outlook för Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="849a6-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span>
