---
title: Skapa DNS-poster på MyDomain för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Läs om hur du verifierar din domän och konfigurerar DNS-poster för e-post, Skype för företag – Online och andra tjänster på MyDomain för Microsoft.
ms.openlocfilehash: 1c6edc1e3ad03b0467c70741d4097cf3a3b5e196
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400418"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a>Skapa DNS-poster på MyDomain för Microsoft


  
 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
> [!CAUTION]
> The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider. 
  
Om du väljer att hantera dina egna Microsoft DNS-poster hos MyDomain trots tjänstbegränsningarna utför du stegen i den här artikeln för att konfigurera DNS-posterna för e-post, Skype för företag – Online o.s.v.
    
När du har lagt till dessa poster på MyDomain är din domän konfigurerad för att fungera med Microsoft-tjänster.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. På raden **Overview** väljer du **DNS**.
    
5. I listrutan **Modify** väljer du **TXT/SPF Record**.
    
6. Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.
    
    ||
    |:-----|
    |**Content** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Välj **Lägg till**.
    
8. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. På raden **Overview** väljer du **DNS**.
    
5. Välj **MX Record** i listrutan **Modify**.
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**Priority**|**Värd**|**Points To: (pekar på)**|
    |:-----|:-----|:-----|
    |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Hämta din \<*domain-key*\> från ditt Microsoft-konto. > [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. Välj **Lägg till**.
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. Om det finns andra befintliga MX-poster väljer du **Remove** i kolumnen **Action** för var och en för att ta bort den. 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. Välj **OK**.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. På raden **Overview** väljer du **DNS**.
    
5. Välj **CNAME Alias** i listrutan **Modify**.
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. Lägg till den första CNAME-posten.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.
    
    |**Värd**|**Points To: (pekar på)**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. Välj **Add** (lägg till) för att lägga till den första posten. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. Lägg till den andra CNAME-posten.
    
    Använd värden från den andra raden i tabellen ovan och välj sedan **Add** (lägg till) för att lägga till den andra posten. 
    
    Lägg till de återstående posterna på samma sätt med värdena från den tredje, fjärde, femte och sjätte raden i tabellen.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md). 
  
1. To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.
    
2. Välj **Domain Central** under **My Favorites**.
    
3. Under **Domain** väljer du namnet på den domän som du vill redigera.
    
4. På raden **Overview** väljer du **DNS**.
    
5. I listrutan **Modify** väljer du **TXT/SPF Record**.
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. Under **Content**, i rutan för den nya posten, skriver du in, eller kopierar och klistrar in, värdet från följande tabell.
    
    |**Content**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. Välj **Lägg till**.
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Microsoft plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq), and you might want to switch to a different DNS hosting provider. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
