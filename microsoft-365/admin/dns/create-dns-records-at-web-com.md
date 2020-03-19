---
title: Skapa DNS-poster på web.com för Office 365
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på web.com för Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806551"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a>Skapa DNS-poster på web.com för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om web.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag och så vidare.
  
När du har lagt till dessa poster på web.com konfigureras domänen så att den fungerar med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för web.com har du lagt till en domän med hjälp av web.com **installationsprocessen.** 
  
Om du vill verifiera och skapa DNS-poster för din domän i Office 365 måste du först ändra namnservrarna hos domänregistratorn så att de använder web.coms namnservrar.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.
    
    |||
    |:-----|:-----|
    |Första namnservern  <br/> |Använd namnet servervärdet som tillhandahålls av web.com.  <br/> |
    |Andra namnservern  <br/> |Använd namnet servervärdet som tillhandahålls av web.com.  <br/> |
   
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
  
1. Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
  
2. På sidan **Kontohanteraren** väljer du **Mina domännamn**. 
  
3. Välj **Redigera avancerade DNS-poster**under **Hantera **min domän***.under **Hantera **min domän****.

  
4. Klicka på **Redigera TXT-poster**under Text (TXT Records) på sidan **Domännamn** och välj sedan värdena i följande tabell under **Text (TXT Records)** och välj sedan värdena i följande tabell. 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Välj **Fortsätt**.
  
  
6. Vänta några minuter innan du verifierar den nya TXT-posten så att posten du just skapade kan uppdateras över Internet.
    
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

1. Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
  
2. På sidan **Kontohanteraren** väljer du **Mina domännamn**. 
  
3. Välj **Redigera avancerade DNS-poster**under **Hantera **min domän***.under **Hantera **min domän****.

4. Klicka på **Redigera MX Records**under **E-postservrar (MX Records)** och välj sedan värdena i följande tabell. 
    
    |**Priority**|**TTL**|**Mail server (postserver)**|
    |:-----|:-----|:-----|
    |1  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |3600  <br/> |*\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Obs:** Hämta din * \<domännyckel\> * från ditt Office 365-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Välj **Spara**.
  
6. Om det finns några andra MX-poster i avsnittet **MX Records** markerar du kryssrutan bredvid posten under **Ta bort**och väljer **Spara**. 
  
7. På bekräftelseskärmen väljer du **Spara ändringar**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Lägga till de sex CNAME-poster som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

1. Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp). Du uppmanas att logga in först.
     
2. På sidan **Kontohanteraren** väljer du **Mina domännamn**. 
  
3. Välj **Redigera avancerade DNS-poster**under **Hantera **min domän***.under **Hantera **min domän****.

4. Lägg till den första av de sex CNAME-posterna.
    
    Klicka på **Redigera CNAME-poster**under **Värdalias (CNAME Records)** och välj sedan värdena i följande tabell.
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Annan värd**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (ingen)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (ingen)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (ingen)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (ingen)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (ingen)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (ingen)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Välj **Fortsätt**.
  
6. Lägg till de andra fem CNAME-posterna var för sig.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
    
  
2. På sidan **Kontohanteraren** väljer du **Mina domännamn**. 
  
3. Välj **Redigera avancerade DNS-poster**under **Hantera **min domän***.under **Hantera **min domän****.

  
4. Klicka på **Redigera TXT-poster**under Text (TXT Records) på sidan **Domännamn** och välj sedan värdena i följande tabell under **Text (TXT Records)** och välj sedan värdena i följande tabell.   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.       |

 
5. Välj **Fortsätt**.

6. Välj **Spara ändringar**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tänk på att web.com är ansvarig för att göra den här funktionen tillgänglig. Om du ser avvikelser mellan stegen nedan och det aktuella web.com GUI(Grafiskt användargränssnitt) kan du utnyttja [web.com community](https://community.web.com.com/). 

1. Gå till domänsidan på web.com genom att använda [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
      
2. På sidan **Kontohanteraren** väljer du **Mina domännamn**. 
  
3. Välj **Redigera avancerade DNS-poster**under **Hantera **min domän***.under **Hantera **min domän****.
  
4. Lägg till den första av de två SRV-posterna.

    Under **Service (SRV Records)** klickar du på **Redigera SRV Records**och väljer sedan värdena i följande tabell. 
        
    |**Service**|**Protocol**|**TTL**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen. 
  
6. Välj **Fortsätt**.

7. Välj **Spara ändringar**.

    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
