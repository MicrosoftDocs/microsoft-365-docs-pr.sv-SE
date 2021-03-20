---
title: Om administratörsrollen i Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
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
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange Online-administratörer hanterar din organisations e-post och postlådor. De återskapar till exempel borttagna objekt i en användares postlåda. '
ms.openlocfilehash: 4db7b55f6bb5bb75149a3b91bd7855565ca1be46
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906354"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="f4777-104">Om administratörsrollen i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f4777-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="f4777-105">För att administrera Microsoft 365 [](assign-admin-roles.md) kan du tilldela användarbehörigheter för att hantera din organisations e-post och postlådor från [administrationscentret för Exchange.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="f4777-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="f4777-106">Det gör du genom att tilldela dem rollen som administratör i Exchange.</span><span class="sxs-lookup"><span data-stu-id="f4777-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="f4777-107">**Tips:** När du tilldelar någon rollen som administratör i Exchange bör du även tilldela den rollen som tjänstadministratör.</span><span class="sxs-lookup"><span data-stu-id="f4777-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="f4777-108">På så sätt kan de se viktig information i administrationscentret för Microsoft 365, till exempel hälsotillståndet för Exchange Online-tjänsten, och ändra och släppa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f4777-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f4777-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="f4777-109">Before you begin</span></span>

<span data-ttu-id="f4777-110">Här är några av de viktigaste uppgifterna som användare kan göra när de tilldelas rollen som administratör i Exchange:</span><span class="sxs-lookup"><span data-stu-id="f4777-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="f4777-111">Recover deleted items in a user mailbox - Admin Help</span><span class="sxs-lookup"><span data-stu-id="f4777-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="f4777-112">[Konfigurera en princip för arkivering och borttagning för postlådor i din organisation.](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="f4777-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="f4777-113">Konfigurera brevlådefunktioner såsom delningsprinciper för postlådor: hur användare kan dela kalender- och kontaktinformation med andra utanför din organisation.</span><span class="sxs-lookup"><span data-stu-id="f4777-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="f4777-114">Konfigurera ombud[av " Skicka](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)som " och "[Skicka](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)för" för någons postlåda.</span><span class="sxs-lookup"><span data-stu-id="f4777-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="f4777-115">En chef kan till exempel vilja att hans/hennes assistent ska kunna skicka e-post åt chefen.</span><span class="sxs-lookup"><span data-stu-id="f4777-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="f4777-116">[Skapa en delad postlåda så](../email/create-a-shared-mailbox.md) att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress.</span><span class="sxs-lookup"><span data-stu-id="f4777-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="f4777-117">[Skydd mot skräppost och filter mot](../../security/office-365-security/anti-spam-protection.md) skadlig programvara för organisationen.</span><span class="sxs-lookup"><span data-stu-id="f4777-117">[Email anti-spam protection](../../security/office-365-security/anti-spam-protection.md) and malware filters for the organization.</span></span>

- <span data-ttu-id="f4777-118">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="f4777-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="f4777-119">Exchange Online-rollgrupper</span><span class="sxs-lookup"><span data-stu-id="f4777-119">Exchange Online role groups</span></span>

<span data-ttu-id="f4777-p105">Om du har en stor organisation kanske Exchange-administratören vill tilldela Exchange-rollgrupper till användare. När en administratör lägger till en användare i en rollgrupp får användaren behörighet att utföra vissa företagsfunktioner som endast medlemmar i den gruppen kan utföra.</span><span class="sxs-lookup"><span data-stu-id="f4777-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="f4777-p106">Till exempel kan Exchange-administratören lägga till någon i rollgruppen för Identifieringshantering så att han/hon kan söka i postlådor efter data som uppfyller vissa villkor. Mer information finns i [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo) och [Hantera rollgrupper](/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="f4777-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="f4777-124">Läs mer om andra administratörsroller</span><span class="sxs-lookup"><span data-stu-id="f4777-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="f4777-125">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4777-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="f4777-126">Om administratörsrollen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4777-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="f4777-127">Om administratörsrollen i Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f4777-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="f4777-128">Använda administratörsrollen i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4777-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)