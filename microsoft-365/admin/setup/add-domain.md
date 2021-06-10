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
description: Använd installationsguiden för att lägga till din domän Microsoft 365 i Microsoft 365 genom att lägga till en DNS-post hos din DNS-värd.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635684"
---
# <a name="add-a-domain-to-microsoft-365"></a>Lägga till en domän i Microsoft 365

 **[Läs frågor och svar om domäner](domains-faq.yml)** om du inte hittar det du letar efter. 
  
 *Om du vill lägga till, ändra eller ta bort **domäner måste** du vara **global administratör** för ett [företags- eller företagsplan.](https://products.office.com/business/office) Dessa ändringar påverkar hela *klientorganisationen, anpassade* administratörer *eller vanliga* användare kommer inte att kunna göra dessa ändringar.*  

 ## <a name="add-a-domain"></a>Lägga till en domän

Följ de här anvisningarna om du vill lägga till, konfigurera eller fortsätta att konfigurera en domän. 

::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Gå till sidan **Inställningar**  >  **Domains.** 

3. Välj **Lägg till domän**.
    
4. Ange namnet på den domän som du vill lägga till och välj sedan **Nästa.**
    
5. Välj hur du vill verifiera att du äger domänen.
    
    1. Om din domänregistrator använder [Domain Anslut](#domain-connect-registrars-integrating-with-microsoft-365)konfigureras dina poster automatiskt av [Microsoft](../get-help-with-domains/domain-connect.md) genom att du loggar in på registratorn och bekräftar anslutningen till Microsoft 365. Du kommer tillbaka till administrationscentret och Microsoft verifierar sedan automatiskt din domän.
    2. Du kan använda en TXT-post för att verifiera din domän. Välj det här alternativet **och välj** Nästa för att se anvisningar för hur du lägger till DNS-posten på registratorns webbplats. Det kan ta upp till 30 minuter att verifiera detta när du har lagt till posten. 
    3. Du kan lägga till en textfil på webbplatsen för din domän. Välj och ladda .txt filen från installationsguiden och ladda sedan upp filen till webbplatsens toppnivåmapp. Sökvägen till filen bör se ut ungefär så här: `http://mydomain.com/ms39978200.txt` . Vi bekräftar att du äger domänen genom att leta reda på filen på webbplatsen.
    
6. Välj hur du vill göra de DNS-ändringar som krävs för att Microsoft ska kunna använda din domän.
    
    1. Välj **Add the DNS records for me** om din registrator har stöd för Domain [Anslut](#domain-connect-registrars-integrating-with-microsoft-365), så kommer [Microsoft](../get-help-with-domains/domain-connect.md) att konfigurera dina poster automatiskt genom att du loggar in på din registrator och bekräftar anslutningen till Microsoft 365.
    2. Välj **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later. **Välj det här alternativet om du vet exakt vad du gör.**

7. Om du väljer att lägga  till *DNS-poster* själv väljer du Nästa. Då visas en sida med alla poster som du behöver lägga till på domänregistratorns webbplats för att konfigurera domänen. 

    Om portalen inte känner igen din registrator kan du [följa de här allmänna anvisningarna.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Kontrollera listan med [värdspecifika instruktioner](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) för att hitta din värd och följ sedan anvisningarna för att lägga till alla posterna du behöver. 
    
    Om du inte känner till DNS-värden eller domänregistratorn för din domän kan du läsa [Hitta din domänregistrator eller DNS-värd](../get-help-with-domains/find-your-domain-registrar.md).
    
    Om du vill vänta till senare avmarkerar du antingen alla tjänster och  klickar på **Fortsätt,** eller så väljer du Fler alternativ i föregående domänanslutningssteg och väljer Hoppa över det **här tills vidare.**
    
8. Välj **Slutför** – nu är du klar!

## <a name="add-or-edit-custom-dns-records"></a>Lägga till eller redigera anpassade DNS-poster

Följ stegen nedan för att lägga till en anpassad post för en webbplats eller tredjepartstjänst.

1. Logga in på Microsofts administrationscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Gå till sidan **Inställningar**   >  **Domains.**

3. Välj en domän på sidan **Domäner**. 
    
4. Under **DNS-inställningar** väljer du **Anpassade poster**. välj sedan **Ny anpassad post**.

5. Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.
    
6. Välj **Spara**.

## <a name="registrars-with-domain-connect"></a>Registratorer med Anslut

[Domän Anslut](https://www.domainconnect.org/) domänregistratorer låter dig lägga till din domän Microsoft 365 i en trestegsprocess som bara tar några minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan konfigureras domänens poster automatiskt, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domän Anslut domänregistratorer som integrerar med Microsoft 365

- [1 &amp; 1 I ENTISKT](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Hannsk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-värd)
    - Exempel:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du är klar med konfigurationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för domänen börjar komma Microsoft 365. Kontrollera att du har lagt till användare och ställt in postlådor i Microsoft 365 för alla som får e-post på din domän!
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Domänkonfigurationsstegen Anslut påverkar inte din webbplats.

## <a name="related-content"></a>Relaterat innehåll

[Vanliga frågor och svar om domäner](domains-faq.yml) (artikel)\
[Vad är en domän?](../get-help-with-domains/what-is-a-domain.md) (artikel)\
[Köp ett domännamn i Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (artikel)\
[Konfigurera din domän](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (artikel)