---
title: Skapa DNS-poster på Crazy Domains för Office 365
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Crazy Domains för Office 365.
ms.openlocfilehash: 157c33a52403efbefe673bf11465de525ffb4f33
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813031"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a>Skapa DNS-poster på Crazy Domains för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Crazy Domains är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
När du har lagt till dessa poster på Crazy Domains konfigureras domänen så att den fungerar med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Välj **Domäner**i avsnittet **Mitt konto** .
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. På sidan **Domännamn** väljer du namnet på den domän som du uppdaterar i avsnittet **Domän.** 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Välj listrutan i avsnittet **DNS-inställningar.** 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Välj **Lägg till post**.
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Välj **TXT Record** i listrutan **Add Record**. 
    
    ![CrazyDomains-BP-Verifiera-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Välj **Lägg till**.
    
    ![CrazyDomains-BP-Verifiera-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Underdomän**|**Textpost**|
    |:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verifiera-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Välj **Uppdatera**.
    
    ![CrazyDomains-BP-Verifiera-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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

1. Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Välj **Domäner**i avsnittet **Mitt konto** .
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. På sidan **Domännamn** väljer du namnet på den domän som du uppdaterar i avsnittet **Domän.** 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Välj listrutan i avsnittet **DNS-inställningar.** 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Välj **Lägg till post**.
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Välj **MX Record** i listrutan **Add Record:**. 
    
    ![CrazyDomains-BP-Konfigurera-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. Välj **Lägg till**.
    
    ![CrazyDomains-BP-Konfigurera-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj **prioritetsvärdet** i listrutan.) 
    
    |**Mail for Zone**|**Priority**|**Assigned To Server**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |1  <br/> [Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet? <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Obs:** Hämta din * \<domännyckel\> * från ditt Office 365-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-Konfigurera-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. Välj **Uppdatera**.
    
    ![CrazyDomains-BP-Konfigurera-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. Om det finns några andra MX-poster i avsnittet **MX Record** väljer du **Ändra** för en av dessa poster. 
    
    ![CrazyDomains-BP-Konfigurera-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. Välj **Ta bort**.
    
    ![CrazyDomains-BP-Konfigurera-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. Välj **Uppdatera för** att bekräfta borttagningen. 
    
    ![CrazyDomains-BP-Konfigurera-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. Använd samma sätt för att ta bort andra MX-poster i listan tills endast den du lade till tidigare i den här proceduren finns kvar.
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Lägg till de sex CNAME-posterna som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

1. Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Välj **Domäner**i avsnittet **Mitt konto** .
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. På sidan **Domännamn** väljer du namnet på den domän som du uppdaterar i avsnittet **Domän.** 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Välj listrutan i avsnittet **DNS-inställningar.** 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Välj **Lägg till post**.
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Välj **CNAME Record** i listrutan **Add Record:**. 
    
    ![CrazyDomains-BP-Konfigurera-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. Välj **Lägg till**.
    
    ![CrazyDomains-BP-Konfigurera-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. Lägg till den första av de sex CNAME-posterna.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    |**Underdomän**|**Alias for**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. Välj **Lägg till CNAME-post**.
    
    ![CrazyDomains-BP-Konfigurera-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. Lägg till den andra CNAME-posten.
    
    I rutorna för den nya posten använder du värdena från nästa rad i tabellen och väljer sedan **lägg till CNAME-post**igen .
    
    Upprepa proceduren tills du har skapat alla sex CNAME-posterna.
    
11. Välj **Uppdatera om** du vill spara ändringarna. 
    
    ![CrazyDomains-BP-Konfigurera-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Välj **Domäner**i avsnittet **Mitt konto** .
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. På sidan **Domännamn** väljer du namnet på den domän som du uppdaterar i avsnittet **Domän.** 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Välj listrutan i avsnittet **DNS-inställningar.** 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Välj **Lägg till post**.
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Välj **TXT Record** i listrutan **Add Record:**. 
    
    ![CrazyDomains-BP-Konfigurera-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. Välj **Lägg till**.
    
    ![CrazyDomains-BP-Konfigurera-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från följande tabell.
    
    |**Underdomän**|**Textpost**|
    |:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![CrazyDomains-BP-Konfigurera-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. Välj **Uppdatera**.
    
    ![CrazyDomains-BP-Konfigurera-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

1. Börja med att gå till domänsidan på Crazy Domains genom att klicka på [den här länken](https://manage.crazydomains.com/members/domains/). Du uppmanas att logga in först.
    
    ![CrazyDomains-BP-Konfigurera-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Välj **Domäner**i avsnittet **Mitt konto** .
    
    ![CrazyDomains-BP-Konfigurera-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. På sidan **Domännamn** väljer du namnet på den domän som du uppdaterar i avsnittet **Domän.** 
    
    ![CrazyDomains-BP-Konfigurera-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Välj listrutan i avsnittet **DNS-inställningar.** 
    
    ![CrazyDomains-BP-Konfigurera-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Välj **Lägg till post**.
    
    ![CrazyDomains-BP-Konfigurera-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Välj **SRV Record** från listrutan **Add Record:**. 
    
    ![CrazyDomains-BP-Konfigurera-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. Välj **Lägg till**.
    
    ![CrazyDomains-BP-Konfigurera-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. Lägg till den första av de två SRV-posterna.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    |**Record Type**|**Underdomän**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV Record  <br/> |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV Record  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![CrazyDomains-BP-Konfigurera-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. Välj **Lägg till SRV-post**.
    
    ![CrazyDomains-BP-Konfigurera-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. Lägg till den andra SRV-posten.
    
    I rutorna för den nya posten använder du värdena från den andra raden i tabellen.
    
11. Välj **Uppdatera om** du vill spara ändringarna. 
    
    ![CrazyDomains-BP-Konfigurera-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
