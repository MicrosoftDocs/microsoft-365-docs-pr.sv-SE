---
title: Planera för Microsoft Viva-ämnen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Läs om hur du planerar för Microsoft Viva-ämnen
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150484"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="cc224-103">Planera för Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="cc224-104">Du har kontroll över hur ämnen upplevs i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="cc224-105">Ditt planeringsbeslut för ämnen säkerställer att ämnen av hög kvalitet visas för användarna och att de har rätt behörighet att använda och bidra med kunskap.</span><span class="sxs-lookup"><span data-stu-id="cc224-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="cc224-106">I den här artikeln undersöker vi de här planeringsbesluten:</span><span class="sxs-lookup"><span data-stu-id="cc224-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="cc224-107">Vilka SharePoint-webbplatser du vill crawla för ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="cc224-108">Vilka ämnen, om det finns några, som du vill utesluta från ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="cc224-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="cc224-109">Vilka användare vill du göra ämnen synliga för</span><span class="sxs-lookup"><span data-stu-id="cc224-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="cc224-110">Vilka användare som du vill ge behörighet till att hantera ämnen i ämnescentret</span><span class="sxs-lookup"><span data-stu-id="cc224-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="cc224-111">Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnescentret</span><span class="sxs-lookup"><span data-stu-id="cc224-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="cc224-112">Vilket namn vill du ge ämnescentret?</span><span class="sxs-lookup"><span data-stu-id="cc224-112">What name you want to give your topic center</span></span>

<span data-ttu-id="cc224-113">Säkerheten och sekretessen för dina data respekteras och ämnesupplevelsen ger inte användarna ytterligare åtkomst till filer som de inte har rättigheter till.</span><span class="sxs-lookup"><span data-stu-id="cc224-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="cc224-114">Vi rekommenderar att du även läser [säkerhet och sekretess i Microsoft Viva Topics som](topic-experiences-security-privacy.md) en del av planeringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="cc224-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc224-115">Krav</span><span class="sxs-lookup"><span data-stu-id="cc224-115">Requirements</span></span>

