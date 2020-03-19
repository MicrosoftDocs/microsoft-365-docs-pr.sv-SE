---
title: Appar på Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: adb6423d5c014b5f02fc272f9653abebc14cf543
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42808589"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="ce6a0-103">Appar på Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ce6a0-103">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="ce6a0-104">Appar i allmänhet</span><span class="sxs-lookup"><span data-stu-id="ce6a0-104">Apps generally</span></span>

<span data-ttu-id="ce6a0-105">Microsoft innehåller vissa nyckelappar tillsammans med microsoft 365 E3- eller E5-licensen som krävs för att delta i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-105">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ce6a0-106">Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder att slutföra.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-106">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="ce6a0-107">Du kan också distribuera ytterligare appar som inte kommer från Microsoft till slutanvändarna för självbetjäning via företagsportalen eller en nödvändig bakgrundsinstallation, alla med Hjälp av Microsoft Intunes distributionspipeline.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-107">You can also deploy additional non-Microsoft apps to your end users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="ce6a0-108">Om du har den expertis en kan du migrera de appar du behöver själv. Alternativt hjälper Microsoft Consulting Services (MCS) eller leverantörer som inte kommer från Microsoft gärna dig med ett paketerings- och migreringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-108">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="ce6a0-109">Mer information om hur du arbetar med MCS finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-109">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="ce6a0-110">Appar från Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce6a0-110">Apps provided by Microsoft</span></span>

<span data-ttu-id="ce6a0-111">Med licensen för Microsoft Managed Desktop finns 64-bitarsversioner av apparna i Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote.) Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men du kan begära att de läggs till.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-111">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="ce6a0-112">Mer information om dessa appar finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter](../get-started/project-visio.md).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-112">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="ce6a0-113">Vad Microsoft gör för att stödja de appar vi tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="ce6a0-113">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="ce6a0-114">Microsoft tillhandahåller full service för distribution, uppdatering och support för de inkluderade Office 365 ProPlus-apparna.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-114">Microsoft will provide full service for the deployment, update, and support for the included Office 365 ProPlus apps.</span></span> <span data-ttu-id="ce6a0-115">Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men Microsoft Managed Desktop tillhandahåller distributionsgrupper som gör det möjligt för IT-administratören att hantera licenser och distribuera dessa program på rätt sätt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-115">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="ce6a0-116">Microsoft kommer att stödja slutanvändare av dessa program via microsoft managed desktop-supportkanalerna.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-116">Microsoft will support end users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="ce6a0-117">Vad du behöver göra för att stödja de appar vi tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="ce6a0-117">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="ce6a0-118">Det finns fortfarande vissa saker du behöver göra med dessa appar:</span><span class="sxs-lookup"><span data-stu-id="ce6a0-118">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="ce6a0-119">**Tilldela licenser** – Du är ansvarig för att hämta och tilldela lämpliga licenser till slutanvändare för Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-119">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to end users for Office 365 ProPlus.</span></span>
- <span data-ttu-id="ce6a0-120">**Lägg till användare i säkerhetsgrupper** – Om du använder Microsoft Project eller Visio måste IT-administratören lägga till dessa användare i lämpliga distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-120">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="ce6a0-121">IT-administratörer ansvarar också för att återkräva licenser från dessa användare om de lämnar företaget.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-121">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="ce6a0-122">**Distribuera Office 365-tillägg** – Om du behöver några tillägg för någon av Office 365 ProPlus-programmen distribuerar du dem centralt som alla andra Windows 32-appar.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-122">**Deploy Office 365 Addons** - If you need any Addons for any of the Office 365 ProPlus apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="ce6a0-123">Appar som du tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="ce6a0-123">Apps you provide</span></span>

<span data-ttu-id="ce6a0-124">Naturligtvis har du förmodligen ett antal andra appar du behöver för din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-124">Of course, you probably have a number of other apps you need for your business operations.</span></span> <span data-ttu-id="ce6a0-125">Dessa kan bara distribueras till Microsoft Managed Desktop-enheter med hjälp av Microsoft Intunes distributionspipeline.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-125">These can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="ce6a0-126">Om appen behöver den kan du få dem paketerade av en leverantör (som kan vara en icke-Microsoft-leverantör eller Microsoft Consulting Services (MCS)) eller om du har medel, kan du paketera dem själv.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-126">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="ce6a0-127">Du lägger sedan till dessa paket i Microsoft Managed Desktop-portalen och tilldelar dem till Azure Active Directory-grupper för att utlösa distributionen.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-127">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="ce6a0-128">Om du för närvarande distribuerar dina appar med Hjälp av Microsoft Endpoint Configuration Manager kan Microsoft Managed Desktop ge dig en fråga för att bedöma dina appar och upptäcka vilka som är redo att migrera till Microsoft Intune och vilka som kan kräva vissa Justering.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-128">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="ce6a0-129">Förbereda dina egna appar för att inkluderas i Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ce6a0-129">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="ce6a0-130">Granska dina appar och kontrollera:</span><span class="sxs-lookup"><span data-stu-id="ce6a0-130">Review your apps, checking:</span></span>

- <span data-ttu-id="ce6a0-131">Ingen av apparna är förbjuden eller har begränsat beteende, enligt beskrivningen i [Appkraven](https://aka.ms/app-req)för Microsoft Managed Desktop .</span><span class="sxs-lookup"><span data-stu-id="ce6a0-131">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="ce6a0-132">Appar måste vara klara för hantering av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-132">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="ce6a0-133">Mer information om detta finns i [Distributionav Windows 10-appar med Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) och [Lägg till appar i Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-133">For more about this, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="ce6a0-134">Andra krav för förpaketering, till exempel att tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-134">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="ce6a0-135">Bestäm hur appar ska paketeras</span><span class="sxs-lookup"><span data-stu-id="ce6a0-135">Decide how to package apps</span></span>

<span data-ttu-id="ce6a0-136">Vissa oberoende programvaruleverantörer kan kräva att dina appar paketeras innan de distribueras centralt.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-136">Some independent software vendors might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="ce6a0-137">"Förpackning" innebär att appens installationsprogram är konfigurerat med inställningar som licensnycklar, fjärrserverplatser eller skrivbordsgenvägar så att appen kan installeras i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-137">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="ce6a0-138">Det finns tre alternativ för att paketera dina appar:</span><span class="sxs-lookup"><span data-stu-id="ce6a0-138">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="ce6a0-139">Du kan paketera appar själv</span><span class="sxs-lookup"><span data-stu-id="ce6a0-139">You can package apps yourself</span></span>
- <span data-ttu-id="ce6a0-140">Du kan arbeta med en leverantör som inte kommer från Microsoft</span><span class="sxs-lookup"><span data-stu-id="ce6a0-140">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="ce6a0-141">Du kan interagera med MCS för att paketera dina appar.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-141">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="ce6a0-142">Arbeta med din Microsoft-kontorepresentant.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-142">Work with your Microsoft account representative.</span></span> <span data-ttu-id="ce6a0-143">Mer information finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-143">For more details, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>







## <a name="deploying-apps"></a><span data-ttu-id="ce6a0-144">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="ce6a0-144">Deploying apps</span></span>

<span data-ttu-id="ce6a0-145">Oavsett vilken metod du använder för att få appar paketerade, när det är klart, är du redo att följa stegen i [Distribuera appar till Microsoft Managed Desktop-enheter](../get-started/deploy-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-145">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


