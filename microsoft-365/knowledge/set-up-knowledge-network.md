---
title: 'Konfigurera kunskaps hantering (för hands version) '
description: Så här konfigurerar du kunskaps hantering.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 6f5d014a8f401d9c3489eabb849b9d666444e6aa
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948156"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="2a4d4-103">Konfigurera kunskaps hantering (för hands version)</span><span class="sxs-lookup"><span data-stu-id="2a4d4-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="2a4d4-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="2a4d4-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2a4d4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2a4d4-106">Du kan använda administrations centret för Microsoft 365 för att ställa in och konfigurera [kunskaps hantering](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2a4d4-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="2a4d4-107">Det är viktigt att planera det bästa sättet att ställa in och konfigurera kunskaps hantering i din miljö.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="2a4d4-108">Till exempel måste du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="2a4d4-109">Vilka SharePoint-webbplatser som du vill analysera för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="2a4d4-110">Vilka användare du vill göra ämnen synliga för.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="2a4d4-111">Vilka användare som du vill ge behörighet att hantera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="2a4d4-112">Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="2a4d4-113">Vilket namn du vill ge ditt ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="2a4d4-114">Det kan vara praktiskt att skapa säkerhets grupper för att ge användarna de behörigheter som krävs för att Visa ämnen, hantera ämne och skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="2a4d4-115">En administratör kan också [göra ändringar i dina valda inställningar när som helst efter installationen](manage-knowledge-network.md) via kunskaps hanterings inställningarna i Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a4d4-116">Krav</span><span class="sxs-lookup"><span data-stu-id="2a4d4-116">Requirements</span></span> 
<span data-ttu-id="2a4d4-117">Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in organisationens kunskaps uppgifter.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="2a4d4-118">Konfigurera kunskaps nätverk</span><span class="sxs-lookup"><span data-stu-id="2a4d4-118">Set up your knowledge network</span></span>

