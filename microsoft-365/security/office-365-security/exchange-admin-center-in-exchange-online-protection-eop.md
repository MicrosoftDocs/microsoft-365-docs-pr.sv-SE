---
title: Exchange administrationscenter i Exchange Online Protection
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
description: Administrationscentret för Exchange (EAC) är den webbaserade hanteringskonsolen för Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 3b5fb014e56a9928d58abffd5e4c96e1eef463ad
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808613"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="dd0ae-103">Exchange administrationscenter i Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dd0ae-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="dd0ae-104">Administrationscentret för Exchange (EAC) är den webbaserade hanteringskonsolen för Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="dd0ae-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="dd0ae-105">Letar du efter Exchange Server-versionen av det här avsnittet?</span><span class="sxs-lookup"><span data-stu-id="dd0ae-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="dd0ae-106">Se [Administrationscenter för Exchange i Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="dd0ae-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="dd0ae-107">Letar du efter Exchange Online-versionen av det här avsnittet?</span><span class="sxs-lookup"><span data-stu-id="dd0ae-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="dd0ae-108">Se [Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="dd0ae-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="dd0ae-109">Tillgång till EAC</span><span class="sxs-lookup"><span data-stu-id="dd0ae-109">Accessing the EAC</span></span>

<span data-ttu-id="dd0ae-110">I de flesta fall kommer EOP-kunder åt EAC via administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="dd0ae-111">Du hittar en länk till EOP i den nedrullningsbara menyn i **panelen Admin,** som ligger bredvid panelen **Jag.**</span><span class="sxs-lookup"><span data-stu-id="dd0ae-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="dd0ae-112">Klicka på panelen **Admin** och välj **Exchange Online Protection** på den nedrullningsbara menyn som ska tas till EAC.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop-down menu to be taken to the EAC.</span></span>

