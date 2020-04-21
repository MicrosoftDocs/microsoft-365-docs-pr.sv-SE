---
title: Dela kalendrar med externa användare
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Lär dig hur du låter användarna dela sina kalendrar med externa användare för möten och avtalade tider. '
ms.openlocfilehash: bd297fc2d684357d0500495e5a8263e5279efa39
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628046"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="b2507-103">Dela kalendrar med externa användare</span><span class="sxs-lookup"><span data-stu-id="b2507-103">Share calendars with external users</span></span>

<span data-ttu-id="b2507-104">Det är ofta nödvändigt att schemalägga möten med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="b2507-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="b2507-105">För att förenkla processen för att hitta ömsesidigt angenäma mötestider kan du med Microsoft 365 göra kalendrar tillgängliga för "externa användare", de som behöver se ledig/upptagen tid men inte har användarkonton för din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="b2507-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="b2507-106">Kalenderdelning är en global inställning, vilket innebär att du, administratören, kan aktivera den för alla användare i klienten.</span><span class="sxs-lookup"><span data-stu-id="b2507-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="b2507-107">När delningen är aktiverad kan användare använda Outlook Web App för att dela sina kalendrar med personer i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="b2507-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="b2507-108">Personer i organisationen kan visa den delade kalendern sida vid sida med sin egen.</span><span class="sxs-lookup"><span data-stu-id="b2507-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="b2507-109">Personer utanför organisationen får ett e-postmeddelande med en URL som de kan använda för att visa kalendern.</span><span class="sxs-lookup"><span data-stu-id="b2507-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="b2507-110">Användaren bestämmer hur mycket som ska delas och när, samt när kalendern ska vara privat.</span><span class="sxs-lookup"><span data-stu-id="b2507-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2507-p103">Om du vill dela kalendrar med en organisation som använder Exchange Server 2013 (en lösning på platsen), Exchange-administratören måste du konfigurera en autentisering relation med molnet. Det här kallas "federation" och som måste uppfylla minimikraven för programvaran. [Mer information finns i ](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) Starta.</span><span class="sxs-lookup"><span data-stu-id="b2507-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="b2507-114">Aktivera kalenderdelning med administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2507-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b2507-115">Gå till sidan **Inställningarstjänster** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">& tillägg i administrationscentret.</a></span><span class="sxs-lookup"><span data-stu-id="b2507-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="b2507-116">På sidan \*\*Tillägg till Tjänster &amp; \*\* väljer du **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="b2507-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="b2507-117">På sidan **Kalender** som öppnas väljer du om du vill att användarna ska kunna dela sina kalendrar med personer utanför organisationen som har Microsoft 365 eller Exchange.</span><span class="sxs-lookup"><span data-stu-id="b2507-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="b2507-118">Välj om du vill tillåta anonyma användare (användare utan inloggningsuppgifter) att komma åt kalendrar via en e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="b2507-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="b2507-119">Välj vilken typ av kalenderinformation som ska göras tillgänglig för användarna.</span><span class="sxs-lookup"><span data-stu-id="b2507-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="b2507-120">Du kan bara tillåta all information eller begränsa den till tid eller tid, ämne och plats.</span><span class="sxs-lookup"><span data-stu-id="b2507-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="b2507-121">Bjuda in personer att få åtkomst till kalendrar</span><span class="sxs-lookup"><span data-stu-id="b2507-121">Invite people to access calendars</span></span>

<span data-ttu-id="b2507-p105">När delning är aktiverad för klienten kan kalenderinnehavare utöka inbjudningar till specifika användare. Se [Dela kalendern i Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) för anvisningar.</span><span class="sxs-lookup"><span data-stu-id="b2507-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  

