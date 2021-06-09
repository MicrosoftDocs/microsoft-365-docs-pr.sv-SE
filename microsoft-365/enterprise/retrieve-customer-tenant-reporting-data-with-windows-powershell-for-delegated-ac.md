---
title: Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Sammanfattning: Använd fjärr-Windows PowerShell för Microsoft Exchange Online att hämta rapporter från enskilda kundklienter.'
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927222"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="dd6e5-103">Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)</span><span class="sxs-lookup"><span data-stu-id="dd6e5-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="dd6e5-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dd6e5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd6e5-105">Använd fjärr-Windows PowerShell för Microsoft Exchange Online att hämta rapporter från enskilda kundklienter.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="dd6e5-106">Syndication- och Molnlösningsleverantör-partner (CSP) kan komma åt data som tillsammans utgör kundklientrapporter direkt via fjärr-Windows PowerShell för Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="dd6e5-107">Det innebär att partner kan samla in och spara rapportdata och sedan utföra andra åtgärder med dem.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="dd6e5-108">När du öppnar en fjärranslutning är det identiskt med att köra en cmdlet mot en kunds innehavare om du hämtar rapporteringsdata om ett kund innehavare.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="dd6e5-109">I den här artikeln använder du fjärrstyrda Windows PowerShell för Exchange Online ansluta till ett enda kund innehavare och hämta en rapport.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="dd6e5-110">Som standard Windows PowerShell det inte går att samla rapporteringsdata från flera kundanspråk.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="dd6e5-111">De rapporter som du hämtar med den här proceduren gäller endast för  _de DelegeradeOrg_ som du ansluter till.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="dd6e5-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="dd6e5-112">Before you begin</span></span>

- <span data-ttu-id="dd6e5-113">Du måste ansluta till klientorganisationen Exchange Online via fjärr-Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-113">You need to connect to your Exchange Online tenant by using remote Windows PowerShell.</span></span> <span data-ttu-id="dd6e5-114">Instruktioner finns i [Anslut för Exchange Online med fjärr-Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="dd6e5-114">For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="dd6e5-115">Kör Get-StaleMailboxReport exempel</span><span class="sxs-lookup"><span data-stu-id="dd6e5-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="dd6e5-116">När du har öppnat en fjärrsession för Exchange Online kör du det här kommandot för att hämta **Get-StaleMailboxReport** för datumintervallet 2015-03-25 till och med 2015-03-31.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="dd6e5-117">Det finns många andra rapporteringscmdlets Exchange Online, Lync Online och SharePoint Online samt andra för meddelandespårning som du kan använda.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-117">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use.</span></span> <span data-ttu-id="dd6e5-118">Mer information om tillgängliga rapportcmdlets och webbtjänsten Office 365 Reporting finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="dd6e5-118">To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd6e5-119">Se även</span><span class="sxs-lookup"><span data-stu-id="dd6e5-119">See also</span></span>

#### 

<span data-ttu-id="dd6e5-120">[Office 365 Rapportwebbtjänst](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="dd6e5-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>
  
[<span data-ttu-id="dd6e5-121">Rapporteringscmdlets i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd6e5-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[<span data-ttu-id="dd6e5-122">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="dd6e5-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)