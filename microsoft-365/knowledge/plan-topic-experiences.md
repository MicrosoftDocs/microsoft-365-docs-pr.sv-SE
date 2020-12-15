---
title: Planera ämnen i Microsoft 365
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
description: Lär dig hur du planerar för avsnitts upplevelser i Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668338"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a><span data-ttu-id="ad7d2-103">Planera ämnen i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad7d2-103">Plan topic experiences in Microsoft 365</span></span>

<span data-ttu-id="ad7d2-104">Du har kontroll över hur ämnen finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="ad7d2-105">Dina planerings beslut för avsnitts upplevelser säkerställer att de högkvalitativ avsnitten visas för användarna och att de har rätt behörighet att använda och bidra med kunskapen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-105">Your planning decisions for topic experiences ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="ad7d2-106">I den här artikeln ska vi undersöka dessa planerings beslut:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="ad7d2-107">Vilka SharePoint-webbplatser du vill crawla för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-107">Which SharePoint sites you want to crawl for topics.</span></span>
- <span data-ttu-id="ad7d2-108">Vilka ämnen, om det finns något, som du vill undanta från avsnitts upplevelser</span><span class="sxs-lookup"><span data-stu-id="ad7d2-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="ad7d2-109">Vilka användare du vill göra ämnen synliga för.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-109">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="ad7d2-110">Vilka användare som du vill ge behörighet att hantera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-110">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="ad7d2-111">Vilka användare som du vill ge behörighet att skapa eller redigera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-111">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="ad7d2-112">Vilket namn du vill ge ditt ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-112">What name you want to give your topic center.</span></span>

<span data-ttu-id="ad7d2-113">Säkerhet och sekretess för dina data respekteras och ämnen som inte har rätt att få åtkomst till filer behålls inte.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="ad7d2-114">Vi rekommenderar också att du läser [avsnittet om säkerhet och sekretess](topic-experiences-security-privacy.md) i olika delar av planerings processen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-114">We recommend you also read [Topic experiences security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad7d2-115">Krav</span><span class="sxs-lookup"><span data-stu-id="ad7d2-115">Requirements</span></span>

<span data-ttu-id="ad7d2-116">Du måste vara global administratör eller SharePoint-administratör för att få åtkomst till administrations centret för Microsoft 365 och konfigurera ämnen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

