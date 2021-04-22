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
description: Lär dig hur du ställer in Microsoft Viva-ämnen
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930227"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="641cb-103">Konfigurera Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="641cb-104">Du kan använda administrationscentret för Microsoft 365 för att konfigurera [ämnen.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="641cb-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="641cb-105">Det är viktigt att planera det bästa sättet att konfigurera ämnen i din miljö.</span><span class="sxs-lookup"><span data-stu-id="641cb-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="641cb-106">Läs Planera för [Microsoft Viva Topics innan du](plan-topic-experiences.md) börjar med procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="641cb-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="641cb-107">Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör eller SharePoint-administratör för att få åtkomst till administrationscentret för Microsoft 365 och konfigurera Ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="641cb-108">Om du har konfigurerat SharePoint så att [hanterade enheter](/sharepoint/control-access-from-unmanaged-devices)krävs måste du konfigurera Ämnen från en hanterad enhet.</span><span class="sxs-lookup"><span data-stu-id="641cb-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="641cb-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="641cb-109">Video demonstration</span></span>

<span data-ttu-id="641cb-110">Den här videon visar processen för att konfigurera ämnen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641cb-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="641cb-111">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="641cb-111">Assign licenses</span></span>

<span data-ttu-id="641cb-112">Du måste tilldela licenser för de användare som ska använda ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="641cb-113">Endast användare med en licens kan se information om ämnen, till exempel höjdpunkter, ämneskort, ämnessidor och ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="641cb-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="641cb-114">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="641cb-114">To assign licenses:</span></span>

