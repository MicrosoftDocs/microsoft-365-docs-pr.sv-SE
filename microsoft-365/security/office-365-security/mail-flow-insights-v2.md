---
title: E-postflödesinsikter i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratörer kan lära sig mer om instrumentpanelen för e-postflödet i Security & Compliance Center, inklusive insikter, rapporter och widgetar.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3139fa6a139c7fa159c2e5e5daa3879322f4bf0
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552680"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="5523a-103">E-postflödesinsikter i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="5523a-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="5523a-104">Administratörer kan använda instrumentpanelen för e-postflödet i Security & Compliance Center för att upptäcka trender, insikter och vidta åtgärder för att åtgärda problem som rör e-postflödet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5523a-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their organization.</span></span>

<span data-ttu-id="5523a-105">De insikter, rapporter och widgetar som är tillgängliga i instrumentpanelen för e-postflödet är:</span><span class="sxs-lookup"><span data-stu-id="5523a-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="5523a-106">Rapport om e-postflödeskarta</span><span class="sxs-lookup"><span data-stu-id="5523a-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="5523a-107">Statusinsikt för domänmeddelandeflöde</span><span class="sxs-lookup"><span data-stu-id="5523a-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="5523a-108">Rapporten SMTP Auth-klienter</span><span class="sxs-lookup"><span data-stu-id="5523a-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="5523a-109">Statistik över avsändaredomän</span><span class="sxs-lookup"><span data-stu-id="5523a-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="5523a-110">Rapport om misslyckad leverans</span><span class="sxs-lookup"><span data-stu-id="5523a-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="5523a-111">Rapport om icke godkänd domän</span><span class="sxs-lookup"><span data-stu-id="5523a-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="5523a-112">Utgående och inkommande e-postflöde</span><span class="sxs-lookup"><span data-stu-id="5523a-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="5523a-113">Köaviseringar och köer</span><span class="sxs-lookup"><span data-stu-id="5523a-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="5523a-114">Rapporten Automatiskt vidarebefordrade meddelanden</span><span class="sxs-lookup"><span data-stu-id="5523a-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="5523a-115">Insikt om e-postloop</span><span class="sxs-lookup"><span data-stu-id="5523a-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="5523a-116">Insikt om långsamma e-postflödesregler</span><span class="sxs-lookup"><span data-stu-id="5523a-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="5523a-117">Behörigheter som krävs för att visa instrumentpanelen för e-postflödet</span><span class="sxs-lookup"><span data-stu-id="5523a-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="5523a-118">Instrumentpanelen för e-postflödet är tillgänglig för:</span><span class="sxs-lookup"><span data-stu-id="5523a-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="5523a-119">Medlemmar i den **globala administratörsrollen.**</span><span class="sxs-lookup"><span data-stu-id="5523a-119">Members of the **global administrator** role.</span></span>

- <span data-ttu-id="5523a-120">Medlemmar i **Exchange-administratörsrollen.**</span><span class="sxs-lookup"><span data-stu-id="5523a-120">Members of **Exchange administrator** role.</span></span>

- <span data-ttu-id="5523a-121">Medlemmar i **administratörsrollen E-postflöde** i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5523a-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="5523a-122">Om den här rollen uttryckligen tilldelas en användare som inte är medlem i den globala administratören eller Exchange-administratörsrollerna:</span><span class="sxs-lookup"><span data-stu-id="5523a-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="5523a-123">Användaren måste logga in på Security & Compliance Center direkt på <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="5523a-123">The user must log in to the Security & Compliance Center directly at <https://protection.office.com>.</span></span>

  - <span data-ttu-id="5523a-124">Användaren har endast skrivskyddad behörighet till instrumentpanelen för e-postflödet.</span><span class="sxs-lookup"><span data-stu-id="5523a-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="5523a-125">Användaren har inte tillgång till Microsoft 365-administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="5523a-125">The user won't have access to the Microsoft 365 admin center.</span></span>

<span data-ttu-id="5523a-126">Mer information om den globala administratörsrollen finns i [Om Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="5523a-126">For more information about the global administrator role, see [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="5523a-127">Information om hur du tilldelar säkerhetsroller & efterlevnadscenter till användare finns i [Ge användarna åtkomst till Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5523a-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="5523a-128">Var du hittar instrumentpanelen för e-postflödet</span><span class="sxs-lookup"><span data-stu-id="5523a-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="5523a-129">Gå till Security & Compliance Center på [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="5523a-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="5523a-130">Expandera **e-postflödet** och välj sedan **Instrumentpanel**.</span><span class="sxs-lookup"><span data-stu-id="5523a-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/mail-flow-dashboard-v2.png)
