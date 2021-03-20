---
title: Utföra ett internt administratörsupptagande
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Lär dig hur du verifierar e-post- och domänägarskap för att ta över en ohanterad klientorganisation i Microsoft 365
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914852"
---
# <a name="perform-an-internal-admin-takeover"></a>Utföra ett internt administratörsupptagande

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 

Om du är administratör och vill ta över en ohanterad klientorganisation som skapas genom registrering av självbetjäning kan du göra detta med ett internt administratörsköp.

> [!NOTE]
> Om du registrerar dig som självbetjäning för en molntjänst som använder Azure AD kommer användaren att läggas till i en ohanterad eller "skuggig" Azure AD-katalog och en ohanterad klientorganisation skapas. En ohanterad klientorganisation är en katalog utan global administratör. Information om huruvida en klientorganisation hanteras eller hanteras utan avbrott finns i [Fastställa klientorganisationstyp.](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>Steg 1: Verifiera din e-postadress

> [!NOTE]
> Om självbetjäning är aktiverad i klientorganisationen kan användarna prenumerera på kostnadsfria tjänster, till exempel Power BI, på egen hand. De här stegen förutsätter att en användarprenumeration med självbetjäning har skapat den ohanterade klientorganisationen som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterade klientorganisationen, med Power BI för att illustrera administratörsupptagandets väg.

1. Registrera dig för Power BI genom att gå till [Power BI-webbplatsen](https://powerbi.com) och välja Starta kostnadsfri start gratis provperiod (i rutan Dela med Power  >   BI Pro). 

2. Registrera dig med ett användarkonto som använder domännamnet för din organisation (t.ex. `powerbiadmin@contoso.com` ). Om ditt konto redan används loggar du in med ditt nuvarande lösenord.

3. Kontrollera din e-postadress **för verifieringskoden** och ange koden för att verifiera din e-postadress.
    
## <a name="step-2-create-a-new-account"></a>Steg 2: Skapa ett nytt konto

1. När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto. 
    
2. Fyll i användarnamns- och lösenordsfälten med det konto som du vill använda och välj sedan **Starta.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Steg 3: Verifiera att du äger domänen och bli administratör

1. Guiden **Bli administratör** öppnas. Om guiden inte startar letar du upp panelen **Admin** och väljer den. 

2. Välj **Ja, jag vill vara administratör.**

3. Verifiera att du äger den domän du vill ta över genom att lägga till en TXT-post i din domänregistrator. Guiden ger dig TXT-posten att lägga till, samt en länk till din registrators webbplats samt en länk till stegvisa instruktioner.
    
4. När du har lagt till TXT-posten på registratorns webbplats går du tillbaka till guiden och väljer **Okej, jag har lagt till posten**.
    
> [!NOTE]
> Att ta över skuggklientorganisationen påverkar inte befintlig information eller befintliga tjänster. Men om några användare i domänen har registrerat sig för tjänster som kräver en licens uppmanas du att köpa licenser till dem när du tar över administratörsrollen. Du kan köpa eller ta bort licenser när administratörsinstallationen är klar.
  
## <a name="related-articles"></a>Relaterade artiklar

YouTube: [3 steg för att göra ett övertagande av IT-administratörer för Power BI och Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Administratörsupptagande i Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Använda självbetjäning för registrering i din organisation](self-service-sign-up.md)
  
[Förstå administratörsrollen i Power BI-tjänsten](/power-bi/service-admin-role)