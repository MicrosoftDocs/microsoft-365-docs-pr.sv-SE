---
title: 'Konfigurera kunskaps hantering (för hands version) '
description: Så här konfigurerar du kunskaps hantering.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612554"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="c0cbd-103">Konfigurera kunskaps hantering (för hands version)</span><span class="sxs-lookup"><span data-stu-id="c0cbd-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c0cbd-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c0cbd-105">[Lär dig mer om Project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c0cbd-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="c0cbd-106">Du kan använda administrations centret för Microsoft 365 för att ställa in och konfigurera [kunskaps hantering](knowledge-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c0cbd-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="c0cbd-107">Det är viktigt att planera det bästa sättet att ställa in och konfigurera kunskaps hantering i din miljö.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="c0cbd-108">Till exempel måste du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="c0cbd-109">Vilka SharePoint-webbplatser som du vill analysera för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="c0cbd-110">Vilka användare du vill göra ämnen synliga för.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="c0cbd-111">Vilka användare som du vill ge behörighet att hantera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="c0cbd-112">Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="c0cbd-113">Vilket namn du vill ge ditt ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="c0cbd-114">Det kan vara praktiskt att skapa säkerhets grupper för att ge användarna de behörigheter som krävs för att Visa ämnen, hantera ämne och skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="c0cbd-115">En administratör kan också [göra ändringar i dina valda inställningar när som helst efter installationen](manage-knowledge-network.md) via kunskaps hanterings inställningarna i Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0cbd-116">Krav</span><span class="sxs-lookup"><span data-stu-id="c0cbd-116">Requirements</span></span> 
<span data-ttu-id="c0cbd-117">Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och ställa in organisationens kunskaps uppgifter.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="c0cbd-118">Konfigurera kunskaps nätverk</span><span class="sxs-lookup"><span data-stu-id="c0cbd-118">Set up your knowledge network</span></span>

