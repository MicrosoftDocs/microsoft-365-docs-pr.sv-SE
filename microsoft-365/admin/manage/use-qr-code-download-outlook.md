---
title: Använda en QR-kod för att logga in på Outlook Mobile-apparna
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Lär dig hur du använder en QR-kod för att autentisera och ladda ned Outlook Mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914972"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Använda en QR-kod för att logga in på Outlook Mobile-apparna

> [!IMPORTANT]
> Den här funktionen är endast tillgänglig för organisationer som har aktiverat riktad version i administrationscentret för Microsoft 365. Om du vill aktivera Riktad version och lära dig mer om hur det fungerar kan [du läsa Konfigurera alternativen Standard eller Riktad version.](release-options-in-office-365.md) Vi kommer att utöka till fler organisationer under de kommande veckorna via en offentlig förhandsversion. Offentlig förhandsversion ger tidig åtkomst till Microsoft 365-funktioner.

Som Microsoft 365-administratör kan du göra det möjligt för användarna att logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord. Genom att skanna en QR-kod kan användarna autentisera och logga in på Outlook Mobile på ett säkert sätt.

I Outlook på webben eller andra Outlook-skrivbordsprogram kan användare se meddelanden om att de kan använda Outlook på sina mobila enheter. De här meddelandena kan hanteras av administratören med Exchange Powershell. Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn. De kommer att kunna skanna QR-koden för att logga in i Outlook på sin telefon eller surfplatta. Den här QR-koden är en kort token som endast kan lösas in en gång.

> [!NOTE]
> I vissa fall måste användarna autentisera sig igen på datorn för att QR-koden ska genereras.

## <a name="use-exchange-powershell"></a>Använda Exchange PowerShell

Den här funktionen är på som standard. Följ stegen nedan om du vill inaktivera den här funktionen.

1. [Anslut till Exchange PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook Mobile-apparna. Det förhindrar också att inloggningsflödet för QR-koden visas.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Relaterade ämnen

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)