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
description: Lär dig mer om webbhanteringsgränssnittet i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 378754f2565604236f7ac33e471d1f991238d304
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209742"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="8cb39-103">Administrationscenter för Exchange i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="8cb39-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="8cb39-104">Exchange admin center (EAC) är en webbaserad hanteringskonsol för fristående Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8cb39-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="8cb39-105">Letar du efter Exchange Online-versionen av det här avsnittet?</span><span class="sxs-lookup"><span data-stu-id="8cb39-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="8cb39-106">Se [Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8cb39-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="8cb39-107">Öppna EAC i EOP</span><span class="sxs-lookup"><span data-stu-id="8cb39-107">Open the EAC in EOP</span></span>

<span data-ttu-id="8cb39-108">Fristående EOP-kunder kan komma åt EAC med hjälp av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="8cb39-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="8cb39-109">**Från Microsoft 365 admin center:**</span><span class="sxs-lookup"><span data-stu-id="8cb39-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="8cb39-110">Gå till <https://admin.microsoft.com> och klicka på Visa **alla**.</span><span class="sxs-lookup"><span data-stu-id="8cb39-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klicka på Visa alla i administrationscentret för Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="8cb39-112">Klicka på Alla **administrationscenter i** avsnittet **Administrationscenter**som visas.</span><span class="sxs-lookup"><span data-stu-id="8cb39-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klicka på Alla administrationscenter i administrationscentret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="8cb39-114">Klicka på **Exchange Online Protection**på sidan Alla **administrationscenter** som visas .</span><span class="sxs-lookup"><span data-stu-id="8cb39-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="8cb39-115">Gå direkt till `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="8cb39-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="8cb39-116">Gemensamma element för användargränssnitt i EAC i EOP</span><span class="sxs-lookup"><span data-stu-id="8cb39-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="8cb39-117">I det här avsnittet beskrivs de användargränssnittselement som finns i EAC.</span><span class="sxs-lookup"><span data-stu-id="8cb39-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="8cb39-119">Funktionsfönstret</span><span class="sxs-lookup"><span data-stu-id="8cb39-119">Feature Pane</span></span>

