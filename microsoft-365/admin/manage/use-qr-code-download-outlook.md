---
title: Använd en QR-kod för att logga in Outlook mobilapparna
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
description: Lär dig hur du använder en QR-kod för att autentisera och ladda ned Outlook mobil.
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286711"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Använd en QR-kod för att logga in Outlook mobilapparna

> [!IMPORTANT]
> Den här funktionen är endast tillgänglig för organisationer som har aktiverat riktad version i Administrationscenter för Microsoft 365. Om du vill aktivera Riktad version och lära dig mer om hur det fungerar kan [du läsa Konfigurera alternativen Standard eller Riktad version.](release-options-in-office-365.md) Vi kommer att utöka till fler organisationer under de kommande veckorna via en offentlig förhandsversion. Offentlig förhandsgranskning ger tidig åtkomst Microsoft 365 funktioner.

Som Microsoft 365 kan du göra det möjligt för användarna att logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord. Genom att skanna en QR-kod kan användarna autentisera och logga in på Outlook mobil.

I Outlook på webben och andra datorprogram Outlook användare se meddelanden om att de kan använda Outlook sina mobila enheter. De här meddelandena kan hanteras av administratören med hjälp Exchange Powershell. Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn. De kommer att kunna skanna QR-koden för att logga in Outlook sin telefon eller surfplatta. Den här QR-koden är en kort token som endast kan lösas in en gång.

> [!NOTE]
> I vissa fall måste användarna autentisera sig igen på datorn för att QR-koden ska skapas.

## <a name="use-exchange-powershell"></a>Använda Exchange PowerShell

Den här funktionen är på som standard. Följ stegen nedan om du vill inaktivera den här funktionen.

1. [Anslut till Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
2. Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna. Det förhindrar också att inloggningsflödet för QR-koden visas.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Relaterat innehåll

[Konfigurera alternativen Standard eller Riktad version](release-options-in-office-365.md) (artikel)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (artikel)