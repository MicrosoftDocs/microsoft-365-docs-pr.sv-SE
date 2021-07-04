---
title: Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner
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
description: 'Sammanfattning: Använd fjärr-Windows PowerShell för Microsoft Exchange Online att hämta rapporter från enskilda kundklienter.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290081"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Använd fjärr-Windows PowerShell för Microsoft Exchange Online att hämta rapporter från enskilda kundklienter.

Syndication- och Molnlösningsleverantör-partner (CSP) kan komma åt data som tillsammans utgör kundklientrapporter direkt via fjärr-Windows PowerShell för Exchange Online PowerShell. Det innebär att partner kan samla in och spara rapportdata och sedan utföra andra åtgärder med dem. När du öppnar en fjärranslutning är det identiskt med att köra en cmdlet mot en kunds innehavare om du hämtar rapporteringsdata om ett kund innehavare.

I den här artikeln använder du fjärrstyrda Windows PowerShell för Exchange Online ansluta till ett enda kund innehavare och hämta en rapport. Som standard Windows PowerShell det inte går att samla rapporteringsdata från flera kundanspråk. De rapporter som du hämtar med den här proceduren gäller endast för  _de DelegeradeOrg_ som du ansluter till.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste ansluta till klientorganisationen Exchange Online via fjärr-Windows PowerShell. Instruktioner finns i [Anslut för Exchange Online med fjärr-Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Kör Get-StaleMailboxReport exempel

När du har öppnat en fjärrsession för Exchange Online kör du det här kommandot för att hämta **Get-StaleMailboxReport** för datumintervallet 2015-03-25 till och med 2015-03-31.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Det finns många andra rapporteringscmdlets Exchange Online, Lync Online och SharePoint Online samt andra för meddelandespårning som du kan använda. Mer information om tillgängliga rapportcmdlets och webbtjänsten Office 365 Reporting finns i följande avsnitt.

## <a name="see-also"></a>Se även

[Office 365 Rapportwebbtjänst](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Rapporteringscmdlets i Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)

[Hjälp för partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)