<span data-ttu-id="c0cbd-119">Genom att konfigurera kunskaps nätverket får du hjälp med följande:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="c0cbd-120">Avsnitts identifiering: välja ämnen och ämnen som ska undantas från identifieringen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="c0cbd-121">Ämnets synlighet: välja vilka som får Visa ämnen som högdagrar, på sidan Sök och ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="c0cbd-122">Behörigheter för ämne: välja vem som kan skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="c0cbd-123">Ämnes Center: skapa ett ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="c0cbd-124">Granska: kontrol lera och tillämpa dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="c0cbd-125">Så här konfigurerar du ditt kunskaps nätverk:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="c0cbd-126">I administrations centret för Microsoft 365 (admin.microsoft.com) väljer du **Konfigurera**och sedan Visa avsnittet **organisations** information.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="c0cbd-127">I avsnittet **organisationsinformation** klickar du på **Anslut personer till kunskap**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="c0cbd-129">På sidan **Anslut personer till kunskap** klickar du på **komma igång** för att vägleda dig genom installations processen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Komma igång](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="c0cbd-131">På sidan **Välj hur kunskaps nätverket kan hitta ämnes** sidor konfigurerar du identifiering av avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="c0cbd-132">Välj vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering i avsnittet Välj avsnitts **källor för SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="c0cbd-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="c0cbd-133">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-133">This includes:</span></span></br>
    <span data-ttu-id="c0cbd-134">a.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-134">a.</span></span> <span data-ttu-id="c0cbd-135">**Alla webbplatser**: alla SharePoint-webbplatser i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="c0cbd-136">Här fångar du aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="c0cbd-137">b.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-137">b.</span></span> <span data-ttu-id="c0cbd-138">**Alla, förutom markerade webbplatser**: Skriv namnen på de webbplatser du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="c0cbd-139">Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="c0cbd-140">Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="c0cbd-141">c.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-141">c.</span></span> <span data-ttu-id="c0cbd-142">**Endast valda webbplatser**: Skriv in namnen på de webbplatser du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="c0cbd-143">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-143">You can also upload a list of sites.</span></span> <span data-ttu-id="c0cbd-144">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Välj hur du vill hitta ämnen](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="c0cbd-146">I avsnittet **undanta ämnen efter namn** kan du välja att inkludera namn på ämnen som du inte vill ska finnas med i resultatet.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="c0cbd-147">Använd den här inställningen för att förhindra att känsliga ämnen tas med i kunskaps nätet.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="c0cbd-148">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-148">Your options include:</span></span></br>
    <span data-ttu-id="c0cbd-149">a.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-149">a.</span></span> <span data-ttu-id="c0cbd-150">**Utelämna inte ämnen**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="c0cbd-151">b.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-151">b.</span></span> <span data-ttu-id="c0cbd-152">**Utelämna ämnen som innehåller följande villkor**: om du har ämnen som du inte vill visa för användarna som en del av kunskaps nätet.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="c0cbd-153">-Ladda ner den medföljande mallen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-153">- Download the provided template.</span></span>
   <span data-ttu-id="c0cbd-154">-Ange ämnen som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="c0cbd-155">Du måste ange matchnings typen som exakt eller delvis.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="c0cbd-156">Exakt matchning innebär att ämnen som uppfyller den exakta termen utesluts.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="c0cbd-157">Delvis träff är striktare och innebär att ämnen som innehåller termen utesluts.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="c0cbd-158">Om du till exempel anger *doc* som ämnes namn utesluts *dokument sammansättning* när *docknings stationen* inte gör det.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="c0cbd-159">Ämnes namn är Skift läges känsliga.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="c0cbd-160">-Välj  **+**   för att importera den färdiga CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="c0cbd-161">Välj sedan **Ladda upp**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-161">Then select **Upload**.</span></span> <span data-ttu-id="c0cbd-162">En grön bock markering visas om filen har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="c0cbd-163">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="c0cbd-164">På sidan **vem kan se ämnen och var de kan se dem** ser du avsnitts visning.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="c0cbd-165">I listan **vilka kan se ämnen i kunskaps nätverkets** inställning väljer du vilka som ska ha åtkomst till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="c0cbd-166">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-166">You can select:</span></span></br>
    <span data-ttu-id="c0cbd-167">a.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-167">a.</span></span> <span data-ttu-id="c0cbd-168">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c0cbd-169">b.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-169">b.</span></span> <span data-ttu-id="c0cbd-170">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="c0cbd-171">c.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-171">c.</span></span> <span data-ttu-id="c0cbd-172">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-172">**No one**</span></span></br>

    ![Vilka som kan se ämnen](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="c0cbd-174">Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskaps hanterings licenser tilldelade till dem kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="c0cbd-175">På sidan **behörigheter för hantering av ämnen** kan du välja vem som ska kunna skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="c0cbd-176">I avsnittet **vilka som kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="c0cbd-177">a.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-177">a.</span></span> <span data-ttu-id="c0cbd-178">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c0cbd-179">b.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-179">b.</span></span> <span data-ttu-id="c0cbd-180">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="c0cbd-181">I avsnittet **vilka kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="c0cbd-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="c0cbd-182">a.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-182">a.</span></span> <span data-ttu-id="c0cbd-183">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="c0cbd-184">b.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-184">b.</span></span> <span data-ttu-id="c0cbd-185">**Markerade personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="c0cbd-185">**Selected people or security groups**</span></span></br>

    ![Behörigheter för hantering av ämnen](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="c0cbd-187">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="c0cbd-188">På sidan **skapa ämnes Center** kan du skapa en ämnes Center-webbplats där du kan visa ämnes sidor och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="c0cbd-189">Skriv ett namn på ämnes centret i rutan **namn på ämnes Center** .</span><span class="sxs-lookup"><span data-stu-id="c0cbd-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="c0cbd-190">Du kan också skriva en kort beskrivning i rutan **Beskrivning** .</span><span class="sxs-lookup"><span data-stu-id="c0cbd-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="c0cbd-191">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-191">Select **Next**.</span></span></br>

   ![Skapa kunskaps Center](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="c0cbd-193">På sidan **Granska och slutför** kan du titta på den valda inställningen och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="c0cbd-194">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![Slutför och granska](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="c0cbd-196">Sidan **kunskaps nätverk aktive rad** visar och bekräftar att systemet kommer att börja analysera dina valda webbplatser för att få hjälp med ämnen och att skapa kunskaps Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="c0cbd-197">Välj **klar**.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-197">Select **Done**.</span></span></br>

    ![Rad](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="c0cbd-199">Du kommer att återföras till sidan **Koppla personer till kunskap** .</span><span class="sxs-lookup"><span data-stu-id="c0cbd-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="c0cbd-200">Från den här sidan kan du välja **Hantera** för att ändra dina konfigurations inställningar.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar tillämpas](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="c0cbd-202">När installationen är slutförd kan administratören [ändra dina valda kunskaps hanterings inställningar](manage-knowledge-network.md) när som helst genom att gå tillbaka till den här sidan.</span><span class="sxs-lookup"><span data-stu-id="c0cbd-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="c0cbd-203">Se även</span><span class="sxs-lookup"><span data-stu-id="c0cbd-203">See also</span></span>



  






