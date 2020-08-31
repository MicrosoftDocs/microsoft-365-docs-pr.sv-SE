---
title: Skapa DNS-poster på Amazon Web Services (AWS) för Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Amazon Web Services (AWS) för Microsoft.
ms.openlocfilehash: dbbf82c9c776108c4d5e34e2eb639f9c36e9f28b
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307073"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Skapa DNS-poster på Amazon Web Services (AWS) för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om AWS är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype online för företag och så vidare.
  
När du har lagt till dessa poster på AWS är din domän konfigurerad för att fungera med Microsoft-tjänster.
  

  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **resurser** väljer du **värd zoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** . 
    
4. Välj **skapa post uppsättning**.
    
5. I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten. 
    
    (Välj värdena för **Type** och **Routing Policy** i listrutorna.) 
    
    > [!TIP]
    > Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type (Typ)** <br/> |**Alias** <br/> |**TTL (sekunder)** <br/> |**Värde** <br/> |**Routing Policy (Routningsprincip)** <br/> |
    |(Lämna det här fältet tomt.)  <br/> |TXT - text  <br/> |Nej  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Enkelt  <br/> |
   
6. Välj **skapa**.
    
7. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domän registratorns webbplats kan du gå tillbaka till Microsoft och begära en sökning efter posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft 365
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **resurser** väljer du **värd zoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** . 
    
4. Välj **skapa post uppsättning**.
    
5. I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från följande tabell i fälten för den nya posten. 
    
    (Välj värdena för **Type** och **Routing Policy** i listrutorna.) 
    
    |**Name (Namn)**|**Type (Typ)**|**Alias**|**TTL (sekunder)**|**Värde**|**Routing Policy (Routningsprincip)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |MX - Mail exchange  <br/> |No  <br/> |300  <br/> |0  *\<domain-key\>*  . mail.Protection.Outlook.com.  <br/> 0 motsvarar MX-prioritetsvärdet. Skriv 0 i början av MX-värdet och infoga ett blanksteg före resten av värdet.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **Obs!** Hämta ditt \<*domain-key*\> från ditt Microsoft 365-konto. [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |Enkelt  <br/> |
       
    ![AWS-BP-Configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Välj **skapa**.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Om det finns andra MX-poster tar du bort dem.
    
    > [!IMPORTANT]
    > AWS lagrar MX-poster som en uppsättning som kan innehålla flera poster. Välj **inte** **ta bort post uppsättning**eftersom det här tar bort alla dina MX-poster, inklusive den du just lagt till. Använd följande instruktioner i stället. 
  
    Välj först MX-postuppsättningen.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    I **Edit Record Set** tar du sedan bort inaktuella MX-poster genom att markera respektive post i rutan **Value** och sedan trycka på **Delete** på tangentbordet. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Välj **Save Record set**.
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Lägga till de fem CNAME-poster som krävs för Microsoft 365
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **resurser** väljer du **värd zoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** . 
    
4. Välj **skapa post uppsättning**.
    
5. Lägg till den första CNAME-posten.
    
    I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten. 
    
    (Välj värdena för **Type** och **Routing Policy** i listrutorna.) 
    
    |**Name (Namn)**|**Type (Typ)**|**Alias**|**TTL (sekunder)**|**Värde**|**Routing Policy (Routningsprincip)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |Simple  <br/> |
    |sip  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |Enkelt  <br/> |
    |enterpriseregistration  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |Simple  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical name  <br/> |No  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |Enkelt  <br/> |
   
    ![AWS-BP-Configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Välj **skapa**.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Lägg till de andra fyra CNAME-posterna.
    
    På sidan **Hosted Zones** väljer du **create Record set**, skapar en post med värdena från nästa rad i tabellen och väljer sedan **igen för att** slutföra den posten. 
    
    Upprepa proceduren tills du har skapat alla fem CNAME-poster.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records). Du kan validera SPF-posten genom att använda någon av dessa[SPF-verifierings verktyg](../setup/domains-faq.md). 
  
1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **resurser** väljer du **värd zoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** . 
    
4. Välj **txt** -postuppsättningen. 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. Tryck på Retur på tangentbordet om du vill skapa en ny rad i området **Edit Record Set** i slutet av den aktuella inmatningen i rutan **Value:** för den befintliga posten. Skriv eller kopiera och klistra sedan in värdet från följande tabell på den nya raden (under det befintliga värdet). (Du kan se ett exempel i bilden under tabellen.) 
    
    |**Värde:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (Citattecken som krävs enligt anvisningarna på skärmen anges automatiskt. Du behöver inte skriva in dem manuellt.)  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![AWS-BP-Configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Välj **Save Record set**.
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Lägga till de två SRV-poster som krävs för Microsoft 365
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på AWS genom att klicka på [den här länken](https://console.aws.amazon.com/route53/home). Du uppmanas att logga in först.
    
2. På sidan **resurser** väljer du **värd zoner**.
    
3. Välj namnet på den domän som du vill redigera i kolumnen **domän namn** på sidan **värdbaserade zoner** . 
    
4. Välj **skapa post uppsättning**.
    
5. Lägg till den första SRV-posten:
    
    I **Create Record Set** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i fälten för den nya posten. 
    
    (Välj värdena för **Type** och **Routing Policy** i listrutorna.) 
    
    |**Name (Namn)**|**Type (Typ)**|**Alias**|**TTL (sekunder)**|**Värde**|**Routing Policy (Routningsprincip)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV - Service locator|No|300|100 1 443 sipdir.online.lync.com. **Det här värdet måste sluta med en punkt (.)**><br> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |Enkelt|
    |_sipfederationtls. _tcp|SRV - Service locator|No|300|100 1 5061 sipfed.online.lync.com. **Värdet MÅSTE sluta med en punkt (.)**<br> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |Enkelt|
   
    ![AWS-BP-Configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Välj **skapa**.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. Lägg till den andra SRV-posten:
    
    På sidan **Hosted Zones** väljer du **create Record set**, skapar en post med värdena från nästa rad i tabellen och väljer sedan **igen för att** slutföra den posten. 
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
