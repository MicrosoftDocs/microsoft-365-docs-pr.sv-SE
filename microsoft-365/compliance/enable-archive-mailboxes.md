---
title: Aktivera arkivpostlådor i Säkerhets- och efterlevnadscentret
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom: seo-marvel-apr2020
description: Lär dig hur du använder efterlevnadscentret för att aktivera arkivpostlådor som stöd för organisationens meddelandekvarhållning, eDiscovery och bevarandekrav.
ms.openlocfilehash: 2bc80d347d1324a317cc2cc2712d475781adc492
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162229"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a><span data-ttu-id="1cd6b-103">Aktivera arkivpostlådor i efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="1cd6b-103">Enable archive mailboxes in the compliance center</span></span>

<span data-ttu-id="1cd6b-104">Med arkivering i Microsoft 365 (även kallat *Arkivering i Office 365*) får användarna ytterligare lagringsutrymme för e-post.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-104">Archiving in Microsoft 365 (also called *In-Place Archiving*) provides users with additional mailbox storage space.</span></span> <span data-ttu-id="1cd6b-105">När du har aktiverat arkivpostlådor kan användare komma åt och lagra meddelanden i sina arkivpostlådor med hjälp av Microsoft Outlook och Outlook på webben (tidigare kallat Outlook Web App).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-105">After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="1cd6b-106">Användare kan också flytta eller kopiera meddelanden mellan sin primära postlåda och sin arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-106">Users can also move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="1cd6b-107">De kan också återskapa borttagna objekt från mappen Återställningsbara objekt i arkivpostlådan med hjälp av verktyget Återskapa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-107">They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

> [!NOTE]
> <span data-ttu-id="1cd6b-108">Den automatiskt expanderande arkiveringsfunktionen i Microsoft 365 ger arkivpostlådorna ytterligare lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-108">The auto-expanding archiving feature in Microsoft 365 provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="1cd6b-109">När automatisk arkiveringsexpansion är aktiverad och den första lagringskvoten i en användares arkivpostlåda uppnås, lägger Microsoft 365 automatiskt till ytterligare lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-109">When auto-expanding  archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Microsoft 365 automatically adds additional storage space.</span></span> <span data-ttu-id="1cd6b-110">Det innebär att användarnas lagringsutrymme för e-post inte tar slut och att du inte behöver hantera något efter att du har aktiverat arkivpostlådan och automatisk arkiveringsexpansion för organisationen.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-110">This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization.</span></span> <span data-ttu-id="1cd6b-111">Mer information finns i [Översikt över obegränsad arkivering](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-111">For more information, see [Overview of unlimited archiving](unlimited-archiving.md).</span></span>

## <a name="get-the-necessary-permissions"></a><span data-ttu-id="1cd6b-112">Hämta nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="1cd6b-112">Get the necessary permissions</span></span>

<span data-ttu-id="1cd6b-113">Du måste ha tilldelats rollen E-postmottagare i Exchange Online för att aktivera eller inaktivera arkivpostlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-113">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes.</span></span> <span data-ttu-id="1cd6b-114">Som standard tilldelas de här rollerna till rollgrupperna för Mottagarhantering och Organisationshantering på sidan **Behörigheter** i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-114">By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1cd6b-115">Om du inte ser sidan **Arkivering** i Säkerhets- och efterlevnadscentret ber du administratören att tilldela dig de behörigheter som krävs.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-115">If you don't see the **Archive** page in the Security & Compliance Center, ask your administrator to assign you the necessary permissions.</span></span>

## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="1cd6b-116">Aktivera arkivpostlåda</span><span class="sxs-lookup"><span data-stu-id="1cd6b-116">Enable an archive mailbox</span></span>

1. <span data-ttu-id="1cd6b-117">Gå till <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-117">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="1cd6b-118">Logga in med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-118">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="1cd6b-119">Klicka på **Informationsstyrning** \>**Arkiv** i vänster fönsterruta i Säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-119">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>

   <span data-ttu-id="1cd6b-120">Sidan **Arkiv** visas.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-120">The **Archive** page is displayed.</span></span> <span data-ttu-id="1cd6b-121">Kolumnen för **Arkivpostlådan** anger om en arkivpostlåda är aktiverad eller inaktiverad för varje användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-121">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cd6b-122">Sidan **Arkiv** visar högst 500 användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-122">The **Archive** page shows a maximum of 500 users.</span></span>

