---
title: Skapa DNS-poster på netregistry för Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på netregistry för Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657809"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Skapa DNS-poster på netregistry för Microsoft

[Läs frågor och svar om domäner](../setup/domains-faq.yml) om du inte hittar det du letar efter. 
  
Om netregistry är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.
  
Det här är de viktigaste posterna att lägga till:
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägga till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Lägga till CNAME-posterna som krävs för Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster på netregistry är domänen konfigurerad för att fungera med Microsoft-tjänster.
  
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="bkmk_txt"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/). Du uppmanas att logga in.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Välj **Hantera** bredvid den domän som du vill hantera.
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Välj **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. Under **Lägg till en zonfil** väljer du **txt Record** i listan och väljer sedan **Skapa ny post**.
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > Du måste använda citat tecken före och efter posten i TXT-rutan. 
  
    Skriv eller kopiera och klistra in värdena från följande tabell i formuläret **ny TXT-post** . 
    
    |**Namn**|**TTL (SEK)**|**TXT (pekar på adress eller värde)**|
    |:-----|:-----|:-----|
    |(lämna tomt)  <br/> |3600 (sekunder)  <br/> |"MS = msXXXXXXXX"  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Välj **Add Record**.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="bkmk_mx"> </a>

1. För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/). Du uppmanas att logga in.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Välj **Hantera** bredvid den domän som du vill hantera.
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Välj **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. Under **aktuella zondata** tar du bort de förvalda MX-posterna genom att välja **ta bort** bredvid varje MX-post i listan. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. Under **Lägg till en zonfil** väljer du **MX Record** i listan och väljer sedan **Skapa ny post**.
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. Skriv in, eller kopiera och klistra in, värdena från följande tabell i det **nya MX Record** -formuläret. 
    
    |**Namn**|**TTL (SEK)**|**Utbyte (pekar på adress eller värde)**|**Är värden fullt kvalificerad?**|**Preferens (prioritet)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(lämna tomt)  <br/> |3600 (sekunder)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)      |(Markera kryss rutan)  <br/> |10.3  <br/> Mer information om prioritet finns i Vad är MX-prioritet?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Välj **Add Record**.
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="bkmk_cname"> </a>

1. För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/). Du uppmanas att logga in.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Välj **Hantera** bredvid den domän som du vill hantera.
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Välj **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. Under  **Lägg till en zonfil** väljer du **CNAME-post** i listan och väljer sedan **Skapa ny post**.
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell.
    
    |**Name (namn)**|**Type (typ)**|**TTL**|**VÄRD (pekar på eller adress värde)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Välj **Add Record**.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Upprepa föregående steg för att skapa de andra fem CNAME-posterna.
    
    För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.
  
1. För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/). Du uppmanas att logga in.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Välj **Hantera** bredvid den domän som du vill hantera.
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Välj **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. Under **Lägg till en zonfil** väljer du **txt Record** i listan och väljer sedan **Skapa ny post**.
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    > [!NOTE]
    > Du måste använda citat tecken före och efter posten i TXT-rutan. 
  
    |**Name**|**Type (typ)**|**TTL**|**TXT-data (mål)**|
    |:-----|:-----|:-----|:-----|
    |(lämna tomt)  <br/> |TXT  <br/> |3600 (sekunder)  <br/> |"v = spf1 inkluderar include SPF. Protection. Outlook. com-all"  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Välj **Add Record**.
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="bkmk_srv"> </a>

1. För att komma igång går du till sidan domäner i netregistry med [den här länken](https://theconsole.netregistry.com.au/). Du uppmanas att logga in.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Välj  **Hantera** bredvid den domän som du vill hantera.
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Välj **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. Under  **Lägg till en zonfil** väljer du **SRV-post** i listan och väljer sedan **Skapa ny post**.
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    > [!NOTE]
    > Fältet Name är en kombination av tjänsten (till exempel _sip) och protokoll (till exempel _tls). 
  
    |**Type (typ)**|**Namn**|**TTL (SEK)**|**Prioritet**|**Vikt**|**Port**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (tjänst)  <br/> |_sip _sip._tls  <br/> |3600 (sekunder)  <br/> |100  <br/> |9.1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (tjänst)  <br/> |_sipfederationtls _sipfederationtls._tcp  <br/> |3600 (sekunder)  <br/> |100  <br/> |9.1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Välj **Add Record**.
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Upprepa stegen för att skapa den andra SRV-posten.
    
    I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  

