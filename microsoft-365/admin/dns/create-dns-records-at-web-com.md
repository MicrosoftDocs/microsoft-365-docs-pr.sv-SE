---
title: Skapa DNS-poster på web.com för Microsoft
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
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på web.com för Microsoft.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629257"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Skapa DNS-poster på web.com för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om web.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.
  
När du har lagt till dessa poster i web.com konfigureras domänen så att den fungerar med Microsoft-tjänster.
  
Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för web.com har du lagt till en domän med hjälp av web.com **installationsprogrammet.** 
  
Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrarna på domänregistraren så att de använder web.coms namnservrar.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden.
    
    |||
    |:-----|:-----|
    |Första namnservern  <br/> |Använd namnservervärdet som anges av web.com.  <br/> |
    |Andra namnservern  <br/> |Använd namnservervärdet som anges av web.com.  <br/> |
   
    > [!TIP]
    > Du bör använda minst två namnserverposter. Om det finns några andra namnservrar i listan bör du ta bort dem. 
  
3. Spara ändringarna.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Då kommer din Microsoft-e-post och andra tjänster att vara inställda på att fungera med din domän. 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder domänen med Microsoft måste vi se till att du äger den. Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
  
2. Välj **Mina domännamn på**sidan **Kontohanteraren** . 
  
3. Under **Hantera *min domän***väljer du **Redigera avancerade DNS-poster**.

  
4. Klicka på **Redigera TXT-poster**under **Text (TXT-poster)** på sidan **Domännamn** och välj sedan värdena i följande tabell. 
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Välj **Fortsätt**.
  
  
6. Vänta några minuter innan du verifierar den nya TXT-posten, så att posten du just skapade kan uppdateras över Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post verifieras domänen.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägg till en MX-post så att e-post för din domän kommer till Microsoft
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
  
2. Välj **Mina domännamn på**sidan **Kontohanteraren** . 
  
3. Under **Hantera *min domän***väljer du **Redigera avancerade DNS-poster**.

4. Klicka på **Redigera MX-poster**under **E-postservrar (MX-poster)** och välj sedan värdena i följande tabell. 
    
    |**Prioritet**|**TTL**|**Mail server (postserver)**|
    |:-----|:-----|:-----|
    |1  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |3600  <br/> |*\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.   [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Välj **Spara**.
  
6. Om det finns andra MX-poster i avsnittet **MX-poster** markerar du kryssrutan bredvid posten under **Ta bort**och väljer **Spara**. 
  
7. Välj **Spara ändringar**på bekräftelseskärmen . 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp). Du uppmanas att logga in först.
     
2. Välj **Mina domännamn på**sidan **Kontohanteraren** . 
  
3. Under **Hantera *min domän***väljer du **Redigera avancerade DNS-poster**.

4. Lägg till den första av de sex CNAME-posterna.
    
    Klicka på **Redigera CNAME-poster** **under Värdalias (CNAME Records)** och välj sedan värdena i följande tabell.
    
    
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
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. 
  
1. Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
    
  
2. Välj **Mina domännamn på**sidan **Kontohanteraren** . 
  
3. Under **Hantera *min domän***väljer du **Redigera avancerade DNS-poster**.

  
4. Klicka på **Redigera TXT-poster**under **Text (TXT-poster)** på sidan **Domännamn** och välj sedan värdena i följande tabell.   
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.       |

 
5. Välj **Fortsätt**.

6. Välj **Spara ändringar**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägg till de två SRV-poster som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tänk på att web.com är ansvarig för att göra den här funktionen tillgänglig. Om du ser avvikelser mellan stegen nedan och den aktuella web.com GUI (Grafiskt användargränssnitt), vänligen utnyttja [web.com community](https://community.web.com.com/). 

1. Kom igång genom att gå till domänsidan på web.com med hjälp av [den här länken](https://checkout.web.com/manage-it/index.jsp). Logga in först.
      
2. Välj **Mina domännamn på**sidan **Kontohanteraren** . 
  
3. Under **Hantera *min domän***väljer du **Redigera avancerade DNS-poster**.
  
4. Lägg till den första av de två SRV-posterna.

    Klicka på **Redigera SRV-poster** **under Service (SRV Records)** och välj sedan värdena i följande tabell. 
        
    |**Service**|**Protocol**|**TTL**|**Prioritet**|**Vikt**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Lägg till den andra SRV-posten genom att välja värdena från den andra raden i tabellen. 
  
6. Välj **Fortsätt**.

7. Välj **Spara ändringar**.

    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
