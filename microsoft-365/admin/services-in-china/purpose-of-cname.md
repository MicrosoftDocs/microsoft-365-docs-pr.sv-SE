---
title: Vad är syftet med Office 365-CNAME-posten för MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Läs mer om CNAME-posten "MSOID" i Office 365 som leder dig till den bästa servern för autentiseringsprocesser, så att du får ett snabbare svar.
monikerRange: o365-21vianet
ms.openlocfilehash: f5369b8a723c60691da0e73f2bd8cc32233abbcd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212227"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Vad är syftet med Office 365-CNAME-posten för MSOID?

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
> [!NOTE]
> Följande gäller endast **Office 365 som drivs av 21Vianet.
  
Du kanske undrar varför du måste lägga till "MSOID"-CNAME-posten i Office 365. Den här posten måste läggas till för alla egna domäner, oavsett vilken prenumeration du använder. Varför behöver du den här posten? Det har med tekniska frågor att göra - men i princip handlar det om att du med den här posten ser till att dirigeras till den bästa servern för vissa autentiseringsprocesser, för snabbare respons.
  
Teknisk information: När du kör ett klientprogram som fungerar med Office 365, till exempel Active Directory-synkroniseringsverktyget i Skype för företag - Online, Outlook, Windows PowerShell och Microsoft Azure, måste du autentiseras. I Office 365 används en CNAME-post för att peka på rätt autentiseringsslutpunkt för din plats, vilket ger snabba svarstider vid autentisering.
  
Om CNAME-posten saknas för din domän använder dessa program en standardslutpunkt för autentisering i USA, vilket innebär att autentiseringen kan saktas ned. Om CNAME-posten inte har konfigurerats korrekt - till exempel om det finns ett stavfel i **Pekar på-adress** - kan programmen inte autentisera uppgifterna.
  
 **Om Office 365 hanterar domänens DNS-poster** Den här CNAME-posten konfigureras för dig i Office 365. 
  
 **Om du hanterar DNS-poster för din domän hos DNS-värden** skapar du den här posten själv genom [att följa instruktionerna för DNS-värden](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).
  
Om du planerar en Office 365-distribution och vill veta mer om alla DNS-poster som du kan behöva lägga till eller uppdatera läser du om dem i [Referens: Externa domännamnssystemposter för Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

