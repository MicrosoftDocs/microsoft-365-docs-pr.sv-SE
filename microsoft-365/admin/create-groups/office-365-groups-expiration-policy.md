---
title: Förfallo princip för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig mer om principer för förfallo datum för Microsoft 365 Groups.
ms.openlocfilehash: bda4bfbbef4e0d145c55b2a49b4d1203c6a7b1f0
ms.sourcegitcommit: 4f82fa7270e7ec6c6dd80329f28612e1f3289b22
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572145"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="2847d-103">Utgångs princip för Microsoft 365-gruppen</span><span class="sxs-lookup"><span data-stu-id="2847d-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="2847d-104">Med ökad användning av Microsoft 365-grupper behöver administratörer och användare ett sätt att rensa oanvända grupper.</span><span class="sxs-lookup"><span data-stu-id="2847d-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="2847d-105">Principer för förfallo datum kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.</span><span class="sxs-lookup"><span data-stu-id="2847d-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="2847d-106">När en grupp går ut tas alla tillhör ande tjänster (post lådan, Planner, SharePoint-webbplatsen, teamet etc.) också bort.</span><span class="sxs-lookup"><span data-stu-id="2847d-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="2847d-107">När en grupp upphör är "mjuk borttagen", vilket innebär att den fortfarande kan återställas i upp till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2847d-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="2847d-108">Administratörer kan ange en förfallo period och alla inaktiva grupper som når slutet av perioden och som inte förnyas, tas bort.</span><span class="sxs-lookup"><span data-stu-id="2847d-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="2847d-109">Utgångs perioden börjar när gruppen skapas, eller vid det datum då den senast förnyades.</span><span class="sxs-lookup"><span data-stu-id="2847d-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="2847d-110">Grupp ägare kommer automatiskt att skicka ett e-postmeddelande innan utgångs datumet gör det möjligt för dem att förnya gruppen för ett annat utgångs intervall.</span><span class="sxs-lookup"><span data-stu-id="2847d-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="2847d-111">Teams användarna kan se beständiga meddelanden i Teams.</span><span class="sxs-lookup"><span data-stu-id="2847d-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="2847d-112">Grupper som aktivt används förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2847d-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="2847d-113">En av följande åtgärder kommer automatiskt att förnya en grupp:</span><span class="sxs-lookup"><span data-stu-id="2847d-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="2847d-114">SharePoint – Visa, redigera, ladda ned, flytta, dela eller ladda upp filer.</span><span class="sxs-lookup"><span data-stu-id="2847d-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="2847d-115">Outlook – gå med i gruppen, läsa eller skriva grupp meddelande från gruppen och gilla ett meddelande (Outlook på webben).</span><span class="sxs-lookup"><span data-stu-id="2847d-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="2847d-116">Teams som besöker en Teams-kanal.</span><span class="sxs-lookup"><span data-stu-id="2847d-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2847d-117">När du ändrar förfallo dagen beräknas utgångs datumet för varje grupp.</span><span class="sxs-lookup"><span data-stu-id="2847d-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="2847d-118">Det börjar alltid räkna från det datum då gruppen skapades och sedan tillämpas den nya princip policyn.</span><span class="sxs-lookup"><span data-stu-id="2847d-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="2847d-119">Det är viktigt att veta att förfallo dagen är inaktive rad som standard.</span><span class="sxs-lookup"><span data-stu-id="2847d-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="2847d-120">Administratörer måste aktivera den för organisationen om de vill använda den.</span><span class="sxs-lookup"><span data-stu-id="2847d-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="2847d-121">Om du konfigurerar och använder policyn för utgångs datum för Microsoft 365-grupper måste du ha men inte nödvändigt vis tilldela Azure AD Premium-licenser för medlemmar i alla grupper som princip för förfallo tid tillämpas.</span><span class="sxs-lookup"><span data-stu-id="2847d-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="2847d-122">Mer information finns under [ Komma igång med Azure Active Directory Premium ](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span><span class="sxs-lookup"><span data-stu-id="2847d-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="2847d-123">Vem kan konfigurera och använda Microsofts 365-grupper giltighets princip?</span><span class="sxs-lookup"><span data-stu-id="2847d-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="2847d-124">Roll</span><span class="sxs-lookup"><span data-stu-id="2847d-124">Role</span></span>|<span data-ttu-id="2847d-125">Vad de kan göra</span><span class="sxs-lookup"><span data-stu-id="2847d-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="2847d-126">Global administratör (i Azure, företags administratören), användar administratör</span><span class="sxs-lookup"><span data-stu-id="2847d-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="2847d-127">Skapa, läsa, uppdatera och ta bort princip inställningar för förfallo principer för Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="2847d-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="2847d-128">Användare</span><span class="sxs-lookup"><span data-stu-id="2847d-128">User</span></span>|<span data-ttu-id="2847d-129">Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger</span><span class="sxs-lookup"><span data-stu-id="2847d-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="2847d-130">Ange förfallo princip</span><span class="sxs-lookup"><span data-stu-id="2847d-130">How to set the expiration policy</span></span>

