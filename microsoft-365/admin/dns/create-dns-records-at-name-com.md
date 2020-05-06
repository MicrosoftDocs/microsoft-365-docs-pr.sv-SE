---
title: Skapa DNS-poster på name.com för Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på name.com för Microsoft.
ms.openlocfilehash: e9133b3701c2b454cad11b9579dc7463f1a74460
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048969"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a>Skapa DNS-poster på name.com för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om name.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
När du har lagt till dessa poster i name.com konfigureras domänen så att den fungerar med Microsoft-tjänster.

  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **Mina domäner**väljer du namnet på den domän som du vill ändra.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Välj **DNS Records**i kolumnen **Detaljer** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj värdet för **Type** i listrutan.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Typ** <br/> |**Host (värd)** <br/> |**Answer (svar)** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Lämna det här fältet tomt.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Använd standardvärdet (300).  <br/> |
   
    ![Namn-BP-Verifiera-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. Välj **Lägg till post**.
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
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
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **Mina domäner**väljer du namnet på den domän som du vill ändra.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Välj **DNS Records**i kolumnen **Detaljer** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Typ**|**Host (värd)**|**Answer (svar)**|**TTL**|**Prio**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(Lämna det här fältet tomt.)  <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |Använd standardvärdet (300).  <br/> |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
   ![Namn-BP-Konfigurera-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. Välj **Lägg till post**.
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:
    
    För varandra MX-post väljer du **Ta bort** i kolumnen **Åtgärder.** 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    Om du vill bekräfta varje borttagning väljer du **Ta bort** i kolumnen **Åtgärder** igen. 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    Upprepa den här tvåstegsproceduren tills du har tagit bort alla de andra MX-posterna.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **Mina domäner**väljer du namnet på den domän som du vill ändra.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Välj **DNS Records**i kolumnen **Detaljer** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Lägg till den första CNAME-posten.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Typ**|**Host (värd)**|**Answer (svar)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |Använd standardvärdet (300).  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |Använd standardvärdet (300).  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |Använd standardvärdet (300).  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |Använd standardvärdet (300).  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |Använd standardvärdet (300).  <br/> |
   
   ![Namn-BP-Konfigurera-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. Välj **Lägg till post om** du vill lägga till den första posten. 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. Lägg till den andra CNAME-posten.
    
    Använd värdena från den andra raden i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten. 
    
    Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. 
  
1. Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **Mina domäner**väljer du namnet på den domän som du vill ändra.

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Välj **DNS Records**i kolumnen **Detaljer** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Typ**|**Host (värd)**|**Answer (svar)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Lämna det här fältet tomt.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |Använd standardvärdet (300).  <br/> |
   
   ![Namn-BP-Konfigurera-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. Välj **Lägg till post**.
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på name.com med [den här länken](https://www.name.com/account/domain). Du uppmanas att logga in först.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Under **Mina domäner**väljer du namnet på den domän som du vill ändra.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Välj **DNS Records+ i**kolumnen **Detaljer.** 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Lägg till den första SRV-posten:
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Type (typ)**|**Service (tjänst)**|**Weight (vikt)**|**TTL**|**Prio**|**Protocol (protokoll)**|**Port**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|1|Använd standardvärdet (300).|100|tls|443|sipdir.online.lync.com <br> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
    |SRV|sipfederationtls|1|Använd standardvärdet (300).|100|tcp|5061|sipfed.online.lync.com <br>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
   ![Namn-BP-Konfigurera-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. Välj **Lägg till post**.

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. Lägg till den andra SRV-posten.

Använd värdena från nästa rad i tabellen ovan och välj sedan **Lägg till post** för att lägga till den andra posten.

>[!NOTE]
>Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).
