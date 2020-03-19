---
title: Skapa DNS-poster för Office 365 med Windows-baserad DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Windows-baserade DNS för Office 365.
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811952"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>Skapa DNS-poster för Office 365 med Windows-baserad DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
   
Om du är värd för dina egna DNS-poster med hjälp av Windows-baserad DNS följer du anvisningarna i den här artikeln för att konfigurera posterna för e-post, Skype för företag - Online och så vidare.
  
För att komma igång måste du [hitta dina DNS-poster i Windows-baserade DNS](#find-your-dns-records-in-windows-based-dns) så att du kan uppdatera dem. Om du planerar att synkronisera din lokala Active Directory med Office 365 läser du även [en icke-dirigerbar e-postadress som används som UPN i din on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problem med e-postflöde eller andra problem när du har lagt till DNS-poster, se [Felsöka problem när du har ändrat domännamnet eller DNS-posterna](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Hitta dina DNS-poster i Windows-baserad DNS
<a name="BKMK_find_your_dns_1"> </a> Gå till sidan som har DNS-posterna för domänen. Om du arbetar i Windows Server 2008 går du till > **Start-Körning**. **Start** Om du arbetar i Windows Server 2012 trycker du på Windows-tangenten och **r**. Skriv **dnsmgmnt.msc**och välj sedan **OK**. Expandera ** \<DNS-servernamn\> \> framåtsökningszoner i  **DNS Manager. Välj din domän. Nu är du redo att skapa DNS-poster.
   
## <a name="add-mx-record"></a>Lägga till MX-post
<a name="BKMK_add_MX"> </a>

Lägg till en MX-post så att e-post för din domän kommer till Office 365.
- MX-posten du lägger till innehåller ett värde (värdet **Pekar på adress**) som ser ut ungefär så här: \<MX token\>.mail.protection.outlook.com, där \<MX token\> är ett värde som MSxxxxxxx. 
- Kopiera värdet som anges under Pekar på adress från RADEN MX i avsnittet Exchange Online på sidan Lägg till DNS-poster i Office 365. Du använder det här värdet i den post som du skapar i den här uppgiften. 
- På sidan DNS Manager för domänen går du till **Action** > **Mail Exchanger (MX).** Information om hur du hittar den här sidan för domänen finns [i Hitta dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns).  
- I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden: 
    - Värdnamn: 
    - @Address: Klistra in värdet Pekar på-adress som du just kopierade från Office 365 här.  
    - Pref: 
- Välj **Spara ändringar**.
- Ta bort eventuella gamla MX-poster. Om du har några gamla MX-poster för den här domänen som dirigerar e-post någon annanstans markerar du kryssrutan bredvid varje gammal post och väljer sedan **Ta bort** > **OK**. 
   
## <a name="add-cname-records"></a>Lägga till CNAME-poster
<a name="BKMK_add_CNAME"> </a>

Lägg till de CNAME-poster som krävs för Office 365. Om det finns ytterligare CNAME-poster i Office 365 lägger du till dem genom att följa samma allmänna anvisningar som visas här.
  
> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster. Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 

- På sidan DNS-hanteraren för domänen går du till **Åtgärd** > **CNAME (CNAME).**
- I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: automatisk upptäckt
    - Typ: 
    - CNAMEAddress: autodiscover.outlook.com
- Välj **O**K.

Lägga till SIP CNAME-posten. 
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME).** 
- I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: sip
    - Typ: CNAME
    - Adress: sipdir.online.lync.com
- Välj **OK**.

Lägga till Autodiscover CNAME-posten för Skype för företag - Online.  
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME).** I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: lyncdiscover
    - Typ: CNAME
    - Adress: webdir.online.lync.com
- Välj **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Lägga till två CNAME-poster för MDM (Mobile Device Management) för Office 365

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Office 365 måste du skapa ytterligare två CNAME-poster. Följ proceduren som används för de andra fyra CNAME-posterna, men använd värdena från följande tabell. >(Om du inte har MDM kan du hoppa över det här steget.) 
  

Lägga till MDM Enterpriseregistration CNAME-posten.  
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME).** 
- I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
- Värdnamn: företagsregistrering
- Typ: CNAME
- Adress: enterpriseregistration.windows.net
- Välj **OK**. 

Lägga till MDM Enterpriseenrollment CNAME-posten. 
-  På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME).** 
-  I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    - Värdnamn: företagsregistrering
    - Typ: CNAME
    - Adress: enterpriseenrollment-s.manage.microsoft.com
- Välj **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden. 
  
Lägg till SPF TXT-posten för din domän för att förhindra skräp i e-posten.
  
- Du kanske redan har andra strängar i TXT-värdet för den här posten (t.ex. strängar för reklamutskick) och det är ok. Låt dessa strängar vara kvar och lägg till den här. Sätt dubbla citattecken runt varje sträng för att separera dem. 
- På sidan DNS-hanteraren för domänen går du till **Action** \> **Text (TXT).** 
-  I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden. 
 > [!IMPORTANT]
