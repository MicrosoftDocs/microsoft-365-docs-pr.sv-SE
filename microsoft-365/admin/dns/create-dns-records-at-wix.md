---
title: Skapa DNS-poster på Wix för Microsoft
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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Wix för Microsoft.
ms.openlocfilehash: 2cbc4887f276e63f09b433225e09315c227c961c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629245"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Skapa DNS-poster på Wix för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Wix är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. 
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägg till en MX-post så att e-post för din domän kommer till Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Lägg till de fem CNAME-poster som krävs för Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägg till de två SRV-poster som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).
    
När du har lagt till dessa poster på Wix konfigureras domänen så att den fungerar med Microsoft-tjänster.
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_txt"> </a>

Innan du använder domänen med Microsoft måste vi se till att du äger den. Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
||||
|:-----|:-----|:-----|
|**Värdnamn** <br/> |**TXT Value** <br/> |**TTL** <br/> |
|Fylls i automatiskt  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.  [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)|1 timme <br/> |          |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post verifieras domänen.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
  
  
3. På sidan **Setup** väljer du **Start setup**.
   
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägg till en MX-post så att e-post för din domän kommer till Microsoft
<a name="BKMK_mx"> </a>

1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. På sidan **Mina domäner** i området **Postlådor** väljer du länken **Konfigurera MX-poster.** 
    
3. Välj **Annat** i listrutan **E-postleverantör.** 
    
4. Välj **+ Lägg till en annan**.
    
5. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Värdnamn**|**Points to (pekar på)**|**Prioritet**|**TTL**|
|:-----|:-----|:-----|:-----|
|Fylls i automatiskt <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.   [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) | 1 timme|
   
6. Om det finns några andra MX-poster i listan tar du bort var och en av dem. 
    
7. Välj **OK**.
    
8. Välj **OK**i bekräftelsedialogrutan .
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Lägga till de fem CNAME-poster som krävs för Microsoft
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
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.  
  
1. Kom igång genom att gå till domänsidan på Wix genom att klicka på [den här länken](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Du uppmanas att logga in först.
    
2. Välj knappen **Redigera DNS** i området **Avancerat** på sidan **Mina domäner.** 
    
3. Välj **+ Lägg till en annan** i raden **TXT (Text)** på DNS-redigeraren. 
    
4. I rutorna för den nya posten skriver du in eller kopierar värdena från följande tabell:
    
|**Värdnamn**|**TXT Value**|**TTL**|
|:-----|:-----|:-----|
|[lämna det här blankt]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    <br/> |TXT  <br/> | 1 timme |
   
5. Välj knappen **Spara DNS** högst upp i DNS-redigeraren. 
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägg till de två SRV-poster som krävs för Microsoft
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
  

