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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Lär dig hur du hittar de värden du behöver för att skapa DNS-poster för Microsoft 365. '
ms.openlocfilehash: db9aff1fdcd9fa52c90cc96b1a32cd3908c30edb
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658513"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Samla den information du behöver för att skapa DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Steg 1: Sök efter TXT-Postens värde och bekräfta

::: moniker range="o365-worldwide"

1. Gå till sidan **konfigurations** domäner i administrations centret för Microsoft 365 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> .

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Konfigurera** domäner i administrations centret > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Konfigurera** domäner i administrations centret > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> .

::: moniker-end
    
2. På sidan **domäner** väljer du din domän och sedan **starta installationen**. Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.
    
3. På sidan **Verifiera domän** väljer du **Lägg till en TXT-post i stället** och sedan **Nästa**.
    
4. Kopiera det **txt-värde** som visas. Det ser ut så här: **MS = msXXXXXXXX**. 
    
5. Gå till [Skapa DNS-poster hos en DNS-värd](create-dns-records-at-any-dns-hosting-provider.md)och välj din DNS-värd i listan med registratorer för att se steg-för-steg-instruktionerna.
    
6. Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Microsoft 365.

7. Ta bort TXT-posten (eller MX-posten) från DNS-värden när domänen har verifierats i Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Steg 2: hitta MX-postvärdet för e-post och mer

::: moniker range="o365-worldwide"

1. Gå till sidan **konfigurations** domäner i administrations centret för Microsoft 365 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> .

::: moniker-end
    
::: moniker range="o365-germany"

1. Gå till sidan **Konfigurera** domäner i administrations centret > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Konfigurera** domäner i administrations centret > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> .

::: moniker-end
    
2. Välj en domän på sidan **Domäner**. 
    
3. Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.
    
    Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.
    
    Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.
    
4. Gå till [Skapa DNS-poster hos en DNS-värd](create-dns-records-at-any-dns-hosting-provider.md)och välj sedan din DNS-värd i listan över registratorer för att Visa stegvisa instruktioner för hur du lägger till poster på DNS-värdens webbplats.
    
5. Följ stegen för att skapa posterna hos din DNS-värd.
