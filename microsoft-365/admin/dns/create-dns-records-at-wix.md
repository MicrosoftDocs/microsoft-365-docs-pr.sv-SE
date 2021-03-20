---
title: Skapa DNS-poster på Wix för Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster hos Wix för Microsoft.
ms.openlocfilehash: 3ec2ea0dc24e1872ba22e591fae96b39a9a0deee
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916112"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Skapa DNS-poster på Wix för Microsoft

**[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.

Det här är de viktigaste posterna att lägga till. 
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägg till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Lägg till de fem CNAME-posterna som krävs för Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägg till de två SRV-posterna som krävs för Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster på Wix är domänen konfigurerad för att fungera med Microsoft-tjänster.
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_txt"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 

> [!NOTE]
> WIX stöder inte DNS-poster för underdomäner.
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner). 
    
3. Välj **+ Add another (lägg** till ytterligare en) på raden TXT **(Text)** i DNS-redigeraren. 
    
4. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
   ||||
   |:-----|:-----|:-----|
   | Host Name <br/> | TXT Value <br/> | TTL <br/> |
   |Fylls i automatiskt  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)|1 timme <br/> |          |
   
5. Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
  
3. På sidan **Setup** väljer du **Start setup**.
   
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_mx"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **My Domains,** i området **Mailboxes,** väljer du **länken Configure your MX records.** 
    
3. Välj **Annat** i **listrutan Din** e-postleverantör. 
    
4. Välj **+ Add another (lägg till ytterligare en).**
    
5. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Host Name | Pekar på | Prioritet | TTL |
   |:-----|:-----|:-----|:-----|
   |Fylls i automatiskt <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) | 1 timme|
   
6. Om det finns andra MX-poster tar du bort dem. 
    
7. Välj **OK**.
    
8. Välj OK i **bekräftelsedialogrutan.**
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Lägg till de fem CNAME-posterna som krävs för Microsoft
<a name="BKMK_cname"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner). 
    
3. Välj **+ Add another (lägg** till ytterligare **en) på raden CNAME (Aliases)** i DNS-redigeraren för varje CNAME-post. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Host Name | Pekar på | TTL |
   |:-----|:-----|:-----|
   |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 timme  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 timme <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 timme  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 timme <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 timme  <br/> |
   
5. Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.  
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner). 
    
3. Välj **+ Add another (lägg** till ytterligare en) på raden TXT **(Text)** i DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Host Name | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[lämna det här blankt]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    <br/> |TXT  <br/> | 1 timme |
   
5. Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_srv"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj **knappen Edit** DNS (redigera **DNS) i** området Advanced **(avancerat) på sidan My** Domains (mina domäner). 
    
3. Välj **+ Add another (lägg** till ytterligare **en) på raden SRV** i DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Tjänst | Protokoll | Namn | Vikt | Port | Mål | Prioritet | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Fylls i automatiskt |1  |443   |sipdir.online.lync.com |100 |1 timme |
   |sipfed|tcp |Fylls i automatiskt|1 |5061 |sipfed.online.lync.com|100 | 1 timme |
   
5. Välj knappen Save DNS (spara **DNS)** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
