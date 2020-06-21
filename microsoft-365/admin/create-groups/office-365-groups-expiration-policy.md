---
title: Principer för förfallodatum för grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Läs mer om principer för förfallodatum för Microsoft 365-grupper.
ms.openlocfilehash: 8def757241dec28f5a54c76dc81614fd52fe85e5
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780427"
---
# <a name="microsoft-365-group-expiration-policy"></a><span data-ttu-id="43b74-103">Principer för förfallodatum för Microsoft 365-grupp</span><span class="sxs-lookup"><span data-stu-id="43b74-103">Microsoft 365 group expiration policy</span></span>

<span data-ttu-id="43b74-104">Med den ökade användningen av Microsoft 365-grupper behöver administratörer och användare ett sätt att rensa oanvända grupper.</span><span class="sxs-lookup"><span data-stu-id="43b74-104">With the increase in usage of Microsoft 365 groups, administrators and users need a way to clean up unused groups.</span></span> <span data-ttu-id="43b74-105">Principer för förfallodatum kan hjälpa till att ta bort inaktiva grupper från systemet och göra saker renare.</span><span class="sxs-lookup"><span data-stu-id="43b74-105">Expiration policies can help remove inactive groups from the system and make things cleaner.</span></span>

<span data-ttu-id="43b74-106">När en grupp upphör att gälla tas även alla tillhörande tjänster (postlådan, Planner, SharePoint-webbplatsen, teamet osv.) bort.</span><span class="sxs-lookup"><span data-stu-id="43b74-106">When a group expires, all of its associated services (the mailbox, Planner, SharePoint site, team, etc.) are also deleted.</span></span>

<span data-ttu-id="43b74-107">När en grupp upphör att gälla är den "mjuk borttagen" vilket innebär att den fortfarande kan återställas i upp till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="43b74-107">When a group expires it is "soft-deleted" which means it can still be recovered for up to 30 days.</span></span>

<span data-ttu-id="43b74-108">Administratörer kan ange en förfalloperiod och alla inaktiva grupper som når slutet av den perioden och som inte förnyas tas bort.</span><span class="sxs-lookup"><span data-stu-id="43b74-108">Administrators can specify an expiration period and any inactive group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="43b74-109">Förfallotiden börjar när gruppen skapas eller på det datum då den senast förnyades.</span><span class="sxs-lookup"><span data-stu-id="43b74-109">The expiration period begins when the group is created, or on the date it was last renewed.</span></span> <span data-ttu-id="43b74-110">Gruppägare skickas automatiskt ett e-postmeddelande före förfallodatumet som gör att de kan förnya gruppen för ett annat utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="43b74-110">Group owners will automatically be sent an email before the expiration that allows them to renew the group for another expiration interval.</span></span> <span data-ttu-id="43b74-111">Teams-användare ser beständiga aviseringar i Teams.</span><span class="sxs-lookup"><span data-stu-id="43b74-111">Teams users will see persistent notifications in Teams.</span></span>

<span data-ttu-id="43b74-112">Grupper som används aktivt förnyas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="43b74-112">Groups that are actively in use are renewed automatically.</span></span> <span data-ttu-id="43b74-113">Någon av följande åtgärder förnyar automatiskt en grupp:</span><span class="sxs-lookup"><span data-stu-id="43b74-113">Any of the following actions will auto-renew a group:</span></span>
- <span data-ttu-id="43b74-114">SharePoint - visa, redigera, ladda ned, flytta, dela eller ladda upp filer.</span><span class="sxs-lookup"><span data-stu-id="43b74-114">SharePoint - view, edit, download, move, share, or upload files.</span></span>
- <span data-ttu-id="43b74-115">Outlook – gå med i grupp-, läs- eller skrivgruppsmeddelande från gruppen och som ett meddelande (Outlook på webben).</span><span class="sxs-lookup"><span data-stu-id="43b74-115">Outlook - join group, read or write group message from the group, and like a message (Outlook on the web).</span></span>
- <span data-ttu-id="43b74-116">Lag - besöker en lagkanal.</span><span class="sxs-lookup"><span data-stu-id="43b74-116">Teams - visiting a teams channel.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43b74-117">När du ändrar förfalloprincipen beräknas tjänsten om förfallodatumet för varje grupp.</span><span class="sxs-lookup"><span data-stu-id="43b74-117">When you change the expiration policy, the service recalculates the expiration date for each group.</span></span> <span data-ttu-id="43b74-118">Den börjar alltid räkna från det datum då gruppen skapades och tillämpar sedan den nya förfalloprincipen.</span><span class="sxs-lookup"><span data-stu-id="43b74-118">It always starts counting from the date when the group was created, and then applies the new expiration policy.</span></span>

<span data-ttu-id="43b74-119">Det är viktigt att veta att förfallodatum är inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="43b74-119">It's important to know that expiration is turned off by default.</span></span> <span data-ttu-id="43b74-120">Administratörer måste aktivera den för sin organisation om de vill använda den.</span><span class="sxs-lookup"><span data-stu-id="43b74-120">Administrators will have to enable it for their organization if they want to use it.</span></span>

