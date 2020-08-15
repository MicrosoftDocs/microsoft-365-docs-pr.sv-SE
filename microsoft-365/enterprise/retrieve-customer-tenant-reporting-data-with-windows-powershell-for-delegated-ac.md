---
title: Hämta klient organisations rapporterings data med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Sammanfattning: Använd Windows PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kund klient organisationer.'
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694383"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Hämta klient organisations rapporterings data med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Använd Windows PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kund klient organisationer.
  
Syndikerings-och moln lösnings leverantörer kan komma åt data som utgör kund klient organisationer direkt via Windows PowerShell för Exchange Online PowerShell. Då kan partners samla in och spara rapporterings data och sedan utföra andra åtgärder på den. När du har öppnat en fjärr anslutning är det identiskt med att köra en cmdlet mot en kund som är innehavd.
  
I den här artikeln använder du Windows PowerShell för Exchange Online för att ansluta till en enskild kund som är innehavare och hämta en rapport. Windows PowerShell stöder som standard inte insamling av rapporterings data från flera kund innehavare. De rapporter som du hämtar med den här proceduren är bara till den  _DelegatedOrg_ som du ansluter till.
  
 
## <a name="before-you-begin"></a>Innan du börjar

- Du måste ansluta till din Exchange Online-klient organisation via Windows PowerShell. Anvisningar finns i [ansluta till Exchange Online-klient organisationer med Windows PowerShell-partners för delegerade åtkomst behörigheter (DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Kör get-StaleMailboxReport-exemplet

När du har öppnat en fjärrsession till Exchange Online kör du det här kommandot för att hämta **Get-StaleMailboxReport** för datum intervallet 03/25/2015 till 03/31/2015.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Det finns många andra uppkopplings-cmdlets tillgängliga för Exchange Online, Lync Online och SharePoint Online samt andra för att spåra meddelanden. Mer information om tillgängliga rapporterings-cmdletar och webb tjänsten för rapportering av Office 365 finns i följande avsnitt.
  
## <a name="see-also"></a>Se även

#### 

[Office 365 repor ting Web Service](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[Rapportera cmdlets i Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)

