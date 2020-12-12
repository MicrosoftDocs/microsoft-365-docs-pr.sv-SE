---
title: Vad är syftet med Office 365-CNAME-posten för MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Läs mer om "MSOID" CNAME-posten i Office 365 som leder dig till den bästa servern för autentiseringsprocessen, så att du får snabbare svar.
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655490"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Vad är syftet med Office 365-CNAME-posten för MSOID?

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
> [!NOTE]
> Följande gäller endast för * * Office 365 som drivs av 21Vianet.
  
Du kanske undrar varför du måste lägga till "MSOID"-CNAME-posten i Office 365. Den här posten måste läggas till för alla egna domäner, oavsett vilken prenumeration du använder. Varför behöver du den här posten? Det har med tekniska frågor att göra - men i princip handlar det om att du med den här posten ser till att dirigeras till den bästa servern för vissa autentiseringsprocesser, för snabbare respons.
  
Teknisk information: När du kör ett klientprogram som fungerar med Office 365, till exempel Active Directory-synkroniseringsverktyget i Skype för företag - Online, Outlook, Windows PowerShell och Microsoft Azure, måste du autentiseras. I Office 365 används en CNAME-post för att peka på rätt autentiseringsslutpunkt för din plats, vilket ger snabba svarstider vid autentisering.
  
Om CNAME-posten saknas för din domän använder dessa program en standardslutpunkt för autentisering i USA, vilket innebär att autentiseringen kan saktas ned. Om CNAME-posten inte har konfigurerats korrekt - till exempel om det finns ett stavfel i **Pekar på-adress** - kan programmen inte autentisera uppgifterna.
  
 **Om Office 365 hanterar din domäns DNS-poster,** Office 365 konfigurerar den här CNAME-posten åt dig. 
  
 **Om du hanterar DNS-poster för din domän hos din DNS-värd kan** du skapa posten själv genom att [följa anvisningarna för din DNS-värd](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).
  
Om du planerar en Office 365-distribution och vill veta mer om alla de DNS-poster som du kan behöva lägga till eller uppdatera kan du läsa mer i [referens: externa DNS-poster för Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

