---
title: Skapa DNS-poster på Dyn.com för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Dyn.com för Microsoft.
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910336"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>Skapa DNS-poster på Dyn.com för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Om Dyn.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
 

  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

1. Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. På sidan **Zone Level Services** väljer du Dyn Standard DNS **Service** för den domän som du vill redigera. 
    
3. På sidan **DNS** för domänen väljer du **Preferences**.
    
4. Välj **Enable Expert Interface**.
    
5. Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Välj **Create Record**.
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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

1. Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. På sidan **Zone Level Services** väljer du Dyn Standard DNS **Service** för den domän som du vill redigera. 
    
3. På sidan DNS för domänen väljer du **Preferences**.
    
4. Välj **Enable Expert Interface**.
    
5. Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |600  <br/> |MX  <br/> |10  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **10** motsvarar MX-prioritetsvärdet. Skriv 10 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  <br/> **Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)      <br>    [Mer information om prioritet finns i ](../setup/domains-faq.yml)Vad är MX-prioritet? <br/> |
   
    ![Dyn-BP - Konfigurera-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. Välj **Create Record**.
    
    ![Dyn-BP - Konfigurera-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. Om det finns andra MX-poster tar du bort dem genom att markera kryssrutan för varje post i kolumnen **Delete**. 
    
    ![Dyn-BP - Konfigurera-2-3](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. Välj **Apply Changes**.
    
    ![Dyn-BP - Konfigurera-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägg till de sex CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. På sidan **Zone Level Services** väljer du Dyn Standard DNS **Service** för den domän som du vill redigera. 
    
3. På sidan **DNS** för domänen väljer du **Preferences**.
    
4. Välj **Enable Expert Interface**.
    
5. Lägg till den första av de sex CNAME-posterna.
    
    Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
   
    ![Dyn-BP - Konfigurera-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. Välj **Create Record**.
    
    ![Dyn-BP - Konfigurera-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. Lägg till de återstående fem CNAME-posterna.
    
    I avsnittet **Add DNS Record** skapar du en post med värdena från nästa rad i tabellen och väljer sedan Create **Record** igen för att slutföra posten. 
    
    Upprepa proceduren tills du har skapat alla sex CNAME-posterna.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden.
  
1. Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först.
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. På sidan **Zone Level Services** väljer du Dyn Standard DNS **Service** för den domän som du vill redigera. 
    
3. På sidan **DNS** för domänen väljer du **Preferences**.
    
4. Välj **Enable Expert Interface**.
    
5. Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Dyn-BP - Konfigurera-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. Välj **Create Record**.
    
    ![Dyn-BP - Konfigurera-4-2](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på Dyn.com genom att klicka på [den här länken](https://account.dyn.com/dns/). Du uppmanas att logga in först 
    
    ![Dyn-BP-Configure-1-1](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. På sidan **Zone Level Services** väljer du Dyn Standard DNS **Service** för den domän som du vill redigera. 
    
3. På sidan **DNS** för domänen väljer du **Preferences**.
    
4. Välj **Enable Expert Interface**.
    
5. Lägg till den första av de två SRV-posterna.
    
    Gå till avsnittet **Add DNS Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600|SRV|100 1 443 sipdir.online.lync.com. **Värdet MÅSTE sluta med en punkt (.)**<br>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
    |_sipfederationtls._tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **Värdet MÅSTE sluta med en punkt (.)**<br> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Dyn-BP - Konfigurera-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. Välj **Create Record**.
    
    ![Dyn-BP - Konfigurera-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. Lägg till den andra SRV-posten.
    
    I avsnittet **Add DNS Record** skapar du en post med värdena från den andra raden i tabellen och väljer sedan Create **Record** igen för att slutföra posten. 
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
