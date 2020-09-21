---
title: Om administratörsrollen i Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Exchange Online-administratörer hanterar organisationens e-post och post lådor. De återställer till exempel borttagna objekt i en användares post låda. '
ms.openlocfilehash: be4c8a4f1c75402d690cc705dd408c9070e40c9b
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131776"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="34715-104">Om administratörsrollen i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="34715-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="34715-105">För att hjälpa dig att administrera Microsoft 365 kan du [tilldela](assign-admin-roles.md) användare behörigheter för att hantera organisationens e-post och post lådor från [administrations centret för Exchange](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span><span class="sxs-lookup"><span data-stu-id="34715-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="34715-106">Det gör du genom att tilldela dem rollen som administratör i Exchange.</span><span class="sxs-lookup"><span data-stu-id="34715-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="34715-107">**Tips**: när du tilldelar någon till rollen Exchange-administratör tilldelar du dem också till rollen tjänst administratör.</span><span class="sxs-lookup"><span data-stu-id="34715-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="34715-108">På det sättet kan de se viktig information i administrations centret för Microsoft 365, till exempel statusen för Exchange Online-tjänsten, samt ändrings-och utgivnings aviseringar.</span><span class="sxs-lookup"><span data-stu-id="34715-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="34715-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="34715-109">Before you begin</span></span>

<span data-ttu-id="34715-110">Här är några av de viktigaste uppgifterna som användare kan göra när de tilldelas rollen som administratör i Exchange:</span><span class="sxs-lookup"><span data-stu-id="34715-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="34715-111">Recover deleted items in a user mailbox - Admin Help</span><span class="sxs-lookup"><span data-stu-id="34715-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="34715-112">[Konfigurera en princip för arkivering och borttagning för post lådor i din organisation](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="34715-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="34715-113">Konfigurera brevlådefunktioner såsom delningsprinciper för postlådor: hur användare kan dela kalender- och kontaktinformation med andra utanför din organisation.</span><span class="sxs-lookup"><span data-stu-id="34715-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="34715-114">Konfigurera ombuden "[Skicka som](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" och "[Skicka på abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" för en persons post låda.</span><span class="sxs-lookup"><span data-stu-id="34715-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on abehalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="34715-115">En chef kan till exempel vilja att hans/hennes assistent ska kunna skicka e-post åt chefen.</span><span class="sxs-lookup"><span data-stu-id="34715-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="34715-116">[Skapa en delad post låda](../email/create-a-shared-mailbox.md) så att en grupp människor kan övervaka och skicka e-post från en gemensam e-postadress.</span><span class="sxs-lookup"><span data-stu-id="34715-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="34715-117">[Skicka skräp post skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) och filter mot skadlig kod för organisationen.</span><span class="sxs-lookup"><span data-stu-id="34715-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="34715-118">Hantera Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="34715-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="34715-119">Exchange Online-rollgrupper</span><span class="sxs-lookup"><span data-stu-id="34715-119">Exchange Online role groups</span></span>

<span data-ttu-id="34715-p105">Om du har en stor organisation kanske Exchange-administratören vill tilldela Exchange-rollgrupper till användare. När en administratör lägger till en användare i en rollgrupp får användaren behörighet att utföra vissa företagsfunktioner som endast medlemmar i den gruppen kan utföra.</span><span class="sxs-lookup"><span data-stu-id="34715-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="34715-p106">Till exempel kan Exchange-administratören lägga till någon i rollgruppen för Identifieringshantering så att han/hon kan söka i postlådor efter data som uppfyller vissa villkor. Mer information finns i [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) och [Hantera rollgrupper](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="34715-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-role"></a><span data-ttu-id="34715-124">Läs mer om andra administratörs roller</span><span class="sxs-lookup"><span data-stu-id="34715-124">Learn about other admin role</span></span>

- [<span data-ttu-id="34715-125">Om administratörsroller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34715-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="34715-126">Om administratörs rollen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="34715-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="34715-127">Om administratörsrollen i Skype för företag</span><span class="sxs-lookup"><span data-stu-id="34715-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="34715-128">Använd Microsoft Teams-administratörs roll</span><span class="sxs-lookup"><span data-stu-id="34715-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 