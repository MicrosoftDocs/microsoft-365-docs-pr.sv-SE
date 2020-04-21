---
title: Skapa DNS-poster för Microsoft med Windows-baserad DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Windows-baserad DNS för Microsoft.
ms.openlocfilehash: 3207a319880a23b71a17e80f3e9e77398fa79ef0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631375"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Skapa DNS-poster för Microsoft med Windows-baserad DNS

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
   
Om du är värd för dina egna DNS-poster med hjälp av Windows-baserad DNS följer du anvisningarna i den här artikeln för att konfigurera posterna för e-post, Skype för företag - Online och så vidare.
  
För att komma igång måste du [hitta dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns) så att du kan uppdatera dem. Om du planerar att synkronisera din lokala Active Directory med Microsoft läser du Även [icke-dirigerbar e-postadress som används som UPN i Active Directory för prem](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problem med e-postflödet eller andra problem när du har lagt till DNS-poster, se [Felsöka problem när du har ändrat ditt domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Hitta dina DNS-poster i Windows-baserad DNS
<a name="BKMK_find_your_dns_1"> </a> Gå till sidan som har DNS-posterna för din domän. Om du arbetar i Windows Server 2008 går du till > **Startkörning**. **Start** Om du arbetar i Windows Server 2012 trycker du på Windows-tangenten och **r**. Skriv **dnsmgmnt.msc**och välj sedan **OK**. Expandera ** \<DNS-servernamnet Framåtslagszoner i DNS-hanteraren\> \>   **. Välj din domän. Nu är du redo att skapa DNS-poster.
   
## <a name="add-mx-record"></a>Lägga till MX-post
<a name="BKMK_add_MX"> </a>

Lägg till en MX-post så att e-post för din domän kommer till Microsoft.
- MX-posten du lägger till innehåller ett värde (värdet **Pekar på adress**) som ser ut ungefär så här: \<MX token\>.mail.protection.outlook.com, där \<MX token\> är ett värde som MSxxxxxxx. 
- Kopiera värdet som anges under Pekar på adress från raden MX i avsnittet Exchange Online på sidan Lägg till DNS-poster i Microsoft. Du ska använda det här värdet i den post som du skapar i den här uppgiften. 
- På sidan DNS-hanteraren för domänen går du till **Action** > **Mail Exchanger (MX)**. Information om hur du hittar den här sidan för domänen finns [i Hitta dina DNS-poster i Windows-baserad DNS](#find-your-dns-records-in-windows-based-dns).  
- Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:** 
    - Värdnamn:  
    - @Address: Klistra in värdet Pekar på-adress som du just kopierade från Microsoft här.  
    - Pref: 
- Välj **Spara ändringar**.
- Ta bort eventuella gamla MX-poster. Om du har några gamla MX-poster för den här domänen som cirkulerar e-post någon annanstans markerar du kryssrutan bredvid varje gammal post och väljer sedan **Ta bort** > **OK**. 
   
## <a name="add-cname-records"></a>Lägga till CNAME-poster
<a name="BKMK_add_CNAME"> </a>

Lägg till de CNAME-poster som krävs för Microsoft. Om ytterligare CNAME-poster visas i Microsoft lägger du till dem enligt samma allmänna steg som visas här.
  
> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. (Om du inte har MDM kan du hoppa över det här steget.) 

- På sidan DNS-hanteraren för domänen går du till **Åtgärd** > **CNAME (CNAME)**.
- Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    - Värdnamn: automatisk upptäckt
    - Typ: 
    - CNAMEAdress: autodiscover.outlook.com
- Välj **O**K.

Lägga till SIP CNAME-posten. 
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME)**. 
- Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    - Värdnamn: sippa
    - Typ: CNAME
    - Adress: sipdir.online.lync.com
- Välj **OK**.

Lägga till Autodiscover CNAME-posten för Skype för företag - Online.  
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME)**. Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    - Värdnamn: lyncdiscover
    - Typ: CNAME
    - Adress: webdir.online.lync.com
- Välj **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Lägga till två CNAME-poster för HANTERING av mobila enheter (MDM) för Microsoft

> [!IMPORTANT]
> Om du har MDM (Mobile Device Management) för Microsoft måste du skapa ytterligare två CNAME-poster. Följ proceduren som du använde för de övriga fyra CNAME-posterna, men ange värden från följande tabell. >(Om du inte har MDM kan du hoppa över det här steget.) 
  

Lägga till MDM Enterpriseregistration CNAME-posten.  
- På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME)**. 
- Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
- Värdnamn: företagsregistrering
- Typ: CNAME
- Adress: enterpriseregistration.windows.net
- Välj **OK**. 

Lägga till MDM Enterpriseenrollment CNAME-posten. 
-  På sidan DNS-hanteraren för domänen går du till **Åtgärd** \> **CNAME (CNAME)**. 
-  Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    - Värdnamn: företagsregistrering
    - Typ: CNAME
    - Adress: enterpriseenrollment-s.manage.microsoft.com
- Välj **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. Lägg i stället till de nödvändiga Microsoft-värdena i den aktuella posten så att du har en *enda* SPF-post som innehåller båda uppsättningarna värden. 
  
Lägg till SPF TXT-posten för din domän för att förhindra skräp i e-posten.
  
