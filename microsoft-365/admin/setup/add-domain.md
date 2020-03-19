---
title: Lägga till en domän i Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Lägg till din domän i Office 365 i administrationscentret för Microsoft 365 genom att lägga till en DNS-post hos DNS-värden. Installationsguiden går igenom processen.
ms.openlocfilehash: 86ca8f986624ad37f780961cb58923ea0a1b2308
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857385"
---
# <a name="add-a-domain-to-office-365"></a>Lägga till en domän i Office 365

 **[Läs frågor och svar om domäner](domains-faq.md)** om du inte hittar det du letar efter. 
  
 *Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller ett [företagsabonnemang](https://products.office.com/business/office). Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*  

 Följ dessa steg för att lägga till, konfigurera eller fortsätta konfigurera en domän. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Gå till sidan **Inställningar** > **domäner.** 

3. Välj **Lägg till domän**.
    
4. Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.
    
5. Välj hur du vill verifiera att du äger domänen.
    
    1. Om domänen är registrerad hos&amp;GoDaddy eller 1 1 väljer du **Logga in** > **Nästa** och Office 365 [konfigurerar dina poster automatiskt](../get-help-with-domains/domain-connect.md).
    
    2. Du kan välja att ett e-postmeddelande ska skickas till den registrerade kontakten för domänen med en verifieringskod. Om du inte känner igen eller har tillgång till den registrerade e-postmeddelandet kan du använda det tredje alternativet.
    
    3. Du kan använda en TXT-post för att verifiera din domän. Välj detta och välj **Nästa** om du vill se instruktioner för hur du lägger till den här DNS-posten på registratorns webbplats. Det kan ta upp till 30 minuter att verifiera när du har lagt till posten. 
    
6. Välj hur du vill göra de DNS-ändringar som krävs för att Office ska kunna använda domänen.
    
    1. Välj **Lägg till DNS-posterna åt mig** om du vill att DNS ska konfigureras automatiskt. 
    
  
    2. **Välj Jag lägger till DNS-posterna själv** om du bara vill koppla specifika Office 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och göra detta senare. **Välj det här alternativet om du vet exakt vad du gör.**
    
7. Om du själv väljer att lägga till *DNS-poster* väljer du **Nästa** så visas en sida med alla poster som du behöver lägga till på din registratorwebbplats för att konfigurera domänen. 
    
  
  
    Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Kontrollera listan med [värdspecifika instruktioner](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
    
    Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
    
    Om du vill vänta till senare bläddrar du till botten och väljer **Hoppa över det här steget**.
    
8. Välj **Slut -** du är klar! 

## <a name="related-articles"></a>Relaterade artiklar

[Vanliga frågor och svar om domäner](domains-faq.md)

[Vad är en domän?](../get-help-with-domains/what-is-a-domain.md)

[Köpa ett domännamn i Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Konfigurera din domän (tjänstspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Få hjälp med Office 365-domäner](../get-help-with-domains/get-help-with-domains.yml)