<span data-ttu-id="cc224-116">Du måste prenumerera [på Viva Topics](https://www.microsoft.com/microsoft-viva/topics) och vara global administratör eller SharePoint-administratör för att få åtkomst till administrationscentret för Microsoft 365 och konfigurera ämnen.</span><span class="sxs-lookup"><span data-stu-id="cc224-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="cc224-117">Alla användare som kommer att använda Ämnen kräver en **licens för ämnesupplevelser.**</span><span class="sxs-lookup"><span data-stu-id="cc224-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="cc224-118">Tilldelning av licenser omfattas av [Konfigurera Microsoft Viva-ämnen.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="cc224-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="cc224-119">Upptäckt av ämne</span><span class="sxs-lookup"><span data-stu-id="cc224-119">Topic discovery</span></span>

<span data-ttu-id="cc224-120">I inställningarna för identifiering av ämnen anges vilka SharePoint-webbplatser som används som källor för ämnen.</span><span class="sxs-lookup"><span data-stu-id="cc224-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="cc224-121">Du kan välja att ta med alla SharePoint-webbplatser, en specifik lista med webbplatser eller inga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="cc224-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="cc224-122">Vi rekommenderar att du väljer alla webbplatser så att ämnesupplevelsen kan upptäcka ett stort antal bra ämnen för användarna.</span><span class="sxs-lookup"><span data-stu-id="cc224-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="cc224-123">När du ställer in ämnen kan du välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="cc224-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="cc224-124">**Alla webbplatser:** Alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="cc224-125">Det omfattar aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="cc224-125">This includes current and future sites.</span></span>
- <span data-ttu-id="cc224-126">**Alla, förutom valda webbplatser:** Alla webbplatser utom de du anger.</span><span class="sxs-lookup"><span data-stu-id="cc224-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="cc224-127">Webbplatser som skapas i framtiden kommer att ingå som källor för ämnesidentifiering.</span><span class="sxs-lookup"><span data-stu-id="cc224-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="cc224-128">**Endast valda webbplatser**: Endast de webbplatser som du anger.</span><span class="sxs-lookup"><span data-stu-id="cc224-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="cc224-129">Webbplatser som skapas i framtiden kommer inte att inkluderas som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="cc224-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="cc224-130">**Inga webbplatser:** Inkludera inte några SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="cc224-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="cc224-131">Om du väljer **Alla, förutom valda webbplatser** **eller** Endast valda webbplatser, kan du ladda upp en CSV-fil med en lista över webbplatser.</span><span class="sxs-lookup"><span data-stu-id="cc224-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="cc224-132">De här alternativen är användbara om du kör en pilot och vill ta med ett begränsat antal webbplatser att börja med.</span><span class="sxs-lookup"><span data-stu-id="cc224-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="cc224-133">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="cc224-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="cc224-134">Vi rekommenderar inte att du väljer **Inga webbplatser eftersom** det förhindrar att ämnen skapas eller uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="cc224-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="cc224-135">Du kan dock välja det här alternativet om du vill konfigurera Ämnen och sedan lägga till webbplatser senare.</span><span class="sxs-lookup"><span data-stu-id="cc224-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="cc224-136">Vi rekommenderar att du skapar en process som användare eller kunskapshanterare kan begära att enskilda webbplatser tas bort från ämnesidentifiering om det behövs i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="cc224-137">Användarbehörigheter</span><span class="sxs-lookup"><span data-stu-id="cc224-137">User permissions</span></span>

<span data-ttu-id="cc224-138">De användarbehörigheter som du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.</span><span class="sxs-lookup"><span data-stu-id="cc224-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="cc224-139">*Hantera ämnen*</span><span class="sxs-lookup"><span data-stu-id="cc224-139">*Manage topics*</span></span>

<span data-ttu-id="cc224-140">Kunskapshanterare övervakar kvaliteten på informationen, hur den är strukturerad och andra metodtips i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="cc224-141">De kan bekräfta och avvisa ämnen.</span><span class="sxs-lookup"><span data-stu-id="cc224-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="cc224-142">Du kan ange enskilda ämneshanterare, men vi rekommenderar att du skapar en säkerhetsgrupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskapshanterare.</span><span class="sxs-lookup"><span data-stu-id="cc224-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="cc224-143">Du kan ange den här säkerhetsgruppen under installationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="cc224-144">*Skapa och redigera ämnen*</span><span class="sxs-lookup"><span data-stu-id="cc224-144">*Create and edit topics*</span></span>

<span data-ttu-id="cc224-145">Ämnesdeltagare är mästare och ämnesexperter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="cc224-146">De kan skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="cc224-146">They can create and edit topics.</span></span> 

<span data-ttu-id="cc224-147">Vi rekommenderar att du låter alla i organisationen skapa och redigera ämnen eftersom ämnesupplevelsen fungerar bäst när alla användare kan dela information.</span><span class="sxs-lookup"><span data-stu-id="cc224-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="cc224-148">Om du vill begränsa skapandet och redigeringen av ämnen till specifika personer eller grupper, skapar du en säkerhetsgrupp för dem och anger den under installationen.</span><span class="sxs-lookup"><span data-stu-id="cc224-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="cc224-149">Du kan välja att inte tillåta att någon bidrar till ämnen, men det rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="cc224-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="cc224-150">Kunskapschefer kommer fortfarande att kunna redigera och skapa ämnen om du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="cc224-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="cc224-151">*Ämnes läsare*</span><span class="sxs-lookup"><span data-stu-id="cc224-151">*Topic viewers*</span></span>

<span data-ttu-id="cc224-152">Ämnes läsare kan se information på ämnessidor, i sökresultat och när ämnen markeras i innehåll som SharePoint-sidor.</span><span class="sxs-lookup"><span data-stu-id="cc224-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="cc224-153">Användare kan bara se upptäckta ämnen när de har åtkomst till filer och sidor som ämnet identifierats i.</span><span class="sxs-lookup"><span data-stu-id="cc224-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="cc224-154">När du inställningar för ämnes läsare kan du välja bland:</span><span class="sxs-lookup"><span data-stu-id="cc224-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="cc224-155">**Alla i min organisation**</span><span class="sxs-lookup"><span data-stu-id="cc224-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="cc224-156">**Endast valda personer eller säkerhetsgrupper**</span><span class="sxs-lookup"><span data-stu-id="cc224-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="cc224-157">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="cc224-157">**No one**</span></span>

<span data-ttu-id="cc224-158">Vi rekommenderar **Alla i min organisation,** men om du kör ett pilottest kanske du bara vill välja valda personer eller säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="cc224-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="cc224-159">Du kan också välja **Ingen om** du vill konfigurera Ämnen, men inte tillåta att andra ser ämnen ännu.</span><span class="sxs-lookup"><span data-stu-id="cc224-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="cc224-160">(Kunskapshanterare har fortfarande åtkomst till att visa ämnen och hjälpa till med beslutet att göra ämnen allmänt tillgängliga.)</span><span class="sxs-lookup"><span data-stu-id="cc224-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="cc224-161">Kunskapsregler</span><span class="sxs-lookup"><span data-stu-id="cc224-161">Knowledge rules</span></span>

<span data-ttu-id="cc224-162">Som administratör kan du utesluta vissa ämnen från ämnesupplevelser.</span><span class="sxs-lookup"><span data-stu-id="cc224-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="cc224-163">Det är användbart om du vill se till att känsliga data inte visas i avsnitten.</span><span class="sxs-lookup"><span data-stu-id="cc224-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="cc224-164">Knowledge Managers kan utesluta ämnen i ämnescentret, men ämnen som utesluts av administratören är inte ens synliga för kunskapschefer.</span><span class="sxs-lookup"><span data-stu-id="cc224-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="cc224-165">(Knowledge Managers kan också ta bort ämnen i ämnescentret efter upptäckten.)</span><span class="sxs-lookup"><span data-stu-id="cc224-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="cc224-166">Om du vill utesluta ämnen på administratörsnivå måste du lägga till dem i en CSV-fil och ladda upp filen.</span><span class="sxs-lookup"><span data-stu-id="cc224-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="cc224-167">Det kan du göra under installationen eller senare.</span><span class="sxs-lookup"><span data-stu-id="cc224-167">You can do this during setup or later.</span></span>

<span data-ttu-id="cc224-168">CSV-filen måste innehålla följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="cc224-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="cc224-169">**Namn:** Skriv namnet på det ämne som du vill utesluta.</span><span class="sxs-lookup"><span data-stu-id="cc224-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="cc224-170">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="cc224-170">There are two ways to do this:</span></span>
- <span data-ttu-id="cc224-171">**MatchType-Exact/Partial:** Ange om namnet du angav var en *exakt eller* *delvis* matchningstyp.</span><span class="sxs-lookup"><span data-stu-id="cc224-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="cc224-172">Exakt matchning: Du kan ta med det exakta namnet eller förkortningen (till exempel *Contoso* eller *ATL).*</span><span class="sxs-lookup"><span data-stu-id="cc224-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="cc224-173">Delvis matchning: Du kan utesluta alla ämnen som innehåller ett visst ord.</span><span class="sxs-lookup"><span data-stu-id="cc224-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="cc224-174">En båge *utesluter* till exempel  alla ämnen där ordet båge finns, t.ex. arcuscirkel, arcus-arcus- eller *utbildningsbåge.*  Observera att den inte exkluderar ämnen där texten ingår som en del av ett ord, till exempel *arkitektur.*</span><span class="sxs-lookup"><span data-stu-id="cc224-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="cc224-175">**Står för (valfritt)**: (Kallas även *expansion)* Om du vill utesluta en förkortning skriver du orden som förkortningen står för.</span><span class="sxs-lookup"><span data-stu-id="cc224-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Utesluta ämnen i CSV-mall](../media/exclude-topics-csv.png) 

<span data-ttu-id="cc224-177">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="cc224-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="cc224-178">Administration</span><span class="sxs-lookup"><span data-stu-id="cc224-178">Administration</span></span>

<span data-ttu-id="cc224-179">När du ställer in ämnen, som en del av installationsprocessen, skapas ett ämnescenter automatiskt.</span><span class="sxs-lookup"><span data-stu-id="cc224-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="cc224-180">Fundera på vad du vill ge ämnescentret och vad du vill att URL-adressen ska vara.</span><span class="sxs-lookup"><span data-stu-id="cc224-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="cc224-181">Du kan ange både namn och URL som en del av installationsprocessen och du kan ändra namn (men inte URL) senare i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc224-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cc224-182">Du kan bara ha ett ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="cc224-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="cc224-183">Checklista för installation</span><span class="sxs-lookup"><span data-stu-id="cc224-183">Setup checklist</span></span>

<span data-ttu-id="cc224-184">När du skapar ämnesupplevelser behöver du följande när du går igenom installationsguiden:</span><span class="sxs-lookup"><span data-stu-id="cc224-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="cc224-185">Lista över webbplatser som ska inkluderas eller undantas om de inte inkluderar alla webbplatser för identifiering av ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="cc224-186">Säkerhetsgrupp för ämnesvisningsprogram om inte alla användare kan visa ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="cc224-187">Säkerhetsgrupp för ämnesdeltagare om inte alla användare kan skapa och redigera ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="cc224-188">Säkerhetsgrupp för ämneskunskapershanterare om de inte tillåter att alla användare hanterar ämnen</span><span class="sxs-lookup"><span data-stu-id="cc224-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="cc224-189">Lista över känsliga ämnen som inte ska upptäckas</span><span class="sxs-lookup"><span data-stu-id="cc224-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="cc224-190">Ett namn på ämnescenterwebbplatsen</span><span class="sxs-lookup"><span data-stu-id="cc224-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="cc224-191">Se även</span><span class="sxs-lookup"><span data-stu-id="cc224-191">See also</span></span>

[<span data-ttu-id="cc224-192">Konfigurera ämnesupplevelser</span><span class="sxs-lookup"><span data-stu-id="cc224-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="cc224-193">Hantera identifiering av ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc224-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="cc224-194">Hantera synlighet för ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc224-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="cc224-195">Hantera ämnesbehörigheter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc224-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="cc224-196">Ändra namnet på ämnescentret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc224-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
