---
title: Använd Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Den här artikeln innehåller information om hur du använder Lean-popouts för att förbättra nedladdnings prestanda för meddelanden i Outlook på webben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694808"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="49ab3-103">Använd Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="49ab3-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="49ab3-104">Den här artikeln innehåller information om hur du förbättrar prestanda för nedladdning av meddelanden i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="49ab3-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="49ab3-105">Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune) Project.</span><span class="sxs-lookup"><span data-stu-id="49ab3-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="49ab3-106">Som en global administratör för Office 365 kan du konfigurera Outlook på webben så att det ger _Lean popouts_, en mindre, mindre minnes krävande version av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="49ab3-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="49ab3-107">När Lean-popouts konfigureras för Outlook på webben laddas serverbaserade åter givnings komponenter som optimerar prestanda.</span><span class="sxs-lookup"><span data-stu-id="49ab3-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49ab3-108">Från och med mars 2018 är Lean popouts inte tillgängliga för meddelanden som anger restriktioner för användnings rättigheter, till exempel IRM (Information Rights Management).</span><span class="sxs-lookup"><span data-stu-id="49ab3-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="49ab3-109">Dessa funktioner fortsätter att fungera i huvud fönstret men är inte tillgängliga i Lean-popouts:</span><span class="sxs-lookup"><span data-stu-id="49ab3-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="49ab3-110">Outlook-tillägg</span><span class="sxs-lookup"><span data-stu-id="49ab3-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="49ab3-111">Skype för företag – närvaro</span><span class="sxs-lookup"><span data-stu-id="49ab3-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="49ab3-112">Konfigurera Lean-popouts för alla användare i din Office 365-organisation</span><span class="sxs-lookup"><span data-stu-id="49ab3-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="49ab3-113">[Ansluta till Exchange Online med fjärr-PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span><span class="sxs-lookup"><span data-stu-id="49ab3-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="49ab3-114">Kör cmdleten [set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) med parametern LeanPopoutEnabled så här:</span><span class="sxs-lookup"><span data-stu-id="49ab3-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="49ab3-115">Om du till exempel vill aktivera Lean-popouts för alla användare i organisationen:</span><span class="sxs-lookup"><span data-stu-id="49ab3-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="49ab3-116">Så här inaktiverar du Lean-popouts för alla användare i organisationen:</span><span class="sxs-lookup"><span data-stu-id="49ab3-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
