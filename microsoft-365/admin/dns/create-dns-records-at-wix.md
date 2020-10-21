---
title: Skapa DNS-poster på WIX för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på WIX för Microsoft.
ms.openlocfilehash: ee236a9178092bb8fd14a9615c2ac5911b1ecc87
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645665"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Skapa DNS-poster på WIX för Microsoft

**[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.

Det här är de viktigaste posterna att lägga till. 
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägg till en MX-post så att e-post för din domän kommer till Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Lägg till de fem CNAME-poster som krävs för Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägg till de två SRV-poster som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).
    
När du har lagt till dessa poster på WIX är din domän konfigurerad för att fungera med Microsoft-tjänster.
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_txt"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 

> [!NOTE]
> WIX stöder inte DNS-poster för under domäner.
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** . 
    
3. Välj **+ Lägg till en annan** på raden **txt (text)** i DNS-redigeraren. 
    
4. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
   ||||
   |:-----|:-----|:-----|
   | Värdnamn <br/> | TXT Value <br/> | TTL <br/> |
   |Fylls i automatiskt  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)|1 timme <br/> |          |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
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
    
2. Välj länken **Konfigurera dina MX-poster** i området **post lådor** på sidan **My Domains** . 
    
3. Välj **annan** från List rutan **din e-postleverantör** . 
    
4. Välj **+ Lägg till ett annat**.
    
5. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Värdnamn | Pekar på | Priority | TTL |
   |:-----|:-----|:-----|:-----|
   |Fylls i automatiskt <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |siffrorna  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) | 1 timme|
   
6. Om det finns andra MX-poster i listan tar du bort dem. 
    
7. Välj **OK**.
    
8. Välj **OK**i bekräftelse dialog rutan.
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Lägga till de fem CNAME-poster som krävs för Microsoft
<a name="BKMK_cname"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** . 
    
3. Välj **+ Lägg till en annan** på raden **CNAME (aliases)** i DNS-redigeraren för varje CNAME-post. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Värdnamn | Pekar på | TTL |
   |:-----|:-----|:-----|
   |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 timme  <br/> |
   |sip  <br/> |sipdir.online.lync.com  <br/> |1 timme <br/> |
   |lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 timme  <br/> |
   |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 timme <br/> |
   |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 timme  <br/> |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.  
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** . 
    
3. Välj **+ Lägg till en annan** på raden **txt (text)** i DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Värdnamn | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[lämna det här blankt]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    <br/> |TXT  <br/> | 1 timme |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_srv"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **My Domains** , i området **Avancerat** , väljer du knappen **Edit DNS** . 
    
3. Välj **+ Lägg till ytterligare** i **SRV** -raden i DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
   | Tjänst | Protokoll | Namn | Väga | Port | Mål | Priority | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Fylls i automatiskt |9.1  |443   |sipdir.online.lync.com |100 |1 timme |
   |sipfed|tcp |Fylls i automatiskt|9.1 |5061 |sipfed.online.lync.com|100 | 1 timme |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
