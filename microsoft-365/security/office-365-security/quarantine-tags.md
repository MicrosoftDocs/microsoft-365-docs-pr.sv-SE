---
title: Karantänprinciper
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
description: Administratörer kan ta reda på hur de kan använda karantänprinciper för att styra vad användare kan göra med meddelanden i karantän.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055229"
---
# <a name="quarantine-policies"></a><span data-ttu-id="a38e1-103">Karantänprinciper</span><span class="sxs-lookup"><span data-stu-id="a38e1-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="a38e1-104">Funktionerna som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="a38e1-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="a38e1-105">Karantänprinciper (tidigare kallade karantäntaggar) i Exchange Online Protection (EOP) gör det möjligt för administratörer att styra vad användare kan göra med meddelanden i karantän baserat på hur meddelandet kom in i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="a38e1-106">EOP har traditionellt tillåtit eller förhindrat [](find-and-release-quarantined-messages-as-a-user.md) vissa nivåer av interaktivitet för meddelanden i karantän och [i skräppost-aviseringar för slutanvändare.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a38e1-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="a38e1-107">Användare kan till exempel visa och släppa meddelanden som satts i karantän genom skräppostfiltrering som skräppost eller massutskick, men de kan inte visa eller släppa meddelanden som har satts i karantän som nätfiske (endast administratörer kan göra det).</span><span class="sxs-lookup"><span data-stu-id="a38e1-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="a38e1-108">För [funktioner som stöds](#step-2-assign-a-quarantine-policy-to-supported-features)anger karantänprinciper vad användare tillåts göra i skräppost-aviseringar för slutanvändare och i deras meddelanden i karantän (meddelanden där användaren är mottagare).</span><span class="sxs-lookup"><span data-stu-id="a38e1-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="a38e1-109">Standardprinciper för karantän tilldelas automatiskt för att tillämpa de historiska funktionerna för användare i karantänmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a38e1-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="a38e1-110">Du kan också skapa och tilldela anpassade karantänprinciper för att tillåta eller förhindra att slutanvändare utför specifika åtgärder på meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="a38e1-111">De enskilda behörigheterna kombineras i följande förinställda behörighetsgrupper:</span><span class="sxs-lookup"><span data-stu-id="a38e1-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="a38e1-112">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-112">No access</span></span>
- <span data-ttu-id="a38e1-113">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-113">Limited access</span></span>
- <span data-ttu-id="a38e1-114">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-114">Full access</span></span>

