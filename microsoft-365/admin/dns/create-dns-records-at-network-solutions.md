---
title: Skapa DNS-poster på Network Solutions för Microsoft
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Network Solutions för Microsoft.
ms.openlocfilehash: f25e21037695c99489adc9038bf70629a103ec7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910144"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>Skapa DNS-poster på Network Solutions för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Om Network Solutions är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. Följ stegen nedan eller [titta på videon](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099). 
  
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)
    
- [Lägga till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Lägga till CNAME-posterna som krävs för Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster på Network Solutions är domänen konfigurerad för att fungera med Microsoft-tjänster.
  

  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon (börja vid 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Login** (logga in) väljer du Manage My **Domain Names** (hantera mina domännamn) i listrutan Log **In to:.** 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Edit DNS**.
    
    ![Välj Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Manage Advanced DNS Records**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Manage Advanced DNS Records](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Edit TXT Records.**
    
    ![Välj Edit TXT Records](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena i följande tabell.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (Värdet ändras till **@ (None)** när du sparar posten.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Ange eller klistra in värden i rutorna för den nya posten](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan eller [titta på videon (börja vid 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Login** (logga in) väljer du Manage My **Domain Names** (hantera mina domännamn) i listrutan Log **In to:.** 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Edit DNS**.
    
    ![Välj Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Manage Advanced DNS Records**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Manage Advanced DNS Records](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Bläddra ned till **avsnittet Mail Servers (MX Records)** och välj sedan **Edit MX Records.**
    
    ![Välj Edit MX Records](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Priority**|**TTL**|**Mail Server**|
    |:-----|:-----|:-----|
    |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) <br/> |3600  <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **Obs!** Skaffa ditt  *\<domain-key\>*  Microsoft-konto. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Ange eller klistra in värden i rutorna för den nya posten](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. Om det finns andra MX-poster tar du bort alla genom att välja **Delete** för varje post. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. När alla är markerade väljer du **Fortsätt.**
    
    ![Välj Continue](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan eller [titta på videon (börja vid 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Login** (logga in) väljer du Manage My **Domain Names** (hantera mina domännamn) i listrutan Log **In to:.** 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Edit DNS**.
    
    ![Välj Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Manage Advanced DNS Records**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Manage Advanced DNS Records](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Rulla ned till avsnittet **Host Aliases (CNAME Records)** och välj sedan **Edit CNAME Records.**
    
    ![Välj Redigera CNAME-poster under Värdalias](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. I rutorna för de fyra nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Other Host          (välj alternativknappen **Other Host**)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(Ingen inställning)  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |sip  <br/> |3600  <br/> |(Ingen inställning)  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(Ingen inställning)  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(Ingen inställning)  <br/> |enterpriseregistration.windows.net  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(Ingen inställning)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    
    ![Ange eller klistra in värden för de nya posterna](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. När du har lagt till alla CNAME-poster som du behöver väljer du **Continue**.
    
    ![Välj Continue](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden. 
  
Följ stegen nedan eller [titta på videon (börja vid 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Login** (logga in) väljer du Manage My **Domain Names** (hantera mina domännamn) i listrutan Log **In to:.** 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Edit DNS**.
    
    ![Välj Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Manage Advanced DNS Records**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Manage Advanced DNS Records](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Bläddra ned till avsnittet **Text (TXT Records)** och välj sedan **Edit TXT Records.**
    
    ![Välj Edit TXT Records under Text](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.
    
    |**Host**|**TTL**|**Text**|
    |:-----|:-----|:-----|
    |@  <br/> (Värdet ändras till **@ (None)** när du sparar posten.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.     |
       
    ![Ange eller klistra in värden för den nya posten](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan eller [titta på videon (börja vid 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Kom igång genom att gå till domänsidan på Network Solutions med [den här länken](https://www.networksolutions.com/manage-it). Du uppmanas att logga in.
    
    > [!IMPORTANT]
    > Innan du väljer **knappen Login** (logga in) väljer du Manage My **Domain Names** (hantera mina domännamn) i listrutan Log **In to:.** 
  
    ![Välj Hantera mina domännamn och logga in på Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Markera kryssrutan bredvid namnet på den domän som du uppdaterar.
    
    ![Markera kryssrutan för din domän](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Välj **Edit DNS**.
    
    ![Välj Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Välj **Manage Advanced DNS Records**.
    
    (Du kan behöva rulla nedåt.)
    
    ![Välj Manage Advanced DNS Records](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Bläddra ned till avsnittet **Service (SRV Records)** och välj sedan **Edit SRV Records.**
    
    ![Välj Edit SRV Records under Service](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj värdena för **Service** och **Protocol** i listrutorna.) 
    
    |**Service**|**Protocol**|**TTL**|**Prioritet**|**Vikt**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |
       
    ![Ange eller klistra in värden för de nya posterna](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. Välj **Save Changes**.
    
    ![Välj Save Changes](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
