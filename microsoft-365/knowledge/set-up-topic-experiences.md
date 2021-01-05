---
title: Konfigurera ämnen i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du konfigurerar ämnen i Microsoft 365
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749617"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="75cb9-103">Konfigurera ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="75cb9-104">Du kan använda Microsoft 365 Admin Center för att konfigurera och konfigurera [avsnitts upplevelser](topic-experiences-overview.md).</span><span class="sxs-lookup"><span data-stu-id="75cb9-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="75cb9-105">Det är viktigt att planera det bästa sättet att konfigurera och konfigurera ämnen i miljön.</span><span class="sxs-lookup"><span data-stu-id="75cb9-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="75cb9-106">Se till att läsa [Plans erfarenheterna](plan-topic-experiences.md) innan du börjar procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="75cb9-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="75cb9-107">Du måste vara global administratör eller SharePoint-administratör för att få åtkomst till administrations centret för Microsoft 365 och konfigurera ämnen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="75cb9-108">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="75cb9-108">Video demonstration</span></span>

<span data-ttu-id="75cb9-109">Den här videon visar processen för att konfigurera ämnen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75cb9-109">This video shows the process for setting up topic experiences in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="75cb9-110">Konfigurera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="75cb9-110">Set up topic experiences</span></span>

<span data-ttu-id="75cb9-111">Så här konfigurerar du ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-111">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="75cb9-112">I [administrations centret för Microsoft 365](https://admin.microsoft.com)väljer du **Konfigurera** och sedan avsnittet **filer och innehåll** .</span><span class="sxs-lookup"><span data-stu-id="75cb9-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="75cb9-113">I avsnittet **filer och innehåll** klickar du på **Anslut personer till kunskap**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Koppla personer till kunskap](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="75cb9-115">På sidan **Anslut personer till kunskap** klickar du på **komma igång** för att vägleda dig genom installations processen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Komma igång](../media/k-get-started.png) 

4. <span data-ttu-id="75cb9-117">På sidan **Välj hur kunskaps nätverket kan hitta ämnes** sidor konfigurerar du identifiering av avsnitt.</span><span class="sxs-lookup"><span data-stu-id="75cb9-117">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="75cb9-118">Välj vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering i avsnittet Välj avsnitts **källor för SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="75cb9-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="75cb9-119">Välj från:</span><span class="sxs-lookup"><span data-stu-id="75cb9-119">Choose from:</span></span>
    - <span data-ttu-id="75cb9-120">**Alla webbplatser**: alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="75cb9-121">Detta inkluderar aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="75cb9-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="75cb9-122">**Alla, förutom markerade webbplatser**: Skriv namnen på de webbplatser du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="75cb9-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="75cb9-123">Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="75cb9-124">Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="75cb9-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="75cb9-125">**Endast valda webbplatser**: Skriv in namnen på de webbplatser du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="75cb9-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="75cb9-126">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="75cb9-126">You can also upload a list of sites.</span></span> <span data-ttu-id="75cb9-127">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="75cb9-128">**Inga webbplatser**: det finns inga SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="75cb9-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Välj hur du vill hitta ämnen](../media/ksetup1.png) 
   
5. <span data-ttu-id="75cb9-130">I avsnittet **undanta ämnen efter namn** kan du lägga till namn på ämnen som du vill undanta från avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="75cb9-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="75cb9-131">Använd den här inställningen för att förhindra att känslig information tas med i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="75cb9-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="75cb9-132">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="75cb9-132">The options are:</span></span>
    - <span data-ttu-id="75cb9-133">**Utelämna inte ämnen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="75cb9-134">**Utelämna ämnen efter namn**</span><span class="sxs-lookup"><span data-stu-id="75cb9-134">**Exclude topics by name**</span></span>

    ![Utelämna ämnen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="75cb9-136">(Kunskaps chefer kan också utesluta ämnen i ämnes centret efter identifiering.)</span><span class="sxs-lookup"><span data-stu-id="75cb9-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="75cb9-137">Så här utesluter du ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="75cb9-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="75cb9-138">Om du behöver undanta ämnen, efter att du har valt **Uteslut ämnen efter namn**, väljer du Hämta CSV-mallen och uppdaterar den med listan med avsnitt som du vill undanta från identifierings resultaten.</span><span class="sxs-lookup"><span data-stu-id="75cb9-138">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Uteslut avsnitt i en CSV-mall](../media/exclude-topics-csv.png) 

    <span data-ttu-id="75cb9-140">I CSV-mallen anger du följande information om de avsnitt som du vill undanta:</span><span class="sxs-lookup"><span data-stu-id="75cb9-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="75cb9-141">**Namn**: Skriv namnet på det ämne som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="75cb9-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="75cb9-142">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="75cb9-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="75cb9-143">Exakt träff: du kan ange exakt namn eller akronym (till exempel *contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="75cb9-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="75cb9-144">Ofullständig matchning: du kan exkludera alla ämnen som har ett visst ord i det.</span><span class="sxs-lookup"><span data-stu-id="75cb9-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="75cb9-145">Till exempel kommer *bågen* att exkludera alla ämnen med ord *båge* i det, till exempel *båge cirkel*, *plasma båge svets* eller *tränings båge*. Observera att den inte utesluter ämnen där texten är inkluderad som en del av ett ord, till exempel *arkitekturen*.</span><span class="sxs-lookup"><span data-stu-id="75cb9-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="75cb9-146">**Står för (valfritt)**: om du vill utesluta en akronym skriver du orden som förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="75cb9-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="75cb9-147">**MatchType-exakt/delvis**: Skriv om det namn du angav är en *exakt* eller *delvis* matchnings typ.</span><span class="sxs-lookup"><span data-stu-id="75cb9-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="75cb9-148">När du är klar med och sparat CSV-filen väljer du **Bläddra** och letar reda på den.</span><span class="sxs-lookup"><span data-stu-id="75cb9-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="75cb9-149">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-149">Select **Next**.</span></span>

