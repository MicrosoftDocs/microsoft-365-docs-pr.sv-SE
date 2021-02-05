---
title: Lägga till en domän i Microsoft 365
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
description: Lägg till din domän i Microsoft 365 i administrationscentret för Microsoft 365 genom att lägga till en DNS-post hos din DNS-värd. Installationsguiden hjälper dig genom processen.
ms.openlocfilehash: 5a3c86fb2b2f93e9da844c15a55555c5d0d7b5c1
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114267"
---
# <a name="add-a-domain-to-microsoft-365"></a>Lägga till en domän i Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

 **[Läs frågor och svar om domäner](domains-faq.yml)** om du inte hittar det du letar efter. 
  
 *Om du vill lägga till, ändra eller ta bort **domäner** måste du **vara global administratör** för ett [företags- eller företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela *klientorganisationen, anpassade* administratörer *eller vanliga* användare kommer inte att kunna göra de här ändringarna.*  

 Följ de här anvisningarna om du vill lägga till, konfigurera eller fortsätta att konfigurera en domän. 

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
    
2. Gå till sidan **Settings**  >  **Domains.** 

3. Välj **Lägg till domän.**
    
4. Ange namnet på den domän som du vill lägga till och välj sedan **Nästa.**
    
5. Välj hur du vill verifiera att du äger domänen.
    
    1. Om din domänregistrator använder [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365)kommer [Microsoft](../get-help-with-domains/domain-connect.md) att konfigurera posterna automatiskt genom att du loggar in på din registrator och bekräftar anslutningen till Microsoft 365. Du kommer tillbaka till administrationscentret och Microsoft verifierar sedan din domän automatiskt.
    2. Du kan använda en TXT-post för att verifiera din domän. Välj det här alternativet och **välj** Nästa om du vill ha anvisningar för hur du lägger till DNS-posten på registratorns webbplats. Det kan ta upp till 30 minuter att verifiera detta när du har lagt till posten. 
    3. Du kan lägga till en textfil på webbplatsen för din domän. Välj och ladda ned TXT-filen från installationsguiden och ladda sedan upp filen till webbplatsens mapp på översta nivån. Sökvägen till filen bör se ut ungefär så här: `http://mydomain.com/ms39978200.txt` . Vi bekräftar att du äger domänen genom att hitta filen på din webbplats.
    
6. Välj hur du vill göra de DNS-ändringar som krävs för att Microsoft ska kunna använda din domän.
    
    1. Välj **Lägg till DNS-poster** åt mig om registratorn stöder [Domain Connect.](#domain-connect-registrars-integrating-with-microsoft-365) [Microsoft](../get-help-with-domains/domain-connect.md) konfigurerar posterna automatiskt genom att du loggar in på din registrator och bekräftar anslutningen till Microsoft 365.
    2. Välj **Jag lägger till DNS-posterna** själv om du vill bifoga endast vissa Microsoft 365-tjänster till din domän eller om du vill hoppa över detta för tillfället och göra det senare. **Välj det här alternativet om du vet exakt vad du gör.**

7. Om du väljer att lägga  till *DNS-poster* själv väljer du Nästa så visas en sida med alla poster som du måste lägga till på domänregistratorns webbplats för att konfigurera din domän. 

    Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Kontrollera listan med [värdspecifika instruktioner](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
    
    Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
    
    Om du vill vänta till senare avmarkerar du antingen alla tjänster och  klickar på **Fortsätt,** eller så väljer du Fler alternativ i föregående domänanslutningssteg och väljer Hoppa över det **här tills vidare.**
    
8. Välj **Slutför** – nu är du klar!

## <a name="add-or-edit-custom-dns-records"></a>Lägga till eller redigera anpassade DNS-poster

Följ stegen nedan för att lägga till en anpassad post för en webbplats eller tredjepartstjänst.

1. Logga in på Administrationscenter för Microsoft på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till sidan **Settings**   >  **Domains.**

3. Välj en domän på sidan **Domäner**. 
    
4. Välj **Anpassade poster** under **DNS-inställningar.** och välj **sedan Ny anpassad post.**

5. Välj den typ av DNS-post du vill lägga till och skriv informationen för den nya posten.
    
6. Välj **Spara**.

## <a name="registrars-with-domain-connect"></a>Domänregistratorer med Domain Connect

[Domänaktiverade](https://www.domainconnect.org/) domänregistratorer låter dig lägga till din domän i Microsoft 365 i en trestegsprocess som bara tar några minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan konfigureras domänens poster automatiskt, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, t.ex. Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domän connect-domänregistratorer som integrerar med Microsoft 365

- [1 &amp; 1 I UPP TILL 6](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Så här ser det ut](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS hosting)
    - Exempel:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du är klar med konfigurationen uppdateras MX-posten för domänen så att den pekar på Microsoft 365 och all e-post för domänen börjar komma till Microsoft 365. Kontrollera att du har lagt till användare och konfigurerat postlådor i Microsoft 365 för alla som får e-post på din domän!
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Konfigurationsstegen för Domain Connect påverkar inte din webbplats.

## <a name="related-articles"></a>Relaterade artiklar

[Vanliga frågor och svar om domäner](domains-faq.yml)

[Vad är en domän?](../get-help-with-domains/what-is-a-domain.md)

[Köpa ett domännamn i Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Konfigurera din domän (tjänstspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
