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
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256849"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Samla den information du behöver för att skapa DNS-poster

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Steg 1: Hitta TXT-postvärdet och verifiera

::: moniker range="o365-worldwide"

1. I Administrationscenter för Microsoft 365 går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a>

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
2. På sidan **Domäner** väljer du din domän och sedan **Starta installationen.** Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.
    
3. På sidan **Domain Verification** väljer du Add a TXT record to **the domain's DNS records** och väljer sedan **Continue**.
    
4. Kopiera **TXT-värdet som** visas. Så här ser det ut: **MS=msXXXXXXXX.** 
    
5. Gå till [Lägg till DNS-poster för att](create-dns-records-at-any-dns-hosting-provider.md)ansluta din domän och följ anvisningarna för att lägga till poster på DNS-värdens webbplats.
    
6. Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Microsoft 365.

7. Ta bort TXT-posten (eller MX-posten) från din DNS-värd när domänen har verifierats i Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Steg 2: Hitta MX-postvärdet för e-post och mycket mer

::: moniker range="o365-worldwide"

1. I Administrationscenter för Microsoft 365 går du till sidan **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains.</a>

::: moniker-end
    
::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
2. Välj en domän på sidan **Domäner**.
    
3. Välj **Manage DNS**, select More Options **Add** your own  >  **DNS** and select Continue **to** see the DNS records to add.
    
    Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.
    
    Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.
    
4. Gå till [Lägg till DNS-poster för att](create-dns-records-at-any-dns-hosting-provider.md)ansluta din domän och följ anvisningarna för att lägga till poster på DNS-värdens webbplats.

5. Följ stegen för att skapa posterna hos din DNS-värd.

## <a name="related-content"></a>Relaterat innehåll

[Vanliga frågor och svar om domäner](../setup/domains-faq.yml) (artikel)\
[Hitta och åtgärda problem när du har lagt till din domän eller DNS-register](find-and-fix-issues.md) (artikel)\
[Hantera domäner](index.yml) (länksida)