- Du kanske redan har andra strängar i TXT-värdet för den här posten (t.ex. strängar för reklamutskick) och det är ok. Låt dessa strängar vara kvar och lägg till den här. Sätt dubbla citattecken runt varje sträng för att separera dem. 
- På sidan DNS-hanteraren för din domän går du till \> **Åtgärdstext (TXT)**. **Action** 
-  Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost.** 
 > [!IMPORTANT]
> I vissa versioner av Windows DNS Manager kan domänen ha konfigurerats så att hemnamnet som standard är standard för den överordnade domänen när du skapar en txt-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

-  Värdtyp: @
-  Posttyp: TXT
-  Adress: v=spf1 include:spf.protection.outlook.com -all 
         
-  Välj **OK**.
   
## <a name="add-srv-records"></a>Lägga till SRV-poster
<a name="BKMK_add_SRV"> </a>

Lägg till de två SRV-poster som krävs för Microsoft.

Lägga till SIP SRV-posten för webbkonferens i Skype för företag - Online.  <br/> 
-  På sidan DNS-hanteraren för din domän går du till **Åtgärd** \> **andra nya poster**. 
-   Välj **Serviceplats (SRV)** i fönstret **Resursposttyp** och välj sedan **Skapa post**. 
-   Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    -  Service: _sip
    -  Protokoll: _tls
    -  Prioritet: 100
    -  Vikt: 1
    -  Hamn: 443
    -  Mål (värdnamn): sipdir.online.lync.com
-  Välj **OK**. 


Lägga till SIP SRV-posten för Skype för företag - Online-federation.  
-  På sidan DNS-hanteraren för din domän går du till **Åtgärd** \> **andra nya poster**.  
-  Välj **Serviceplats (SRV)** i fönstret **Resursposttyp** och välj sedan **Skapa post**. 
-   Kontrollera att fälten är inställda på exakt följande värden i dialogrutan **Ny resurspost:**  
    -  Service: _sipfederationtls
    -  Protokoll: _tcp
    -  Prioritet: 100
    -  Vikt: 1
    -  Hamn: 5061
    -  Mål (värdnamn): sipfed.online.lync.com
-  Välj **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Lägg till en post för att verifiera att du äger domänen, om du inte redan har gjort det
<a name="BKMK_verify"> </a>

Innan du lägger till DNS-posterna för att konfigurera Dina Microsoft-tjänster måste Microsoft bekräfta att du äger domänen du lägger till. Det här gör du genom att lägga till en post enligt stegen nedan.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen, den påverkar ingenting annat. 
  

1. Samla in information från Microsoft.  <br/> 
2. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>. 
3. Välj **Starta installation**i kolumnen **Åtgärder** för den domän som du verifierar på sidan **Domäner** . 
4. På sidan **Lägg till en domän i Microsoft** väljer du **Startsteg 1**. 
5. På sidan **Bekräfta att du äger domänen** väljer du Allmänna **instruktioner**i listrutan Se instruktioner för att utföra det här **steget med** . 
6. Kopiera värdet för Mål eller pekar på-adress i tabellen. Du behöver det i nästa steg. Vi rekommenderar att du kopierar och klistrar in det här värdet så att alla avstånd förblir korrekta.

Lägga till en TXT-post. 
-  På sidan DNS-hanteraren för din domän går du till \> **Åtgärdstext (TXT)**. **Action** 
-   Välj **Redigera**i dialogrutan **Ny resurspost** .  
-  Kontrollera att fälten är inställda på exakt följande värden i området **Anpassade värdnamn** i dialogrutan **Ny resurspost.** 

> [!IMPORTANT] 
> I vissa versioner av Windows DNS Manager kan domänen ha konfigurerats så att hemnamnet som standard är standard för den överordnade domänen när du skapar en txt-post. När du lägger till en TXT-post i det här fallet ska du ange värdnamnet till tomt (inget värde) i stället för att ange det till @ eller domännamnet. 

- Värdnamn: @
- Typ: TXT
- Adress: Klistra in värdet Mål eller pekar på-adress som du just kopierade från Microsoft här.  
- Välj **OK** > **Klar**.

Verifiera din domän i Microsoft.  
> [!IMPORTANT]
> Vänta ungefär 15 minuter innan du gör detta, så att posten du just skapade kan uppdateras över Internet.       

- Gå tillbaka till Microsoft och följ stegen nedan för att begära en verifieringskontroll. Kontrollen används för TXT-posten du lade till i föregående steg. När den hittar rätt TXT-post är domänen verifierad.  
1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
2. Välj **Starta installation**på **Action** sidan Domäner på sidan **Domäner** för den domän som du verifierar . 
3. På sidan **Bekräfta att du äger domänen** väljer du **klar, verifierar nu**och väljer sedan Slutför i bekräftelsedialogrutan . **Finish** 
   
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Icke-dirigerbar e-postadress som används som UPN i din lokala Active Directory
<a name="BKMK_ADNote"> </a>

Om du planerar att synkronisera din lokala Active Directory med Microsoft, bör du se till att Active Directory-användarens huvudnamn (UPN) är ett giltigt domänsuffix och inte ett domänsuffix som inte stöds, till exempel @contoso.local. Om du behöver ändra upn-suffixet läser du Så här förbereder du [en domän som inte kan dirigerbara för katalogsynkronisering](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