1. <span data-ttu-id="641cb-115">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="641cb-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="641cb-116">Välj de användare som du vill licensiera och klicka på **Licenser och appar.**</span><span class="sxs-lookup"><span data-stu-id="641cb-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="641cb-117">Under **Licenser** väljer du **Viva Ämnen.**</span><span class="sxs-lookup"><span data-stu-id="641cb-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="641cb-118">Kontrollera **att** sökningen med **Index (Viva Topics)** och **Viva** Topics är markerad under Appar.</span><span class="sxs-lookup"><span data-stu-id="641cb-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="641cb-119">![Microsoft Viva Topics-licenser i administrationscentret för Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="641cb-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="641cb-120">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="641cb-120">Click **Save changes**.</span></span>

<span data-ttu-id="641cb-121">Det kan ta upp till en timme för användarna att få åtkomst till Ämnen när licenserna har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="641cb-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="641cb-122">Konfigurera ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-122">Set up Topics</span></span>

<span data-ttu-id="641cb-123">Så här ställer du in ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-123">To set up Topics</span></span>

1. <span data-ttu-id="641cb-124">I [administrationscentret för Microsoft 365](https://admin.microsoft.com)väljer **du Konfigurera** och visar sedan **avsnittet Filer och** innehåll.</span><span class="sxs-lookup"><span data-stu-id="641cb-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="641cb-125">I avsnittet **Filer och innehåll** klickar du på Anslut personer till **kunskap.**</span><span class="sxs-lookup"><span data-stu-id="641cb-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Koppla personer till kunskap](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="641cb-127">På sidan **Anslut personer till kunskap** klickar du på Kom **igång** så får du de steg för steg som gäller installationen.</span><span class="sxs-lookup"><span data-stu-id="641cb-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Komma igång](../media/k-get-started.png) 

4. <span data-ttu-id="641cb-129">På sidan **Välj hur Viva Ämnen kan hitta ämnen** konfigurerar du identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="641cb-130">I avsnittet **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som crawlas som källor för ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="641cb-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="641cb-131">Välj mellan:</span><span class="sxs-lookup"><span data-stu-id="641cb-131">Choose from:</span></span>
    - <span data-ttu-id="641cb-132">**Alla webbplatser:** Alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="641cb-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="641cb-133">Det omfattar nuvarande och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="641cb-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="641cb-134">**Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="641cb-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="641cb-135">Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering.</span><span class="sxs-lookup"><span data-stu-id="641cb-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="641cb-136">Webbplatser som skapas i framtiden kommer att ingå som källor för upptäckt av ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="641cb-137">**Endast valda webbplatser**: Skriv namnen på de webbplatser som du vill ska ingå.</span><span class="sxs-lookup"><span data-stu-id="641cb-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="641cb-138">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="641cb-138">You can also upload a list of sites.</span></span> <span data-ttu-id="641cb-139">Webbplatser som skapas i framtiden inkluderas inte som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="641cb-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="641cb-140">**Inga webbplatser**: Inkludera inte några SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="641cb-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Välj hur du hittar ämnen](../media/ksetup1.png) 
   
5. <span data-ttu-id="641cb-142">I avsnittet **Exkludera ämnen efter namn** kan du lägga till namn på ämnen som du inte vill ska upptäckas.</span><span class="sxs-lookup"><span data-stu-id="641cb-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="641cb-143">Använd den här inställningen för att förhindra att känslig information inkluderas som ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="641cb-144">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="641cb-144">The options are:</span></span>
    - <span data-ttu-id="641cb-145">**Undanta inte några ämnen**</span><span class="sxs-lookup"><span data-stu-id="641cb-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="641cb-146">**Utesluta ämnen efter namn**</span><span class="sxs-lookup"><span data-stu-id="641cb-146">**Exclude topics by name**</span></span>

    ![Undanta ämnen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="641cb-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span><span class="sxs-lookup"><span data-stu-id="641cb-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="641cb-149">Så här utesluter du ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="641cb-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="641cb-150">Om du behöver utesluta ämnen efter att ha valt Exkludera ämnen efter namn laddar du ned CSV-mallen och uppdaterar den med listan över ämnen som du vill utesluta från dina identifieringsresultat.</span><span class="sxs-lookup"><span data-stu-id="641cb-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Utesluta ämnen i CSV-mallen](../media/exclude-topics-csv.png) 

    <span data-ttu-id="641cb-152">I CSV-mallen anger du följande information om de ämnen som du inte vill ska ingå:</span><span class="sxs-lookup"><span data-stu-id="641cb-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="641cb-153">**Namn**: Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="641cb-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="641cb-154">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="641cb-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="641cb-155">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="641cb-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="641cb-156">Delvis matchning: Du kan utesluta alla avsnitt som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="641cb-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="641cb-157">En båge *utesluter* till exempel  alla ämnen som innehåller ordet båge, t.ex. arcuscirkel,  *Arcus* arcus- eller *utbildningsbåge.* Observera att den inte exkluderar ämnen där texten ingår i ett ord, till exempel *Arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="641cb-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="641cb-158">**Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="641cb-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="641cb-159">**MatchType-Exact/Partial**: Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="641cb-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="641cb-160">När du har slutfört och sparat CSV-filen väljer du Bläddra **för att** leta reda på och välja den.</span><span class="sxs-lookup"><span data-stu-id="641cb-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="641cb-161">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="641cb-161">Select **Next**.</span></span>

6. <span data-ttu-id="641cb-162">På sidan **Vilka som kan se ämnen och var de kan se dem** konfigurerar du avsnittets synlighet.</span><span class="sxs-lookup"><span data-stu-id="641cb-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="641cb-163">I inställningen **Vilka kan se ämnen** väljer du vilka som ska ha åtkomst till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sökningar och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="641cb-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="641cb-164">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="641cb-164">You can select:</span></span>
    - <span data-ttu-id="641cb-165">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="641cb-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="641cb-166">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="641cb-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="641cb-167">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="641cb-167">**No one**</span></span>

    ![Vilka kan se ämnen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="641cb-169">Med den här inställningen kan du välja vilken användare som helst i organisationen, men endast användare som har tilldelats ämneserfarenhetslicenser kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="641cb-170">På sidan **Behörigheter för ämneshantering** väljer du vilka som ska kunna skapa, redigera eller hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="641cb-171">I avsnittet **Vem kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="641cb-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="641cb-172">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="641cb-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="641cb-173">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="641cb-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="641cb-174">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="641cb-174">**No one**</span></span>

    ![Behörigheter för ämneshantering, vem som kan skapa och redigera ämnen](../media/ksetup3.png) 

8. <span data-ttu-id="641cb-176">I avsnittet **Vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="641cb-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="641cb-177">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="641cb-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="641cb-178">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="641cb-178">**Only selected people or security groups**</span></span>

    ![Behörigheter för ämneshantering](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="641cb-180">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="641cb-180">Select **Next**.</span></span>

9. <span data-ttu-id="641cb-181">På sidan **Skapa ämnescenter** kan du skapa en ämnescenterwebbplats där ämnessidor kan visas och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="641cb-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="641cb-182">Ange **ett namn** på ämnescentret i rutan Webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="641cb-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="641cb-183">Du kan också skriva en kort beskrivning i **rutan** Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="641cb-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="641cb-184">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="641cb-184">Select **Next**.</span></span>

   ![Skapa Knowledge Center](../media/ksetup4.png)  

10. <span data-ttu-id="641cb-186">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="641cb-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="641cb-187">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="641cb-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="641cb-188">Sidan **Viva Ämnen som** har aktiverats visas och bekräftar att systemet nu börjar analysera valda webbplatser för ämnen och skapa webbplatsen för ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="641cb-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="641cb-189">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="641cb-189">Select **Done**.</span></span>

12. <span data-ttu-id="641cb-190">Du kommer nu tillbaka till **kunskapssidan för Anslut personer till** kunskap.</span><span class="sxs-lookup"><span data-stu-id="641cb-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="641cb-191">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="641cb-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar som används](../media/ksetup7.png)    

<span data-ttu-id="641cb-193">Observera att första gången ämnesidentifiering är aktiverat kan det ta upp till två veckor för alla föreslagna ämnen att visas i vyn Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="641cb-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="641cb-194">Ämnesidentifiering fortsätter allt eftersom nytt innehåll eller uppdateringar av innehåll görs.</span><span class="sxs-lookup"><span data-stu-id="641cb-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="641cb-195">Det är normalt att ha fluktuationer i antalet föreslagna ämnen i organisationen eftersom Viva Topics utvärderar ny information.</span><span class="sxs-lookup"><span data-stu-id="641cb-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="641cb-196">Hantera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="641cb-196">Manage topic experiences</span></span>

<span data-ttu-id="641cb-197">När du har ställt in Ämnen kan du ändra inställningarna som du valde vid installationen i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="641cb-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="641cb-198">Se följande exempel:</span><span class="sxs-lookup"><span data-stu-id="641cb-198">See the following references:</span></span>

- [<span data-ttu-id="641cb-199">Hantera identifiering av ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="641cb-200">Hantera synlighet för ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="641cb-201">Hantera ämnesbehörigheter i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="641cb-202">Ändra namnet på ämnescentret i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="641cb-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="641cb-203">Se även</span><span class="sxs-lookup"><span data-stu-id="641cb-203">See also</span></span>

[<span data-ttu-id="641cb-204">Översikt över ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="641cb-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
