---
title: Lägga till en domän i Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Lägg till din domän i Office 365 i Microsoft 365-administrationscentret genom att lägga till en DNS-post hos din DNS-värd. Installationsguiden går igenom processen.
ms.openlocfilehash: b5ad21174c0a2ebb3466072ef43fb1ba284d3b59
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398996"
---
# <a name="add-a-domain-to-microsoft-365"></a>Lägga till en domän i Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Läs frågor och svar om domäner](domains-faq.md)** om du inte hittar det du letar efter. 
  
 *Om du vill lägga till, ändra eller ta bort domäner **måste** du vara **global administratör för** ett företag eller en [företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela klienten, *anpassade administratörer* eller *vanliga användare* kan inte göra dessa ändringar.*  

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
    
2. Gå till sidan **Inställningar**  >  **domäner.** 

3. Välj **Lägg till domän**.
    
4. Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.
    
5. Välj hur du vill verifiera att du äger domänen.
    
    1. Om din domän är registrerad på GoDaddy eller 1 &amp; 1 väljer du **Logga in**  >  **nästa** så [konfigurerar](../get-help-with-domains/domain-connect.md)Microsoft dina poster automatiskt .
    
    2. Du kan välja att ett e-postmeddelande ska skickas till den registrerade kontakten för domänen med en verifieringskod. Om du inte känner igen eller har tillgång till e-postmeddelandet kan du använda det tredje alternativet.
    
    3. Du kan använda en TXT-post för att verifiera din domän. Välj det här och välj **Nästa** om du vill se instruktioner för hur du lägger till den här DNS-posten på registratorns webbplats. Det kan ta upp till 30 minuter att verifiera när du har lagt till posten. 
    
6. Välj hur du vill göra de DNS-ändringar som krävs för att Office ska kunna använda domänen.
    
    1. Välj **Lägg till DNS-posterna åt mig** om du vill att Dns ska konfigureras automatiskt. 
    
  
    2. Välj **Jag lägger till DNS-posterna själv** om du bara vill koppla specifika Office 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och göra detta senare. **Välj det här alternativet om du vet exakt vad du gör.**
    
7. Om du själv väljer att lägga till *DNS-poster* väljer du **Nästa** och du ser en sida med alla poster som du behöver lägga till på registrarernas webbplats för att konfigurera domänen. 
    
  
  
    Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Kontrollera listan med [värdspecifika instruktioner](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
    
    Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
    
    Om du vill vänta till senare bläddrar du längst ned och väljer **Hoppa över det här steget**.
    
8. Välj **Slutför** - du är klar! 

## <a name="add-or-edit-custom-dns-records"></a>Lägga till eller redigera anpassade DNS-poster

Följ stegen nedan för att lägga till en anpassad post för en webbplats eller tjänst från tredje part.

1. Logga in på Microsofts administrationscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till sidan **Inställningar**   >  **domäner.**

3. Välj en domän på sidan **Domäner**. 
    
4. Under **DNS-inställningar**väljer du **Anpassade poster.** välj sedan **Ny anpassad post**.

5. Välj den typ av DNS-post som du vill lägga till och skriv informationen för den nya posten.
    
6. Välj **Spara**.

## <a name="registrars-with-domain-connect"></a>Registratorer med Domain Connect

[Med Domain](https://www.domainconnect.org/) Connect-aktiverade registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, som Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-registratorer som integreras med Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg (På andra)](https://www.123-reg.co.uk/)
- [Godaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare med SecureServer DNS hosting)
    - [MadDog domäner](https://www.maddogdomains.com/)
    - [BilligaNamn](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du är klar med installationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för din domän börjar komma till Microsoft 365. Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Installationsstegen För Domain Connect påverkar inte din webbplats.

## <a name="related-articles"></a>Relaterade artiklar

[Vanliga frågor och svar om domäner](domains-faq.md)

[Vad är en domän?](../get-help-with-domains/what-is-a-domain.md)

[Köpa ett domännamn i Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Konfigurera din domän (tjänstspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Få hjälp med domäner](../get-help-with-domains/get-help-with-domains.md)
