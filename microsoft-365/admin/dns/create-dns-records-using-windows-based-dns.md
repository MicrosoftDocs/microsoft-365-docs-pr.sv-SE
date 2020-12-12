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
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster i Windows-baserad DNS för Microsoft.
ms.openlocfilehash: 8202ffe10b4a0ff9c94d863d92fc55c47ebb38d3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656849"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Skapa DNS-poster för Microsoft med Windows-baserad DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
   
Om du är värd för dina egna DNS-poster med hjälp av Windows-baserad DNS följer du anvisningarna i den här artikeln för att konfigurera posterna för e-post, Skype för företag - Online och så vidare.
  
För att komma igång måste du [hitta dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns) så att du kan uppdatera dem. Om du planerar att synkronisera den lokala Active Directory med Microsoft kan du läsa mer i [den icke-flyttbara e-postadressen som används som ett UPN i lokala Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problem med e-postflöden eller andra problem när du har lagt till DNS-poster finns i [Felsöka problem efter ändring av domän namn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Hitta dina DNS-poster i Windows-baserad DNS
<a name="BKMK_find_your_dns_1"></a> Gå till sidan som innehåller DNS-posterna för din domän. Om du arbetar i Windows Server 2008 går du till **Start**  >  **Kör**. Om du arbetar i Windows Server 2012 trycker du på Windows-tangenten och **r**. Skriv **dnsmgmnt. msc** och välj sedan **OK**. Utöka **\<DNS server name\> \> zoner för vanlig sökning** i DNS-hanteraren. Välj din domän. Nu är du redo att skapa DNS-poster.
   
## <a name="add-mx-record"></a>Lägga till MX-post
<a name="BKMK_add_MX"> </a>

Lägg till en MX-post så att e-post för din domän kommer till Microsoft.
- MX-posten du lägger till innehåller ett värde (värdet **pekar på adress** ) som ser ut ungefär så här: \<MX token\> . mail.Protection.Outlook.com, där \<MX token\> är ett värde som MSxxxxxxx. 
- Gå till raden MX i avsnittet Exchange Online på sidan Lägg till DNS-poster i Microsoft och kopiera värdet som visas under pekar på adress. Det här värdet ska användas i den post som du skapar i den här uppgiften. 
- På sidan DNS-hanteraren för domänen går du till **Action**  >  **Mail Exchanger (MX)**. Information om hur du hittar den här sidan för domänen finns i [hitta dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns).  
- I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden: 
    - Värdnamn:  
    - @Address: klistra in värdet pekar på adress som du just kopierade från Microsoft här.  
    - Pref: 
- Välj **Spara ändringar**.
- Ta bort eventuella gamla MX-poster. Om du har några gamla MX-poster för den här domänen som dirigerar e-post till någon annan plats markerar du kryss rutan bredvid varje gammal post och väljer sedan **ta bort**  >  **OK**. 
   
## <a name="add-cname-records"></a>Lägga till CNAME-poster
<a name="BKMK_add_CNAME"> </a>

Lägg till de CNAME-poster som krävs för Microsoft. Om ytterligare CNAME-poster visas i Microsoft lägger du till dem som följer samma allmänna steg som visas här.
  
> [!IMPORTANT]
> Om du har Mobile Device Management (MDM) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 

- På sidan DNS-hanteraren för domänen går du till **Action**  >  **CNAME (CNAME)**.
- I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: Autodiscover
    - Format 
    - CNAMEAddress: autodiscover.outlook.com
- Välj **O** K.

Lägga till SIP CNAME-posten. 
- På sidan DNS-hanteraren för domänen går du till **Action** \> **CNAME (CNAME)**. 
- I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: SIP
    - Typ: CNAME
    - Adress: sipdir.online.lync.com
- Välj **OK**.

Lägga till Autodiscover CNAME-posten för Skype för företag - Online.  
- På sidan DNS-hanteraren för domänen går du till **Action** \> **CNAME (CNAME)**. I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: Lyncdiscover
    - Typ: CNAME
    - Adress: webdir.online.lync.com
- Välj **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Lägga till två CNAME-poster för MDM (Mobile Device Management) för Microsoft

> [!IMPORTANT]
> Om du har Mobile Device Management (MDM) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. > (om du inte har MDM kan du hoppa över det här steget.) 
  

Lägga till MDM Enterpriseregistration CNAME-posten.  
- På sidan DNS-hanteraren för domänen går du till **Action** \> **CNAME (CNAME)**. 
- I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
- Värdnamn: enterpriseregistration
- Typ: CNAME
- Adress: enterpriseregistration.windows.net
- Välj **OK**. 

Lägga till MDM Enterpriseenrollment CNAME-posten. 
-  På sidan DNS-hanteraren för domänen går du till **Action** \> **CNAME (CNAME)**. 
-  I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: EnterpriseEnrollment
    - Typ: CNAME
    - Adress: enterpriseenrollment-s.manage.microsoft.com
- Välj **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden. 
  
Lägg till SPF TXT-posten för din domän för att förhindra skräp i e-posten.
  
- Du kanske redan har andra strängar i TXT-värdet för den här posten (t.ex. strängar för reklamutskick) och det är ok. Låt dessa strängar vara kvar och lägg till den här. Sätt dubbla citattecken runt varje sträng för att separera dem. 
- På sidan DNS-hanteraren för din domän går du till **Åtgärds** \> **text (txt)**. 
-  I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden. 
 > [!IMPORTANT]
> I vissa versioner av Windows DNS Manager kan domänen ha ställts in så att hem namnet används som standard för den överordnade domänen när du skapar en TXT-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

-  Värd typ: @
-  Posttyp: TXT
-  Address: v = spf1 inkluderar include SPF. Protection. Outlook. com-alla 
         
-  Välj **OK**.
   
## <a name="add-srv-records"></a>Lägga till SRV-poster
<a name="BKMK_add_SRV"> </a>

Lägg till de två SRV-poster som krävs för Microsoft.

Lägga till SIP SRV-posten för webbkonferens i Skype för företag - Online.  <br/> 
-  På sidan DNS-hanteraren för din domän går du till **åtgärda** \> **andra nya poster**. 
-   I fönstret **resurs post typ** väljer du **service Location (SRV)** och väljer sedan **skapa post**. 
-   I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Tjänst: _sip
    -  Protokoll: _tls
    -  Prioritet: 100
    -  Vikt: 1
    -  Port: 443
    -  Mål (värdnamn): sipdir.online.lync.com
-  Välj **OK**. 


Lägga till SIP SRV-posten för Skype för företag - Online-federation.  
-  På sidan DNS-hanteraren för din domän går du till **åtgärda** \> **andra nya poster**.  
-  I fönstret **resurs post typ** väljer du **service Location (SRV)** och väljer sedan **skapa post**. 
-   I dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Tjänst: _sipfederationtls
    -  Protokoll: _tcp
    -  Prioritet: 100
    -  Vikt: 1
    -  Port: 5061
    -  Mål (värdnamn): sipfed.online.lync.com
-  Välj **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Lägg till en post för att verifiera att du äger domänen, om du inte redan har gjort det
<a name="BKMK_verify"> </a>

Innan du lägger till DNS-posterna för att konfigurera Microsoft-tjänsterna måste Microsoft bekräfta att du äger den domän som du lägger till. Det här gör du genom att lägga till en post enligt stegen nedan.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen, den påverkar ingenting annat. 
  

1. Samla in information från Microsoft.  <br/> 
2. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>. 
3. Välj **Starta installation** i kolumnen **åtgärder** för den domän du verifierar på sidan **Domains** . 
4. På sidan **Lägg till en domän till Microsoft** väljer du **Starta steg 1**. 
5. På sidan **Bekräfta att du äger din domän** , i list rutan **Se anvisningar för att utföra det här steget med** , väljer du **allmänna instruktioner**. 
6. Kopiera värdet för Mål eller pekar på-adress i tabellen. Du behöver det i nästa steg. Vi rekommenderar att du kopierar och klistrar in det här värdet så att alla avstånd förblir korrekta.

Lägga till en TXT-post. 
-  På sidan DNS-hanteraren för din domän går du till **Åtgärds** \> **text (txt)**. 
-   I dialog rutan **Ny resurs post** väljer du **Redigera**.  
-  I området **anpassade värd namn** i dialog rutan **Ny resurs post** kontrollerar du att fälten är inställda på exakt följande värden. 

> [!IMPORTANT] 
> I vissa versioner av Windows DNS Manager kan domänen ha ställts in så att hem namnet används som standard för den överordnade domänen när du skapar en TXT-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

- Värdnamn: @
- Skriv: TXT
- Adress: klistra in värdet för mål eller pekar på-adress som du just kopierade från Microsoft här.  
- Välj **OK**  >  **klar**.

Verifiera din domän i Microsoft.  
> [!IMPORTANT]
> Vänta i ungefär 15 minuter innan du gör det så att den post som du just skapade kan uppdateras på Internet.       

- Gå tillbaka till Microsoft och följ stegen nedan för att begära en verifierings kontroll. Kontrollen används för TXT-posten du lade till i föregående steg. När den hittar rätt TXT-post är domänen verifierad.  
1. Gå till sidan **Konfigurera** domäner i administrations centret \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> .
2. På sidan **Domains** i kolumnen **Action** för den domän du verifierar väljer du **Starta installation**. 
3. På sidan **Bekräfta att du äger din domän väljer du** **klar, verifiera nu** och sedan **Slutför** i bekräftelse dialog rutan. 
   
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Icke-dirigerbar e-postadress som används som UPN i din lokala Active Directory
<a name="BKMK_ADNote"> </a>

Om du planerar att synkronisera den lokala Active Directory med Microsoft, bör du se till att UPN-suffix (User Principal Name) för Active Directory är ett giltigt domänsuffix och inte ett domänsuffix som inte stöds, till exempel @contoso. local. Om du behöver ändra UPN-suffix kan du läsa om [hur du förbereder en icke-routing Domain för Active Directory-synkronisering](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