<span data-ttu-id="a38e1-115">De tillgängliga enskilda behörigheterna och vad som ingår eller inte ingår i de förinställda behörighetsgrupperna beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a38e1-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="a38e1-116">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-116">Permission</span></span>|<span data-ttu-id="a38e1-117">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-117">No access</span></span>|<span data-ttu-id="a38e1-118">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-118">Limited access</span></span>|<span data-ttu-id="a38e1-119">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="a38e1-120">**Tillåt avsändare** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="a38e1-122">**Spärra avsändare** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="a38e1-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-125">**Delete** (_PermissionToDelete_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="a38e1-128">**Preview** _(PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-128">**Preview** (_PermissionToPreview_)</span></span>||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="a38e1-131">**Tillåt mottagare att släppa ett meddelande från karantän** _(PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="a38e1-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="a38e1-133">**Tillåt mottagare att begära att ett meddelande ska släppas från karantän** _(PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Bockmarkering](../../media/checkmark.png)||
|

<span data-ttu-id="a38e1-135">Om du inte gillar standardbehörigheterna i de förinställda behörighetsgrupperna kan du använda anpassade behörigheter när du skapar eller ändrar anpassade karantänprinciper.</span><span class="sxs-lookup"><span data-stu-id="a38e1-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="a38e1-136">Mer information om vad varje behörighet gör finns i avsnittet Behörighetsinformation [för karantänprinciper](#quarantine-policy-permission-details) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="a38e1-137">Du skapar och tilldelar karantänprinciper i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med Exchange Online-postlådor; fristående EOP PowerShell i EOP-organisationer utan Exchange Online postlådor).</span><span class="sxs-lookup"><span data-stu-id="a38e1-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a38e1-138">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a38e1-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a38e1-139">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a38e1-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a38e1-140">Om du vill gå direkt till **sidan Karantänprinciper** öppnar du <https://security.microsoft.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="a38e1-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="a38e1-141">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a38e1-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a38e1-142">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a38e1-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a38e1-143">Om du vill visa, skapa, ändra eller ta bort  karantänprinciper måste du vara medlem i rollerna Organisationshantering eller **Säkerhetsadministratör** i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="a38e1-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="a38e1-144">Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="a38e1-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-145">Steg 1: Skapa karantänprinciper i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="a38e1-146">I Microsoft 365 Defender-portalen går du till **E-& för samarbete** – hotregler. Sätt principer för karantän \>  \>  och välj \>  sedan **karantänprinciper.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="a38e1-147">På sidan **Karantänprincip klickar** du på Lägg ![ till anpassad princip-ikon ](../../media/m365-cc-sc-create-icon.png) **Lägg till anpassad princip.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="a38e1-148">Guiden **Ny princip** öppnas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="a38e1-149">På sidan **Principnamn** anger du ett kort men unikt namn i **rutan Principnamn.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="a38e1-150">Du måste identifiera och välja karantänprincipen efter namn i kommande steg.</span><span class="sxs-lookup"><span data-stu-id="a38e1-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="a38e1-151">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a38e1-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a38e1-152">Välj **något av följande** värden på sidan Åtkomst till mottagarmeddelande:</span><span class="sxs-lookup"><span data-stu-id="a38e1-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="a38e1-153">**Ingen åtkomst**</span><span class="sxs-lookup"><span data-stu-id="a38e1-153">**No access**</span></span>
   - <span data-ttu-id="a38e1-154">**Begränsad åtkomst**</span><span class="sxs-lookup"><span data-stu-id="a38e1-154">**Limited access**</span></span>
   - <span data-ttu-id="a38e1-155">**Fullständig åtkomst**</span><span class="sxs-lookup"><span data-stu-id="a38e1-155">**Full access**</span></span>

   <span data-ttu-id="a38e1-156">De enskilda behörigheterna som ingår i behörighetsgrupperna beskrivs tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="a38e1-157">Om du vill ange anpassade behörigheter **väljer du Ange specifik åtkomst (Avancerat)** och konfigurerar följande inställningar som visas:</span><span class="sxs-lookup"><span data-stu-id="a38e1-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="a38e1-158">**Välj inställning för släppåtgärd:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="a38e1-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="a38e1-159">**Ingen utgivningsåtgärd:** Det här är standardvärdet.</span><span class="sxs-lookup"><span data-stu-id="a38e1-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="a38e1-160">**Tillåt mottagare att släppa ett meddelande från karantän**</span><span class="sxs-lookup"><span data-stu-id="a38e1-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="a38e1-161">**Tillåt mottagare att begära att ett meddelande ska släppas från karantän**</span><span class="sxs-lookup"><span data-stu-id="a38e1-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="a38e1-162">**Välj ytterligare åtgärder som mottagare kan utföra för meddelanden** i karantän: Välj några, alla eller inga av följande värden:</span><span class="sxs-lookup"><span data-stu-id="a38e1-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="a38e1-163">**Radera**</span><span class="sxs-lookup"><span data-stu-id="a38e1-163">**Delete**</span></span>
       - <span data-ttu-id="a38e1-164">**Förhandsgranska**</span><span class="sxs-lookup"><span data-stu-id="a38e1-164">**Preview**</span></span>
       - <span data-ttu-id="a38e1-165">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-165">**Block sender**</span></span>

   <span data-ttu-id="a38e1-166">De här behörigheterna och deras påverkan på meddelanden i karantän [](#quarantine-policy-permission-details) och i skräppost-aviseringar för slutanvändare beskrivs i avsnittet Om karantänprinciper senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="a38e1-167">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a38e1-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a38e1-168">Granska **inställningarna på** sidan Granska princip som visas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="a38e1-169">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a38e1-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="a38e1-170">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="a38e1-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="a38e1-171">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="a38e1-172">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="a38e1-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="a38e1-173">Nu är du redo att tilldela karantänprincipen till en karantänfunktion enligt beskrivningen i [avsnittet Steg 2.](#step-2-assign-a-quarantine-policy-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="a38e1-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="a38e1-174">Skapa karantänprinciper i PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e1-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="a38e1-175">Om du hellre vill använda PowerShell för att skapa karantänprinciper ska du ansluta till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använda cmdleten **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="a38e1-176">Du har två olika metoder att välja bland:</span><span class="sxs-lookup"><span data-stu-id="a38e1-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="a38e1-177">Använd _parametern EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="a38e1-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="a38e1-178">Använd _parametern EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="a38e1-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="a38e1-179">De här metoderna beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="a38e1-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="a38e1-180">Använda parametern EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="a38e1-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="a38e1-181">Om du vill skapa en karantänprincip _med hjälp av parametern EndUserQuarantinePermissionsValue_ ska du använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a38e1-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="a38e1-182">Parametern _EndUserQuarantinePermissionsValue_ använder ett decimalvärde som konverteras från ett binärt värde.</span><span class="sxs-lookup"><span data-stu-id="a38e1-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="a38e1-183">Det binära värdet motsvarar de tillgängliga karantänbehörigheterna för slutanvändare i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="a38e1-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="a38e1-184">För varje behörighet är värdet 1 lika med Sant och värdet 0 är falskt.</span><span class="sxs-lookup"><span data-stu-id="a38e1-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="a38e1-185">Den ordning och de värden som krävs för varje enskild behörighet i förinställda behörighetsgrupper beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a38e1-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="a38e1-186">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-186">Permission</span></span>|<span data-ttu-id="a38e1-187">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-187">No access</span></span>|<span data-ttu-id="a38e1-188">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-188">Limited access</span></span>|<span data-ttu-id="a38e1-189">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="a38e1-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="a38e1-190">PermissionToAllowSender</span></span>|<span data-ttu-id="a38e1-191">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-191">0</span></span>|<span data-ttu-id="a38e1-192">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-192">0</span></span>|<span data-ttu-id="a38e1-193">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-193">1</span></span>|
|<span data-ttu-id="a38e1-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="a38e1-194">PermissionToBlockSender</span></span>|<span data-ttu-id="a38e1-195">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-195">0</span></span>|<span data-ttu-id="a38e1-196">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-196">1</span></span>|<span data-ttu-id="a38e1-197">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-197">1</span></span>|
|<span data-ttu-id="a38e1-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="a38e1-198">PermissionToDelete</span></span>|<span data-ttu-id="a38e1-199">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-199">0</span></span>|<span data-ttu-id="a38e1-200">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-200">1</span></span>|<span data-ttu-id="a38e1-201">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-201">1</span></span>|
|<span data-ttu-id="a38e1-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a38e1-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="a38e1-203">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-203">0</span></span>|<span data-ttu-id="a38e1-204">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-204">0</span></span>|<span data-ttu-id="a38e1-205">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-205">0</span></span>|
|<span data-ttu-id="a38e1-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="a38e1-206">PermissionToPreview</span></span>|<span data-ttu-id="a38e1-207">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-207">0</span></span>|<span data-ttu-id="a38e1-208">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-208">1</span></span>|<span data-ttu-id="a38e1-209">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-209">1</span></span>|
|<span data-ttu-id="a38e1-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a38e1-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="a38e1-211">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-211">0</span></span>|<span data-ttu-id="a38e1-212">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-212">0</span></span>|<span data-ttu-id="a38e1-213">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-213">1</span></span>|
|<span data-ttu-id="a38e1-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="a38e1-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="a38e1-215">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-215">0</span></span>|<span data-ttu-id="a38e1-216">1</span><span class="sxs-lookup"><span data-stu-id="a38e1-216">1</span></span>|<span data-ttu-id="a38e1-217">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-217">0</span></span>|
|<span data-ttu-id="a38e1-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a38e1-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="a38e1-219">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-219">0</span></span>|<span data-ttu-id="a38e1-220">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-220">0</span></span>|<span data-ttu-id="a38e1-221">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-221">0</span></span>|
|<span data-ttu-id="a38e1-222">Binärt värde</span><span class="sxs-lookup"><span data-stu-id="a38e1-222">Binary value</span></span>|<span data-ttu-id="a38e1-223">00000000</span><span class="sxs-lookup"><span data-stu-id="a38e1-223">00000000</span></span>|<span data-ttu-id="a38e1-224">01101010</span><span class="sxs-lookup"><span data-stu-id="a38e1-224">01101010</span></span>|<span data-ttu-id="a38e1-225">11101100</span><span class="sxs-lookup"><span data-stu-id="a38e1-225">11101100</span></span>|
|<span data-ttu-id="a38e1-226">Decimalvärde som ska användas</span><span class="sxs-lookup"><span data-stu-id="a38e1-226">Decimal value to use</span></span>|<span data-ttu-id="a38e1-227">0</span><span class="sxs-lookup"><span data-stu-id="a38e1-227">0</span></span>|<span data-ttu-id="a38e1-228">106</span><span class="sxs-lookup"><span data-stu-id="a38e1-228">106</span></span>|<span data-ttu-id="a38e1-229">236</span><span class="sxs-lookup"><span data-stu-id="a38e1-229">236</span></span>|
|

<span data-ttu-id="a38e1-230"><sup>\*</sup> Det här värdet är för närvarande alltid 0.</span><span class="sxs-lookup"><span data-stu-id="a38e1-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="a38e1-231">För PermissionToViewHeader döljer inte värdet 0  knappen Visa meddelanderubrik i informationen om det karantänfördelade meddelandet (knappen är alltid tillgänglig).</span><span class="sxs-lookup"><span data-stu-id="a38e1-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="a38e1-232"><sup>\*\*</sup> Ange inte båda dessa värden till 1.</span><span class="sxs-lookup"><span data-stu-id="a38e1-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="a38e1-233">Ställ in 1 och en annan på 0 eller ange 0 för båda.</span><span class="sxs-lookup"><span data-stu-id="a38e1-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="a38e1-234">I det här exemplet skapas ett nytt namn på karantänprincipen NoAccess som tilldelar behörigheterna Ingen åtkomst enligt beskrivningen i föregående tabell.</span><span class="sxs-lookup"><span data-stu-id="a38e1-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="a38e1-235">För begränsad åtkomstbehörighet använder du värdet 106.</span><span class="sxs-lookup"><span data-stu-id="a38e1-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="a38e1-236">För fullständig åtkomst använder du värdet 236.</span><span class="sxs-lookup"><span data-stu-id="a38e1-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="a38e1-237">För anpassade behörigheter använder du föregående tabell för att få det binära värde som motsvarar de behörigheter du vill ha.</span><span class="sxs-lookup"><span data-stu-id="a38e1-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="a38e1-238">Konvertera det binära värdet till ett decimalvärde och använd decimalvärdet för parametern _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="a38e1-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="a38e1-239">Detaljerad information om syntax och parametrar finns i [Ny karantäntagg.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="a38e1-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="a38e1-240">Använda parametern EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="a38e1-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="a38e1-241">Så här skapar du en karantänprincip med hjälp av parametern _EndUserQuarantinePermissionsValue:_</span><span class="sxs-lookup"><span data-stu-id="a38e1-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="a38e1-242">A.</span><span class="sxs-lookup"><span data-stu-id="a38e1-242">A.</span></span> <span data-ttu-id="a38e1-243">Lagra ett objekt med karantänbehörigheter i en variabel med cmdleten **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="a38e1-244">B.</span><span class="sxs-lookup"><span data-stu-id="a38e1-244">B.</span></span> <span data-ttu-id="a38e1-245">Använd variabeln som _värdet EndUserQuarantinePermissions_ i **kommandot Ny karantäntag.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="a38e1-246">Steg A: Lagra ett behörighetsobjekt i karantän för en variabel</span><span class="sxs-lookup"><span data-stu-id="a38e1-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="a38e1-247">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a38e1-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="a38e1-248">Standardvärdet för oanvända parametrar `$false` är , så du behöver bara använda parametrarna där du vill ange värdet till `$true` .</span><span class="sxs-lookup"><span data-stu-id="a38e1-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="a38e1-249">Följande exempel visar hur du skapar behörighetsobjekt som motsvarar de förinställda behörighetsgrupperna:</span><span class="sxs-lookup"><span data-stu-id="a38e1-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="a38e1-250">**Ingen åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="a38e1-251">**Begränsad åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="a38e1-252">**Fullständig åtkomst:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="a38e1-253">Om du vill se de värden du har angett kör du variabelnamnet som ett kommando (kör till exempel kommandot `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="a38e1-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="a38e1-254">För anpassade behörigheter ska du inte ange både parametrarna _PermissionToRelease och_ _PermissionToRequestRelease_ till `$true` .</span><span class="sxs-lookup"><span data-stu-id="a38e1-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="a38e1-255">Ange en till `$true` och lämna den andra som , eller lämna båda som `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="a38e1-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="a38e1-256">Du kan också ändra en befintlig objektvariabel för behörigheter när du har skapat men innan du använder den med hjälp av cmdleten **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="a38e1-257">Detaljerad information om syntax och parametrar finns [i New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) och [Set-QuarantinePermissions.](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="a38e1-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="a38e1-258">Steg B: Använda variabeln i New-QuarantineTag kommando</span><span class="sxs-lookup"><span data-stu-id="a38e1-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="a38e1-259">När du har skapat och lagrat behörighetsobjektet i en variabel använder du variabeln för parametervärdet _EndUserQuarantinePermission_ i följande **New-QuarantineTag-kommando:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="a38e1-260">I det här exemplet skapas en ny karantänprincip med namnet LimitedAccess med `$LimitedAccess` behörighetsobjektet som beskrevs och skapades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="a38e1-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="a38e1-261">Detaljerad information om syntax och parametrar finns i [Ny karantäntagg.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="a38e1-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="a38e1-262">Steg 2: Tilldela en karantänprincip till funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="a38e1-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="a38e1-263">I _skyddsfunktioner_ som stöds och som sätt meddelanden eller filer i karantän (automatiskt eller som en konfigurerbar åtgärd) kan du tilldela en karantänprincip till de tillgängliga karantänåtgärderna.</span><span class="sxs-lookup"><span data-stu-id="a38e1-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="a38e1-264">Funktioner som sätt meddelanden i karantän och tillgängligheten till karantänprinciper beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a38e1-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="a38e1-265">Funktion</span><span class="sxs-lookup"><span data-stu-id="a38e1-265">Feature</span></span>|<span data-ttu-id="a38e1-266">Karantänprinciper som stöds?</span><span class="sxs-lookup"><span data-stu-id="a38e1-266">Quarantine policies supported?</span></span>|<span data-ttu-id="a38e1-267">Standardprinciper för karantän som används</span><span class="sxs-lookup"><span data-stu-id="a38e1-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="a38e1-268">[Principer för skydd mot skräppost:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a38e1-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="a38e1-269">**Spam** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="a38e1-270">**Skräppost med hög konfidens** _(HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="a38e1-271">**Nätfiske** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="a38e1-272">**Nätfiske med** hög konfidens (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="a38e1-273">**Bulk** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="a38e1-274">Ja</span><span class="sxs-lookup"><span data-stu-id="a38e1-274">Yes</span></span>|<ul><li><span data-ttu-id="a38e1-275">DefaultSpamTag (fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a38e1-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="a38e1-276">DefaultHighConfSpamTag (fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a38e1-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="a38e1-277">DefaultPhishTag (fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a38e1-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="a38e1-278">DefaultHighConfPhishTag (ingen åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a38e1-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="a38e1-279">DefaultBulkTag (fullständig åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a38e1-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="a38e1-280">Principer mot nätfiske:</span><span class="sxs-lookup"><span data-stu-id="a38e1-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="a38e1-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) _(AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="a38e1-282">[Personifieringsskydd:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a38e1-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="a38e1-283">**Om meddelandet identifieras som en imiterad användare** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="a38e1-284">**Om meddelandet identifieras som en imiterad domän** _(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="a38e1-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="a38e1-285">**Om postlådeinformation identifierar och utger sig för att vara användare** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="a38e1-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="a38e1-286">Nej</span><span class="sxs-lookup"><span data-stu-id="a38e1-286">No</span></span>|<span data-ttu-id="a38e1-287">Ej a</span><span class="sxs-lookup"><span data-stu-id="a38e1-287">n/a</span></span>|
|<span data-ttu-id="a38e1-288">[Principer för skadlig programvara:](configure-anti-malware-policies.md)Alla identifierade meddelanden har alltid satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="a38e1-289">Nej</span><span class="sxs-lookup"><span data-stu-id="a38e1-289">No</span></span>|<span data-ttu-id="a38e1-290">Ej a</span><span class="sxs-lookup"><span data-stu-id="a38e1-290">n/a</span></span>|
|[<span data-ttu-id="a38e1-291">Säkra bilagor för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a38e1-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="a38e1-292">Nej</span><span class="sxs-lookup"><span data-stu-id="a38e1-292">No</span></span>|<span data-ttu-id="a38e1-293">Ej a</span><span class="sxs-lookup"><span data-stu-id="a38e1-293">n/a</span></span>|
|<span data-ttu-id="a38e1-294">[E-postflödesregler](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) med åtgärden: Leverera meddelandet till **den värdinde karantänen** _(karantän)._</span><span class="sxs-lookup"><span data-stu-id="a38e1-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="a38e1-295">Nej</span><span class="sxs-lookup"><span data-stu-id="a38e1-295">No</span></span>|<span data-ttu-id="a38e1-296">Ej a</span><span class="sxs-lookup"><span data-stu-id="a38e1-296">n/a</span></span>|
|

<span data-ttu-id="a38e1-297"><sup>\*</sup>Inställningarna för personifieringsskydd är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="a38e1-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="a38e1-298">Om du är nöjd med de behörigheter för slutanvändare som anges i standardprinciperna för karantän behöver du inte göra något.</span><span class="sxs-lookup"><span data-stu-id="a38e1-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="a38e1-299">Om du vill anpassa slutanvändarfunktionerna (tillgängliga knappar) i skräppost-aviseringar för slutanvändare eller i meddelandeinformation i karantän kan du tilldela en anpassad karantänprincip.</span><span class="sxs-lookup"><span data-stu-id="a38e1-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-300">Tilldela karantänprinciper i principer för skydd mot skräppost i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="a38e1-301">Fullständiga instruktioner för hur du skapar och ändrar principer för skydd mot skräppost beskrivs i Konfigurera principer för skydd [mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a38e1-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="a38e1-302">I Microsoft 365 Defender går du till Principer för **&** \>  \>  \> **e-& e-postsamarbete** i avsnittet Principer för skräppost.</span><span class="sxs-lookup"><span data-stu-id="a38e1-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="a38e1-303">Eller öppna <https://security.microsoft.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="a38e1-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="a38e1-304">Gör **något av följande på** sidan Principer för skydd mot skräppost:</span><span class="sxs-lookup"><span data-stu-id="a38e1-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="a38e1-305">Hitta och välj en befintlig **princip för inkommande** skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="a38e1-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="a38e1-306">Skapa en ny **princip för inkommande** skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="a38e1-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="a38e1-307">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="a38e1-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="a38e1-308">**Redigera befintlig policy för skräppostskydd:** Gå till avsnittet  Åtgärder i den utfällade principinformationen och klicka på **Redigera åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="a38e1-309">**Skapa en ny princip mot skräppost:** I den nya principguiden går du till **sidan** Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a38e1-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="a38e1-310">På **sidan** Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a38e1-310">On the **Actions** page.</span></span> <span data-ttu-id="a38e1-311">Varje bedömning som har **åtgärden Karantänmeddelande** kommer också att ha rutan Välj **karantänprincip** där du kan välja en motsvarande karantänprincip.</span><span class="sxs-lookup"><span data-stu-id="a38e1-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="a38e1-312">**Obs!** När du skapar en ny princip anger ett tomt värde för **Välj** karantänprincip att standardprincipen för karantänen för den här bedömningsplatsen används.</span><span class="sxs-lookup"><span data-stu-id="a38e1-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="a38e1-313">När du senare redigerar principen ersätts de tomma värdena med de faktiska standardnamnen för karantänprinciper enligt beskrivningen i föregående tabell.</span><span class="sxs-lookup"><span data-stu-id="a38e1-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![Val av karantänprincip i en princip mot skräppost](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="a38e1-315">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a38e1-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="a38e1-316">Tilldela karantänprinciper i principer för skydd mot skräppost i PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e1-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="a38e1-317">Om du hellre vill använda PowerShell för att tilldela karantänprinciper i principer mot skräppost ska du ansluta till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a38e1-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="a38e1-318">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="a38e1-318">**Notes**:</span></span>

- <span data-ttu-id="a38e1-319">Standardvärdet för parametern _HighConfidencePhishAction_ är Karantän, så du behöver inte ange åtgärder för karantän för identifiering av nätfiske med hög säkerhet i nya principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="a38e1-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="a38e1-320">För alla andra skräppostfiltreringsprinciper i nya eller befintliga principer mot skräppost är karantänsprincipen bara effektiv om åtgärdsvärdet är karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="a38e1-321">Om du vill se åtgärdsvärdena i befintliga principer för skräppostskydd kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a38e1-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="a38e1-322">Mer information om standardåtgärdsvärdena och de rekommenderade åtgärdsvärdena för Standard och Strikt finns i Inställningarna för [EOP-principen för](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="a38e1-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="a38e1-323">En skräppostfiltrering som skulle vara utan en motsvarande karantänprincipparameter innebär att [standardprincipen för](#step-2-assign-a-quarantine-policy-to-supported-features) karantänen används för den aktuella bedömningsposten.</span><span class="sxs-lookup"><span data-stu-id="a38e1-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="a38e1-324">Du behöver bara ersätta en standardprincip för karantän med en anpassad karantänprincip om du vill ändra slutanvändarfunktionerna för meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="a38e1-325">En ny policy mot skräppost i PowerShell kräver en princip för skräppostfilter (inställningar) med cmdleten **New-HostedContentFilterPolicy** och en ny skräppostfilterregel (mottagarfilter) med cmdleten **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="a38e1-326">Instruktioner finns i Använda [PowerShell för att skapa principer mot skräppost.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="a38e1-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="a38e1-327">I det här exemplet skapas en ny policy för skräppostfilter med namnet Research Department med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a38e1-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="a38e1-328">Åtgärden för all skräppostfiltrering är inställd på karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="a38e1-329">Den anpassade karantänprincipen med namnet NoAccess som tilldelar **inga** åtkomstbehörigheter ersätter alla standardprinciper för karantän som inte redan tilldelar Inga **åtkomstbehörigheter** som standard.</span><span class="sxs-lookup"><span data-stu-id="a38e1-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="a38e1-330">Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a38e1-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="a38e1-331">Det här exemplet ändrar den befintliga policyn för skräppostfilter med namnet Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a38e1-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="a38e1-332">Åtgärden för karantänen för skräppost är inställd på karantän och den anpassade karantänprincipen NoAccess tilldelas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="a38e1-333">Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a38e1-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-334">Konfigurera inställningar för globala karantänmeddelanden i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="a38e1-335">Med de globala inställningarna för karantänprinciper kan du anpassa skräppost-aviseringarna för slutanvändaren som skickas till mottagare av meddelanden som har satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="a38e1-336">Mer information om dessa meddelanden finns i [Skräppost-aviseringar för slutanvändare.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a38e1-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="a38e1-337">I Microsoft 365 Defender-portalen går du till **E-& för samarbete** – hotregler. Sätt principer för karantän \>  \>  och välj \>  sedan **karantänprinciper.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="a38e1-338">Välj **Globala inställningar** på sidan **Karantänprincip.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="a38e1-339">I den **utfällfältet** för meddelandeinställningar för karantän som öppnas konfigurerar du några eller alla av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a38e1-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="a38e1-340">**Visningsnamn:** Anpassa avsändarens visningsnamn som används i skräppost-aviseringarna för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="a38e1-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="a38e1-341">För varje språk som du har lagt till väljer du språket i rutan för det andra språket (klicka inte på X) och ange det textvärde du vill ha i rutan **Visningsnamn.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="a38e1-342">Följande skärmbild visar det anpassade visningsnamnet i en skräppost-avisering för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="a38e1-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Ett anpassat avsändarvisningsnamn i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="a38e1-344">**Ansvarsfriskrivning:** Lägg till en anpassad ansvarsfriskrivning längst ned i skräppost-aviseringar för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="a38e1-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="a38e1-345">Lokaliserad text, **en ansvarsfriskrivning från organisationen:** inkluderas alltid först, följt av den text som du anger.</span><span class="sxs-lookup"><span data-stu-id="a38e1-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="a38e1-346">För varje språk som du har lagt till väljer du språk i rutan för det andra språket (klicka inte på X) och ange det textvärde du vill ha i rutan **Ansvarsfriskrivning.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="a38e1-347">Följande skärmbild visar den anpassade ansvarsfriskrivningen i en skräppost-avisering för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="a38e1-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![En anpassad ansvarsfriskrivning längst ned i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="a38e1-349">**Välj språk:** Skräppost-aviseringar för slutanvändare har redan lokaliserats baserat på mottagarens språkinställningar.</span><span class="sxs-lookup"><span data-stu-id="a38e1-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="a38e1-350">Du kan ange anpassad text på olika språk för värdena **Visningsnamn och** **Ansvarsfriskrivning.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="a38e1-351">Välj minst ett språk i rutan för det första språket och klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="a38e1-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="a38e1-352">Du kan välja flera språk genom att klicka **på Lägg** till efter varje.</span><span class="sxs-lookup"><span data-stu-id="a38e1-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="a38e1-353">En ruta för avsnittsspråk visar alla språk som du har valt:</span><span class="sxs-lookup"><span data-stu-id="a38e1-353">A section language box shows all of the languages that you've selected:</span></span>

     ![Valda språk i den andra språkrutan i meddelandeinställningarna för den globala karantänen för karantänprinciperna](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="a38e1-355">**Använd min företagslogotyp:** Välj det här alternativet om du vill ersätta standardlogotypen som visas längst upp bland skräppost-aviseringarna för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="a38e1-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="a38e1-356">Innan du gör det måste du följa anvisningarna i Anpassa företagets [Microsoft 365 för att](../../admin/setup/customize-your-organization-theme.md) ladda upp din anpassade logotyp.</span><span class="sxs-lookup"><span data-stu-id="a38e1-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="a38e1-357">Följande skärmbild visar en anpassad logotyp i en skräppost-avisering för slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="a38e1-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![En anpassad logotyp i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-359">Visa karantänprinciper i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="a38e1-360">I Microsoft 365 Defender-portalen går du till **E-& för samarbete** – hotregler. Sätt principer för karantän \>  \>  och välj \>  sedan **karantänprinciper.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="a38e1-361">På **sidan Karantänprincip** visas listan med principer efter **namn** och datum **för senaste** uppdatering.</span><span class="sxs-lookup"><span data-stu-id="a38e1-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="a38e1-362">Om du vill visa inställningarna för inbyggda eller anpassade karantänprinciper väljer du karantänprincipen i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="a38e1-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="a38e1-363">Om du vill visa de globala inställningarna klickar du **på Globala inställningar**</span><span class="sxs-lookup"><span data-stu-id="a38e1-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="a38e1-364">Visa karantänprinciper i PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e1-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="a38e1-365">Om du hellre vill använda PowerShell för att visa karantänprinciper gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="a38e1-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="a38e1-366">Om du vill visa en sammanfattningslista över alla inbyggda eller anpassade principer kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a38e1-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="a38e1-367">Om du vill visa inställningarna för inbyggda eller anpassade karantänprinciper ersätter du med namnet på \<QuarantinePolicyName\> karantänprincipen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a38e1-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="a38e1-368">Kör följande kommando för att visa de globala inställningarna:</span><span class="sxs-lookup"><span data-stu-id="a38e1-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="a38e1-369">Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="a38e1-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-370">Ändra karantänprinciper i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="a38e1-371">I Microsoft 365 Defender-portalen går du till **E-& för samarbete** – hotregler. Sätt principer för karantän \>  \>  och välj \>  sedan **karantänprinciper.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="a38e1-372">Markera principen **på sidan** Karantänprinciper genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="a38e1-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="a38e1-373">När du har valt principen klickar du på ![ ikonen Redigera ](../../media/m365-cc-sc-edit-icon.png) **princip, Redigera** princip som visas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="a38e1-374">Guiden **Redigera princip** som öppnas är  i princip identisk med guiden Ny princip enligt beskrivningen i avsnittet Skapa principer [för Microsoft 365 Defender-portalen](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="a38e1-375">Den största skillnaden är att du inte kan byta namn på en befintlig princip.</span><span class="sxs-lookup"><span data-stu-id="a38e1-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="a38e1-376">När du är klar med att ändra principen går du till sidan **Sammanfattning och** klickar på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="a38e1-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="a38e1-377">Ändra karantänprinciper i PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e1-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="a38e1-378">Om du hellre vill använda PowerShell för att ändra en anpassad karantänprincip ersätter du med namnet på karantänprincipen \<QuarantinePolicyName\> och använder följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a38e1-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="a38e1-379">De tillgängliga inställningarna är desamma som beskrivs för att skapa karantänprinciper tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="a38e1-380">Detaljerad information om syntax och parametrar finns i [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="a38e1-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="a38e1-381">Ta bort karantänprinciper i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="a38e1-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="a38e1-382">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="a38e1-382">**Notes**:</span></span>

- <span data-ttu-id="a38e1-383">Du kan inte ta bort inbyggda karantänprinciper.</span><span class="sxs-lookup"><span data-stu-id="a38e1-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="a38e1-384">Innan du tar bort en anpassad karantänprincip ska du kontrollera att den inte används.</span><span class="sxs-lookup"><span data-stu-id="a38e1-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="a38e1-385">Kör till exempel följande kommando i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a38e1-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="a38e1-386">Om karantänprincipen används ersätter [du den tilldelade karantänprincipen innan](#step-2-assign-a-quarantine-policy-to-supported-features) du tar bort den.</span><span class="sxs-lookup"><span data-stu-id="a38e1-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="a38e1-387">I Microsoft 365 Defender-portalen går du till **E-& för samarbete** – hotregler. Sätt principer för karantän \>  \>  och välj \>  sedan **karantänprinciper.**</span><span class="sxs-lookup"><span data-stu-id="a38e1-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="a38e1-388">På sidan **Karantänprincip** väljer du den anpassade karantänprincip som du vill ta bort genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="a38e1-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="a38e1-389">När du har valt principen klickar du på ikonen ![ Ta bort princip ta ](../../media/m365-cc-sc-delete-icon.png) **bort** princip som visas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="a38e1-390">Klicka **på Ta** bort princip i bekräftelsedialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="a38e1-391">Ta bort karantänprinciper i PowerShell</span><span class="sxs-lookup"><span data-stu-id="a38e1-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="a38e1-392">Om du hellre vill använda PowerShell för att ta bort en anpassad karantänprincip ersätter du med namnet på \<QuarantinePolicyName\> karantänprincipen och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a38e1-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="a38e1-393">Detaljerad information om syntax och parametrar finns i [Ta bort karantäntagg.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="a38e1-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="a38e1-394">Information om karantänprinciper</span><span class="sxs-lookup"><span data-stu-id="a38e1-394">Quarantine policy permission details</span></span>

<span data-ttu-id="a38e1-395">I följande avsnitt beskrivs effekterna av förinställda behörighetsgrupper och enskilda behörigheter i information om meddelanden i karantän och i skräppost-aviseringar för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="a38e1-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="a38e1-396">Förinställda behörighetsgrupper</span><span class="sxs-lookup"><span data-stu-id="a38e1-396">Preset permissions groups</span></span>

<span data-ttu-id="a38e1-397">De enskilda behörigheterna som ingår i förinställda behörighetsgrupper visas i tabellen i början av den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a38e1-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="a38e1-398">Ingen åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-398">No access</span></span>

<span data-ttu-id="a38e1-399">Om karantänprincipen tilldelar **behörigheterna Ingen åtkomst** (ingen behörighet) får användarna fortfarande vissa grundläggande funktioner:</span><span class="sxs-lookup"><span data-stu-id="a38e1-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="a38e1-400">**Information om meddelanden i karantän:** **Knappen Visa meddelanderubrik** är alltid tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantänprincipen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="a38e1-402">**Skräppost-aviseringar för slutanvändare:** **Knappen** Granska som för användaren till meddelandet i karantän är alltid tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantänprincipen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="a38e1-404">Begränsad åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-404">Limited access</span></span>

<span data-ttu-id="a38e1-405">Om karantänprincipen tilldelar **behörigheterna Begränsad** åtkomst får användarna följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="a38e1-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="a38e1-406">**Information om meddelanden i karantän:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="a38e1-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="a38e1-407">**Begär utgivning**</span><span class="sxs-lookup"><span data-stu-id="a38e1-407">**Request release**</span></span>
  - <span data-ttu-id="a38e1-408">**Visa meddelanderubrik**</span><span class="sxs-lookup"><span data-stu-id="a38e1-408">**View message header**</span></span>
  - <span data-ttu-id="a38e1-409">**Förhandsgranskningsmeddelande**</span><span class="sxs-lookup"><span data-stu-id="a38e1-409">**Preview message**</span></span>
  - <span data-ttu-id="a38e1-410">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-410">**Block sender**</span></span>
  - <span data-ttu-id="a38e1-411">**Ta bort från karantän**</span><span class="sxs-lookup"><span data-stu-id="a38e1-411">**Remove from quarantine**</span></span>

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantänprincipen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="a38e1-413">**Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="a38e1-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="a38e1-414">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-414">**Block sender**</span></span>
  - <span data-ttu-id="a38e1-415">**Granska**</span><span class="sxs-lookup"><span data-stu-id="a38e1-415">**Review**</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantänprincipen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="a38e1-417">Fullständig åtkomst</span><span class="sxs-lookup"><span data-stu-id="a38e1-417">Full access</span></span>

<span data-ttu-id="a38e1-418">Om karantänprincipen tilldelar **fullständig åtkomst** (alla tillgängliga behörigheter) får användarna följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="a38e1-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="a38e1-419">**Information om meddelanden i karantän:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="a38e1-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="a38e1-420">**Släpp meddelande**</span><span class="sxs-lookup"><span data-stu-id="a38e1-420">**Release message**</span></span>
  - <span data-ttu-id="a38e1-421">**Visa meddelanderubrik**</span><span class="sxs-lookup"><span data-stu-id="a38e1-421">**View message header**</span></span>
  - <span data-ttu-id="a38e1-422">**Förhandsgranskningsmeddelande**</span><span class="sxs-lookup"><span data-stu-id="a38e1-422">**Preview message**</span></span>
  - <span data-ttu-id="a38e1-423">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-423">**Block sender**</span></span>
  - <span data-ttu-id="a38e1-424">**Tillåt avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-424">**Allow sender**</span></span>
  - <span data-ttu-id="a38e1-425">**Ta bort från karantän**</span><span class="sxs-lookup"><span data-stu-id="a38e1-425">**Remove from quarantine**</span></span>

  ![Tillgängliga knappar i meddelandeinformationen i karantän om karantänprincipen ger användaren fullständig åtkomstbehörighet](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="a38e1-427">**Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="a38e1-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="a38e1-428">**Spärra avsändare**</span><span class="sxs-lookup"><span data-stu-id="a38e1-428">**Block sender**</span></span>
  - <span data-ttu-id="a38e1-429">**Version**</span><span class="sxs-lookup"><span data-stu-id="a38e1-429">**Release**</span></span>
  - <span data-ttu-id="a38e1-430">**Granska**</span><span class="sxs-lookup"><span data-stu-id="a38e1-430">**Review**</span></span>

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantänprincipen ger användaren fullständig åtkomstbehörighet](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="a38e1-432">Enskilda behörigheter</span><span class="sxs-lookup"><span data-stu-id="a38e1-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="a38e1-433">Kom ihåg att användarna alltid får de knappar som beskrivs i [avsnittet Ingen](#no-access) åtkomst.</span><span class="sxs-lookup"><span data-stu-id="a38e1-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="a38e1-434">Dessa knappar ingår inte i de enskilda behörighetsbeskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="a38e1-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="a38e1-435">Tillåt avsändarbehörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-435">Allow sender permission</span></span>

<span data-ttu-id="a38e1-436">Med **tillåt avsändarbehörighet** _(PermissionToAllowSender)_ styr du åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän Valv sina avsändare i Valv avsändare.</span><span class="sxs-lookup"><span data-stu-id="a38e1-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="a38e1-437">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-438">**Tillåt avsändarbehörighet** aktiverad: **Knappen Tillåt avsändare** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="a38e1-439">**Tillåt avsändarbehörighet** inaktiverad: **Knappen Tillåt** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="a38e1-440">**Skräppost-aviseringar för slutanvändare**: Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="a38e1-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="a38e1-441">Mer information om listan Valv-avsändare finns i Förhindra att betrodda avsändare [blockeras](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) och Använda Exchange Online PowerShell för att konfigurera samlingen [safelist för en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="a38e1-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="a38e1-442">Blockera avsändarbehörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-442">Block sender permission</span></span>

<span data-ttu-id="a38e1-443">Behörigheten **Blockera avsändare** _(PermissionToBlockSender)_ styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän i sin lista med spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="a38e1-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="a38e1-444">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-445">**Behörigheten Blockera** avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="a38e1-446">**Spärra avsändarbehörighet** inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="a38e1-447">**Skräppost-aviseringar för slutanvändare:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="a38e1-448">**Spärra avsändarbehörighet** inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="a38e1-449">**Behörigheten Blockera** avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="a38e1-450">Mer information om listan Spärrade avsändare [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) finns i Spärra meddelanden från någon och Använda Exchange Online PowerShell för att konfigurera samlingslistan över betrodda avsändare [i en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="a38e1-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="a38e1-451">Ta bort behörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-451">Delete permission</span></span>

<span data-ttu-id="a38e1-452">Behörigheten **Delete** _(PermissionToDelete)_ styr möjligheten för användare att ta bort sina meddelanden (meddelanden där användaren är mottagare) från karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="a38e1-453">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-454">**Ta** bort behörighet aktiverad: **Knappen Ta bort från** karantän är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="a38e1-455">**Ta** bort behörighet inaktiverad: **Knappen Ta bort från** karantän är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="a38e1-456">**Skräppost-aviseringar för slutanvändare**: Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="a38e1-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="a38e1-457">Förhandsgranskningsbehörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-457">Preview permission</span></span>

<span data-ttu-id="a38e1-458">**Förhandsversionsbehörigheten** _(PermissionToPreview)_ styr möjligheten för användare att förhandsgranska sina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="a38e1-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="a38e1-459">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-460">**Förhandsgranskningsbehörighet** aktiverad: **Knappen Förhandsgranska** meddelande är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="a38e1-461">**Förhandsgranskningsbehörighet** **inaktiverad: Knappen Förhandsgranska** meddelande är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="a38e1-462">**Skräppost-aviseringar för slutanvändare**: Ingen effekt.</span><span class="sxs-lookup"><span data-stu-id="a38e1-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="a38e1-463">Tillåt mottagare att släppa ett meddelande från karantänbehörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="a38e1-464">Allow **recipients to release a message from quarantine** permission _(PermissionToRelease)_ controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span><span class="sxs-lookup"><span data-stu-id="a38e1-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="a38e1-465">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-466">Behörighet aktiverad: Knappen **Släpp meddelande** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="a38e1-467">Behörigheten är **inaktiverad: Knappen Släpp** meddelande är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="a38e1-468">**Skräppost-aviseringar för slutanvändare:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="a38e1-469">Behörighet aktiverad: **Knappen Släpp** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="a38e1-470">Behörigheten är **inaktiverad: Knappen** Släpp är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="a38e1-471">Tillåt mottagare att begära att ett meddelande ska släppas från karantänbehörighet</span><span class="sxs-lookup"><span data-stu-id="a38e1-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="a38e1-472">Tillåta **mottagare att** begära att ett meddelande ska släppas från karantänbehörighet  _(PermissionToRequestRelease)_ kontrollerar möjligheten för användare att begära att meddelanden i karantän ska släppas.</span><span class="sxs-lookup"><span data-stu-id="a38e1-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="a38e1-473">Meddelandet släpps bara när en administratör godkänt begäran.</span><span class="sxs-lookup"><span data-stu-id="a38e1-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="a38e1-474">**Information om meddelanden i karantän:**</span><span class="sxs-lookup"><span data-stu-id="a38e1-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="a38e1-475">Behörighet aktiverad: **Knappen Begär version** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="a38e1-476">Behörigheten är **inaktiverad: Knappen Begär** version är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="a38e1-477">**Skräppost-aviseringar för slutanvändare:** **Knappen Släpp** är inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a38e1-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