4. <span data-ttu-id="1cd6b-123">Markera användaren som du vill aktivera arkivpostlådan för i listan över postlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-123">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>

   ![Klicka på Aktivera i informationsfönstret för den markerade användaren för att aktivera arkivpostlådan](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. <span data-ttu-id="1cd6b-125">I informationsfönstret för den valda användaren klickar du på **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-125">In the details pane for the selected user, click **Enable**.</span></span>

   <span data-ttu-id="1cd6b-126">En varning förklarar att när du aktiverar arkivpostlådan så flyttas objekt i användarens postlåda som är äldre än den tilldelade arkiveringsprincipen till den nya arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-126">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox.</span></span> <span data-ttu-id="1cd6b-127">Den standardarkiveringsprincip som är en del av kvarhållningsprincipen som tilldelas Exchange Online-postlådor flyttar objekt till arkivpostlådan två år efter det datum då objektet levererades till postlådan eller skapades av användaren.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-127">The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="1cd6b-128">Du hittar mer information i avsnittet **Mer information** i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-128">For more information, see the **More info** section in this article.</span></span>

6. <span data-ttu-id="1cd6b-129">Klicka **Ja** för att aktivera arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-129">Click **Yes** to enable the archive mailbox.</span></span>

   <span data-ttu-id="1cd6b-130">Det kan ta en stund att skapa arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-130">It might take a few moments to create the archive mailbox.</span></span> <span data-ttu-id="1cd6b-131">När den har skapats visas **Arkivpostlåda: aktiverad** i informationsfönstret för den valda användaren.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-131">When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="1cd6b-132">Du kanske måste klicka på **Uppdatera** ![ikonen Uppdatera](../media/O365-MDM-Policy-RefreshIcon.gif) för att uppdatera informationen i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-132">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span>

> [!TIP]
> <span data-ttu-id="1cd6b-133">Du kan även massaktivera arkivpostlådor genom att välja flera användare med inaktiverade arkivpostlådor (använd Skift- eller Ctrl-tangenterna). </span><span class="sxs-lookup"><span data-stu-id="1cd6b-133">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys).</span></span> <span data-ttu-id="1cd6b-134">När du har valt flera postlådor klickar du på **Aktivera** i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-134">After selecting multiple mailboxes, click **Enable** in the details pane.</span></span>

## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="1cd6b-135">Inaktivera en arkivpostlåda</span><span class="sxs-lookup"><span data-stu-id="1cd6b-135">Disable an archive mailbox</span></span>

<span data-ttu-id="1cd6b-136">Du kan även använda sidan **Arkivera** i Säkerhets- och efterlevnadscentret för att inaktivera en användares arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-136">You can also use the **Archive** page in the Security & Compliance Center to disable a user's archive mailbox.</span></span> <span data-ttu-id="1cd6b-137">När du inaktiverat en arkivpostlåda kan du återansluta den till användarens primära postlåda inom 30 dagar efter att du inaktiverat den.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-137">After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it.</span></span> <span data-ttu-id="1cd6b-138">I det här fallet återställs det ursprungliga innehållet i arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-138">In this case, the original contents of the archive mailbox are restored.</span></span> <span data-ttu-id="1cd6b-139">Efter 30 dagar tas innehållet i den ursprungliga arkivpostlådan bort permanent och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-139">After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered.</span></span> <span data-ttu-id="1cd6b-140">Om du återaktivera arkivet mer än 30 dagar efter att du inaktiverat det skapas en ny arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-140">So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span>

<span data-ttu-id="1cd6b-141">Standardarkiveringsprincipen som tilldelas användarnas postlådor flyttar objekt till arkivpostlådan två år efter objektets leveransdatum.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-141">The default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered.</span></span> <span data-ttu-id="1cd6b-142">Om du inaktiverar en användares arkivpostlåda vidtas inga åtgärder på postlådeobjekten och de finns kvar i användarens primära postlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-142">If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>

<span data-ttu-id="1cd6b-143">Så här inaktiverar du en arkivpostlåda:</span><span class="sxs-lookup"><span data-stu-id="1cd6b-143">To disable an archive mailbox:</span></span>

