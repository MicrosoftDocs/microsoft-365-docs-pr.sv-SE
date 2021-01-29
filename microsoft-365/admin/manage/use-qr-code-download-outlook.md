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
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050784"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Använda en QR-kod för att logga in på Outlook Mobile-apparna

> [!IMPORTANT]
> Den här Microsoft 365-funktionen är en offentlig förhandsversion. Offentlig förhandsversion ger tidig åtkomst till Microsoft 365-funktioner.

Som Microsoft 365-administratör kan du låta användarna logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord. Genom att skanna en QR-kod kan användare autentisera och logga in i Outlook Mobile på ett säkert sätt.

I Outlook på webben eller andra Outlook-skrivbordsprogram kanske användarna ser meddelanden om att de kan använda Outlook på sina mobila enheter. De här meddelandena kan hanteras av administratören med Exchange Powershell. Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn. De kommer att kunna skanna QR-koden för att logga in i Outlook på sin telefon eller surfplatta. Den här QR-koden är ett kort löst token som bara kan lösas in en gång.

> [!NOTE]
> I vissa fall måste användarna autentisera igen på sin dator för att kunna generera QR-koden.

## <a name="use-exchange-powershell"></a>Använda Exchange PowerShell

Den här upplevelsen är på som standard. Följ stegen nedan om du vill inaktivera den här funktionen.

1. [Anslut till Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna. Det förhindrar också att inloggningsflödet för QR-kod visas.

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

Relaterade ämnen

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)