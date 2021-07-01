---
title: Använda Anslut
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med Anslut domänregistratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228021"
---
# <a name="using-domain-connect"></a><span data-ttu-id="5b9b2-103">Använda Anslut</span><span class="sxs-lookup"><span data-stu-id="5b9b2-103">Using Domain Connect</span></span>

 <span data-ttu-id="5b9b2-104">**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="5b9b2-105">[Domän Anslut](https://www.domainconnect.org/) domänregistratorer låter dig lägga till din domän Microsoft 365 i en trestegsprocess som bara tar några minuter.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="5b9b2-106">I guiden bekräftar vi bara att du äger domänen och sedan konfigureras domänens poster automatiskt, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="5b9b2-107">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="5b9b2-108">Domän Anslut domänregistratorer som integrerar med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b9b2-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="5b9b2-109">1 &amp; 1 I ENTISKT</span><span class="sxs-lookup"><span data-stu-id="5b9b2-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="5b9b2-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="5b9b2-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="5b9b2-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="5b9b2-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="5b9b2-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="5b9b2-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="5b9b2-113">Hannsk</span><span class="sxs-lookup"><span data-stu-id="5b9b2-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="5b9b2-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="5b9b2-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="5b9b2-115">SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-värd)</span><span class="sxs-lookup"><span data-stu-id="5b9b2-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="5b9b2-116">MadDog Web Hosting</span><span class="sxs-lookup"><span data-stu-id="5b9b2-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="5b9b2-117">BilligaNamn</span><span class="sxs-lookup"><span data-stu-id="5b9b2-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="5b9b2-118">Vad händer med min e-post och webbplats?</span><span class="sxs-lookup"><span data-stu-id="5b9b2-118">What happens to my email and website?</span></span>

<span data-ttu-id="5b9b2-119">När du är klar med konfigurationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för domänen börjar komma Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="5b9b2-120">Kontrollera att du har lagt till användare och ställt in postlådor i Microsoft 365 för alla som får e-post på din domän!</span><span class="sxs-lookup"><span data-stu-id="5b9b2-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="5b9b2-121">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="5b9b2-122">Domänkonfigurationsstegen Anslut påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="5b9b2-122">The Domain Connect setup steps don't affect your website.</span></span>
