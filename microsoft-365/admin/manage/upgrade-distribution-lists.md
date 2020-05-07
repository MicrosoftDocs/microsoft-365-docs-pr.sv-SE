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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Lär dig hur du uppgraderar en eller flera distributionslistor till Microsoft 365-grupper i Outlook och hur du använder PowerShell för att uppgradera flera distributionslistor samtidigt.
ms.openlocfilehash: 993b0baf46b702322df64693f682e25b0240a0ab
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065675"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e6d93-103">Uppgradera distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="e6d93-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e6d93-104">Du kan uppgradera distributionslistor till Microsoft 365 Groups med Outlook.</span><span class="sxs-lookup"><span data-stu-id="e6d93-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="e6d93-105">Det här är ett bra sätt att ge organisationens distribution listor över alla funktioner i Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="e6d93-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="e6d93-106">Varför du bör uppgradera dina distributionslistor till grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="e6d93-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="e6d93-107">Du kan uppgradera dina distributionslistor en i taget eller flera samtidigt.</span><span class="sxs-lookup"><span data-stu-id="e6d93-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e6d93-108">Uppgradera en eller flera distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="e6d93-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e6d93-109">Du måste vara global administratör eller Exchange-administratör för att kunna uppgradera en distributionslista.</span><span class="sxs-lookup"><span data-stu-id="e6d93-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="e6d93-110">Om du vill uppgradera till Microsoft 365-grupper måste en distributionsgrupp ha en ägare med en postlåda.</span><span class="sxs-lookup"><span data-stu-id="e6d93-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="e6d93-111">Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e6d93-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="e6d93-112">Gå till Mottagare **grupper**i **administrationscentret** \> för Exchange .</span><span class="sxs-lookup"><span data-stu-id="e6d93-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="e6d93-113">Ett meddelande visas om att du har distributionslistor (kallas även **distributionsgrupper)** som kan uppgraderas till Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="e6d93-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="e6d93-114">![Välj knappen Kom igång](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="e6d93-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="e6d93-115">Välj en eller flera distributionslistor (kallas även för **distributionsgrupp** ) från **gruppsidan**.</span><span class="sxs-lookup"><span data-stu-id="e6d93-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="e6d93-116">![Välj en distributionsgrupp](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="e6d93-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="e6d93-117">Välj uppgraderingsikonen.</span><span class="sxs-lookup"><span data-stu-id="e6d93-117">Select the upgrade icon.</span></span><br/>![Ikonen Uppgradera till Microsoft 365 Groups](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="e6d93-119">I informationsdialogrutan väljer du **Ja** för att bekräfta uppgraderingen.</span><span class="sxs-lookup"><span data-stu-id="e6d93-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="e6d93-120">Processen börjar omedelbart.</span><span class="sxs-lookup"><span data-stu-id="e6d93-120">The process begins immediately.</span></span> <span data-ttu-id="e6d93-121">Beroende på storlek och antal DLs du uppgraderar kan processen ta minuter eller timmar.</span><span class="sxs-lookup"><span data-stu-id="e6d93-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="e6d93-122">Om det inte går att uppgradera distributionslistan visas en dialogruta som anger det.</span><span class="sxs-lookup"><span data-stu-id="e6d93-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="e6d93-123">Se [Vilka distributionslistor kan inte uppgraderas?](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="e6d93-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="e6d93-124">Om du uppgraderar flera distributionslistor använder du listrutan för att filtrera vilka distributionslistor som har uppgraderats.</span><span class="sxs-lookup"><span data-stu-id="e6d93-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="e6d93-125">Om listan inte är klar väntar du ett tag till och väljer sedan **Uppdatera** för att se vad som har uppgraderats.</span><span class="sxs-lookup"><span data-stu-id="e6d93-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="e6d93-p106">Du får inget meddelande om att uppgraderingen har slutförts för alla distributionslistor du valde. Det här kan du se genom att visa vad som står under **Tillgängliga för uppgradering** eller **Uppgraderade distributionslistor**.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="e6d93-p107">Om du valde en distributionslista för uppgradering, men den fortfarande visas på sidan som Tillgänglig för uppgradering, så gick det inte att uppgradera listan. Läs mer i [Vad gör jag om uppgraderingen inte fungerar](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="e6d93-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="e6d93-p108">Om du får e-postsammandrag för grupper kanske du har lagt märke till erbjudandet om att uppgradera de kvalificerade distributionslistor du äger. Mer information om e-postsammandrag finns i [Hålla en gruppkonversation i Outlook](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22).</span><span class="sxs-lookup"><span data-stu-id="e6d93-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="e6d93-132">Vad gör jag om uppgraderingen inte fungerar</span><span class="sxs-lookup"><span data-stu-id="e6d93-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="e6d93-133">Distributionslistor som inte går att uppgradera förändras inte.</span><span class="sxs-lookup"><span data-stu-id="e6d93-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="e6d93-p109">Om du inte kan uppgradera en eller flera **kvalificerade** distributionslistor ska du öppna ett [supportärende](../contact-support-for-business-products.md). Ärendet eskaleras till ingenjörsteamet för grupper som försöker lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="e6d93-p110">Det är möjligt att distributionslistan inte uppgraderades på grund av ett avbrott i tjänsten, men det är ganska osannolikt. Om du vill kan du vänta en stund och sedan försöka uppgradera distributionslistan igen.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="e6d93-138">Använda PowerShell till att uppgradera flera distributionslistor åt gången</span><span class="sxs-lookup"><span data-stu-id="e6d93-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="e6d93-139">Om du är van vid att använda PowerShell kanske du vill göra det i stället för att använda gränssnittet.</span><span class="sxs-lookup"><span data-stu-id="e6d93-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="e6d93-140">Vi har en uppsättning cmdlets som hjälper dig att uppgradera distributionslistor.</span><span class="sxs-lookup"><span data-stu-id="e6d93-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="e6d93-141">Se nedan.</span><span class="sxs-lookup"><span data-stu-id="e6d93-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="e6d93-142">Uppgradera en enda DL</span><span class="sxs-lookup"><span data-stu-id="e6d93-142">Upgrade a single DL</span></span>

<span data-ttu-id="e6d93-143">Så här uppgraderar du ett enda DL-kommando:</span><span class="sxs-lookup"><span data-stu-id="e6d93-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="e6d93-144">Om du till exempel vill uppgradera en DLs med SMTP-adress dl1@contoso.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="e6d93-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="e6d93-145">Du kan också uppgradera en enda distributionslista till en Microsoft 365-grupp med hjälp av PowerShell-cmdleten [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)</span><span class="sxs-lookup"><span data-stu-id="e6d93-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="e6d93-146">Uppgradera flera DOMÄNKONTROLLISTA i en batch</span><span class="sxs-lookup"><span data-stu-id="e6d93-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="e6d93-147">Du kan också skicka flera DLs som en batch och uppgradera dem tillsammans:</span><span class="sxs-lookup"><span data-stu-id="e6d93-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="e6d93-148">Om du till exempel vill uppgradera fem DLs `dl1@contoso.com` `dl2@contoso.com`med `dl3@contoso.com` `dl4@contoso.com` SMTP-adress och , och `dl5@contoso.com`kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="e6d93-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="e6d93-149">Uppgradera alla kvalificerade DLs</span><span class="sxs-lookup"><span data-stu-id="e6d93-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="e6d93-150">Det finns två sätt att uppgradera alla berättigade DLs.</span><span class="sxs-lookup"><span data-stu-id="e6d93-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="e6d93-151">Cmdlet upgrade-DistributionGroup tar inte emot data från pipelinen, av den anledningen krävs{}det att du använder operatorn "foreach-object" för att köras.</span><span class="sxs-lookup"><span data-stu-id="e6d93-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="e6d93-152">Hämta de kvalificerade DLs i klienten och uppgradera dem med hjälp av uppgraderingskommandot:</span><span class="sxs-lookup"><span data-stu-id="e6d93-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="e6d93-153">Hämta listan över alla DLs och uppgradera endast de kvalificerade DLs:</span><span class="sxs-lookup"><span data-stu-id="e6d93-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e6d93-154">Vanliga frågor och svar om uppgradering av distributionslistor till Microsoft 365-grupper i Outlook</span><span class="sxs-lookup"><span data-stu-id="e6d93-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="e6d93-155">Vilka distributionslistor kan inte uppgraderas?</span><span class="sxs-lookup"><span data-stu-id="e6d93-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="e6d93-156">Du kan bara uppgradera enkla distributionslistor som hanteras i molnet och inte är kapslade.</span><span class="sxs-lookup"><span data-stu-id="e6d93-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="e6d93-157">I tabellen nedan visas distributionslistor som **INTE KAN** uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="e6d93-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="e6d93-158">**Egenskap**</span><span class="sxs-lookup"><span data-stu-id="e6d93-158">**Property**</span></span>|<span data-ttu-id="e6d93-159">**Kvalificerad?**</span><span class="sxs-lookup"><span data-stu-id="e6d93-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6d93-160">Lokalt hanterad distributionslista</span><span class="sxs-lookup"><span data-stu-id="e6d93-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="e6d93-161">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-161">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-p113">Kapslade distributionslistor Distributionslistan har antingen underordnade grupper eller är medlem i en annan grupp.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="e6d93-164">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-164">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-165">Distributionslistor med medlemmar **RecipientTypeDetails** andra än **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="e6d93-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="e6d93-166">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-166">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-167">Distributionslista som har mer än 100 ägare</span><span class="sxs-lookup"><span data-stu-id="e6d93-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="e6d93-168">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-168">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-169">Distributionslista som endast har medlemmar och ingen ägare</span><span class="sxs-lookup"><span data-stu-id="e6d93-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="e6d93-170">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-170">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-171">Distributionslista med ett alias som innehåller specialtecken</span><span class="sxs-lookup"><span data-stu-id="e6d93-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="e6d93-172">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-172">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-173">Om distributionslistan är konfigurerad som en adress för vidarebefordran för Delad postlåda</span><span class="sxs-lookup"><span data-stu-id="e6d93-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="e6d93-174">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-174">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-175">Om DL är en del av **Sender Restriction** i en annan DL.</span><span class="sxs-lookup"><span data-stu-id="e6d93-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="e6d93-176">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-176">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-177">Säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="e6d93-177">Security groups</span></span>  <br/> |<span data-ttu-id="e6d93-178">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-178">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-179">Dynamiska distributionslistor</span><span class="sxs-lookup"><span data-stu-id="e6d93-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="e6d93-180">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-180">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-181">Distributionslistor som konverterades till **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="e6d93-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="e6d93-182">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-182">No</span></span>  <br/> |
|<span data-ttu-id="e6d93-183">Distributionslistor där **MemberJoinRestriction** och/eller **MemberDepartRestriction** är **stängd**</span><span class="sxs-lookup"><span data-stu-id="e6d93-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="e6d93-184">Nej</span><span class="sxs-lookup"><span data-stu-id="e6d93-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="e6d93-185">Hur kontrollerar jag vilka domänkontrollistor som är berättigade till uppgradering?</span><span class="sxs-lookup"><span data-stu-id="e6d93-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="e6d93-186">Om du vill kontrollera om en DL är kvalificerad eller inte kan du köra kommandot nedan:</span><span class="sxs-lookup"><span data-stu-id="e6d93-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="e6d93-187">Om du vill kontrollera vilka DLs är berättigade till uppgradering bara köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="e6d93-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="e6d93-188">Vilka kan köra uppgraderingsskripten?</span><span class="sxs-lookup"><span data-stu-id="e6d93-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="e6d93-189">Personer med globala administratörs- eller Exchange-administratörsrättigheter.</span><span class="sxs-lookup"><span data-stu-id="e6d93-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="e6d93-190">Varför visas det fortfarande en distributionslista på kontaktkortet?</span><span class="sxs-lookup"><span data-stu-id="e6d93-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="e6d93-191">Hur kan jag förhindra att en uppgraderad distributionslista visas i min lista med automatiska förslag?</span><span class="sxs-lookup"><span data-stu-id="e6d93-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="e6d93-192">För Outlook: När någon försöker skicka ett e-postmeddelande i Outlook genom att skriva Microsoft 365-gruppnamnet efter migreringen matchas mottagaren som distributionslista i stället för i gruppen.</span><span class="sxs-lookup"><span data-stu-id="e6d93-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="e6d93-193">Mottagarens kontaktkort blir distributionslistans kontaktkort.</span><span class="sxs-lookup"><span data-stu-id="e6d93-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="e6d93-194">Det här beror på mottagarens cache eller cachen för smeknamn i Outlook.</span><span class="sxs-lookup"><span data-stu-id="e6d93-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="e6d93-195">E-postmeddelandet skickas till gruppen, men kan orsaka förvirring för avsändaren.</span><span class="sxs-lookup"><span data-stu-id="e6d93-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="e6d93-196">Du kan följa instruktionerna i [Information om listan Komplettera automatiskt i Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) om du vill återställa cachen, vilket löser problemet.</span><span class="sxs-lookup"><span data-stu-id="e6d93-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="e6d93-197">För Outlook på webben: När det gäller Outlook på webben finns mottagaren för distributionslistan kvar i cacheminnet.</span><span class="sxs-lookup"><span data-stu-id="e6d93-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="e6d93-198">Du kan följa stegen i [Ta bort föreslaget namn eller e-postadress från listan Komplettera automatiskt](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) för att uppdatera cacheminnet för att se gruppkontaktkortet.</span><span class="sxs-lookup"><span data-stu-id="e6d93-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="e6d93-199">Får nya gruppmedlemmar ett välkomstmeddelande i Inkorgen?</span><span class="sxs-lookup"><span data-stu-id="e6d93-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="e6d93-p117">Nej. Inställningen för välkomstmeddelanden är inaktiverad som standard. Den här inställningen påverkar både befintliga och nya gruppmedlemmar som kan ansluta efter migreringen. Om gruppägare senare tillåter gästanvändare får inte heller gästanvändare något välkomstmeddelande i Inkorgen. Gästmedlemmar kan fortsätta att arbeta med gruppen.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="e6d93-205">Vad händer om en eller några av DLs inte uppgraderas?</span><span class="sxs-lookup"><span data-stu-id="e6d93-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="e6d93-206">Det finns vissa fall där även DL är berättigad men inte kunde uppgraderas.</span><span class="sxs-lookup"><span data-stu-id="e6d93-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="e6d93-207">DL uppgraderas inte och förblir dl.</span><span class="sxs-lookup"><span data-stu-id="e6d93-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="e6d93-208">Om administratören har tillämpat **gruppadressprincip** för grupperna i en organisation och de försöker uppgradera DLs som inte uppfyller kriterierna, uppgraderas inte DL</span><span class="sxs-lookup"><span data-stu-id="e6d93-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="e6d93-209">DCl med **MemberJoinRestriction** eller **MemberDepartRestriction** inställd på **Stängd**, kunde inte uppgraderas</span><span class="sxs-lookup"><span data-stu-id="e6d93-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="e6d93-210">Vad händer med distributionslistan om uppgraderingen från EAC misslyckas?</span><span class="sxs-lookup"><span data-stu-id="e6d93-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="e6d93-p119">Uppgraderingen utförs bara när anropet skickas till servern. Om uppgraderingen misslyckas förblir distributionslistorna intakta. De fungerar som de brukade.</span><span class="sxs-lookup"><span data-stu-id="e6d93-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>


