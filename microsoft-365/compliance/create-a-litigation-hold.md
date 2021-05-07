---
title: Skapa ett bevarande av juridiska skäl
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Lär dig hur du placerar en postlåda i Bevarande av juridiska skäl, bevarar allt innehåll i postlådan under en undersökning.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162656"
---
# <a name="create-a-litigation-hold"></a>Skapa ett bevarande av juridiska skäl

Du kan placera en postlåda i Bevarande av juridiska skäl för att behålla allt innehåll i postlådan, inklusive borttagna objekt och de ursprungliga versionerna av ändrade objekt. När du placerar en användarpostlåda i Bevarande av juridiska skäl bevaras även innehållet i användarens arkivpostlåda (om det är aktiverat). När du skapar ett hold-up kan du ange varaktigheten för ett varaktighets bevaras (kallas även ett tidsbaserat is) så att borttagna och ändrade objekt bevaras under en angiven period och sedan tas bort permanent från postlådan. Du kan också bara behålla innehåll på obestämd tid (kallas oändligt *bevarande)* eller tills Bevarande av juridiska skäl har tagits bort. Om du anger en varaktighet för att hålla kvar beräknas det utifrån datumet då ett meddelande togs emot eller ett postlådeobjekt skapas. 
  
Det här händer när du skapar bevarande av juridiska skäl.
  
- Objekt som tas bort permanent av användaren finns kvar i mappen Återställningsbara objekt i användarens postlåda under tiden som det är kvar.

- Objekt som rensas från mappen Återställningsbara objekt av användaren behålls under tiden som det är kvar.

- Lagringskvoten för mappen Återställningsbara objekt ökar från 30 GB till 110 GB.

- Objekt i användarens primära postlådor och arkivpostlådor behålls

## <a name="assign-an-exchange-online-plan-2-license"></a>Tilldela en licens Exchange Online abonnemang 2

För att kunna placera Exchange Online postlåda i bevarande av juridiska skäl måste den tilldelas en licens Exchange Online abonnemang 2. Om en postlåda har tilldelats en Exchange Online abonnemang 1-licens måste du tilldela den en separat licens Exchange Online - arkivering den behöver för att kunna skapa en väntande licens.

> [!NOTE]
> För Office 365 Education organisationer stöds bevarande av juridiska skäl i Office 365 A1-prenumerationer, som omfattar en licens Exchange Online abonnemang 1 med kompletterande funktioner. Mer information finns i avsnittet "Exchange Online" i avsnittet om [Office 365 Education tjänstbeskrivning](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).

## <a name="place-a-mailbox-on-litigation-hold"></a>Placera en postlåda i Bevarande av juridiska skäl

Här är stegen för att placera en postlåda i Bevarande av juridiska skäl med hjälp Exchange administrationscenter.

1. Gå till [https://outlook.office.com/ecp](https://outlook.office.com/ecp) och logga in med ditt globala administratörskonto.

2. Klicka **på > postlådor** i det vänstra navigeringsfönstret.

3. Markera postlådan som du vill placera i Bevarande av juridiska skäl och klicka sedan på **Redigera**.

4. Klicka på Postlådefunktioner på **sidan med postlådeegenskaper.**
    
5. Under **Bevarande av juridiska skäl: Inaktiverad** klickar du **på** Aktivera för att placera postlådan i bevarande av juridiska skäl.
    
6. På sidan **Bevarande av juridiska** skäl anger du följande valfria information: 
    
    - **Bevarande av juridiska skäl varaktighet (dagar)** – Använd den här rutan för att skapa ett tidsbaserat bevarande och ange hur länge postlådeobjekt ska behållas när postlådan hålls i bevarande av juridiska skäl. Varaktigheten beräknas från det datum då ett postlådeobjekt togs emot eller skapades. När varaktigheten för undantaget upphör att gälla för ett visst objekt bevaras inte längre objektet. Om du låter rutan vara tom bevaras objekten ett obestämt sätt eller tills det att fältet tas bort. Ange varaktigheten genom att använda dagar.
    
    - **Obs!** – Använd den här rutan om du vill informera användaren om att användarens postlåda har bevarande av juridiska skäl. Anteckningen visas på sidan Kontoinformation i användarens postlåda om han eller hon använder Outlook 2010 eller senare. För att komma åt den här sidan kan användarna **klicka på Arkiv** i Outlook.
    
    - **URL** – Använd den här rutan om du vill dirigera användaren till en webbplats för mer information om bevarande av juridiska skäl. Den här URL-adressen visas på sidan Kontoinformation i användarens postlåda om de använder Outlook 2010 eller senare. För att komma åt den här sidan kan användarna **klicka på** Arkiv Outlook..

7. Klicka **på** Spara på **sidan Bevarande av** juridiska skäl och klicka sedan **på** Spara på egenskapssidan för postlådan.

### <a name="create-a-litigation-hold-using-powershell"></a>Skapa bevarande av juridiska skäl med PowerShell

Du kan också skapa ett bevarande av juridiska skäl genom att köra följande kommando [i Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Det föregående kommandot bevarar objekt ett obestämt antal objekt eftersom varaktigheten för bevarande inte har angetts. Så här skapar du ett tidsbaserat väntande kommando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Mer information finns i [Set-Mailbox](/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Hur fungerar Bevarande av juridiska skäl?

I det normala arbetsflödet för borttaget flyttas ett postlådeobjekt till undermappen Borttagningar i mappen Återställningsbara objekt när en användare tar bort det permanent (Skift+Delete) eller tar bort det från mappen Borttaget. En borttagningsprincip (som är en bevarandetagg som konfigurerats med åtgärden Ta bort bevarande) flyttar också objekt till undermappen Borttagningar när bevarandetiden löper ut. När en användare rensar ett objekt i mappen för permanent borttagna objekt eller när bevarandeperioden för borttagna objekt löper ut för ett objekt flyttas det till undermappen Rensningar i mappen Återställningsbara objekt och markeras för permanent borttagning. Den rensas från Exchange nästa gång postlådan bearbetas av assistenten för hanterade mappar (MFA).

När en postlåda placeras i Bevarande av juridiska skäl bevaras objekt i undermappen Rensningar under den bevarandetid som anges av Bevarande av juridiska skäl. Varaktigheten för håll beräknas från det ursprungliga datumet som ett objekt togs emot eller skapades och definierar hur länge objekten i undermappen Rensningar hålls kvar. När varaktigheten för undantaget för ett objekt i undermappen Rensningar förfaller markeras objektet för permanent borttagning och rensas från Exchange nästa gång postlådan bearbetas av MFA. Om ett obestämt sätt sätts på en postlåda rensas aldrig objekten från undermappen Rensningar.

Följande bild visar undermappar i mapparna för återställningsbara objekt och arbetsflödet för att hålla kvar.

![Livscykel för bevarande av juridiska skäl](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Om ett undantat objekt som är kopplat till ett eDiscovery-ärende placeras i en postlåda flyttas bortrensade objekt från undermappen Borttagningar till undermappen DiscoveryHolds och bevaras tills postlådan släpps från eDiscovery-undantas.
