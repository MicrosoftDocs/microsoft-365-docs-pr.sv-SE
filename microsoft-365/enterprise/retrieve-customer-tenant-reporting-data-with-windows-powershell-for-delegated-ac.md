---
title: Hämta klient organisations rapporterings data med Windows PowerShell för DAP partners
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
description: 'Sammanfattning: Använd Windows PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kund klient organisationer.'
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694383"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="e76f4-103">Hämta klient organisations rapporterings data med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="e76f4-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="e76f4-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e76f4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e76f4-105">Använd Windows PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kund klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="e76f4-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="e76f4-106">Syndikerings-och moln lösnings leverantörer kan komma åt data som utgör kund klient organisationer direkt via Windows PowerShell för Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e76f4-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="e76f4-107">Då kan partners samla in och spara rapporterings data och sedan utföra andra åtgärder på den.</span><span class="sxs-lookup"><span data-stu-id="e76f4-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="e76f4-108">När du har öppnat en fjärr anslutning är det identiskt med att köra en cmdlet mot en kund som är innehavd.</span><span class="sxs-lookup"><span data-stu-id="e76f4-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="e76f4-109">I den här artikeln använder du Windows PowerShell för Exchange Online för att ansluta till en enskild kund som är innehavare och hämta en rapport.</span><span class="sxs-lookup"><span data-stu-id="e76f4-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="e76f4-110">Windows PowerShell stöder som standard inte insamling av rapporterings data från flera kund innehavare.</span><span class="sxs-lookup"><span data-stu-id="e76f4-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="e76f4-111">De rapporter som du hämtar med den här proceduren är bara till den  _DelegatedOrg_ som du ansluter till.</span><span class="sxs-lookup"><span data-stu-id="e76f4-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="e76f4-112">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e76f4-112">Before you begin</span></span>

- <span data-ttu-id="e76f4-113">Du måste ansluta till din Exchange Online-klient organisation via Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e76f4-113">You need to connect to your Exchange Online tenant by using remote Windows PowerShell.</span></span> <span data-ttu-id="e76f4-114">Anvisningar finns i [ansluta till Exchange Online-klient organisationer med Windows PowerShell-partners för delegerade åtkomst behörigheter (DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)</span><span class="sxs-lookup"><span data-stu-id="e76f4-114">For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="e76f4-115">Kör get-StaleMailboxReport-exemplet</span><span class="sxs-lookup"><span data-stu-id="e76f4-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="e76f4-116">När du har öppnat en fjärrsession till Exchange Online kör du det här kommandot för att hämta **Get-StaleMailboxReport** för datum intervallet 03/25/2015 till 03/31/2015.</span><span class="sxs-lookup"><span data-stu-id="e76f4-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="e76f4-117">Det finns många andra uppkopplings-cmdlets tillgängliga för Exchange Online, Lync Online och SharePoint Online samt andra för att spåra meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e76f4-117">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use.</span></span> <span data-ttu-id="e76f4-118">Mer information om tillgängliga rapporterings-cmdletar och webb tjänsten för rapportering av Office 365 finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e76f4-118">To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e76f4-119">Se även</span><span class="sxs-lookup"><span data-stu-id="e76f4-119">See also</span></span>

#### 

[<span data-ttu-id="e76f4-120">Office 365 repor ting Web Service</span><span class="sxs-lookup"><span data-stu-id="e76f4-120">Office 365 Reporting web service</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[<span data-ttu-id="e76f4-121">Rapportera cmdlets i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e76f4-121">Reporting cmdlets in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[<span data-ttu-id="e76f4-122">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="e76f4-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

