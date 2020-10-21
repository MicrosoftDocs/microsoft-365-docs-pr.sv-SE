---
title: Skapa DNS-poster på CloudFlare för Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på CloudFlare för Microsoft.
ms.openlocfilehash: 301ed156584d9a9a2b84b88db7d6969ade5b34a2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646157"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Skapa DNS-poster på CloudFlare för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Cloudflare är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.
  
När du har lagt till dessa poster på CloudFlare är din domän konfigurerad för att fungera med Microsoft 365-tjänster.
  
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för Cloudflare lade du till en domän med hjälp av Cloudflares **konfigurationsprocess**. 
  
Domänen som du lade till köptes från CloudFlare eller en separat domän registrator. Om du vill verifiera och skapa DNS-poster för din domän i Microsoft 365 måste du först ändra namnservrar hos domän registratorn så att de använder CloudFlare.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.
    
    |||
    |:-----|:-----|
    |Första namnservern  <br/> |Använd namnservervärdet från Cloudflare.  <br/> |
    |Andra namnservern  <br/> |Använd namnservervärdet från Cloudflare.  <br/> |
   
    > [!TIP]
    > Du bör använda minst två namnserver poster. Om det finns andra namnservrar angivna ska du ta bort dem. 
  
3. Spara ändringarna.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän. 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
  
2. På **Start** sidan väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för din domän.

  
4. Klicka på **Lägg till post**på sidan **DNS Management** och välj sedan värdena från följande tabell. 
    
    |**Type (typ)**|**Name (namn)**|**Automatic TTL (automatisk TTL)**|**Innehåll**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minuter  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Välj **Spara**.
  
  
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och söka efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
  
2. På **Start** sidan väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för din domän.

  
4. Klicka på **Lägg till post**på sidan **DNS Management** och välj sedan värdena från följande tabell. 
    
    |**Type (typ)**|**Namn**|**Mail server (postserver)**|**Prioritet**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft 365-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |9.1  <br/> [Mer information om prioritet finns i ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)Vad är MX-prioritet? <br/>|30 minuter  <br/> |
   

  
5. Välj **Spara**.
  
9. Om det finns andra MX-poster som i avsnittet **MX Records** (MX-poster) ska du ta bort alla genom att välja ikonen **Delete (X)** (ta bort (X)). 
  
10. Klicka på **ta bort** i bekräftelse dialog rutan för att bekräfta ändringarna. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
    
  
2. På **Start** sidan väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för din domän.

  
4. Lägg till den första av de fem CNAME-posterna.
    
    Klicka på **Lägg till post**på sidan **DNS Management** och välj sedan värdena från följande tabell.
    
    
    |**Type (typ)**|**Namn**|**Mål**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minuter  <br/> |
    
  
5. Välj ikonen för **DNS-trafik** (orange moln) för att kringgå CloudFlare-servrarna.
  
6. Välj **Spara**.
  
7. Lägg till de andra fem CNAME-posterna var för sig.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365. Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
    
  
2. På **Start** sidan väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för din domän.

  
4. Klicka på **Lägg till post**på sidan **DNS Management** och välj sedan värdena från följande tabell.  
    
    |**Type (typ)**|**Namn**|**TTL**|**Innehåll**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minuter  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.       |

 
5. Välj **Spara**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Kom ihåg att CloudFlare är ansvarigt för att göra denna funktion tillgänglig. Om du inte ser avvikelser mellan stegen nedan och det aktuella CloudFlare GUI (grafiskt användar gränssnitt) bör du använda [CloudFlare community](https://community.cloudflare.com/). 

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
      
2. På **Start** sidan väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för din domän.
  
4. Lägg till den första av de två SRV-posterna.

    Klicka på **Lägg till post**på sidan **DNS Management** och välj sedan värdena från den första raden i följande tabell.
        
    |**Type (typ)**|**Service (tjänst)**|**Protocol (protokoll)**|**Namn**|**TTL**|**Prioritet**|**Vikt**|**Port**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Använd din *domain_name*; till exempel contoso.com  |30 minuter | 100|9.1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Använd din *domain_name*; till exempel contoso.com   |30 minuter |100 |9.1 |5061 | sipfed.online.lync.com |

  
5. Välj **Spara**.

  
6. Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen. 

    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
