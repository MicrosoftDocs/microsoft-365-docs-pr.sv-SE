---
title: Lägga till en domän i Microsoft 365
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
description: Lägga till din domän i Microsoft 365 i Microsoft 365 Admin Center genom att lägga till en DNS-post hos din DNS-värd. Installations guiden hjälper dig genom processen.
ms.openlocfilehash: 3da99644f339eac2db6f1904e4eb50a7f584bc80
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315723"
---
# <a name="add-a-domain-to-microsoft-365"></a>Lägga till en domän i Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

 **[Läs frågor och svar om domäner](domains-faq.md)** om du inte hittar det du letar efter. 
  
 *För att lägga till, ändra eller ta bort domäner **måste** du vara **Global administratör** för [företags-eller företags abonnemang](https://products.office.com/business/office). Dessa ändringar påverkar hela klient organisationen, *anpassade administratörer* eller *vanliga användare* kommer inte att kunna göra dessa ändringar.*  

 Följ de här anvisningarna för att lägga till, konfigurera eller fortsätta konfigurera en domän. 

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
    
2. Gå till sidan **Inställningar**-  >  **domäner** . 

3. Välj **Lägg till domän**.
    
4. Ange namnet på den domän som du vill lägga till och välj sedan **Nästa**.
    
5. Välj hur du vill verifiera att du äger domänen.
    
    1. Om domän registratorn använder [domän Anslut](#domain-connect-registrars-integrating-with-microsoft-365)väljer du **Logga in på**  >  **Nästa** och Microsoft registrerar [dina poster automatiskt](../get-help-with-domains/domain-connect.md).
    
    2. Du kan välja att ett e-postmeddelande ska skickas till den registrerade kontakten för domänen med en verifieringskod. Om du inte känner igen eller har åtkomst till e-postmeddelandet i posten kan du använda det tredje alternativet.
    
    3. Du kan använda en TXT-post för att verifiera din domän. Välj det här alternativet och välj **Nästa** för att Visa anvisningar för hur du lägger till den här DNS-posten på din registrators webbplats. Det kan ta upp till 30 minuter innan du har lagt till posten. 

    4. Du kan lägga till en textfil till din domäns webbplats. Välj och ladda ner txt-filen från installations guiden och ladda upp filen till webbplatsen på den översta nivån. Sökvägen till filen bör se ut ungefär så här: `http://mydomain.com/ms39978200.txt` . Vi bekräftar att du äger domänen genom att hitta filen på webbplatsen.
    
6. Välj hur du vill göra de DNS-ändringar som krävs för att Office ska kunna använda domänen.
    
    1. Välj **Lägg till DNS-posterna åt mig** om du vill att Office ska konfigurera DNS automatiskt. 
    
  
    2. Välj **jag lägger till DNS-posterna själv** om du bara vill bifoga specifika Microsoft 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och gör det senare. **Välj det här alternativet om du vet exakt vad du gör.**
    
7. Om du väljer att  *lägga till DNS-poster själv*  väljer du **Nästa** så visas en sida med alla de poster du behöver lägga till på webbplatsen för registratorer för att konfigurera din domän. 
    
  
  
    Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Kontrollera listan med [värdspecifika instruktioner](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
    
    Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
    
    Om du vill vänta senare bläddrar du längst ned och väljer **hoppa över det här steget**.
    
8. Välj **finish** – nu är du klar! 

## <a name="add-or-edit-custom-dns-records"></a>Lägga till eller redigera anpassade DNS-poster

Följ stegen nedan om du vill lägga till en anpassad post för en webbplats eller tredje parts tjänst.

1. Logga in på administrations centret för Microsoft på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till sidan **Inställningar**-   >  **domäner** .

3. Välj en domän på sidan **Domäner**. 
    
4. Välj **anpassade poster**under **DNS-inställningar**. Välj sedan **ny anpassad post**.

5. Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.
    
6. Välj **Spara**.

## <a name="registrars-with-domain-connect"></a>Registratorer med domän anslutning

Med [domän Connect-reservdomänkontrollanter](https://www.domainconnect.org/) kan du lägga till din domän i Microsoft 365 i en tre stegs process som tar minuter. 
  
I guiden bekräftar vi bara att du äger domänen och registrerar sedan automatiskt domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domän anslutnings registratorer som integreras med Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [CloudFlare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy åter försäljare med SecureServer DNS-värd)
    - [MadDog-domäner](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du har slutfört installationen uppdateras MX-posten för domänen så att den pekar på Microsoft 365 och alla e-postmeddelanden för domänen kommer att komma till Microsoft 365. Kontrol lera att du har lagt till användare och konfigurerat post lådor i Microsoft 365 för alla som får e-post på din domän!
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Anvisningarna för att konfigurera domänen påverkar inte din webbplats.

## <a name="related-articles"></a>Relaterade artiklar

[Vanliga frågor och svar om domäner](domains-faq.md)

[Vad är en domän?](../get-help-with-domains/what-is-a-domain.md)

[Köpa ett domännamn i Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Konfigurera din domän (tjänstspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
