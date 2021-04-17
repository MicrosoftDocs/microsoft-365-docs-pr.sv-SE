---
title: Skapa DNS-poster för Microsoft med Windows-baserad DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster hos Windows-baserad DNS för Microsoft.
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876355"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Skapa DNS-poster för Microsoft med Windows-baserad DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
   
Om du är värd för dina egna DNS-poster med hjälp av Windows-baserad DNS följer du anvisningarna i den här artikeln för att konfigurera posterna för e-post, Skype för företag - Online och så vidare.
  
För att komma igång måste du hitta [dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns) så att du kan uppdatera dem. Om du planerar att synkronisera din lokala Active Directory med Microsoft kan du även gå till [Icke-dirigerbar e-postadress](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)som används som UPN i din lokala Active Directory.
  
Problem med e-postflöde eller andra problem när du har lagt till DNS-poster, se [Felsöka problem när du har ändrat domännamn eller DNS-poster.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Hitta dina DNS-poster i Windows-baserad DNS
<a name="BKMK_find_your_dns_1"></a> Gå till sidan som innehåller DNS-posterna för din domän. Om du arbetar i Windows Server 2008 går du till **Starta**  >  **kör.** Om du arbetar i Windows Server 2012 trycker du på Windows-tangenten och **r.** Skriv **dnsmgmnt.msc** och välj sedan **OK.** Expandera Zoner för **\<DNS server name\> \> framåtuppslag i DNS-hanteraren.** Välj din domän. Nu är du redo att skapa DNS-poster.
   
## <a name="add-mx-record"></a>Lägga till MX-post
<a name="BKMK_add_MX"> </a>

Lägg till en MX-post så att e-post för din domän kommer till Microsoft.
- MX-posten du lägger till innehåller  ett värde (värdet Pekar på adress) som ser ut ungefär så här: .mail.protection.outlook.com, där är ett värde som \<MX token\> \<MX token\> MSxxxxxxx. 
- Kopiera värdet som visas under Pekar på adress från MX-raden i avsnittet Exchange Online på sidan Add DNS records i Microsoft. Du ska använda det här värdet i den post som du skapar i den här uppgiften. 
- Gå till **Action** Mail Exchanger (MX) på sidan  >  **DNS-hanteraren för domänen.** Information om hur du hittar den här sidan för domänen finns i [Hitta dina DNS-poster i Windows-baserad DNS.](#find-your-dns-records-in-windows-based-dns)  
- I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden: 
    - Värdnamn:  
    - @Address: Klistra in värdet Pekar på-adress som du just kopierade från Microsoft här.  
    - Pref: 
- Välj **Save Changes**.
- Ta bort eventuella gamla MX-poster. Om du har några gamla MX-poster för den här domänen som dirigerar e-post till någon annan plats markerar du kryssrutan bredvid varje gammal post och väljer sedan Ta **bort**  >  **OK.** 
   
## <a name="add-cname-records"></a>Lägga till CNAME-poster
<a name="BKMK_add_CNAME"> </a>

Lägg till de CNAME-poster som krävs för Microsoft. Om det finns ytterligare CNAME-poster i Microsoft lägger du till dem genom att följa samma allmänna anvisningar som visas här.
  
> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 

- Gå till Åtgärd   >  **CNAME (CNAME) på sidan DNS-hanteraren för domänen.**
- I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: autodiscover
    - Typ: 
    - CNAMEAddress: autodiscover.outlook.com
- Välj **O** K.

Lägga till SIP CNAME-posten. 
- Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.** 
- I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: sip
    - Skriv: CNAME
    - Adress: sipdir.online.lync.com
- Välj **OK**.

Lägga till Autodiscover CNAME-posten för Skype för företag - Online.  
- Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.** I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: lyncdiscover
    - Skriv: CNAME
    - Adress: webdir.online.lync.com
- Välj **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Lägga till två CNAME-poster för MDM (Mobile Device Management) för Microsoft

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. >(Om du inte har MDM kan du hoppa över det här steget.) 
  

Lägga till MDM Enterpriseregistration CNAME-posten.  
- Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.** 
- I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
- Värdnamn: enterpriseregistration
- Skriv: CNAME
- Adress: enterpriseregistration.windows.net
- Välj **OK**. 

Lägga till MDM Enterpriseenrollment CNAME-posten. 
-  Gå till Åtgärd  \> **CNAME (CNAME) på sidan DNS-hanteraren för domänen.** 
-  I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: enterpriseenrollment
    - Skriv: CNAME
    - Adress: enterpriseenrollment-s.manage.microsoft.com
- Välj **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg istället till de obligatoriska Microsoft-värdena i den aktuella posten så att du har  *en*  enda SPF-post som innehåller båda uppsättningarna med värden. 
  
Lägg till SPF TXT-posten för din domän för att förhindra skräp i e-posten.
  
- Du kanske redan har andra strängar i TXT-värdet för den här posten (t.ex. strängar för reklamutskick) och det är ok. Låt dessa strängar vara kvar och lägg till den här. Sätt dubbla citattecken runt varje sträng för att separera dem. 
- På sidan DNS-hanteraren för din domän går du till **Action** \> **Text (TXT)**. 
-  I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden. 
 > [!IMPORTANT]
> I vissa versioner av Windows DNS-hanteraren kan domänen ha ställts in så att när du skapar en txt-post blir startdomänens standardnamn den överordnade domänen. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

-  Värdtyp: @
-  Posttyp: TXT
-  Adress: v=spf1 include:spf.protection.outlook.com -all 
         
-  Välj **OK**.
   
## <a name="add-srv-records"></a>Lägga till SRV-poster
<a name="BKMK_add_SRV"> </a>

Lägg till de två SRV-posterna som krävs för Microsoft.

Lägga till SIP SRV-posten för webbkonferens i Skype för företag - Online.  <br/> 
-  På sidan DNS-hanteraren för din domän går du till **Action** \> **Other New Records**. 
-   I fönstret **Typ av resurspost** väljer du **Tjänstplats (SRV)** och väljer sedan **Skapa post.** 
-   I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Tjänst: _sip
    -  Protokoll: _tls
    -  Prioritet: 100
    -  Vikt: 1
    -  Port: 443
    -  Target (Hostname): sipdir.online.lync.com
-  Välj **OK**. 


Lägga till SIP SRV-posten för Skype för företag - Online-federation.  
-  På sidan DNS-hanteraren för din domän går du till **Action** \> **Other New Records**.  
-  I fönstret **Typ av resurspost** väljer du **Tjänstplats (SRV)** och väljer sedan **Skapa post.** 
-   I **dialogrutan Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Tjänst: _sipfederationtls
    -  Protokoll: _tcp
    -  Prioritet: 100
    -  Vikt: 1
    -  Port: 5061
    -  Target (Hostname): sipfed.online.lync.com
-  Välj **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Lägg till en post för att verifiera att du äger domänen, om du inte redan har gjort det
<a name="BKMK_verify"> </a>

Innan du lägger till DNS-posterna för att konfigurera dina Microsoft-tjänster måste Microsoft bekräfta att du äger den domän som du vill lägga till. Det här gör du genom att lägga till en post enligt stegen nedan.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen, den påverkar ingenting annat. 
  

1. Samla in information från Microsoft.  <br/> 
2. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>. 
3. Välj **Start setup** i **kolumnen Actions** för den domän du verifierar på sidan **Domains.** 
4. På sidan **Lägg till en domän i Microsoft** väljer du Starta steg **1.** 
5. Välj **Allmänna instruktioner i listrutan** Se  anvisningar för att utföra det här steget med på sidan Bekräfta att du äger **domänen.** 
6. Kopiera värdet för Mål eller pekar på-adress i tabellen. Du behöver det i nästa steg. Vi rekommenderar att du kopierar och klistrar in det här värdet så att alla avstånd förblir korrekta.

Lägga till en TXT-post. 
-  På sidan DNS-hanteraren för din domän går du till **Action** \> **Text (TXT)**. 
-   Välj **Redigera i dialogrutan Ny** **resurspost.**  
-  I området **För namn på** anpassade värdar i dialogrutan **Ny** resurspost kontrollerar du att fälten är inställda på exakt följande värden. 

> [!IMPORTANT] 
> I vissa versioner av Windows DNS-hanteraren kan domänen ha ställts in så att när du skapar en txt-post blir startdomänens standardnamn den överordnade domänen. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

- Värdnamn: @
- Typ: TXT
- Adress: Klistra in värdet för Mål eller pekar på-adress som du just kopierade från Microsoft här.  
- Välj **OK**  >  **Klar**.

Verifiera din domän i Microsoft.  
> [!IMPORTANT]
> Vänta cirka 15 minuter innan du gör detta så att den post som du nyss skapade kan uppdateras på Internet.       

- Gå tillbaka till Microsoft och följ stegen nedan för att begära en verifieringskontroll. Kontrollen används för TXT-posten du lade till i föregående steg. När den hittar rätt TXT-post är domänen verifierad.  
1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Konfigurera</a> domäner.
2. På sidan **Domains,** i kolumnen **Action** för den domän du verifierar, väljer du **Start setup.** 
3. På sidan **Bekräfta att du äger domänen** väljer du **klar, verifiera** nu och väljer sedan Slutför i **bekräftelsedialogrutan.** 
   
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Icke-dirigerbar e-postadress som används som UPN i din lokala Active Directory
<a name="BKMK_ADNote"> </a>

Om du planerar att synkronisera din lokala Active Directory med Microsoft bör du se till att UPN-suffixet i Active Directory är ett giltigt domänsuffix och inte ett domänsuffix som inte stöds, till exempel @contoso.local. Om du behöver ändra ditt UPN-suffix kan du gå [till Så här förbereder du en icke-dirigerbar domän för katalogsynkronisering.](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>Relaterat innehåll

[Överföra en domän från Micrsoft 365 till en annan värd](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (artikel)

[Pilottesta Microsoft 365 från min egen domän](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (artikel)

[Vanliga frågor och svar](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) om domäner (artikel)