---
title: Skapa DNS-poster för Azure DNS-zoner
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Azure DNS-zoner för Office 365.
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807040"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Skapa DNS-poster för Azure DNS-zoner

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Azure är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag och så vidare.
  
Det här är de viktigaste posterna att lägga till. 
  
- [Ändra domänens namnserverposter (NS)](#change-your-domains-nameserver-ns-records)
    
- [Lägga till en TXT-post för verifiering](#add-a-txt-record-for-verification)

- [Lägga till en MX-post så att e-post för din domän kommer till Office 365](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Lägga till de fyra CNAME-poster som krävs för Office 365](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [Lägga till en TXT-post för SPF för att förhindra skräppost](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Lägga till de två SRV-posterna som krävs för Office 365](#add-the-two-srv-records-that-are-required-for-office-365)
    
När du har lagt till dessa poster på Azure konfigureras domänen så att den fungerar med Office 365-tjänster.
  
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> Du måste genomföra anvisningarna hos den domänregistrator där du köpte och registrerade domänen. 
  
När du registrerade dig för Azure skapade du en resursgrupp inom en DNS-zon och tilldelade sedan domännamnet till den resursgruppen. Domännamnet är registrerat hos en extern domänregistrator. Azure erbjuder inte domänregistreringstjänster.
  
Om du vill verifiera och skapa DNS-poster för din domän i Office 365 måste du först ändra namnservrarna hos domänregistratorn så att de använder De Azure-namnservrar som tilldelats resursgruppen.
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa antingen två nya namnserverposter med hjälp av värdena i följande tabell eller ändra de befintliga namnserverposterna så att de matchar följande värden. Ett exempel på Azure-tilldelade namnservrar visas nedan.
    


**Förnamnsserver:** Använd namnservervärdet som tilldelats av Azure.  
**Andra namnserver:** Använd namnservervärdet som tilldelats av Azure.  

![Azure-BP-Redelegate-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> Du bör använda minst två namnserverposter. Om det finns några andra namnservrar listade på domänregistratorns webbplats bör du ta bort dem. 
  
3. Spara ändringarna.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Skriv in **DNS-zoner**med **sökfältet** på **instrumentpanelssidan** . I resultatvisningen väljer du **DNS-zoner** under delen **Tjänster.** När du har omdirigerats markerar du den domän som du vill uppdatera.
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Markera värdena i tabellen **Lägg till postuppsättning** i rutorna för den nya postuppsättningen. 
    
    (Välj enhetsvärden för **typ** och **TTL** i listrutorna.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Värde**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Timmar  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verifiera-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Välj **OK**.
  
6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
    
2. På sidan **Domäner** väljer du den domän som du verifierar. 
    
    
  
3. På **sidan Inställningar** väljer du **Starta installationsprogrammet**.
    
    
  
4. Välj **Verifiera**på **sidan Verifiera domän.**
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

1. Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Markera värdena i tabellen **Lägg till postuppsättning** i rutorna för den nya postuppsättningen. 
    
    (Välj enhetsvärden för **typ** och **TTL** i listrutorna.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Preference**|**Utbyte av e-post**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> |Timmar  <br/> |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Obs:** Hämta din * \<domännyckel\> * från ditt Office 365-konto.   [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-Konfigurera-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Konfigurera-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Om det finns några andra MX-poster i avsnittet **MX Records** måste du ta bort dem. 
    
    Först, i **DNS-zonområdet,** välj **MX Record-uppsättningen**.
    
    ![Azure-BP-Konfigurera-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Markera sedan den MX-post som du vill ta bort.
    
    ![Azure-BP-Konfigurera-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Markera **snabbmenyn (...)** och välj sedan **Ta bort**.
    
    ![Azure-BP-Konfigurera-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Välj **Spara**.
    
    ![Azure-BP-Konfigurera-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a>Lägga till de fyra CNAME-poster som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

1. Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Lägg till den första av de fyra CNAME-posterna.
    
    Skriv eller kopiera värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen i området **Lägg till postuppsättning.** 
    
    (Välj enhetsvärden för **typ** och **TTL** i listrutorna.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1  <br/> |Timmar  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1  <br/> |Timmar  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1  <br/> |Timmar  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-Konfigurera-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Konfigurera-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Lägg till var och en av de andra tre CNAME-posterna.
    
    Välj **+ Postuppsättning i**området **DNS-zon** . Skapa sedan en post med värdena från nästa rad i tabellen i den tomma postuppsättningen och välj återigen **OK** för att slutföra posten. 
    
    Upprepa den här processen tills du har skapat alla fyra CNAME-posterna.
    
7.  (Valfritt) Lägg till 2 CNAME-poster för MDM.

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster. Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 
  
|**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1  <br/> |Timmar  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1  <br/> |Timmar  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
1. Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Markera **TXT-postuppsättningen i** **zonen DNS** .
    
    ![Azure-BP-Konfigurera-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Markera värdena i följande tabell i rutorna för den nya postuppsättningen i området Egenskaper för **postuppsättning.** 
    
    (Välj enhetsvärden för **typ** och **TTL** i listrutorna.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Värde**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Timmar  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               

    ![Azure-BP-Konfigurera-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Välj **Spara**.
    
    ![Azure-BP-Konfigurera-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

1. Gå till domänsidan på Azure med hjälp av [den här länken](https://portal.azure.com ). Du uppmanas att logga in först.
    
    ![Azure-BP-Konfigurera-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. På sidan **Instrumentpanel** i området **Alla resurser** väljer du den domän som du vill uppdatera. 
    
    ![Azure-BP-Konfigurera-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Välj **+ Postuppsättning**i **OMRÅDET DNS-zon** på sidan **Inställningar** för domänen.
    
    ![Azure-BP-Konfigurera-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Lägg till den första av de två SRV-posterna.
    
    I området **Lägg till postuppsättning** markerar du värdena från den första raden i följande tabell i rutorna för den nya postuppsättningen. 
    
    (Välj enhetsvärden för **typ** och **TTL** i listrutorna.) 
    
    |**Name**|**Type (typ)**|**TTL**|**TTL-enhet**|**Priority (prioritet)**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |1  <br/> |Timmar  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |1  <br/> |Timmar  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-Konfigurera-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Välj **OK**.
    
    ![Azure-BP-Konfigurera-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Lägg till den andra SRV-posten.
    
    Skriv eller kopiera värdena från den andra raden i tabellen i rutorna för den nya posten.
    
> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
