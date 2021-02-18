---
title: Karantäntaggar
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratörer kan ta reda på hur de kan använda karantäntaggar för att styra vad användarna kan göra med meddelanden i karantän.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 207f22c9acaa183e195f5a2ee33be65cdf4991dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289419"
---
# <a name="quarantine-tags"></a><span data-ttu-id="21eac-103">Karantäntaggar</span><span class="sxs-lookup"><span data-stu-id="21eac-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="21eac-104">De funktioner som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="21eac-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="21eac-105">Med karantäntaggar i Exchange Online Protection (EOP) kan administratörer styra vad användare kan göra med meddelanden i karantän baserat på hur meddelandet kom i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="21eac-106">EOP har traditionellt tillåtit eller förhindrat [](find-and-release-quarantined-messages-as-a-user.md) vissa nivåer av interaktivitet för meddelanden i karantän och [i skräppost-aviseringar för slutanvändare.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="21eac-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="21eac-107">Slutanvändarna kan till exempel visa och släppa meddelanden som satt i karantän genom skräppostfiltrering som skräppost eller massutskick, men de kan inte visa eller släppa meddelanden som satt i karantän som nätfiske i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="21eac-108">För [funktioner som stöds](#step-2-assign-a-quarantine-tag-to-supported-features)anger karantäntaggar vad användare tillåts att göra i skräppost-aviseringar för slutanvändare och i de meddelanden i karantän som sätts i karantän (meddelanden där användaren är mottagare).</span><span class="sxs-lookup"><span data-stu-id="21eac-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="21eac-109">Standardtaggar för karantän tilldelas automatiskt för att tillämpa historiska funktioner för slutanvändare på meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="21eac-110">Du kan också skapa och tilldela anpassade karantäntaggar för att tillåta eller förhindra att slutanvändare utför särskilda åtgärder på meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="21eac-111">De enskilda behörigheterna kombineras i följande förinställda behörighetsgrupper:</span><span class="sxs-lookup"><span data-stu-id="21eac-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="21eac-112">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-112">No access</span></span>
- <span data-ttu-id="21eac-113">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-113">Limited access</span></span>
- <span data-ttu-id="21eac-114">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-114">Full access</span></span>