<span data-ttu-id="dd0ae-113">Du kan också komma åt inloggningssidan för EAC direkt via följande webbadress: `https://admin.protection.outlook.com/ecp/<companydomain>`.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-113">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`.</span></span> <span data-ttu-id="dd0ae-114">Till exempel `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-114">For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`.</span></span> <span data-ttu-id="dd0ae-115">När du har angett dina användaruppgifter kommer du att tas direkt in i EAC.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-115">After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="dd0ae-116">Vanliga användargränssnittselement i EAC</span><span class="sxs-lookup"><span data-stu-id="dd0ae-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="dd0ae-117">I det här avsnittet beskrivs de element i användargränssnittet som finns i EAC.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="dd0ae-119">Funktionsfönstret</span><span class="sxs-lookup"><span data-stu-id="dd0ae-119">Feature Pane</span></span>

<span data-ttu-id="dd0ae-120">Detta är den första navigeringsnivån för de flesta av de uppgifter du utför i EAC.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="dd0ae-121">Funktionsfönstret är organiserat efter funktionsområden.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-121">The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="dd0ae-122">**Mottagare**: Här visar du interna användare och externa kontakter.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="dd0ae-123">**Behörigheter**: Här hanterar du administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="dd0ae-124">**Efterlevnadshantering**: Här hittar du granskningsloggar och rapporter, till exempel rollen administratörsgruppsrapport.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="dd0ae-125">**Skydd**: Här hanterar du skydd mot skadlig kod och skräppost för din organisation samt hanterar meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="dd0ae-126">**E-postflöde:** Här hanterar du regler, accepterade domäner och kopplingar samt vart du ska gå för att utföra meddelandespårning.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="dd0ae-127">Flikar</span><span class="sxs-lookup"><span data-stu-id="dd0ae-127">Tabs</span></span>

<span data-ttu-id="dd0ae-128">Flikarna är din andra navigeringsnivå.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="dd0ae-129">Vart och ett av funktionsområdena innehåller olika flikar, som var och en representerar en funktion.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="dd0ae-130">Verktygsfältet</span><span class="sxs-lookup"><span data-stu-id="dd0ae-130">Toolbar</span></span>

<span data-ttu-id="dd0ae-131">När du klickar på de flesta flikar visas ett verktygsfält.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-131">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="dd0ae-132">Verktygsfältet har ikoner som utför en viss åtgärd.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-132">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="dd0ae-133">I följande tabell beskrivs ikonerna och deras handlingar.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-133">The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="dd0ae-134">**Ikonen**</span><span class="sxs-lookup"><span data-stu-id="dd0ae-134">**Icon**</span></span>|<span data-ttu-id="dd0ae-135">**Namn**</span><span class="sxs-lookup"><span data-stu-id="dd0ae-135">**Name**</span></span>|<span data-ttu-id="dd0ae-136">**Åtgärder**</span><span class="sxs-lookup"><span data-stu-id="dd0ae-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Lägg till ikon](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="dd0ae-138">Lägg till, Ny</span><span class="sxs-lookup"><span data-stu-id="dd0ae-138">Add, New</span></span>|<span data-ttu-id="dd0ae-139">Använd den här ikonen om du vill skapa ett nytt objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-139">Use this icon to create a new object.</span></span> <span data-ttu-id="dd0ae-140">Vissa av dessa ikoner har en associerad nedpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-140">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Redigera ikon](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="dd0ae-142">Redigera</span><span class="sxs-lookup"><span data-stu-id="dd0ae-142">Edit</span></span>|<span data-ttu-id="dd0ae-143">Använd den här ikonen om du vill redigera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-143">Use this icon to edit an object.</span></span>|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="dd0ae-145">Ta bort</span><span class="sxs-lookup"><span data-stu-id="dd0ae-145">Delete</span></span>|<span data-ttu-id="dd0ae-146">Använd den här ikonen om du vill ta bort ett objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-146">Use this icon to delete an object.</span></span> <span data-ttu-id="dd0ae-147">Vissa borttagningsikoner har en nedpil som du kan klicka på för att visa ytterligare alternativ.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-147">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Sökikon](../../media/ITPro-EAC-.gif)|<span data-ttu-id="dd0ae-149">Sök</span><span class="sxs-lookup"><span data-stu-id="dd0ae-149">Search</span></span>|<span data-ttu-id="dd0ae-150">Använd den här ikonen om du vill öppna en sökruta där du kan skriva sökfrasen efter ett objekt som du vill hitta.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ikon för uppdatering](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="dd0ae-152">Uppdatera</span><span class="sxs-lookup"><span data-stu-id="dd0ae-152">Refresh</span></span>|<span data-ttu-id="dd0ae-153">Använd den här ikonen för att uppdatera listvyn.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-153">Use this icon to refresh the list view.</span></span>|
|![Ikon för fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="dd0ae-155">Fler alternativ</span><span class="sxs-lookup"><span data-stu-id="dd0ae-155">More options</span></span>|<span data-ttu-id="dd0ae-156">Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för den flikens objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-156">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="dd0ae-157">I \*\* \> Mottagare användare\*\* klickar på den här ikonen visar alternativet att utföra en **avancerad sökning**.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-157">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ikon för upppil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikon för nedpil](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="dd0ae-160">Upppil och nedåtpil</span><span class="sxs-lookup"><span data-stu-id="dd0ae-160">Up arrow and down arrow</span></span>|<span data-ttu-id="dd0ae-161">Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-161">Use these icons to move an object's priority up or down.</span></span>|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="dd0ae-163">Ta bort</span><span class="sxs-lookup"><span data-stu-id="dd0ae-163">Remove</span></span>|<span data-ttu-id="dd0ae-164">Använd den här ikonen om du vill ta bort objekt från en lista.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="dd0ae-165">Listvy</span><span class="sxs-lookup"><span data-stu-id="dd0ae-165">List View</span></span>

<span data-ttu-id="dd0ae-166">När du väljer en flik visas en listvy i de flesta fall.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-166">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="dd0ae-167">Den synliga gränsen med EAC-listvyn är cirka 10 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-167">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="dd0ae-168">Dessutom inkluderas växling så att du kan bläddra till resultat.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-168">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="dd0ae-169">Informationsfönstret</span><span class="sxs-lookup"><span data-stu-id="dd0ae-169">Details Pane</span></span>

<span data-ttu-id="dd0ae-170">När du markerar ett objekt i listvyn visas information om objektet i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-170">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="dd0ae-171">I vissa fall innehåller informationsfönstret hanteringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-171">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="dd0ae-172">Jag kakel och hjälp</span><span class="sxs-lookup"><span data-stu-id="dd0ae-172">Me tile and Help</span></span>

<span data-ttu-id="dd0ae-173">Med panelen **Me** kan du logga ut eac och logga in som en annan användare.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-173">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="dd0ae-174">På **Help**den nedrullningsbara hjälpikonen](../../media/ITPro-EAC-HelpIcon.gif) kan du utföra följande åtgärder:![</span><span class="sxs-lookup"><span data-stu-id="dd0ae-174">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="dd0ae-175">**Hjälp**: ![Klicka](../../media/ITPro-EAC-HelpIcon.gif) på Hjälpikonen om du vill visa hjälpinnehållet online.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-175">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="dd0ae-176">**Inaktivera hjälpbubbla:** Hjälpbubblan visar kontextuell hjälp för fält när du skapar eller redigerar ett objekt.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="dd0ae-177">Du kan stänga av hjälpbubblan eller aktivera den om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="dd0ae-178">**Upphovsrätt**: Klicka på denna länk för att läsa upphovsrättsmeddelandet för Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="dd0ae-179">**Sekretess:** Klicka för att läsa sekretesspolicyn för Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="dd0ae-180">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="dd0ae-180">Supported Browsers</span></span>

<span data-ttu-id="dd0ae-181">För bästa upplevelse med EAC rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och apparna.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="dd0ae-182">Vi rekommenderar också att du installerar programuppdateringar när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="dd0ae-183">Mer information om webbläsare och systemkrav som stöds för tjänsten finns i [Systemkrav för Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="dd0ae-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="dd0ae-184">Språk som stöds i EOP</span><span class="sxs-lookup"><span data-stu-id="dd0ae-184">Supported languages in EOP</span></span>

<span data-ttu-id="dd0ae-185">Följande språk stöds och är tillgängliga för Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="dd0ae-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="dd0ae-186">Amhariska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-186">Amharic</span></span>

- <span data-ttu-id="dd0ae-187">Arabiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-187">Arabic</span></span>

- <span data-ttu-id="dd0ae-188">Baskiska (baskiska)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-188">Basque (Basque)</span></span>

- <span data-ttu-id="dd0ae-189">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-189">Bengali (India)</span></span>

- <span data-ttu-id="dd0ae-190">Bulgariska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-190">Bulgarian</span></span>

- <span data-ttu-id="dd0ae-191">Katalanska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-191">Catalan</span></span>

- <span data-ttu-id="dd0ae-192">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="dd0ae-193">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="dd0ae-194">Kroatiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-194">Croatian</span></span>

- <span data-ttu-id="dd0ae-195">Tjeckiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-195">Czech</span></span>

- <span data-ttu-id="dd0ae-196">Danska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-196">Danish</span></span>

- <span data-ttu-id="dd0ae-197">Nederländska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-197">Dutch</span></span>

- <span data-ttu-id="dd0ae-198">Nederländska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-198">Dutch</span></span>

- <span data-ttu-id="dd0ae-199">Engelska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-199">English</span></span>

- <span data-ttu-id="dd0ae-200">Estniska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-200">Estonian</span></span>

- <span data-ttu-id="dd0ae-201">Filippinska (Filippinerna)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="dd0ae-202">Finska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-202">Finnish</span></span>

- <span data-ttu-id="dd0ae-203">Franska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-203">French</span></span>

- <span data-ttu-id="dd0ae-204">Galiciska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-204">Galician</span></span>

- <span data-ttu-id="dd0ae-205">Tyska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-205">German</span></span>

- <span data-ttu-id="dd0ae-206">Grekiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-206">Greek</span></span>

- <span data-ttu-id="dd0ae-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="dd0ae-207">Gujarati</span></span>

- <span data-ttu-id="dd0ae-208">Hebreiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-208">Hebrew</span></span>

- <span data-ttu-id="dd0ae-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="dd0ae-209">Hindi</span></span>

- <span data-ttu-id="dd0ae-210">Ungerska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-210">Hungarian</span></span>

- <span data-ttu-id="dd0ae-211">Isländska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-211">Icelandic</span></span>

- <span data-ttu-id="dd0ae-212">Indonesiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-212">Indonesian</span></span>

- <span data-ttu-id="dd0ae-213">Italienska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-213">Italian</span></span>

- <span data-ttu-id="dd0ae-214">Japanska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-214">Japanese</span></span>

- <span data-ttu-id="dd0ae-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="dd0ae-215">Kannada</span></span>

- <span data-ttu-id="dd0ae-216">Kazakiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-216">Kazakh</span></span>

- <span data-ttu-id="dd0ae-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="dd0ae-217">Kiswahili</span></span>

- <span data-ttu-id="dd0ae-218">Koreanska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-218">Korean</span></span>

- <span data-ttu-id="dd0ae-219">Lettiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-219">Latvian</span></span>

- <span data-ttu-id="dd0ae-220">Litauiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-220">Lithuanian</span></span>

- <span data-ttu-id="dd0ae-221">Malajiska (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="dd0ae-222">Malajiska (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="dd0ae-223">Malayalam</span><span class="sxs-lookup"><span data-stu-id="dd0ae-223">Malayalam</span></span>

- <span data-ttu-id="dd0ae-224">Marathi</span><span class="sxs-lookup"><span data-stu-id="dd0ae-224">Marathi</span></span>

- <span data-ttu-id="dd0ae-225">Norska (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="dd0ae-226">Norska (nynorsk)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="dd0ae-227">Oriya</span><span class="sxs-lookup"><span data-stu-id="dd0ae-227">Oriya</span></span>

- <span data-ttu-id="dd0ae-228">Persiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-228">Persian</span></span>

- <span data-ttu-id="dd0ae-229">Polska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-229">Polish</span></span>

- <span data-ttu-id="dd0ae-230">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="dd0ae-231">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="dd0ae-232">Rumänska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-232">Romanian</span></span>

- <span data-ttu-id="dd0ae-233">Ryska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-233">Russian</span></span>

- <span data-ttu-id="dd0ae-234">Serbiska (kyrilliska, Serbien)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="dd0ae-235">Serbiska (latin)</span><span class="sxs-lookup"><span data-stu-id="dd0ae-235">Serbian (Latin)</span></span>

- <span data-ttu-id="dd0ae-236">Slovakiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-236">Slovak</span></span>

- <span data-ttu-id="dd0ae-237">Slovenska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-237">Slovenian</span></span>

- <span data-ttu-id="dd0ae-238">Spanska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-238">Spanish</span></span>

- <span data-ttu-id="dd0ae-239">Svenska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-239">Swedish</span></span>

- <span data-ttu-id="dd0ae-240">Tamilska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-240">Tamil</span></span>

- <span data-ttu-id="dd0ae-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="dd0ae-241">Telugu</span></span>

- <span data-ttu-id="dd0ae-242">Thai</span><span class="sxs-lookup"><span data-stu-id="dd0ae-242">Thai</span></span>

- <span data-ttu-id="dd0ae-243">Turkiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-243">Turkish</span></span>

- <span data-ttu-id="dd0ae-244">Ukrainska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-244">Ukrainian</span></span>

- <span data-ttu-id="dd0ae-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="dd0ae-245">Urdu</span></span>

- <span data-ttu-id="dd0ae-246">Vietnamesiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-246">Vietnamese</span></span>

- <span data-ttu-id="dd0ae-247">Walesiska</span><span class="sxs-lookup"><span data-stu-id="dd0ae-247">Welsh</span></span>