<span data-ttu-id="ad7d2-117">Alla användare som ska använda ämnes upplevelser kräver en licens för **ämnes upplevelser** .</span><span class="sxs-lookup"><span data-stu-id="ad7d2-117">All users who are going to use topic experiences require a **Topic Experiences** license.</span></span> <span data-ttu-id="ad7d2-118">Att tilldela licenser beskrivs i [avsnittet Konfigurera ämnen](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="ad7d2-118">Assigning licenses is covered in [Set up topic experiences](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="ad7d2-119">Avsnitts identifiering</span><span class="sxs-lookup"><span data-stu-id="ad7d2-119">Topic discovery</span></span>

<span data-ttu-id="ad7d2-120">Identifieringen av ämnen anger vilka SharePoint-webbplatser som används som källor för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="ad7d2-121">Du kan välja att inkludera alla SharePoint-webbplatser, en specifik lista över webbplatser eller inga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="ad7d2-122">Vi rekommenderar att du väljer alla webbplatser så att ämnena kan upptäcka ett stort antal bra ämnen för dina användare.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="ad7d2-123">När du ställer in ämnen kan du välja bland följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-123">When you set up topic experiences, you can choose from the following options:</span></span>

- <span data-ttu-id="ad7d2-124">**Alla webbplatser**: alla SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="ad7d2-125">Detta inkluderar aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-125">This includes current and future sites.</span></span>
- <span data-ttu-id="ad7d2-126">**Alla, förutom utvalda webbplatser**: alla webbplatser förutom de som du anger.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="ad7d2-127">Webbplatser som skapats i framtiden tas med i källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="ad7d2-128">**Endast valda webbplatser**: bara de webbplatser som du anger.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="ad7d2-129">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="ad7d2-130">**Inga webbplatser**: det finns inga SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="ad7d2-131">Om du väljer antingen **alla, förutom markerade webbplatser** eller **bara valda webbplatser**, kan du ladda upp en CSV-fil med en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="ad7d2-132">Dessa alternativ är användbara om du utför en pilot och vill inkludera ett begränsat antal webbplatser att starta.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="ad7d2-133">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="ad7d2-134">Vi rekommenderar inte att du väljer **några webbplatser** eftersom den förhindrar att ämnen skapas eller uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="ad7d2-135">Men du kan välja det här alternativet om du vill konfigurera ämnen och sedan lägga till webbplatser senare.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-135">However, you can choose this option if you want to set up topic experiences and then add sites later.</span></span>

<span data-ttu-id="ad7d2-136">Vi rekommenderar att du skapar en process för användare eller kunskaps chefer för att begära att enskilda webbplatser tas bort från avsnitts identifiering om de behövs i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="ad7d2-137">Användar behörigheter</span><span class="sxs-lookup"><span data-stu-id="ad7d2-137">User permissions</span></span>

<span data-ttu-id="ad7d2-138">De användar behörigheter du anger avgör vilka personer i organisationen som interagerar med ämnen och vad de kan göra.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="ad7d2-139">*Hantera ämnen*</span><span class="sxs-lookup"><span data-stu-id="ad7d2-139">*Manage topics*</span></span>

<span data-ttu-id="ad7d2-140">Kunskaps cheferna övervakar informationen, hur de struktureras och andra metod tips i organisationen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="ad7d2-141">De kan bekräfta och avvisa ämnen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="ad7d2-142">Du kan ange enskilda ämnes hanterare, men vi rekommenderar att du skapar en säkerhets grupp (eller använder en befintlig) som innehåller de personer som du vill ska vara kunskaps chefer.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="ad7d2-143">Du kan ange denna säkerhets grupp under inställnings processen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="ad7d2-144">*Skapa och redigera ämnen*</span><span class="sxs-lookup"><span data-stu-id="ad7d2-144">*Create and edit topics*</span></span>

<span data-ttu-id="ad7d2-145">Ämnes deltagare är representanter och ämne experter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="ad7d2-146">De kan skapa och redigera ämnen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-146">They can create and edit topics.</span></span> 

<span data-ttu-id="ad7d2-147">Vi rekommenderar att du gör det möjligt för alla i organisationen att skapa och redigera ämnen eftersom ämnet fungerar bäst när alla användare kan dela information.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="ad7d2-148">Om du vill begränsa skapandet av och redigera ämnen för vissa personer eller grupper kan du skapa en säkerhets grupp för dem och ange den under konfigurations processen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="ad7d2-149">Du kan välja att inte tillåta att vem som helst bidrar till ämnen, men detta rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="ad7d2-150">Kunskaps cheferna kan fortfarande redigera och skapa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-150">Knowledge managers will still be able to edit and create topics.</span></span>

<span data-ttu-id="ad7d2-151">*Visnings program*</span><span class="sxs-lookup"><span data-stu-id="ad7d2-151">*Topic viewers*</span></span>

<span data-ttu-id="ad7d2-152">Avsnitts visnings program kan se information på ämnes sidor, i Sök Resultat och när ämnen markeras i innehållet som SharePoint-sidor.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="ad7d2-153">Användare kan bara se upptäckta ämnen när de har åtkomst till de filer och sidor som avsnittet upptäcktes i.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="ad7d2-154">När du konfigurerar visnings program kan du välja mellan:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="ad7d2-155">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="ad7d2-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="ad7d2-156">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="ad7d2-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="ad7d2-157">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="ad7d2-157">**No one**</span></span>

<span data-ttu-id="ad7d2-158">Vi rekommenderar **alla i organisationen**, men om du gör en pilot kanske du vill välja bara utvalda personer eller säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="ad7d2-159">Du kan också välja **Nej** om du vill konfigurera ämnen, men inte tillåta att andra kan se ämnen ännu.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-159">You can also choose **No one** if you want to set up topic experiences, but not allow people to see topics yet.</span></span> <span data-ttu-id="ad7d2-160">(Kunskaps ansvariga har fortfarande åtkomst att tillåta att de kan läsa ämnen och hjälp med beslutet att göra avsnitts upplevelser mer tillgängliga.)</span><span class="sxs-lookup"><span data-stu-id="ad7d2-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make topic experiences broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="ad7d2-161">Kunskaps regler</span><span class="sxs-lookup"><span data-stu-id="ad7d2-161">Knowledge rules</span></span>

<span data-ttu-id="ad7d2-162">Som administratör kan du exkludera vissa ämnen från ämnen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="ad7d2-163">Det här är praktiskt om du vill förhindra att känsliga data visas i avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="ad7d2-164">Även om kunskaps cheferna kan utesluta ämnen i ämnes centret är de avsnitt som inte är undantagna av administratören inte ens synliga för kunskaps cheferna.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="ad7d2-165">(Kunskaps chefer kan också ta bort ämnen i ämnes Center efter identifiering.)</span><span class="sxs-lookup"><span data-stu-id="ad7d2-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="ad7d2-166">Om du vill undanta ämnen på administratörs nivå måste du lägga till dem i en. csv-fil och ladda upp filen.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="ad7d2-167">Du kan göra det under installationen eller senare.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-167">You can do this during setup or later.</span></span>

<span data-ttu-id="ad7d2-168">CSV-filen måste innehålla följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="ad7d2-169">**Namn**: Skriv namnet på det ämne som du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="ad7d2-170">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-170">There are two ways to do this:</span></span>
- <span data-ttu-id="ad7d2-171">**MatchType-exakt/delvis**: Skriv om det namn du angav är en *exakt* eller *delvis* matchnings typ.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="ad7d2-172">Exakt träff: du kan ange exakt namn eller akronym (till exempel *contoso* eller *ATL*).</span><span class="sxs-lookup"><span data-stu-id="ad7d2-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="ad7d2-173">Ofullständig matchning: du kan exkludera alla ämnen som har ett visst ord i det.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="ad7d2-174">Till exempel kommer *bågen* att exkludera alla ämnen med ord *båge* i det, till exempel *båge cirkel*, *plasma båge svets* eller *tränings båge*. Observera att den inte utesluter ämnen där texten är inkluderad som en del av ett ord, till exempel *arkitekturen*.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="ad7d2-175">**Står för (valfritt)**: (kallas även för att *utöka*) om du vill undanta en akronym skriver du in de ord som akronym står för.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Uteslut avsnitt i en CSV-mall](../media/exclude-topics-csv.png) 

<span data-ttu-id="ad7d2-177">Du kan kopiera CSV-mallen nedan:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="ad7d2-178">Administration</span><span class="sxs-lookup"><span data-stu-id="ad7d2-178">Administration</span></span>

<span data-ttu-id="ad7d2-179">När du ställer in ämnen som en del av inställningen skapas ett avsnitts Center automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-179">When you set up topic experiences, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="ad7d2-180">Tänk på vad du vill namnge ämnes centret och vad du vill att URL-adressen ska vara.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="ad7d2-181">Du kan ange både namn och URL som en del av konfigurations processen och du kan ändra namnet (men inte URL) senare i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ad7d2-182">Du kan bara ha ett ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="ad7d2-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="ad7d2-183">Check lista för inställningar</span><span class="sxs-lookup"><span data-stu-id="ad7d2-183">Setup checklist</span></span>

<span data-ttu-id="ad7d2-184">När du konfigurerar ämnen måste du ha följande objekt i installations guiden:</span><span class="sxs-lookup"><span data-stu-id="ad7d2-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ad7d2-185">Lista över webbplatser att inkludera eller exkludera om de inte innehåller alla webbplatser för avsnitts identifiering</span><span class="sxs-lookup"><span data-stu-id="ad7d2-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="ad7d2-186">Säkerhets grupp för avsnitts läsare om du inte vill att alla användare ska kunna se ämnen</span><span class="sxs-lookup"><span data-stu-id="ad7d2-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="ad7d2-187">Säkerhets grupp för ämne deltagare om de inte tillåter alla användare att skapa och redigera ämnen</span><span class="sxs-lookup"><span data-stu-id="ad7d2-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="ad7d2-188">Säkerhets grupp för kunskaps chefer om du inte vill att alla användare ska kunna hantera ämnen</span><span class="sxs-lookup"><span data-stu-id="ad7d2-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="ad7d2-189">Lista över känsliga ämnen som ska undantas från identifiering av avsnitt</span><span class="sxs-lookup"><span data-stu-id="ad7d2-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="ad7d2-190">Ett namn på webbplatsen för ämnes Center</span><span class="sxs-lookup"><span data-stu-id="ad7d2-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="ad7d2-191">Se även</span><span class="sxs-lookup"><span data-stu-id="ad7d2-191">See also</span></span>

[<span data-ttu-id="ad7d2-192">Konfigurera ämnen</span><span class="sxs-lookup"><span data-stu-id="ad7d2-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="ad7d2-193">Hantera identifiering av avsnitt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad7d2-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="ad7d2-194">Hantera ämnets synlighet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad7d2-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="ad7d2-195">Hantera behörigheter för ämne i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad7d2-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="ad7d2-196">Ändra namnet på ämnes centret i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad7d2-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
