---
title: Hantera Microsoft 365 med Windows PowerShell för DAP partners
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
description: Så här kan syndikerings-och moln lösnings leverantörer använda Windows PowerShell för att hantera Microsoft 365-kundtjänster.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429884"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="096ad-103">Hantera Microsoft 365 med Windows PowerShell för delegerade åtkomst behörighets partners</span><span class="sxs-lookup"><span data-stu-id="096ad-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="096ad-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="096ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="096ad-105">DAP-partners (delegerade åtkomst behörigheter) för syndikering och moln lösnings leverantörer.</span><span class="sxs-lookup"><span data-stu-id="096ad-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="096ad-106">Många är nätverks-eller Telekom-leverantörer.</span><span class="sxs-lookup"><span data-stu-id="096ad-106">Many are network or telecom providers.</span></span> <span data-ttu-id="096ad-107">De fördelar Microsoft 365-abonnemang i sina tjänst erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="096ad-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="096ad-108">När de säljer en Microsoft 365-prenumeration beviljas de automatiskt administration på uppdrag av (AOBO) behörigheter till kundens innehav, så att de kan administrera och rapportera om dessa innehavare.</span><span class="sxs-lookup"><span data-stu-id="096ad-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="096ad-109">De här uppgifterna är svåra att utföra i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="096ad-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="096ad-110">Det är mycket enklare att använda PowerShell för Microsoft 365 för att utföra administrativa uppgifter som:</span><span class="sxs-lookup"><span data-stu-id="096ad-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="096ad-111">Lista alla kund **TenantIds** och deras domäner</span><span class="sxs-lookup"><span data-stu-id="096ad-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="096ad-112">Identifiera alla användare i en kunds innehav och deras tilldelade licenser</span><span class="sxs-lookup"><span data-stu-id="096ad-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="096ad-113">Vissa administrativa uppgifter kan bara göras i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="096ad-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="096ad-114">Följande artiklar visar hur syndikerings-och KRYPTOGRAFIPROVIDER-partners använder PowerShell för att administrera sina kund innehav:</span><span class="sxs-lookup"><span data-stu-id="096ad-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="096ad-115">Hantera Microsoft 365-klient organisationer med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="096ad-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="096ad-116">Lägga till en domän i en klient innehav med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="096ad-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="096ad-117">Ansluta till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="096ad-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="096ad-118">Hämta klient organisations rapporterings data med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="096ad-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   