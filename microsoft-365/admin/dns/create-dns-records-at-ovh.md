---
title: Skapa DNS-poster för Office 365 hos OVH
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på OVH för Office 365.
ms.openlocfilehash: 3ba4e61c875f74a0a6cf76c8b7cd82ea88e0221b
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211116"
---
# <a name="create-dns-records-at-ovh-for-office-365"></a>Skapa DNS-poster för Office 365 hos OVH

[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter. 
  
Om OVH är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype for Business Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. 
  
- [Skapa DNS-poster på OVH för Office 365](#create-dns-records-at-ovh-for-office-365)
    
- [Lägga till en MX-post så att e-post för din domän kommer till Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Lägg till CNAME-posterna som krävs för Office 365](#add-the-cname-records-that-are-required-for-office-365)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
När du har lagt till dessa poster på OVH är din domän konfigurerad för att fungera med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="bkmk_txt"> </a>

Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domäner**väljer du namnet på den domän som du vill redigera.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Välj **DNS-zon**.
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Välj **Lägg till en post**.
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Välj **TXT**
    
    ![OVH välj TXT-post](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan. 
    
    |**Record type**|**Underdomän**|**TTL**|**Värde**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(lämna tomt)  <br/> |3600 (sekunder)  <br/> |MS=msxxxxxxxx  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Välj **Bekräfta**. 
    
    ![OVH confirm TXT for verification](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="bkmk_mx"> </a>

1. Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domäner**väljer du namnet på den domän som du vill redigera.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Välj **DNS-zon**.
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Välj **Lägg till en post**.
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Välj **MX**.
    
    ![OVH MX record type](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell. Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan. 
    
    > [!NOTE]
    > Som standard använder OVH relativ notation för målet, som lägger till domännamnet i slutet av målposten. Lägg till en punkt i målposten, som visas i tabellen nedan, om du vill använda absolut notation i stället. 
  
    |**Record type**|**Underdomän**|**TTL**|**Priority**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(lämna tomt)  <br/> |3600 (sekunder)  <br/> |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |\<domännyckel\>.mail.protection.outlook.com.  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Office 365-konto.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![OVH MX rekord för post](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Välj **Nästa**.
    
    ![OVH MX record select Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Välj **Bekräfta**.
    
    ![OVH MX record select Confirm](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. Om det finns andra MX-poster kan du ta bort alla i listan på sidan **DNS Zone**. Markera varje post och välj sedan ikonen Papperskorgen **Ta bort** i kolumnen **Åtgärder.** 
    
    ![OVH delete MX record](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Välj **Bekräfta**.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Lägga till CNAME-posterna som krävs för Office 365
<a name="bkmk_cname"> </a>

1. Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domäner**väljer du namnet på den domän som du vill redigera.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Välj **DNS-zon**.
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Välj **Lägg till en post**.
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Välj **CNAME**.
    
    ![OVH add CNAME record type](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. Skapa den första CNAME-posten.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell. Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan. 
    
    |**Record type**|**Sub-domain (Underdomän)**|**Target (mål)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |3600 sekunder  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |3600 sekunder  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |3600 sekunder  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |3600 sekunder  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |3600 sekunder  <br/> |
   
    ![OVH CNAME-post](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Välj **Nästa**.
    
    ![OVH Add CNAME values and select Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Välj **Bekräfta**.
    
9. Upprepa föregående steg för att skapa de andra fem CNAME-posterna.
    
    För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domäner**väljer du namnet på den domän som du vill redigera.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Välj **DNS-zon**.
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Välj **Lägg till en post**.
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Välj **TXT**.
    
6. I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.
    
    |**Record type**|**Underdomän**|**TTL**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(lämna tomt)  <br/> |3600 (sekunder)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![OVH Lägg till TXT-post för SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Välj **Nästa**.
    
    ![OVH Lägg till TXT-post för SPF och välj Nästa](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Välj **Bekräfta**.
    
    ![OVH Add TXT record for SPF and Confirm](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="bkmk_srv"> </a>

1. Kom igång genom att gå till domänsidan på OVH med [den här länken](https://www.ovh.com/manager/). Du uppmanas att logga in först.
    
    ![OVH login](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Under **Domäner**väljer du namnet på den domän som du vill redigera.
    
    ![OVH Select the domain](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Välj **DNS-zon**.
    
    ![OVH select DNS zone](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Välj **Lägg till en post**.
    
    ![OVH Add an entry](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Välj **SRV**.
    
    ![OVH select SRV record type](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Skapa den första SRV-posten.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell. Om du vill tilldela ett TTL-värde väljer du **Anpassad** i listrutan och skriver sedan värdet i textrutan. 
    
    |**Record type**|**Sub-domain (Underdomän)**|**Prioritet**|**Vikt**|**Port**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (sekunder)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (Service)  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (sekunder)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![OVH SRV-rekord](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Välj **Nästa**.
    
    ![OVH SRV record select Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Välj **Bekräfta**.
    
9. Upprepa stegen för att skapa den andra SRV-posten. I rutorna för den andra posten skriver du in, eller kopierar och klistrar in, värdena från den andra raden i tabellen ovan.
    
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
