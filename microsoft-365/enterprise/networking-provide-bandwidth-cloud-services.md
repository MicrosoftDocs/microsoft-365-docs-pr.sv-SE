---
title: 'Steg 1: förbereda nätverket för Microsoft 365'
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
description: Förstå behovet av bandbredd för molntjänsterna i Microsoft 365 Enterprise.
ms.openlocfilehash: 2f20542609c757c4fbccd2f9b0e4af59d9bc7566
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810032"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a><span data-ttu-id="ad2cc-103">Steg 1: förbereda nätverket för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad2cc-103">Step 1: Prepare your network for Microsoft 365</span></span>

<span data-ttu-id="ad2cc-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ad2cc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="ad2cc-106">I steg 1 måste du göra följande:</span><span class="sxs-lookup"><span data-stu-id="ad2cc-106">In Step 1, you must:</span></span>

- <span data-ttu-id="ad2cc-107">Utvärdera och justera nätverkets bandbredd för interna länkar och internetanslutningar för att klara trafik till molntjänsterna i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-107">Evaluate and adjust network bandwidth for internal links and Internet connections to account for traffic to Microsoft 365 Enterprise cloud services.</span></span>
- <span data-ttu-id="ad2cc-108">Justera nätverket med [Office 365 Reference Architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="ad2cc-108">Align your network with an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="ad2cc-109">Planera ändringarna, gör ett pilotprojekt och testa om ändringarna passar din bandbredd och krav på svarstider.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-109">Plan the changes, pilot them, and then test whether the changes fit your bandwidth and traffic latency requirements.</span></span>

<span data-ttu-id="ad2cc-110">Mer information och rekommendationer om hur du använder ExpressRoute med Office 365 och andra molntjänster för Microsoft 365 Enterprise finns i [Azure ExpressRoute för Office 365](https://docs.microsoft.com/office365/enterprise/azure-expressroute).</span><span class="sxs-lookup"><span data-stu-id="ad2cc-110">For information and recommendations about using ExpressRoute with Office 365 and the other cloud services of Microsoft 365 Enterprise, see [Azure ExpressRoute for Office 365](https://docs.microsoft.com/office365/enterprise/azure-expressroute).</span></span>

<span data-ttu-id="ad2cc-111">Som en mellanliggande kontrollpunkt kan du se vilka [avslutsvillkor](networking-exit-criteria.md#crit-networking-step1) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-111">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ad2cc-112">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ad2cc-112">Next step</span></span>

|||
|:-------|:-----|
|![Steg 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="ad2cc-114">Konfigurera lokala internetanslutningar för Office</span><span class="sxs-lookup"><span data-stu-id="ad2cc-114">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|

