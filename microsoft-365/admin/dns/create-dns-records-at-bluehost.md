---
title: Skapa DNS-poster på Bluehost för Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Bluehost för Microsoft.
ms.openlocfilehash: c2aabd7a578ab792cfb341f67765fc3021038e44
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049101"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a>Skapa DNS-poster på Bluehost för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Bluehost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
När du har lagt till dessa poster på Bluehost konfigureras domänen så att den fungerar med Microsoft-tjänster.

> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.)
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .
    
4. Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Välj **lägg till post**.
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär en sökning efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.)
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .
    
4. Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/>**Obs!** Hämta din \<*domännyckel*\> från ditt Microsoft-konto. [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
   ![Välj Typ i listrutan](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Välj **lägg till post**.
    
    ![Välj Lägg till post](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Om det finns andra MX-poster i avsnittet **MX (Mail Exchanger)** ska du ta bort dem. 
    
    För en av de andra MX-posterna väljer du **Ta bort.**
    
    ![Välj Ta bort för varje ytterligare MX-post](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. Välj **OK**i bekräftelsedialogrutan .
    
    ![Välj OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Du använder samma process för att ta bort eventuella andra MX-poster som visas.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.)
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .
    
4. Leta reda på raden för posten för **automatisk upptäckt** i avsnittet **A (Värd)** och välj sedan **ta bort** för den raden. 
    
    > [!IMPORTANT]
    > Du måste ta bort den befintliga posten för **automatisk upptäckt** *innan* du lägger till den **automatiska upptäcktspost** som krävs av Microsoft. Bluehost tillåter inte att du har två **autodiscover** -poster samtidigt. 
  
    ![Välj Ta bort](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Välj **OK**.
    
    ![Välj OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Skapa den första av de sex CNAME-posterna.
    
    Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Skapa den första CNAME-posten](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Välj **lägg till post**.
    
    ![Välj Lägg till post](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Lägg till de andra fem CNAME-posterna var för sig.
    
    I avsnittet **Lägg till DNS-post** skapar du en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **lägga till post** igen för att slutföra posten. 
    
    Upprepa proceduren tills du har skapat alla sex CNAME-posterna.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md). 
  
1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.)
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .
    
4. Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
        
    |**Host Record**|**TTL**|**Type**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Kopiera TXT-värdet](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Välj **lägg till post**.
    
    ![Välj Lägg till post](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på Bluehost genom att klicka på [den här länken](https://my.bluehost.com/cgi/dm). Du uppmanas att logga in först.
    
2. Gå till sidan **domains** och området **domain**. Leta reda på raden för den domän du ändrar och markera kryssrutan för den domänen. 
    
    (Du kan behöva rulla nedåt.)
    
3. Välj **Hantera DNS-poster**på raden **DNS Zone Editor** i området ***domain_name*** .
    
4. Skapa den första av de två SRV-posterna.
    
    Gå till sidan **DNS Zone Editor** och området **Add DNS Record**. I den nya postens rutor skriver du eller kopierar och klistrar in värdena från den första raden i följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Service**|**Protocol**|**Host**|**TTL**|**Type**|**Prioritet**|**Vikt**|**Port**|**Points To**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Kopiera värdet för den nya posten](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Välj **lägg till post**.
    
    ![Välj Lägg till post](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Lägg till den andra SRV-posten.
    
    I avsnittet **Lägg till DNS-post** skapar du en post med hjälp av värdena från den andra raden i tabellen och väljer sedan **lägga till post** igen för att slutföra posten. 
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  

