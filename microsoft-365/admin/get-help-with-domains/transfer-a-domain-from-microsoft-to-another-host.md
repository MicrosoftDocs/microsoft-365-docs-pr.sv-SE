---
title: Överföra en domän från Microsoft till en annan värd
f1.keywords:
- NOCSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Hitta stegen här för att överföra en domän från Microsoft till en annan registrator. '
ms.openlocfilehash: 1fb1fa50bd919bddb620a39d9edb46abb6710ba4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645281"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="c3c35-103">Överföra en domän från Microsoft till en annan värd</span><span class="sxs-lookup"><span data-stu-id="c3c35-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="c3c35-104">Du kan inte överföra en Microsoft 365-domän till en annan registrator för 60 dagar efter att du har köpt domänen från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3c35-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="c3c35-105">En _whois_-   fråga visar en Microsoft-köpt domän registrator som vilda Västeuropa Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="c3c35-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="c3c35-106">Men endast Microsoft bör kontaktas angående din Microsoft 365-köpta domän.</span><span class="sxs-lookup"><span data-stu-id="c3c35-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="c3c35-107">Följ de här stegen för att få en kod på Microsoft 365 och gå sedan till den andra webbplatsen för domän registratorn för att konfigurera ditt domän namn till den nya registratorn.</span><span class="sxs-lookup"><span data-stu-id="c3c35-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="c3c35-108">Överföra en domän</span><span class="sxs-lookup"><span data-stu-id="c3c35-108">Transfer a domain</span></span>

1. <span data-ttu-id="c3c35-109">Gå till inställningar i administrations centret  **Settings**   >  **Domains**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="c3c35-110">På sidan **domäner** väljer du den Microsoft 365-domän som du vill överföra till en annan domän registrator och väljer sedan **kontrol lera hälsa**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="c3c35-111">Högst upp på sidan väljer du **överför domän**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="c3c35-112">På sidan **Välj var du vill överföra din domän** väljer du **en annan registrator**och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="c3c35-113">På sidan **Lås upp domän överföring** väljer \*\* _du_ > Lås upp överföring för <domänen\*\*och väljer sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="c3c35-114">Kontrol lera din domän överförings kontakt information och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="c3c35-115">Kopiera auktoriseringsregeln och vänta ungefär 30 minuter för din domän överförings status till **olåst för överföring** på fliken **registrering** innan du fortsätter med nästa steg.</span><span class="sxs-lookup"><span data-stu-id="c3c35-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="c3c35-116">Gå till webbplatsen för den domän registrator som du vill hantera ditt domän namn på.</span><span class="sxs-lookup"><span data-stu-id="c3c35-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="c3c35-117">Följ anvisningarna för att överföra en domän (Sök efter hjälp på webbplatsen).</span><span class="sxs-lookup"><span data-stu-id="c3c35-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="c3c35-118">Det innebär vanligt vis att du betalar överförings avgifter och ger Authcode till den nya registratoren så att de kan initiera överföringen.</span><span class="sxs-lookup"><span data-stu-id="c3c35-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="c3c35-119">Microsoft skickar dig ett e-postmeddelande för att bekräfta att vi har tagit emot överföringsbegäran och att domänen överförs inom fem dagar.</span><span class="sxs-lookup"><span data-stu-id="c3c35-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="c3c35-120">Fliken registrerings kod för **registrering** på sidan  **domäner** i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3c35-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c3c35-121">. uk-domäner kräver en annan procedur.</span><span class="sxs-lookup"><span data-stu-id="c3c35-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="c3c35-122">Kontakta Microsoft support och be om en **IP-märkning** som stämmer överens med den registrator som du vill hantera domänen på.</span><span class="sxs-lookup"><span data-stu-id="c3c35-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="c3c35-123">När märket ändras överförs domänen direkt till den nya registratorn.</span><span class="sxs-lookup"><span data-stu-id="c3c35-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="c3c35-124">Sedan måste du arbeta med den nya registratorn för att slutföra överföringen, som troligen betalar överförings avgifter och lägga till den överförda domänen på ditt konto hos din nya registrator.</span><span class="sxs-lookup"><span data-stu-id="c3c35-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="c3c35-125">När överföringen är färdig förnyar du din domän hos den nya domän registratorn.</span><span class="sxs-lookup"><span data-stu-id="c3c35-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="c3c35-126">Slutför processen genom att gå tillbaka till sidan **domäner** i administrations centret och sedan välja  **fullständig domän överföring**.</span><span class="sxs-lookup"><span data-stu-id="c3c35-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="c3c35-127">Detta markerar domänen som att den inte längre är inköpt från Microsoft 365 och inaktiverar domän prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="c3c35-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="c3c35-128">Domänen tas inte bort från klienten och påverkar inte befintliga användare och post lådor på domänen.</span><span class="sxs-lookup"><span data-stu-id="c3c35-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c3c35-129">Microsoft 365-köpta domäner är inte kvalificerat för namnserver ändringar eller överföring av domänen mellan Microsoft 365-organisationer.</span><span class="sxs-lookup"><span data-stu-id="c3c35-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="c3c35-130">Om något av följande är obligatoriskt måste domän registreringen flyttas till en annan registrator.</span><span class="sxs-lookup"><span data-stu-id="c3c35-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