<span data-ttu-id="2a4d4-119">Genom att konfigurera kunskaps nätverket får du hjälp med följande:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="2a4d4-120">Avsnitts identifiering: välja ämnen och ämnen som ska undantas från identifieringen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="2a4d4-121">Ämnets synlighet: välja vilka som får Visa ämnen som högdagrar, på sidan Sök och ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="2a4d4-122">Behörigheter för ämne: välja vem som kan skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="2a4d4-123">Ämnes Center: skapa ett ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="2a4d4-124">Granska: kontrol lera och tillämpa dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="2a4d4-125">Så här konfigurerar du ditt kunskaps nätverk:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="2a4d4-126">I administrations centret för Microsoft 365 (admin.microsoft.com) väljer du **Konfigurera**och sedan Visa avsnittet **organisations** information.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="2a4d4-127">I avsnittet **organisationsinformation** klickar du på **Anslut personer till kunskap**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="2a4d4-129">På sidan **Anslut personer till kunskap** klickar du på **komma igång** för att vägleda dig genom installations processen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Komma igång](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="2a4d4-131">På sidan **Välj hur kunskaps nätverket kan hitta ämnes** sidor konfigurerar du identifiering av avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="2a4d4-132">Välj vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering i avsnittet Välj avsnitts **källor för SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="2a4d4-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="2a4d4-133">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-133">This includes:</span></span></br>
    <span data-ttu-id="2a4d4-134">a.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-134">a.</span></span> <span data-ttu-id="2a4d4-135">**Alla webbplatser**: alla SharePoint-webbplatser i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="2a4d4-136">Här fångar du aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="2a4d4-137">b.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-137">b.</span></span> <span data-ttu-id="2a4d4-138">**Alla, förutom markerade webbplatser**: Skriv namnen på de webbplatser du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="2a4d4-139">Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="2a4d4-140">Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="2a4d4-141">c.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-141">c.</span></span> <span data-ttu-id="2a4d4-142">**Endast valda webbplatser**: Skriv in namnen på de webbplatser du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="2a4d4-143">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-143">You can also upload a list of sites.</span></span> <span data-ttu-id="2a4d4-144">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Välj hur du vill hitta ämnen](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="2a4d4-146">I avsnittet **undanta ämnen efter namn** kan du välja att inkludera namn på ämnen som du inte vill ska finnas med i resultatet.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="2a4d4-147">Använd den här inställningen för att förhindra att känsliga ämnen tas med i kunskaps nätet.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="2a4d4-148">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-148">Your options include:</span></span></br>
    <span data-ttu-id="2a4d4-149">a.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-149">a.</span></span> <span data-ttu-id="2a4d4-150">**Utelämna inte ämnen**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="2a4d4-151">b.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-151">b.</span></span> <span data-ttu-id="2a4d4-152">**Utelämna ämnen efter namn**: om du har ämnen som du inte vill visa för användarna som en del av kunskaps nätverket.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-152">**Exclude topics by name**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![Utelämna ämnen](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="2a4d4-154">Så här utesluter du ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="2a4d4-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="2a4d4-155">Om du behöver undanta ämnen, efter att du har valt **Uteslut ämnen efter namn**, väljer **du Hämta CSV-mallen**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-155">If you need to exclude topics, after selecting **Exclude topics by name**, select **Download the .csv template**.</span></span> <span data-ttu-id="2a4d4-156">Använda Excel. CSV-mallen för att inkludera en lista med ämnen som du vill undanta från identifierings resultaten.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![Uteslut avsnitt i en CSV-mall](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="2a4d4-158">I CSV-mallen anger du följande information om de avsnitt som du vill undanta:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="2a4d4-159">**Namn**: Skriv namnet på det ämne som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-159">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="2a4d4-160">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="2a4d4-161">Exakt träff: du kan ange exakt namn eller akronym (till exempel *contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="2a4d4-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span></br>
        - <span data-ttu-id="2a4d4-162">Ofullständig matchning: du kan exkludera alla ämnen som har ett visst ord i det.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="2a4d4-163">Till exempel kommer *bågen* att exkludera alla ämnen med ord *båge* i det, till exempel *båge cirkel*, *plasma båge svets*eller *tränings båge*. Observera att den inte utesluter ämnen där texten är inkluderad som en del av ett ord, till exempel *arkitekturen*.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="2a4d4-164">**Expansion (valfritt)**: om du vill utesluta en akronym skriver du orden som akronym står för.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-164">**Expansion (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="2a4d4-165">**MatchType-exakt/delvis**: Skriv om det namn du angav är en *exakt* eller *delvis* matchnings typ.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-165">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="2a4d4-166">När du har slutfört och sparat CSV-mallfilen väljer du **Bläddra** och letar reda på och markerar den.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="2a4d4-167">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="2a4d4-168">På sidan **vem kan se ämnen och var de kan se dem** ser du avsnitts visning.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="2a4d4-169">I listan **vilka kan se ämnen i kunskaps nätverkets** inställning väljer du vilka som ska ha åtkomst till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="2a4d4-170">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-170">You can select:</span></span></br>
    <span data-ttu-id="2a4d4-171">a.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-171">a.</span></span> <span data-ttu-id="2a4d4-172">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2a4d4-173">b.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-173">b.</span></span> <span data-ttu-id="2a4d4-174">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="2a4d4-175">c.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-175">c.</span></span> <span data-ttu-id="2a4d4-176">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-176">**No one**</span></span></br>

    ![Vilka som kan se ämnen](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="2a4d4-178">Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskaps hanterings licenser tilldelade till dem kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="2a4d4-179">På sidan **behörigheter för hantering av ämnen** kan du välja vem som ska kunna skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="2a4d4-180">I avsnittet **vilka som kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="2a4d4-181">a.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-181">a.</span></span> <span data-ttu-id="2a4d4-182">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2a4d4-183">b.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-183">b.</span></span> <span data-ttu-id="2a4d4-184">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="2a4d4-185">I avsnittet **vilka kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="2a4d4-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="2a4d4-186">a.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-186">a.</span></span> <span data-ttu-id="2a4d4-187">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="2a4d4-188">b.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-188">b.</span></span> <span data-ttu-id="2a4d4-189">**Markerade personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="2a4d4-189">**Selected people or security groups**</span></span></br>

    ![Behörigheter för hantering av ämnen](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="2a4d4-191">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="2a4d4-192">På sidan **skapa ämnes Center** kan du skapa en ämnes Center-webbplats där du kan visa ämnes sidor och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="2a4d4-193">Skriv ett namn på ämnes centret i rutan **namn på ämnes Center** .</span><span class="sxs-lookup"><span data-stu-id="2a4d4-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="2a4d4-194">Du kan också skriva en kort beskrivning i rutan **Beskrivning** .</span><span class="sxs-lookup"><span data-stu-id="2a4d4-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="2a4d4-195">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-195">Select **Next**.</span></span></br>

   ![Skapa kunskaps Center](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="2a4d4-197">På sidan **Granska och slutför** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2a4d4-198">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Slutför och granska](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="2a4d4-200">Sidan **kunskaps nätverk aktive rad** visar och bekräftar att systemet kommer att börja analysera dina valda webbplatser för att få hjälp med ämnen och att skapa kunskaps Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="2a4d4-201">Välj **klar**.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-201">Select **Done**.</span></span></br>

    ![Rad](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="2a4d4-203">Du kommer att återföras till sidan **Koppla personer till kunskap** .</span><span class="sxs-lookup"><span data-stu-id="2a4d4-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="2a4d4-204">Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar tillämpas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="2a4d4-206">När installationen är slutförd kan administratören [ändra dina valda kunskaps hanterings inställningar](manage-knowledge-network.md) när som helst genom att gå tillbaka till den här sidan.</span><span class="sxs-lookup"><span data-stu-id="2a4d4-206">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="2a4d4-207">Se även</span><span class="sxs-lookup"><span data-stu-id="2a4d4-207">See also</span></span>



  






