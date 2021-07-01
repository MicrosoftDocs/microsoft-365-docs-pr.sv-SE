---
title: Planera för Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Lär dig planera för Abonnemang på Microsoft Viva Topics
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229545"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="199e1-103">Planera för Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="199e1-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="199e1-104">Du har kontroll över hur ämnen upplevs i organisationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="199e1-105">Dina planeringsbeslut för ämnen säkerställer att ämnen av hög kvalitet visas för användarna och att de har rätt behörighet att använda och bidra med kunskap.</span><span class="sxs-lookup"><span data-stu-id="199e1-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="199e1-106">I den här artikeln kommer vi att undersöka följande planeringsbeslut:</span><span class="sxs-lookup"><span data-stu-id="199e1-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="199e1-107">Vilka SharePoint webbplatser du vill crawla efter ämnen</span><span class="sxs-lookup"><span data-stu-id="199e1-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="199e1-108">Vilka ämnen, om det finns några, som du vill utesluta från ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="199e1-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="199e1-109">Vilka användare vill du göra ämnen synliga för</span><span class="sxs-lookup"><span data-stu-id="199e1-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="199e1-110">Vilka användare som du vill ge behörighet att hantera ämnen i ämnescentret</span><span class="sxs-lookup"><span data-stu-id="199e1-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="199e1-111">Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnescentret</span><span class="sxs-lookup"><span data-stu-id="199e1-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="199e1-112">Vilket namn vill du ge ditt ämnescenter?</span><span class="sxs-lookup"><span data-stu-id="199e1-112">What name you want to give your topic center</span></span>

