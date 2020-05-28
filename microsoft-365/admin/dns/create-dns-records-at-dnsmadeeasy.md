---
title: Skapa DNS-poster på DNSMadeEasy för Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på DNSMadeEasy för Microsoft.
ms.openlocfilehash: db28ac0cb95bd86bc13a1a1ce47f273989aa4436
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400527"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>Skapa DNS-poster på DNSMadeEasy för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om DNSMadeEasy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
När du har lagt till dessa poster på DNSMadeEasy konfigureras domänen så att den fungerar med Microsoft-tjänster.
  

  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
> [!IMPORTANT]
> För DNSMadeEasy-konton köptes domänen som du lade till från en separat domänregistratorer. DNSMadeEasy erbjuder inte domänregistreringstjänster. Din förmåga att logga in på DNSMadeEasy och skapa DNS-posten är tillräckligt bevis på ägande. 
  
1. Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.
    
2. Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
3. På sidan **Hanterad DNS** i området **TXT Records** väljer du **+** () **(Lägg till ny**).
    
    (Du kan behöva rulla nedåt.)
    
4. Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    ||||
    |:-----|:-----|:-----|
    |**Namn** <br/> |**Värde** <br/> |**TTL** <br/> |
    |(Lämna det här fältet tomt.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Välj **Skicka**.
    
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Microsoft och begär posten.
  
När Microsoft hittar rätt TXT-post är din domän verifierad.
  
1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
3. På sidan **Setup** väljer du **Start setup**.
    
4. På sidan **Verify domain** väljer du **Verify**.
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.
    
2. Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
    Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
    ![DNSMadeEasy-BP-Konfigurera-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. På sidan **Hanterad DNS** i området **MX Records** väljer du **(+)** kontrollen ( **Lägg till ny**).
    
    (Du kan behöva rulla nedåt.)
    
    ![DNSMadeEasy-BP-Konfigurera-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Gå till området **Add MX Records**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    (Du kan behöva rulla nedåt.)
    
    |**Namn**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **Anm.:** Hämta ditt \<*domain-key*\> från ditt Microsoft-konto. [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Välj **Skicka**.
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Om det finns andra MX-poster som visas i avsnittet **MX Records** ska du ta bort alla genom att välja dem. 
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. När alla poster är markerade väljer du **Ta bort markerat**.
    
    ![DNSMadeEasy-BP-Konfigurera-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Välj **Ta bort** för att bekräfta ändringarna i dialogrutan Ta **bort MX-poster.** 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Lägga till de fem CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.
    
2. Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
3. På sidan **Hanterad DNS** i området **CNAME Records** väljer du **(+)** kontrollen ( **Lägg till ny**).
    
    (Du kan behöva rulla nedåt.)
    
    ![DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMadeEasy-BP-Configure-3-1 DNSMade](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Lägg till den första av de fem CNAME-posterna.
    
    I den nya postens rutor i området **Add CNAME Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell. 
    
    |**Name**|**Alias to**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Välj **Skicka**.
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Lägg till var och en av de fyra andra CNAME-posterna.
    
    I avsnittet **CNAME-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten. 
    
    Upprepa den här processen tills du har skapat alla fem CNAME-poster.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Om du vill validera SPF-posten kan du använda något av dessa[SPF-valideringsverktyg](../setup/domains-faq.md). 
  
1. Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.
    
2. Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
3. På sidan **Hanterad DNS** i området **TXT Records** väljer du **(+)** kontrollen ( **Lägg till ny**).
    
    (Du kan behöva rulla nedåt.)
    
    ![DNSMadeEasy-BP-Konfigurera-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. Gå till området **Add TXT Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell. 
    
    |**Namn**|**Värde**|**TTL**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |1800  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Välj **Skicka**.
    
    ![DNSMadeEasy-BP-Konfigurera-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på DNSMadeEasy genom att klicka på [den här länken](https://cp.dnsmadeeasy.com/). Du uppmanas att logga in först.
    
2. Välj den domän som du vill uppdatera i området **Nyligen uppdaterade domäner** på sidan **Management Console.** 
    
3. På sidan **Hanterad DNS** i området **SRV Records** på sidan Hanterade DNS väljer du **(+)** kontrollen ( **Lägg till ny**).
    
    (Du kan behöva rulla nedåt.)
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Lägg till den första av de två SRV-posterna.
    
    I den nya postens rutor i området **Add SRV Records** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell. 
    
    |**Name**|**Prioritet**|**Vikt**|**Port**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-Konfigurera-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Välj **Skicka**.
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Lägg till den andra SRV-posten.
    
    I avsnittet **SRV-poster** markerar du **(+)** kontrollen ( **Lägg till ny**), skapar en post med hjälp av värdena från nästa rad i tabellen och väljer sedan **Skicka** igen för att slutföra posten. 
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  

