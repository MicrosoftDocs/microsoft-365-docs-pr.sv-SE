---
title: Skapa DNS-poster på Dreamhost för Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dreamhost för Microsoft.
ms.openlocfilehash: 756889457e802bdd9ee18b239b6986fb69f6b924
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939301"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a>Skapa DNS-poster på Dreamhost för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om DreamHost är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Lync och så vidare.
 
När du har lagt till dessa poster på DreamHost konfigureras domänen så att den fungerar med Microsoft-tjänster.
  
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/). Du uppmanas att logga in.
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.** 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Typ**|**Värde**|**Kommentar**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |(Det här fältet är valfritt.)  <br/> |
   
   ![Dreamhost-BP-Verifiera-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. Välj **Lägg till post nu!**
    
    ![Dreamhost-BP-Verifiera-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan.
  
1. För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/). Du uppmanas att logga in.
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. På **instrumentpanelssidan** väljer du **E-post**och sedan **Anpassad MX**.
    
    ![Dreamhost-BP-Konfigurera-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. Välj **Redigera** för den domän som du vill redigera i kolumnen **Åtgärder** i avsnittet **Hantera e-postleverans.** 
    
    ![Dreamhost-BP-Konfigurera-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. I avsnittet **Anpassad MX-post** skriver eller kopierar eller klistrar du in följande värden från följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Om det finns några andra befintliga MX-poster markerar du de poster som ska tas bort.)
    
    |**MX-post (obligatoriskt)**|
    |:-----|
    |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> 0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-Konfigurera-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. Välj **Ändra den här domänen om du vill använda anpassade MX-poster nu!**
    
    ![Dreamhost-BP-Konfigurera-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. Om det finns några andra befintliga MX-poster tar du bort varje post genom att markera posten och sedan trycka på **Delete-tangenten** på tangentbordet. 
    
    ![Dreamhost-BP-Konfigurera-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. Om du har tagit bort några poster väljer du **Uppdatera dina anpassade MX-poster nu!**
    
    ![Dreamhost-BP-Konfigurera-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan.
  
1. För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/). Du uppmanas att logga in.
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.** 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Typ**|**Värde**|**Kommentar**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
   
    ![Dreamhost-BP-Konfigurera-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. Välj **Lägg till post nu!**
    
    ![Dreamhost-BP-Konfigurera-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. Lägg till var och en av de två andra CNAME-posterna med hjälp av föregående två steg och värdena från de andra fem raderna i tabellen.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden.
  
Följ stegen nedan.
  
1. För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/). Du uppmanas att logga in.
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.** 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Typ**|**Värde**|**Kommentar**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |(Det här fältet är valfritt.)  <br/> |
   
   ![Dreamhost-BP-Konfigurera-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. Välj **Lägg till post nu!**
    
    ![Dreamhost-BP-Konfigurera-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. Lägg till den andra SRV-posten med föregående två steg och värdena från den andra raden i tabellen.
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan.
  
1. För att komma igång, gå till din domänsida på DreamHost med hjälp av [denna länk](https://panel.dreamhost.com/). Du uppmanas att logga in.
    
    ![Dreamhost-BP-Konfigurera-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. På **instrumentpanelssidan** väljer du **Domäner**och hanterar sedan **domäner**.
    
    ![Dreamhost-BP-Konfigurera-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Välj **DNS** för den domän som du vill redigera i avsnittet **Domän** på sidan **Hantera domäner.** 
    
    ![Dreamhost-BP-Konfigurera-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. I avsnittet **Lägg till en anpassad DNS-post** skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**Typ**|**Värde**|**Kommentar**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |(Det här fältet är valfritt.)  <br/> |
   
    ![Dreamhost-BP-Konfigurera-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. Välj **Lägg till post nu!**.
    
    ![Dreamhost-BP-Konfigurera-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. Lägg till den andra SRV-posten med föregående två steg och värdena från den andra raden i tabellen.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 

  
