---
title: Skapa DNS-poster med 1&1 IONOS för Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på 1&1 IONOS för Microsoft.
ms.openlocfilehash: 1c32e15be8bfdf9ea29647af511d0f8ff0ac0b57
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049149"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Skapa DNS-poster med 1&1 IONOS för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
> [!CAUTION]
> Observera att 1&1 IONOS inte tillåter att en domän har både en MX-post och en CNAME-post på den högsta nivån. Detta begränsar hur du kan konfigurera Exchange Online för Microsoft. Det finns en lösning, men vi rekommenderar att du använder den **endast** om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS. > Om du trots den här [tjänstbegränsningen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) väljer att hantera dina egna Microsoft DNS-poster med 1&1 IONOS följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare. 
  
När du har lagt till dessa poster vid 1&1 IONOS konfigureras domänen så att den fungerar med Microsoft-tjänster.
  
  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon (börja vid 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/). Du uppmanas att logga in.
    
2. Välj **Hantera domäner**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.
    
6. Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Typ** <br/> |**Prefix** <br/> |**Name Value** <br/> |
    |TXT  <br/> |(Lämna det här fältet tomt)  <br/> |MS=ms *XXXXXXXX*  <br/> Obs: Detta är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Välj **Spara**.
    
8. Välj **Spara** igen. 
    
9. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
10. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan eller [titta på videon (börja vid 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/). Du uppmanas att logga in.
    
2. Välj **Hantera domäner**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. Välj **Annan e-postserver**i området **MX Record (MX Record)** i avsnittet **MX** Records .<br/>(Du kan behöva rulla nedåt.)<br/>![1&amp;1-BP-Konfigurera-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. Om det förekommer några MX-poster sen tidigare tar du bort var och en genom att markera posten och sedan trycka på **Del**-tangenten.<br/>(Om det inte finns några MX-poster sen tidigare fortsätter du till nästa steg.)<br/>![1&amp;1-BP-Konfigurera-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. I rutorna för **MX 1**-posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    |**MX 1**|**Priority (prioritet)**|
    |:-----|:-----|
    | *\<domännyckel\>*  .mail.protection.outlook.com  <br/>  Skaffa domännyckeln \<\> från ditt Microsoft-konto. [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | 
    
    ![1 och 1 - konfigurera 2 och 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Välj **Spara**.<br/>(Du kan behöva rulla nedåt.)<br/>![1&amp;1-BP-Konfigurera-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .<br/>![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS kräver en lösning så att du kan använda en MX-post tillsammans med CNAME-posterna som krävs för Microsofts e-posttjänster. Den här lösningen kräver att du skapar en uppsättning underdomäner vid 1&1 IONOS och tilldela dem till CNAME-poster.
  
> [!IMPORTANT]
> Kontrollera att du har minst två tillgängliga underdomäner innan du startar den här proceduren. Vi rekommenderar den här lösningen endast om du redan har erfarenhet av att skapa underdomäner vid 1&1 IONOS. 
  
### <a name="basic-cname-records"></a>Grundläggande CNAME-poster

Följ stegen nedan eller [titta på videon (börja vid 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/). Du uppmanas att logga in.
    
2. Välj **Hantera domäner**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan **Hantera underdomäner**.<br/>![1&amp;1-BP-Konfigurera-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Nu ska du skapa du två underdomäner och ange ett värde för **Alias** för var och en av dem.<br/>(Detta krävs eftersom 1&1 IONOS stöder endast en CNAME-post på den högsta nivån, men Microsoft kräver flera CNAME-poster.)<br/>Först måste du skapa Autodiscover-underdomänen.
    
4. I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)

    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-Konfigurera-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Välj **Skapa underdomän**.<br/>![1&amp;1-BP-Konfigurera-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Leta reda på underdomänen **autodiscover** i **underdomänen i översikten** och välj sedan **panelkontrollen (v)** för underdomänen. <br/>![1&amp;1-BP-Konfigurera-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**. <br/>![1&amp;1-BP-Konfigurera-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**<br/>![1&amp;1-BP-Konfigurera-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan.<br/> 
    
    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-Konfigurera-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Markera kryssrutan för ansvarsfriskrivningen **I am aware** (jag är medveten om).<br/>![1&amp;1-BP-Konfigurera-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Välj **Spara**.<br/>![1&amp;1-BP-Konfigurera-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Ytterligare CNAME-poster

De ytterligare CNAME-poster som skapas i följande proceduren aktiverar Skype för företag - Online-tjänster. Du kan utföra samma steg som du använde för att skapa de två CNAME-poster som du redan har skapat.
  
1. Skapa den tredje underdomänen (Lyncdiscover).<br/>I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**
    
2. I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)<br/> 
    
    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Välj **Skapa underdomän**.
    
4. På sidan **Domain Center** väljer du **Hantera underdomäner**.
    
5. Leta reda på **lyncdiscover** underdomänunderdomänen som du just skapade i avsnittet **Underdomänöver** och välj sedan **panelkontrollen (v)** för underdomänen. <br/>I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.
    
6. Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**
    
7. I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan. <br/>
    
    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.
    
9. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
10. Skapa den fjärde underdomänen (SIP): <br/>I avsnittet **Underdomänöversikt** väljer du **Skapa underdomän .**
    
11. I rutan **Create Subdomain** (skapa underdomän) för den nya underdomänen skriver du in, eller kopierar och klistrar in, endast värdet i **Skapa underdomän** från tabellen nedan. (Du kommer att lägga till värdet för **Alias** i ett senare steg.)<br/>
    
    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Välj **Skapa underdomän**.
    
13. På sidan **Domain Center** väljer du **Hantera underdomäner**.
    
14. Leta reda på den **sip-underdomän** som du just skapade i avsnittet **Underdomänöversikt** och välj sedan **panelkontrollen (v)** för underdomänen. <br/>I området **Inställningar för underdomäner** väljer du **Redigera DNS-inställningar**.
    
15. Välj **CNAME i området IP-adress (AAAA Records)** i området **IP-adress (A Record).** **CNAME**
    
16. I rutan **Alias:** skriver du in, eller kopierar och klistrar in, värdet i **Alias** från tabellen nedan. 
    
    |**Skapa underdomän**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Markera kryssrutan för **ansvarsfriskrivningen Jag är medveten** om och välj sedan **Spara**.
    
18. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .
    
### <a name="cname-records-needed-for-mdm"></a>CNAME-poster som krävs för MDM

> [!IMPORTANT]
> Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell. 
  
|**Skapa underdomän**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md). 
  
Följ stegen nedan eller [titta på videon (börja vid 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/). Du uppmanas att logga in.
    
2. Välj **Hantera domäner**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**. <br/>(Du kan behöva rulla nedåt.)
    
6. Gå till **Add Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. <br/>(Välj värdet för **Type** i listrutan.) <br/>
    
    |**Typ**|**Prefix**|**Name Value**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Lämna det här fältet tomt.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               | 
    
    ![TXT-post](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Välj **Spara**.<br/>![Lägg till post](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Välj **Spara**.<br/>![Spara post](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** .<br/>![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft

Följ stegen nedan eller [titta på videon (börja vid 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Om du har registrerat dig hos 1und1.de [loggar du in här](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. För att komma igång, gå till din domänsida på 1&1 IONOS med hjälp av [denna länk](https://my.1and1.com/). Du uppmanas att logga in.
    
2. Välj **Hantera domäner**.
    
3. Leta reda på den domän som du vill uppdatera på sidan **Domain Center** och välj sedan kontrollen **Panel** **(v)** för den domänen.
    
4. Välj **Redigera DNS-inställningar**i området **Domäninställningar** .
    
5. I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**.
    
6. Lägg till den första av de två SRV-posterna.<br/>I den nya postens rutor i området **Add Record** (lägg till post) skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan. <br/>(Välj **typ-** och **TTL-värden** i listrutan.) 
    
    |**Type (typ)**|**Service (tjänst)**|**Protocol (protokoll)**|**Name (namn)**|**Host (värd)**|**Prioritet**|**Vikt**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Lämna det här fältet tomt.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Lämna det här fältet tomt.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1&amp;1-BP-Konfigurera-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Välj **Spara**. <br/>![1&amp;1-BP-Konfigurera-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Välj **Spara**. <br/>![1&amp;1-BP-Konfigurera-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Välj **Ja**i dialogrutan **Redigera DNS-inställningar** . <br/>![Välja Ja i dialogrutan Redigera DNS-inställningar](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Lägg till den andra SRV-posten. <br/>I avsnittet **TXT- och SRV-poster** väljer du **Lägg till post**. <br/>Skapa en post med värdena från den andra raden i tabellen i området **Lägg till post** och välj sedan Lägg **till**, **Spara**och **Ja** igen för att slutföra posten. 
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
