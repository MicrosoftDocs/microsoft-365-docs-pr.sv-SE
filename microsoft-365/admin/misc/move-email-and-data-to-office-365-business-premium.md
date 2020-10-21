---
title: Flytta e-post och data till Microsoft 365 Business Standard
f1.keywords:
- NOCSH
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
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: Lär dig hur du flyttar data till den nya företags identiteten.
ms.openlocfilehash: 4f105e00ab6496a5d1d3edfc0e0f1abd4eced412
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645041"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>Flytta e-post och data till Microsoft 365 Business Standard

När du uppgraderar till Microsoft 365 Business Standard ger vi dig en ny  *företags identitet*. Du får ett nytt e-postkonto och ett separat OneDrive-konto för företagsdata. 
  
Om du vill flytta några av dina personliga data till den nya företagsidentiteten följer du anvisningarna nedan.
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **Kopiera dina OneDrive-data**
1. Skapa en tillfällig mapp på hård disken för att tillfälligt lagra de filer som du vill migrera till Microsoft 365 för företag.
    
2. Gå till [https://onedrive.live.com/](https://onedrive.live.com/) och logga in med det Microsoft-konto som du använder för att komma åt prenumerationen för microsoft 365-familjen. 
    
3. Kopiera de filer som du vill använda med Microsoft 365 för företag till den lokala mappen som du skapade i steg 1.
    
 **Importera OneDrive-filer till Microsoft 365 för företag**
1. Gå till [admin.Microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877) och logga in med ditt Microsoft 365-program för företag – användar namn och lösen ord. 
    
2. Välj ikonen för **startprogrammet** i det övre vänstra hörnet och välj sedan **OneDrive**.
  
    > [!TIP]
    > Första gången du öppnar OneDrive för företag måste du konfigurera din OneDrive. Om det inträffar väljer du **Nästa**på sidan **Välkommen till OneDrive för företag** . När OneDrive är aktiverat väljer **du OneDrive är klar**. 
  
3. En tom OneDrive-mapp visas. Om du vill skapa undermappar väljer du **ny** \> **mapp**.

4. Välj **Ladda upp** för att kopiera filerna från hård disken dit du kopierade dina OneDrive-filer. 
  
    > [!NOTE]
    >  Du kan ladda upp enskilda filer och grupper med filer (till exempel alla filer i en viss mapp) samtidigt, men du kan inte kopiera en mapp till OneDrive för företag. I stället måste du skapa den mappstruktur som du vill ha i OneDrive för företag. >  Om du vill kopiera filer till en mapp som du skapade i steg 4 öppnar du den mappen innan du laddar upp filerna. Annars laddas filerna upp till rotmappen. Du kan även flytta filer mellan mappar i OneDrive för företag när du har laddat upp dem. 
  
## <a name="outlookemail"></a>[Outlook/E-post](#tab/Outlook)
  
 **Exportera Outlook 2013-information till en Outlook-datafil**
1. Innan du kan skapa Outlook-datafilen (PST) måste det konto som du vill exportera Outlook-information från redan ha lagts till i skrivbordsversionen av Outlook. Information om hur du lägger till ett konto i Outlook 2013 eller senare finns i [Konfigurera e-post i Outlook (för Windows)](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) eller [Konfigurera e-post i Outlook för Mac 2011](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54).
    
2. Alla användare måste följa anvisningarna i [Exportera eller säkerhetskopiera e-post, kontakter och kalender till en Outlook-fil (.pst)](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91).
    
 **Konfigurera ditt nya e-postkonto i Outlook**
1. Varje användare måste konfigurera sitt nya e-postkonto som medföljde Microsoft 365 för företag-prenumerationen. De behöver då adressen till sitt nya e-postkonto. Alla användares e-postkonton är samma som det användar namn som de använder för att logga in på Microsoft 365 för företag. Det ser ut ungefär som sue@contoso.onmicrosoft.com eller david@contoso.com.
    
2. Be alla användare att lägga till sina e-postkonton i Outlook. Mer information finns i [Konfigurera e-post i Outlook (för Windows)](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) eller [Konfigurera e-post i Outlook för Mac 2011](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54).
    
 **Importera information från Outlook-datafilen**
1. Då kopplas e-post, kalender, uppgifter och kontakter som lagras i PST-filen till ditt Microsoft 365 för företag-e-postkonto.
    
2. Om du vill importera informationen som lagras i PST-filen till ditt Microsoft 365 för företag-e-postkonto, måste varje användare följa stegen i [Importera e-post, kontakter och kalender från en Outlook. PST-fil](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
    
---

