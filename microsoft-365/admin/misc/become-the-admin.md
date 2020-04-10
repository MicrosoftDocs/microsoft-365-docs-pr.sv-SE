---
title: Utföra ett internt administrationsövertagande i Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
description: Läs om hur du verifierar din e-post och domänägarskap för att ta över en ohanterat klientorganisation i Office 365
ms.openlocfilehash: 3c732d55c533c72983aaa59e39e7bb8ff130f280
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212251"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a>Utföra ett internt administrationsövertagande i Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 

Om du är administratör och vill ta över en ohanterlig klient som skapats av en självbetjäningsanvändaranst registrering kan du göra detta med ett internt administrationsövertagande.

> [!NOTE]
> En självbetjäningslogga för alla molntjänster som använder Azure AD lägger till användaren i en ohanterad eller "skugga" Azure AD-katalog och skapar en ohanterad klientorganisation. En ohanterat klient är en katalog utan global administratör. Information om huruvida en klient hanteras eller inte hanteras finns i [Bestämma klienttyp](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Steg 1: Verifiera din e-postadress

> [!NOTE]
> Om självbetjäning är aktiverat i din klientorganisation kan användare prenumerera på kostnadsfria tjänster, till exempel Power BI, på egen hand. De här stegen förutsätter att en självbetjäningsanvändarprenumeration har skapat den ohanterat klient som du vill ta över som administratör. I det första steget skapar du en användarkontext i den ohanterat klienten med Power BI för att illustrera sökvägen till administration.

1. Om du vill registrera dig för Power BI går du till [Power BI-webbplatsen](https://powerbi.com) och väljer **Startfri** > **startfri utvärderingsversion** (i rutan Dela med Power BI Pro). 

2. Registrera dig med ett användarkonto som använder domännamnet `powerbiadmin@contoso.com`för din organisation (till exempel ). Om ditt konto redan används loggar du in med ditt nuvarande lösenord.

3. Kontrollera din e-post för **verifieringskoden** och ange koden för att validera din e-postadress.
    
## <a name="step-2-create-a-new-account"></a>Steg 2: Skapa ett nytt konto

1. När du anger verifieringskoden kommer du till en sida där du kan skapa ett nytt konto. 
    
2. Fyll i användarnamn och lösenord med det konto som du vill använda och välj sedan **Start**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Steg 3: Verifiera domänägarskap och bli administratör

1. Guiden **Bli administratör** öppnas. Om guiden inte startar letar du efter panelen **Admin** och väljer den. 

2. Välj **Ja, jag vill vara administratör**.

3. Kontrollera att du äger den domän som du vill ta över genom att lägga till en TXT-post i domänregistratorern. Guiden ger dig TXT-posten att lägga till, samt ger en länk till din registrators webbplats och en länk till steg-för-steg-instruktioner.
    
4. När du har lagt till TXT-posten på din registratorswebbplats går du tillbaka till guiden och väljer **Okej, jag har lagt till posten**.
    
> [!NOTE]
> Att ta över skuggklienten påverkar inte befintlig information eller tjänster. Om några användare i domänen har registrerat sig för tjänster som kräver en licens blir du ombedd att köpa licenser för dem som en del av att ta över administratörsrollen. Du kan lägga till eller ta bort licenser när administratörsinstallationen är klar. 
  
## <a name="related-articles"></a>Relaterade artiklar

YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Admin övertagande i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Få hjälp med Office 365-domäner](../get-help-with-domains/get-help-with-domains.md)

[Använda självbetjäningsanmäla i din organisation](self-service-sign-up.md)
  
[Förstå rollen power bi-tjänstadministratör](https://docs.microsoft.com/power-bi/service-admin-role)

