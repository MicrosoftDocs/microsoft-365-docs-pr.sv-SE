---
title: Hämta rapportdata för kundklientorganisationen med Windows PowerShell för DAP-partner
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
description: Sammanfattning Använd Windows PowerShell fjärr-PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kundklienter.
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927222"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Använd Fjärr-Windows PowerShell för Microsoft Exchange Online för att hämta rapporter från enskilda kundklienter.
  
Syndication- och leverantör av molnlösningar (CSP) kan komma åt data som tillsammans utgör kundklientrapporter direkt via fjärr-Windows PowerShell för Exchange Online PowerShell. Det innebär att partner kan samla in och spara rapportdata och sedan utföra andra åtgärder med dem. När du öppnar en fjärranslutning är det identiskt med att köra en cmdlet mot en kunds innehavare om du hämtar rapporteringsdata om ett kund innehavare.
  
I den här artikeln använder du fjärr-Windows PowerShell för Exchange Online för att ansluta till ett enda kundnöjdhet och hämta en rapport. Som standard har Windows PowerShell inte stöd för att samla rapporteringsdata från flera kundanspråk. De rapporter som du hämtar med den här proceduren gäller endast för  _de DelegeradeOrg_ som du ansluter till.
  
 
## <a name="before-you-begin"></a>Innan du börjar

- Du måste ansluta till Exchange Online-klienten med fjärr-Windows PowerShell. Instruktioner finns i Ansluta [till Exchange Online-klientorganisationen med Windows PowerShell för partner med behörighet för delegerad åtkomst (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Kör Get-StaleMailboxReport exempel

När du har öppnat en fjärrsession för Exchange Online kör du det här kommandot för att hämta **Get-StaleMailboxReport** för datumintervallet 2015-03-25 till och med 2015-03-31.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Det finns många andra rapporteringscmdlets för Exchange Online, Lync Online och SharePoint Online samt andra för meddelandespårning som du kan använda. Mer information om tillgängliga rapportcmdlets och webbtjänsten Office 365-rapportering finns i följande avsnitt.
  
## <a name="see-also"></a>Se även

#### 

[Webbtjänsten Office 365-rapportering](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))
  
[Rapporteringscmdlets i Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)