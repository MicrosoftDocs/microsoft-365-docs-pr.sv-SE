---
title: Skapa DNS-poster på Freenom för Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Freenom för Microsoft.
ms.openlocfilehash: 39963b5c0f5f3f82fe193160e8aa8ab03894cedd
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049041"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Skapa DNS-poster på Freenom för Microsoft

[Läs frågor och svar om domäner ](../setup/domains-faq.md) om du inte hittar det du letar efter. 
  
> [!CAUTION]
> Freenom-webbplatsen stöder inte SRV-poster, vilket innebär att flera Skype för företag – online och Outlook Web App-funktioner inte fungerar. Oavsett vilket Microsoft-abonnemang du använder finns det betydande tjänstebegränsningar, och du kanske vill byta till en annan DNS-värd. 
  
Om du trots tjänstbegränsningarna väljer att hantera dina egna Microsoft DNS-poster på Freenom följer du stegen i den här artikeln för att verifiera domänen och konfigurera DNS-poster för e-post och andra tjänster.
  
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="bkmk_txt"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/). Du uppmanas att logga in först.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Välj **Tjänster**och välj sedan **Mina domäner**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. För den domän som du vill redigera väljer du **Hantera domän**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Välj **Hantera Freenom DNS**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. I rutorna för den nya posten skriver du in eller kopierar och klistrar in värdena från följande tabell. 
    
    |**Name**|**Type (typ)**|**TTL**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|
    |(lämna tomt)  <br/> |TXT  <br/> |3600 (sekunder)  <br/> |MS=msXXXXXXXX  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Välj **Spara ändringar**.
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
    
  
3. På sidan **Setup** väljer du **Start setup**.
    
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="bkmk_mx"> </a>

1. För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/). Du uppmanas att logga in först.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Välj **Tjänster**och välj sedan **Mina domäner**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. För den domän som du vill redigera väljer du **Hantera domän**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Ange namnet för din domän till standard freenom namnservrar. Välj **Hanteringsverktyg**och välj sedan **Namnservrar**.
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Kontrollera att **Använd standardnamnservrar** är markerat och välj sedan **Ändra namnservrar**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Välj **Hantera Freenom DNS**.
    
    ![Freenom välj Hantera Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Under **Add Record** går du till kolumnen **Type** och väljer **MX** på menyn. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell. 
    
    |**Name**|**Type (typ)**|**TTL**|**Target (mål)**|**Priority (prioritet)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(lämna tomt)  <br/> |MX (Mail Exchanger)  <br/> |3600 (sekunder)  <br/> |\<domännyckeln\>.mail.protection.outlook.com  <br/> **Anm.:** Hämta * \<domännyckeln\> * från ditt Microsoft-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Mer information om prioritet finns i [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Välj **Spara ändringar**.
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Om det finns några andra MX-poster tar du bort dem alla. För varje post väljer du **Ta bort**. När meddelandet Vill du verkligen ta bort den **OK** **här posten?**
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="bkmk_cname"> </a>

1. För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/). Du uppmanas att logga in först.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Välj **Tjänster**och välj sedan **Mina domäner**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. För den domän som du vill redigera väljer du **Hantera domän**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Välj **Hantera Freenom DNS**.
    
    ![Freenom välj Hantera Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Under **Add Record** går du till kolumnen **Type** och väljer **CNAME** på menyn. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Skapa den första CNAME-posten. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från den första raden i tabellen nedan. 
    
    |**Name (namn)**|**Record type (posttyp)**|**TTL**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (sekunder)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Välj **Spara ändringar**.
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Upprepa föregående steg för att skapa de andra fem CNAME-posterna. 
    
    För varje post skriver du in, eller kopierar och klistrar in, värdena från nästa rad i tabellen ovan i rutorna för den posten.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. 

1. För att komma igång, gå till din domänsida i Freenom med hjälp av [denna länk](https://my.freenom.com/). Du uppmanas att logga in först.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Välj **Tjänster**och välj sedan **Mina domäner**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. För den domän som du vill redigera väljer du **Hantera domän**.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Välj **Hantera Freenom DNS**.
    
    ![Freenom välj Hantera Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Under **Add Record** går du till kolumnen **Type** och väljer **TXT** på menyn. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden. 
    
    |**Name (namn)**|**Record type (posttyp)**|**TTL**|**Target (mål)**|
    |:-----|:-----|:-----|:-----|
    |(lämna tomt)  <br/> |TXT  <br/> |3600 (sekunder)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Välj **Spara ändringar**.
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

