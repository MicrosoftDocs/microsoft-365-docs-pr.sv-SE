---
title: Hantera Microsoft 365 med Windows PowerShell för DAP-partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Hur syndicerings- och molnlösningsleverantörpartners kan använda Windows PowerShell för att hantera Microsoft 365-kundklienter.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909532"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="68d4e-103">Hantera Microsoft 365 med Windows PowerShell för partner med delegerade åtkomstbehörigheter</span><span class="sxs-lookup"><span data-stu-id="68d4e-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="68d4e-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="68d4e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="68d4e-105">DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP).</span><span class="sxs-lookup"><span data-stu-id="68d4e-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="68d4e-106">Många är nätverks- eller tjänsteleverantörer.</span><span class="sxs-lookup"><span data-stu-id="68d4e-106">Many are network or telecom providers.</span></span> <span data-ttu-id="68d4e-107">De buntar ihop Microsoft 365-prenumerationer till sina tjänsteerbjudanden.</span><span class="sxs-lookup"><span data-stu-id="68d4e-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="68d4e-108">När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om dessa tenaniteter.</span><span class="sxs-lookup"><span data-stu-id="68d4e-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="68d4e-109">De här uppgifterna är svåra att utföra i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68d4e-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68d4e-110">Det är mycket enklare att använda PowerShell för Microsoft 365 för att utföra administrativa uppgifter som:</span><span class="sxs-lookup"><span data-stu-id="68d4e-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="68d4e-111">Lista alla kundens **klientorganisations-ID** och deras domäner</span><span class="sxs-lookup"><span data-stu-id="68d4e-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="68d4e-112">Identifiera alla användare i en kunds innehavare och deras tilldelade licenser</span><span class="sxs-lookup"><span data-stu-id="68d4e-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="68d4e-113">Vissa administrativa uppgifter kan endast utföras i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68d4e-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="68d4e-114">Följande artiklar visar hur Syndication- och CSP-partner använder PowerShell för att administrera kundrelationer:</span><span class="sxs-lookup"><span data-stu-id="68d4e-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="68d4e-115">Hantera Microsoft 365-klientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)</span><span class="sxs-lookup"><span data-stu-id="68d4e-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="68d4e-116">Lägga till en domän i ett klientföretag med Windows PowerShell för DAP-partners (Delegerad åtkomstbehörighet)</span><span class="sxs-lookup"><span data-stu-id="68d4e-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="68d4e-117">Ansluta till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="68d4e-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="68d4e-118">Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)</span><span class="sxs-lookup"><span data-stu-id="68d4e-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
