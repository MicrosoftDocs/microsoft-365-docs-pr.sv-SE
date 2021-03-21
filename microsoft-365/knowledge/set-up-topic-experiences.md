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
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929450"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="47fe6-103">Konfigurera Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="47fe6-104">Du kan använda administrationscentret för Microsoft 365 för att konfigurera [ämnen.](topic-experiences-overview.md)</span><span class="sxs-lookup"><span data-stu-id="47fe6-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="47fe6-105">Det är viktigt att planera det bästa sättet att konfigurera ämnen i din miljö.</span><span class="sxs-lookup"><span data-stu-id="47fe6-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="47fe6-106">Läs Planera för [Microsoft Viva Topics innan du](plan-topic-experiences.md) börjar med procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="47fe6-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="47fe6-107">Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör eller SharePoint-administratör för att få åtkomst till administrationscentret för Microsoft 365 och konfigurera Ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="47fe6-108">Om du har konfigurerat SharePoint så att [hanterade enheter](/sharepoint/control-access-from-unmanaged-devices)krävs måste du konfigurera Ämnen från en hanterad enhet.</span><span class="sxs-lookup"><span data-stu-id="47fe6-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="47fe6-109">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="47fe6-109">Video demonstration</span></span>

<span data-ttu-id="47fe6-110">Den här videon visar processen för att konfigurera ämnen i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47fe6-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="47fe6-111">Konfigurera ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-111">Set up Topics</span></span>

<span data-ttu-id="47fe6-112">Så här ställer du in ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-112">To set up Topics</span></span>

