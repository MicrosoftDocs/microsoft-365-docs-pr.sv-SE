---
title: Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Lär dig hur du skapar DNS-poster för Office 365 som drivs av 21Vianet när du hanterar dina DNS-poster. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644825"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="8dd0a-103">Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="8dd0a-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="8dd0a-104">Detaljerade anvisningar om hur du skapar DNS-poster för Office 365 som drivs av 21Vianet, inklusive MX-posten som krävs för e-postdirigering finns i [Skapa DNS-poster hos en DNS-värd för Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="8dd0a-105">Fler alternativ och några saker att vara medveten om:</span><span class="sxs-lookup"><span data-stu-id="8dd0a-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="8dd0a-106">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="8dd0a-107">Beskrivningar av vad DNS-posterna gör finns i [grundläggande om DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="8dd0a-108">Vissa DNS-värdar låter dig inte skapa alla nödvändiga post typer, vilket innebär [tjänst begränsningar när din värd inte stöder SRV, CNAME, txt eller omdirigering](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="8dd0a-109">Om din leverantör inte stöder SRV-, TXT-eller CNAME-poster rekommenderar vi att du [överför domänen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) till en [leverantör som stöder alla nödvändiga post typer](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="8dd0a-110">Information om vilka DNS-poster som krävs och hur du hittar de värden som ska användas för varje post, inklusive MX-posten för e-post, finns i [samla in informationen du behöver för att skapa DNS-poster för Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="8dd0a-111">Beskrivningar av vad DNS-posterna gör finns i [grundläggande om DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="8dd0a-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

