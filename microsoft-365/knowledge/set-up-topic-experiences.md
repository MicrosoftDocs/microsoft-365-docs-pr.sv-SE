---
title: Konfigurera Microsoft Viva-ämnen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig konfigurera Microsoft Viva-ämnen
ms.openlocfilehash: cc420a0631f5b861341116abcd50cfe90e15450e
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551897"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="21348-103">Konfigurera Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="21348-104">Du kan använda administrationscentret för Microsoft 365 för att konfigurera [ämnen.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="21348-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="21348-105">Det är viktigt att planera det bästa sättet att konfigurera och konfigurera ämnen i din miljö.</span><span class="sxs-lookup"><span data-stu-id="21348-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="21348-106">Läs Plan för [Microsoft Viva Topics innan du](plan-topic-experiences.md) påbörjar procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="21348-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="21348-107">Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör eller SharePoint-administratör för att få åtkomst till administrationscentret för Microsoft 365 och konfigurera ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="21348-108">Om du har konfigurerat SharePoint så att [hanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)krävs måste du konfigurera Ämnen från en hanterad enhet.</span><span class="sxs-lookup"><span data-stu-id="21348-108">If you have configured SharePoint to [require managed devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="21348-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="21348-109">Video demonstration</span></span>

<span data-ttu-id="21348-110">I den här videon visas processen för att konfigurera ämnen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="21348-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="21348-111">Konfigurera ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-111">Set up Topics</span></span>

<span data-ttu-id="21348-112">Så här ställer du in ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-112">To set up Topics</span></span>

1. <span data-ttu-id="21348-113">I [administrationscentret för Microsoft 365](https://admin.microsoft.com)väljer du **Installation** och visar sedan **avsnittet Filer och** innehåll.</span><span class="sxs-lookup"><span data-stu-id="21348-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="21348-114">Klicka på **Anslut personer till** kunskap i avsnittet Filer och **innehåll.**</span><span class="sxs-lookup"><span data-stu-id="21348-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Koppla samman personer med kunskap](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="21348-116">På sidan **Anslut personer till kunskap** klickar du på Kom **igång** så får du hjälp med installationen.</span><span class="sxs-lookup"><span data-stu-id="21348-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Komma igång](../media/k-get-started.png) 

4. <span data-ttu-id="21348-118">På sidan **Välj hur Viva Ämnen kan hitta ämnen konfigurerar** du identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="21348-119">I avsnittet **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="21348-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="21348-120">Välj mellan:</span><span class="sxs-lookup"><span data-stu-id="21348-120">Choose from:</span></span>
    - <span data-ttu-id="21348-121">**Alla webbplatser:** Alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="21348-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="21348-122">Det omfattar aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="21348-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="21348-123">**Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="21348-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="21348-124">Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering.</span><span class="sxs-lookup"><span data-stu-id="21348-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="21348-125">Webbplatser som skapas i framtiden kommer att ingå som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="21348-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="21348-126">**Endast valda webbplatser:** Skriv namnen på de webbplatser som du vill ska ingå.</span><span class="sxs-lookup"><span data-stu-id="21348-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="21348-127">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="21348-127">You can also upload a list of sites.</span></span> <span data-ttu-id="21348-128">Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="21348-129">**Inga webbplatser:** Inkludera inte några SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="21348-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Välj hur du vill hitta ämnen](../media/ksetup1.png) 
   
5. <span data-ttu-id="21348-131">I avsnittet **Exkludera ämnen efter namn** kan du lägga till namn på ämnen som du inte vill ska upptäckas.</span><span class="sxs-lookup"><span data-stu-id="21348-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="21348-132">Använd den här inställningen för att förhindra att känslig information inkluderas som ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="21348-133">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="21348-133">The options are:</span></span>
    - <span data-ttu-id="21348-134">**Exkludera inte några ämnen**</span><span class="sxs-lookup"><span data-stu-id="21348-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="21348-135">**Utesluta ämnen efter namn**</span><span class="sxs-lookup"><span data-stu-id="21348-135">**Exclude topics by name**</span></span>

    ![Undanta ämnen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="21348-137">(Kunskapshanterare kan också utesluta ämnen i ämnescentret efter upptäckten.)</span><span class="sxs-lookup"><span data-stu-id="21348-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="21348-138">Så här utesluter du ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="21348-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="21348-139">Om du behöver utesluta ämnen ska du ladda ned CSV-mallen efter att ha valt Exkludera ämnen efter namn och uppdatera den med listan med ämnen som du inte vill ska få.</span><span class="sxs-lookup"><span data-stu-id="21348-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Utesluta ämnen i CSV-mall](../media/exclude-topics-csv.png) 

    <span data-ttu-id="21348-141">I CSV-mallen anger du följande information om de ämnen du vill utesluta:</span><span class="sxs-lookup"><span data-stu-id="21348-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="21348-142">**Namn:** Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="21348-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="21348-143">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="21348-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="21348-144">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL).*</span><span class="sxs-lookup"><span data-stu-id="21348-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="21348-145">Delvis matchning: Du kan utesluta alla ämnen som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="21348-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="21348-146">En båge *utesluter* till exempel  alla ämnen där ordet båge finns, t.ex. arcuscirkel, arcus-arcus- eller *utbildningsbåge.*  Observera att den inte exkluderar ämnen där texten ingår som en del av ett ord, till exempel *arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="21348-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="21348-147">**Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden som förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="21348-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="21348-148">**MatchType-Exact/Partial:** Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="21348-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="21348-149">När du har slutfört och sparat CSV-filen väljer du Bläddra **för att** leta reda på och välja den.</span><span class="sxs-lookup"><span data-stu-id="21348-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="21348-150">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="21348-150">Select **Next**.</span></span>

6. <span data-ttu-id="21348-151">På sidan **Vilka som kan se ämnen och var de kan se dem** konfigurerar du avsnittets synlighet.</span><span class="sxs-lookup"><span data-stu-id="21348-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="21348-152">I inställningen **Vem kan se ämnen** kan du välja vem som ska ha åtkomst till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sökningar och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="21348-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="21348-153">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="21348-153">You can select:</span></span>
    - <span data-ttu-id="21348-154">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="21348-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="21348-155">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="21348-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="21348-156">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="21348-156">**No one**</span></span>

    ![Vilka kan se ämnen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="21348-158">Med den här inställningen kan du välja vilken användare som helst i organisationen, men endast användare som har tilldelats licenser för Ämnesupplevelse kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="21348-159">På sidan **Behörigheter för ämneshantering** väljer du vilka som ska kunna skapa, redigera eller hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="21348-160">I avsnittet **Vem kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="21348-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="21348-161">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="21348-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="21348-162">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="21348-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="21348-163">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="21348-163">**No one**</span></span>

    ![Behörigheter för ämneshantering, vem som kan skapa och redigera ämnen](../media/ksetup3.png) 

8. <span data-ttu-id="21348-165">I avsnittet **Vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="21348-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="21348-166">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="21348-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="21348-167">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="21348-167">**Only selected people or security groups**</span></span>

    ![Behörigheter för ämneshantering](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="21348-169">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="21348-169">Select **Next**.</span></span>

9. <span data-ttu-id="21348-170">På sidan **Skapa ämnescenter** kan du skapa en ämnescenterwebbplats där ämnessidor kan visas och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="21348-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="21348-171">Ange ett **namn på** ämnescentret i rutan Webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="21348-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="21348-172">Du kan också skriva en kort beskrivning i **rutan** Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="21348-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="21348-173">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="21348-173">Select **Next**.</span></span>

   ![Skapa Knowledge Center](../media/ksetup4.png)  

10. <span data-ttu-id="21348-175">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="21348-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="21348-176">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="21348-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="21348-177">Sidan **Aktiverade Viva-ämnen** visas och bekräftar att systemet nu börjar analysera valda webbplatser för ämnen och skapa webbplatsen för ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="21348-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="21348-178">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="21348-178">Select **Done**.</span></span>

12. <span data-ttu-id="21348-179">Då kommer du tillbaka till din **sida för att ansluta personer till kunskap.**</span><span class="sxs-lookup"><span data-stu-id="21348-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="21348-180">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="21348-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar som används](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="21348-182">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="21348-182">Assign licenses</span></span>

<span data-ttu-id="21348-183">När du har konfigurerat ämnesupplevelsen måste du tilldela licenser för de användare som kommer att använda Ämnen.</span><span class="sxs-lookup"><span data-stu-id="21348-183">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="21348-184">Endast användare med en licens kan se information om ämnen som höjdpunkter, ämneskort, ämnessidor och ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="21348-184">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="21348-185">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="21348-185">To assign licenses:</span></span>

1. <span data-ttu-id="21348-186">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="21348-186">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="21348-187">Markera de användare som du vill licensiera och klicka **på Licenser och appar.**</span><span class="sxs-lookup"><span data-stu-id="21348-187">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="21348-188">Välj Viva Topics **under Licenser.**</span><span class="sxs-lookup"><span data-stu-id="21348-188">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="21348-189">Kontrollera **att** sökning efter **Graph-kopplingar med Index (Viva Topics)** och **Viva Topics** är markerade under Program.</span><span class="sxs-lookup"><span data-stu-id="21348-189">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

    ![Microsoft Viva Topics-licenser i administrationscentret för Microsoft 365](../media/topic-experiences-licenses.png)

5. <span data-ttu-id="21348-191">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="21348-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="21348-192">Hantera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="21348-192">Manage topic experiences</span></span>

<span data-ttu-id="21348-193">När du har ställt in Ämnen kan du ändra inställningarna som du valde vid installationen i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="21348-193">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="21348-194">Se följande exempel:</span><span class="sxs-lookup"><span data-stu-id="21348-194">See the following references:</span></span>

- [<span data-ttu-id="21348-195">Hantera identifiering av ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-195">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="21348-196">Hantera synlighet för ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-196">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="21348-197">Hantera ämnesbehörigheter i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-197">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="21348-198">Ändra namnet på ämnescentret i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="21348-198">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="21348-199">Se även</span><span class="sxs-lookup"><span data-stu-id="21348-199">See also</span></span>

[<span data-ttu-id="21348-200">Översikt över ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="21348-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
