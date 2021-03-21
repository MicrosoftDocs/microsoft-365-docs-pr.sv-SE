---
title: Använd mindre stödmeddelanden för att minska det minne som används när du läser e-postmeddelanden
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
description: Den här artikeln innehåller information om hur du kan använda smidiga popup-fönster för att förbättra prestanda för nedladdning av meddelanden i Outlook på webben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925262"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="99f7c-103">Använd mindre stödmeddelanden för att minska det minne som används när du läser e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="99f7c-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="99f7c-104">Den här artikeln innehåller information om hur du förbättrar prestanda för nedladdning av meddelanden i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="99f7c-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="99f7c-105">Den här artikeln är en del [av projektet Nätverksplanering och prestandajustering för Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="99f7c-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="99f7c-106">Som global Office 365-administratör kan du konfigurera Outlook på webben så att du får mindre och mindre minneskrävande versioner av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="99f7c-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="99f7c-107">När lutande popup-fönster konfigureras för Outlook på webben läses återgivna komponenter in på serversidan som optimerar prestanda.</span><span class="sxs-lookup"><span data-stu-id="99f7c-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99f7c-108">Från och med mars 2018 går det inte att använda magera popup-fönster för meddelanden som anger begränsningar av användningsrättigheter, till exempel IRM (Information Rights Management).</span><span class="sxs-lookup"><span data-stu-id="99f7c-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="99f7c-109">De här funktionerna kommer att fortsätta att fungera i huvudfönstret men är inte tillgängliga i mer smidiga popup-fönster:</span><span class="sxs-lookup"><span data-stu-id="99f7c-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="99f7c-110">Outlook-tillägg</span><span class="sxs-lookup"><span data-stu-id="99f7c-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="99f7c-111">Skype för företag-närvaro</span><span class="sxs-lookup"><span data-stu-id="99f7c-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="99f7c-112">Konfigurera magera popup-fönster för alla användare i din Office 365-organisation</span><span class="sxs-lookup"><span data-stu-id="99f7c-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="99f7c-113">[Anslut till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="99f7c-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="99f7c-114">Kör [cmdleten Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) med parametern LeanPopoutEnabled enligt följande:</span><span class="sxs-lookup"><span data-stu-id="99f7c-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="99f7c-115">Om du till exempel vill aktivera smidiga popup-fönster för alla användare i organisationen:</span><span class="sxs-lookup"><span data-stu-id="99f7c-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="99f7c-116">Så här inaktiverar du magera popup-fönster för alla användare i organisationen:</span><span class="sxs-lookup"><span data-stu-id="99f7c-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```