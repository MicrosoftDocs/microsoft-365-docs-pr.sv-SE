---
title: Administrationscenter för Exchange i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Lär dig mer om webb hanterings gränssnittet i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652915"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="4c477-103">Administrationscenter för Exchange i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="4c477-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="4c477-104">Administrations centret för Exchange (UK) är en webbaserad hanterings konsol för fristående Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="4c477-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="4c477-105">Letar du efter Exchange Online-versionen av det här avsnittet?</span><span class="sxs-lookup"><span data-stu-id="4c477-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="4c477-106">Se [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4c477-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="4c477-107">Öppna EOP i UK</span><span class="sxs-lookup"><span data-stu-id="4c477-107">Open the EAC in EOP</span></span>

<span data-ttu-id="4c477-108">Fristående EOP-kunder kan komma åt UK på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="4c477-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="4c477-109">**Från administrations centret för Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="4c477-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="4c477-110">Gå till <https://admin.microsoft.com> och klicka på **Visa alla**.</span><span class="sxs-lookup"><span data-stu-id="4c477-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klicka på Visa alla i administrations centret för Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="4c477-112">I avsnittet **Administratörer** som visas klickar du på **alla administratörs Center**.</span><span class="sxs-lookup"><span data-stu-id="4c477-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klicka på alla administratörs Center i administrations centret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="4c477-114">På sidan **alla administratörs Center** som visas klickar du på **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="4c477-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="4c477-115">Gå direkt till `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="4c477-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="4c477-116">Vanliga gränssnitts element i EOP</span><span class="sxs-lookup"><span data-stu-id="4c477-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="4c477-117">I det här avsnittet beskrivs de användar gränssnitts element som finns i UK.</span><span class="sxs-lookup"><span data-stu-id="4c477-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="4c477-119">Fönstret funktion</span><span class="sxs-lookup"><span data-stu-id="4c477-119">Feature Pane</span></span>

<span data-ttu-id="4c477-120">Det här är den första navigerings nivån för de flesta uppgifter som du utför i UK.</span><span class="sxs-lookup"><span data-stu-id="4c477-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="4c477-121">Fönstret funktion är ordnad efter funktions områden.</span><span class="sxs-lookup"><span data-stu-id="4c477-121">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="4c477-122">**Mottagare**: här visas grupper och externa kontakter.</span><span class="sxs-lookup"><span data-stu-id="4c477-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="4c477-123">**Behörigheter**: här hanterar du administratörs roller.</span><span class="sxs-lookup"><span data-stu-id="4c477-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="4c477-124">**Hantering av efterlevnad**: här hittar du rapporten administratörs roll grupp och rapporten administratörs granskning.</span><span class="sxs-lookup"><span data-stu-id="4c477-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="4c477-125">**Skydd**: här kan du hantera principer mot skadlig program vara, standard princip för anslutnings filter och DKIM.</span><span class="sxs-lookup"><span data-stu-id="4c477-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c477-126">Du bör hantera principer mot skadlig program vara och standard princip för anslutnings filter i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4c477-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="4c477-127">Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md) och [Konfigurera ANSLUTNINGS filtrering i EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4c477-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="4c477-128">**E-postflöde**: här hanterar du regler för e-postflöde (kallas även transport regler), godkända domäner och kopplingar, samt var du kan gå till spåra meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4c477-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="4c477-129">**Hybrid**: här kan du köra [hybrid konfigurations guiden](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)och där du kan installera [Exchange Online PowerShell-modulen](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c477-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="4c477-130">TABB</span><span class="sxs-lookup"><span data-stu-id="4c477-130">Tabs</span></span>

<span data-ttu-id="4c477-131">Flikarna är den andra navigerings nivån.</span><span class="sxs-lookup"><span data-stu-id="4c477-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="4c477-132">Varje funktions område innehåller olika flikar, som representerar en funktion.</span><span class="sxs-lookup"><span data-stu-id="4c477-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="4c477-133">Raden</span><span class="sxs-lookup"><span data-stu-id="4c477-133">Toolbar</span></span>

<span data-ttu-id="4c477-134">När du klickar på de flesta flikar ser du ett verktygsfält.</span><span class="sxs-lookup"><span data-stu-id="4c477-134">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="4c477-135">Verktygsfältet innehåller ikoner som utför en viss åtgärd.</span><span class="sxs-lookup"><span data-stu-id="4c477-135">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="4c477-136">I följande tabell beskrivs ikonerna och deras åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4c477-136">The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="4c477-137">Ikonen</span><span class="sxs-lookup"><span data-stu-id="4c477-137">Icon</span></span>|<span data-ttu-id="4c477-138">Namn</span><span class="sxs-lookup"><span data-stu-id="4c477-138">Name</span></span>|<span data-ttu-id="4c477-139">Fattning</span><span class="sxs-lookup"><span data-stu-id="4c477-139">Action</span></span>|
|---|---|---|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="4c477-141">Lägga till, ny</span><span class="sxs-lookup"><span data-stu-id="4c477-141">Add, New</span></span>|<span data-ttu-id="4c477-142">Använd den här ikonen för att skapa ett nytt objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-142">Use this icon to create a new object.</span></span> <span data-ttu-id="4c477-143">Vissa av de här ikonerna har en associerad nedpilen som du kan klicka på för att visa ytterligare objekt som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="4c477-143">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Redigera-ikon](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="4c477-145">Redigera</span><span class="sxs-lookup"><span data-stu-id="4c477-145">Edit</span></span>|<span data-ttu-id="4c477-146">Använd den här ikonen om du vill redigera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-146">Use this icon to edit an object.</span></span>|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="4c477-148">Ta bort</span><span class="sxs-lookup"><span data-stu-id="4c477-148">Delete</span></span>|<span data-ttu-id="4c477-149">Använd den här ikonen om du vill ta bort ett objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-149">Use this icon to delete an object.</span></span> <span data-ttu-id="4c477-150">Vissa borttagnings ikoner är nedpilen som du kan klicka på för att visa fler alternativ.</span><span class="sxs-lookup"><span data-stu-id="4c477-150">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Sökikon](../../media/ITPro-EAC-.gif)|<span data-ttu-id="4c477-152">Sökmotor</span><span class="sxs-lookup"><span data-stu-id="4c477-152">Search</span></span>|<span data-ttu-id="4c477-153">Använd den här ikonen för att öppna en sökruta där du kan skriva Sök frasen för ett objekt som du vill hitta.</span><span class="sxs-lookup"><span data-stu-id="4c477-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ikonen uppdatera](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="4c477-155">Återställning</span><span class="sxs-lookup"><span data-stu-id="4c477-155">Refresh</span></span>|<span data-ttu-id="4c477-156">Använd den här ikonen för att uppdatera listvyn.</span><span class="sxs-lookup"><span data-stu-id="4c477-156">Use this icon to refresh the list view.</span></span>|
|![Ikonen fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="4c477-158">Fler alternativ</span><span class="sxs-lookup"><span data-stu-id="4c477-158">More options</span></span>|<span data-ttu-id="4c477-159">Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för den flikens objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-159">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="4c477-160">I **mottagarna \> användare** klickar du till exempel på den här ikonen för att utföra en **Avancerad sökning**.</span><span class="sxs-lookup"><span data-stu-id="4c477-160">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ikonen uppåtpil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikonen nedåtpil](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="4c477-163">UPPIL och NEDPIL</span><span class="sxs-lookup"><span data-stu-id="4c477-163">Up arrow and down arrow</span></span>|<span data-ttu-id="4c477-164">Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.</span><span class="sxs-lookup"><span data-stu-id="4c477-164">Use these icons to move an object's priority up or down.</span></span>|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="4c477-166">Bort</span><span class="sxs-lookup"><span data-stu-id="4c477-166">Remove</span></span>|<span data-ttu-id="4c477-167">Använd den här ikonen för att ta bort objekt från en lista.</span><span class="sxs-lookup"><span data-stu-id="4c477-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="4c477-168">Listvy</span><span class="sxs-lookup"><span data-stu-id="4c477-168">List View</span></span>

<span data-ttu-id="4c477-169">När du väljer en flik visas en listvy.</span><span class="sxs-lookup"><span data-stu-id="4c477-169">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="4c477-170">Den synliga gränsen för vyn UK visar ungefär 10 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-170">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="4c477-171">Dessutom är växling inkluderat för att du ska kunna göra en sida till resultatet.</span><span class="sxs-lookup"><span data-stu-id="4c477-171">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="4c477-172">Informations fönstret</span><span class="sxs-lookup"><span data-stu-id="4c477-172">Details Pane</span></span>

<span data-ttu-id="4c477-173">När du väljer ett objekt från listvyn visas information om objektet i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="4c477-173">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="4c477-174">I vissa fall innehåller informations fönstret hanterings uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4c477-174">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="4c477-175">Panel och hjälp med mig</span><span class="sxs-lookup"><span data-stu-id="4c477-175">Me tile and Help</span></span>

<span data-ttu-id="4c477-176">Med panelen **min** kan du logga ut från UK och logga in som en annan användare.</span><span class="sxs-lookup"><span data-stu-id="4c477-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="4c477-177">I den **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) nedrullningsbara menyn hjälp hjälp ikon kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="4c477-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="4c477-178">**Hjälp**: Klicka på ![ ikonen hjälp ](../../media/ITPro-EAC-HelpIcon.gif) för att visa onlinehjälpen.</span><span class="sxs-lookup"><span data-stu-id="4c477-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="4c477-179">**Feedback**: lämna feedback.</span><span class="sxs-lookup"><span data-stu-id="4c477-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="4c477-180">**Community**: Ställ en fråga för att hitta svar i Community-forumen.</span><span class="sxs-lookup"><span data-stu-id="4c477-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="4c477-181">**Inaktivera hjälp bubbla**: hjälp bubblan visar kontextuell hjälp för fält när du skapar eller redigerar ett objekt.</span><span class="sxs-lookup"><span data-stu-id="4c477-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="4c477-182">Du kan stänga av hjälp bubblan eller aktivera den om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="4c477-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="4c477-183">**Visa kommando loggning**: ett nytt fönster öppnas med motsvarande PowerShell-kommandon baserat på vad du konfigurerade i UK.</span><span class="sxs-lookup"><span data-stu-id="4c477-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="4c477-184">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="4c477-184">Supported Browsers</span></span>

<span data-ttu-id="4c477-185">Vi rekommenderar att du alltid använder de senaste webbläsarna, Office-klienterna och apparna för att få den bästa upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="4c477-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="4c477-186">Vi rekommenderar även att du installerar program varu uppdateringar när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="4c477-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="4c477-187">Mer information om webbläsare och system krav för tjänsten finns i [system krav för Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="4c477-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="4c477-188">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="4c477-188">Supported languages</span></span>

<span data-ttu-id="4c477-189">Följande språk stöds och är tillgängliga för UK i fristående EOP.</span><span class="sxs-lookup"><span data-stu-id="4c477-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="4c477-190">Amhariska</span><span class="sxs-lookup"><span data-stu-id="4c477-190">Amharic</span></span>
- <span data-ttu-id="4c477-191">Arabiska</span><span class="sxs-lookup"><span data-stu-id="4c477-191">Arabic</span></span>
- <span data-ttu-id="4c477-192">Baskiska (baskiska)</span><span class="sxs-lookup"><span data-stu-id="4c477-192">Basque (Basque)</span></span>
- <span data-ttu-id="4c477-193">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="4c477-193">Bengali (India)</span></span>
- <span data-ttu-id="4c477-194">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="4c477-194">Bulgarian</span></span>
- <span data-ttu-id="4c477-195">Catalan</span><span class="sxs-lookup"><span data-stu-id="4c477-195">Catalan</span></span>
- <span data-ttu-id="4c477-196">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="4c477-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="4c477-197">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="4c477-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="4c477-198">Croatian</span><span class="sxs-lookup"><span data-stu-id="4c477-198">Croatian</span></span>
- <span data-ttu-id="4c477-199">Czech</span><span class="sxs-lookup"><span data-stu-id="4c477-199">Czech</span></span>
- <span data-ttu-id="4c477-200">Danish</span><span class="sxs-lookup"><span data-stu-id="4c477-200">Danish</span></span>
- <span data-ttu-id="4c477-201">Dutch</span><span class="sxs-lookup"><span data-stu-id="4c477-201">Dutch</span></span>
- <span data-ttu-id="4c477-202">English</span><span class="sxs-lookup"><span data-stu-id="4c477-202">English</span></span>
- <span data-ttu-id="4c477-203">Estonian</span><span class="sxs-lookup"><span data-stu-id="4c477-203">Estonian</span></span>
- <span data-ttu-id="4c477-204">Filippinska (Filippinerna)</span><span class="sxs-lookup"><span data-stu-id="4c477-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="4c477-205">Finnish</span><span class="sxs-lookup"><span data-stu-id="4c477-205">Finnish</span></span>
- <span data-ttu-id="4c477-206">French</span><span class="sxs-lookup"><span data-stu-id="4c477-206">French</span></span>
- <span data-ttu-id="4c477-207">Galician</span><span class="sxs-lookup"><span data-stu-id="4c477-207">Galician</span></span>
- <span data-ttu-id="4c477-208">German</span><span class="sxs-lookup"><span data-stu-id="4c477-208">German</span></span>
- <span data-ttu-id="4c477-209">Greek</span><span class="sxs-lookup"><span data-stu-id="4c477-209">Greek</span></span>
- <span data-ttu-id="4c477-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="4c477-210">Gujarati</span></span>
- <span data-ttu-id="4c477-211">Hebrew</span><span class="sxs-lookup"><span data-stu-id="4c477-211">Hebrew</span></span>
- <span data-ttu-id="4c477-212">Hindi</span><span class="sxs-lookup"><span data-stu-id="4c477-212">Hindi</span></span>
- <span data-ttu-id="4c477-213">Hungarian</span><span class="sxs-lookup"><span data-stu-id="4c477-213">Hungarian</span></span>
- <span data-ttu-id="4c477-214">Isländska</span><span class="sxs-lookup"><span data-stu-id="4c477-214">Icelandic</span></span>
- <span data-ttu-id="4c477-215">Indonesian</span><span class="sxs-lookup"><span data-stu-id="4c477-215">Indonesian</span></span>
- <span data-ttu-id="4c477-216">Italian</span><span class="sxs-lookup"><span data-stu-id="4c477-216">Italian</span></span>
- <span data-ttu-id="4c477-217">Japanese</span><span class="sxs-lookup"><span data-stu-id="4c477-217">Japanese</span></span>
- <span data-ttu-id="4c477-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="4c477-218">Kannada</span></span>
- <span data-ttu-id="4c477-219">Kazakh</span><span class="sxs-lookup"><span data-stu-id="4c477-219">Kazakh</span></span>
- <span data-ttu-id="4c477-220">Swahili</span><span class="sxs-lookup"><span data-stu-id="4c477-220">Kiswahili</span></span>
- <span data-ttu-id="4c477-221">Korean</span><span class="sxs-lookup"><span data-stu-id="4c477-221">Korean</span></span>
- <span data-ttu-id="4c477-222">Latvian</span><span class="sxs-lookup"><span data-stu-id="4c477-222">Latvian</span></span>
- <span data-ttu-id="4c477-223">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="4c477-223">Lithuanian</span></span>
- <span data-ttu-id="4c477-224">Malajiska (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="4c477-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="4c477-225">Malajiska (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="4c477-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="4c477-226">Malayalam</span><span class="sxs-lookup"><span data-stu-id="4c477-226">Malayalam</span></span>
- <span data-ttu-id="4c477-227">Marathi</span><span class="sxs-lookup"><span data-stu-id="4c477-227">Marathi</span></span>
- <span data-ttu-id="4c477-228">Norska (bokmål)</span><span class="sxs-lookup"><span data-stu-id="4c477-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="4c477-229">Norska (nynorsk)</span><span class="sxs-lookup"><span data-stu-id="4c477-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="4c477-230">Odia</span><span class="sxs-lookup"><span data-stu-id="4c477-230">Oriya</span></span>
- <span data-ttu-id="4c477-231">Persiska</span><span class="sxs-lookup"><span data-stu-id="4c477-231">Persian</span></span>
- <span data-ttu-id="4c477-232">Polish</span><span class="sxs-lookup"><span data-stu-id="4c477-232">Polish</span></span>
- <span data-ttu-id="4c477-233">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="4c477-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="4c477-234">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="4c477-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="4c477-235">Romanian</span><span class="sxs-lookup"><span data-stu-id="4c477-235">Romanian</span></span>
- <span data-ttu-id="4c477-236">Russian</span><span class="sxs-lookup"><span data-stu-id="4c477-236">Russian</span></span>
- <span data-ttu-id="4c477-237">Serbiska (kyrillisk skrift, Serbien)</span><span class="sxs-lookup"><span data-stu-id="4c477-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="4c477-238">Serbiska (latinsk)</span><span class="sxs-lookup"><span data-stu-id="4c477-238">Serbian (Latin)</span></span>
- <span data-ttu-id="4c477-239">Slovak</span><span class="sxs-lookup"><span data-stu-id="4c477-239">Slovak</span></span>
- <span data-ttu-id="4c477-240">Slovenian</span><span class="sxs-lookup"><span data-stu-id="4c477-240">Slovenian</span></span>
- <span data-ttu-id="4c477-241">Spanish</span><span class="sxs-lookup"><span data-stu-id="4c477-241">Spanish</span></span>
- <span data-ttu-id="4c477-242">Swedish</span><span class="sxs-lookup"><span data-stu-id="4c477-242">Swedish</span></span>
- <span data-ttu-id="4c477-243">Tamilska</span><span class="sxs-lookup"><span data-stu-id="4c477-243">Tamil</span></span>
- <span data-ttu-id="4c477-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="4c477-244">Telugu</span></span>
- <span data-ttu-id="4c477-245">Thai</span><span class="sxs-lookup"><span data-stu-id="4c477-245">Thai</span></span>
- <span data-ttu-id="4c477-246">Turkish</span><span class="sxs-lookup"><span data-stu-id="4c477-246">Turkish</span></span>
- <span data-ttu-id="4c477-247">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="4c477-247">Ukrainian</span></span>
- <span data-ttu-id="4c477-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="4c477-248">Urdu</span></span>
- <span data-ttu-id="4c477-249">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="4c477-249">Vietnamese</span></span>
- <span data-ttu-id="4c477-250">Walesiska</span><span class="sxs-lookup"><span data-stu-id="4c477-250">Welsh</span></span>
