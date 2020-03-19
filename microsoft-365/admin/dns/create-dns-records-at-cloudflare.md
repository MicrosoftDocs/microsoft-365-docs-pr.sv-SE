---
title: Skapa DNS-poster för Office 365 hos Cloudfare
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
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Cloudflare för Office 365.
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810824"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a>Skapa DNS-poster för Office 365 hos Cloudfare

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Cloudflare är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.
  
När du har lagt till dessa poster i Cloudflare är domänen konfigurerad för att fungera med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för Cloudflare lade du till en domän med hjälp av Cloudflares **konfigurationsprocess**. 
  
Den domän du lade till har köpts från en separat domänregistrator. Cloudflare erbjuder inte tjänster för domänregistrering. Om du vill verifiera och skapa DNS-poster för din domän i Office 365, måste du ändra namnservrarna hos domänregistratorn så att de använder Cloudflares namnservrar.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.
    
    |||
    |:-----|:-----|
    |Första namnservern  <br/> |Använd namnservervärdet från Cloudflare.  <br/> |
    |Andra namnservern  <br/> |Använd namnservervärdet från Cloudflare.  <br/> |
   
    > [!TIP]
    > Du bör använda minst två namnserverposter. Om det finns några andra namnservrar i listan bör du ta bort dem. 
  
3. Spara ändringarna.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
  
2. På **startsidan** väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för domänen.

  
4. Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell. 
    
    |**Type (typ)**|**Name (namn)**|**Automatic TTL (automatisk TTL)**|**Innehåll**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minuter  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Välj **Spara**.
  
  
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>

    
2. På sidan **Domäner** väljer du den domän som du verifierar. 
    
    
  
3. På **sidan Inställningar** väljer du **Starta installationsprogrammet**.
    
    
  
4. Välj **Verifiera**på **sidan Verifiera domän.**
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
  
2. På **startsidan** väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för domänen.

  
4. Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell. 
    
    |**Type (typ)**|**Namn**|**Mail server (postserver)**|**Priority (prioritet)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Obs:** Hämta din * \<domännyckel\> * från ditt Office 365-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> [Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet? <br/>|30 minuter  <br/> |
   

  
5. Välj **Spara**.
  
9. Om det finns andra MX-poster som i avsnittet **MX Records** (MX-poster) ska du ta bort alla genom att välja ikonen **Delete (X)** (ta bort (X)). 
  
10. Välj **Ta bort** i bekräftelsedialogrutan för att bekräfta ändringarna. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Lägga till de sex CNAME-poster som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
    
  
2. På **startsidan** väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för domänen.

  
4. Lägg till den första av de fem CNAME-posterna.
    
    Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.
    
    
    |**Type (typ)**|**Namn**|**Target (mål)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minuter  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minuter  <br/> |
    
  
5. Välj **ikonen DNS Traffic** (orange moln) för att kringgå Cloudflare-servrarna.
  
6. Välj **Spara**.
  
7. Lägg till de andra fem CNAME-posterna var för sig.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
    
  
2. På **startsidan** väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för domänen.

  
4. Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena i följande tabell.  
    
    |**Typ**|**Namn**|**TTL**|**Innehåll**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minuter  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.       |

 
5. Välj **Spara**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tänk på att Cloudflare ansvarar för att göra den här funktionen tillgänglig. Om du ser avvikelser mellan stegen nedan och det aktuella Cloudflare GUI(Graphical User Interface) kan du utnyttja [Cloudflare-communityn](https://community.cloudflare.com/). 

1. Kom igång genom att gå till domänsidan på Cloudflare genom att klicka på [den här länken](https://www.cloudflare.com/a/login). Du uppmanas att logga in först.
      
2. På **startsidan** väljer du den domän som du vill uppdatera. 
  
3. Välj **DNS**på sidan **Översikt** för domänen.
  
4. Lägg till den första av de två SRV-posterna.

    Klicka på **Lägg till post**på sidan **DNS-hantering** och välj sedan värdena från den första raden i följande tabell.
        
    |**Type (typ)**|**Service (tjänst)**|**Protocol (protokoll)**|**Namn**|**TTL**|**Priority**|**Weight**|**Port**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Använd din *domain_name;* till exempel contoso.com  |30 minuter | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Använd din *domain_name;* till exempel contoso.com   |30 minuter |100 |1 |5061 | sipfed.online.lync.com |

  
5. Välj **Spara**.

  
6. Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen. 

    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
