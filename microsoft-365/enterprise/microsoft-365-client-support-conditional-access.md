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
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904972"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="34f70-103">Microsoft 365 Stöd för klientprogram: Villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="34f70-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="34f70-104">På den moderna arbetsplatsen har användarna åtkomst till organisationens resurser från olika enheter och appar, var de än befinner sig.</span><span class="sxs-lookup"><span data-stu-id="34f70-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="34f70-105">Därför räcker det inte längre att fokusera på vem som kan komma åt en resurs.</span><span class="sxs-lookup"><span data-stu-id="34f70-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="34f70-106">Organisationen måste också stödja hur och var en resurs nås i din infrastruktur för åtkomstkontroll.</span><span class="sxs-lookup"><span data-stu-id="34f70-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="34f70-107">Med Azure Active Directory enhet, plats och multifaktorautentiseringsbaserad villkorsstyrd åtkomst kan du uppfylla det här nya kravet.</span><span class="sxs-lookup"><span data-stu-id="34f70-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="34f70-108">Villkorsstyrd åtkomst är en funktion i Azure Active Directory som gör att du kan tillämpa kontroller för åtkomst till appar i din miljö, allt baserat på specifika villkor och hanteras från en central plats.</span><span class="sxs-lookup"><span data-stu-id="34f70-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="34f70-109">Läs mer om [Azure Active Directory villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="34f70-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="34f70-110">Klienter som stöds & plattformar</span><span class="sxs-lookup"><span data-stu-id="34f70-110">Supported clients & platforms</span></span>

<span data-ttu-id="34f70-111">De senaste versionerna av följande klienter och plattformar har stöd för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="34f70-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="34f70-112">Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="34f70-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="34f70-113">PowerShell-moduler som stöds</span><span class="sxs-lookup"><span data-stu-id="34f70-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="34f70-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f70-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="34f70-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f70-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="34f70-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="34f70-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
