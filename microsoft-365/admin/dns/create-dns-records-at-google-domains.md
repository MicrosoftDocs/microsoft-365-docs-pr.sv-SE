---
title: Skapa DNS-poster på Google Domains för Office 365
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Lync och andra tjänster på Google Domains för Office 365.
ms.openlocfilehash: f0a9a42127fc5b722679013b899255f77840d670
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211733"
---
# <a name="create-dns-records-at-google-domains-for-office-365"></a>Skapa DNS-poster på Google Domains för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Google Domains är din DNS-värd följer du anvisningarna i den här artikeln om du vill verifiera din domän och konfigurera DNS-posterna för e-post, Lync och så vidare.
  
När du har lagt till dessa poster på Google Domains konfigureras domänen så att den fungerar med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
1. Välj **Logga in**.
    
2. Ange dina inloggningsuppgifter och välj sedan **logga in**igen .
    
2. Leta reda på den domän som du vill använda med Office 365 på sidan **Mina domäner** och välj länken **HANTERA** bredvid den. Välj **DNS**i den vänstra navigeringen .
    
3. Skriv eller kopiera och klistra in värdena från följande tabell i rutorna för den nya posten i avsnittet ** Anpassade resursposter ** i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type (typ)** <br/> |**TTL** <br/> |**Data** <br/> |
    |@  <br/> |TXT  <br/> |1H (1H)  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Välj **Lägg till**.
    
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

1. Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
2. Välj **Logga in**.
    
3. Ange dina inloggningsuppgifter och välj sedan **logga in**igen .
4. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera.
    
    > [!IMPORTANT]
    > Om du har ett G Suite-e-postkonto måste du först ta bort MX-posterna som är kopplade till kontot. MX-posterna kopplade till G Suite förhindrar tillägg av MX-poster, däribland dem som krävs för Office 365. Observera att borttagning av MX-poster inte raderar ditt G Suite-konto. Så här tar du bort MX-posterna från ditt G Suite-konto. 
  
5. Välj **Ta bort**i området **S suite** i avsnittet **Syntetiska poster** .
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Ta bort i avsnittet Syntetiska poster](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Välj **Ta bort**.
    
    ![Välj Ta bort](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H (1H)  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **0** motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  <br/> **Obs!** Hämta din \<*domännyckel*\> från ditt Office 365-konto.  [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          [Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet? <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Välj **Lägg till**.
    
    ![Välj Lägg till](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Om det finns andra Custom MX-poster tar du bort dem.
    
1. Välj **Redigera** på MX-postraden. 
    
    ![Välj Redigera på MX-postraden](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. För var och en av de andra anpassade MX-posterna markerar du posten i rutan **Data** och trycker sedan på **Delete-tangenten** på tangentbordet för att ta bort posten. 
    
    Fortsätt tills du har tagit bort **Data**-posten för var övriga MX-poster. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. När du har tagit bort **dataposten** för var och en av de andra MX-posterna väljer du **Spara** för att spara ändringarna. 
    
    ![Välj Spara](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Lägga till de fem CNAME-poster som krävs för Office 365

1. Kom igång genom att gå till sidanhttps://domains.google.com/registrar) [Google Domäner] ( och logga in.
    
2. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera. 
    
3. Lägg till den första CNAME-posten.
    
    Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du, eller kopierar och klistrar, in värdena från första raden i följande tabell. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H (1H)  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H (1H)  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H (1H)  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H (1H)  <br/> |enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H (1H)  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Välj **Lägg till**.
    
    ![Välj Lägg till](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Lägg till de andra fyra CNAME-posterna.
    
    Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från nästa rad i tabellen och välj sedan **Lägg** till för att slutföra posten igen. 
    
    Upprepa den här processen tills du har skapat alla nödvändiga CNAME-poster.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md). 
  
1. Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
1. Välj **Logga in**.
    
2. Ange dina inloggningsuppgifter och välj sedan **logga in**igen .
    
3. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera. 
    
4. Välj **Redigera**på TXT-postraden i avsnittet **Anpassade resursposter.** 
    
    > [!IMPORTANT]
    > I Google Domains betraktas en TXT-post som en uppsättning som kan innehålla flera poster. Om du har minst en TXT-post, till exempel TXT-posten du använde för att verifiera din domän, måste du lägga till nya TXT-poster i denna postuppsättning. Försöker du att ange ytterligare TXT-poster som separata poster får du ett felmeddelande om **Duplicate record** (dublettpost). 
  
    ![Välj Redigera på TXT-postraden](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Markera **kontrollen (+).** 
    
    ![Välj pluskontrollen](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Du kan behöva rulla nedåt.)
    
    |**Data**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.           
   
   ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Välj **Spara**.
    
    ![Välj Spara](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

1. Börja med att gå till domänsidan på Google Domains genom att klicka på [den här länken](https://domains.google.com/registrar). Du uppmanas att logga in. Gör så här:
    
2. Välj **Logga in**.
    
3. Ange dina inloggningsuppgifter och välj sedan **logga in**igen .
    
4. På sidan **Domäner** i avsnittet **Domän** väljer du **Konfigurera DNS** för den domän som du vill redigera. 
    
5. Lägga till den första SRV-posten.
    
    Gå till avsnittet **Custom resource records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H (1H)|100 1 443 sipdir.online.lync.com. **Det här värdet MÅSTE sluta med en punkt (.)** **Anm.:** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.           |
    |_sipfederationtls._tcp|SRV|1H (1H)|100 1 5061 sipfed.online.lync.com. **Värdet MÅSTE sluta med en punkt (.)**

    Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.       
   
    ![Skriva eller klistra in värden i avsnittet Anpassade resursposter](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Välj **Lägg till**.
    
    ![Välj Lägg till](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Lägg till den andra SRV-posten.
    
    Skapa en post i avsnittet **Anpassade resursposter** med hjälp av värdena från den andra raden i tabellen och välj sedan **Lägg** till för att slutföra posten igen. 
    
    > [!NOTE]
    > Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
