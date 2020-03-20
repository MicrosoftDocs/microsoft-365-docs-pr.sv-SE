---
title: 'Steg 5: optimera prestanda för klienten och Office 365-tjänsten'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Konfigurera TCP-inställningar och Office 365-tjänster för bättre prestanda.
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805630"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="b96e3-103">Steg 5: optimera prestanda för klienten och Office 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="b96e3-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="b96e3-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b96e3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="b96e3-106">Du kan öka prestandan genom att finjustera hur TCP (Transmission Control Protocol) fungerar mellan klientenheterna och Office 365-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="b96e3-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="b96e3-107">Du kan ändra följande TCP-inställningar på klientenheterna för att optimera TCP-prestanda:</span><span class="sxs-lookup"><span data-stu-id="b96e3-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="b96e3-108">[Skala TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/) så att klientenheten kan skicka fler data innan bekräftelse krävs</span><span class="sxs-lookup"><span data-stu-id="b96e3-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="b96e3-109">[TCP inaktivitetstid](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/) så att klientenheten kan hantera öppna anslutningar effektivare</span><span class="sxs-lookup"><span data-stu-id="b96e3-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="b96e3-110">[Maximal storlek på TCP-segmentet](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/) så att klientenheten kan skicka de största datablocken i ett paket</span><span class="sxs-lookup"><span data-stu-id="b96e3-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="b96e3-111">[Selektiva TCP-bekräftelser](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/) så att klientenheten kan bekräfta mottagna data på ett effektivare sätt</span><span class="sxs-lookup"><span data-stu-id="b96e3-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="b96e3-112">Se följande resurser för att optimera prestandan för Office 365-tjänster:</span><span class="sxs-lookup"><span data-stu-id="b96e3-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="b96e3-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b96e3-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="b96e3-114">Skype för företag Online</span><span class="sxs-lookup"><span data-stu-id="b96e3-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="b96e3-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b96e3-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="b96e3-116">Project Web App i Microsoft Project Online</span><span class="sxs-lookup"><span data-stu-id="b96e3-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="b96e3-117">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step5) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="b96e3-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b96e3-118">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="b96e3-118">Next step</span></span>

[<span data-ttu-id="b96e3-119">Avslutsvillkor för nätverksinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="b96e3-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