1. <span data-ttu-id="47fe6-113">I [administrationscentret för Microsoft 365](https://admin.microsoft.com)väljer **du Konfigurera** och visar sedan **avsnittet Filer och** innehåll.</span><span class="sxs-lookup"><span data-stu-id="47fe6-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="47fe6-114">I avsnittet **Filer och innehåll** klickar du på Anslut personer till **kunskap.**</span><span class="sxs-lookup"><span data-stu-id="47fe6-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Koppla personer till kunskap](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="47fe6-116">På sidan **Anslut personer till kunskap** klickar du på Kom **igång** så får du de steg för steg som gäller installationen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![Komma igång](../media/k-get-started.png) 

4. <span data-ttu-id="47fe6-118">På sidan **Välj hur Viva Ämnen kan hitta ämnen** konfigurerar du identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="47fe6-119">I avsnittet **Välj SharePoint-ämneskällor** väljer du vilka SharePoint-webbplatser som crawlas som källor för ämnen under identifieringen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="47fe6-120">Välj mellan:</span><span class="sxs-lookup"><span data-stu-id="47fe6-120">Choose from:</span></span>
    - <span data-ttu-id="47fe6-121">**Alla webbplatser:** Alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="47fe6-122">Det omfattar nuvarande och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="47fe6-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="47fe6-123">**Alla, förutom valda webbplatser:** Skriv namnen på de webbplatser som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="47fe6-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="47fe6-124">Du kan också ladda upp en lista över webbplatser som du vill avanmäla från identifiering.</span><span class="sxs-lookup"><span data-stu-id="47fe6-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="47fe6-125">Webbplatser som skapas i framtiden kommer att ingå som källor för upptäckt av ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="47fe6-126">**Endast valda webbplatser**: Skriv namnen på de webbplatser som du vill ska ingå.</span><span class="sxs-lookup"><span data-stu-id="47fe6-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="47fe6-127">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="47fe6-127">You can also upload a list of sites.</span></span> <span data-ttu-id="47fe6-128">Webbplatser som skapas i framtiden inkluderas inte som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="47fe6-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="47fe6-129">**Inga webbplatser**: Inkludera inte några SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="47fe6-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![Välj hur du hittar ämnen](../media/ksetup1.png) 
   
5. <span data-ttu-id="47fe6-131">I avsnittet **Exkludera ämnen efter namn** kan du lägga till namn på ämnen som du inte vill ska upptäckas.</span><span class="sxs-lookup"><span data-stu-id="47fe6-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="47fe6-132">Använd den här inställningen för att förhindra att känslig information inkluderas som ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="47fe6-133">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="47fe6-133">The options are:</span></span>
    - <span data-ttu-id="47fe6-134">**Undanta inte några ämnen**</span><span class="sxs-lookup"><span data-stu-id="47fe6-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="47fe6-135">**Utesluta ämnen efter namn**</span><span class="sxs-lookup"><span data-stu-id="47fe6-135">**Exclude topics by name**</span></span>

    ![Undanta ämnen](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="47fe6-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span><span class="sxs-lookup"><span data-stu-id="47fe6-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="47fe6-138">Så här utesluter du ämnen efter namn</span><span class="sxs-lookup"><span data-stu-id="47fe6-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="47fe6-139">Om du behöver utesluta ämnen efter att ha valt Exkludera ämnen efter namn laddar du ned CSV-mallen och uppdaterar den med listan över ämnen som du vill utesluta från dina identifieringsresultat.</span><span class="sxs-lookup"><span data-stu-id="47fe6-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![Utesluta ämnen i CSV-mallen](../media/exclude-topics-csv.png) 

    <span data-ttu-id="47fe6-141">I CSV-mallen anger du följande information om de ämnen som du inte vill ska ingå:</span><span class="sxs-lookup"><span data-stu-id="47fe6-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="47fe6-142">**Namn**: Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="47fe6-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="47fe6-143">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="47fe6-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="47fe6-144">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="47fe6-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="47fe6-145">Delvis matchning: Du kan utesluta alla avsnitt som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="47fe6-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="47fe6-146">En båge *utesluter* till exempel  alla ämnen som innehåller ordet båge, t.ex. arcuscirkel,  *Arcus* arcus- eller *utbildningsbåge.* Observera att den inte exkluderar ämnen där texten ingår i ett ord, till exempel *Arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="47fe6-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="47fe6-147">**Står för (valfritt)**: Om du vill utesluta en förkortning skriver du orden förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="47fe6-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="47fe6-148">**MatchType-Exact/Partial**: Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="47fe6-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="47fe6-149">När du har slutfört och sparat CSV-filen väljer du Bläddra **för att** leta reda på och välja den.</span><span class="sxs-lookup"><span data-stu-id="47fe6-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="47fe6-150">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-150">Select **Next**.</span></span>

6. <span data-ttu-id="47fe6-151">På sidan **Vilka som kan se ämnen och var de kan se dem** konfigurerar du avsnittets synlighet.</span><span class="sxs-lookup"><span data-stu-id="47fe6-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="47fe6-152">I inställningen **Vilka kan se ämnen** väljer du vilka som ska ha åtkomst till ämnesinformation, till exempel markerade ämnen, ämneskort, ämnessvar i sökningar och ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="47fe6-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="47fe6-153">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="47fe6-153">You can select:</span></span>
    - <span data-ttu-id="47fe6-154">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="47fe6-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="47fe6-155">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="47fe6-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="47fe6-156">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="47fe6-156">**No one**</span></span>

    ![Vilka kan se ämnen](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="47fe6-158">Med den här inställningen kan du välja vilken användare som helst i organisationen, men endast användare som har tilldelats ämneserfarenhetslicenser kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="47fe6-159">På sidan **Behörigheter för ämneshantering** väljer du vilka som ska kunna skapa, redigera eller hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="47fe6-160">I avsnittet **Vem kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="47fe6-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="47fe6-161">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="47fe6-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="47fe6-162">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="47fe6-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="47fe6-163">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="47fe6-163">**No one**</span></span>

    ![Behörigheter för ämneshantering, vem som kan skapa och redigera ämnen](../media/ksetup3.png) 

8. <span data-ttu-id="47fe6-165">I avsnittet **Vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="47fe6-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="47fe6-166">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="47fe6-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="47fe6-167">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="47fe6-167">**Only selected people or security groups**</span></span>

    ![Behörigheter för ämneshantering](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="47fe6-169">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-169">Select **Next**.</span></span>

9. <span data-ttu-id="47fe6-170">På sidan **Skapa ämnescenter** kan du skapa en ämnescenterwebbplats där ämnessidor kan visas och ämnen kan hanteras.</span><span class="sxs-lookup"><span data-stu-id="47fe6-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="47fe6-171">Ange **ett namn** på ämnescentret i rutan Webbplatsnamn.</span><span class="sxs-lookup"><span data-stu-id="47fe6-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="47fe6-172">Du kan också skriva en kort beskrivning i **rutan** Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="47fe6-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="47fe6-173">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-173">Select **Next**.</span></span>

   ![Skapa Knowledge Center](../media/ksetup4.png)  

10. <span data-ttu-id="47fe6-175">På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="47fe6-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="47fe6-176">Om du är nöjd med dina val väljer du **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="47fe6-177">Sidan **Viva Ämnen som** har aktiverats visas och bekräftar att systemet nu börjar analysera valda webbplatser för ämnen och skapa webbplatsen för ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="47fe6-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="47fe6-178">Välj **Klar**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-178">Select **Done**.</span></span>

12. <span data-ttu-id="47fe6-179">Du kommer nu tillbaka till **kunskapssidan för Anslut personer till** kunskap.</span><span class="sxs-lookup"><span data-stu-id="47fe6-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="47fe6-180">På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="47fe6-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![Inställningar som används](../media/ksetup7.png)    

<span data-ttu-id="47fe6-182">Observera att första gången ämnesidentifiering är aktiverat kan det ta upp till två veckor för alla föreslagna ämnen att visas i vyn Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-182">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="47fe6-183">Ämnesidentifiering fortsätter allt eftersom nytt innehåll eller uppdateringar av innehåll görs.</span><span class="sxs-lookup"><span data-stu-id="47fe6-183">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="47fe6-184">Det är normalt att ha fluktuationer i antalet föreslagna ämnen i organisationen eftersom Viva Topics utvärderar ny information.</span><span class="sxs-lookup"><span data-stu-id="47fe6-184">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="47fe6-185">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="47fe6-185">Assign licenses</span></span>

<span data-ttu-id="47fe6-186">När du har konfigurerat ämnesupplevelsen måste du tilldela licenser för de användare som kommer att använda ämnen.</span><span class="sxs-lookup"><span data-stu-id="47fe6-186">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="47fe6-187">Endast användare med en licens kan se information om ämnen, till exempel höjdpunkter, ämneskort, ämnessidor och ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="47fe6-187">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="47fe6-188">För att tilldela licenser:</span><span class="sxs-lookup"><span data-stu-id="47fe6-188">To assign licenses:</span></span>

1. <span data-ttu-id="47fe6-189">I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-189">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="47fe6-190">Välj de användare som du vill licensiera och klicka på **Licenser och appar.**</span><span class="sxs-lookup"><span data-stu-id="47fe6-190">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="47fe6-191">Under **Licenser** väljer du **Viva Ämnen.**</span><span class="sxs-lookup"><span data-stu-id="47fe6-191">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="47fe6-192">Kontrollera **att** sökningen med **Index (Viva Topics)** och **Viva** Topics är markerad under Appar.</span><span class="sxs-lookup"><span data-stu-id="47fe6-192">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47fe6-193">![Microsoft Viva Topics-licenser i administrationscentret för Microsoft 365](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="47fe6-193">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="47fe6-194">Klicka på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="47fe6-194">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="47fe6-195">Hantera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="47fe6-195">Manage topic experiences</span></span>

<span data-ttu-id="47fe6-196">När du har ställt in Ämnen kan du ändra inställningarna som du valde vid installationen i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="47fe6-196">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="47fe6-197">Se följande exempel:</span><span class="sxs-lookup"><span data-stu-id="47fe6-197">See the following references:</span></span>

- [<span data-ttu-id="47fe6-198">Hantera identifiering av ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-198">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="47fe6-199">Hantera synlighet för ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-199">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="47fe6-200">Hantera ämnesbehörigheter i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-200">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="47fe6-201">Ändra namnet på ämnescentret i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="47fe6-201">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="47fe6-202">Se även</span><span class="sxs-lookup"><span data-stu-id="47fe6-202">See also</span></span>

[<span data-ttu-id="47fe6-203">Översikt över ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="47fe6-203">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
