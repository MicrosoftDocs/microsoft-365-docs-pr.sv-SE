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
ms.openlocfilehash: 4dc1f435571650ae4a805198782c3c24a92024fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197655"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="34264-104">Om administratörsrollen i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="34264-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="34264-105">För att administrera Microsoft 365 [](assign-admin-roles.md) kan du tilldela användarbehörigheter för att hantera din organisations e-post och postlådor från [administrationscentret för Exchange.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="34264-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="34264-106">Det gör du genom att tilldela dem rollen som administratör i Exchange.</span><span class="sxs-lookup"><span data-stu-id="34264-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="34264-107">**Tips:** När du tilldelar någon rollen som administratör i Exchange bör du även tilldela den rollen som tjänstadministratör.</span><span class="sxs-lookup"><span data-stu-id="34264-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="34264-108">På så sätt kan de se viktig information i administrationscentret för Microsoft 365, till exempel hälsotillståndet för Exchange Online-tjänsten, och ändra och släppa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="34264-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="34264-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="34264-109">Before you begin</span></span>

<span data-ttu-id="34264-110">Här är några av de viktigaste uppgifterna som användare kan göra när de tilldelas rollen som administratör i Exchange:</span><span class="sxs-lookup"><span data-stu-id="34264-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="34264-111">Recover deleted items in a user mailbox - Admin Help</span><span class="sxs-lookup"><span data-stu-id="34264-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="34264-112">[Konfigurera en princip för arkivering och borttagning för postlådor i din organisation.](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="34264-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="34264-113">Konfigurera brevlådefunktioner såsom delningsprinciper för postlådor: hur användare kan dela kalender- och kontaktinformation med andra utanför din organisation.</span><span class="sxs-lookup"><span data-stu-id="34264-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="34264-114">Konfigurera ombud[av " Skicka](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)som " och "[Skicka](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)för" för någons postlåda.</span><span class="sxs-lookup"><span data-stu-id="34264-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="34264-115">En chef kan till exempel vilja att hans/hennes assistent ska kunna skicka e-post åt chefen.</span><span class="sxs-lookup"><span data-stu-id="34264-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="34264-116">[Skapa en delad postlåda så](../email/create-a-shared-mailbox.md) att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress.</span><span class="sxs-lookup"><span data-stu-id="34264-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="34264-117">[Skydd mot skräppost och filter mot](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) skadlig programvara för organisationen.</span><span class="sxs-lookup"><span data-stu-id="34264-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="34264-118">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="34264-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="34264-119">Exchange Online-rollgrupper</span><span class="sxs-lookup"><span data-stu-id="34264-119">Exchange Online role groups</span></span>

<span data-ttu-id="34264-p105">Om du har en stor organisation kanske Exchange-administratören vill tilldela Exchange-rollgrupper till användare. När en administratör lägger till en användare i en rollgrupp får användaren behörighet att utföra vissa företagsfunktioner som endast medlemmar i den gruppen kan utföra.</span><span class="sxs-lookup"><span data-stu-id="34264-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="34264-p106">Till exempel kan Exchange-administratören lägga till någon i rollgruppen för Identifieringshantering så att han/hon kan söka i postlådor efter data som uppfyller vissa villkor. Mer information finns i [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo) och [Hantera rollgrupper](/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="34264-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="34264-124">Läs mer om andra administratörsroller</span><span class="sxs-lookup"><span data-stu-id="34264-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="34264-125">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34264-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="34264-126">Om administratörsrollen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="34264-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="34264-127">Om administratörsrollen i Skype för företag</span><span class="sxs-lookup"><span data-stu-id="34264-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="34264-128">Använda administratörsrollen i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34264-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)