<span data-ttu-id="21eac-115">De tillgängliga enskilda behörigheterna och vad som ingår eller inte ingår i de förinställda behörighetsgrupperna beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="21eac-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="21eac-116">Behörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-116">Permission</span></span>|<span data-ttu-id="21eac-117">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-117">No access</span></span>|<span data-ttu-id="21eac-118">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-118">Limited access</span></span>|<span data-ttu-id="21eac-119">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="21eac-120">**Allow sender** _(PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="21eac-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="21eac-122">**Blockera avsändare** _(PermissionToBlockSender)_</span><span class="sxs-lookup"><span data-stu-id="21eac-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="21eac-125">**Delete** _(PermissionToDelete)_</span><span class="sxs-lookup"><span data-stu-id="21eac-125">**Delete** (_PermissionToDelete_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="21eac-128">**Preview** _(PermissionToPreview)_</span><span class="sxs-lookup"><span data-stu-id="21eac-128">**Preview** (_PermissionToPreview_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="21eac-131">**Tillåt mottagare att släppa ett meddelande från karantän** _(PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="21eac-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="21eac-133">**Tillåt mottagare att begära att ett meddelande släpps från karantän** _(PermissionToRequestRelease)_</span><span class="sxs-lookup"><span data-stu-id="21eac-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Bockmarkering](../../media/checkmark.png)||
|

<span data-ttu-id="21eac-135">Om du inte gillar standardbehörigheterna i de förinställda behörighetsgrupperna kan du använda anpassade behörigheter när du skapar eller ändrar anpassade karantäntaggar.</span><span class="sxs-lookup"><span data-stu-id="21eac-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="21eac-136">Mer information om vad varje behörighet gör finns i avsnittet [om](#quarantine-tag-permission-details) taggbehörighet för karantän senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21eac-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="21eac-137">Du skapar och tilldelar karantäntaggar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med Exchange Online-postlådor, fristående EOP PowerShell i EOP-organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="21eac-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="21eac-138">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="21eac-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="21eac-139">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="21eac-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="21eac-140">Gå direkt till sidan **med karantäntaggar** genom att <https://protection.office.com/quarantineTags> öppna.</span><span class="sxs-lookup"><span data-stu-id="21eac-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="21eac-141">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="21eac-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="21eac-142">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="21eac-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="21eac-143">Om du vill visa, skapa, ändra eller ta bort  karantäntaggar  måste du vara medlem i rollerna Organisationshantering eller Säkerhetsadministratör i Säkerhets- [& Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="21eac-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="21eac-144">Steg 1: Skapa karantäntaggar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="21eac-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="21eac-145">Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="21eac-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="21eac-146">På sidan **Karantän-taggar** väljer du **Lägg till anpassad tagg.**</span><span class="sxs-lookup"><span data-stu-id="21eac-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="21eac-147">Guiden **Ny tagg** öppnas.</span><span class="sxs-lookup"><span data-stu-id="21eac-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="21eac-148">Ange ett **kort men** unikt namn i fältet Taggnamn på sidan **Taggnamn.**</span><span class="sxs-lookup"><span data-stu-id="21eac-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="21eac-149">Du måste identifiera och välja taggen efter namn i kommande steg.</span><span class="sxs-lookup"><span data-stu-id="21eac-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="21eac-150">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="21eac-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="21eac-151">Välj **något av följande** värden på sidan För mottagarmeddelandeåtkomst:</span><span class="sxs-lookup"><span data-stu-id="21eac-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="21eac-152">**Ingen åtkomst**</span><span class="sxs-lookup"><span data-stu-id="21eac-152">**No access**</span></span>
   - <span data-ttu-id="21eac-153">**Begränsad åtkomst**</span><span class="sxs-lookup"><span data-stu-id="21eac-153">**Limited access**</span></span>
   - <span data-ttu-id="21eac-154">**Fullständig åtkomst**</span><span class="sxs-lookup"><span data-stu-id="21eac-154">**Full access**</span></span>

   <span data-ttu-id="21eac-155">De enskilda behörigheterna som ingår i behörighetsgrupperna beskrivs tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21eac-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="21eac-156">Om du vill ange anpassade behörigheter **väljer du Ange specifik åtkomst (avancerat)** och konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="21eac-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="21eac-157">**Välj inställning för släppåtgärd:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="21eac-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="21eac-158">**Ingen utgivningsåtgärd:** Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="21eac-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="21eac-159">**Tillåt mottagare att släppa ett meddelande från karantän**</span><span class="sxs-lookup"><span data-stu-id="21eac-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="21eac-160">**Tillåt mottagare att begära att ett meddelande ska släppas från karantän**</span><span class="sxs-lookup"><span data-stu-id="21eac-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="21eac-161">**Välj ytterligare åtgärder som mottagarna kan utföra för meddelanden** i karantän: Markera några, alla eller inget av följande värden:</span><span class="sxs-lookup"><span data-stu-id="21eac-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="21eac-162">**Ta bort**</span><span class="sxs-lookup"><span data-stu-id="21eac-162">**Delete**</span></span>
       - <span data-ttu-id="21eac-163">**Förhandsgranska**</span><span class="sxs-lookup"><span data-stu-id="21eac-163">**Preview**</span></span>
       - <span data-ttu-id="21eac-164">**Tillåt avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-164">**Allow sender**</span></span>
       - <span data-ttu-id="21eac-165">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-165">**Block sender**</span></span>

   <span data-ttu-id="21eac-166">De här behörigheterna och deras påverkan på meddelanden i karantän [](#quarantine-tag-permission-details) och i skräppost-aviseringar för slutanvändare beskrivs i avsnittet om taggbehörighet för karantän senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21eac-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="21eac-167">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="21eac-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="21eac-168">Granska **inställningarna** på sammanfattningssidan som visas.</span><span class="sxs-lookup"><span data-stu-id="21eac-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="21eac-169">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="21eac-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="21eac-170">Klicka på Skicka när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="21eac-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="21eac-171">Klicka **på** Klar på bekräftelsesidan som visas.</span><span class="sxs-lookup"><span data-stu-id="21eac-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="21eac-172">Nu är du redo att tilldela karantäntaggen till en karantänfunktion enligt beskrivningen i [steg 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="21eac-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="21eac-173">Skapa karantäntaggar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="21eac-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="21eac-174">Om du hellre vill använda PowerShell för att skapa karantäntaggar ansluter du till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använder cmdleten **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="21eac-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="21eac-175">Du har två olika metoder att välja bland:</span><span class="sxs-lookup"><span data-stu-id="21eac-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="21eac-176">Använd _parametern EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="21eac-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="21eac-177">Använd _parametern EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="21eac-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="21eac-178">De här metoderna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="21eac-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="21eac-179">Använda parametern EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="21eac-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="21eac-180">Om du vill skapa en karantäntagg _med hjälp av parametern EndUserQuarantinePermissionsValue_ ska du använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="21eac-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="21eac-181">Parametern _EndUserQuarantinePermissionsValue_ använder ett decimalvärde som konverteras från ett binärt värde.</span><span class="sxs-lookup"><span data-stu-id="21eac-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="21eac-182">Det binära värdet motsvarar de tillgängliga karantänbehörigheterna för slutanvändare i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="21eac-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="21eac-183">För varje behörighet är värdet 1 lika med Sant och värdet 0 är falskt.</span><span class="sxs-lookup"><span data-stu-id="21eac-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="21eac-184">Den ordning och de värden som krävs för varje enskild behörighet i förinställda behörighetsgrupper beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="21eac-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="21eac-185">Behörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-185">Permission</span></span>|<span data-ttu-id="21eac-186">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-186">No access</span></span>|<span data-ttu-id="21eac-187">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-187">Limited access</span></span>|<span data-ttu-id="21eac-188">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="21eac-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="21eac-189">PermissionToAllowSender</span></span>|<span data-ttu-id="21eac-190">0</span><span class="sxs-lookup"><span data-stu-id="21eac-190">0</span></span>|<span data-ttu-id="21eac-191">0</span><span class="sxs-lookup"><span data-stu-id="21eac-191">0</span></span>|<span data-ttu-id="21eac-192">1</span><span class="sxs-lookup"><span data-stu-id="21eac-192">1</span></span>|
|<span data-ttu-id="21eac-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="21eac-193">PermissionToBlockSender</span></span>|<span data-ttu-id="21eac-194">0</span><span class="sxs-lookup"><span data-stu-id="21eac-194">0</span></span>|<span data-ttu-id="21eac-195">1</span><span class="sxs-lookup"><span data-stu-id="21eac-195">1</span></span>|<span data-ttu-id="21eac-196">1</span><span class="sxs-lookup"><span data-stu-id="21eac-196">1</span></span>|
|<span data-ttu-id="21eac-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="21eac-197">PermissionToDelete</span></span>|<span data-ttu-id="21eac-198">0</span><span class="sxs-lookup"><span data-stu-id="21eac-198">0</span></span>|<span data-ttu-id="21eac-199">1</span><span class="sxs-lookup"><span data-stu-id="21eac-199">1</span></span>|<span data-ttu-id="21eac-200">1</span><span class="sxs-lookup"><span data-stu-id="21eac-200">1</span></span>|
|<span data-ttu-id="21eac-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="21eac-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="21eac-202">0</span><span class="sxs-lookup"><span data-stu-id="21eac-202">0</span></span>|<span data-ttu-id="21eac-203">0</span><span class="sxs-lookup"><span data-stu-id="21eac-203">0</span></span>|<span data-ttu-id="21eac-204">0</span><span class="sxs-lookup"><span data-stu-id="21eac-204">0</span></span>|
|<span data-ttu-id="21eac-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="21eac-205">PermissionToPreview</span></span>|<span data-ttu-id="21eac-206">0</span><span class="sxs-lookup"><span data-stu-id="21eac-206">0</span></span>|<span data-ttu-id="21eac-207">1</span><span class="sxs-lookup"><span data-stu-id="21eac-207">1</span></span>|<span data-ttu-id="21eac-208">1</span><span class="sxs-lookup"><span data-stu-id="21eac-208">1</span></span>|
|<span data-ttu-id="21eac-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="21eac-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="21eac-210">0</span><span class="sxs-lookup"><span data-stu-id="21eac-210">0</span></span>|<span data-ttu-id="21eac-211">0</span><span class="sxs-lookup"><span data-stu-id="21eac-211">0</span></span>|<span data-ttu-id="21eac-212">1</span><span class="sxs-lookup"><span data-stu-id="21eac-212">1</span></span>|
|<span data-ttu-id="21eac-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="21eac-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="21eac-214">0</span><span class="sxs-lookup"><span data-stu-id="21eac-214">0</span></span>|<span data-ttu-id="21eac-215">1</span><span class="sxs-lookup"><span data-stu-id="21eac-215">1</span></span>|<span data-ttu-id="21eac-216">0</span><span class="sxs-lookup"><span data-stu-id="21eac-216">0</span></span>|
|<span data-ttu-id="21eac-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="21eac-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="21eac-218">0</span><span class="sxs-lookup"><span data-stu-id="21eac-218">0</span></span>|<span data-ttu-id="21eac-219">0</span><span class="sxs-lookup"><span data-stu-id="21eac-219">0</span></span>|<span data-ttu-id="21eac-220">0</span><span class="sxs-lookup"><span data-stu-id="21eac-220">0</span></span>|
|<span data-ttu-id="21eac-221">Binärt värde</span><span class="sxs-lookup"><span data-stu-id="21eac-221">Binary value</span></span>|<span data-ttu-id="21eac-222">00000000</span><span class="sxs-lookup"><span data-stu-id="21eac-222">00000000</span></span>|<span data-ttu-id="21eac-223">01101010</span><span class="sxs-lookup"><span data-stu-id="21eac-223">01101010</span></span>|<span data-ttu-id="21eac-224">11101100</span><span class="sxs-lookup"><span data-stu-id="21eac-224">11101100</span></span>|
|<span data-ttu-id="21eac-225">Decimalvärde att använda</span><span class="sxs-lookup"><span data-stu-id="21eac-225">Decimal value to use</span></span>|<span data-ttu-id="21eac-226">0</span><span class="sxs-lookup"><span data-stu-id="21eac-226">0</span></span>|<span data-ttu-id="21eac-227">106</span><span class="sxs-lookup"><span data-stu-id="21eac-227">106</span></span>|<span data-ttu-id="21eac-228">236</span><span class="sxs-lookup"><span data-stu-id="21eac-228">236</span></span>|

<span data-ttu-id="21eac-229"><sup>\*</sup> Det här värdet är för närvarande alltid 0.</span><span class="sxs-lookup"><span data-stu-id="21eac-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="21eac-230">För PermissionToViewHeader döljer inte värdet 0  knappen Visa meddelanderubrik i information om det karantän-meddelandet (knappen är alltid tillgänglig).</span><span class="sxs-lookup"><span data-stu-id="21eac-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="21eac-231"><sup>\*\*</sup> Ange inte 1 för båda dessa värden.</span><span class="sxs-lookup"><span data-stu-id="21eac-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="21eac-232">Ange 0 för en till 1 och en annan eller ange 0 för båda.</span><span class="sxs-lookup"><span data-stu-id="21eac-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="21eac-233">I det här exemplet skapas ett nytt taggnamn för karantän, NoAccess, som tilldelar behörigheterna Ingen åtkomst enligt beskrivningen i föregående tabell.</span><span class="sxs-lookup"><span data-stu-id="21eac-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="21eac-234">Använd värdet 106 för begränsad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="21eac-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="21eac-235">För fullständig åtkomstbehörighet använder du värdet 236.</span><span class="sxs-lookup"><span data-stu-id="21eac-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="21eac-236">För anpassade behörigheter använder du föregående tabell för att få det binära värde som motsvarar de behörigheter du vill ha.</span><span class="sxs-lookup"><span data-stu-id="21eac-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="21eac-237">Konvertera det binära värdet till ett decimalvärde och använd decimalvärdet för _parametern EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="21eac-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="21eac-238">Detaljerad information om syntax och parametrar finns [i New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="21eac-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="21eac-239">Använda parametern EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="21eac-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="21eac-240">Så här skapar du en _karantäntagg med parametern EndUserQuarantinePermissionsValue:_</span><span class="sxs-lookup"><span data-stu-id="21eac-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="21eac-241">A.</span><span class="sxs-lookup"><span data-stu-id="21eac-241">A.</span></span> <span data-ttu-id="21eac-242">Lagra ett behörighetsobjekt i karantän för en variabel med cmdleten **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="21eac-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="21eac-243">B.</span><span class="sxs-lookup"><span data-stu-id="21eac-243">B.</span></span> <span data-ttu-id="21eac-244">Använd variabeln som _värdet EndUserQuarantinePermissions_ i **kommandot Ny karantäntag.**</span><span class="sxs-lookup"><span data-stu-id="21eac-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="21eac-245">Steg A: Lagra ett behörighetsobjekt i karantän för en variabel</span><span class="sxs-lookup"><span data-stu-id="21eac-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="21eac-246">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="21eac-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="21eac-247">Standardvärdet för oanvända parametrar är, så du behöver `$false` bara använda parametrarna där du vill ange `$true` värdet.</span><span class="sxs-lookup"><span data-stu-id="21eac-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="21eac-248">Följande exempel visar hur du skapar behörighetsobjekt som motsvarar de förinställda behörighetsgrupperna:</span><span class="sxs-lookup"><span data-stu-id="21eac-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="21eac-249">**Ingen åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="21eac-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="21eac-250">**Begränsad åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="21eac-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="21eac-251">**Fullständig åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="21eac-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="21eac-252">Om du vill se de värden du har angett kör du variabelnamnet som ett kommando (till exempel kör `$NoAccess` kommandot).</span><span class="sxs-lookup"><span data-stu-id="21eac-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="21eac-253">För anpassade behörigheter ska du inte ange både parametrarna _PermissionToRelease_ och _PermissionToRequestRelease._ `$true`</span><span class="sxs-lookup"><span data-stu-id="21eac-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="21eac-254">Ange en till `$true` och lämna den andra `$false` som, eller lämna båda `$false` som.</span><span class="sxs-lookup"><span data-stu-id="21eac-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="21eac-255">Du kan också ändra en befintlig objektvariabel för behörigheter när du har skapat den, men innan du använder den med hjälp av cmdleten **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="21eac-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="21eac-256">Detaljerad information om syntax och parametrar finns [i New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) [och Set-QuarantinePermissions.](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="21eac-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="21eac-257">Steg B: Använda variabeln i New-QuarantineTag kommando</span><span class="sxs-lookup"><span data-stu-id="21eac-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="21eac-258">När du har skapat och lagrat behörighetsobjektet i en variabel använder du variabeln för parametervärdet _EndUserQuarantinePermission_ i **följande** kommando för karantäntag:</span><span class="sxs-lookup"><span data-stu-id="21eac-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="21eac-259">I det här exemplet skapas en ny karantäntagg med namnet LimitedAccess med `$LimitedAccess` behörighetsobjektet som beskrevs och skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="21eac-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="21eac-260">Detaljerad information om syntax och parametrar finns [i New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="21eac-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="21eac-261">Steg 2: Tilldela en karantäntagg till funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="21eac-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="21eac-262">I _skyddsfunktioner_ som stöds som sätt meddelanden eller filer i karantän (automatiskt eller som en konfigurerbar åtgärd) kan du tilldela en karantäntagg till de tillgängliga karantänåtgärderna.</span><span class="sxs-lookup"><span data-stu-id="21eac-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="21eac-263">Funktioner som sätt meddelanden i karantän och tillgängligheten för karantäntaggar beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="21eac-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="21eac-264">Funktion</span><span class="sxs-lookup"><span data-stu-id="21eac-264">Feature</span></span>|<span data-ttu-id="21eac-265">Stöds karantäntaggar?</span><span class="sxs-lookup"><span data-stu-id="21eac-265">Quarantine tags supported?</span></span>|<span data-ttu-id="21eac-266">Standardtaggar för karantän som används</span><span class="sxs-lookup"><span data-stu-id="21eac-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="21eac-267">[Principer för skydd mot skräppost:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="21eac-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="21eac-268">**Spam** _(SpamAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="21eac-269">**Skräppost med högt förtroende** _(HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="21eac-270">**Nätfiskemeddelande** _(PhishSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="21eac-271">**Nätfiske med högt förtroende** _(HighConfidencePhishAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="21eac-272">**Massutskick** _(BulkSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="21eac-273">Ja</span><span class="sxs-lookup"><span data-stu-id="21eac-273">Yes</span></span>|<ul><li><span data-ttu-id="21eac-274">DefaultSpamTag (Fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="21eac-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="21eac-275">DefaultHighConfSpamTag (Fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="21eac-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="21eac-276">DefaultPhishTag (Fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="21eac-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="21eac-277">DefaultHighConfPhishTag (ingen åtkomst)</span><span class="sxs-lookup"><span data-stu-id="21eac-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="21eac-278">DefaultBulkTag (fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="21eac-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="21eac-279">Principer mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="21eac-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="21eac-280">[Spoof Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) _(AuthenticationFailAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="21eac-281">[Personifieringsskydd:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="21eac-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="21eac-282">**Om e-post skickas av en imiterad användare** _(TargetedUserProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="21eac-283">**Om e-post skickas med en imiterad domän** _(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="21eac-284">**Postlådeinformation** \> **Om e-post skickas av en imiterad användare** _(MailboxIntelligenceProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="21eac-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="21eac-285">Nej</span><span class="sxs-lookup"><span data-stu-id="21eac-285">No</span></span>|<span data-ttu-id="21eac-286">ej a</span><span class="sxs-lookup"><span data-stu-id="21eac-286">n/a</span></span>|
|<span data-ttu-id="21eac-287">[Principer för skydd mot skadlig](configure-anti-malware-policies.md)programvara: Alla identifierade meddelanden sätts alltid i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="21eac-288">Nej</span><span class="sxs-lookup"><span data-stu-id="21eac-288">No</span></span>|<span data-ttu-id="21eac-289">ej a</span><span class="sxs-lookup"><span data-stu-id="21eac-289">n/a</span></span>|
|[<span data-ttu-id="21eac-290">Säkra bilagor för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21eac-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="21eac-291">Nej</span><span class="sxs-lookup"><span data-stu-id="21eac-291">No</span></span>|<span data-ttu-id="21eac-292">ej a</span><span class="sxs-lookup"><span data-stu-id="21eac-292">n/a</span></span>|
|<span data-ttu-id="21eac-293">[E-postflödesregler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) med åtgärden: Leverera meddelandet till **den värdinde karantänen** _(karantän)._</span><span class="sxs-lookup"><span data-stu-id="21eac-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="21eac-294">Nej</span><span class="sxs-lookup"><span data-stu-id="21eac-294">No</span></span>|<span data-ttu-id="21eac-295">ej a</span><span class="sxs-lookup"><span data-stu-id="21eac-295">n/a</span></span>|
|

<span data-ttu-id="21eac-296"><sup>\*</sup> Inställningar för personifieringsskydd är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="21eac-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="21eac-297">Om du är nöjd med slutanvändarbehörigheterna som anges av standardtaggarna för karantän behöver du inte göra något.</span><span class="sxs-lookup"><span data-stu-id="21eac-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="21eac-298">Om du vill anpassa slutanvändarfunktionerna (tillgängliga knappar) i skräppost-aviseringar för slutanvändare eller i information i karantän kan du tilldela en anpassad karantäntagg.</span><span class="sxs-lookup"><span data-stu-id="21eac-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="21eac-299">Tilldela karantäntaggar i principer för skydd mot skräppost i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="21eac-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="21eac-300">Fullständiga instruktioner för hur du skapar och ändrar principer för skydd mot skräppost beskrivs i [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="21eac-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="21eac-301">I Säkerhets- & Efterlevnadscenter går du till **Policy för** hantering \> **av** hot och väljer \> sedan **Skräppostskydd.**</span><span class="sxs-lookup"><span data-stu-id="21eac-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="21eac-302">Eller <https://protection.office.com/antispam> öppna.</span><span class="sxs-lookup"><span data-stu-id="21eac-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="21eac-303">Hitta och välj en befintlig policy för skydd mot skräppost om du vill redigera eller skapa en ny policy för skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="21eac-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="21eac-304">Expandera avsnittet Skräppost- och massåtgärder i den **utfällande policyinformationen.**</span><span class="sxs-lookup"><span data-stu-id="21eac-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="21eac-305">Om du har  valt karantänmeddelande för åtgärden av en  tillgänglig skräppostfiltrering som avgörs är rutan Använd karantänprinciptagg tillgänglig så att du kan välja karantäntaggen för den aktuella bedömningspolicyn.</span><span class="sxs-lookup"><span data-stu-id="21eac-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="21eac-306">**Obs!** När du skapar en ny princip visar en tom karantäntagg för en skräppostfiltrering vilken karantäntagg som används som standard för den bedömning som ska användas.</span><span class="sxs-lookup"><span data-stu-id="21eac-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="21eac-307">När du senare redigerar principen ersätts de tomma värdena med de faktiska namnen på karantäntaggarna enligt beskrivningen i föregående tabell.</span><span class="sxs-lookup"><span data-stu-id="21eac-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Sätt taggar i karantän i en princip mot skräppost](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="21eac-309">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="21eac-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="21eac-310">Tilldela karantäntaggar i principer för skydd mot skräppost i PowerShell</span><span class="sxs-lookup"><span data-stu-id="21eac-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="21eac-311">Om du hellre vill använda PowerShell för att tilldela karantäntaggar i principer mot skräppost ska du ansluta till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="21eac-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="21eac-312">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="21eac-312">**Notes**:</span></span>

- <span data-ttu-id="21eac-313">Standardvärdet för parametern _HighConfidencePhishAction_ är karantän, så du behöver inte ange åtgärder för karantän för identifiering av nätfiske med hög konfidens i de nya principerna för skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="21eac-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="21eac-314">För alla andra skräppostfiltreringsutskick i nya eller befintliga principer för skydd mot skräppost är karantäntaggen bara effektiv om åtgärdsvärdet är Karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="21eac-315">Om du vill se åtgärdsvärdena i befintliga principer för skydd mot skräppost kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="21eac-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="21eac-316">Mer information om standardåtgärdsvärdena och de rekommenderade åtgärdsvärdena för Standard och Strikt finns i [principinställningarna för EOP-skydd mot skräppost.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="21eac-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="21eac-317">En skräppostfiltrering som skulle vara utan en motsvarande karantäntaggsparameter innebär att [standardtaggen](#step-2-assign-a-quarantine-tag-to-supported-features) för karantänen används för den aktuella aktuella frågan.</span><span class="sxs-lookup"><span data-stu-id="21eac-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="21eac-318">Du behöver bara ersätta en standardtagg för karantän med en anpassad karantäntagg om du vill ändra standardkapaciteten för slutanvändare för meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="21eac-319">En ny policy mot skräppost i PowerShell kräver en princip för skräppostfilter (inställningar) med cmdleten **New-HostedContentFilterPolicy** och en ny skräppostfilterregel (mottagarfilter) med cmdleten **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="21eac-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="21eac-320">Instruktioner finns i Använda [PowerShell för att skapa principer för skydd mot skräppost.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="21eac-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="21eac-321">I det här exemplet skapas en ny policy för skräppostfilter med namnet Research Department med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="21eac-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="21eac-322">Åtgärden för all skräppostfiltrering är inställd på karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="21eac-323">Den anpassade karantäntaggen NoAccess som tilldelar **inga** åtkomstbehörigheter ersätter alla standardtaggar i karantän som inte redan tilldelar **Inga åtkomstbehörigheter** som standard.</span><span class="sxs-lookup"><span data-stu-id="21eac-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="21eac-324">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="21eac-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="21eac-325">I det här exemplet ändras den befintliga policyn för skräppostfilter med namnet Human Resources.</span><span class="sxs-lookup"><span data-stu-id="21eac-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="21eac-326">Åtgärden för karantänen för skräppost är inställd på karantän och den anpassade karantäntaggen NoAccess tilldelas.</span><span class="sxs-lookup"><span data-stu-id="21eac-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="21eac-327">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="21eac-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="21eac-328">Konfigurera meddelandeinställningar för global karantän i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="21eac-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="21eac-329">Med de globala inställningarna för karantäntaggar kan du anpassa skräppost-aviseringarna för slutanvändaren som skickas till mottagare av meddelanden som har satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="21eac-330">Mer information om dessa meddelanden finns i [skräppost-aviseringarna för slutanvändaren.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="21eac-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="21eac-331">Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="21eac-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="21eac-332">Välj Globala **inställningar på** sidan **karantäntaggar.**</span><span class="sxs-lookup"><span data-stu-id="21eac-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="21eac-333">I **meddelandeinställningarna för karantän** som öppnas konfigurerar du några eller alla av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="21eac-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="21eac-334">**Använd mitt företags logotyp:** Välj det här alternativet om du vill ersätta standardlogotypen för Microsoft som används högst upp i skräppost-aviseringarna för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="21eac-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="21eac-335">Innan du gör det måste du följa instruktionerna i Anpassa [Microsoft 365-temat](../../admin/setup/customize-your-organization-theme.md) för din organisation för att ladda upp din anpassade logotyp.</span><span class="sxs-lookup"><span data-stu-id="21eac-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="21eac-336">Följande skärmbild visar en anpassad logotyp i en skräppost-avisering för slutanvändaren:</span><span class="sxs-lookup"><span data-stu-id="21eac-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![En anpassad logotyp i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="21eac-338">**Välj språk:** Skräppost-aviseringar för slutanvändare har redan lokaliserats baserat på mottagarens språkinställningar.</span><span class="sxs-lookup"><span data-stu-id="21eac-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="21eac-339">Du kan ange anpassad text på olika språk för **värdena visningsnamn och** **ansvarsfriskrivning.**</span><span class="sxs-lookup"><span data-stu-id="21eac-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="21eac-340">Välj minst ett språk i den första språkrutan och klicka sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="21eac-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="21eac-341">Du kan välja flera språk genom att klicka **på Lägg till** efter varje.</span><span class="sxs-lookup"><span data-stu-id="21eac-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="21eac-342">I rutan för avsnittsspråk visas alla språk som du har valt:</span><span class="sxs-lookup"><span data-stu-id="21eac-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Valda språk i rutan för det andra språket i meddelandeinställningarna för global karantän för karantäntaggar](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="21eac-344">**Visningsnamn:** Anpassa avsändarens visningsnamn som används i skräppost-aviseringar för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="21eac-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="21eac-345">För varje språk som du har lagt till väljer du språket i den andra språkrutan (klicka inte på X) och ange det textvärde du vill ha i rutan **Visningsnamn.**</span><span class="sxs-lookup"><span data-stu-id="21eac-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="21eac-346">Följande skärmbild visar det anpassade visningsnamnet i ett skräppost-meddelande för slutanvändaren:</span><span class="sxs-lookup"><span data-stu-id="21eac-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Ett anpassat avsändarvisningsnamn i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="21eac-348">**Ansvarsfriskrivning:** Lägg till en anpassad ansvarsfriskrivning längst ned i skräppost-aviseringar för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="21eac-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="21eac-349">Lokaliserad text, **en ansvarsfriskrivning från din organisation:** inkluderas alltid först, följt av den text du anger.</span><span class="sxs-lookup"><span data-stu-id="21eac-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="21eac-350">För varje språk som du har lagt till väljer du språket i den andra språkrutan (klicka inte på X) och ange det textvärde du vill ha i rutan **Ansvarsfriskrivning.**</span><span class="sxs-lookup"><span data-stu-id="21eac-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="21eac-351">På följande skärmbild visas den anpassade ansvarsfriskrivningen i en skräppost-avisering för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="21eac-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![En anpassad ansvarsfriskrivning längst ned i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="21eac-353">Visa karantäntaggar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="21eac-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="21eac-354">Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="21eac-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="21eac-355">Om du vill visa inställningarna för inbyggda eller anpassade karantäntaggar väljer du karantäntaggen i listan (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="21eac-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="21eac-356">Om du vill visa de globala inställningarna väljer **du Globala inställningar**</span><span class="sxs-lookup"><span data-stu-id="21eac-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="21eac-357">Visa karantäntaggar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="21eac-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="21eac-358">Om du hellre vill använda PowerShell för att visa karantäntaggar gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="21eac-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="21eac-359">Om du vill visa en sammanfattningslista över alla inbyggda eller anpassade taggar kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="21eac-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="21eac-360">Om du vill visa inställningarna för inbyggda eller anpassade karantäntaggar ersätter du med namnet på \<TagName\> karantäntaggen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="21eac-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="21eac-361">Om du vill visa de globala inställningarna kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="21eac-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="21eac-362">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="21eac-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="21eac-363">Ta bort karantäntaggar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="21eac-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="21eac-364">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="21eac-364">**Notes**:</span></span>

- <span data-ttu-id="21eac-365">Du kan inte ta bort inbyggda karantäntaggar.</span><span class="sxs-lookup"><span data-stu-id="21eac-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="21eac-366">Innan du tar bort en anpassad karantäntagg kontrollerar du att den inte används.</span><span class="sxs-lookup"><span data-stu-id="21eac-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="21eac-367">Kör till exempel följande kommando i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21eac-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="21eac-368">Om karantäntaggen används ersätter du [den tilldelade karantäntaggen](#step-2-assign-a-quarantine-tag-to-supported-features) innan du tar bort den.</span><span class="sxs-lookup"><span data-stu-id="21eac-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="21eac-369">Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="21eac-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="21eac-370">På sidan **Karantän-taggar** väljer du den anpassade karantäntagg du vill ta bort och klickar på Ta **bort taggen.**</span><span class="sxs-lookup"><span data-stu-id="21eac-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="21eac-371">Klicka **på Ta bort** tagg i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="21eac-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="21eac-372">Ta bort karantäntaggar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="21eac-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="21eac-373">Om du hellre vill använda PowerShell för att ta bort en anpassad karantäntagg ersätter du med namnet på karantänstaggen \<TagName\> och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="21eac-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="21eac-374">Detaljerad information om syntax och parametrar finns i [Ta bort karantän.](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="21eac-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="21eac-375">Information om taggbehörighet i karantän</span><span class="sxs-lookup"><span data-stu-id="21eac-375">Quarantine tag permission details</span></span>

<span data-ttu-id="21eac-376">I följande avsnitt beskrivs effekterna av förinställda behörighetsgrupper och enskilda behörigheter i information om meddelanden i karantän och i skräppost-aviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="21eac-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="21eac-377">Förinställda behörighetsgrupper</span><span class="sxs-lookup"><span data-stu-id="21eac-377">Preset permissions groups</span></span>

<span data-ttu-id="21eac-378">De enskilda behörigheterna som ingår i förinställda behörighetsgrupper visas i tabellen i början av den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21eac-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="21eac-379">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-379">No access</span></span>

<span data-ttu-id="21eac-380">Om karantäntaggen tilldelar **inga åtkomstbehörigheter** (inga behörigheter) får användarna fortfarande vissa grundläggande funktioner:</span><span class="sxs-lookup"><span data-stu-id="21eac-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="21eac-381">**Information om meddelande i karantän:** **Knappen Visa meddelanderubrik** är alltid tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="21eac-383">**Skräppost-aviseringar för slutanvändare:** **Knappen** Granska som tar användaren till meddelandet i karantän är alltid tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="21eac-385">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-385">Limited access</span></span>

<span data-ttu-id="21eac-386">Om karantäntaggen tilldelar **behörigheterna** begränsad åtkomst får användarna följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="21eac-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="21eac-387">**Meddelandeinformation i karantän:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="21eac-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="21eac-388">**Begär version**</span><span class="sxs-lookup"><span data-stu-id="21eac-388">**Request release**</span></span>
  - <span data-ttu-id="21eac-389">**Visa meddelanderubrik**</span><span class="sxs-lookup"><span data-stu-id="21eac-389">**View message header**</span></span>
  - <span data-ttu-id="21eac-390">**Förhandsgranskningsmeddelande**</span><span class="sxs-lookup"><span data-stu-id="21eac-390">**Preview message**</span></span>
  - <span data-ttu-id="21eac-391">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-391">**Block sender**</span></span>
  - <span data-ttu-id="21eac-392">**Ta bort från karantän**</span><span class="sxs-lookup"><span data-stu-id="21eac-392">**Remove from quarantine**</span></span>

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="21eac-394">**Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="21eac-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="21eac-395">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-395">**Block sender**</span></span>
  - <span data-ttu-id="21eac-396">**Granska**</span><span class="sxs-lookup"><span data-stu-id="21eac-396">**Review**</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="21eac-398">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="21eac-398">Full access</span></span>

<span data-ttu-id="21eac-399">Om karantäntaggen tilldelar **fullständig behörighet** (alla tillgängliga behörigheter) får användarna följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="21eac-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="21eac-400">**Meddelandeinformation i karantän:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="21eac-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="21eac-401">**Utgivningsmeddelande**</span><span class="sxs-lookup"><span data-stu-id="21eac-401">**Release message**</span></span>
  - <span data-ttu-id="21eac-402">**Visa meddelanderubrik**</span><span class="sxs-lookup"><span data-stu-id="21eac-402">**View message header**</span></span>
  - <span data-ttu-id="21eac-403">**Förhandsgranskningsmeddelande**</span><span class="sxs-lookup"><span data-stu-id="21eac-403">**Preview message**</span></span>
  - <span data-ttu-id="21eac-404">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-404">**Block sender**</span></span>
  - <span data-ttu-id="21eac-405">**Tillåt avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-405">**Allow sender**</span></span>
  - <span data-ttu-id="21eac-406">**Ta bort från karantän**</span><span class="sxs-lookup"><span data-stu-id="21eac-406">**Remove from quarantine**</span></span>

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren fullständig åtkomst](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="21eac-408">**Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="21eac-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="21eac-409">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="21eac-409">**Block sender**</span></span>
  - <span data-ttu-id="21eac-410">**Version**</span><span class="sxs-lookup"><span data-stu-id="21eac-410">**Release**</span></span>
  - <span data-ttu-id="21eac-411">**Granska**</span><span class="sxs-lookup"><span data-stu-id="21eac-411">**Review**</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren fullständig åtkomst](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="21eac-413">Enskilda behörigheter</span><span class="sxs-lookup"><span data-stu-id="21eac-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="21eac-414">Kom ihåg att användarna alltid får knapparna som beskrivs i [avsnittet Ingen](#no-access) åtkomst.</span><span class="sxs-lookup"><span data-stu-id="21eac-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="21eac-415">Dessa knappar ingår inte i de enskilda behörighetsbeskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="21eac-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="21eac-416">Tillåt avsändarbehörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-416">Allow sender permission</span></span>

<span data-ttu-id="21eac-417">Tillåt **avsändarbehörighet** _(PermissionToAllowSender)_ styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän i sin lista med betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="21eac-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="21eac-418">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-419">**Tillåt att avsändarens** behörighet är **aktiverad: Knappen Tillåt** avsändare är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="21eac-420">**Tillåt avsändarbehörighet** inaktiverad: **Knappen Tillåt** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="21eac-421">**Skräppost-aviseringar för slutanvändare:** Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="21eac-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="21eac-422">Mer information om listan Betrodda avsändare finns i Förhindra att betrodda avsändare [blockeras](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) och Använda Exchange Online PowerShell för att konfigurera samlingen listor över betrodda avsändare [för en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="21eac-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="21eac-423">Blockera avsändarbehörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-423">Block sender permission</span></span>

<span data-ttu-id="21eac-424">Behörigheten **Blockera avsändare** _(PermissionToBlockSender)_ styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän i listan Spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="21eac-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="21eac-425">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-426">**Behörigheten** Blockera avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="21eac-427">**Spärra avsändarbehörighet** inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="21eac-428">**Skräppost-aviseringar för slutanvändare:**</span><span class="sxs-lookup"><span data-stu-id="21eac-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="21eac-429">**Spärra avsändarbehörighet** inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="21eac-430">**Behörigheten** Blockera avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="21eac-431">Mer information om listan Spärrade avsändare [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) finns i Spärra meddelanden från någon och Använda Exchange Online PowerShell för att konfigurera samlingen med listor över betrodda avsändare [för en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="21eac-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="21eac-432">Ta bort behörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-432">Delete permission</span></span>

<span data-ttu-id="21eac-433">Behörigheten **Ta** bort _(PermissionToDelete)_ styr möjligheten för användare att ta bort sina meddelanden (meddelanden där användaren är mottagare) från karantän.</span><span class="sxs-lookup"><span data-stu-id="21eac-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="21eac-434">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-435">**Ta** bort behörighet aktiverad: **Knappen Ta bort från** karantän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="21eac-436">**Ta** bort behörighet inaktiverad: **Knappen Ta bort från** karantän är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="21eac-437">**Skräppost-aviseringar för slutanvändare:** Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="21eac-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="21eac-438">Förhandsgranskningsbehörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-438">Preview permission</span></span>

<span data-ttu-id="21eac-439">_Förhandsgranskningsbehörigheten (PermissionToPreview)_ styr möjligheten för användare att förhandsgranska sina meddelanden i karantän. </span><span class="sxs-lookup"><span data-stu-id="21eac-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="21eac-440">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-441">**Behörighet** för förhandsgranskning aktiverad: **Knappen Förhandsgranskningsmeddelande** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="21eac-442">**Förhandsgranskningsbehörighet** inaktiverad: **Knappen Förhandsgranskningsmeddelande** är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="21eac-443">**Skräppost-aviseringar för slutanvändare:** Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="21eac-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="21eac-444">Tillåt mottagare att släppa ett meddelande från karantän-behörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="21eac-445">Allow **recipients to release a message from quarantine** permission _(PermissionToRelease)_ controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span><span class="sxs-lookup"><span data-stu-id="21eac-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="21eac-446">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-447">Behörighet aktiverad: Knappen **Släpp meddelande** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="21eac-448">Behörighet inaktiverad: **Knappen Släpp meddelande** är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="21eac-449">**Skräppost-aviseringar för slutanvändare:**</span><span class="sxs-lookup"><span data-stu-id="21eac-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="21eac-450">Behörighet aktiverad: **Knappen Släpp** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="21eac-451">Behörighet inaktiverad: **Knappen** Släpp är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="21eac-452">Tillåt mottagare att begära att ett meddelande ska släppas från karantänsbehörighet</span><span class="sxs-lookup"><span data-stu-id="21eac-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="21eac-453">Allow **recipients to request a message to be released from quarantine** permission _(PermissionToRequestRelease) controls_ the ability of users to request the release of their quarantined messages. </span><span class="sxs-lookup"><span data-stu-id="21eac-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="21eac-454">Meddelandet släpps bara när en administratör godkänt begäran.</span><span class="sxs-lookup"><span data-stu-id="21eac-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="21eac-455">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="21eac-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="21eac-456">Behörighet aktiverad: **Knappen Begär version** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="21eac-457">Behörighet inaktiverad: **Knappen Släpp av** begäran är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="21eac-458">**Skräppost-aviseringar för slutanvändare:** Knappen **Släpp** är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="21eac-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
