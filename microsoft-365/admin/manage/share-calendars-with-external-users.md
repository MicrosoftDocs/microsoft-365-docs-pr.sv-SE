---
title: Dela kalendrar med externa användare
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Lär dig hur du låter användarna dela sina kalendrar med externa användare för möten och avtalade tider.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760060"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="b5249-103">Dela kalendrar med externa användare</span><span class="sxs-lookup"><span data-stu-id="b5249-103">Share calendars with external users</span></span>

<span data-ttu-id="b5249-104">Det är ibland nödvändigt för användarna att schemalägga möten med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="b5249-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="b5249-105">För att förenkla processen att hitta vanliga Mötes tider kan du använda Microsoft 365 för att göra kalendrar tillgängliga för dessa personer.</span><span class="sxs-lookup"><span data-stu-id="b5249-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="b5249-106">Det här är personer som måste se lediga och upptagna tider för användare i organisationen, men har inte användar konton för Microsoft 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="b5249-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="b5249-107">Du kan aktivera kalender delning för alla användare i organisationen i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5249-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b5249-108">När delning är aktiverat kan användarna använda Outlook Web App för att dela sina kalendrar med alla i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="b5249-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="b5249-109">Personer i organisationen kan visa den delade kalendern tillsammans med sin egen kalender.</span><span class="sxs-lookup"><span data-stu-id="b5249-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="b5249-110">Personer utanför organisationen får ett e-postmeddelande med en URL som de kan använda för att visa kalendern.</span><span class="sxs-lookup"><span data-stu-id="b5249-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="b5249-111">Användare i organisationen bestämmer när de ska dela och hur många som ska delas.</span><span class="sxs-lookup"><span data-stu-id="b5249-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="b5249-112">Om du vill dela kalendrar med en organisation som använder Exchange Server 2013 (en lösning på platsen), Exchange-administratören måste du konfigurera en autentisering relation med molnet.</span><span class="sxs-lookup"><span data-stu-id="b5249-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="b5249-113">Detta kallas för Federation och måste uppfylla minst program varu krav.</span><span class="sxs-lookup"><span data-stu-id="b5249-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="b5249-114">[Mer information finns i ](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) Starta.</span><span class="sxs-lookup"><span data-stu-id="b5249-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="b5249-115">Aktivera kalender delning med administrations centret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5249-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b5249-116">Gå till **Inställningar** \> **organisations inställningar** i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="b5249-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="b5249-117">På fliken **tjänster** väljer du **kalender**.</span><span class="sxs-lookup"><span data-stu-id="b5249-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="b5249-118">På sidan **kalender** väljer du om du vill låta användarna dela sina kalendrar med personer utanför organisationen som har Microsoft 365 eller Exchange.</span><span class="sxs-lookup"><span data-stu-id="b5249-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="b5249-119">Välj om du vill tillåta anonyma användare (användare utan autentiseringsuppgifter) för att komma åt kalendrar via en e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="b5249-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="b5249-120">Välj vilken typ av kalender information som ska vara tillgänglig för användarna.</span><span class="sxs-lookup"><span data-stu-id="b5249-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="b5249-121">Du kan tillåta all information eller begränsa den till endast tid, ämne och plats.</span><span class="sxs-lookup"><span data-stu-id="b5249-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="b5249-122">Bjuda in personer att få åtkomst till kalendrar</span><span class="sxs-lookup"><span data-stu-id="b5249-122">Invite people to access calendars</span></span>

<span data-ttu-id="b5249-123">När delning har Aktiver ATS kan kalender ägare utöka inbjudningar till specifika användare.</span><span class="sxs-lookup"><span data-stu-id="b5249-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="b5249-124">Se [Dela kalendern i Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) för anvisningar.</span><span class="sxs-lookup"><span data-stu-id="b5249-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>