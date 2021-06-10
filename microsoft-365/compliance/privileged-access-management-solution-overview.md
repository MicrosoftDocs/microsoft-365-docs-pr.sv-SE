---
title: Hantering av behörighet i Microsoft 365
description: Lär dig hur du konfigurerar insiderriskfunktioner i hela Microsoft 365.
keywords: Microsoft 365, insider-risk, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "52161808"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="178bc-104">Hantering av behörighet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="178bc-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="178bc-105">Att vissa användare har stående åtkomst till känslig information eller viktiga nätverkskonfigurationsinställningar i Microsoft Exchange Online är en möjlig väg för komprometterade konton eller interna hotaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="178bc-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="178bc-106">Hantering av privilegierad åtkomst hjälper till att skydda organisationen från överträdelser och hjälper dig att uppfylla metodtips för efterlevnad genom att begränsa stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="178bc-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="178bc-107">I stället för att administratörer har konstant åtkomst implementeras direktåtkomstregler för aktiviteter som behöver förhöjda behörigheter.</span><span class="sxs-lookup"><span data-stu-id="178bc-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="178bc-108">Genom att aktivera hantering av privilegierad åtkomst för Exchange Online i Microsoft 365 kan organisationen arbeta utan några stående behörigheter och tillhandahålla ett skyddslager mot säkerhetsproblem av administrativ åtkomst.</span><span class="sxs-lookup"><span data-stu-id="178bc-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="178bc-109">Konfigurera hantering av behörighet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="178bc-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="178bc-110">Använd följande steg för att konfigurera hantering av behörighet för din organisation:</span><span class="sxs-lookup"><span data-stu-id="178bc-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Steg för hantering av privilegierad åtkomsthantering för Insider-risklösningar](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="178bc-112">Läs mer om [hantering av privilegierad](privileged-access-management-overview.md) åtkomst i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="178bc-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="178bc-113">Skapa en [godkännaresgrupp](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="178bc-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="178bc-114">Aktivera [hantering av privilegierad åtkomst](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="178bc-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="178bc-115">Skapa en [åtkomstprincip](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="178bc-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="178bc-116">Skicka/godkänna [behörighetsförfrågningar](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="178bc-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="178bc-117">Mer information om hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="178bc-117">More information about privileged access management</span></span>

- [<span data-ttu-id="178bc-118">Vanliga frågor och svar om hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="178bc-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)