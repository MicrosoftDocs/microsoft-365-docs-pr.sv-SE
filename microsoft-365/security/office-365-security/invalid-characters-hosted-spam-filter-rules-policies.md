---
title: Undvik ogiltiga tecken i reglerna för skräppostfilter och skräppostfilterpolicyn
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Ger hjälp för administratörer som har ogiltiga tecken i sin anti-spam-konfiguration och stöter på problem när du försöker använda Security &amp; Compliance Center.
ms.openlocfilehash: f1841eb86583a48acecde0770f030b626323fa8e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812237"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="e78b4-103">Undvik ogiltiga tecken i reglerna för skräppostfilter och skräppostfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="e78b4-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="e78b4-104">Tidigare har Office 365-administratörer konfigurerat och konfigurerat regler för skräppostfilter och principen om skräppostfilter med hjälp av Administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e78b4-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="e78b4-105">Nu använder du &amp; Security Compliance Center för att hantera din anti-spam-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e78b4-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="e78b4-106">Följande tecken stöddes i EAC men stöds inte &amp; för användning i Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e78b4-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="e78b4-107">**Ogiltiga tecken:**</span><span class="sxs-lookup"><span data-stu-id="e78b4-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="e78b4-108">Om reglerna för skräppostfilter eller din skräppostfilterprincip innehåller något av de ogiltiga tecknen kan du stöta på något eller alla av dessa problem:</span><span class="sxs-lookup"><span data-stu-id="e78b4-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="e78b4-109">Du kanske inte kan hitta principen eller &amp; reglerna i Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e78b4-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="e78b4-110">Du kan få fel när du försöker få reglerna eller principen med hjälp av Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e78b4-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="e78b4-111">Du kanske upptäcker att principen eller inställningarna inte körs eller fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="e78b4-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="e78b4-112">Ta bort ogiltiga tecken från principen och reglerna för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="e78b4-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="e78b4-113">När du har identifierat principen och reglerna som innehåller ogiltiga tecken kan du ändra namnen med hjälp av Windows PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e78b4-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="e78b4-114">[Anslut till Exchange Online med Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e78b4-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="e78b4-115">Om du vill ändra namnet på principen för skräppostfilter kör du cmdleten Set-HostedContentFilterPolicy enligt följande:</span><span class="sxs-lookup"><span data-stu-id="e78b4-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="e78b4-116">Om du vill ändra namnet på en skräppostfilterregel kör du cmdleten Set-HostedContentFilterRule enligt följande:</span><span class="sxs-lookup"><span data-stu-id="e78b4-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="e78b4-117">Mer information</span><span class="sxs-lookup"><span data-stu-id="e78b4-117">For more information</span></span>

[<span data-ttu-id="e78b4-118">Hothantering i &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e78b4-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e78b4-119">PrincipbaseradContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="e78b4-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="e78b4-120">Regel för innehållsbaserad innehållsuppsättning</span><span class="sxs-lookup"><span data-stu-id="e78b4-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