> I vissa versioner av Windows DNS Manager kan domänen ha konfigurerats så att hemnamnet standardtill den överordnade domänen när du skapar en txt-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

-  Värdtyp: @
-  Posttyp: TXT
-  Adress: v=spf1 include:spf.protection.outlook.com -all 
         
-  Välj **OK**.
   
## <a name="add-srv-records"></a>Lägga till SRV-poster
<a name="BKMK_add_SRV"> </a>

Lägg till de två SRV-poster som krävs för Office 365.

Lägga till SIP SRV-posten för webbkonferens i Skype för företag - Online.  <br/> 
-  Gå till **Action** \> **Other New Records**på sidan DNS Manager för domänen. 
-   Välj **Serviceplats (SRV)** i fönstret **Resursposttyp** och välj sedan **Skapa post**. 
-   I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Service: _sip
    -  Protokoll: _tls
    -  Prioritet: 100
    -  Vikt: 1
    -  Hamn: 443
    -  Mål (värdnamn): sipdir.online.lync.com
-  Välj **OK**. 


Lägga till SIP SRV-posten för Skype för företag - Online-federation.  
-  Gå till **Action** \> **Other New Records**på sidan DNS Manager för domänen.  
-  Välj **Serviceplats (SRV)** i fönstret **Resursposttyp** och välj sedan **Skapa post**. 
-   I dialogrutan **Ny resurspost** kontrollerar du att fälten är inställda på exakt följande värden:  
    -  Service: _sipfederationtls
    -  Protokoll: _tcp
    -  Prioritet: 100
    -  Vikt: 1
    -  Hamn: 5061
    -  Mål (värdnamn): sipfed.online.lync.com
-  Välj **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Lägg till en post för att verifiera att du äger domänen, om du inte redan har gjort det
<a name="BKMK_verify"> </a>

Innan du kan lägga till DNS-posterna för att konfigurera dina Office 365-tjänster, måste Office 365 bekräfta att du äger den domän som du håller på att lägga till. Det här gör du genom att lägga till en post enligt stegen nedan.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen, den påverkar ingenting annat. 
  

1. Hämta information från Office 365.  <br/> 
2. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a> 
3. Välj **Starta inställningar**i kolumnen **Åtgärder** för den domän som du verifierar på sidan **Domäner.** 
4. Välj **Startsteg 1**på sidan **Lägg till en domän i Office 365.** 
5. Välj **Allmänna instruktioner**i listrutan Se instruktioner för hur du utför det här **steget med** på sidan Bekräfta att du **äger domänsidan.** 
6. Kopiera värdet för Mål eller pekar på-adress i tabellen. Du behöver det i nästa steg. Vi rekommenderar att du kopierar och klistrar in det här värdet så att alla avstånd förblir korrekta.

Lägga till en TXT-post. 
-  På sidan DNS-hanteraren för domänen går du till **Action** \> **Text (TXT).** 
-   Välj **Redigera i**dialogrutan **Ny resurspost.**  
-  Kontrollera att fälten är inställda på exakt följande värden i området **Anpassade värdnamn** i dialogrutan **Ny resurspost.** 

> [!IMPORTANT] 
> I vissa versioner av Windows DNS Manager kan domänen ha konfigurerats så att hemnamnet standardtill den överordnade domänen när du skapar en txt-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

- Värdnamn: @
- Typ: TXT
- Adress: Klistra in värdet Mål eller Pekar på adress som du just kopierade från Office 365 här.  
- Välj **OK** > **klar**.

Verifiera din domän i Office 365.  
> [!IMPORTANT]
> Vänta ungefär 15 minuter innan du gör detta, så posten du just skapade kan uppdatera över Internet.       

- Gå tillbaka till Office 365 och följ stegen nedan för att begära en verifikationskontroll. Kontrollen används för TXT-posten du lade till i föregående steg. När den hittar rätt TXT-post är domänen verifierad.  
1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
2. Välj **Starta inställningar**i kolumnen **Åtgärd** för den domän som du verifierar på sidan **Domäner.** 
3. Välj **klar, verifiera nu**och välj **sedan Slutför**i bekräftelsedialogrutan på fliken **Bekräfta att du äger domänsidan.** 
   
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Icke-dirigerbar e-postadress som används som UPN i din lokala Active Directory
<a name="BKMK_ADNote"> </a>

Om du planerar att synkronisera din lokala Active Directory med Office 365 bör du se till att UPN-suffixet i Active Directory är ett giltigt domänsuffix och inte ett domänsuffix som inte stöds som @contoso.local. Om du behöver ändra ditt UPN-suffix läser du [Så här förbereder du en domän som inte är dirigerbar för katalogsynkronisering](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
