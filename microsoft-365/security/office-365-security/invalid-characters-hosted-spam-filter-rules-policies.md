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
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Undvik ogiltiga tecken i reglerna för skräppostfilter och skräppostfilterpolicy 

Tidigare har Office 365-administratörer konfigurerat och konfigurerat regler för skräppostfilter och principen om skräppostfilter med hjälp av Administrationscentret för Exchange (EAC). Nu använder du &amp; Security Compliance Center för att hantera din anti-spam-konfiguration. Följande tecken stöddes i EAC men stöds inte &amp; för användning i Security Compliance Center.  

**Ogiltiga tecken:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Om reglerna för skräppostfilter eller din skräppostfilterprincip innehåller något av de ogiltiga tecknen kan du stöta på något eller alla av dessa problem:
- Du kanske inte kan hitta principen eller &amp; reglerna i Security Compliance Center.
- Du kan få fel när du försöker få reglerna eller principen med hjälp av Windows PowerShell.
- Du kanske upptäcker att principen eller inställningarna inte körs eller fungerar som förväntat.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Ta bort ogiltiga tecken från principen och reglerna för skräppostfilter

När du har identifierat principen och reglerna som innehåller ogiltiga tecken kan du ändra namnen med hjälp av Windows PowerShell-cmdlets. 

1. [Anslut till Exchange Online med Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
    
2. Om du vill ändra namnet på principen för skräppostfilter kör du cmdleten Set-HostedContentFilterPolicy enligt följande:
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Om du vill ändra namnet på en skräppostfilterregel kör du cmdleten Set-HostedContentFilterRule enligt följande:
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Mer information

[Hothantering i &amp; Security Compliance Center](protect-against-threats.md)
  
[PrincipbaseradContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[Regel för innehållsbaserad innehållsuppsättning](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
