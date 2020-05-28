---
title: Skapa DNS-poster hos Hostgator för Microsoft
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster hos Hostgator för Microsoft.
ms.openlocfilehash: 8adfc4b6154dad0da7dd2fe037c73fcfc4f84d58
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400443"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Skapa DNS-poster hos Hostgator för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Hostgator är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
  
> [!IMPORTANT]
> Du måste utföra den första proceduren nedan, [Peka din domän till ditt webbhotell](#point-your-domain-to-your-hosting-account), innan du lägger till DNS-poster med hjälp av någon av de andra procedurerna i den här artikeln. 

När du har gjort alla dessa ändringar hos Hostgator konfigureras domänen så att den fungerar med Microsoft-tjänster.
  

  
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Ange att domänen ska peka på värdkontot
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Du måste utföra den här proceduren innan du utför någon av de andra procedurerna i den här artikeln. 
  
Följ dessa steg för att associera domänen med värdkontona.
  
1. Kom igång genom att gå till domänhanteringssidan på Hostgator genom att klicka på [den här länken](https://portal.hostgator.com/). Du uppmanas att logga in.
    
2. Välj **Domäner** till vänster.
  
3. På sidan **Hantera domäner** väljer du den domän som du vill uppdatera. 
  
4. Välj **Namnservrar**på popup-menyn till vänster .
  
5. På sidan **Namnservrar** för din domän väljer du det värdkonto som är associerat med din domän i listrutan Automatiskt pekar **den här domänen på min värdkonto.** 
  
6. Välj **Spara namnservrar**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Ange att domänen ska peka på värdkontot](#point-your-domain-to-your-hosting-account). 
  
Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. För att komma igång, gå till din cPanel sida på Hostgator. Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. Registreringsmeddelandet du fick från Hostgator anger den adressen, och en **Hosting** cPanel-länk finns också tillgänglig på värdsidan.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång med Microsoft kan du antingen köpa ett värdkonto från Hostgator eller [redigera om dina namnservrar för att peka på Microsoft](change-nameservers-at-hostgator.md). 
  
2. Välj **Avancerad zonredigerare**i området **Domäner** på sidan **Kontrollpanelen** .
    
3. På sidan **Avancerad zonredigerare,** i området **Lägg till en post,** skriver eller kopierar eller klistrar du in värdena från följande tabell i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Använd din *domain_name*. (Till exempel fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress ** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Välj **Lägg till post**.
    
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
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

> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Ange att domänen ska peka på värdkontot](#point-your-domain-to-your-hosting-account). 
  
1. Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. Registreringsmeddelandet du fick från Hostgator anger den adressen, och en **Hosting** cPanel-länk finns också tillgänglig på värdsidan.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång med Microsoft kan du antingen köpa ett värdkonto från Hostgator eller [redigera om dina namnservrar för att peka på Microsoft](change-nameservers-at-hostgator.md). 
  
2. Välj **MX Entry**i området **E-post** på sidan **Kontrollpanelen** .
    
 
3. I området **Email Routing** väljer du **Remote Mail Exchanger**.

4. Välj **Ändra**.
  
5. I området **Lägg till en ny post** skriver eller kopierar eller klistrar du in värdena från följande tabell i rutorna för den nya posten. 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Anm.:** Hämta ditt \< *domain-key*  \> från ditt Microsoft-konto.  [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Välj **Lägg till ny post**.
   
 
7. Om det finns andra MX-poster i avsnittet **MX Records** (MX-poster) tar du bort dem. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Lägga till de sex CNAME-poster som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Ange att domänen ska peka på värdkontot](#point-your-domain-to-your-hosting-account). 
  
1. Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. Registreringsmeddelandet du fick från Hostgator anger den adressen, och en **Hosting** cPanel-länk finns också tillgänglig på värdsidan.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång med Microsoft kan du antingen köpa ett värdkonto från Hostgator eller [redigera om dina namnservrar för att peka på Microsoft](change-nameservers-at-hostgator.md). 
  
2. Välj **Avancerad zonredigerare**i området **Domäner** på sidan **Kontrollpanelen** .
    
3. Lägg till den första av de sex CNAME-posterna.
    
    På sidan **Avancerad zonredigerare,** i området **Lägg till en post,** i rutorna för den nya posten, skriver eller kopierar eller klistrar du in värdena från den första raden i följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (Till exempel autodiscover.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (Till exempel sip.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (Till exempel lyncdiscover.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (Till exempel enterpriseregistration.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (Till exempel enterpriseregistration.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Välj **Lägg till post**.

5. Lägg till de andra fem CNAME-posterna var för sig.
    
    Skapa **en** post i avsnittet Lägg till en post med hjälp av värdena från nästa rad i tabellen och välj sedan **Lägg till post** igen för att slutföra posten. 
    
    Upprepa proceduren tills du har skapat alla sex CNAME-posterna.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten, så att du har en enda SPF-post som innehåller båda uppsättningarna med värden. Behöver du exempel? Ta en titt på dessa [externa DNS-poster för Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). Om du vill validera SPF-posten kan du använda något av dessa [SPF-valideringsverktyg](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Ange att domänen ska peka på värdkontot](#point-your-domain-to-your-hosting-account). 
  
1. Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. Registreringsmeddelandet du fick från Hostgator anger den adressen, och en **Hosting** cPanel-länk finns också tillgänglig på värdsidan.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång med Microsoft kan du antingen köpa ett värdkonto från Hostgator eller [redigera om dina namnservrar för att peka på Microsoft](change-nameservers-at-hostgator.md). 
  
2. Välj **Avancerad zonredigerare**i området **Domäner** på sidan **Kontrollpanelen** .
    
3. Gå till sidan **Advanced DNS Zone Editor** och området **Add a Record**. I den nya postens rutor skriver du in, eller kopierar och klistrar in värdena från följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Använd din *domain_name*. (Till exempel fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
  
4. Välj **Lägg till post**.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Innan du utför den här proceduren måste du först utföra proceduren i det första avsnittet i den här artikeln, [Ange att domänen ska peka på värdkontot](#point-your-domain-to-your-hosting-account). 
  
1. Kom igång genom att gå till sidan cPanel på Hostgator Du uppmanas att logga in först.
    
    (Varje konto på Hostgator har tilldelats en unik cPanel-adress. cPanel-adressen bör se ut ungefär så här: https://YourSiteAddress:secure-port-number. Registreringsmeddelandet du fick från Hostgator anger den adressen, och en **Hosting** cPanel-länk finns också tillgänglig på värdsidan.)
    
    > [!IMPORTANT]
    > Du måste ha ett konto på Hostgator för att associera en cPanel med domänen. För att komma igång med Microsoft kan du antingen köpa ett värdkonto från Hostgator eller [redigera om dina namnservrar för att peka på Microsoft](change-nameservers-at-hostgator.md). 
  
2. Välj **Avancerad zonredigerare**i området **Domäner** på sidan **Kontrollpanelen** .

    
3. Lägg till den första av de två SRV-posterna.
    
    Gå till sidan **Advanced DNS Zone Editor** och området **Add a Record**. I den nya postens rutor skriver du, eller kopierar och klistrar in, värdena från den första raden följande tabell. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    |**Name**|**TTL**|**Type**|**Prioritet**|**Vikt**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*. (Till exempel _sip._tls.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*. (Till exempel _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Välj **Lägg till post**.

  
5. Lägg till den andra SRV-posten.
    
    Skapa **en** post i avsnittet Lägg till en post med hjälp av värdena från nästa rad i tabellen och välj sedan **Lägg till post** igen för att slutföra posten. 
    
> [!NOTE]
> Det brukar ta omkring 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Hitta och åtgärda problem när du har lagt till din domän eller DNS-poster i Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
