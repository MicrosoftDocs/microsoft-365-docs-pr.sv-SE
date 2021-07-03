---
title: 'Microsoft 365 Stöd för klientprogram: Villkorsstyrd åtkomst'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig vilka plattformar, klienter och PowerShell-moduler som stöder villkorsstyrda Access för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286567"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="651ed-103">Microsoft 365 Stöd för klientprogram: Villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="651ed-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="651ed-104">På den moderna arbetsplatsen har användarna åtkomst till organisationens resurser från olika enheter och appar, var de än befinner sig.</span><span class="sxs-lookup"><span data-stu-id="651ed-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="651ed-105">Därför räcker det inte längre att fokusera på vem som kan komma åt en resurs.</span><span class="sxs-lookup"><span data-stu-id="651ed-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="651ed-106">Organisationen måste också stödja hur och var en resurs nås i din infrastruktur för åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="651ed-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="651ed-107">Med Azure Active Directory enhet, plats och multifaktorautentiseringsbaserad villkorsstyrd åtkomst kan du uppfylla det här nya kravet.</span><span class="sxs-lookup"><span data-stu-id="651ed-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="651ed-108">Villkorsstyrd åtkomst är en funktion i Azure Active Directory som gör att du kan tillämpa kontroller för åtkomst till appar i din miljö, allt baserat på specifika villkor och hanteras från en central plats.</span><span class="sxs-lookup"><span data-stu-id="651ed-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="651ed-109">Läs mer om [Azure Active Directory villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="651ed-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="651ed-110">Klienter som stöds & plattformar</span><span class="sxs-lookup"><span data-stu-id="651ed-110">Supported clients & platforms</span></span>

<span data-ttu-id="651ed-111">De senaste versionerna av följande klienter och plattformar har stöd för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="651ed-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="651ed-112">Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="651ed-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="651ed-113">PowerShell-moduler som stöds</span><span class="sxs-lookup"><span data-stu-id="651ed-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="651ed-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="651ed-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="651ed-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="651ed-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="651ed-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="651ed-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