<span data-ttu-id="2847d-131">Som vi noterade ovan är förfallo datumet inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="2847d-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="2847d-132">En administratör måste aktivera policyn för förfallo datum och ställa in egenskaperna för att den ska gälla.</span><span class="sxs-lookup"><span data-stu-id="2847d-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="2847d-133">Så här aktiverar du funktionen gå till gruppen **Azure Active Directory (AAD)**  >  **Groups**  >  **Expiration**.</span><span class="sxs-lookup"><span data-stu-id="2847d-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="2847d-134">Här kan du ange standard livstid för gruppen och ange hur långt i förväg du vill att aviseringarna för första och sista giltighets tiden ska gå till gruppens ägare.</span><span class="sxs-lookup"><span data-stu-id="2847d-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="2847d-135">Gruppens livs längd anges i dagar och kan anges till 180, 365 eller till ett anpassat värde som du anger.</span><span class="sxs-lookup"><span data-stu-id="2847d-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="2847d-136">Värdet måste vara minst 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2847d-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="2847d-137">Om gruppen inte har någon ägare skickas e-postmeddelandet till angiven administratör.</span><span class="sxs-lookup"><span data-stu-id="2847d-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="2847d-138">Du kan ställa in policyn för alla dina grupper, endast valda grupper eller stänga av den helt och hållet genom att välja **ingen**.</span><span class="sxs-lookup"><span data-stu-id="2847d-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="2847d-139">Observera att du inte kan använda olika principer för olika grupper.</span><span class="sxs-lookup"><span data-stu-id="2847d-139">Note that currently you can't have different policies for different groups.</span></span>

