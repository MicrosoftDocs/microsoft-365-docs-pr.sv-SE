---
title: Använda domänanslutning
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med Domain Connect-aktiverade registratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 59e2f94fe83f87a5426064e49f0441356fbd732e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811219"
---
# <a name="using-domain-connect"></a><span data-ttu-id="745fb-103">Använda domänanslutning</span><span class="sxs-lookup"><span data-stu-id="745fb-103">Using Domain Connect</span></span>

 <span data-ttu-id="745fb-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="745fb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="745fb-105">[Med Domänanslutningaktiverade](https://www.domainconnect.org/) registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter.</span><span class="sxs-lookup"><span data-stu-id="745fb-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="745fb-106">I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="745fb-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="745fb-107">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="745fb-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="745fb-108">Domain Connect-registratorer som integreras med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="745fb-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="745fb-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="745fb-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="745fb-110">123Reg (på 80)</span><span class="sxs-lookup"><span data-stu-id="745fb-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="745fb-111">Godaddy</span><span class="sxs-lookup"><span data-stu-id="745fb-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="745fb-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="745fb-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="745fb-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="745fb-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="745fb-114">MediaTemple (på annat sätt)</span><span class="sxs-lookup"><span data-stu-id="745fb-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="745fb-115">SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-hosting)</span><span class="sxs-lookup"><span data-stu-id="745fb-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="745fb-116">MadDog-domäner</span><span class="sxs-lookup"><span data-stu-id="745fb-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="745fb-117">BilligaNamn</span><span class="sxs-lookup"><span data-stu-id="745fb-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="745fb-118">Vad händer med min e-postadress och hemsida?</span><span class="sxs-lookup"><span data-stu-id="745fb-118">What happens to my email and website?</span></span>

<span data-ttu-id="745fb-119">När du har konfigurerat installationen uppdateras MX-posten för domänen för att peka på Microsoft 365 och all e-post för domänen börjar komma till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="745fb-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="745fb-120">Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.</span><span class="sxs-lookup"><span data-stu-id="745fb-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="745fb-121">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="745fb-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="745fb-122">Installationsstegen för Domain Connect påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="745fb-122">The Domain Connect setup steps don't affect your website.</span></span>