<span data-ttu-id="8cb39-120">Detta är den första navigeringsnivån för de flesta av de uppgifter som du utför i EAC.</span><span class="sxs-lookup"><span data-stu-id="8cb39-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="8cb39-121">Funktionsfönstret är ordnat efter funktionsområden.</span><span class="sxs-lookup"><span data-stu-id="8cb39-121">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="8cb39-122">**Mottagare**: Här ska du visa grupper och externa kontakter.</span><span class="sxs-lookup"><span data-stu-id="8cb39-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="8cb39-123">**Behörigheter**: Här hanterar du administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="8cb39-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="8cb39-124">**Efterlevnadshantering**: Här hittar du rapporten administratörsrollgrupp och rapporten administratörsgranskningslogg.</span><span class="sxs-lookup"><span data-stu-id="8cb39-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="8cb39-125">**Skydd**: Här kan du hantera principer mot skadlig kod, standardprincipen för anslutningsfilter och DKIM.</span><span class="sxs-lookup"><span data-stu-id="8cb39-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8cb39-126">Du bör hantera principer mot skadlig kod och standardprincipen för anslutningsfilter i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8cb39-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="8cb39-127">Mer information finns [i Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md) och Konfigurera [anslutningsfiltrering i EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8cb39-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="8cb39-128">**E-postflöde:** Här hanterar du regler för e-postflöde (kallas även transportregler), accepterade domäner och kopplingar samt var du kan gå för att köra meddelandespårning.</span><span class="sxs-lookup"><span data-stu-id="8cb39-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="8cb39-129">**Hybrid:** Här kan du köra [hybridkonfigurationsguiden](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)och där du kan installera [Exchange Online PowerShell-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8cb39-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="8cb39-130">Flikar</span><span class="sxs-lookup"><span data-stu-id="8cb39-130">Tabs</span></span>

<span data-ttu-id="8cb39-131">Flikarna är din andra navigeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="8cb39-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="8cb39-132">Vart och ett av funktionsområdena innehåller olika flikar, som var och en representerar en funktion.</span><span class="sxs-lookup"><span data-stu-id="8cb39-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="8cb39-133">Verktygsfältet</span><span class="sxs-lookup"><span data-stu-id="8cb39-133">Toolbar</span></span>

<span data-ttu-id="8cb39-134">När du klickar på de flesta flikar visas ett verktygsfält.</span><span class="sxs-lookup"><span data-stu-id="8cb39-134">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="8cb39-135">Verktygsfältet har ikoner som utför en viss åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8cb39-135">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="8cb39-136">I följande tabell beskrivs ikonerna och deras åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8cb39-136">The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="8cb39-137">**Ikonen**</span><span class="sxs-lookup"><span data-stu-id="8cb39-137">**Icon**</span></span>|<span data-ttu-id="8cb39-138">**Namn**</span><span class="sxs-lookup"><span data-stu-id="8cb39-138">**Name**</span></span>|<span data-ttu-id="8cb39-139">**Åtgärder**</span><span class="sxs-lookup"><span data-stu-id="8cb39-139">**Action**</span></span>|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="8cb39-141">Lägg till, Nytt</span><span class="sxs-lookup"><span data-stu-id="8cb39-141">Add, New</span></span>|<span data-ttu-id="8cb39-142">Använd den här ikonen om du vill skapa ett nytt objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-142">Use this icon to create a new object.</span></span> <span data-ttu-id="8cb39-143">Vissa av dessa ikoner har en associerad nedpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="8cb39-143">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Ikonen Redigera](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="8cb39-145">Redigera</span><span class="sxs-lookup"><span data-stu-id="8cb39-145">Edit</span></span>|<span data-ttu-id="8cb39-146">Använd den här ikonen för att redigera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-146">Use this icon to edit an object.</span></span>|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="8cb39-148">Ta bort</span><span class="sxs-lookup"><span data-stu-id="8cb39-148">Delete</span></span>|<span data-ttu-id="8cb39-149">Använd den här ikonen om du vill ta bort ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-149">Use this icon to delete an object.</span></span> <span data-ttu-id="8cb39-150">Vissa borttagningsikoner har en nedpil som du kan klicka på för att visa ytterligare alternativ.</span><span class="sxs-lookup"><span data-stu-id="8cb39-150">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Sökikon](../../media/ITPro-EAC-.gif)|<span data-ttu-id="8cb39-152">Sök</span><span class="sxs-lookup"><span data-stu-id="8cb39-152">Search</span></span>|<span data-ttu-id="8cb39-153">Använd den här ikonen för att öppna en sökruta där du kan skriva sökfrasen för ett objekt som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="8cb39-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ikonen Uppdatera](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="8cb39-155">Återställning</span><span class="sxs-lookup"><span data-stu-id="8cb39-155">Refresh</span></span>|<span data-ttu-id="8cb39-156">Använd den här ikonen för att uppdatera listvyn.</span><span class="sxs-lookup"><span data-stu-id="8cb39-156">Use this icon to refresh the list view.</span></span>|
|![Ikonen Fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="8cb39-158">Fler alternativ</span><span class="sxs-lookup"><span data-stu-id="8cb39-158">More options</span></span>|<span data-ttu-id="8cb39-159">Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för flikens objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-159">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="8cb39-160">I Mottagare **visar \> användare** som klickar på den här ikonen alternativet för att utföra en **avancerad sökning**.</span><span class="sxs-lookup"><span data-stu-id="8cb39-160">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ikon för uppåtpil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikon för nedpil](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="8cb39-163">Uppil och nedpil</span><span class="sxs-lookup"><span data-stu-id="8cb39-163">Up arrow and down arrow</span></span>|<span data-ttu-id="8cb39-164">Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-164">Use these icons to move an object's priority up or down.</span></span>|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="8cb39-166">Ta bort</span><span class="sxs-lookup"><span data-stu-id="8cb39-166">Remove</span></span>|<span data-ttu-id="8cb39-167">Använd den här ikonen om du vill ta bort objekt från en lista.</span><span class="sxs-lookup"><span data-stu-id="8cb39-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="8cb39-168">Listvy</span><span class="sxs-lookup"><span data-stu-id="8cb39-168">List View</span></span>

<span data-ttu-id="8cb39-169">När du väljer en flik visas i de flesta fall en listvy.</span><span class="sxs-lookup"><span data-stu-id="8cb39-169">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="8cb39-170">Den synliga gränsen med EAC-listvyn är cirka 10 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-170">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="8cb39-171">Dessutom ingår personsökning så att du kan bläddra till resultat.</span><span class="sxs-lookup"><span data-stu-id="8cb39-171">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="8cb39-172">Informationsfönstret</span><span class="sxs-lookup"><span data-stu-id="8cb39-172">Details Pane</span></span>

<span data-ttu-id="8cb39-173">När du markerar ett objekt i listvyn visas information om objektet i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8cb39-173">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="8cb39-174">I vissa fall innehåller informationsfönstret hanteringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="8cb39-174">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="8cb39-175">Jag kakel och hjälp</span><span class="sxs-lookup"><span data-stu-id="8cb39-175">Me tile and Help</span></span>

<span data-ttu-id="8cb39-176">Med panelen **Jag** kan du logga ut EAC:en och logga in som en annan användare.</span><span class="sxs-lookup"><span data-stu-id="8cb39-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="8cb39-177">På **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) den nedrullningssvänliga menyn Hjälpikon kan du utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="8cb39-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="8cb39-178">**Hjälp:** Klicka på ![ ](../../media/ITPro-EAC-HelpIcon.gif) Hjälpikonen för att visa hjälpinnehållet online.</span><span class="sxs-lookup"><span data-stu-id="8cb39-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="8cb39-179">**Feedback**: Lämna feedback.</span><span class="sxs-lookup"><span data-stu-id="8cb39-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="8cb39-180">**Community**: Post en fråga för att hitta svar i community forum.</span><span class="sxs-lookup"><span data-stu-id="8cb39-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="8cb39-181">**Inaktivera hjälpbubbla:** Hjälpbubblan visar sammanhangsberoende hjälp för fält när du skapar eller redigerar ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8cb39-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="8cb39-182">Du kan stänga av hjälpbubblan eller slå på den om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="8cb39-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="8cb39-183">**Visa kommandologgning:** Ett nytt fönster öppnas som visar motsvarande PowerShell-kommandon baserat på vad du har konfigurerat i EAC.</span><span class="sxs-lookup"><span data-stu-id="8cb39-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="8cb39-184">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="8cb39-184">Supported Browsers</span></span>

<span data-ttu-id="8cb39-185">För bästa möjliga upplevelse av EAC rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och apparna.</span><span class="sxs-lookup"><span data-stu-id="8cb39-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="8cb39-186">Vi rekommenderar också att du installerar programuppdateringar när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="8cb39-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="8cb39-187">Mer information om de webbläsare och systemkrav som stöds för tjänsten finns i [Systemkrav för Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="8cb39-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="8cb39-188">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="8cb39-188">Supported languages</span></span>

<span data-ttu-id="8cb39-189">Följande språk stöds och är tillgängliga för EAC i fristående EOP.</span><span class="sxs-lookup"><span data-stu-id="8cb39-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="8cb39-190">Amhariska</span><span class="sxs-lookup"><span data-stu-id="8cb39-190">Amharic</span></span>

- <span data-ttu-id="8cb39-191">Arabiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-191">Arabic</span></span>

- <span data-ttu-id="8cb39-192">Baskiska (baskiska)</span><span class="sxs-lookup"><span data-stu-id="8cb39-192">Basque (Basque)</span></span>

- <span data-ttu-id="8cb39-193">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="8cb39-193">Bengali (India)</span></span>

- <span data-ttu-id="8cb39-194">Bulgariska</span><span class="sxs-lookup"><span data-stu-id="8cb39-194">Bulgarian</span></span>

- <span data-ttu-id="8cb39-195">Katalanska</span><span class="sxs-lookup"><span data-stu-id="8cb39-195">Catalan</span></span>

- <span data-ttu-id="8cb39-196">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="8cb39-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="8cb39-197">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="8cb39-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="8cb39-198">Kroatiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-198">Croatian</span></span>

- <span data-ttu-id="8cb39-199">Tjeckiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-199">Czech</span></span>

- <span data-ttu-id="8cb39-200">Danska</span><span class="sxs-lookup"><span data-stu-id="8cb39-200">Danish</span></span>

- <span data-ttu-id="8cb39-201">Nederländska</span><span class="sxs-lookup"><span data-stu-id="8cb39-201">Dutch</span></span>

- <span data-ttu-id="8cb39-202">Nederländska</span><span class="sxs-lookup"><span data-stu-id="8cb39-202">Dutch</span></span>

- <span data-ttu-id="8cb39-203">Engelska</span><span class="sxs-lookup"><span data-stu-id="8cb39-203">English</span></span>

- <span data-ttu-id="8cb39-204">Estniska</span><span class="sxs-lookup"><span data-stu-id="8cb39-204">Estonian</span></span>

- <span data-ttu-id="8cb39-205">Filippinska (Filippinerna)</span><span class="sxs-lookup"><span data-stu-id="8cb39-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="8cb39-206">Finska</span><span class="sxs-lookup"><span data-stu-id="8cb39-206">Finnish</span></span>

- <span data-ttu-id="8cb39-207">Franska</span><span class="sxs-lookup"><span data-stu-id="8cb39-207">French</span></span>

- <span data-ttu-id="8cb39-208">Galiciska</span><span class="sxs-lookup"><span data-stu-id="8cb39-208">Galician</span></span>

- <span data-ttu-id="8cb39-209">Tyska</span><span class="sxs-lookup"><span data-stu-id="8cb39-209">German</span></span>

- <span data-ttu-id="8cb39-210">Grekiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-210">Greek</span></span>

- <span data-ttu-id="8cb39-211">Gujarati</span><span class="sxs-lookup"><span data-stu-id="8cb39-211">Gujarati</span></span>

- <span data-ttu-id="8cb39-212">Hebreiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-212">Hebrew</span></span>

- <span data-ttu-id="8cb39-213">Hindi</span><span class="sxs-lookup"><span data-stu-id="8cb39-213">Hindi</span></span>

- <span data-ttu-id="8cb39-214">Ungerska</span><span class="sxs-lookup"><span data-stu-id="8cb39-214">Hungarian</span></span>

- <span data-ttu-id="8cb39-215">Isländska</span><span class="sxs-lookup"><span data-stu-id="8cb39-215">Icelandic</span></span>

- <span data-ttu-id="8cb39-216">Indonesiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-216">Indonesian</span></span>

- <span data-ttu-id="8cb39-217">Italienska</span><span class="sxs-lookup"><span data-stu-id="8cb39-217">Italian</span></span>

- <span data-ttu-id="8cb39-218">Japanska</span><span class="sxs-lookup"><span data-stu-id="8cb39-218">Japanese</span></span>

- <span data-ttu-id="8cb39-219">Kannada</span><span class="sxs-lookup"><span data-stu-id="8cb39-219">Kannada</span></span>

- <span data-ttu-id="8cb39-220">Kazakiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-220">Kazakh</span></span>

- <span data-ttu-id="8cb39-221">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="8cb39-221">Kiswahili</span></span>

- <span data-ttu-id="8cb39-222">Koreanska</span><span class="sxs-lookup"><span data-stu-id="8cb39-222">Korean</span></span>

- <span data-ttu-id="8cb39-223">Lettiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-223">Latvian</span></span>

- <span data-ttu-id="8cb39-224">Litauiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-224">Lithuanian</span></span>

- <span data-ttu-id="8cb39-225">Malajiska (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="8cb39-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="8cb39-226">Malajiska (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="8cb39-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="8cb39-227">Malayalam</span><span class="sxs-lookup"><span data-stu-id="8cb39-227">Malayalam</span></span>

- <span data-ttu-id="8cb39-228">Marathi</span><span class="sxs-lookup"><span data-stu-id="8cb39-228">Marathi</span></span>

- <span data-ttu-id="8cb39-229">Norska (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="8cb39-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="8cb39-230">Norska (nynorsk)</span><span class="sxs-lookup"><span data-stu-id="8cb39-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="8cb39-231">Oriya</span><span class="sxs-lookup"><span data-stu-id="8cb39-231">Oriya</span></span>

- <span data-ttu-id="8cb39-232">Persiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-232">Persian</span></span>

- <span data-ttu-id="8cb39-233">Polska</span><span class="sxs-lookup"><span data-stu-id="8cb39-233">Polish</span></span>

- <span data-ttu-id="8cb39-234">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="8cb39-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="8cb39-235">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="8cb39-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="8cb39-236">Rumänska</span><span class="sxs-lookup"><span data-stu-id="8cb39-236">Romanian</span></span>

- <span data-ttu-id="8cb39-237">Ryska</span><span class="sxs-lookup"><span data-stu-id="8cb39-237">Russian</span></span>

- <span data-ttu-id="8cb39-238">Serbiska (kyrilliska, Serbien)</span><span class="sxs-lookup"><span data-stu-id="8cb39-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="8cb39-239">Serbiska (latin)</span><span class="sxs-lookup"><span data-stu-id="8cb39-239">Serbian (Latin)</span></span>

- <span data-ttu-id="8cb39-240">Slovakiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-240">Slovak</span></span>

- <span data-ttu-id="8cb39-241">Slovenska</span><span class="sxs-lookup"><span data-stu-id="8cb39-241">Slovenian</span></span>

- <span data-ttu-id="8cb39-242">Spanska</span><span class="sxs-lookup"><span data-stu-id="8cb39-242">Spanish</span></span>

- <span data-ttu-id="8cb39-243">Svenska</span><span class="sxs-lookup"><span data-stu-id="8cb39-243">Swedish</span></span>

- <span data-ttu-id="8cb39-244">Tamilska</span><span class="sxs-lookup"><span data-stu-id="8cb39-244">Tamil</span></span>

- <span data-ttu-id="8cb39-245">Telugu</span><span class="sxs-lookup"><span data-stu-id="8cb39-245">Telugu</span></span>

- <span data-ttu-id="8cb39-246">Thai</span><span class="sxs-lookup"><span data-stu-id="8cb39-246">Thai</span></span>

- <span data-ttu-id="8cb39-247">Turkiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-247">Turkish</span></span>

- <span data-ttu-id="8cb39-248">Ukrainska</span><span class="sxs-lookup"><span data-stu-id="8cb39-248">Ukrainian</span></span>

- <span data-ttu-id="8cb39-249">Urdu</span><span class="sxs-lookup"><span data-stu-id="8cb39-249">Urdu</span></span>

- <span data-ttu-id="8cb39-250">Vietnamesiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-250">Vietnamese</span></span>

- <span data-ttu-id="8cb39-251">Walesiska</span><span class="sxs-lookup"><span data-stu-id="8cb39-251">Welsh</span></span>
