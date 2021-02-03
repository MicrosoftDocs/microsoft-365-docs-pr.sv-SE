---
title: Uppgradera distributionslistor till Microsoft 365-grupper i Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Lär dig hur du uppgraderar en eller flera distributionslistor till Microsoft 365-grupper i Outlook och hur du använder PowerShell för att uppgradera flera distributionslistor samtidigt.
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080533"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="8dba5-103">Uppgradera distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="8dba5-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="8dba5-104">Du kan uppgradera distributionslistor till Microsoft 365-grupper med Outlook.</span><span class="sxs-lookup"><span data-stu-id="8dba5-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="8dba5-105">Det här är ett bra sätt att ge organisationens distributionslistor alla funktioner som Finns i Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="8dba5-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="8dba5-106">Varför du bör uppgradera dina distributionslistor till grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="8dba5-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="8dba5-107">Du kan uppgradera dina distributionslistor en i taget eller flera samtidigt.</span><span class="sxs-lookup"><span data-stu-id="8dba5-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="8dba5-108">Uppgradera en eller flera distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="8dba5-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="8dba5-109">Du måste vara global administratör eller Exchange-administratör för att uppgradera en distributionslista.</span><span class="sxs-lookup"><span data-stu-id="8dba5-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="8dba5-110">Om du vill uppgradera till Microsoft 365-grupper måste en distributionsgrupp ha en ägare med en postlåda.</span><span class="sxs-lookup"><span data-stu-id="8dba5-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="8dba5-111">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="8dba5-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="8dba5-112">Gå till Mottagare grupper i **administrationscentret för** \> **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="8dba5-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="8dba5-113">Ett meddelande visas om att du har distributionslistor (kallas även **distributionsgrupper)** som kan uppgraderas till Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="8dba5-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="8dba5-114">![Välj knappen Komma igång](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="8dba5-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="8dba5-115">Välj en eller flera distributionslistor (kallas även för **distributionsgrupp** ) från **gruppsidan**.</span><span class="sxs-lookup"><span data-stu-id="8dba5-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="8dba5-116">![Välj en distributionsgrupp](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="8dba5-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="8dba5-117">Välj uppgraderingsikonen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-117">Select the upgrade icon.</span></span><br/>![Ikonen Uppgradera till Microsoft 365-grupper](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="8dba5-119">Välj Ja i **informationsdialogrutan för** att bekräfta uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="8dba5-120">Processen börjar direkt.</span><span class="sxs-lookup"><span data-stu-id="8dba5-120">The process begins immediately.</span></span> <span data-ttu-id="8dba5-121">Beroende på hur många och stora adresser du uppgraderar kan processen ta några minuter eller timmar.</span><span class="sxs-lookup"><span data-stu-id="8dba5-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="8dba5-122">Om det inte går att uppgradera distributionslistan visas en dialogruta som anger det.</span><span class="sxs-lookup"><span data-stu-id="8dba5-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="8dba5-123">Se [Vilka distributionslistor kan inte uppgraderas?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="8dba5-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="8dba5-124">Om du uppgraderar flera distributionslistor kan du använda listrutan för att filtrera fram vilka distributionslistor som har uppgraderats.</span><span class="sxs-lookup"><span data-stu-id="8dba5-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="8dba5-125">Om listan inte är klar väntar du en stund till och väljer **sedan** Uppdatera för att se vad som har uppgraderats.</span><span class="sxs-lookup"><span data-stu-id="8dba5-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="8dba5-p106">Du får inget meddelande om att uppgraderingen har slutförts för alla distributionslistor du valde. Det här kan du se genom att visa vad som står under **Tillgängliga för uppgradering** eller **Uppgraderade distributionslistor**.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="8dba5-p107">Om du valde en distributionslista för uppgradering, men den fortfarande visas på sidan som Tillgänglig för uppgradering, så gick det inte att uppgradera listan. Läs mer i [Vad gör jag om uppgraderingen inte fungerar](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="8dba5-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="8dba5-p108">Om du får e-postsammandrag för grupper kanske du har lagt märke till erbjudandet om att uppgradera de kvalificerade distributionslistor du äger. Mer information om e-postsammandrag finns i [Hålla en gruppkonversation i Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="8dba5-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="8dba5-132">Vad gör jag om uppgraderingen inte fungerar</span><span class="sxs-lookup"><span data-stu-id="8dba5-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="8dba5-133">Distributionslistor som inte går att uppgradera förändras inte.</span><span class="sxs-lookup"><span data-stu-id="8dba5-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="8dba5-p109">Om du inte kan uppgradera en eller flera **kvalificerade** distributionslistor ska du öppna ett [supportärende](../contact-support-for-business-products.md). Ärendet eskaleras till ingenjörsteamet för grupper som försöker lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="8dba5-p110">Det är möjligt att distributionslistan inte uppgraderades på grund av ett avbrott i tjänsten, men det är ganska osannolikt. Om du vill kan du vänta en stund och sedan försöka uppgradera distributionslistan igen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="8dba5-138">Använda PowerShell till att uppgradera flera distributionslistor åt gången</span><span class="sxs-lookup"><span data-stu-id="8dba5-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="8dba5-139">Om du är van vid att använda PowerShell kanske du vill göra det i stället för att använda gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="8dba5-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="8dba5-140">Vi har en uppsättning cmdlets som hjälper dig att uppgradera distributionslistor.</span><span class="sxs-lookup"><span data-stu-id="8dba5-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="8dba5-141">Se nedan.</span><span class="sxs-lookup"><span data-stu-id="8dba5-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="8dba5-142">Uppgradera en enda dl</span><span class="sxs-lookup"><span data-stu-id="8dba5-142">Upgrade a single DL</span></span>

<span data-ttu-id="8dba5-143">Om du vill uppgradera en enskild DLL kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8dba5-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="8dba5-144">Om du till exempel vill uppgradera en DLs med SMTP-dl1@contoso.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8dba5-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="8dba5-145">Du kan också uppgradera en enskild distributionslista till en Microsoft 365-grupp med [PowerShell-cmdleten New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)</span><span class="sxs-lookup"><span data-stu-id="8dba5-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="8dba5-146">Uppgradera flera adresser i en batch</span><span class="sxs-lookup"><span data-stu-id="8dba5-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="8dba5-147">Du kan även överföra flera DLs som en batch och uppgradera dem tillsammans:</span><span class="sxs-lookup"><span data-stu-id="8dba5-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="8dba5-148">Om du till exempel vill uppgradera fem DLs med SMTP-adress och köra `dl1@contoso.com` `dl2@contoso.com` följande `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` kommando:</span><span class="sxs-lookup"><span data-stu-id="8dba5-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="8dba5-149">Uppgradera alla kvalificerade adresser</span><span class="sxs-lookup"><span data-stu-id="8dba5-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="8dba5-150">Du kan uppgradera alla kvalificerade adresser på två sätt.</span><span class="sxs-lookup"><span data-stu-id="8dba5-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="8dba5-151">CmdletUpgrade-DistributionGroup tar inte emot data från pipelinen, av den anledningen är det nödvändigt att använda operatorn "foreach-object " för {} att köras korrekt.</span><span class="sxs-lookup"><span data-stu-id="8dba5-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="8dba5-152">Hämta de kvalificerade DLs i klientorganisationen och uppgradera dem med hjälp av uppgraderingskommandot:</span><span class="sxs-lookup"><span data-stu-id="8dba5-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="8dba5-153">Hämta listan över alla DLs och uppgradera endast de kvalificerade DLs:</span><span class="sxs-lookup"><span data-stu-id="8dba5-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="8dba5-154">Vanliga frågor och svar om uppgradering av distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="8dba5-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="8dba5-155">Vilka distributionslistor kan inte uppgraderas?</span><span class="sxs-lookup"><span data-stu-id="8dba5-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="8dba5-156">Du kan bara uppgradera enkla distributionslistor som hanteras i molnet och inte är kapslade.</span><span class="sxs-lookup"><span data-stu-id="8dba5-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="8dba5-157">I tabellen nedan visas distributionslistor som **INTE** kan uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="8dba5-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="8dba5-158">**Egenskap**</span><span class="sxs-lookup"><span data-stu-id="8dba5-158">**Property**</span></span>|<span data-ttu-id="8dba5-159">**Kvalificerad?**</span><span class="sxs-lookup"><span data-stu-id="8dba5-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8dba5-160">Lokalt hanterad distributionslista</span><span class="sxs-lookup"><span data-stu-id="8dba5-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="8dba5-161">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-161">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-p113">Kapslade distributionslistor Distributionslistan har antingen underordnade grupper eller är medlem i en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="8dba5-164">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-164">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-165">Distributionslistor med andra **RecipientTypeDetails** för medlemmar än **UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**</span><span class="sxs-lookup"><span data-stu-id="8dba5-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="8dba5-166">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-166">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-167">Distributionslista med fler än 100 ägare</span><span class="sxs-lookup"><span data-stu-id="8dba5-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="8dba5-168">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-168">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-169">Distributionslista som endast har medlemmar och ingen ägare</span><span class="sxs-lookup"><span data-stu-id="8dba5-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="8dba5-170">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-170">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-171">Distributionslista med ett alias som innehåller specialtecken</span><span class="sxs-lookup"><span data-stu-id="8dba5-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="8dba5-172">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-172">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-173">Om distributionslistan är konfigurerad som en adress för vidarebefordran för Delad postlåda</span><span class="sxs-lookup"><span data-stu-id="8dba5-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="8dba5-174">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-174">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-175">Om dll-listan ingår i en **avsändarbegränsning** i en annan dll-post.</span><span class="sxs-lookup"><span data-stu-id="8dba5-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="8dba5-176">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-176">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-177">Säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="8dba5-177">Security groups</span></span>  <br/> |<span data-ttu-id="8dba5-178">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-178">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-179">Dynamiska distributionslistor</span><span class="sxs-lookup"><span data-stu-id="8dba5-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="8dba5-180">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-180">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-181">Distributionslistor som har konverterats till **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="8dba5-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="8dba5-182">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-182">No</span></span>  <br/> |
|<span data-ttu-id="8dba5-183">Distributionslistor där **MemberJoinRestriction** och/eller **MemberDepartRestriction** är **stängt**</span><span class="sxs-lookup"><span data-stu-id="8dba5-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="8dba5-184">Nej</span><span class="sxs-lookup"><span data-stu-id="8dba5-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="8dba5-185">Kontrollera vilka adresser som är kvalificerade för uppgradering</span><span class="sxs-lookup"><span data-stu-id="8dba5-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="8dba5-186">Om du vill kontrollera om en dll-lista är berättigad eller inte kan du köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8dba5-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="8dba5-187">Om du vill kontrollera vilka DLs som är kvalificerade för uppgradering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8dba5-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="8dba5-188">Vilka kan köra uppgraderingsskripten?</span><span class="sxs-lookup"><span data-stu-id="8dba5-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="8dba5-189">Användare med global administratör eller Exchange-administratörsrättigheter.</span><span class="sxs-lookup"><span data-stu-id="8dba5-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="8dba5-190">Varför visas det fortfarande en distributionslista på kontaktkortet?</span><span class="sxs-lookup"><span data-stu-id="8dba5-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="8dba5-191">Hur kan jag förhindra att en uppgraderad distributionslista visas i min lista med automatiska förslag?</span><span class="sxs-lookup"><span data-stu-id="8dba5-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="8dba5-192">För Outlook: När någon försöker skicka ett e-postmeddelande i Outlook genom att skriva namnet på Microsoft 365-gruppen efter migrering matchas mottagaren som distributionslistan i stället för gruppen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="8dba5-193">Mottagarens kontaktkort blir distributionslistans kontaktkort.</span><span class="sxs-lookup"><span data-stu-id="8dba5-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="8dba5-194">Det här beror på mottagarens cache eller cachen för smeknamn i Outlook.</span><span class="sxs-lookup"><span data-stu-id="8dba5-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="8dba5-195">E-postmeddelandet kommer att skickas till gruppen, men det kan vara förvirrande för avsändaren.</span><span class="sxs-lookup"><span data-stu-id="8dba5-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="8dba5-196">Du kan följa instruktionerna i [Information om listan Komplettera automatiskt i Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) om du vill återställa cachen, vilket löser problemet.</span><span class="sxs-lookup"><span data-stu-id="8dba5-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="8dba5-197">För Outlook på webben: Om du använder Outlook på webben ligger distributionslistan kvar som mottagare i cachen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="8dba5-198">Du kan följa stegen i Ta bort föreslagna namn eller [e-postadresser](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) från listan Komplettera automatiskt om du vill uppdatera cachen så att gruppkontaktkortet visas.</span><span class="sxs-lookup"><span data-stu-id="8dba5-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="8dba5-199">Får nya gruppmedlemmar ett välkomstmeddelande i Inkorgen?</span><span class="sxs-lookup"><span data-stu-id="8dba5-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="8dba5-p117">Nej. Inställningen för välkomstmeddelanden är inaktiverad som standard. Den här inställningen påverkar både befintliga och nya gruppmedlemmar som kan ansluta efter migreringen. Om gruppägare senare tillåter gästanvändare får inte heller gästanvändare något välkomstmeddelande i Inkorgen. Gästmedlemmar kan fortsätta att arbeta med gruppen.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="8dba5-205">Vad händer om en eller några av dina E-adresser inte uppgraderas?</span><span class="sxs-lookup"><span data-stu-id="8dba5-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="8dba5-206">Det finns vissa fall där dl är berättigande men inte kunde uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="8dba5-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="8dba5-207">Dl uppgraderas inte och blir kvar som en dl.</span><span class="sxs-lookup"><span data-stu-id="8dba5-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="8dba5-208">Om administratören har **tillämpat** principen för grupp-e-postadress för grupperna i en organisation och de försöker uppgradera dina adresser som inte uppfyller villkoren uppgraderas inte dll-posten</span><span class="sxs-lookup"><span data-stu-id="8dba5-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="8dba5-209">DLs med **MemberJoinRestriction** eller **MemberDepartRestriction** inställd på **Stängt,** kunde inte uppgraderas</span><span class="sxs-lookup"><span data-stu-id="8dba5-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="8dba5-210">Vad händer med distributionslistan om uppgraderingen från EAC misslyckas?</span><span class="sxs-lookup"><span data-stu-id="8dba5-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="8dba5-p119">Uppgraderingen utförs bara när anropet skickas till servern. Om uppgraderingen misslyckas förblir distributionslistorna intakta. De fungerar som de brukade.</span><span class="sxs-lookup"><span data-stu-id="8dba5-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>
