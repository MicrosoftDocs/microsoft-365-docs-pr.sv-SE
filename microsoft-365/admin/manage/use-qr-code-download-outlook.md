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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242360"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Använda en QR-kod för att logga in på Outlook Mobile-apparna

> [!IMPORTANT]
> Den här funktionen är endast tillgänglig för organisationer som har aktiverat riktad version i administrationscentret för Microsoft 365. Mer information om hur du aktiverar Riktad version finns i Konfigurera standard- eller [riktad version.](release-options-in-office-365.md) Vi kommer att utöka till fler organisationer under de kommande veckorna via en offentlig förhandsversion. Offentlig förhandsversion ger tidig åtkomst till Microsoft 365-funktioner.

Som Microsoft 365-administratör kan du låta användarna logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord. Genom att skanna en QR-kod kan användarna autentisera och logga in på Outlook Mobile på ett säkert sätt.

I Outlook på webben eller andra Outlook-skrivbordsprogram kanske användarna ser meddelanden om att de kan använda Outlook på sina mobila enheter. De här meddelandena kan hanteras av administratören med Exchange Powershell. Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn. De kommer att kunna skanna QR-koden för att logga in i Outlook på sin telefon eller surfplatta. Den här QR-koden är ett kort löst token som bara kan lösas in en gång.

> [!NOTE]
> I vissa fall måste användarna autentisera igen på sin dator för att kunna generera QR-koden.

## <a name="use-exchange-powershell"></a>Använda Exchange PowerShell

Den här funktionen är på som standard. Följ stegen nedan om du vill inaktivera den här funktionen.

1. [Anslut till Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna. Det förhindrar också att inloggningsflödet för QR-kod visas.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Relaterade ämnen

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
