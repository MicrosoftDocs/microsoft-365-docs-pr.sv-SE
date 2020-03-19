---
title: Vad är syftet med Office 365-CNAME-posten för MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Läs mer om CNAME-posten "MSOID" i Office 365 som leder dig till den bästa servern för autentiseringsprocesser, så att du får ett snabbare svar.
monikerRange: o365-21vianet
ms.openlocfilehash: fdf728dcaebf65485b1eaed9b41e49f5327e9a41
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807577"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="5c1ad-103">Vad är syftet med Office 365-CNAME-posten för MSOID?</span><span class="sxs-lookup"><span data-stu-id="5c1ad-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="5c1ad-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="5c1ad-105">Följande gäller endast \*\*Office 365 som drivs av 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="5c1ad-p101">Du kanske undrar varför du måste lägga till "MSOID"-CNAME-posten i Office 365. Den här posten måste läggas till för alla egna domäner, oavsett vilken prenumeration du använder. Varför behöver du den här posten? Det har med tekniska frågor att göra - men i princip handlar det om att du med den här posten ser till att dirigeras till den bästa servern för vissa autentiseringsprocesser, för snabbare respons.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="5c1ad-p102">Teknisk information: När du kör ett klientprogram som fungerar med Office 365, till exempel Active Directory-synkroniseringsverktyget i Skype för företag - Online, Outlook, Windows PowerShell och Microsoft Azure, måste du autentiseras. I Office 365 används en CNAME-post för att peka på rätt autentiseringsslutpunkt för din plats, vilket ger snabba svarstider vid autentisering.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="5c1ad-p103">Om CNAME-posten saknas för din domän använder dessa program en standardslutpunkt för autentisering i USA, vilket innebär att autentiseringen kan saktas ned. Om CNAME-posten inte har konfigurerats korrekt - till exempel om det finns ett stavfel i **Pekar på-adress** - kan programmen inte autentisera uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="5c1ad-114">**Om Office 365 hanterar domänens DNS-poster** Den här CNAME-posten konfigureras för dig i Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c1ad-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="5c1ad-115">**Om du hanterar DNS-poster för din domän hos DNS-värden** skapar du den här posten själv genom [att följa instruktionerna för DNS-värden](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c1ad-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).</span></span>
  
<span data-ttu-id="5c1ad-116">Om du planerar en Office 365-distribution och vill veta mer om alla DNS-poster som du kan behöva lägga till eller uppdatera läser du om dem i [Referens: Externa domännamnssystemposter för Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span><span class="sxs-lookup"><span data-stu-id="5c1ad-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).</span></span>
  

