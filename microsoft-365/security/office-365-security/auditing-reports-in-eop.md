---
title: Granskningsrapporter i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan läsa mer om de administratörsgranskningsrapporter som är tillgängliga i Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207119"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="6e271-103">Granskningsrapporter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="6e271-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6e271-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="6e271-104">**Applies to**</span></span>
-  [<span data-ttu-id="6e271-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="6e271-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="6e271-106">I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan granskningsrapporter hjälpa dig att uppfylla regelverk, efterlevnads- och rättstvistkrav för organisationen.</span><span class="sxs-lookup"><span data-stu-id="6e271-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="6e271-107">Du kan när som helst skaffa granskningsrapporter för att avgöra vilka ändringar som har gjorts i EOP-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="6e271-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="6e271-108">De här rapporterna kan hjälpa dig att felsöka konfigurationsproblem eller hitta orsaken till säkerhets- eller efterlevnadsrelaterade problem.</span><span class="sxs-lookup"><span data-stu-id="6e271-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="6e271-109">Det finns två granskningsrapporter tillgängliga i fristående EOP:</span><span class="sxs-lookup"><span data-stu-id="6e271-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="6e271-110">**Rapport om administratörsrollgrupp:** Med rapporten över administratörsrollgrupper kan du se när en användare läggs till eller tas bort från medlemskap i en administratörsrollgrupp.</span><span class="sxs-lookup"><span data-stu-id="6e271-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="6e271-111">Du kan använda den här rapporten för att övervaka ändringar av administratörsbehörigheter som tilldelats användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6e271-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="6e271-112">Mer information finns i Köra [en administratörsrollgruppsrapport i fristående EOP.](run-an-administrator-role-group-report-in-eop-eop.md)</span><span class="sxs-lookup"><span data-stu-id="6e271-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="6e271-113">**Granskningslogg för** administratör: Administratörens granskningslogg registrerar alla åtgärder (baserat på fristående EOP PowerShell-cmdlets) av en administratör eller en användare med administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="6e271-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="6e271-114">Mer information finns i Visa [granskningsloggen för administratörer i Exchange Online.](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)</span><span class="sxs-lookup"><span data-stu-id="6e271-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>