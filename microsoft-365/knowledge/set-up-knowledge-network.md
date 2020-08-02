---
title: 'Konfigurera kunskapshantering (förhandsversion) '
description: Så här ställer du in Knowledge Management.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540136"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="ce6d1-103">Konfigurera kunskapshantering (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="ce6d1-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="ce6d1-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="ce6d1-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ce6d1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="ce6d1-106">Du kan använda administrationscentret för Microsoft 365 för att konfigurera [Kunskapshantering](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce6d1-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="ce6d1-107">Det är viktigt att planera det bästa sättet att konfigurera och konfigurera Kunskapshantering i din miljö.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="ce6d1-108">Du måste till exempel ta hänsyn till följande:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="ce6d1-109">Vilka SharePoint-webbplatser du vill analysera för ämnen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="ce6d1-110">Vilka användare du vill göra ämnen synliga för.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="ce6d1-111">Vilka användare du vill ge behörighet att hantera ämnen i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="ce6d1-112">Vilka användare du vill ge behörighet att skapa eller redigera ämnen i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="ce6d1-113">Vilket namn du vill ge ditt ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="ce6d1-114">Det kan vara bra att skapa säkerhetsgrupper för att tilldela användarna de behörigheter som behövs för att visa ämnen, hantera ämnen och skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="ce6d1-115">En administratör kan också [göra ändringar i dina valda inställningar när som helst efter installationen](manage-knowledge-network.md) via knowledge management-inställningarna i Administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce6d1-116">Krav</span><span class="sxs-lookup"><span data-stu-id="ce6d1-116">Requirements</span></span> 
<span data-ttu-id="ce6d1-117">Du måste ha behörighet för global administratör eller SharePoint-administratör för att kunna komma åt Microsoft 365-administrationscentret och konfigurera organisatoriska kunskapsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="ce6d1-118">Konfigurera kunskapsnätverket</span><span class="sxs-lookup"><span data-stu-id="ce6d1-118">Set up your knowledge network</span></span>

<span data-ttu-id="ce6d1-119">När du konfigurerar kunskapsnätverket får du följande information:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="ce6d1-120">Ämnesidentifiering: Välja ämneskällor och ämnen som ska uteslutas från identifiering.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="ce6d1-121">Ämnessynlighet: Välja vem som kan visa ämnen som högdagrar, på sök- och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="ce6d1-122">Ämnesbehörigheter: Välja vem som kan skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="ce6d1-123">Ämnescenter: Skapa ditt ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="ce6d1-124">Granska: Kontrollera och tillämpa inställningarna.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="ce6d1-125">Så här konfigurerar du kunskapsnätverket:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="ce6d1-126">I administrationscentret för Microsoft 365 (admin.microsoft.com) väljer du **Installationsprogrammet**och visar sedan avsnittet **Organisationskunskap.**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="ce6d1-127">Klicka på Anslut personer **till kunskap**i avsnittet **Organisationskunskap.**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="ce6d1-129">På sidan **Anslut personer till kunskap** klickar du på Kom **igång** för att gå igenom installationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Komma igång](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="ce6d1-131">På sidan **Välj hur kunskapsnätverket kan hitta ämnen** konfigurerar du ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="ce6d1-132">I avsnittet **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska genomsökas som källor för dina ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="ce6d1-133">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-133">This includes:</span></span></br>
    <span data-ttu-id="ce6d1-134">a.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-134">a.</span></span> <span data-ttu-id="ce6d1-135">**Alla webbplatser:** Alla SharePoint-webbplatser i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="ce6d1-136">Detta fångar nuvarande och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="ce6d1-137">b.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-137">b.</span></span> <span data-ttu-id="ce6d1-138">**Alla, utom valda platser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="ce6d1-139">Du kan också ladda upp en lista över webbplatser som du vill välja bort från identifiering.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="ce6d1-140">Webbplatser som skapas i framtiden kommer att inkluderas som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="ce6d1-141">c.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-141">c.</span></span> <span data-ttu-id="ce6d1-142">**Endast valda platser:** Skriv namnen på de platser som du vill inkludera.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="ce6d1-143">Du kan också ladda upp en lista över webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-143">You can also upload a list of sites.</span></span> <span data-ttu-id="ce6d1-144">Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Välj hur du hittar ämnen](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="ce6d1-146">I avsnittet **Uteslut efter namn** kan du välja att ta med namn på ämnen som du inte vill ska finnas i de identifierade resultaten.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="ce6d1-147">Använd den här inställningen om du vill förhindra att känsliga ämnen inkluderas som en del av kunskapsnätverket.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="ce6d1-148">Dina alternativ inkluderar:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-148">Your options include:</span></span></br>
    <span data-ttu-id="ce6d1-149">a.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-149">a.</span></span> <span data-ttu-id="ce6d1-150">**Uteslut inte några ämnen**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="ce6d1-151">b.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-151">b.</span></span> <span data-ttu-id="ce6d1-152">**Uteslut ämne som innehåller dessa termer**: Om du har ämnen som du inte vill visa för användare som en del av kunskapsnätverket.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="ce6d1-153">- Ladda ner den medföljande mallen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-153">- Download the provided template.</span></span>
   <span data-ttu-id="ce6d1-154">- Ange de ämnesnamn som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="ce6d1-155">Du måste ange matchningstypen som exakt eller partiell.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="ce6d1-156">Exakt matchning innebär att ämnen som passar den exakta termen utesluts.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="ce6d1-157">Partiell matchning är strängare och innebär att ämnen som innehåller termen utesluts.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="ce6d1-158">Om du till exempel anger *Doc* som ämnesnamn utesluts *Doc-sammansättning* medan *Docker* inte gör det.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="ce6d1-159">Ämnesnamn är skiftlägesokänsliga.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="ce6d1-160">- Välj om du  **+**   vill importera den färdiga CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="ce6d1-161">Välj sedan **Ladda upp**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-161">Then select **Upload**.</span></span> <span data-ttu-id="ce6d1-162">Du ser en grön bock om filen har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="ce6d1-163">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="ce6d1-164">På sidan **Vem kan se ämnen och var de kan se dem** konfigurerar du ämnessynlighet.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="ce6d1-165">I inställningen **Vem kan se ämnen i kunskapsnätverket** väljer du vem som ska ha tillgång till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sök- och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="ce6d1-166">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-166">You can select:</span></span></br>
    <span data-ttu-id="ce6d1-167">a.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-167">a.</span></span> <span data-ttu-id="ce6d1-168">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="ce6d1-169">b.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-169">b.</span></span> <span data-ttu-id="ce6d1-170">**Endast markerade personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="ce6d1-171">c.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-171">c.</span></span> <span data-ttu-id="ce6d1-172">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-172">**No one**</span></span></br>

    ![Vem kan se ämnen](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="ce6d1-174">Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskapshanteringslicenser som tilldelats dem kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="ce6d1-175">På sidan **Behörigheter för ämneshantering** väljer du vem som ska kunna skapa, redigera eller hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="ce6d1-176">I avsnittet **Vem kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="ce6d1-177">a.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-177">a.</span></span> <span data-ttu-id="ce6d1-178">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="ce6d1-179">b.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-179">b.</span></span> <span data-ttu-id="ce6d1-180">**Endast markerade personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="ce6d1-181">I avsnittet **Vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="ce6d1-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="ce6d1-182">a.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-182">a.</span></span> <span data-ttu-id="ce6d1-183">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="ce6d1-184">b.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-184">b.</span></span> <span data-ttu-id="ce6d1-185">**Utvalda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-185">**Selected people or security groups**</span></span></br>

    ![Behörigheter för ämneshantering](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="ce6d1-187">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="ce6d1-188">På sidan **Skapa ämnescenter** kan du skapa en webbplats för ämnescenter där ämnessidor kan visas och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="ce6d1-189">Skriv ett namn på ämnescentret i **rutan Ämnescenter.**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="ce6d1-190">Du kan också skriva en kort beskrivning i rutan **Webbplatsbeskrivning.**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="ce6d1-191">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-191">Select **Next**.</span></span></br>

   ![Skapa kunskapscenter](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="ce6d1-193">På sidan **Granska och avsluta** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="ce6d1-194">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Avsluta och granska](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="ce6d1-196">Sidan **Kunskapsnätverk som aktiveras** visas och bekräftar att systemet nu kommer att börja analysera dina valda webbplatser för ämnen och skapa knowledge center-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="ce6d1-197">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-197">Select **Done**.</span></span></br>

    ![Aktiverat](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="ce6d1-199">Du kommer tillbaka till din **Anslut personer till kunskapssidan.**</span><span class="sxs-lookup"><span data-stu-id="ce6d1-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="ce6d1-200">På den här sidan kan du välja **Hantera** om du vill göra ändringar i konfigurationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar tillämpas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="ce6d1-202">Efter installationen kan en administratör [göra ändringar i dina valda inställningar för kunskapshantering](manage-knowledge-network.md) när som helst genom att gå tillbaka till den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ce6d1-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="ce6d1-203">Se även</span><span class="sxs-lookup"><span data-stu-id="ce6d1-203">See also</span></span>



  






