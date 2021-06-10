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
description: Aktivera kalenderdelning i Microsoft 365 så att användare kan dela sina kalendrar med personer i eller utanför organisationen.
ms.openlocfilehash: ee2b48182efec3e8bc22f47fd1657cd123ec65f8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635816"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="5d6ce-103">Dela kalendrar med externa användare</span><span class="sxs-lookup"><span data-stu-id="5d6ce-103">Share calendars with external users</span></span>

<span data-ttu-id="5d6ce-104">Ibland är det nödvändigt för användarna att schemalägga möten med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="5d6ce-105">För att förenkla processen med att hitta vanliga mötestider Microsoft 365 du göra kalendrar tillgängliga för dessa personer.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="5d6ce-106">Det här är personer som behöver se lediga och upptagna tider för användare i organisationen, men som inte har användarkonton för Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="5d6ce-107">Du kan aktivera kalenderdelning för alla användare i organisationen Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5d6ce-108">När delning har aktiverats kan användarna använda Outlook Web App och dela sina kalendrar med personer i eller utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="5d6ce-109">Personer i organisationen kan visa den delade kalendern tillsammans med sin egen kalender.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="5d6ce-110">Personer utanför organisationen får ett e-postmeddelande med en URL som de kan använda för att visa kalendern.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="5d6ce-111">Användarna i organisationen bestämmer när de ska dela och hur mycket de vill dela.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="5d6ce-112">Om du vill dela kalendrar med en organisation som använder Exchange Server 2013 (en lösning på platsen), Exchange-administratören måste du konfigurera en autentisering relation med molnet.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="5d6ce-113">Detta kallas federation och måste uppfylla minimikraven för programvara.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="5d6ce-114">[Mer information finns i ](/exchange/sharing-exchange-2013-help) Starta.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="5d6ce-115">Aktivera kalenderdelning med hjälp Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="5d6ce-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="5d6ce-116">I administrationscentret går du till sidan **Inställningar** \> **organisation Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="5d6ce-117">Välj **Kalender** på fliken **Tjänster.**</span><span class="sxs-lookup"><span data-stu-id="5d6ce-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="5d6ce-118">På sidan **Kalender** väljer du om du vill låta användare dela sina kalendrar med personer utanför din organisation som har Microsoft 365 eller Exchange.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="5d6ce-119">Välj om du vill tillåta anonyma användare (användare utan autentiseringsuppgifter) att få åtkomst till kalendrar via en e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="5d6ce-120">Välj vilken typ av kalenderinformation som användarna ska få tillgång till.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="5d6ce-121">Du kan tillåta all information eller begränsa den till endast tid eller tid, ämne och plats.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="5d6ce-122">Bjuda in personer att få åtkomst till kalendrar</span><span class="sxs-lookup"><span data-stu-id="5d6ce-122">Invite people to access calendars</span></span>

<span data-ttu-id="5d6ce-123">När delning har aktiverats kan kalenderägare utöka inbjudningar till specifika användare.</span><span class="sxs-lookup"><span data-stu-id="5d6ce-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="5d6ce-124">Anvisningar finns i [Dela din kalender i Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span><span class="sxs-lookup"><span data-stu-id="5d6ce-124">For instructions, see [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span></span>

## <a name="related-content"></a><span data-ttu-id="5d6ce-125">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="5d6ce-125">Related content</span></span>

<span data-ttu-id="5d6ce-126">[Aktivera eller inaktivera extern delning för en webbplats](/sharepoint/change-external-sharing-site) (artikel)</span><span class="sxs-lookup"><span data-stu-id="5d6ce-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>\
<span data-ttu-id="5d6ce-127">[Översikt över Microsoft 365 administrationscenter](../../business-video/admin-center-overview.md) (video)</span><span class="sxs-lookup"><span data-stu-id="5d6ce-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="5d6ce-128">[Hantera e-post och kalendrar](../email/index.yml) (länksida)</span><span class="sxs-lookup"><span data-stu-id="5d6ce-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>