> [!NOTE]
> <span data-ttu-id="43b74-121">Konfigurera och använda principen för förfallodatum för Microsoft 365-grupper kräver att du har men inte nödvändigtvis tilldela Azure AD Premium-licenser för medlemmarna i alla grupper som principen för förfallodatum tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="43b74-121">Configuring and using the expiration policy for Microsoft 365 groups requires you to possess but not necessarily assign Azure AD Premium licenses for the members of all groups to which the expiration policy is applied.</span></span> <span data-ttu-id="43b74-122">Mer information finns under [ Komma igång med Azure Active Directory Premium ](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span><span class="sxs-lookup"><span data-stu-id="43b74-122">For more information see [Getting started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span></span>

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a><span data-ttu-id="43b74-123">Vem kan konfigurera och använda förfalloprincipen för Microsoft 365-grupper?</span><span class="sxs-lookup"><span data-stu-id="43b74-123">Who can configure and use the Microsoft 365 groups expiration policy?</span></span>

|<span data-ttu-id="43b74-124">Roll</span><span class="sxs-lookup"><span data-stu-id="43b74-124">Role</span></span>|<span data-ttu-id="43b74-125">Vad de kan göra</span><span class="sxs-lookup"><span data-stu-id="43b74-125">What they can do</span></span>|
|---------|---------|
|<span data-ttu-id="43b74-126">Global administratör (i Azure, företagsadministratören), användaradministratör</span><span class="sxs-lookup"><span data-stu-id="43b74-126">Global admin (in Azure, the Company administrator), User administrator</span></span>|<span data-ttu-id="43b74-127">Skapa, läsa, uppdatera eller ta bort principinställningarna för förfallodatum för Microsoft 365-grupper.</span><span class="sxs-lookup"><span data-stu-id="43b74-127">Create, read, update, or delete the Microsoft 365 groups expiration policy settings.</span></span>|
|<span data-ttu-id="43b74-128">Användare</span><span class="sxs-lookup"><span data-stu-id="43b74-128">User</span></span>|<span data-ttu-id="43b74-129">Förnya eller [återställa](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) en Microsoft 365-grupp som de äger</span><span class="sxs-lookup"><span data-stu-id="43b74-129">Renew or [restore](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) a Microsoft 365 group that they own</span></span>|

## <a name="how-to-set-the-expiration-policy"></a><span data-ttu-id="43b74-130">Så här ställer du in principen om förfallodatum</span><span class="sxs-lookup"><span data-stu-id="43b74-130">How to set the expiration policy</span></span>

<span data-ttu-id="43b74-131">Som nämnts ovan är förfallodatumet inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="43b74-131">As noted above, expiry is turned off by default.</span></span> <span data-ttu-id="43b74-132">En administratör måste aktivera förfalloprincipen och ange att egenskaperna för den ska börja gälla.</span><span class="sxs-lookup"><span data-stu-id="43b74-132">An administrator will have to enable the expiration policy and set the properties for it to take effect.</span></span> <span data-ttu-id="43b74-133">Om du vill aktivera den går du till **Azure Active Directory (AAD)**  >  **Grupper**  >  **förfallodatum**.</span><span class="sxs-lookup"><span data-stu-id="43b74-133">To enable it go to **Azure Active Directory (AAD)** > **Groups** > **Expiration**.</span></span> <span data-ttu-id="43b74-134">Här kan du ange standardgruppens livstid och ange hur långt i förväg du vill att den första och andra förfallodatum meddelanden att gå till gruppens ägare.</span><span class="sxs-lookup"><span data-stu-id="43b74-134">Here you can set the default group lifetime and specify how far in advance you want the first and second expiration notifications to go to the group owner.</span></span>

<span data-ttu-id="43b74-135">Gruppens livstid anges i dagar och kan ställas in på 180, 365 eller till ett anpassat värde som du anger.</span><span class="sxs-lookup"><span data-stu-id="43b74-135">The group lifetime is specified in days and can be set to 180, 365 or to a custom value that you specify.</span></span> <span data-ttu-id="43b74-136">Det anpassade värdet måste vara minst 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="43b74-136">The custom value has to be at least 30 days.</span></span>

<span data-ttu-id="43b74-137">Om gruppen inte har någon ägare går e-postmeddelandena för utgångsdatum till en angiven administratör.</span><span class="sxs-lookup"><span data-stu-id="43b74-137">If the group does not have an owner, the expiration emails will go to a specified administrator.</span></span>

<span data-ttu-id="43b74-138">Du kan ange principen för alla dina grupper, bara valda grupper eller stänga av den helt genom att välja **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="43b74-138">You can set the policy for all of your groups, only selected groups, or turn it off completely by selecting **None**.</span></span> <span data-ttu-id="43b74-139">Observera att du för närvarande inte kan ha olika principer för olika grupper.</span><span class="sxs-lookup"><span data-stu-id="43b74-139">Note that currently you can't have different policies for different groups.</span></span>

![Skärmbild av inställningar för gruppförfallodatum i Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a><span data-ttu-id="43b74-141">Så här fungerar förfallodatum med bevarandeprincipen</span><span class="sxs-lookup"><span data-stu-id="43b74-141">How expiry works with the retention policy</span></span>

<span data-ttu-id="43b74-142">Om du har inställningsbevarandeprincip i Säkerhets- och efterlevnadscenter för grupper fungerar principen för förfallodatum sömlöst med bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="43b74-142">If you have setup retention policy in Security and Compliance center for groups, expiration policy works seamlessly with retention policy.</span></span> <span data-ttu-id="43b74-143">När en grupp upphör att gälla behålls gruppens konversationer i e-postlådan och filer på gruppwebbplatsen i behållarbehållaren för det specifika antal dagar som definierats i bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="43b74-143">When a group expires, the group's conversations in mail box and files in the group site are retained in the retention container for the specific number of days defined in the retention policy.</span></span> <span data-ttu-id="43b74-144">Användarna kommer dock inte att se gruppen eller dess innehåll efter utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="43b74-144">Users will not see the group, or its content, after expiration however.</span></span>

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a><span data-ttu-id="43b74-145">Hur och när en gruppägare får reda på om deras grupper kommer att löpa ut</span><span class="sxs-lookup"><span data-stu-id="43b74-145">How and when a group owner learns if their groups are going to expire</span></span>

<span data-ttu-id="43b74-146">Gruppägare meddelas endast via e-post.</span><span class="sxs-lookup"><span data-stu-id="43b74-146">Group owners will only be notified via email.</span></span> <span data-ttu-id="43b74-147">Om gruppen skapades via Planner, SharePoint eller någon annan app kommer meddelanden om förfallodatum alltid via e-post.</span><span class="sxs-lookup"><span data-stu-id="43b74-147">If the group was created via Planner, SharePoint, or any other app, the expiration notifications will always come via email.</span></span> <span data-ttu-id="43b74-148">Om gruppen skapades via Teams får gruppägaren ett meddelande om att förnya genom aktivitetsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="43b74-148">If the group was created via Teams, the group owner will receive a notification to renew through the activity section.</span></span> <span data-ttu-id="43b74-149">Vi rekommenderar inte att du aktiverar förfallodatum för en grupp om gruppägaren inte har en giltig e-postadress.</span><span class="sxs-lookup"><span data-stu-id="43b74-149">It's not recommended that you enable expiration on a group if your group owner doesn't have a valid email address.</span></span>

<span data-ttu-id="43b74-150">30 dagar innan gruppen går ut får gruppägarna (eller de e-postadresser som du har angett för grupper som inte har en ägare) ett e-postmeddelande som gör att de enkelt kan förnya gruppen.</span><span class="sxs-lookup"><span data-stu-id="43b74-150">30 days before the group expires, the group owners (or the email addresses that you specified for groups that don't have an owner) will receive an email allowing them to easily renew the group.</span></span> <span data-ttu-id="43b74-151">Om de inte förnyar det får de ett nytt förnyelsemeddelande 15 dagar före utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="43b74-151">If they don't renew it, they'll receive another renewal email 15 days before expiration.</span></span> <span data-ttu-id="43b74-152">Om de fortfarande inte har förnyat det får de ytterligare ett e-postmeddelande dagen före förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="43b74-152">If they still haven't renewed it, they will receive one more email notification the day before expiration.</span></span>

<span data-ttu-id="43b74-153">Om ingen av ägarna eller administratörerna av någon anledning förnyar gruppen innan den upphör att gälla kan administratören fortfarande återställa gruppen i upp till 30 dagar efter utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="43b74-153">If for some reason none of the owners or admins renew the group before it expires, the admin can still restore the group for up to 30 days after expiration.</span></span> <span data-ttu-id="43b74-154">Mer information finns i: [Återställ en borttagen Microsoft 365-grupp](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="43b74-154">For details see: [Restore a deleted Microsoft 365 group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

## <a name="related-articles"></a><span data-ttu-id="43b74-155">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="43b74-155">Related articles</span></span>

[<span data-ttu-id="43b74-156">Översikt över bevarandeprinciper</span><span class="sxs-lookup"><span data-stu-id="43b74-156">Overview of retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[<span data-ttu-id="43b74-157">Tilldela en ny ägare till en överbliven grupp</span><span class="sxs-lookup"><span data-stu-id="43b74-157">Assign a new owner to an orphaned group</span></span>](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

<span data-ttu-id="43b74-158">[Konfigurera Microsoft 365-gruppers förfallodatum](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span><span class="sxs-lookup"><span data-stu-id="43b74-158">[Configure Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '</span></span>
