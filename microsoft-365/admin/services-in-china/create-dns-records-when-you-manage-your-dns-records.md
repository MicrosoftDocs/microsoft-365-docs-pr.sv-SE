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
description: 'Lär dig hur du skapar DNS-Office 365 som drivs av 21Vianet när du hanterar dina DNS-poster. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914360"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="4ada6-103">Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster</span><span class="sxs-lookup"><span data-stu-id="4ada6-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="4ada6-104">Detaljerade anvisningar om hur du skapar DNS-poster för Office 365 som drivs av 21Vianet, inklusive MX-posten som krävs för e-postdirigering, finns i Skapa DNS-poster hos valfri [DNS-värd för Office 365.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="4ada6-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="4ada6-105">Fler alternativ och några saker att vara medveten om:</span><span class="sxs-lookup"><span data-stu-id="4ada6-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="4ada6-106">Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="4ada6-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="4ada6-107">En beskrivning av vad DNS-posterna gör finns i [Grundläggande om DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="4ada6-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="4ada6-108">Vissa DNS-värdtjänster tillåter inte att du skapar alla nödvändiga posttyper, vilket leder till tjänstbegränsningar när din värd inte har stöd för [SRV, CNAME, TXT eller omdirigering.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="4ada6-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="4ada6-109">Om din leverantör inte har stöd för SRV-, TXT- [](../get-help-with-domains/buy-a-domain-name.md) eller CNAME-poster rekommenderar vi att du överför din domän till en leverantör som har stöd för [alla nödvändiga posttyper.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="4ada6-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="4ada6-110">Information om vilka DNS-poster som krävs och vilka värden som ska användas för varje post, inklusive MX-posten för e-post, finns i Samla in den information du behöver för att skapa [Office 365 DNS-poster.](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="4ada6-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="4ada6-111">En beskrivning av vad DNS-posterna gör finns i [Grundläggande om DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="4ada6-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
