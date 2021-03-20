---
title: Skapa DNS-poster på Register.com för Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Register.com för Microsoft.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910060"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Skapa DNS-poster på Register.com för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Om Register.com är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. Följ stegen nedan eller [titta på videon](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
- [Lägga till en TXT-post på Register.com för att verifiera att det är din domän](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Lägga till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Lägga till CNAME-posterna som krävs för Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Lägga till de två SRV-posterna som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster Register.com domän är din domän konfigurerad för att fungera med Microsoft-tjänster.
  

  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Lägga till en TXT-post på Register.com för att verifiera att det är din domän
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
Följ stegen nedan eller [titta på videon (börja vid 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.
    
2. Välj **Domäner**.
    
3. Välj **Hantera**.
    
4. Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**
    
5. Bläddra ned till **avsnittet Advanced Technical Settings** och välj sedan Edit TXT Records **(SPF).**
    
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |||
    |:-----|:-----|
    |**Värdnamn** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Välj **Fortsätt.**
    
8. På nästa sida väljer du **Continue igen** för att bekräfta ändringarna. 
    
9. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan eller [titta på videon (börja vid 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.
    
2. Välj **Domäner**.
    
3. Välj **Hantera**.
    
4. Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**
    
5. Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit Mail **Exchanger Records.**
    
    ![Välj Redigera e-postutväxlingsposter](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    (Välj **värdet Priority** i listrutan.) 
    
    |****Host Name****|****Priority****|****E-postserver****|
    |:-----|:-----|:-----|
    |@  <br/> |High  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  <br/>**Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto. <br> [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Kopiera och klistra in värdet från tabellen](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Om det redan finns andra MX-poster som visas, väljer du var och en av posterna och tar bort dem.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna. 
    
    ![Välj Continue](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan eller [titta på videon (börja vid 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.
    
2. Välj **Domäner**.
    
3. Välj **Hantera**.
    
4. Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**
    
5. Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit Domain **Aliases Records**.
    
    ![Välj Edit Domain Aliases Records](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Välj **Lägg till fler domänalias**.
    
    ![Välj Lägg till fler domänalias](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Lägg till nödvändiga CNAME-poster.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    |****First field (unlabeled)****|****Pekar på****|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Kopiera och klistra in DNS-värdena från tabellen](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. När du har lagt till alla CNAME-poster som du behöver väljer du **Continue**.
    
    ![Välj Continue](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna. 
    
    ![Välj Continue](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden.  
  
Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.
    
2. Välj **Domäner**.
    
3. Välj **Hantera**.
    
4. Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**
    
5. Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit TXT Records **(SPF).**
    
    ![Välj Edit TXT Records (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |****Hostname****|****TXT-post****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.      |
   
     ![Kopiera och klistra in värdena från tabellen](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Välj **Fortsätt.**
    
    ![Välj Continue](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna. 
    
    ![Välj Continue](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan eller [titta på videon (börja vid 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Kom igång genom att gå till domänsidan på Register.com med [den här länken](https://www.register.com/myaccount/). Du uppmanas att logga in först.
    
2. Välj **Domäner**.
    
3. Välj **Hantera**.
    
4. Leta reda på raden som innehåller namnet på den domän som du vill ändra. och sedan väljer du Hantera på **den raden.**
    
5. Bläddra till avsnittet **Advanced Technical Settings** och välj sedan Edit **SRV Records**.
    
    ![Välj Edit SRV Records](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Lägg till den första av de två SRV-posterna:
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    (Välj **värdet Priority** i listrutan.) 
    
    |****Service****|****Proto****|****Name****|****Priority****|****Vikt****|****Port****|****Target****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Kopiera och klistra in värdena från tabellen](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Välj **Add more SRV records**.
    
    ![Välj Lägg till fler SRV-poster](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Lägg till den andra SRV-posten:
    
    I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.
    
9. När du har lagt till båda SRV-posterna väljer du **Continue**.
    
    ![Välj Continue](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. På nästa sida väljer du **Fortsätt igen** för att bekräfta och spara ändringarna. 
    
    ![Välj Continue](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