1. <span data-ttu-id="1cd6b-144">Gå till <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-144">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="1cd6b-145">Logga in med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-145">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="1cd6b-146">Klicka på **Informationsstyrning** \>**Arkiv** i vänster fönsterruta i Säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-146">In the left pane of the Security & Compliance Center, click **Information governance** \> **Archive**.</span></span>

   <span data-ttu-id="1cd6b-147">Sidan **Arkiv** visas.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-147">The **Archive** page is displayed.</span></span> <span data-ttu-id="1cd6b-148">Kolumnen för **Arkivpostlådan** anger om en arkivpostlåda är aktiverad eller inaktiverad för varje användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-148">The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cd6b-149">Sidan **Arkiv** visar högst 500 användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-149">The **Archive** page shows a maximum of 500 users.</span></span>

4. <span data-ttu-id="1cd6b-150">Markera användaren som du vill inaktivera arkivpostlådan för i listan över postlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-150">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>

5. <span data-ttu-id="1cd6b-151">Klicka på **Inaktivera** i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-151">In the details pane, click **Disable**.</span></span>

   <span data-ttu-id="1cd6b-152">Ett varningsmeddelande informerar dig om att du har 30 dagar på dig att aktivera arkivpostlådan på nytt, och att all information i arkivet tas bort permanent efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-152">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span>

6. <span data-ttu-id="1cd6b-153">Klicka **Ja** för att inaktivera arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-153">Click **Yes** to disable the archive mailbox.</span></span>

   <span data-ttu-id="1cd6b-154">Det kan ta en stund att inaktivera arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-154">It might take a few moments to disable the archive mailbox.</span></span> <span data-ttu-id="1cd6b-155">När den är inaktiverad visas **Arkivpostlåda: inaktiverad** i informationsfönstret för den valda användaren.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-155">When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user.</span></span> <span data-ttu-id="1cd6b-156">Du kanske måste klicka på **Uppdatera** ![ikonen Uppdatera](../media/O365-MDM-Policy-RefreshIcon.gif) för att uppdatera informationen i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-156">You might have to click **Refresh** ![Refresh icon](../media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span>

> [!TIP]
> <span data-ttu-id="1cd6b-157">Du kan även massinaktivera arkivpostlådor genom att välja flera användare med aktiverade arkivpostlådor (använd Skift- eller Ctrl-tangenterna). </span><span class="sxs-lookup"><span data-stu-id="1cd6b-157">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys).</span></span> <span data-ttu-id="1cd6b-158">När du har valt flera postlådor klickar du på **Inaktivera** i informationsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-158">After selecting multiple mailboxes, click **Disable** in the details pane.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="1cd6b-159">Använd Exchange Online PowerShell för att aktivera eller inaktivera arkivpostlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-159">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="1cd6b-160">Du kan även använda Exchange Online PowerShell för att aktivera eller inaktivera arkivpostlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-160">You can also use Exchange Online PowerShell to enable archive mailboxes.</span></span> <span data-ttu-id="1cd6b-161">Den primära orsaken till att använda PowerShell är att du snabbt kan aktivera arkivpostlådan för alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-161">The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="1cd6b-162">Det första steget är att ansluta till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-162">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="1cd6b-163">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-163">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="1cd6b-164">När du är ansluten till Exchange Online kan du köra kommandona i följande avsnitt för att aktivera eller inaktivera arkivpostlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-164">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="1cd6b-165">Aktivera arkivpostlådor</span><span class="sxs-lookup"><span data-stu-id="1cd6b-165">Enable archive mailboxes</span></span>

<span data-ttu-id="1cd6b-166">Kör följande kommando för att aktivera arkivpostlådan för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-166">Run the following command to enable the archive mailbox for a single user.</span></span>

```powershell
Enable-Mailbox -Identity <username> -Archive
```

<span data-ttu-id="1cd6b-167">Kör följande kommando för att aktivera arkivpostlådan för alla användare i organisationen (vars arkivpostlåda för närvarande inte är aktiverad).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-167">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a><span data-ttu-id="1cd6b-168">Inaktivera arkivpostlådor</span><span class="sxs-lookup"><span data-stu-id="1cd6b-168">Disable archive mailboxes</span></span>

<span data-ttu-id="1cd6b-169">Kör följande kommando för att inaktivera arkivpostlådan för en enskild användare.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-169">Run the following command to disable the archive mailbox for a single user.</span></span>

```powershell
Disable-Mailbox -Identity <username> -Archive
```

