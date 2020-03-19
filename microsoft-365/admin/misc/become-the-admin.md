---
title: Utföra ett internt administratörsövertagande i Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Lär dig hur du verifierar din e-postadress och domänägarskap att ta över en ohanterad klientorganisation i Office 365
ms.openlocfilehash: 0f7932b9ba727db62f81ac15b99a5f5ca276f09f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857409"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a>Utföra ett internt administratörsövertagande i Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 

Om du är administratör och vill ta över en ohanterad klient som skapats av en självbetjäningsanvändare registrering, kan du göra detta med en intern administratör övertagande.

> [!NOTE]
> En självbetjäningsregistrering för alla molntjänster som använder Azure AD kommer att lägga till användaren i en ohanterad eller "skugga" Azure AD-katalog och skapa en ohanterad klientorganisation. En ohanterad klient är en katalog utan en global administratör. Information om huruvida en klient hanteras eller inte hanteras finns [i Bestämma klienttyp](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Steg 1: Verifiera din e-postadress

> [!NOTE]
> Om självbetjäning är aktiverat i din klientkan användarna prenumerera på kostnadsfria tjänster, till exempel Power BI, på egen hand. De här stegen förutsätter att en självbetjäningsanvändarprenumeration har skapat den ohanterade klientorganisation som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterade klienten med Power BI för att illustrera sökvägen för övertagande av administratörer.

1. Om du vill registrera dig för Power BI går du till [Power BI-webbplatsen](https://powerbi.com) och väljer **Start gratis** > **startgratis provversion** (i rutan Dela med Power BI Pro). 

2. Registrera dig med ett användarkonto som använder organisationens `powerbiadmin@contoso.com`domännamn (t.ex. ). Om ditt konto redan används loggar du in med ditt nuvarande lösenord.

3. Kontrollera din e-post för **verifieringskoden** och ange koden för att validera din e-postadress.
    
## <a name="step-2-create-a-new-account"></a>Steg 2: Skapa ett nytt konto

1. När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto. 
    
2. Fyll i fälten användarnamn och lösenord med det konto som du vill använda och välj sedan **Start**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Steg 3: Verifiera domänägarskap och bli administratör

1. Guiden **Bli administratör** öppnas. Om guiden inte startar letar du efter **panelen Admin** och markerar den. 

2. Välj **Ja, jag vill vara admin**.

3. Kontrollera att du äger den domän som du vill ta över genom att lägga till en TXT-post i domänregistratorn. Guiden ger dig TXT-posten att lägga till, samt ger en länk till registratorns webbplats och en länk till steg-för-steg-instruktioner.
    
4. När du har lagt till TXT-posten på din registratorwebbplats, gå tillbaka till guiden och välj **Okej, jag har lagt till posten**.
    
> [!NOTE]
> Att ta över skuggklienten påverkar inte befintlig information eller tjänster. Om några användare i domänen har registrerat sig för tjänster som kräver en licens blir du dock ombedd att köpa licenser för dem som en del av att ta över administratörsrollen. Du kan lägga till eller ta bort licenser när administratörsinstallationen är klar. 
  
## <a name="related-articles"></a>Relaterade artiklar

YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Övertagande av administratörer i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Få hjälp med Office 365-domäner](../get-help-with-domains/get-help-with-domains.yml)

[Använda självbetjäningsregistrering i organisationen](self-service-sign-up.md)
  
[Förstå rollen power BI-tjänstadministratör](https://docs.microsoft.com/power-bi/service-admin-role)

