---
title: Skapa DNS-poster för Office 365 på Wix
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Wix för Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211068"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>Skapa DNS-poster för Office 365 på Wix

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. 
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägga till en MX-post så att e-post för din domän kommer till Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365).
    
- [Lägg till de fem CNAME-poster som krävs för Office 365](#add-the-five-cname-records-that-are-required-for-office-365).
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Office 365](#add-the-two-srv-records-that-are-required-for-office-365).
    
När du har lagt till dessa poster på Wix är din domän konfigurerad för att fungera med Office 365-tjänster.
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_txt"> </a>

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
||||
|:-----|:-----|:-----|
|**Värdnamn** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|Fylls i automatiskt  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)|1 timme <br/> |          |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
  
  
3. På sidan **Setup** väljer du **Start setup**.
   
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_mx"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **Mina domäner** i området **Postlådor** väljer du länken **Konfigurera MX-poster.** 
    
3. Välj **Annat** i listrutan **E-postleverantör.** 
    
4. Välj **+ Lägg till en annan**.
    
5. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Värdnamn**|**Points to (pekar på)**|**Prioritet**|**TTL**|
|:-----|:-----|:-----|:-----|
|Fylls i automatiskt <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Office 365-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) | 1 timme|
   
6. Om det finns några andra MX-poster i listan tar du bort var och en av dem. 
    
7. Välj **OK**.
    
8. Välj **OK**i bekräftelsedialogrutan .
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Lägga till de fem CNAME-poster som krävs för Office 365
<a name="BKMK_cname"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i raden **CNAME (Alias)** på DNS-redigeraren för varje CNAME-post. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Värdnamn**|**Pekar på**|**TTL**|
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
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.  
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Värdnamn**|**TXT Value**|**TTL**|
|:-----|:-----|:-----|
|[lämna det här blankt]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    <br/> |TXT  <br/> | 1 timme |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_srv"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i **SRV-raden** i DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Service**|**Protocol (protokoll)**|**Name (namn)**|**Vikt**|**Port**|**Target (mål)**|**Prioritet**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Fylls i automatiskt |1  |443   |sipdir.online.lync.com |100 |1 timme |
|sipfed|tcp |Fylls i automatiskt|1 |5061 |sipfed.online.lync.com|100 | 1 timme |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  

