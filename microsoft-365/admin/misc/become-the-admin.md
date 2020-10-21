---
title: Utföra en intern administrativ övertag Ande
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
description: Lär dig hur du verifierar din e-post och domän ägarskap för att ta över en ohanterad klient organisation i Microsoft 365
ms.openlocfilehash: 9ae09a4b88887664a0615128bcddc48ad6f57118
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645065"
---
# <a name="perform-an-internal-admin-takeover"></a>Utföra en intern administrativ övertag Ande

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 

Om du är administratör och vill ta över en ohanterad klient organisation som skapats av en självbetjänings användar registrering kan du göra det med en intern administratörs övertag Ande.

> [!NOTE]
> Ett själv underhåll för alla moln tjänster som använder Azure AD lägger till användaren i en ohanterad eller "skugg" Azure AD-katalog och skapar en ohanterad klient organisation. En ohanterad klient organisation är en katalog utan global administratör. För att avgöra om en klient organisation är hanterad eller ohanterad, se kontrol lera [klient organisations typ](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Steg 1: bekräfta din e-postadress

> [!NOTE]
> Om själv service är aktiverat i din klient organisation kan användare abonnera på gratis tjänster, till exempel Power BI, på egen hand. De här stegen förutsätter att en självbetjänings användar prenumeration har skapat den ohanterade klient organisation som du vill ta över som administratör. I det första steget skapar du en användar kontext i den ohanterade innehavaren med Power BI för att illustrera administratörs upptagnings vägen.

1. Registrera dig för Power BI genom att gå till [Power BI-webbplatsen](https://powerbi.com) och välja **Starta**gratis  >  **prov period** (i dela med Power BI Pro). 

2. Registrera dig med ett användar konto som använder organisationens domän namn (till exempel `powerbiadmin@contoso.com` ). Om ditt konto redan används loggar du in med ditt nuvarande lösen ord.

3. Kontrol lera e-postmeddelandet **och ange koden för** att verifiera din e-postadress.
    
## <a name="step-2-create-a-new-account"></a>Steg 2: skapa ett nytt konto

1. När du anger verifierings koden kommer du till en sida där du kan skapa ett nytt konto. 
    
2. Fyll i fälten användar namn och lösen ord med det konto som du vill använda och välj sedan **Starta**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Steg 3: bekräfta domän ägandet och bli administratör

1. Då öppnas **Administratörs** guiden. Om guiden inte startar letar du reda på panelen **Administratörer** och väljer den. 

2. Välj **Ja, jag vill vara administratör**.

3. Verifiera att du äger den domän som du vill ta med genom att lägga till en TXT-post i domän registratorn. Guiden ger dig TXT-posten att lägga till samt en länk till registratorns webbplats samt en länk till steg-för-steg-instruktioner.
    
4. När du har lagt till TXT-posten på din registrators webbplats går du tillbaka till guiden och väljer **OK, jag har lagt till posten**.
    
> [!NOTE]
> Att ta över skugg klient organisationen påverkar inte befintliga uppgifter eller tjänster. Om en användare i domänen har registrerat sig för tjänster som kräver en licens uppmanas du att köpa licenser för dem som en del av att ta över administratörs rollen. Du kan köpa eller ta bort licenser när administratörs konfigurationen är klar.
  
## <a name="related-articles"></a>Relaterade artiklar

YouTube: [3 steg för att utföra en IT-administratörs övertag Ande för Power BI och Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Administratörs övertag Ande i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Använda automatisk registrering i din organisation](self-service-sign-up.md)
  
[Förstå administratörs rollen för Power BI-tjänsten](https://docs.microsoft.com/power-bi/service-admin-role)