<span data-ttu-id="1cd6b-170">Kör följande kommando för att inaktivera arkivpostlådan för alla användare i organisationen (vars arkivpostlåda för närvarande är aktiverad).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-170">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a><span data-ttu-id="1cd6b-171">Mer information</span><span class="sxs-lookup"><span data-stu-id="1cd6b-171">More information</span></span>

- <span data-ttu-id="1cd6b-172">När en arkivpostlåda är aktiverad kan användarna lagra meddelanden i sin arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-172">When an archive mailbox is enabled, users can store messages in their archive mailbox.</span></span> <span data-ttu-id="1cd6b-173">Användarna kan komma åt sina arkivpostlådor genom att använda av Microsoft Outlook och Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-173">Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web.</span></span> <span data-ttu-id="1cd6b-174">Genom att använda ett av dessa klientprogram kan användarna visa meddelanden i sin arkivpostlåda och flytta eller kopiera meddelanden mellan sin primära postlåda och arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-174">Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox.</span></span> <span data-ttu-id="1cd6b-175">Användarna kan även återskapa borttagna objekt från mappen Återställningsbara objekt i arkivpostlådan med hjälp av verktyget Återskapa borttagna objekt.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-175">Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span>

  <span data-ttu-id="1cd6b-176">För att se en lista över Outlook-licenser som har stöd för lokal arkivering, gå till [Licenskrav i Outlook för Exchange-funktioner](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span><span class="sxs-lookup"><span data-stu-id="1cd6b-176">For a list of Outlook licenses that support In-Place Archiving, see [Outlook license requirements for Exchange features](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).</span></span>

- <span data-ttu-id="1cd6b-177">Med arkivpostlådor kan du och användarna uppfylla organisationens krav på kvarhållning, eDiscovery och bevarande.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-177">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements.</span></span> <span data-ttu-id="1cd6b-178">Du kan till exempel använda organisationens kvarhållningsprincip för Exchange för att flytta postlådeinnehåll till användarnas arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-178">For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox.</span></span> <span data-ttu-id="1cd6b-179">När du använder verktyget Innehållssökning i Säkerhets- och efterlevnadscentret för att söka i en användares postlåda efter specifikt innehåll genomsöks även användarens arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-179">When you use the Content Search tool in the Security & Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched.</span></span> <span data-ttu-id="1cd6b-180">Och när du placerar ett Bevarande av juridiska skäl eller tillämpar en kvarhållningsprincip på en användares postlåda sparas även objekten i arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-180">And, when you place a Litigation Hold or apply a retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>

- <span data-ttu-id="1cd6b-181">När arkivpostlådor har aktiverats kan organisationen dra nytta av standardprincipen för Exchange-kvarhållning (även kallad Messaging Records Management eller MRM-principen) som automatiskt tilldelas till alla postlådor.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-181">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox.</span></span> <span data-ttu-id="1cd6b-182">När en arkivpostlåda är aktiverad gör standardprincipen för Exchange-kvarhållning automatiskt följande:</span><span class="sxs-lookup"><span data-stu-id="1cd6b-182">When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span>

  - <span data-ttu-id="1cd6b-183">Flyttar objekt som är äldre än två år från en användares primära postlåda till deras arkivpostlåda.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-183">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span>

  - <span data-ttu-id="1cd6b-184">Flyttar objekt som är äldre än 14 dagar från mappen Återställningsbara objekt i användarens primära postlåda till mappen Återställningsbara objekt i arkivpostlådan.</span><span class="sxs-lookup"><span data-stu-id="1cd6b-184">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>

- <span data-ttu-id="1cd6b-185">Mer information om arkivpostlådor och kvarhållningsprinciper för Exchange finns i:</span><span class="sxs-lookup"><span data-stu-id="1cd6b-185">For more information about archive mailboxes and Exchange retention policies, see:</span></span>

  - [<span data-ttu-id="1cd6b-186">Kvarhållningstaggar och kvarhållningsprinciper i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1cd6b-186">Retention tags and retention policies in Exchange Online</span></span>](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [<span data-ttu-id="1cd6b-187">Standardprincip för kvarhållning i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1cd6b-187">Default Retention Policy in Exchange Online</span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [<span data-ttu-id="1cd6b-188">Konfigurera en princip för arkivering och borttagning för postlådor i din organisation</span><span class="sxs-lookup"><span data-stu-id="1cd6b-188">Set up an archive and deletion policy for mailboxes in your organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)