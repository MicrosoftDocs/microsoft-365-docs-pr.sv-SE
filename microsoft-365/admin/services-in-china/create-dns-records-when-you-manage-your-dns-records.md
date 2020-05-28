---
title: Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: 'Lär dig att skapa DNS-poster för Office 365 som drivs av 21Vianet när du hanterar dina DNS-poster. '
monikerRange: o365-21vianet
ms.openlocfilehash: 478f3d48a8d94d0a42d6501df8f0c32efc41e902
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399080"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="2fe56-103">Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="2fe56-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="2fe56-104">Detaljerade instruktioner om hur du skapar DNS-poster för Office 365 som drivs av 21Vianet, inklusive MX-posten som krävs för e-postroutning, finns i [Skapa DNS-poster hos alla DNS-värd för Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2fe56-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="2fe56-105">Fler alternativ och några saker att vara medveten om:</span><span class="sxs-lookup"><span data-stu-id="2fe56-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="2fe56-106">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="2fe56-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="2fe56-107">Beskrivningar av vad DNS-posterna gör finns i [grunderna för DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="2fe56-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="2fe56-108">Vissa DNS-värdleverantörer låter dig inte skapa alla nödvändiga posttyper, vilket orsakar [servicebegränsningar när din värdleverantör inte stöder SRV, CNAME, TXT eller omdirigering](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="2fe56-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="2fe56-109">Om din leverantör inte stöder SRV-, TXT- eller CNAME-poster rekommenderar vi att du [överför domänen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) till en [leverantör som stöder alla nödvändiga posttyper](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="2fe56-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="2fe56-110">Information om vilka DNS-poster som krävs och vilka värden som ska användas för varje post, inklusive MX-posten för e-post, finns [i Samla in den information du behöver för att skapa Office 365 DNS-poster](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span><span class="sxs-lookup"><span data-stu-id="2fe56-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="2fe56-111">Beskrivningar av vad DNS-posterna gör finns i [grunderna för DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="2fe56-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

