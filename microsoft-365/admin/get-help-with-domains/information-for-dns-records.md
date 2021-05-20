---
title: Samla den information du behöver för att skapa DNS-poster
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Samla in de värden/den information du behöver för att skapa DNS-poster för att ansluta din domän Microsoft 365 prenumerationen.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582962"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Samla den information du behöver för att skapa DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Steg 1: Hitta TXT-postvärdet och verifiera

::: moniker range="o365-worldwide"

1. I Microsoft 365 administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Konfigurera</a> domäner.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Konfigurera</a> domäner.

::: moniker-end
    
2. På sidan **Domäner** väljer du din domän och sedan **Starta installationen.** Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.
    
3. På sidan **Verifiera domän** väljer du Lägg till **en TXT-post i stället** och välj sedan **Nästa.**
    
4. Kopiera **TXT-värdet som** visas. Så här ser det ut: **MS=msXXXXXXXX.** 
    
5. Gå till [Skapa DNS-poster](create-dns-records-at-any-dns-hosting-provider.md)hos en DNS-värd och välj din DNS-värd i listan med registratorer om du vill ha stegvisa anvisningar.
    
6. Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Microsoft 365.

7. Ta bort TXT-posten (eller MX-posten) från din DNS-värd när domänen har verifierats i Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Steg 2: Hitta MX-postvärdet för e-post och mycket mer

::: moniker range="o365-worldwide"

1. I Microsoft 365 administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.

::: moniker-end
    
::: moniker range="o365-germany"

1. I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Konfigurera</a> domäner.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **sidan** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Konfigurera</a> domäner.

::: moniker-end
    
2. Välj en domän på sidan **Domäner**. 
    
3. Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.
    
    Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.
    
    Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.
    
4. Gå till [Skapa DNS-poster](create-dns-records-at-any-dns-hosting-provider.md)hos en DNS-värd och välj sedan din DNS-värd i listan med registratorer om du vill se stegvisa instruktioner för hur du lägger till poster på DNS-värdens webbplats.
    
5. Följ stegen för att skapa posterna hos din DNS-värd.

## <a name="related-content"></a>Relaterat innehåll

[Vanliga frågor och svar](../setup/domains-faq.yml) om domäner (artikel)

[Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster](find-and-fix-issues.md) (artikel)

[Hantera domäner](index.yml) (länksida)