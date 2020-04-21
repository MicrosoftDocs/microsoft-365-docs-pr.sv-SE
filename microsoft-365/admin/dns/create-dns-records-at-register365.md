---
title: Skapa DNS-poster på Register365 för Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register365 för Microsoft.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629269"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>Skapa DNS-poster på Register365 för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Register365 är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare. 
  
Det här är de viktigaste posterna att lägga till.  
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägg till en MX-post så att e-post för din domän kommer till Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Lägga till de sex CNAME-poster som krävs för Microsoft](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägg till de två SRV-poster som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster på Microsoft konfigureras domänen så att den fungerar med Microsoft-tjänster.
  
Mer information om webbhotell och DNS för webbplatser med Microsoft finns i [Använda en offentlig webbplats med Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder domänen med Microsoft måste vi se till att du äger den. Din förmåga att logga in på ditt konto hos domänregistratorer och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
    
    |**Värdnamn**|**Typ**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **mål- eller poäng till-adress-värde** här, från bordet.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Spara](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorerns webbplats går du tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post verifieras domänen.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägg till en MX-post så att e-post för din domän kommer till Microsoft
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    |**Värdnamn**|**Priority**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |1  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Spara](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Spara](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
    
    |****Värdnamn****|****Typ****|****Resultat****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Välj **Spara**.
    
    ![Välj Spara](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. 
  
1. Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
    
    |**Värdnamn**|**Typ**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Ange värden på sidan Lägg till/ändra DNS-zon](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Spara](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägg till de två SRV-poster som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på Register365 genom att klicka på [den här länken](https://admin.register365.com/dns/). Du uppmanas att logga in först.
    
    ![Inloggningssidan för kontrollpanelen](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![Välja DNS-inställningar i listan](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för de nya posterna. 
    
    (Du kan behöva rulla nedåt.)
    
    |**Name**|**Prioritet**|**Vikt**|**Port**|**Result**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Ange värden i avsnittet Serviceposter](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Spara](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
