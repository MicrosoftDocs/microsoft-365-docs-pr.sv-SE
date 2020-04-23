---
title: Jämföra grupper
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Lär dig mer om de typer av grupper som du kan använda.
ms.openlocfilehash: 6f44214441c67e14d2cbc7ac12c0e2f3036acb2b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630719"
---
# <a name="compare-groups"></a><span data-ttu-id="5210c-103">Jämföra grupper</span><span class="sxs-lookup"><span data-stu-id="5210c-103">Compare groups</span></span>

<span data-ttu-id="5210c-104">I avsnittet **Grupper** i administrationscentret för Office 365 kan du skapa och hantera följande typer av grupper:</span><span class="sxs-lookup"><span data-stu-id="5210c-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="5210c-105">**Microsoft 365-grupper** används för samarbete mellan användare, både inom och utanför företaget.</span><span class="sxs-lookup"><span data-stu-id="5210c-105">**Microsoft 365 groups** are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="5210c-106">**Distributionsgrupper** används för att skicka aviseringar till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="5210c-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="5210c-107">**Säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5210c-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="5210c-108">**E-postaktiverade säkerhetsgrupper** används för att bevilja åtkomst till resurser som SharePoint och för att skicka e-postmeddelanden till dessa användare.</span><span class="sxs-lookup"><span data-stu-id="5210c-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="5210c-109">**Delade postlådor** används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation och supportens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5210c-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="5210c-110">Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="5210c-110">Microsoft 365 groups</span></span>

<span data-ttu-id="5210c-111">Microsoft 365-grupper används för samarbete mellan användare, både inom och utanför företaget.</span><span class="sxs-lookup"><span data-stu-id="5210c-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="5210c-112">Med varje Microsoft 365-grupp får medlemmarna en grupp-e-post och en delad arbetsyta för konversationer, filer och kalenderhändelser samt en planerare.</span><span class="sxs-lookup"><span data-stu-id="5210c-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="5210c-113">Du kan lägga till personer utanför organisationen i en grupp så länge som detta har [aktiverats av administratören](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5210c-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="5210c-114">Du kan också tillåta externa avsändare att skicka e-post till gruppens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5210c-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="5210c-115">Microsoft 365-grupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmarna kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning osv.</span><span class="sxs-lookup"><span data-stu-id="5210c-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="5210c-116">Microsoft 365-grupper kan nås via mobilappar, t. ex. Outlook för iOS och Outlook för Android.</span><span class="sxs-lookup"><span data-stu-id="5210c-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="5210c-117">Gruppmedlemmar kan skicka som eller skicka för gruppens e-postadress om det har [Aktiverats av administratören](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="5210c-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="5210c-118">Distributionsgrupper</span><span class="sxs-lookup"><span data-stu-id="5210c-118">Distribution groups</span></span>

<span data-ttu-id="5210c-119">[Distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) används för att skicka aviseringar till en grupp användare.</span><span class="sxs-lookup"><span data-stu-id="5210c-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="5210c-120">De kan ta emot externa e-postmeddelanden om de aktiveras av administratören.</span><span class="sxs-lookup"><span data-stu-id="5210c-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="5210c-121">Distributionsgrupper passar bäst för situationer där du behöver skicka information till en grupp användare, t. ex. "personer i byggnad A" eller "alla på Contoso".</span><span class="sxs-lookup"><span data-stu-id="5210c-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="5210c-122">Säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="5210c-122">Security groups</span></span>

<span data-ttu-id="5210c-123">[Säkerhetsgrupper](../email/create-edit-or-delete-a-security-group.md) används för att bevilja åtkomst till Microsoft 365-resurser, t.ex. SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5210c-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="5210c-124">De kan göra administrationen enklare eftersom du bara behöver administrera gruppen i stället för att lägga till användare i varje resurs individuellt.</span><span class="sxs-lookup"><span data-stu-id="5210c-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="5210c-125">Säkerhetsgrupper kan innehålla användare och enheter.</span><span class="sxs-lookup"><span data-stu-id="5210c-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="5210c-126">Om du vill skapa en säkerhetsgrupp för enheter kan du använda tjänster för hantering av mobila enheter, t. ex. Intune.</span><span class="sxs-lookup"><span data-stu-id="5210c-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="5210c-127">Säkerhetsgrupper kan vara [konfigurerade för dynamiskt medlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), så att gruppmedlemmar eller enheter kan läggas till eller tas bort automatiskt utifrån användarattribut, till exempel avdelning, plats, befattning eller enhetsattribut, t. ex. versionen på operativsystem.</span><span class="sxs-lookup"><span data-stu-id="5210c-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="5210c-128">E-postaktiverad säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="5210c-128">Mail-enabled security groups</span></span>

<span data-ttu-id="5210c-129">E-postaktiverade säkerhetsgrupper fungerar på samma sätt som vanliga säkerhetsgrupper förutom att de inte kan hanteras dynamiskt i Azure Active Directory och kan inte innehålla enheter.</span><span class="sxs-lookup"><span data-stu-id="5210c-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="5210c-130">De innehåller möjligheten att skicka e-post till alla medlemmar i gruppen.</span><span class="sxs-lookup"><span data-stu-id="5210c-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="5210c-131">Delade postlådor</span><span class="sxs-lookup"><span data-stu-id="5210c-131">Shared mailboxes</span></span>

<span data-ttu-id="5210c-132">[Delade postlådor](../email/create-a-shared-mailbox.md) används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.</span><span class="sxs-lookup"><span data-stu-id="5210c-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="5210c-133">Delade postlådor kan ta emot externa e-postmeddelanden om administratören har aktiverat det.</span><span class="sxs-lookup"><span data-stu-id="5210c-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="5210c-134">Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="5210c-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="5210c-135">Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".</span><span class="sxs-lookup"><span data-stu-id="5210c-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="5210c-136">Det är för närvarande inte möjligt att migrera en delad postlåda till en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="5210c-136">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="5210c-137">Finns det något du önskar?</span><span class="sxs-lookup"><span data-stu-id="5210c-137">Is this something you want?</span></span> <span data-ttu-id="5210c-138">Berätta för oss.</span><span class="sxs-lookup"><span data-stu-id="5210c-138">Let us know.</span></span> <span data-ttu-id="5210c-139">**[Rösta här](https://go.microsoft.com/fwlink/?linkid=871518)**.</span><span class="sxs-lookup"><span data-stu-id="5210c-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5210c-140">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5210c-140">Related articles</span></span>

[<span data-ttu-id="5210c-141">Läs mer om Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="5210c-141">Learn about Microsoft 365 groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
