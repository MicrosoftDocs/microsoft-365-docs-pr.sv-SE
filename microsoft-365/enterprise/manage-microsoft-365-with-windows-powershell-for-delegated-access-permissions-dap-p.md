---
title: Hantera Microsoft 365 med Windows PowerShell för DAP-partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Hur syndicerings- och molnlösningsleverantörpartners kan använda Windows PowerShell för att hantera Microsoft 365-kundklienter.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909532"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Hantera Microsoft 365 med Windows PowerShell för partner med delegerade åtkomstbehörigheter

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP). Många är nätverks- eller tjänsteleverantörer. De buntar ihop Microsoft 365-prenumerationer till sina tjänsteerbjudanden. När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om dessa tenaniteter. De här uppgifterna är svåra att utföra i administrationscentret för Microsoft 365. Det är mycket enklare att använda PowerShell för Microsoft 365 för att utföra administrativa uppgifter som:
- Lista alla kundens **klientorganisations-ID** och deras domäner 
- Identifiera alla användare i en kunds innehavare och deras tilldelade licenser
> [!NOTE]
> Vissa administrativa uppgifter kan endast utföras i PowerShell.

Följande artiklar visar hur Syndication- och CSP-partner använder PowerShell för att administrera kundrelationer:
  
- [Hantera Microsoft 365-klientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Lägga till en domän i ett klientföretag med Windows PowerShell för DAP-partners (Delegerad åtkomstbehörighet)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [Hämta rapportdata från kundklientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