![Skärm bild av inställningar för förfallo tid för grupper i Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiration-and-renewal-work"></a><span data-ttu-id="2847d-141">Så här fungerar förfallo datum och förnyelse</span><span class="sxs-lookup"><span data-stu-id="2847d-141">How expiration and renewal work</span></span>

<span data-ttu-id="2847d-142">Princip för förfallo tid fungerar så här:</span><span class="sxs-lookup"><span data-stu-id="2847d-142">The expiration policy works as follows:</span></span> 

- <span data-ttu-id="2847d-143">Om en månad före utgångs datum kontrollerar systemet om det finns någon grupp aktivitet sedan gruppen skapades eller sedan början av den aktuella förnyelse cykeln.</span><span class="sxs-lookup"><span data-stu-id="2847d-143">About a month before expiration, the system will check to see if there has been any group activity since the group was created or since the beginning of the current renewal cycle.</span></span>

- <span data-ttu-id="2847d-144">Om en tidigare aktivitet identifieras är utgångs datumet Avancerat vid den tidpunkten med det antal dagar som anges i policyn för förfallo dag.</span><span class="sxs-lookup"><span data-stu-id="2847d-144">If prior activity is detected, then the expiration date is advanced at that time by the number of days specified in the expiration policy.</span></span>

- <span data-ttu-id="2847d-145">Om en föregående aktivitet inte hittas fortsätter systemet att titta efter aktivitet fram till utgångs datumet.</span><span class="sxs-lookup"><span data-stu-id="2847d-145">If prior activity is not detected, the system will continue to watch for activity until the expiration date.</span></span> <span data-ttu-id="2847d-146">Om aktiviteten hittas förfaller systemet fram utgångs datumet med angivet belopp vid den tidpunkten.</span><span class="sxs-lookup"><span data-stu-id="2847d-146">If activity is detected, the system will advance the expiration date by the specified amount at that time.</span></span>

<span data-ttu-id="2847d-147">30 dagar innan gruppen går ut får grupp ägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör det enkelt att förnya gruppen.</span><span class="sxs-lookup"><span data-stu-id="2847d-147">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="2847d-148">Om de inte förnyar det får de en ny förnyelse via e-post 15 dagar före utgångs datum.</span><span class="sxs-lookup"><span data-stu-id="2847d-148">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="2847d-149">Om de fortfarande inte har förnyat det får de ett mer e-postmeddelande dagen innan den upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="2847d-149">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span> <span data-ttu-id="2847d-150">(När gruppen har förnyats skickas inga fler e-postpåminnelser förrän 30 dagar före det nya utgångs datumet.)</span><span class="sxs-lookup"><span data-stu-id="2847d-150">(Once the group has been renewed, no further email reminders are sent until 30 days before the new expiration date.)</span></span>

<span data-ttu-id="2847d-151">Grupp ägare meddelas via e-post.</span><span class="sxs-lookup"><span data-stu-id="2847d-151">Group owners will be notified via email.</span></span> <span data-ttu-id="2847d-152">Om gruppen skapades via Planner, SharePoint eller något annat program kommer giltighets meddelandena alltid att skickas via e-post.</span><span class="sxs-lookup"><span data-stu-id="2847d-152">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="2847d-153">Om gruppen skapades via Teams får grupp ägaren ett meddelande om att förnya via avsnittet aktivitet.</span><span class="sxs-lookup"><span data-stu-id="2847d-153">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="2847d-154">Du rekommenderas inte att aktivera utgångs datum för en grupp om gruppens ägare inte har en giltig e-postadress.</span><span class="sxs-lookup"><span data-stu-id="2847d-154">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="2847d-155">Om du av någon anledning inte förnyar gruppen innan den upphör att gälla, och automatisk förnyelse inte sker på grund av att den grupp som inte uppfyller kraven automatiskt förnyas, kan administratören återställa gruppen i upp till 30 dagar efter förfallo dagen.</span><span class="sxs-lookup"><span data-stu-id="2847d-155">If for some reason none of the owners or admins renew the group before it expires, and automatic renewal does not occur due to the group not meeting the requirements to be automatically renewed, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="2847d-156">Mer information finns i: [återställa en borttagen Microsoft 365-grupp](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="2847d-156">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="how-expiry-works-with-retention-policies"></a><span data-ttu-id="2847d-157">Hur upphör ande fungerar med bevarande principer</span><span class="sxs-lookup"><span data-stu-id="2847d-157">How expiry works with retention policies</span></span>

<span data-ttu-id="2847d-158">Om du har en princip för konfigurations lagring i säkerhets-och kompatibilitetstillstånd för grupper fungerar utgångs principen sömlöst med bevarande princip.</span><span class="sxs-lookup"><span data-stu-id="2847d-158">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="2847d-159">När en grupp går ut bevaras gruppens konversationer i e-postlådan och filer i grupp webbplatsen bevaras i behållnings behållaren för det angivna antalet dagar som definierats i bevarande principen.</span><span class="sxs-lookup"><span data-stu-id="2847d-159">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="2847d-160">Användarna kan inte se gruppen eller dess innehåll efter att det har gått ut.</span><span class="sxs-lookup"><span data-stu-id="2847d-160">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2847d-161">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="2847d-161">Related articles</span></span>

[<span data-ttu-id="2847d-162">Översikt över bevarande principer</span><span class="sxs-lookup"><span data-stu-id="2847d-162">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="2847d-163">Tilldela en ny ägare till en överbliven grupp</span><span class="sxs-lookup"><span data-stu-id="2847d-163">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[<span data-ttu-id="2847d-164">Konfigurera att Microsoft 365-grupper upphör</span><span class="sxs-lookup"><span data-stu-id="2847d-164">Configure Microsoft 365 groups expiration</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[<span data-ttu-id="2847d-165">Aktivitet baserad automatisk förnyelse</span><span class="sxs-lookup"><span data-stu-id="2847d-165">Activity-based automatic renewal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
