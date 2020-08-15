---
title: Återskapa borttagna objekt i en användar post låda
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: eb15194b-63ec-41b0-8d90-1823d3f558e4
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller information som administratörer kan använda för att återställa borttagna objekt om de inte har tagits bort permanent från post lådan.
ms.openlocfilehash: a4755e592182d93c37a241958ba37c95d1565cdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694403"
---
# <a name="recover-deleted-items-in-a-user-mailbox"></a><span data-ttu-id="f4682-103">Återskapa borttagna objekt i en användar post låda</span><span class="sxs-lookup"><span data-stu-id="f4682-103">Recover deleted items in a user mailbox</span></span>

<span data-ttu-id="f4682-104">**Den här artikeln gäller för administratörer. Försöker du återställa borttagna objekt i din egen post låda?**</span><span class="sxs-lookup"><span data-stu-id="f4682-104">**This article is for administrators. Are you trying to recover deleted items in your own mailbox?**</span></span> <span data-ttu-id="f4682-105">Prova något av följande:</span><span class="sxs-lookup"><span data-stu-id="f4682-105">Try one of the following:</span></span>
- [<span data-ttu-id="f4682-106">Återskapa borttagna objekt i Outlook för Windows</span><span class="sxs-lookup"><span data-stu-id="f4682-106">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
- [<span data-ttu-id="f4682-107">Återskapa borttagna objekt eller e-post i Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="f4682-107">Recover deleted items or email in Outlook Web App</span></span>](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
- [<span data-ttu-id="f4682-108">Återställa borttagna e-postmeddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="f4682-108">Restore deleted email messages in Outlook on the web</span></span>](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
- [<span data-ttu-id="f4682-109">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4682-109">Outlook.com</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=623435)
   
<span data-ttu-id="f4682-110">Tog en användare permanent att ta bort objekt från post lådan i Outlook?</span><span class="sxs-lookup"><span data-stu-id="f4682-110">Did a user permanently delete items from their Outlook mailbox?</span></span> <span data-ttu-id="f4682-111">Användaren vill ha tillbaka dem men kan inte återställa dem.</span><span class="sxs-lookup"><span data-stu-id="f4682-111">The user wants them back but can't recover them.</span></span> <span data-ttu-id="f4682-112">Du kanske kan återställa borttagna objekt om de inte har tagits bort permanent från användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-112">You may be able recover the purged items if they haven't been permanently removed from the user's mailbox.</span></span> <span data-ttu-id="f4682-113">Det gör du genom att använda eDiscovery-verktyget i Exchange Online för att söka efter borttagna e-postmeddelanden och andra objekt – och till exempel kontakter, kalender möten och uppgifter – i en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-113">You do this by using the In-Place eDiscovery tool in Exchange Online to search for deleted email and other items—and such as contacts, calendar appointments, and tasks—in a user's mailbox.</span></span> <span data-ttu-id="f4682-114">Om du hittar borttagna objekt kan du exportera dem till en PST-fil (kallas även för en Outlook-datafil) som användaren sedan kan använda för att återställa objekten till post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-114">If you find the deleted items, you can export them to a PST file (also called an Outlook Data File), which the user can then use to restore the items back to their mailbox.</span></span>
  
<span data-ttu-id="f4682-115">Här är de här stegen för att återställa borttagna objekt i en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-115">Here are the steps for recovering deleted items in a user's mailbox.</span></span> <span data-ttu-id="f4682-116">Hur lång tid tar det?</span><span class="sxs-lookup"><span data-stu-id="f4682-116">How long will this take?</span></span> <span data-ttu-id="f4682-117">Första gången kan det ta 20 eller 30 minuter att slutföra alla stegen, beroende på hur många objekt du försöker återställa.</span><span class="sxs-lookup"><span data-stu-id="f4682-117">The first time might take 20 or 30 minutes to complete all the steps, depending on how many items you're trying to recover.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4682-118">Du måste vara Exchange- **administratör** eller **Global administratör** i Microsoft 365 eller vara medlem i roll gruppen organisations hantering i Exchange Online för att kunna utföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f4682-118">You have to be an **Exchange administrator** or **Global administrator** in Microsoft 365 or be a member of the Organization Management role group in Exchange Online to perform the steps in this article.</span></span> <span data-ttu-id="f4682-119">Mer information finns i [Om Microsoft 365-administratörsroller](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="f4682-119">For more information, see [About Microsoft 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span> 
  
## <a name="step-1-assign-yourself-ediscovery-permissions"></a><span data-ttu-id="f4682-120">Steg 1: tilldela dig själv eDiscovery-behörigheter</span><span class="sxs-lookup"><span data-stu-id="f4682-120">Step 1: Assign yourself eDiscovery permissions</span></span>
<span data-ttu-id="f4682-121"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-121"><a name="step1"> </a></span></span>

<span data-ttu-id="f4682-122">Det första steget är att tilldela dig själv nödvändiga behörigheter i Exchange Online, så att du kan använda det på plats eDiscovery för att söka i en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-122">The first step is to assign yourself the necessary permissions in Exchange Online so you can use the In-Place eDiscovery tool to search a user's mailbox.</span></span> <span data-ttu-id="f4682-123">Du behöver bara göra detta en gång.</span><span class="sxs-lookup"><span data-stu-id="f4682-123">You only have to do this once.</span></span> <span data-ttu-id="f4682-124">Om du behöver söka efter en annan post låda i framtiden kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="f4682-124">If you have to search another mailbox in the future, you can skip this step.</span></span>
  
1. <span data-ttu-id="f4682-125">[Här loggar du in i Microsoft 365 för företag](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="f4682-125">[Where to sign in to Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="f4682-126">Välj ikonen för Start programmet Start ![ ikonen i Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) i det övre vänstra hörnet och klicka på **administratör**.</span><span class="sxs-lookup"><span data-stu-id="f4682-126">Select the app launcher icon ![The app launcher icon in Microsoft 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) in the upper-left and click **Admin**.</span></span>
    
3. <span data-ttu-id="f4682-127">I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **administrations**Center och klickar sedan på **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f4682-127">In the left navigation in the Microsoft 365 admin center, expand **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Listan administrations Center](../media/7d308eb7-ba63-4156-a845-3770facc5de4.PNG)
  
4. <span data-ttu-id="f4682-129">I Exchange Admin Center klickar du på **behörigheter**och sedan på **Administratörs roller**.</span><span class="sxs-lookup"><span data-stu-id="f4682-129">In the Exchange admin center, click **Permissions**, and then click **Admin roles**.</span></span>
    
5. <span data-ttu-id="f4682-130">I listvyn väljer du **identifierings hantering**och klickar sedan på **Redigera** ![ redigerings ikon ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="f4682-130">In the list view, select **Discovery Management**, and then click **Edit**![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
    ![Lägga till dig själv i roll gruppen identifierings hantering i UK](../media/e5c98e93-d6a0-40c5-a143-bac956eedaa7.png)
  
6. <span data-ttu-id="f4682-132">Klicka på **Lägg**till ikon under **medlemmar**i **roll gruppen** ![ ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .</span><span class="sxs-lookup"><span data-stu-id="f4682-132">In **Role Group**, under **Members**, click **Add**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
7. <span data-ttu-id="f4682-133">I **Välj medlemmar**väljer du dig själv från listan med namn, klickar på **Lägg till**och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4682-133">In **Select Members**, select yourself from the list of names, click **Add**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4682-134">Du kan också lägga till en grupp som du är medlem i, till exempel organisations hantering eller TenantAdmins.</span><span class="sxs-lookup"><span data-stu-id="f4682-134">You can also add a group that you are a member of, such as Organization Management or TenantAdmins.</span></span> <span data-ttu-id="f4682-135">Om du lägger till en grupp tilldelas andra medlemmar i gruppen de behörigheter som krävs för att köra eDiscovery-verktyget på plats.</span><span class="sxs-lookup"><span data-stu-id="f4682-135">If you add a group, other members of the group will be assigned the necessary permissions to run the In-Place eDiscovery tool.</span></span> 
  
8. <span data-ttu-id="f4682-136">Klicka på **Spara**i **roll grupp**.</span><span class="sxs-lookup"><span data-stu-id="f4682-136">In **Role Group**, click **Save**.</span></span>
    
9. <span data-ttu-id="f4682-137">Logga ut från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4682-137">Sign out of Microsoft 365.</span></span>
    
    <span data-ttu-id="f4682-138">Du måste logga ut innan du börjar nästa steg så att den nya behörigheten börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="f4682-138">You have to sign out before you start the next step so the new permissions will take effect.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="f4682-139">Medlemmar i roll gruppen identifierings hantering kan komma åt känsligt meddelande innehåll.</span><span class="sxs-lookup"><span data-stu-id="f4682-139">Members of the Discovery Management role group can access sensitive message content.</span></span> <span data-ttu-id="f4682-140">Detta inkluderar sökning i alla post lådor i organisationen, för att förhandsgranska Sök resultaten (och andra objekt i post lådan), kopiera resultatet till en identifierings post låda och exportera Sök resultatet till en PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-140">This includes searching all mailboxes in your organization, previewing the search results (and other mailbox items), copying the results to a discovery mailbox, and exporting the search results to a PST file.</span></span> 
  
[<span data-ttu-id="f4682-141">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-141">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-2-search-the-users-mailbox-for-deleted-items"></a><span data-ttu-id="f4682-142">Steg 2: Sök efter borttagna objekt i användarens post låda</span><span class="sxs-lookup"><span data-stu-id="f4682-142">Step 2: Search the user's mailbox for deleted items</span></span>
<span data-ttu-id="f4682-143"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-143"><a name="step2"> </a></span></span>

<span data-ttu-id="f4682-144">När du kör en eDiscovery-sökning på plats tas mappen återställnings bara objekt i den post låda som du söker automatiskt med i sökningen.</span><span class="sxs-lookup"><span data-stu-id="f4682-144">When you run an In-Place eDiscovery search, the Recoverable Items folder in the mailbox that you search is automatically included in the search.</span></span> <span data-ttu-id="f4682-145">Mappen återställnings bara objekt är den plats där permanent borttagna objekt lagras tills de tas bort (permanent borttagna) från post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-145">The Recoverable Items folder is where permanently deleted items are stored until they're purged (permanently removed) from the mailbox.</span></span> <span data-ttu-id="f4682-146">Om ett objekt inte har rensats bör du kunna hitta det med hjälp av eDiscovery-verktyget på plats.</span><span class="sxs-lookup"><span data-stu-id="f4682-146">So, if an item hasn't been purged, you should be able to find it by using the In-Place eDiscovery tool.</span></span>
  
1. <span data-ttu-id="f4682-147">[Här loggar du in i Microsoft 365 för företag](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="f4682-147">[Where to sign in to Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="f4682-148">Välj ikonen för Start programmet Start ![ ikonen i Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) i det övre vänstra hörnet och klicka på **administratör**.</span><span class="sxs-lookup"><span data-stu-id="f4682-148">Select the app launcher icon ![The app launcher icon in Microsoft 365](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) in the upper-left and click **Admin**.</span></span>
    
3. <span data-ttu-id="f4682-149">I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **admin**och klickar sedan på **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f4682-149">In the left navigation in the Microsoft 365 admin center, expand **Admin**, and then click **Exchange**.</span></span>
    
4. <span data-ttu-id="f4682-150">Klicka på **hantering av efterlevnad**i administrations centret för Exchange, klicka på **i ett eDiscovery- &amp; undantag**och klicka sedan på **ny**ikon för att ![ lägga till ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .</span><span class="sxs-lookup"><span data-stu-id="f4682-150">In the Exchange admin center, click **Compliance management**, click **In-Place eDiscovery &amp; Hold**, and then click **New**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
    ![Klicka på lokal eDiscovery och håll ned på sidan Compliance Management i UK](../media/9d9ff0f5-b9be-45b8-8b5e-6037a856b0a8.png)
  
5. <span data-ttu-id="f4682-152">Skriv ett namn för sökningen (till exempel namnet på den användare som du återställer e-post för) på sidan **namn och beskrivning** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f4682-152">On the **Name and description** page, type a name for the search (such as the name of the user you're recovering email for), an optional description, and then click **Next**.</span></span>
    
6. <span data-ttu-id="f4682-153">Klicka på **Ange post lådor att söka efter**på sidan **post lådor** och klicka sedan på **Lägg till** ![ ikonen Lägg till ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) .</span><span class="sxs-lookup"><span data-stu-id="f4682-153">On the **Mailboxes** page, click **Specify mailboxes to search**, and then click **Add**![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).</span></span>
    
    ![Klicka på Ange post lådor för att söka efter en specifik-postlåda](../media/83879a40-5e5c-49a8-be3b-c0023d197588.png)
  
7. <span data-ttu-id="f4682-155">Leta reda på och välj namnet på den användare som du återställer det borttagna e-postmeddelandet för, klicka på **Lägg till**och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4682-155">Find and select the name of the user that you're recovering the deleted email for, click **Add**, and then click **OK**.</span></span>
    
8. <span data-ttu-id="f4682-156">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f4682-156">Click **Next**.</span></span>
    
    <span data-ttu-id="f4682-157">Sidan **Sök fråga** visas.</span><span class="sxs-lookup"><span data-stu-id="f4682-157">The **Search query** page is displayed.</span></span> <span data-ttu-id="f4682-158">Här definierar du Sök villkoren som hjälper dig att hitta de saknade objekten i användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-158">This is where you define the search criteria that will help you find the missing items in user's mailbox.</span></span> 
    
9. <span data-ttu-id="f4682-159">Fyll i följande fält på sidan **Sök fråga** :</span><span class="sxs-lookup"><span data-stu-id="f4682-159">On the **Search query** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="f4682-160">**Ta med allt innehåll** Välj det här alternativet om du vill inkludera allt innehåll i användarens post låda i Sök resultatet.</span><span class="sxs-lookup"><span data-stu-id="f4682-160">**Include all content** Select this option to include all content in the user's mailbox in the search results.</span></span> <span data-ttu-id="f4682-161">Om du väljer det här alternativet kan du inte ange fler Sök villkor.</span><span class="sxs-lookup"><span data-stu-id="f4682-161">If you select this option, you can't specify additional search criteria.</span></span> 
    
  - <span data-ttu-id="f4682-162">**Filter utifrån villkor** Välj det här alternativet om du vill ange Sök villkor, inklusive nyckelord, start-och slutdatum, avsändare och mottagar adresser samt meddelande typer.</span><span class="sxs-lookup"><span data-stu-id="f4682-162">**Filter based on criteria** Select this option to specify the search criteria, including keywords, start and end dates, sender and recipient addresses, and message types.</span></span> 
    
    ![Skapa en sökning utifrån villkor som nyckelord, datum intervall, mottagare och meddelande typer](../media/ee47b833-9122-46a0-85e6-fcbe25be0dd5.png)
  
|<span data-ttu-id="f4682-164">**Fält**</span><span class="sxs-lookup"><span data-stu-id="f4682-164">**Field**</span></span>|<span data-ttu-id="f4682-165">**Använd detta för att...**</span><span class="sxs-lookup"><span data-stu-id="f4682-165">**Use this to...**</span></span>|
|:-----|:-----|
|![Nummer ett i en rosa cirkel](../media/a4da261d-2516-48c5-b58a-9c452b9086b8.png)           <br/> |<span data-ttu-id="f4682-167">Ange nyckelord, datum intervall, mottagare och meddelande typer.</span><span class="sxs-lookup"><span data-stu-id="f4682-167">Specify keywords, date range, recipients, and message types.</span></span>  <br/> |
|![Nummer två i en rosa cirkel.](../media/de3c1ab4-4f01-4026-b1ba-3265bdb32a89.png)           <br/> |<span data-ttu-id="f4682-169">Sök efter meddelanden med nyckelord eller fraser och Använd logiska operatorer som **och** eller **eller**.</span><span class="sxs-lookup"><span data-stu-id="f4682-169">Search for messages with keywords or phrases, and use logical operators such as **AND** or **OR**.</span></span>  <br/> |
|![Nummer tre i en rosa cirkel.](../media/60fa378c-6ac1-4cbd-a782-2fa7ca619dc6.png)           <br/> |<span data-ttu-id="f4682-171">Sök efter meddelanden som skickats eller tagits emot inom ett datum intervall.</span><span class="sxs-lookup"><span data-stu-id="f4682-171">Search for messages sent or received within a date range.</span></span>  <br/> |
|![Nummer 4 i en rosa cirkel.](../media/1a0ff2ce-0942-405a-94e3-9bfeb1e5059e.png)           <br/> |<span data-ttu-id="f4682-173">Sök efter meddelanden som tas emot från eller skickas till vissa personer.</span><span class="sxs-lookup"><span data-stu-id="f4682-173">Search for messages received from or sent to specific people.</span></span>  <br/> |
|![Nummer fem i en rosa cirkel.](../media/878cc815-0165-49ba-a1ee-9236e5980403.png)           <br/> |<span data-ttu-id="f4682-175">Sök efter alla meddelande typer eller Välj specifika.</span><span class="sxs-lookup"><span data-stu-id="f4682-175">Search for all message types or select specific ones.</span></span>  <br/> |
   
   > [!TIP]
   >  <span data-ttu-id="f4682-176">Här är några tips om hur du skapar en Sök fråga för att hitta saknade objekt.</span><span class="sxs-lookup"><span data-stu-id="f4682-176">Here are a few tips about how to build a search query to find missing items.</span></span> <span data-ttu-id="f4682-177">Försök att få så mycket information från användaren som hjälper dig att skapa en Sök fråga så att du kan hitta det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f4682-177">Try to get as much information from the user to help you create a search query so you can find what you're looking for.</span></span> <span data-ttu-id="f4682-178">Om du inte är säker på hur du hittar ett meddelande som saknas kan du använda alternativet **Inkludera allt innehåll** .</span><span class="sxs-lookup"><span data-stu-id="f4682-178">If you are not sure how to find a missing message, consider using the **Include all content** option.</span></span> <span data-ttu-id="f4682-179">Sök resultatet inkluderar alla objekt i användarens mapp för återställnings bara objekt, inklusive den dolda mappen (kallas mappen rensar) som innehåller objekt som har tömts av användaren.</span><span class="sxs-lookup"><span data-stu-id="f4682-179">The search results will include all items in the user's Recoverable Items folder, including the hidden folder (called the Purges folder) that contain items that have been purged by the user.</span></span> <span data-ttu-id="f4682-180">Sedan kan du gå till steg 3, kopiera resultatet till en Discovery-postlåda och titta på meddelandet i den dolda mappen.</span><span class="sxs-lookup"><span data-stu-id="f4682-180">Then you can go to Step 3, copy the results to a discovery mailbox, and look at the message in the hidden folder.</span></span> <span data-ttu-id="f4682-181">Om du vet ungefär när det saknade meddelandet ursprungligen skickades eller togs emot av användaren använder du alternativen **Ange start datum** och **Ange slutdatum** för att ange ett datum intervall.</span><span class="sxs-lookup"><span data-stu-id="f4682-181">If you know approximately when the missing message was originally sent or received by the user, use the **Specify start date** and **Specify end date** options to provide a date range.</span></span> <span data-ttu-id="f4682-182">Då returneras alla meddelanden som skickas eller tas emot av användaren inom det datum intervallet.</span><span class="sxs-lookup"><span data-stu-id="f4682-182">This will return all messages sent or received by the user within that date range.</span></span> <span data-ttu-id="f4682-183">Att ange ett datum intervall är ett mycket bra sätt att begränsa Sök resultaten.</span><span class="sxs-lookup"><span data-stu-id="f4682-183">Specifying a date range is a really good way to narrow the search results.</span></span> <span data-ttu-id="f4682-184">Om du vet vem som har skickat den saknade e-postmeddelandet, Använd rutan **från** för att ange den avsändaren.</span><span class="sxs-lookup"><span data-stu-id="f4682-184">If you know who sent the missing email, use the **From** box to specify this sender.</span></span> <span data-ttu-id="f4682-185">Om du vill begränsa Sök resultaten till olika typer av post lådor klickar du på **Välj meddelande typer**, klickar på **Välj meddelande typer för att söka**och väljer sedan en specifik meddelande typ att söka efter.</span><span class="sxs-lookup"><span data-stu-id="f4682-185">If you want to narrow the search results to different types of mailbox items, click **Select message types**, click **Select the message types to search**, and then choose a specific message type to search for.</span></span> <span data-ttu-id="f4682-186">Du kan till exempel bara söka efter Kalender objekt eller kontakter.</span><span class="sxs-lookup"><span data-stu-id="f4682-186">For example, you can search only for calendar items or contacts.</span></span> <span data-ttu-id="f4682-187">Här är en skärm bild av de olika meddelande typer som du kan söka efter; Standardinställningen är att söka efter alla meddelande typer.</span><span class="sxs-lookup"><span data-stu-id="f4682-187">Here's a screenshot of the different message types you can search for; the default is to search for all message types.</span></span> 
  
   <span data-ttu-id="f4682-188">Klicka på **Nästa** när du är klar med sidan **Sök fråga** .</span><span class="sxs-lookup"><span data-stu-id="f4682-188">Click **Next** when you've completed the **Search query** page.</span></span> 
    
10. <span data-ttu-id="f4682-189">På sidan **in-Place Hold-inställningar** klickar du på **Slutför** för att starta sökningen.</span><span class="sxs-lookup"><span data-stu-id="f4682-189">On the **In-Place Hold settings** page, click **Finish** to start the search.</span></span> <span data-ttu-id="f4682-190">För att återställa borttagna e-postmeddelanden finns det ingen anledning att hålla användarens post låda stoppad.</span><span class="sxs-lookup"><span data-stu-id="f4682-190">To recover deleted email, there's no reason to place the user's mailbox on hold.</span></span> 
    
    <span data-ttu-id="f4682-191">När du har startat sökningen visar Exchange en uppskattning av den totala storleken och antalet objekt som returneras av sökningen baserat på de kriterier du angett.</span><span class="sxs-lookup"><span data-stu-id="f4682-191">After you start the search, Exchange will display an estimate of the total size and number of items that will be returned by the search based on the criteria you specified.</span></span>
    
11. <span data-ttu-id="f4682-192">Välj den sökning du just har skapat och klicka på **Uppdatera** ![ uppdatering ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) för att uppdatera informationen som visas i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="f4682-192">Select the search you just created and click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the information displayed in the details pane.</span></span> <span data-ttu-id="f4682-193">Statusen för **uppskattningen lyckades** indikerar att sökningen är klar.</span><span class="sxs-lookup"><span data-stu-id="f4682-193">The status of **Estimate Succeeded** indicates that the search has finished.</span></span> <span data-ttu-id="f4682-194">Dessutom visar Exchange en uppskattning av det totala antalet objekt (och storlek) som hittats i sökningen baserat på Sök villkoren du angav i steg 9.</span><span class="sxs-lookup"><span data-stu-id="f4682-194">Exchange also displays an estimate of the total number of items (and their size) found by the search based on the search criteria you specified in step 9.</span></span> 
    
12. <span data-ttu-id="f4682-195">Klicka på **Förhandsgranska Sök Resultat** i informations fönstret för att visa de objekt som hittades.</span><span class="sxs-lookup"><span data-stu-id="f4682-195">In the details pane, click **Preview search results** to view the items that were found.</span></span> <span data-ttu-id="f4682-196">Det här kan hjälpa dig att identifiera de objekt som du letar efter.</span><span class="sxs-lookup"><span data-stu-id="f4682-196">This might help you identify the item(s) that you're looking for.</span></span> <span data-ttu-id="f4682-197">Om du hittar de objekt du försöker återställa går du till steg 4 för att exportera Sök resultaten till en PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-197">If you find the item(s) you're trying to recover, go to step 4 to export the search results to a PST file.</span></span> 
    
    ![Klicka på Förhandsgranska Sök Resultat för att visa det objekt du försöker återställa](../media/a2cea921-dafa-45d6-97d4-ae45a226b8d3.png)
  
13. <span data-ttu-id="f4682-199">Om du inte hittar det du letar efter kan du ändra Sök villkoren genom att välja Sök, klicka på **Redigera** ![ Redigera ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) -ikonen och sedan klicka på **Sök fråga**.</span><span class="sxs-lookup"><span data-stu-id="f4682-199">If you don't find what you're looking for, you can revise your search criteria by selecting the search, clicking **Edit**![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif), and then clicking **Search query**.</span></span> <span data-ttu-id="f4682-200">Ändra Sök villkoren och kör sedan sökningen igen.</span><span class="sxs-lookup"><span data-stu-id="f4682-200">Change the search criteria and then rerun the search.</span></span>
    
[<span data-ttu-id="f4682-201">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-201">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="optional-step-3-copy-the-search-results-to-a-discovery-mailbox"></a><span data-ttu-id="f4682-202">Skriver Steg 3: kopiera Sök resultatet till en identifierings post låda</span><span class="sxs-lookup"><span data-stu-id="f4682-202">(Optional) Step 3: Copy the search results to a discovery mailbox</span></span>
<span data-ttu-id="f4682-203"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-203"><a name="step3"> </a></span></span>

<span data-ttu-id="f4682-204">Om du inte kan hitta ett objekt genom att förhandsgranska Sök resultaten eller om du vill se vilka objekt som finns i användarens mapp för återställnings bara objekt kan du kopiera Sök resultaten till en särskild post låda (kallas för en identifierings post låda) och sedan öppna den post lådan i Outlook på webben för att visa de faktiska objekten.</span><span class="sxs-lookup"><span data-stu-id="f4682-204">If you can't find an items by previewing the search results or if you want to see which items are in the user's Recoverable Items folder, then you can copy the search results to a special mailbox (called a discovery mailbox) and then open that mailbox in Outlook on the web to view the actual items.</span></span> <span data-ttu-id="f4682-205">Det bästa skälet till att kopiera Sök resultaten är att visa objekten i användarens mapp för återställnings bara objekt.</span><span class="sxs-lookup"><span data-stu-id="f4682-205">The best reason to copy the search results is so you can view the items in the user's Recoverable Items folder.</span></span> <span data-ttu-id="f4682-206">Mer än troligt vis finns objektet du försöker återställa finns i undermappen rensar.</span><span class="sxs-lookup"><span data-stu-id="f4682-206">More than likely, the item you're trying to recover is located in the Purges subfolder.</span></span> 
  
1. <span data-ttu-id="f4682-207">I Exchange Admin Center går du till **hantering** \> \*\*av efterlevnadsprincip på plats &amp; \*\*.</span><span class="sxs-lookup"><span data-stu-id="f4682-207">In the Exchange admin center, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f4682-208">I listan med sökningar väljer du den sökning som du skapade i steg 2.</span><span class="sxs-lookup"><span data-stu-id="f4682-208">In the list of searches, select the search that you created in Step 2.</span></span>
    
3. <span data-ttu-id="f4682-209">Klicka på **Sök** ![ ](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png) och sedan på **Kopiera Sök Resultat** i list rutan.</span><span class="sxs-lookup"><span data-stu-id="f4682-209">Click **Search**![search](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png), and then click **Copy search results** from the drop-down list.</span></span> 
    
    ![Klicka på Sök och sedan på Kopiera Sök Resultat](../media/7888df82-94b4-4e44-8a53-f66854dc7c86.png)
  
4. <span data-ttu-id="f4682-211">Klicka på **Bläddra**på sidan **Kopiera Sök Resultat** .</span><span class="sxs-lookup"><span data-stu-id="f4682-211">On the **Copy Search Results** page, click **Browse**.</span></span>
    
    ![Lämna kryss rutor omarkerade när borttagna objekt återställs](../media/37f27999-a5b2-4fed-87e2-bad6dc23cdae.png)
  
5. <span data-ttu-id="f4682-213">Klicka på **post låda för identifierings sökning**under **visnings namn**och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4682-213">Under **Display Name**, click **Discovery Search Mailbox**, and then click **OK**.</span></span>
    
    ![Kopiera Sök resultatet till post lådan för standard sökning](../media/36e8ef47-0035-4982-9ed6-426719c5f9ec.png)
  
    > [!NOTE]
    > <span data-ttu-id="f4682-215">Identifierings post lådan är en standard Sök brev låda som skapas automatiskt i din Microsoft 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="f4682-215">The Discovery Search Mailbox is a default discovery mailbox that is automatically created in your Microsoft 365 organization.</span></span> 
  
6. <span data-ttu-id="f4682-216">Klicka på **Kopiera** på sidan **Kopiera Sök Resultat** för att starta processen för att kopiera Sök resultatet till post lådan för identifierings sökning.</span><span class="sxs-lookup"><span data-stu-id="f4682-216">Back on the **Copy Search Results** page, click **Copy** to start the process to copy the search results to the Discovery Search Mailbox.</span></span> 
    
    ![Klicka på Kopiera för att kopiera Sök resultatet till post lådan för identifierings sökning](../media/71307a9d-f7a1-4e01-ae37-1d49040cc3fd.png)
  
7. <span data-ttu-id="f4682-218">Klicka på **Uppdatera** ![ uppdatering ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) för att uppdatera informationen om den kopierings status som visas i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="f4682-218">Click **Refresh**![refresh](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
8. <span data-ttu-id="f4682-219">När kopieringen är klar klickar du på **Öppna** för att öppna post lådan för identifierings sökning för att Visa Sök resultaten.</span><span class="sxs-lookup"><span data-stu-id="f4682-219">When the copying is complete, click **Open** to open the Discovery Search Mailbox to view the search results.</span></span> 
    
    ![Klicka på öppna för att gå till post lådan för identifierings sökning för att Visa Sök resultaten](../media/6cc81e0f-ceed-4464-9040-79b6f920de35.png)
  
    <span data-ttu-id="f4682-221">Sök resultatet som kopierats till post lådan för identifierings sökning placeras i en mapp som har samma namn som den eDiscovery-sökning som finns på plats.</span><span class="sxs-lookup"><span data-stu-id="f4682-221">The search results copied to the Discovery Search Mailbox are placed in a folder that has the same name as the In-Place eDiscovery search.</span></span> <span data-ttu-id="f4682-222">Du kan klicka på en mapp för att visa objekten i den mappen.</span><span class="sxs-lookup"><span data-stu-id="f4682-222">You can click a folder to display the items in that folder.</span></span>
    
    ![Sök resultat i post lådan för identifierings sökning; objekt i mappen rensningar kan endast återställas av en administratör](../media/2ef8e5fb-3e63-4f62-938e-307efe9f6998.gif)
  
    <span data-ttu-id="f4682-224">När du kör en sökning genomsöks också användarens mapp för återställnings bara objekt.</span><span class="sxs-lookup"><span data-stu-id="f4682-224">When you run a search, the user's Recoverable Items folder is also searched.</span></span> <span data-ttu-id="f4682-225">Det innebär att om objekt i mappen för att återställa objekt motsvarar Sök villkoren inkluderas de i Sök resultaten.</span><span class="sxs-lookup"><span data-stu-id="f4682-225">That means if items in the Recoverable Items folder meet the search criteria, they are included in the search results.</span></span> <span data-ttu-id="f4682-226">Objekt i mappen borttagningar är objekt som användaren permanent tar bort (genom att ta bort ett objekt från mappen Borttaget eller genom att klicka på **SKIFT + DELETE**.</span><span class="sxs-lookup"><span data-stu-id="f4682-226">Items in the Deletions folder are items that the user permanently deleted (by deleting an item from the Deleted Items folder or by selecting it and pressing **Shift+Delete**.</span></span> <span data-ttu-id="f4682-227">En användare kan använda verktyget Återställ borttagna objekt i Outlook eller Outlook på webben för att återskapa objekt i mappen Borttaget.</span><span class="sxs-lookup"><span data-stu-id="f4682-227">A user can use the Recover Deleted Items tool in Outlook or Outlook on the web to recover items in the Deletions folder.</span></span> <span data-ttu-id="f4682-228">Objekt i mappen rensar är objekt som användaren har rensat med verktyget Återställ borttagna objekt eller objekt som de rensades automatiskt av en princip som lagts till i post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-228">Items in the Purges folder are items that the user purged by using the Recover Deleted Items tool or items they were automatically purged by a policy applied to the mailbox.</span></span> <span data-ttu-id="f4682-229">I båda fallen kan bara administratörer återskapa objekt i mappen rensningar.</span><span class="sxs-lookup"><span data-stu-id="f4682-229">In either case, only an admin can recover items in the Purges folder.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f4682-230">Om en användare inte kan hitta ett borttaget objekt med hjälp av verktyget återställnings bara objekt, men objektet är fortfarande återställbart (vilket innebär att det inte har tagits bort permanent från post lådan) är det mer än troligt i mappen rensningar.</span><span class="sxs-lookup"><span data-stu-id="f4682-230">If a user can't find a deleted item using the Recoverable Items tool, but that item is still recoverable (meaning that it hasn't been permanently removed from the mailbox), it's more than likely located in the Purges folder.</span></span> <span data-ttu-id="f4682-231">Se till att du letar i mappen rensningar för det borttagna objekt som du försöker återställa för en användare.</span><span class="sxs-lookup"><span data-stu-id="f4682-231">So, be sure to look in the Purges folder for the deleted item you're trying to recover for a user.</span></span> 
  
[<span data-ttu-id="f4682-232">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-232">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-4-export-the-search-results-to-a-pst-file"></a><span data-ttu-id="f4682-233">Steg 4: exportera Sök resultatet till en PST-fil</span><span class="sxs-lookup"><span data-stu-id="f4682-233">Step 4: Export the search results to a PST file</span></span>
<span data-ttu-id="f4682-234"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-234"><a name="step4"> </a></span></span>

<span data-ttu-id="f4682-235">När du hittar objektet du försöker återställa för en användare är nästa steg att exportera resultaten från den sökning du körde i steg 2 till en PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-235">After you find the item you're trying to recover for a user, the next step is to export the results from the search you ran in Step 2 to a PST file.</span></span> <span data-ttu-id="f4682-236">Användaren kommer att använda den här PST-filen i nästa steg för att återställa det borttagna objektet till post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-236">The user will use this PST file in the next step to restore the deleted item to their mailbox.</span></span>
  
1. <span data-ttu-id="f4682-237">I Exchange Admin Center går du till **hantering** \> \*\*av efterlevnadsprincip på plats &amp; \*\*.</span><span class="sxs-lookup"><span data-stu-id="f4682-237">In the Exchange admin center, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="f4682-238">I listan med sökningar väljer du den sökning som du skapade i steg 2.</span><span class="sxs-lookup"><span data-stu-id="f4682-238">In the list of searches, select the search that you created in Step 2.</span></span>
    
3. <span data-ttu-id="f4682-239">Klicka på **Exportera till en PST-fil**.</span><span class="sxs-lookup"><span data-stu-id="f4682-239">Click **Export to a PST file**.</span></span>
    
    ![Klicka på Exportera till en PST-fil](../media/4e59ae17-4541-43f4-a6d1-1f8b9ba9404b.png)
  
4. <span data-ttu-id="f4682-241">Om du uppmanas att installera verktyget för eDiscovery-export klickar du på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="f4682-241">If you're prompted to install the eDiscovery Export Tool, click **Run**.</span></span>
    
5. <span data-ttu-id="f4682-242">I export verktyget för det här eDiscovery-programmet klickar du på **Bläddra** och anger den plats där du vill ladda ned PST-filen.</span><span class="sxs-lookup"><span data-stu-id="f4682-242">In the eDiscovery PST Export Tool, click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    ![Export verktyget för eDiscovery-PST](../media/17274d27-992e-4034-8133-8f793f554e6c.png)
  
    <span data-ttu-id="f4682-244">Du kan ignorera alternativen för att aktivera avduplicering och ta med sökbara objekt.</span><span class="sxs-lookup"><span data-stu-id="f4682-244">You can ignore the options to enable deduplication and include unsearchable items.</span></span>
    
6. <span data-ttu-id="f4682-245">Klicka på **Start** för att ladda ned PST-filen till datorn.</span><span class="sxs-lookup"><span data-stu-id="f4682-245">Click **Start** to download the PST file to your computer.</span></span> 
    
    <span data-ttu-id="f4682-246">I import **verktyget för eDiscovery-PST** visas statusinformation om exporten.</span><span class="sxs-lookup"><span data-stu-id="f4682-246">The **eDiscovery PST Export Tool** displays status information about the export process.</span></span> <span data-ttu-id="f4682-247">När exporten är klar kan du komma åt filen på den plats där den laddades ned.</span><span class="sxs-lookup"><span data-stu-id="f4682-247">When the export is complete, you can access the file in the location where it was downloaded.</span></span> 
    
[<span data-ttu-id="f4682-248">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-248">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-5-restore-the-recovered-items-to-the-users-mailbox"></a><span data-ttu-id="f4682-249">Steg 5: återställa återställda objekt till användarens post låda</span><span class="sxs-lookup"><span data-stu-id="f4682-249">Step 5: Restore the recovered items to the user's mailbox</span></span>
<span data-ttu-id="f4682-250"><a name="step5"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-250"><a name="step5"> </a></span></span>

<span data-ttu-id="f4682-251">Det sista steget är att använda PST-filen som exporterades i steg 4 för att återställa de återställda objekten till användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="f4682-251">The final step is to use the PST file that was exported in step 4 to restore the recovered items to the user's mailbox.</span></span> <span data-ttu-id="f4682-252">När du har skickat PST-filen till användaren utförs resten av det här steget av användaren för att öppna PST-filen och sedan flytta de återställda objekten till en annan mapp i post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-252">After you send the PST file to the user, the remainder of this step is performed by the user to open the PST file and then move the recovered items to another folder in their mailbox.</span></span> <span data-ttu-id="f4682-253">Stegvisa anvisningar kan du också skicka en länk till det här avsnittet: [öppna och Stäng Outlook-datafiler (. pst)](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2).</span><span class="sxs-lookup"><span data-stu-id="f4682-253">For step-by-step instructions, you can also send the user a link to this topic: [Open and close Outlook Data Files (.pst)](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2).</span></span> <span data-ttu-id="f4682-254">Eller så kan du skicka en länk till användaren [Återställ borttagna objekt till en post låda med hjälp av en PST-fil](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) nedan och be dem att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="f4682-254">Or you can send the user a link to the [Restore deleted items to a mailbox using a PST file](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) section below and ask them to perform these steps.</span></span> 
  
 <span data-ttu-id="f4682-255">**Skicka PST-filen till användaren**</span><span class="sxs-lookup"><span data-stu-id="f4682-255">**Send the PST file to the user**</span></span>
  
<span data-ttu-id="f4682-256">Det sista steget som du måste utföra när du skickar PST-filen som exporterades i steg 4 till användaren.</span><span class="sxs-lookup"><span data-stu-id="f4682-256">The final step that you need to perform is sending the PST file that was exported in step 4 to the user.</span></span> <span data-ttu-id="f4682-257">Det finns några olika sätt att göra detta:</span><span class="sxs-lookup"><span data-stu-id="f4682-257">There are a few ways to do this:</span></span>
  
- <span data-ttu-id="f4682-258">Bifoga PST-filen i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="f4682-258">Attach the PST file to an email message.</span></span> <span data-ttu-id="f4682-259">Om Outlook är konfigurerat för att blockera PST-filer måste du zippa filen och sedan bifoga den i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f4682-259">If Outlook is configured to block PST files, then you will have to zip the file and then attach it to the message.</span></span> <span data-ttu-id="f4682-260">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="f4682-260">Here's how:</span></span>
    
1. <span data-ttu-id="f4682-261">Bläddra till PST-filen i Utforskaren i Windows.</span><span class="sxs-lookup"><span data-stu-id="f4682-261">In Windows Explorer or File Explorer, browse to the PST file.</span></span>
    
2. <span data-ttu-id="f4682-262">Högerklicka på filen och välj sedan **Skicka till** \> **komprimerad mapp**.</span><span class="sxs-lookup"><span data-stu-id="f4682-262">Right-click the file, and then select **Send to** \> **Compressed (zipped) folder**.</span></span> <span data-ttu-id="f4682-263">Windows skapar en ny zip-fil och ger den ett identiskt namn som PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-263">Windows creates a new zip file and gives it an identical name as the PST file.</span></span>
    
3. <span data-ttu-id="f4682-264">Bifoga den komprimerade PST-filen i ett e-postmeddelande och skicka den till användaren, som sedan kan expandera filen genom att klicka på den.</span><span class="sxs-lookup"><span data-stu-id="f4682-264">Attach the compressed PST file to an email message and send it to the user, who can then decompress the file just by clicking it.</span></span>
    
- <span data-ttu-id="f4682-265">Kopiera PST-filen till en delad mapp som användaren kan komma åt och hämta.</span><span class="sxs-lookup"><span data-stu-id="f4682-265">Copy the PST file to a shared folder that the user can access and retrieve it.</span></span>
    
<span data-ttu-id="f4682-266">Stegen i nästa avsnitt utförs av användaren för att återställa borttagna objekt till post lådan.</span><span class="sxs-lookup"><span data-stu-id="f4682-266">The steps in the next section are performed by the user to restore the deleted items to their mailbox.</span></span>
  
 <a name="restoredeleteditems"></a>
<span data-ttu-id="f4682-267">**Återställa borttagna objekt till en post låda med hjälp av en PST-fil**</span><span class="sxs-lookup"><span data-stu-id="f4682-267">**Restore deleted items to a mailbox using a PST file**</span></span>
  
<span data-ttu-id="f4682-268">Du måste använda Outlook-programmet för att återställa ett borttaget objekt med hjälp av en PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-268">You have to use the Outlook desktop app to restore a deleted item by using a PST file.</span></span> <span data-ttu-id="f4682-269">Du kan inte använda Outlook Web App eller Outlook på webben för att öppna en PST-fil.</span><span class="sxs-lookup"><span data-stu-id="f4682-269">You can't use Outlook Web App or Outlook on the web to open a PST file.</span></span>
  
1. <span data-ttu-id="f4682-270">Klicka på fliken **Arkiv** i Outlook 2013 eller Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="f4682-270">In Outlook 2013 or Outlook 2016, click the **File** tab.</span></span> 
    
2. <span data-ttu-id="f4682-271">Klicka på **Öppna &amp; export**och sedan på **Öppna Outlook-datafil**.</span><span class="sxs-lookup"><span data-stu-id="f4682-271">Click **Open &amp; Export**, and then click **Open Outlook Data File**.</span></span>
    
3. <span data-ttu-id="f4682-272">Bläddra till den plats där du sparade PST-filen som administratören skickade.</span><span class="sxs-lookup"><span data-stu-id="f4682-272">Browse to the location where you saved the PST file that your administrator sent.</span></span>
    
4. <span data-ttu-id="f4682-273">Markera PST-filen och klicka på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="f4682-273">Select the PST and then click **Open**.</span></span>
    
    <span data-ttu-id="f4682-274">PST-filen visas i det vänstra navigerings fältet i Outlook.</span><span class="sxs-lookup"><span data-stu-id="f4682-274">The PST file appears in the left-nav bar in Outlook.</span></span>
    
    ![PST-filen visas i det vänstra navigerings fältet i Outlook](../media/c9389392-d08a-4aa7-848c-4986d448b0f2.png)
  
5. <span data-ttu-id="f4682-276">Klicka på pilarna för att expandera PST-filen och mapparna under den för att hitta det objekt du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="f4682-276">Click the arrows to expand the PST file and the folders under it to locate the item you want to recover.</span></span>
    
    ![Leta i mappen rensningar för det objekt som du vill återställa](../media/d4e372d9-ac23-4e95-8639-d8da690fefa7.png)
  
    > [!TIP]
    > <span data-ttu-id="f4682-278">Leta i mappen rensningar för det objekt du vill återställa.</span><span class="sxs-lookup"><span data-stu-id="f4682-278">Look in the Purges folder for the item you want to recover.</span></span> <span data-ttu-id="f4682-279">Det här är en dold mapp där borttagna objekt flyttas till.</span><span class="sxs-lookup"><span data-stu-id="f4682-279">This is a hidden folder that purged items are moved to.</span></span> <span data-ttu-id="f4682-280">Det objekt som administratören har återskapat finns i den här mappen.</span><span class="sxs-lookup"><span data-stu-id="f4682-280">It's likely the item that your administrator recovered is in this folder.</span></span> 
  
6. <span data-ttu-id="f4682-281">Högerklicka på objektet som du vill återställa och klicka sedan på **Flytta** \> **andra mappen**.</span><span class="sxs-lookup"><span data-stu-id="f4682-281">Right-click the item you want to recover and then click **Move** \> **Other Folder**.</span></span>
    
    ![Klicka på flytta och välj sedan annan mapp](../media/090063df-2aa0-444a-8e47-abd6fe6cf7a8.png)
  
7. <span data-ttu-id="f4682-283">Om du vill flytta objektet till Inkorgen klickar du på **Inkorgen**och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4682-283">To move the item to your inbox, click **Inbox**, and then click **OK**.</span></span>
    
    <span data-ttu-id="f4682-284">**Tips:** Gör något av följande om du vill återställa andra typer av objekt:</span><span class="sxs-lookup"><span data-stu-id="f4682-284">**Tip:** To recover other types of items, do one of the following:</span></span> 
    
  - <span data-ttu-id="f4682-285">Om du vill återställa ett Kalender objekt högerklickar du på det och klickar sedan på **Flytta** \> **annan** \> **kalendermapp**.</span><span class="sxs-lookup"><span data-stu-id="f4682-285">To recover a calendar item, right-click it, and then click **Move** \> **Other Folder** \> **Calendar**.</span></span>
    
  - <span data-ttu-id="f4682-286">Om du vill återställa en kontakt högerklickar du på den och klickar sedan på **Flytta** \> **andra** \> **kontakter**.</span><span class="sxs-lookup"><span data-stu-id="f4682-286">To recover a contact, right-click it, and then click **Move** \> **Other Folder** \> **Contacts**.</span></span>
    
  - <span data-ttu-id="f4682-287">Om du vill återställa en uppgift högerklickar du på den och klickar sedan på **Flytta** \> **andra mappaktiviteter** \> **Tasks**.</span><span class="sxs-lookup"><span data-stu-id="f4682-287">To recover a task, right-click it, and then click **Move** \> **Other Folder** \> **Tasks**.</span></span>
    
![Välj en mapp för att flytta andra typer av objekt](../media/f8290131-43f2-46f1-bc07-228c2d83b96c.png)
  
   > [!NOTE]
   > <span data-ttu-id="f4682-289">Kalender objekt, kontakter och uppgifter placeras direkt i mappen rensa och inte i en mapp för kalender, kontakter eller uppgifter.</span><span class="sxs-lookup"><span data-stu-id="f4682-289">Calendar items, contacts, and tasks are located directly in the Purges folder, and not in a Calendar, Contacts, or Tasks subfolder.</span></span> <span data-ttu-id="f4682-290">Du kan sortera efter **typ** för att gruppera liknande typer av objekt.</span><span class="sxs-lookup"><span data-stu-id="f4682-290">However, you can sort by **Type** to group similar types of items.</span></span> 
    
8. <span data-ttu-id="f4682-291">När du är klar med att återställa borttagna objekt högerklickar du på PST-filen i det vänstra navigerings fältet och väljer **Stäng "namn på PST-fil"**.</span><span class="sxs-lookup"><span data-stu-id="f4682-291">When you're finished recovering deleted items, right-click the PST file in the left-nav bar and select **Close "name of PST file"**.</span></span>
    
[<span data-ttu-id="f4682-292">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-292">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  
## <a name="more-information"></a><span data-ttu-id="f4682-293">Mer information</span><span class="sxs-lookup"><span data-stu-id="f4682-293">More information</span></span>
<span data-ttu-id="f4682-294"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="f4682-294"><a name="moreinfo"> </a></span></span>

- <span data-ttu-id="f4682-295">Det kan vara möjligt för en användare att återställa ett permanent borttaget objekt om objektets lagrings period för borttagna artiklar inte har gått ut.</span><span class="sxs-lookup"><span data-stu-id="f4682-295">It might be possible for a user to recover a permanently deleted item if the deleted item retention period for the item hasn't expired.</span></span> <span data-ttu-id="f4682-296">Som administratör kan du ha angett hur länge objekt i mappen för återställnings bara objekt är tillgängliga för återställning.</span><span class="sxs-lookup"><span data-stu-id="f4682-296">As an admin you may have specified how long items in the Recoverable Items folder are available for recovery.</span></span> <span data-ttu-id="f4682-297">Det kan till exempel finnas en policy som tar bort allt som finns i en användares borttagna objekt-mappen i 30 dagar, och en annan princip som gör att användare kan återskapa objekt i mappen för återställnings bara objekt i upp till en annan 14 dagar.</span><span class="sxs-lookup"><span data-stu-id="f4682-297">For example, there might be a policy that deletes anything that's been in a user's Deleted Items folder for 30 days, and another policy that lets users recover items in the Recoverable Items folder for up to another 14 days.</span></span> <span data-ttu-id="f4682-298">Men efter den här 14 dagarna kan du fortfarande kunna återskapa ett objekt i en användares post låda genom att följa procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="f4682-298">However, after this 14 days, you may still be able to recover an item in a user's mailbox by using the procedures in this topic.</span></span>
    
- <span data-ttu-id="f4682-299">Användare kan återställa ett borttaget objekt om det inte har tagits bort och om den lagrings tid för borttaget objekt inte har gått ut.</span><span class="sxs-lookup"><span data-stu-id="f4682-299">Users can recover a deleted item if it hasn't been purged and if the deleted item retention period for that item hasn't expired.</span></span> <span data-ttu-id="f4682-300">Om du vill hjälpa användare att återställa borttagna objekt i post lådan pekar du på något av följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f4682-300">To help users recover deleted items in their mailbox, point them to one of the following topics:</span></span>
    
  - [<span data-ttu-id="f4682-301">Återskapa borttagna objekt i Outlook för Windows</span><span class="sxs-lookup"><span data-stu-id="f4682-301">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
    
  - [<span data-ttu-id="f4682-302">Återskapa borttagna objekt i Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="f4682-302">Recover deleted items in Outlook 2010</span></span>](https://support.office.com/article/cd9dfe12-8e8c-4a21-bbbf-4bd103a3f1fe)
    
  - [<span data-ttu-id="f4682-303">Återskapa borttagna objekt eller e-post i Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="f4682-303">Recover deleted items or email in Outlook Web App</span></span>](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
    
  - [<span data-ttu-id="f4682-304">Återställa borttagna e-postmeddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="f4682-304">Restore deleted email messages in Outlook on the web</span></span>](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
    
  - [<span data-ttu-id="f4682-305">Återställa en borttagen kontakt i Outlook</span><span class="sxs-lookup"><span data-stu-id="f4682-305">Recover a deleted contact in Outlook</span></span>](https://support.office.com/article/51c83288-6888-4dcd-8c99-4932daabf643)
    
  - [<span data-ttu-id="f4682-306">Återställa borttagna e-postmeddelanden i Outlook.com</span><span class="sxs-lookup"><span data-stu-id="f4682-306">Restore deleted email messages in Outlook.com</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=623435)
    
[<span data-ttu-id="f4682-307">Return to top</span><span class="sxs-lookup"><span data-stu-id="f4682-307">Return to top</span></span>](recover-deleted-items-in-a-mailbox.md)
  

