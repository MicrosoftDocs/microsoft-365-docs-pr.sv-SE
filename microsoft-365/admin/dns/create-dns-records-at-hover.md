---
title: Skapa DNS-poster på Hover för Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Hover för Office 365.
ms.openlocfilehash: 72df2d98f3446087a1e9796cd616293a91003ad9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813036"
---
# <a name="create-dns-records-at-hover-for-office-365"></a>Skapa DNS-poster på Hover för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Hover är din DNS-värd följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
     
När du har lagt till dessa poster på Hover är din domän konfigurerad för att fungera med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Välj fliken **DNS.** 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Välj **Lägg till ny**.
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.
    
    ||||
    |:-----|:-----|:-----|
    |Hostname  <br/> |Record Type  <br/> |Value  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Välj **Spara**.
    
    ![Välj Spara](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
    
2. På sidan **Domäner** väljer du den domän som du verifierar. 
    
    
  
3. Välj **Starta inställningar**på sidan **Inställningar** .
    
    
  
4. På sidan **Verifiera domän** väljer du **Verifiera**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Välj fliken **DNS.** 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Välj **Lägg till ny**.
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. I rutan för den nya posten väljer du **MX** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Hostname**|**Record Type**|**Priority**|**Hostname**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Office 365-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. Välj **Spara**.
    
    ![Välj Spara](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. Om det förekommer andra MX-poster tar du bort dem med följande tvåstegsprocedur:
    
    Välj först **Ta bort**en post som du vill ta bort .
    
    ![Musen över och välj Ta bort](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    För det andra väljer du **Ja** för att bekräfta varje borttagning. 
    
    ![Välj Ja för att bekräfta borttagning](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    Upprepa proceduren tills du har tagit bort alla MX-poster förutom den du lade till tidigare i proceduren.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Lägg till CNAME-posterna som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Välj fliken **DNS.** 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Lägg till den första av de sex CNAME-posterna.
    
    Välj **Lägg till ny**.
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. I de tomma rutorna för den nya posten väljer du **CNAME** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.
    
    |**Hostname**|**Record Type**|**Target Host**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. Välj **Spara**.
    
    ![Välj Spara](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. Du använder de tre föregående stegen när du lägger till de andra fem CNAME-posterna med värdena från de andra fem raderna i tabellen.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Välj fliken **DNS.** 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Välj **Lägg till ny**.
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. I rutan för den nya posten väljer du **TXT** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Hostname**|**Record Type**|**Value (Värde)**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. Välj **Spara**.
    
    ![Välj Spara](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan eller [titta på videon](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Kom igång genom att gå till domänsidan på Hover med [den här länken](https://www.hover.com/domains). Du uppmanas att logga in först.
    
    ![Logga in](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Under **Hantera dina domäner**väljer du namnet på den domän som du vill redigera.
    
    ![Välj en domän](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Välj fliken **DNS.** 
    
    ![Välj fliken DNS](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Lägg till den första av de två SRV-posterna.
    
    Välj **Lägg till ny**.
    
    ![Välj Lägg till ny](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. I de tomma rutorna för den nya posten väljer du **SRV** för **Record Type** och skriver sedan in, eller kopierar och klistrar in, värdena från den första raden i följande tabell.
    
    |**Hostname**|**Record Type**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Skriva eller kopiera och klistra in DNS-värden](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. Välj **Spara**.
    
    ![Välj Spara](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. Du använder de tre föregående stegen när du lägger till den andra SRV-posten med värdena från tabellens andra rad.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
