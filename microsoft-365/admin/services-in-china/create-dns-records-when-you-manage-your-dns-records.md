---
title: Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Lär dig hur du skapar DNS-Office 365 som drivs av 21Vianet när du hanterar dina DNS-poster. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914360"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster

Detaljerade anvisningar om hur du skapar DNS-poster för Office 365 som drivs av 21Vianet, inklusive MX-posten som krävs för e-postdirigering, finns i Skapa DNS-poster hos valfri [DNS-värd för Office 365.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 
  
  
Fler alternativ och några saker att vara medveten om:
      
-  Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md). En beskrivning av vad DNS-posterna gör finns i [Grundläggande om DNS.](../get-help-with-domains/dns-basics.md)
    
-  Vissa DNS-värdtjänster tillåter inte att du skapar alla nödvändiga posttyper, vilket leder till tjänstbegränsningar när din värd inte har stöd för [SRV, CNAME, TXT eller omdirigering.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) Om din leverantör inte har stöd för SRV-, TXT- [](../get-help-with-domains/buy-a-domain-name.md) eller CNAME-poster rekommenderar vi att du överför din domän till en leverantör som har stöd för [alla nödvändiga posttyper.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77) 
    
- Information om vilka DNS-poster som krävs och vilka värden som ska användas för varje post, inklusive MX-posten för e-post, finns i Samla in den information du behöver för att skapa [Office 365 DNS-poster.](../get-help-with-domains/information-for-dns-records.md) En beskrivning av vad DNS-posterna gör finns i [Grundläggande om DNS.](../get-help-with-domains/dns-basics.md)
