---
title: Ta bort en inaktiv postlåda
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: När du inte längre behöver bevara innehållet i en inaktiv Microsoft 365 kan du ta bort den inaktiva postlådan permanent.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162926"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="b3b72-103">Ta bort en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="b3b72-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="b3b72-104">En inaktiv postlåda används för att bevara en tidigare anställds e-post när de har lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="b3b72-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="b3b72-105">När du inte längre behöver bevara innehållet i en inaktiv postlåda kan du ta bort den inaktiva postlådan permanent genom att ta bort bevarandet.</span><span class="sxs-lookup"><span data-stu-id="b3b72-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="b3b72-106">Det är också möjligt att flera inkorgar kan placeras i en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="b3b72-107">En inaktiv postlåda kan till exempel spärras för bevarande av juridiska skäl och på ett eller flera In-Place inkorgar.</span><span class="sxs-lookup"><span data-stu-id="b3b72-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="b3b72-108">Dessutom kan en bevarandeprincip (skapas i säkerhets- och efterlevnadscentret i Office 365 eller Microsoft 365) tillämpas på den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="b3b72-109">Du måste ta bort alla bevarandeprinciper och bevarandeprinciper från en inaktiv postlåda för att ta bort den.</span><span class="sxs-lookup"><span data-stu-id="b3b72-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="b3b72-110">När du har tagit bort principer för kvarhållning och kvarhållning markeras den inaktiva postlådan för borttagning och tas bort permanent när den har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="b3b72-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b3b72-111">Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet presenterar vi att innehållet i In-Place Holds har Exchange i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b3b72-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="b3b72-112">Det innebär att du bör använda principer för kvarhållning av juridiska skäl och bevarandeprinciper för att skapa en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="b3b72-113">Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3b72-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="b3b72-114">Men du kan fortfarande ändra varaktigheten för ett aktivt In-Place som gjorts på en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="b3b72-115">Men med början den 1 oktober 2020 kan du inte ändra varaktigheten för varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="b3b72-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="b3b72-116">Du kan bara ta bort en inaktiv postlåda genom att ta bort In-Place inaktiv.</span><span class="sxs-lookup"><span data-stu-id="b3b72-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="b3b72-117">Befintliga inaktiva postlådor som finns på In-Place behålls fortfarande tills brytningen tas bort.</span><span class="sxs-lookup"><span data-stu-id="b3b72-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="b3b72-118">Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="b3b72-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="b3b72-119">I avsnittet [Mer information finns](#more-information) en beskrivning av vad som händer när inkorgarna har tagits bort från en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="b3b72-120">Innan du tar bort en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="b3b72-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="b3b72-121">Du måste använda PowerShell Exchange Online ta bort ett bevarande av juridiska skäl från en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="b3b72-122">Du kan inte använda Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="b3b72-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="b3b72-123">Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="b3b72-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b3b72-124">Du kan kopiera innehållet i en inaktiv postlåda till en annan postlåda innan du tar bort den inaktiva postlådan och tar bort den.</span><span class="sxs-lookup"><span data-stu-id="b3b72-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="b3b72-125">Mer information finns i [Återställa en inaktiv postlåda i Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b3b72-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="b3b72-126">Om du tar bort bevarandeprincipen eller bevarandeprincipen från en inaktiv postlåda och bevarandeperioden för den mjukt borttagna postlådan för postlådan har upphört att gälla, tas postlådan bort permanent.</span><span class="sxs-lookup"><span data-stu-id="b3b72-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="b3b72-127">När den har tagits bort går det inte att återställa den.</span><span class="sxs-lookup"><span data-stu-id="b3b72-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="b3b72-128">Se till att du inte längre behöver innehållet i postlådan innan du tar bort det.</span><span class="sxs-lookup"><span data-stu-id="b3b72-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="b3b72-129">Om du vill återaktivera en inaktiv postlåda kan du återställa den.</span><span class="sxs-lookup"><span data-stu-id="b3b72-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="b3b72-130">Mer information finns i [Återställa en inaktiv postlåda i Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b3b72-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="b3b72-131">Mer information om inaktiva postlådor finns i [Inaktiva postlådor i Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b3b72-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="b3b72-132">Steg 1: Identifiera eventuella spärrade e-postlådor i inaktiva postlådor</span><span class="sxs-lookup"><span data-stu-id="b3b72-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="b3b72-133">Som tidigare nämnts kan bevarande av juridiska skäl, In-Place bevarandeprincip eller bevarandeprincip placeras i en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="b3b72-134">Det första steget är att identifiera spärrade e-postlådor i inaktiva postlådor.</span><span class="sxs-lookup"><span data-stu-id="b3b72-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="b3b72-135">Kör följande kommando för att visa information om inaktiva postlådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b3b72-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="b3b72-136">Värdet för **True för** egenskapen **LitigationHoldEnabled** anger att den inaktiva postlådan finns på Bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="b3b72-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="b3b72-137">Om ett In-Place inaktiv postlåda placeras på en inaktiv postlåda visas GUID för holden som värde för egenskapen **InPlaceHolds.**</span><span class="sxs-lookup"><span data-stu-id="b3b72-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="b3b72-138">Följande resultat för två inaktiva postlådor visar till exempel att bevarande av juridiska skäl sätts på Ann Beebe och att en policy för bevarande av In-Place och bevarande placeras på Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="b3b72-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="b3b72-139">Om många spärrade In-Place eller bevarandeprinciper placeras på en inaktiv postlåda visas inte alla In-Place-guid för håll visas.</span><span class="sxs-lookup"><span data-stu-id="b3b72-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="b3b72-140">Du kan köra följande kommando för att visa alla GUID:er i egenskapen InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="b3b72-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="b3b72-141">Mer information om vilka som är spärrade finns i Identifiera typ av [spärrade objekt i en postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="b3b72-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="b3b72-142">Steg 2: Ta bort ett väntande från en inaktiv postlåda</span><span class="sxs-lookup"><span data-stu-id="b3b72-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="b3b72-143">När du har identifierat vilken typ av spärrade objekt som har placerats på den inaktiva postlådan (och om det finns flera spärrade objekt) är nästa steg att ta bort de spärrade objekten i postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="b3b72-144">Som tidigare nämnts måste du ta bort alla som är spärrade för att permanent ta bort en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="b3b72-145">Ta bort bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="b3b72-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="b3b72-146">Som tidigare nämnts måste du använda Windows PowerShell ta bort bevarande av juridiska skäl från en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="b3b72-147">Du kan inte använda EAC.</span><span class="sxs-lookup"><span data-stu-id="b3b72-147">You can't use the EAC.</span></span> <span data-ttu-id="b3b72-148">Kör följande kommando för att ta bort bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="b3b72-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="b3b72-149">Det bästa sättet att identifiera en inaktiv postlåda är att använda det unika namnet eller det unika Exchange GUID-värdet.</span><span class="sxs-lookup"><span data-stu-id="b3b72-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="b3b72-150">Om du använder något av dessa värden undviker du att ange fel postlåda av misstag.</span><span class="sxs-lookup"><span data-stu-id="b3b72-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="b3b72-151">Ta bort en inaktiv postlåda från en bevarandeprincip</span><span class="sxs-lookup"><span data-stu-id="b3b72-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="b3b72-152">Proceduren för att ta bort en inaktiv postlåda från Microsoft 365 bevarandeprincip beror på om den inaktiva postlådans bevarandeprincip är organisationsomfattande eller explicit.</span><span class="sxs-lookup"><span data-stu-id="b3b72-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="b3b72-153">på vilken typ av bevarandeprincip som tilldelas till den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="b3b72-154">Organisationsomfattande bevarandeprinciper som tilldelats alla postlådor i organisationen.</span><span class="sxs-lookup"><span data-stu-id="b3b72-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="b3b72-155">Använd **cmdlet Get-OrganizationConfig** i Exchange Online PowerShell för att få information om bevarandeprinciper för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b3b72-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="b3b72-156">Specifika bevarandeprinciper för plats som tilldelats specifika postlådor.</span><span class="sxs-lookup"><span data-stu-id="b3b72-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="b3b72-157">Det här är principer som tilldelas till innehållsplatser för specifika användare.</span><span class="sxs-lookup"><span data-stu-id="b3b72-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="b3b72-158">Använd **cmdleten Get-Mailbox -IncludeInactiveMailbox** i Exchange Online PowerShell för att få information om bevarandeprinciper som tilldelats till specifika inaktiva postlådor.</span><span class="sxs-lookup"><span data-stu-id="b3b72-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="b3b72-159">Ta bort en inaktiv postlåda från en bevarandeprincip för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="b3b72-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="b3b72-160">Kör följande kommando i Exchange Online PowerShell för att utesluta en inaktiv postlåda från en bevarandeprincip för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b3b72-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="b3b72-161">Mer information om att identifiera organisationsomfattande bevarandeprinciper som tillämpas på en inaktiv postlåda och skaffa GUID för en bevarandeprincip finns i avsnittet Get-OrganizationConfig i Identifiera typ av bevarande som gjorts för en [postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="b3b72-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="b3b72-162">Alternativt kan du köra följande kommando för att ta bort den inaktiva postlådan från alla organisationsomfattande principer:</span><span class="sxs-lookup"><span data-stu-id="b3b72-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="b3b72-163">Ta bort en inaktiv postlåda från en viss bevarandeprincip för plats</span><span class="sxs-lookup"><span data-stu-id="b3b72-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="b3b72-164">Kör följande kommando i Säkerhets- [& Compliance Center PowerShell för](/powershell/exchange/connect-to-scc-powershell) att ta bort en inaktiv postlåda från en explicit bevarandeprincip.</span><span class="sxs-lookup"><span data-stu-id="b3b72-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="b3b72-165">Mer information om att identifiera specifika platsbevarandeprinciper som tillämpas på en inaktiv postlåda och skaffa GUID för en bevarandeprincip finns i avsnittet "Get-Mailbox" i Så här identifierar du typen av bevarande som har placerats i en [postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)</span><span class="sxs-lookup"><span data-stu-id="b3b72-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="b3b72-166">Ta bort In-Place in innehåller</span><span class="sxs-lookup"><span data-stu-id="b3b72-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="b3b72-167">Det finns två sätt att ta bort ett In-Place från en inaktiv postlåda:</span><span class="sxs-lookup"><span data-stu-id="b3b72-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="b3b72-168">**Ta bort In-Place Håll ned-objektet**.</span><span class="sxs-lookup"><span data-stu-id="b3b72-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="b3b72-169">Om den inaktiva postlåda som du vill ta bort permanent är den enda källpostlådan för ett In-Place-objekt, kan du bara ta bort In-Place Håll objekt.</span><span class="sxs-lookup"><span data-stu-id="b3b72-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b3b72-170">Du måste inaktivera holden innan du kan ta bort ett objekt In-Place På.</span><span class="sxs-lookup"><span data-stu-id="b3b72-170">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="b3b72-171">Om du försöker ta bort In-Place ett Håll-objekt som har aktiverats för att hålla får du ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="b3b72-171">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="b3b72-172">**Ta bort den inaktiva postlådan som en källpostlåda i ett In-Place på**.</span><span class="sxs-lookup"><span data-stu-id="b3b72-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="b3b72-173">Om du vill behålla andra källpostlådor för ett In-Place-objekt kan du ta bort den inaktiva postlådan från listan med källpostlådor och behålla In-Place-objekt.</span><span class="sxs-lookup"><span data-stu-id="b3b72-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="b3b72-174">Ta bort ett In-Place håll</span><span class="sxs-lookup"><span data-stu-id="b3b72-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="b3b72-175">Skapa en variabel som innehåller egenskaperna för den In-Place som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="b3b72-175">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="b3b72-176">Använd det In-Place guiD för håll som du fick i steg [1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identifiera antalet i en inaktiv postlåda .</span><span class="sxs-lookup"><span data-stu-id="b3b72-176">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="b3b72-177">Inaktivera alternativet för att hålla In-Place håll.</span><span class="sxs-lookup"><span data-stu-id="b3b72-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="b3b72-178">Ta bort In-Place håll.</span><span class="sxs-lookup"><span data-stu-id="b3b72-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="b3b72-179">Ta bort en inaktiv postlåda från ett In-Place postlåda</span><span class="sxs-lookup"><span data-stu-id="b3b72-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="b3b72-180">Om In-Place innehåller ett stort antal källpostlådor är det möjligt att den inaktiva postlådan  inte visas på sidan Källor i EAC.</span><span class="sxs-lookup"><span data-stu-id="b3b72-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="b3b72-181">Upp till 3 000 postlådor  visas på sidan Källor när du redigerar ett In-Place på plats.</span><span class="sxs-lookup"><span data-stu-id="b3b72-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="b3b72-182">Om en inaktiv postlåda inte  finns med på sidan Källor kan du använda PowerShell Exchange Online ta bort den från sidan In-Place Postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="b3b72-183">Skapa en variabel som innehåller egenskaperna för den In-Place som är placerat på den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-183">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="b3b72-184">Använd det In-Place guiD för håll som du fick i steg [1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identifiera antalet i en inaktiv postlåda .</span><span class="sxs-lookup"><span data-stu-id="b3b72-184">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="b3b72-185">Kontrollera att den inaktiva postlådan visas som en källpostlåda för In-Place postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="b3b72-186">Egenskapen *Sources* för egenskapen In-Place Identifierar källpostlådorna med deras *LegacyExchangeDN-egenskaper.*</span><span class="sxs-lookup"><span data-stu-id="b3b72-186">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="b3b72-187">Eftersom den här egenskapen unikt identifierar inaktiva  postlådor förhindrar du att fel postlåda tas bort med egenskapen Sources från In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="b3b72-187">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="b3b72-188">På så sätt undviker du också problem om två postlådor har samma alias eller SMTP-adress.</span><span class="sxs-lookup"><span data-stu-id="b3b72-188">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="b3b72-189">Ta bort den inaktiva postlådan från listan över källpostlådor i variabeln.</span><span class="sxs-lookup"><span data-stu-id="b3b72-189">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="b3b72-190">Se till att använda **LegacyExchangeDN** för den inaktiva postlåda som returnerades av kommandot i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="b3b72-190">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="b3b72-191">Med följande kommando tas till exempel den inaktiva postlådan bort för Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="b3b72-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="b3b72-192">Kontrollera att den inaktiva postlådan tas bort från listan över källpostlådor i variabeln.</span><span class="sxs-lookup"><span data-stu-id="b3b72-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="b3b72-193">Ändra In-Place med den uppdaterade listan över källpostlådor, som inte innehåller den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="b3b72-194">Kontrollera att den inaktiva postlådan tas bort från listan över källpostlådor för In-Place postlådan.</span><span class="sxs-lookup"><span data-stu-id="b3b72-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="b3b72-195">Mer information</span><span class="sxs-lookup"><span data-stu-id="b3b72-195">More information</span></span>

- <span data-ttu-id="b3b72-196">**En inaktiv postlåda är en typ av mjuk borttagna postlåda.**</span><span class="sxs-lookup"><span data-stu-id="b3b72-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="b3b72-197">I Exchange Online är en mjuk borttagna postlåda en postlåda som har tagits bort men kan återställas inom en viss bevarandeperiod.</span><span class="sxs-lookup"><span data-stu-id="b3b72-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="b3b72-198">En tidigare inaktiv postlåda blir tillgänglig som en mjuk borttagna postlåda om Exchange Online i 183 dagar.</span><span class="sxs-lookup"><span data-stu-id="b3b72-198">A previously inactive mailbox will be available as a soft-deleted mailbox in Exchange Online for 183 days.</span></span> <span data-ttu-id="b3b72-199">Det innebär att postlådan kan återställas inom 183 dagar efter att den tagits bort mjukt.</span><span class="sxs-lookup"><span data-stu-id="b3b72-199">This means that the mailbox can be recovered within 183 days of being soft-deleted.</span></span> <span data-ttu-id="b3b72-200">Efter 183 dagar markeras en mjuk borttagen postlåda för permanent borttagning och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="b3b72-200">After 183 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="b3b72-201">**Vad händer när du har tagit bort borttagningen av en inaktiv postlåda?**</span><span class="sxs-lookup"><span data-stu-id="b3b72-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="b3b72-202">Postlådan behandlas som andra mjuk borttagna postlådor och markeras för permanent borttagning efter att den mjuka bevarandeperioden på 183 dagar har löpt ut.</span><span class="sxs-lookup"><span data-stu-id="b3b72-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 183-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="b3b72-203">Bevarandetiden startar det datum då postlådan först blev inaktiv.</span><span class="sxs-lookup"><span data-stu-id="b3b72-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="b3b72-204">Det här datumet kallas för mjuk borttagningsdatum, det datum då motsvarande användarkonto togs bort eller när Exchange Online-postlådan togs bort med cmdleten **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="b3b72-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="b3b72-205">Det mjukt borttagna datumet är inte det datum då du tog bort det.</span><span class="sxs-lookup"><span data-stu-id="b3b72-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="b3b72-206">**Tas en inaktiv postlåda bort permanent direkt efter att brytningen har tagits bort?**</span><span class="sxs-lookup"><span data-stu-id="b3b72-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="b3b72-207">En tidigare inaktiv postlåda blir tillgänglig med mjuk borttagning i 183 dagar.</span><span class="sxs-lookup"><span data-stu-id="b3b72-207">A formerly inactive mailbox will be available in the soft-deleted state for 183 days.</span></span> <span data-ttu-id="b3b72-208">Efter 183 dagar markeras postlådan för permanent borttagning.</span><span class="sxs-lookup"><span data-stu-id="b3b72-208">After 183 days the mailbox will be marked for permanent deletion.</span></span>

- <span data-ttu-id="b3b72-209">**Hur visar du information om en inaktiv postlåda när du har tagit bort det?**</span><span class="sxs-lookup"><span data-stu-id="b3b72-209">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="b3b72-210">När ett håll har tagits bort och den inaktiva postlådan återställs till en mjuk borttagen postlåda returneras den inte med hjälp av parametern *InactiveMailboxOnly* med cmdlet:en **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="b3b72-210">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="b3b72-211">Men du kan visa information om postlådan med hjälp av **kommandot Get-Mailbox -SoftDeletedMailbox.**</span><span class="sxs-lookup"><span data-stu-id="b3b72-211">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="b3b72-212">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b3b72-212">For example:</span></span>

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  <span data-ttu-id="b3b72-213">I exemplet ovan identifierar egenskapen *WhenSoftDeleted* det mjukt borttagna datumet, som i det här exemplet är 16 juni 2020.</span><span class="sxs-lookup"><span data-stu-id="b3b72-213">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is June 16, 2020.</span></span> <span data-ttu-id="b3b72-214">Egenskapen *WasInactiveMailbox* visas som eftersom `True` den tidigare var en inaktiv postlåda.</span><span class="sxs-lookup"><span data-stu-id="b3b72-214">The *WasInactiveMailbox* property is listed as `True` because it was previously an inactive mailbox.</span></span> <span data-ttu-id="b3b72-215">Postlådan tas bort permanent 183 dagar efter den 30 september 2020.</span><span class="sxs-lookup"><span data-stu-id="b3b72-215">The mailbox will be permanently deleted 183 days after September 30, 2020.</span></span>