<span data-ttu-id="199e1-113">Säkerhet och sekretess för dina data respekteras och ämnesupplevelsen ger inte användarna ytterligare åtkomst till filer som de inte har rättigheter till.</span><span class="sxs-lookup"><span data-stu-id="199e1-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="199e1-114">Vi rekommenderar att du även läser [Säkerhet och sekretess för Microsoft Viva Topics](topic-experiences-security-privacy.md) som en del av planeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="199e1-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="199e1-115">Mer information om AI-tekniken bakom Viva Topics finns [i Alexandria i Microsoft Viva Ämnen: från stora data till stora kunskaper](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span><span class="sxs-lookup"><span data-stu-id="199e1-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="199e1-116">Krav</span><span class="sxs-lookup"><span data-stu-id="199e1-116">Requirements</span></span>

<span data-ttu-id="199e1-117">Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör SharePoint administratör för att få åtkomst Administrationscenter för Microsoft 365 och konfigurera Ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="199e1-118">Alla användare som ska använda Ämnen kräver en **licens för ämnesupplevelser.**</span><span class="sxs-lookup"><span data-stu-id="199e1-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="199e1-119">Tilldelning av licenser omfattas av [Konfigurera Microsoft Viva-ämnen.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="199e1-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="199e1-120">Upptäckt av ämne</span><span class="sxs-lookup"><span data-stu-id="199e1-120">Topic discovery</span></span>

<span data-ttu-id="199e1-121">Inställningarna för identifiering av ämne anger vilka SharePoint som används som källor för ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="199e1-122">Det inkluderar både klassiska och moderna webbplatser samt webbplatser som är associerade med Microsoft Teams och Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="199e1-122">This includes both classic and modern sites, as well as sites associated with Microsoft Teams and Microsoft 365 Groups.</span></span> <span data-ttu-id="199e1-123">OneDrive-webbplatserna inte ingår.</span><span class="sxs-lookup"><span data-stu-id="199e1-123">OneDrive sites are not included.</span></span>

<span data-ttu-id="199e1-124">Du kan välja att inkludera SharePoint webbplatser, en viss lista med webbplatser eller inga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="199e1-124">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="199e1-125">Vi rekommenderar att du väljer alla webbplatser så att ämnesupplevelsen kan upptäcka ett stort antal bra ämnen för användarna.</span><span class="sxs-lookup"><span data-stu-id="199e1-125">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="199e1-126">När du konfigurerade ämnen kan du välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="199e1-126">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="199e1-127">**Alla webbplatser:** alla SharePoint webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-127">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="199e1-128">Det omfattar nuvarande och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="199e1-128">This includes current and future sites.</span></span>
- <span data-ttu-id="199e1-129">**Alla, förutom valda webbplatser:** Alla webbplatser utom de du anger.</span><span class="sxs-lookup"><span data-stu-id="199e1-129">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="199e1-130">Webbplatser som skapas i framtiden kommer att ingå som källor för upptäckt av ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-130">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="199e1-131">**Endast markerade webbplatser**: Endast de webbplatser som du anger.</span><span class="sxs-lookup"><span data-stu-id="199e1-131">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="199e1-132">Webbplatser som skapas i framtiden inkluderas inte som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="199e1-132">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="199e1-133">**Inga webbplatser**: Inkludera inte några SharePoint webbplatser.</span><span class="sxs-lookup"><span data-stu-id="199e1-133">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="199e1-134">Om du väljer **Alla, förutom valda webbplatser** eller Endast valda **webbplatser,** kan du ladda upp .csv en fil med en lista över webbplatser.</span><span class="sxs-lookup"><span data-stu-id="199e1-134">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="199e1-135">De här alternativen är användbara om du kör ett pilottest och vill ta med ett begränsat antal webbplatser att börja med.</span><span class="sxs-lookup"><span data-stu-id="199e1-135">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="199e1-136">Du kan kopiera .csv nedan:</span><span class="sxs-lookup"><span data-stu-id="199e1-136">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="199e1-137">Vi rekommenderar inte att du väljer **Inga webbplatser eftersom** det förhindrar att ämnen skapas eller uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="199e1-137">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="199e1-138">Du kan dock välja det här alternativet om du vill konfigurera Ämnen och sedan lägga till webbplatser senare.</span><span class="sxs-lookup"><span data-stu-id="199e1-138">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="199e1-139">Vi rekommenderar att du skapar en process som användare eller kunskapshanterare kan begära att enskilda webbplatser tas bort från ämnesidentifiering om det behövs i organisationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-139">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="199e1-140">Multi-geo</span><span class="sxs-lookup"><span data-stu-id="199e1-140">Multi-geo</span></span>

<span data-ttu-id="199e1-141">Om din organisation har [distribuerat Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)är ämnescentret etablerat på den centrala platsen och endast SharePoint-webbplatser på den centrala platsen är tillgängliga för användning som källor för ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-141">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="199e1-142">(Om du väljer **Alla webbplatser** används alla webbplatser i Viva Topics på den centrala platsen.)</span><span class="sxs-lookup"><span data-stu-id="199e1-142">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="199e1-143">All bearbetning och lagring av innehåll utförs på den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="199e1-143">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="199e1-144">Användarbehörigheter</span><span class="sxs-lookup"><span data-stu-id="199e1-144">User permissions</span></span>

<span data-ttu-id="199e1-145">De användarbehörigheter som du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.</span><span class="sxs-lookup"><span data-stu-id="199e1-145">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="199e1-146">För stunden har Viva Topics inte stöd för att tillhandahålla licenser eller användarbehörigheter för gästanvändare (externa).</span><span class="sxs-lookup"><span data-stu-id="199e1-146">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="199e1-147">*Hantera ämnen*</span><span class="sxs-lookup"><span data-stu-id="199e1-147">*Manage topics*</span></span>

<span data-ttu-id="199e1-148">Kunskapschefer övervakar kvaliteten på informationen, hur den strukturerade och andra metodtips i din organisation.</span><span class="sxs-lookup"><span data-stu-id="199e1-148">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="199e1-149">De kan bekräfta och avvisa ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-149">They can confirm and reject topics.</span></span>

<span data-ttu-id="199e1-150">Du kan ange enskilda ämneshanterare, men vi rekommenderar att du skapar en säkerhetsgrupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskapshanterare.</span><span class="sxs-lookup"><span data-stu-id="199e1-150">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="199e1-151">Du kan ange den här säkerhetsgruppen under installationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-151">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="199e1-152">*Skapa och redigera ämnen*</span><span class="sxs-lookup"><span data-stu-id="199e1-152">*Create and edit topics*</span></span>

<span data-ttu-id="199e1-153">Ämnesdeltagare är mästare och ämnesexperter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-153">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="199e1-154">De kan skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="199e1-154">They can create and edit topics.</span></span> 

<span data-ttu-id="199e1-155">Vi rekommenderar att du låter alla i organisationen skapa och redigera ämnen eftersom ämnesupplevelsen fungerar bäst när alla användare kan dela information.</span><span class="sxs-lookup"><span data-stu-id="199e1-155">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="199e1-156">Om du vill begränsa skapandet och redigeringen av ämnen till specifika personer eller grupper, skapar du en säkerhetsgrupp för dem och anger den under installationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-156">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="199e1-157">Du kan välja att inte tillåta någon att bidra till ämnen, men detta rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="199e1-157">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="199e1-158">Kunskapschefer kommer fortfarande att kunna redigera och skapa ämnen om du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="199e1-158">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="199e1-159">*Ämnes läsare*</span><span class="sxs-lookup"><span data-stu-id="199e1-159">*Topic viewers*</span></span>

<span data-ttu-id="199e1-160">Ämneslyssarna kan se information på ämnessidor, i sökresultat och när ämnen markeras i innehållet SharePoint sidor.</span><span class="sxs-lookup"><span data-stu-id="199e1-160">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="199e1-161">Användare kan bara se upptäckta ämnen när de har åtkomst till filer och sidor som ämnet identifierats i.</span><span class="sxs-lookup"><span data-stu-id="199e1-161">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="199e1-162">När du ställer in ämnes läsare kan du välja bland:</span><span class="sxs-lookup"><span data-stu-id="199e1-162">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="199e1-163">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="199e1-163">**Everyone in my organization**</span></span>
- <span data-ttu-id="199e1-164">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="199e1-164">**Only selected people or security groups**</span></span>
- <span data-ttu-id="199e1-165">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="199e1-165">**No one**</span></span>

<span data-ttu-id="199e1-166">Vi rekommenderar **Alla i min organisation,** men om du kör ett pilottest kan det vara bra att välja endast valda personer eller säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="199e1-166">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="199e1-167">Du kan också välja **Ingen om** du vill konfigurera Ämnen, men inte tillåta att andra ser ämnen ännu.</span><span class="sxs-lookup"><span data-stu-id="199e1-167">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="199e1-168">(Knowledge Managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span><span class="sxs-lookup"><span data-stu-id="199e1-168">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="199e1-169">Kunskapsregler</span><span class="sxs-lookup"><span data-stu-id="199e1-169">Knowledge rules</span></span>

<span data-ttu-id="199e1-170">Som administratör kan du utesluta vissa ämnen från olika ämnesupplevelser.</span><span class="sxs-lookup"><span data-stu-id="199e1-170">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="199e1-171">Det här är användbart om du vill se till att känsliga data inte visas i avsnitt.</span><span class="sxs-lookup"><span data-stu-id="199e1-171">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="199e1-172">Knowledge Managers kan utesluta ämnen i ämnescentret, men ämnen som utesluts av administratören är inte ens synliga för kunskapschefer.</span><span class="sxs-lookup"><span data-stu-id="199e1-172">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="199e1-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span><span class="sxs-lookup"><span data-stu-id="199e1-173">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="199e1-174">Om du vill utesluta ämnen på administratörsnivå måste du lägga till dem i .csv filen och ladda upp filen.</span><span class="sxs-lookup"><span data-stu-id="199e1-174">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="199e1-175">Du kan göra detta under installationen eller senare.</span><span class="sxs-lookup"><span data-stu-id="199e1-175">You can do this during setup or later.</span></span>

<span data-ttu-id="199e1-176">Filen .csv måste innehålla följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="199e1-176">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="199e1-177">**Namn**: Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="199e1-177">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="199e1-178">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="199e1-178">There are two ways to do this:</span></span>
- <span data-ttu-id="199e1-179">**MatchType-Exact/Partial**: Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="199e1-179">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="199e1-180">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="199e1-180">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="199e1-181">Delvis matchning: Du kan utesluta alla avsnitt som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="199e1-181">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="199e1-182">En båge *utesluter* till exempel  alla ämnen som innehåller ordet båge, t.ex. arcuscirkel,  *Arcus* arcus- eller *utbildningsbåge.* Observera att den inte exkluderar ämnen där texten ingår i ett ord, till exempel *Arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="199e1-182">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="199e1-183">**Står för (valfritt)**: (kallas även *expansion*) Om du vill utesluta en förkortning skriver du orden förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="199e1-183">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Utesluta ämnen i CSV-mallen](../media/exclude-topics-csv.png) 

<span data-ttu-id="199e1-185">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="199e1-185">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="199e1-186">Administration</span><span class="sxs-lookup"><span data-stu-id="199e1-186">Administration</span></span>

<span data-ttu-id="199e1-187">När du ställer in Ämnen skapas ett ämnescenter automatiskt som en del av installationen.</span><span class="sxs-lookup"><span data-stu-id="199e1-187">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="199e1-188">Fundera på vad du vill ge ämnescentret ett namn och vad du vill att URL-adressen ska vara.</span><span class="sxs-lookup"><span data-stu-id="199e1-188">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="199e1-189">Du kan ange både namn och URL-adress som en del av installationsprocessen och du kan ändra namnet (men inte URL:en) senare i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="199e1-189">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="199e1-190">Du kan bara ha ett ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="199e1-190">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="199e1-191">Checklista för konfiguration</span><span class="sxs-lookup"><span data-stu-id="199e1-191">Setup checklist</span></span>

<span data-ttu-id="199e1-192">När du skapar ämnesupplevelser behöver du följande när du går igenom installationsguiden:</span><span class="sxs-lookup"><span data-stu-id="199e1-192">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="199e1-193">Lista över webbplatser som ska inkluderas eller uteslutas om de inte omfattar alla webbplatser för ämnesidentifiering</span><span class="sxs-lookup"><span data-stu-id="199e1-193">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="199e1-194">Säkerhetsgrupp för ämnesvyer om inte alla användare kan visa ämnen</span><span class="sxs-lookup"><span data-stu-id="199e1-194">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="199e1-195">Säkerhetsgrupp för ämnesdeltagare om inte alla användare kan skapa och redigera ämnen</span><span class="sxs-lookup"><span data-stu-id="199e1-195">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="199e1-196">Säkerhetsgrupp för ämneshanterare om inte alla användare får hantera ämnen</span><span class="sxs-lookup"><span data-stu-id="199e1-196">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="199e1-197">Lista över känsliga ämnen som ska undantas från ämnesidentifiering</span><span class="sxs-lookup"><span data-stu-id="199e1-197">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="199e1-198">Ett namn på webbplatsen för ämnescentret</span><span class="sxs-lookup"><span data-stu-id="199e1-198">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="199e1-199">Se även</span><span class="sxs-lookup"><span data-stu-id="199e1-199">See also</span></span>

[<span data-ttu-id="199e1-200">Konfigurera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="199e1-200">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="199e1-201">Hantera ämnesidentifiering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="199e1-201">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="199e1-202">Hantera synligheten för ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="199e1-202">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="199e1-203">Hantera ämnesbehörigheter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="199e1-203">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="199e1-204">Ändra namnet på ämnescentret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="199e1-204">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
