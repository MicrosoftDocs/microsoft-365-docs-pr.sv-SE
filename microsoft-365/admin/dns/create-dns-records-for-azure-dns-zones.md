---
title: Skapa DNS-poster för Azure DNS-zoner
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS Zones för Microsoft.
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656873"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Skapa DNS-poster för Azure DNS-zoner

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och så vidare.
  
Det här är de viktigaste posterna att lägga till. 
  
- [Ändra domänens namnserverposter (NS)](#change-your-domains-nameserver-ns-records)
    
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)

- [Lägga till en MX-post så att e-post för din domän kommer till Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Lägga till de fyra CNAME-posterna som krävs för Microsoft](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
När du har lagt till dessa poster på Azure är din domän konfigurerad för att fungera med Microsoft-tjänster.
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för Azure skapade du en resurs grupp i en DNS-zon och kopplade sedan domän namnet till den resurs gruppen. Domän namnet är registrerat i en extern domän registrator; Azure erbjuder inte tjänster för domän registrering.
  
Om du vill verifiera och skapa DNS-poster för din domän i Microsoft måste du först ändra namnservrar hos din domän registrator så att de använder Azure-namnservrar som är tilldelad till din resurs grupp.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden. Ett exempel på en Azure-tilldelad namnservrar visas nedan.
    


**Första Namnserver:** Använd värdet Name Server som tilldelats av Azure.  
**Andra Namnserver:** Använd värdet Name Server som tilldelats av Azure.  

![Azure-BP-omdelegera-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> Du bör använda minst två namnserver poster. Om det finns fler namnservrar på din domän registrators webbplats ska du ta bort dem. 
  
3. Spara ändringarna.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän. 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. I **Sök fältet** på sidan **instrument panel** skriver du in **DNS Zones**. I resultat visningen väljer du **DNS Zones** under **tjänste** delen. När du har omdirigerats väljer du den domän som du vill uppdatera.
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. I rutan **Lägg till post uppsättning** väljer du värden från följande tabell i rutorna för den nya posten. 
    
    (Välj värdena **Type** och **TTL** i list rutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Värde**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |9.1  <br/> |Tider  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Välj **OK**.
  
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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

1. Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. I rutan **Lägg till post uppsättning** väljer du värden från följande tabell i rutorna för den nya posten. 
    
    (Välj värdena **Type** och **TTL** i list rutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Preference**|**E-postutbyte**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |9.1  <br/> |Tider  <br/> |10.3  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto.   [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Om det finns andra MX-poster i avsnittet **MX Records** måste du ta bort dem. 
    
    I området **DNS Zone** väljer du först **MX-postuppsättningen**.
    
    ![Azure-BP-Configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Välj sedan den MX-post som du vill ta bort.
    
    ![Azure-BP-Configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Välj **snabb menyn (...)** och välj sedan **ta bort**.
    
    ![Azure-BP-Configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Välj **Spara**.
    
    ![Azure-BP-Configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>Lägga till de fyra CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Lägg till den första av de fyra CNAME-posterna.
    
    I rutan **Lägg till post uppsättning** skriver du in, eller kopierar och klistrar in, värdena från den första raden i följande tabell i rutorna för den nya posten. 
    
    (Välj värdena **Type** och **TTL** i list rutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |9.1  <br/> |Tider  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |9.1  <br/> |Tider  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |9.1  <br/> |Tider  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-Configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Lägg till de andra tre CNAME-posterna.
    
    Välj **+ Record set** i området **DNS Zone** . I den tomma post uppsättningen skapar du en post med värdena från nästa rad i tabellen och väljer sedan **OK** för att slutföra den posten. 
    
    Upprepa proceduren tills du har skapat alla fyra CNAME-posterna.
    
7.  Skriver Lägga till 2 CNAME-poster för MDM.

> [!IMPORTANT]
> Om du har Mobile Device Management (MDM) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 
  
|**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |9.1  <br/> |Tider  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |9.1  <br/> |Tider  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden. 
  
1. Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. I området **DNS Zone** väljer du txt- **postuppsättningen**.
    
    ![Azure-BP-Configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. I rutorna för den nya post uppsättningen i området **Egenskaper för post uppsättning** väljer du värdena från följande tabell. 
    
    (Välj värdena **Type** och **TTL** i list rutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Värde**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |9.1  <br/> |Tider  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               

    ![Azure-BP-Configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Välj **Spara**.
    
    ![Azure-BP-Configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domän sidan på Azure med [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **instrument panel** i området **alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Record set** i området **DNS Zone** på sidan **Inställningar** för din domän.
    
    ![Azure-BP-Configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Lägg till den första av de två SRV-posterna.
    
    Markera värdena från den första raden i följande tabell i rutorna för den nya posten i avsnittet **Lägg till post uppsättning** . 
    
    (Välj värdena **Type** och **TTL** i list rutan.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Prioritet**|**Vikt**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls  <br/> |SRV  <br/> |9.1  <br/> |Tider  <br/> |100  <br/> |9.1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _sipfederationtls._tcp  <br/> |SRV  <br/> |9.1  <br/> |Tider  <br/> |100  <br/> |9.1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-Configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Lägg till den andra SRV-posten.
    
    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den andra raden i tabellen.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