6. <span data-ttu-id="75cb9-150">På sidan **vem kan se ämnen och var de kan se dem ser** du avsnitts visning.</span><span class="sxs-lookup"><span data-stu-id="75cb9-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="75cb9-151">I listan **vilka kan se ämnen i kunskaps nätverkets** inställning väljer du vilka som ska ha åtkomst till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="75cb9-151">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="75cb9-152">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="75cb9-152">You can select:</span></span>
    - <span data-ttu-id="75cb9-153">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="75cb9-154">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="75cb9-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="75cb9-155">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-155">**No one**</span></span>

    ![Vilka som kan se ämnen](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="75cb9-157">Med den här inställningen kan du välja vilken användare som helst i din organisation, men endast användare som har olika ämnen har tilldelats licenser kan se ämnen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="75cb9-158">På sidan **behörigheter för hantering av ämnen** kan du välja vem som ska kunna skapa, redigera och hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="75cb9-159">I avsnittet **vilka som kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="75cb9-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="75cb9-160">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="75cb9-161">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="75cb9-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="75cb9-162">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-162">**No one**</span></span>

    ![Behörigheter för avsnitts hantering, som kan skapa och redigera ämnen](../media/ksetup3.png) 

8. <span data-ttu-id="75cb9-164">I avsnittet **vilka kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="75cb9-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="75cb9-165">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="75cb9-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="75cb9-166">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="75cb9-166">**Only selected people or security groups**</span></span>

    ![Behörigheter för hantering av ämnen](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="75cb9-168">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-168">Select **Next**.</span></span>

9. <span data-ttu-id="75cb9-169">På sidan **skapa ämnes Center** kan du skapa en ämnes Center-webbplats där du kan visa ämnes sidor och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="75cb9-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="75cb9-170">I rutan **webbplats namn** skriver du ett namn på ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="75cb9-170">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="75cb9-171">Du kan också skriva en kort beskrivning i rutan **Beskrivning** .</span><span class="sxs-lookup"><span data-stu-id="75cb9-171">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="75cb9-172">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-172">Select **Next**.</span></span>

   ![Skapa kunskaps Center](../media/ksetup4.png)  

10. <span data-ttu-id="75cb9-174">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="75cb9-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="75cb9-175">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="75cb9-176">Sidan **kunskaps nätverk aktive rad** visar och bekräftar att systemet kommer att börja analysera dina valda webbplatser för att få hjälp med ämnen och att skapa kunskaps Center webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-176">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="75cb9-177">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-177">Select **Done**.</span></span>

12. <span data-ttu-id="75cb9-178">Du kommer att återföras till sidan **Koppla personer till kunskap** .</span><span class="sxs-lookup"><span data-stu-id="75cb9-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="75cb9-179">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="75cb9-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar tillämpas](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="75cb9-181">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="75cb9-181">Assign licenses</span></span>

<span data-ttu-id="75cb9-182">När du har konfigurerat ämnen måste du tilldela licenser för de användare som ska använda ämnes upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="75cb9-182">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="75cb9-183">Endast användare med en licens kan se information om ämnen, till exempel markeringar, ämnes kort, ämnes sidor och ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="75cb9-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="75cb9-184">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="75cb9-184">To assign licenses:</span></span>

1. <span data-ttu-id="75cb9-185">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="75cb9-186">Välj de användare som du vill licensiera och klicka på **Hantera produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-186">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="75cb9-187">Välj **Tilldela fler**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-187">Select **Assign more**.</span></span>

4. <span data-ttu-id="75cb9-188">Under **licenser** väljer du **avsnitts upplevelser**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-188">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="75cb9-189">Under **appar** bör du kontrol lera att **Graph Connectors söker med index** och att **ämnes upplevelser** är markerade.</span><span class="sxs-lookup"><span data-stu-id="75cb9-189">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="75cb9-190">![SharePoint Syntex-licenser i Administrationscentret för Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="75cb9-190">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="75cb9-191">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="75cb9-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="75cb9-192">Hantera avsnitts upplevelser</span><span class="sxs-lookup"><span data-stu-id="75cb9-192">Manage topic experiences</span></span>

<span data-ttu-id="75cb9-193">När du har konfigurerat ämnen kan du ändra inställningarna under installationen i [administrations centret för Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span><span class="sxs-lookup"><span data-stu-id="75cb9-193">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="75cb9-194">Se följande exempel:</span><span class="sxs-lookup"><span data-stu-id="75cb9-194">See the following references:</span></span>

- [<span data-ttu-id="75cb9-195">Hantera identifiering av avsnitt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-195">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="75cb9-196">Hantera ämnets synlighet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-196">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="75cb9-197">Hantera behörigheter för ämne i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-197">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="75cb9-198">Ändra namnet på ämnes centret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cb9-198">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="75cb9-199">Se även</span><span class="sxs-lookup"><span data-stu-id="75cb9-199">See also</span></span>

[<span data-ttu-id="75cb9-200">Översikt över ämnen</span><span class="sxs-lookup"><span data-stu-id="75cb9-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
