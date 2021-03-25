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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Läs mer om webbhanteringsgränssnittet i fristående EOP (Exchange Online Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207477"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="8205b-103">Administrationscenter för Exchange i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="8205b-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8205b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="8205b-104">**Applies to**</span></span>
-  [<span data-ttu-id="8205b-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="8205b-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="8205b-106">Administrationscentret för Exchange (EAC) är en webbaserad hanteringskonsol för fristående Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8205b-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="8205b-107">Letar du efter Exchange Online-versionen av det här avsnittet?</span><span class="sxs-lookup"><span data-stu-id="8205b-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="8205b-108">Se [Administrationscenter för Exchange i Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="8205b-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="8205b-109">Öppna EAC i EOP</span><span class="sxs-lookup"><span data-stu-id="8205b-109">Open the EAC in EOP</span></span>

<span data-ttu-id="8205b-110">Fristående EOP-kunder kan komma åt EAC på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="8205b-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="8205b-111">**Från administrationscentret för Microsoft 365:**</span><span class="sxs-lookup"><span data-stu-id="8205b-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="8205b-112">Gå till <https://admin.microsoft.com> och klicka på Visa **alla.**</span><span class="sxs-lookup"><span data-stu-id="8205b-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klicka på Visa alla i administrationscentret för Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="8205b-114">I avsnittet **Administrationscenter** som visas klickar du på **Alla administrationscenter.**</span><span class="sxs-lookup"><span data-stu-id="8205b-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klicka på Alla administrationscenter i administrationscentret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="8205b-116">Klicka på Exchange Online **Protection** på sidan Alla **administrationscenter som visas.**</span><span class="sxs-lookup"><span data-stu-id="8205b-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="8205b-117">Gå direkt till `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="8205b-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="8205b-118">Vanliga element i användargränssnittet i EAC i EOP</span><span class="sxs-lookup"><span data-stu-id="8205b-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="8205b-119">I det här avsnittet beskrivs de användargränssnittselement som finns i EAC.</span><span class="sxs-lookup"><span data-stu-id="8205b-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Administrationscentret för Exchange i Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="8205b-121">Funktionsfönstret</span><span class="sxs-lookup"><span data-stu-id="8205b-121">Feature Pane</span></span>

<span data-ttu-id="8205b-122">Det här är den första navigeringsnivån för de flesta av de uppgifter som du kommer att utföra i EAC.</span><span class="sxs-lookup"><span data-stu-id="8205b-122">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="8205b-123">Funktionsfönstret är ordnat efter funktionsområden.</span><span class="sxs-lookup"><span data-stu-id="8205b-123">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="8205b-124">**Mottagare:** Det är här du visar grupper och externa kontakter.</span><span class="sxs-lookup"><span data-stu-id="8205b-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="8205b-125">**Behörigheter:** Här hanterar du administratörsroller.</span><span class="sxs-lookup"><span data-stu-id="8205b-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="8205b-126">**Efterlevnadshantering:** Det är här du hittar rapporten över administratörsrollgrupper och granskningsloggrapporten för administratörer.</span><span class="sxs-lookup"><span data-stu-id="8205b-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="8205b-127">**Skydd:** Det är här du kan hantera principer mot skadlig programvara, standardprincipen för anslutningsfilter och DKIM.</span><span class="sxs-lookup"><span data-stu-id="8205b-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8205b-128">Du bör hantera principer för skydd mot skadlig programvara och standardprincipen för anslutningsfilter i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="8205b-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="8205b-129">Mer information finns i Konfigurera [principer för skydd mot skadlig programvara i EOP och](configure-anti-malware-policies.md) Konfigurera [anslutningsfiltrering i EOP.](configure-the-connection-filter-policy.md)</span><span class="sxs-lookup"><span data-stu-id="8205b-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="8205b-130">**E-postflöde:** Det är här du hanterar e-postflödesregler (kallas även transportregler), godkända domäner och kopplingar, samt var du kan köra meddelandespårning.</span><span class="sxs-lookup"><span data-stu-id="8205b-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="8205b-131">**Hybrid:** Det är här du kan köra [hybridkonfigurationsguiden,](/Exchange/hybrid-configuration-wizard)och där kan du installera [Exchange Online PowerShell-modulen](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8205b-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="8205b-132">Flikar</span><span class="sxs-lookup"><span data-stu-id="8205b-132">Tabs</span></span>

<span data-ttu-id="8205b-133">Flikarna är din andra nivå av navigering.</span><span class="sxs-lookup"><span data-stu-id="8205b-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="8205b-134">Alla funktionsområden innehåller olika flikar, som var och en representerar en funktion.</span><span class="sxs-lookup"><span data-stu-id="8205b-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="8205b-135">Verktygsfält</span><span class="sxs-lookup"><span data-stu-id="8205b-135">Toolbar</span></span>

<span data-ttu-id="8205b-136">När du klickar på de flesta flikar visas ett verktygsfält.</span><span class="sxs-lookup"><span data-stu-id="8205b-136">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="8205b-137">Verktygsfältet innehåller ikoner som utför en viss åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8205b-137">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="8205b-138">I följande tabell beskrivs ikonerna och deras åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8205b-138">The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="8205b-139">Ikon</span><span class="sxs-lookup"><span data-stu-id="8205b-139">Icon</span></span>|<span data-ttu-id="8205b-140">Namn</span><span class="sxs-lookup"><span data-stu-id="8205b-140">Name</span></span>|<span data-ttu-id="8205b-141">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="8205b-141">Action</span></span>|
|---|---|---|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="8205b-143">Lägg till, Ny</span><span class="sxs-lookup"><span data-stu-id="8205b-143">Add, New</span></span>|<span data-ttu-id="8205b-144">Använd den här ikonen för att skapa ett nytt objekt.</span><span class="sxs-lookup"><span data-stu-id="8205b-144">Use this icon to create a new object.</span></span> <span data-ttu-id="8205b-145">Vissa av dessa ikoner har en tillhörande nedåtpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="8205b-145">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Redigeringsikon](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="8205b-147">Redigera</span><span class="sxs-lookup"><span data-stu-id="8205b-147">Edit</span></span>|<span data-ttu-id="8205b-148">Använd den här ikonen för att redigera ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8205b-148">Use this icon to edit an object.</span></span>|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="8205b-150">Ta bort</span><span class="sxs-lookup"><span data-stu-id="8205b-150">Delete</span></span>|<span data-ttu-id="8205b-151">Använd den här ikonen för att ta bort ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8205b-151">Use this icon to delete an object.</span></span> <span data-ttu-id="8205b-152">Vissa borttagningsikoner har en nedpil som du kan klicka på för att visa fler alternativ.</span><span class="sxs-lookup"><span data-stu-id="8205b-152">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Sökikon](../../media/ITPro-EAC-.gif)|<span data-ttu-id="8205b-154">Sök</span><span class="sxs-lookup"><span data-stu-id="8205b-154">Search</span></span>|<span data-ttu-id="8205b-155">Använd den här ikonen för att öppna en sökruta där du kan skriva sökfrasen för ett objekt som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="8205b-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Ikonen Uppdatera](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="8205b-157">Återställning</span><span class="sxs-lookup"><span data-stu-id="8205b-157">Refresh</span></span>|<span data-ttu-id="8205b-158">Använd den här ikonen för att uppdatera listvyn.</span><span class="sxs-lookup"><span data-stu-id="8205b-158">Use this icon to refresh the list view.</span></span>|
|![Ikonen Fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="8205b-160">Fler alternativ</span><span class="sxs-lookup"><span data-stu-id="8205b-160">More options</span></span>|<span data-ttu-id="8205b-161">Använd den här ikonen för att visa fler åtgärder som du kan utföra för objekten på den fliken.</span><span class="sxs-lookup"><span data-stu-id="8205b-161">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="8205b-162">I Mottagare visar till **exempel \> användare som** klickar på den här ikonen alternativet för att utföra en avancerad **sökning.**</span><span class="sxs-lookup"><span data-stu-id="8205b-162">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Ikon med uppil](../../media/ITPro-EAC-UpArrowIcon.gif)![Nedåtpilikon](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="8205b-165">Uppil och nedpil</span><span class="sxs-lookup"><span data-stu-id="8205b-165">Up arrow and down arrow</span></span>|<span data-ttu-id="8205b-166">Använd de här ikonerna om du vill flytta ett objekts prioritet uppåt eller nedåt.</span><span class="sxs-lookup"><span data-stu-id="8205b-166">Use these icons to move an object's priority up or down.</span></span>|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="8205b-168">Ta bort</span><span class="sxs-lookup"><span data-stu-id="8205b-168">Remove</span></span>|<span data-ttu-id="8205b-169">Använd den här ikonen för att ta bort objekt från en lista.</span><span class="sxs-lookup"><span data-stu-id="8205b-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="8205b-170">Listvy</span><span class="sxs-lookup"><span data-stu-id="8205b-170">List View</span></span>

<span data-ttu-id="8205b-171">När du väljer en flik visas i de flesta fall en listvy.</span><span class="sxs-lookup"><span data-stu-id="8205b-171">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="8205b-172">Visningsgränsen för EAC-listvyn är cirka 10 000 objekt.</span><span class="sxs-lookup"><span data-stu-id="8205b-172">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="8205b-173">Dessutom ingår sidindening så att du kan sida till resultat.</span><span class="sxs-lookup"><span data-stu-id="8205b-173">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="8205b-174">Informationsfönstret</span><span class="sxs-lookup"><span data-stu-id="8205b-174">Details Pane</span></span>

<span data-ttu-id="8205b-175">När du väljer ett objekt i listvyn visas information om objektet i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8205b-175">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="8205b-176">I vissa fall innehåller informationsfönstret hanteringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="8205b-176">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="8205b-177">Panelen Jag och Hjälp</span><span class="sxs-lookup"><span data-stu-id="8205b-177">Me tile and Help</span></span>

<span data-ttu-id="8205b-178">På **panelen** Jag kan du logga ut från EAC och logga in som en annan användare.</span><span class="sxs-lookup"><span data-stu-id="8205b-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="8205b-179">I den ![ ](../../media/ITPro-EAC-HelpIcon.gif) nedrullningrullningrullningrullningsmenyn Hjälpikon kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="8205b-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="8205b-180">**Hjälp:** Klicka på ![ ikonen Hjälp om du vill visa innehållet i ](../../media/ITPro-EAC-HelpIcon.gif) onlinehjälpen.</span><span class="sxs-lookup"><span data-stu-id="8205b-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="8205b-181">**Feedback**: Lämna feedback.</span><span class="sxs-lookup"><span data-stu-id="8205b-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="8205b-182">**Community:** Publicera en fråga för att få svar i community-forumen.</span><span class="sxs-lookup"><span data-stu-id="8205b-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="8205b-183">**Inaktivera hjälpbubblan:** Hjälpbubblan visar sammanhangsberoende hjälp för fält när du skapar eller redigerar ett objekt.</span><span class="sxs-lookup"><span data-stu-id="8205b-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="8205b-184">Du kan stänga av hjälpbubblan eller aktivera den om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="8205b-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="8205b-185">**Visa kommandologgning:** Ett nytt fönster öppnas som visar motsvarande PowerShell-kommandon baserat på vad du har konfigurerat i EAC.</span><span class="sxs-lookup"><span data-stu-id="8205b-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="8205b-186">Webbläsare som stöds</span><span class="sxs-lookup"><span data-stu-id="8205b-186">Supported Browsers</span></span>

<span data-ttu-id="8205b-187">För att EAC ska bli så bra som möjligt rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och apparna.</span><span class="sxs-lookup"><span data-stu-id="8205b-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="8205b-188">Vi rekommenderar även att du installerar programuppdateringar när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="8205b-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="8205b-189">Mer information om vilka webbläsare och systemkrav som stöds för tjänsten finns i [Systemkrav för Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="8205b-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="8205b-190">Språk som stöds</span><span class="sxs-lookup"><span data-stu-id="8205b-190">Supported languages</span></span>

<span data-ttu-id="8205b-191">Följande språk stöds och är tillgängliga för EAC i fristående EOP.</span><span class="sxs-lookup"><span data-stu-id="8205b-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="8205b-192">Amhariska</span><span class="sxs-lookup"><span data-stu-id="8205b-192">Amharic</span></span>
- <span data-ttu-id="8205b-193">Arabiska</span><span class="sxs-lookup"><span data-stu-id="8205b-193">Arabic</span></span>
- <span data-ttu-id="8205b-194">Baskiska (Baskien)</span><span class="sxs-lookup"><span data-stu-id="8205b-194">Basque (Basque)</span></span>
- <span data-ttu-id="8205b-195">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="8205b-195">Bengali (India)</span></span>
- <span data-ttu-id="8205b-196">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="8205b-196">Bulgarian</span></span>
- <span data-ttu-id="8205b-197">Catalan</span><span class="sxs-lookup"><span data-stu-id="8205b-197">Catalan</span></span>
- <span data-ttu-id="8205b-198">Kinesiska (förenklad)</span><span class="sxs-lookup"><span data-stu-id="8205b-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="8205b-199">Kinesiska (traditionell)</span><span class="sxs-lookup"><span data-stu-id="8205b-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="8205b-200">Croatian</span><span class="sxs-lookup"><span data-stu-id="8205b-200">Croatian</span></span>
- <span data-ttu-id="8205b-201">Czech</span><span class="sxs-lookup"><span data-stu-id="8205b-201">Czech</span></span>
- <span data-ttu-id="8205b-202">Danish</span><span class="sxs-lookup"><span data-stu-id="8205b-202">Danish</span></span>
- <span data-ttu-id="8205b-203">Dutch</span><span class="sxs-lookup"><span data-stu-id="8205b-203">Dutch</span></span>
- <span data-ttu-id="8205b-204">Engelska</span><span class="sxs-lookup"><span data-stu-id="8205b-204">English</span></span>
- <span data-ttu-id="8205b-205">Estonian</span><span class="sxs-lookup"><span data-stu-id="8205b-205">Estonian</span></span>
- <span data-ttu-id="8205b-206">Filippinska (Filippinerna)</span><span class="sxs-lookup"><span data-stu-id="8205b-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="8205b-207">Finnish</span><span class="sxs-lookup"><span data-stu-id="8205b-207">Finnish</span></span>
- <span data-ttu-id="8205b-208">French</span><span class="sxs-lookup"><span data-stu-id="8205b-208">French</span></span>
- <span data-ttu-id="8205b-209">Galician</span><span class="sxs-lookup"><span data-stu-id="8205b-209">Galician</span></span>
- <span data-ttu-id="8205b-210">German</span><span class="sxs-lookup"><span data-stu-id="8205b-210">German</span></span>
- <span data-ttu-id="8205b-211">Greek</span><span class="sxs-lookup"><span data-stu-id="8205b-211">Greek</span></span>
- <span data-ttu-id="8205b-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="8205b-212">Gujarati</span></span>
- <span data-ttu-id="8205b-213">Hebrew</span><span class="sxs-lookup"><span data-stu-id="8205b-213">Hebrew</span></span>
- <span data-ttu-id="8205b-214">Hindi</span><span class="sxs-lookup"><span data-stu-id="8205b-214">Hindi</span></span>
- <span data-ttu-id="8205b-215">Hungarian</span><span class="sxs-lookup"><span data-stu-id="8205b-215">Hungarian</span></span>
- <span data-ttu-id="8205b-216">Isländska</span><span class="sxs-lookup"><span data-stu-id="8205b-216">Icelandic</span></span>
- <span data-ttu-id="8205b-217">Indonesian</span><span class="sxs-lookup"><span data-stu-id="8205b-217">Indonesian</span></span>
- <span data-ttu-id="8205b-218">Italian</span><span class="sxs-lookup"><span data-stu-id="8205b-218">Italian</span></span>
- <span data-ttu-id="8205b-219">Japanese</span><span class="sxs-lookup"><span data-stu-id="8205b-219">Japanese</span></span>
- <span data-ttu-id="8205b-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="8205b-220">Kannada</span></span>
- <span data-ttu-id="8205b-221">Kazakh</span><span class="sxs-lookup"><span data-stu-id="8205b-221">Kazakh</span></span>
- <span data-ttu-id="8205b-222">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="8205b-222">Kiswahili</span></span>
- <span data-ttu-id="8205b-223">Korean</span><span class="sxs-lookup"><span data-stu-id="8205b-223">Korean</span></span>
- <span data-ttu-id="8205b-224">Latvian</span><span class="sxs-lookup"><span data-stu-id="8205b-224">Latvian</span></span>
- <span data-ttu-id="8205b-225">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="8205b-225">Lithuanian</span></span>
- <span data-ttu-id="8205b-226">Malajiska (Brunei)</span><span class="sxs-lookup"><span data-stu-id="8205b-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="8205b-227">Malajiska (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="8205b-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="8205b-228">Malayalam</span><span class="sxs-lookup"><span data-stu-id="8205b-228">Malayalam</span></span>
- <span data-ttu-id="8205b-229">Marathi</span><span class="sxs-lookup"><span data-stu-id="8205b-229">Marathi</span></span>
- <span data-ttu-id="8205b-230">Norska (bokmål)</span><span class="sxs-lookup"><span data-stu-id="8205b-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="8205b-231">Norska (nynorsk)</span><span class="sxs-lookup"><span data-stu-id="8205b-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="8205b-232">Oriya</span><span class="sxs-lookup"><span data-stu-id="8205b-232">Oriya</span></span>
- <span data-ttu-id="8205b-233">Persiska</span><span class="sxs-lookup"><span data-stu-id="8205b-233">Persian</span></span>
- <span data-ttu-id="8205b-234">Polish</span><span class="sxs-lookup"><span data-stu-id="8205b-234">Polish</span></span>
- <span data-ttu-id="8205b-235">Portugisiska (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="8205b-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="8205b-236">Portugisiska (Portugal)</span><span class="sxs-lookup"><span data-stu-id="8205b-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="8205b-237">Romanian</span><span class="sxs-lookup"><span data-stu-id="8205b-237">Romanian</span></span>
- <span data-ttu-id="8205b-238">Russian</span><span class="sxs-lookup"><span data-stu-id="8205b-238">Russian</span></span>
- <span data-ttu-id="8205b-239">Serbiska (kyrillisk språk, Serbien)</span><span class="sxs-lookup"><span data-stu-id="8205b-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="8205b-240">Serbiska (latinsk)</span><span class="sxs-lookup"><span data-stu-id="8205b-240">Serbian (Latin)</span></span>
- <span data-ttu-id="8205b-241">Slovak</span><span class="sxs-lookup"><span data-stu-id="8205b-241">Slovak</span></span>
- <span data-ttu-id="8205b-242">Slovenian</span><span class="sxs-lookup"><span data-stu-id="8205b-242">Slovenian</span></span>
- <span data-ttu-id="8205b-243">Spanish</span><span class="sxs-lookup"><span data-stu-id="8205b-243">Spanish</span></span>
- <span data-ttu-id="8205b-244">Swedish</span><span class="sxs-lookup"><span data-stu-id="8205b-244">Swedish</span></span>
- <span data-ttu-id="8205b-245">Tamilska</span><span class="sxs-lookup"><span data-stu-id="8205b-245">Tamil</span></span>
- <span data-ttu-id="8205b-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="8205b-246">Telugu</span></span>
- <span data-ttu-id="8205b-247">Thai</span><span class="sxs-lookup"><span data-stu-id="8205b-247">Thai</span></span>
- <span data-ttu-id="8205b-248">Turkish</span><span class="sxs-lookup"><span data-stu-id="8205b-248">Turkish</span></span>
- <span data-ttu-id="8205b-249">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="8205b-249">Ukrainian</span></span>
- <span data-ttu-id="8205b-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="8205b-250">Urdu</span></span>
- <span data-ttu-id="8205b-251">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="8205b-251">Vietnamese</span></span>
- <span data-ttu-id="8205b-252">Walesiska</span><span class="sxs-lookup"><span data-stu-id="8205b-252">Welsh</span></span>