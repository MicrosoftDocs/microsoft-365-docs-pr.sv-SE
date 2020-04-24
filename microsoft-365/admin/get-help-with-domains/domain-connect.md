---
title: Använda Domain Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med Domain Connect-aktiverade registratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 6a86783ca880f6cb4ea833e4c2b659de4da5e5c1
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800017"
---
# <a name="using-domain-connect"></a><span data-ttu-id="275b3-103">Använda Domain Connect</span><span class="sxs-lookup"><span data-stu-id="275b3-103">Using Domain Connect</span></span>

 <span data-ttu-id="275b3-104">**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.</span><span class="sxs-lookup"><span data-stu-id="275b3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="275b3-105">[Med Domain](https://www.domainconnect.org/) Connect-aktiverade registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter.</span><span class="sxs-lookup"><span data-stu-id="275b3-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="275b3-106">I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, som Teams, fungerar med din domän.</span><span class="sxs-lookup"><span data-stu-id="275b3-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="275b3-107">Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="275b3-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="275b3-108">Domain Connect-registratorer som integreras med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="275b3-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="275b3-109">1&amp;1 IONOS</span><span class="sxs-lookup"><span data-stu-id="275b3-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="275b3-110">123Reg (På andra)</span><span class="sxs-lookup"><span data-stu-id="275b3-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="275b3-111">Godaddy</span><span class="sxs-lookup"><span data-stu-id="275b3-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="275b3-112">Wordpress</span><span class="sxs-lookup"><span data-stu-id="275b3-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="275b3-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="275b3-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="275b3-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="275b3-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="275b3-115">SecureServer eller WildWestDomains (GoDaddy-återförsäljare med SecureServer DNS hosting)</span><span class="sxs-lookup"><span data-stu-id="275b3-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="275b3-116">MadDog domäner</span><span class="sxs-lookup"><span data-stu-id="275b3-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="275b3-117">BilligaNamn</span><span class="sxs-lookup"><span data-stu-id="275b3-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="275b3-118">Vad händer med min e-post och webbplats?</span><span class="sxs-lookup"><span data-stu-id="275b3-118">What happens to my email and website?</span></span>

<span data-ttu-id="275b3-119">När du är klar med installationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för din domän börjar komma till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="275b3-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="275b3-120">Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.</span><span class="sxs-lookup"><span data-stu-id="275b3-120">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="275b3-121">Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är.</span><span class="sxs-lookup"><span data-stu-id="275b3-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="275b3-122">Installationsstegen För Domain Connect påverkar inte din webbplats.</span><span class="sxs-lookup"><span data-stu-id="275b3-122">The Domain Connect setup steps don't affect your website.</span></span>
