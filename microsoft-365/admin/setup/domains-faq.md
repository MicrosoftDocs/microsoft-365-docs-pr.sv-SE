---
title: Vanliga frågor och svar om domäner
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Läs mer om domäner genom att hitta svar på dina frågor i vanliga frågor.
ms.custom: okr_smb
ms.openlocfilehash: 4ece90306f37b6f07e34ce93423a76f084d50b6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627600"
---
# <a name="domains-faq"></a>Vanliga frågor och svar om domäner

Den här artikeln innehåller svar på vanliga frågor och svar om domäner i Office 365.

Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.
    
## <a name="what-is-mx-priority"></a>Vad är MX-prioritet?

E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet. 
  
- När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.
    
- Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  . 
    
- Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  . 
    
- Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.
    
- Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hur validerar jag SPF-poster för min domän?

Det är viktigt att du har eller skapar **endast en TXT-post för SPF**. Om du redan har en SPF-post ska du lägga till nya Office 365-värden till den istället för att skapa en ny. När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrollera att syntaxen är korrekt med något av följande verktyg: 
  
- [SPF Record Testing Tools](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig web interface](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Hur hanteras mina DNS-poster i Office 365?

Det finns två alternativ för DNS-hantering med Office 365:
  
1. Du ändrar dina NS-poster (Nameserver) och sedan tar Microsoft hand om alla tjänstspecifika poster, till exempel konfigurera din MX-post för e-post. **(Rekommenderas)**
    
2. Du lägger själv till DNS-poster för e-post och andra Office 365-tjänster hos din DNS-värd. **(Endast experter)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 skapar och är värd för DNS-posterna 
**Fördelar** 
- Du behöver inte oroa dig för att göra misstag i de värden du anger för DNS-posterna för Office 365-tjänsterna.  
- Du får fler valmöjligheter när det gäller domänregistrator och DNS-värd. 
- Du kan använda valfri leverantör som låter dig ändra namnserverposterna, även om leverantören inte hanterar alla nödvändiga posttyper.   
- När Office 365 lägger till nya DNS-poster behöver du inte göra uppdateringar.  

#### <a name="disadvantages"></a>Nackdelar 
- Du kan inte ändra dina DNS-poster för e-post utanför Office 365. 
- Om du redan använder en offentlig webbplats med din domän som adress, till exempel www.fourthcoffee.com, måste du dirigera om besökare till den adressen från Office 365. 
- För att kunna konfigurera en omdirigering behöver du en statisk IP-adress, och det är inte alltid lätt att få tag i för offentliga webbplatser. - Om din nuvarande domänregistratorer inte tillåter dig att ändra domänens namnserverposter måste du byta till en annan registrator för att använda det här DNS-hanteringsalternativet.  

 ### <a name="you-manage-the-dns-records-yourself"></a>Du hanterar DNS-posterna själv 
 #### <a name="advantages"></a>Fördelar
- Du styr DNS-posterna för Office 365-tjänsterna.   
- Om du har en offentlig webbplats med din domän som adress, exempelvis www.fourthcoffee.com, behöver du inte tänka på att dirigera om för att folk fortfarande ska kunna använda webbplatsen när du har konfigurerat domänen i Office 365.    
- Du har möjlighet att ha e-post någon annanstans, t.ex. med en lokal Exchange-server.      
 
#### <a name="disadvantages"></a>Nackdelar
Du måste konfigurera DNS-posterna för Office 365-tjänsterna själv (om du inte har en GoDaddy-domän). 
-  Om din nuvarande DNS-värd inte stöder alla nödvändiga posttyper för Microsoft 365 är vissa funktioner inte tillgängliga och du kan behöva byta till en annan DNS-värd. 
- När Office 365 ändrar krav för DNS-poster eller lägger till nya tjänster måste du själv göra uppdateringar hos din DNS-värd. 
   
## <a name="what-is-a-domain-name"></a>Vad är ett domännamn?


En domän är ett unikt namn som visas efter **@** -tecknet i e-postadresser och efter **www.** i webbadresser. Det består vanligen av organisationens namn och ett vanligt Internetsuffix, till exempel  *företagsnamn.com*  eller  *universitetsnamn.edu*  . 
  
Genom att använda en anpassad domän som "**rob\@contoso.com**" med Office 365 kan du skapa trovärdighet och erkännande för ditt varumärke. 
  
Du kan [köpa en domän i Office 365](../get-help-with-domains/buy-a-domain-name.md), som vi konfigurerar automatiskt, eller så kan du köpa eller ta med en du redan äger från en domänregistrator.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>Kan jag överföra en domän som jag har köpt från Microsoft till en annan leverantör?

Ja, men du kan inte överföra en Office 365-domän till en annan registrator förrän 60 dagar efter att du köpte den med Office 365.

Observera att en *Whois-fråga* visar en Office 365-köpt domänregistrare som Wild West Domains LLC. Endast Office 365 bör dock kontaktas angående din köpta Office 365-domän.
  
Följ anvisningarna nedan för att hämta koden på Office 365, och gå sedan till den andra domänregistratorns webbplats för att överföra domännamnet till den registratorn.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Inställningars** > licenser i <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">administrationscentret.</a>

::: moniker-end
    
2. På sidan **Domäner** väljer du den Office 365-domän som du vill överföra till en annan domänregistratorer och väljer sedan **Domänöverföring** > **aktivera domänöverföring**.
       
4. Följ anvisningarna för att förbereda överföringen av domänen.
    
5. När du fått koden går du till webbplatsen för domänregistratorn som du vill hantera domännamnet hos framöver och följer dennes anvisningar för att överföra en domän (sök efter hjälp på domänregistratorns webbplats).
    
6. Om du behöver se koden igen väljer du **Visa auktoriseringskod för domänöverföring**på sidan **Domäninställningar** i Office 365 .
    
7. När överföringen är klar förnyar du domänen hos den nya domänregistraren.
    
8. Slutför processen genom att gå tillbaka till sidan Domäner för **administrationscenter** och välja **Slutför domänöverföring**. 

*Observera att köpta Office 365-domäner inte är berättigade till namnserverändringar eller överföring av domänen mellan Office 365-klienter.  Om något av dessa krävs måste domänregistreringen överföras till en annan registrator.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Hur ändrar jag hur mina DNS-poster hanteras i Office 365?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>Ändra DNS-hanteringen till en DNS-värd utanför Office 365
   
1. Logga in på domänregistratorn för din domän.
    
2. Leta reda på var du uppdaterar namnserverposterna på registratorns webbplats och uppdatera namnservrarna så att de pekar på domänens DNS-värd. (DNS-värden är ofta domänregistratorn.)
    
3. Följ en länk för att gå till installationsguiden för domäner:

::: moniker range="o365-worldwide"

4. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-germany"

4. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

4. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
5. På sidan **Domäner** väljer du den domän du byter och väljer **DNS-hantering**.
    
6. I guiden Konfigurera domäner väljer du Jag ska **hantera mina egna DNS-poster**på sidan **Konfigurera onlinetjänster** och väljer sedan **Nästa**.
    
7. Lägg till de DNS-poster som guiden föreslår på sidan **Uppdatera DNS-inställningar** på registratorns webbplats. 
    
8. När du har lagt till posterna kommer du tillbaka till Office 365 och väljer **Verifiera**.
    

### <a name="change-dns-management-to-office-365"></a>Ändra DNS-hanteringen till Office 365

::: moniker range="o365-worldwide"

1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret..</a>

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
2. På sidan **Domäner** väljer du den domän du byter och väljer **DNS-hantering**.
    
3. I guiden Konfigurera domäner väljer du Konfigurera mina onlinetjänster åt mig på sidan **Konfigurera onlinetjänster.** ** (Rekommenderas)** och välj sedan **Nästa**.
    
4. Om du inte har verifierat domänen ännu, följer du stegen nedan för att göra det först.
    
5. På sidan **Uppdatera DNS-inställningar** visar vi namnservrarna för Office 365. Gå till domänregistratorn för domänen och uppdatera namnservrarna till Office 365-namnservrarna. 
    
4. När du har uppdaterat namnservrarna bör du **vänta i minst en timme**. Välj sedan **Verifiera**i guiden i Office 365.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Vad händer om min DNS-värd inte har stöd för vissa typer av poster?

Om du hanterar dina egna DNS-poster och din DNS-värd inte har stöd för alla DNS-poster som Office 365 kräver kommer vissa funktioner i Office 365 inte att fungera. Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.
  
Värdar som har stöd för alla DNS-poster som krävs:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- Godaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
    
 **Om SRV-poster inte stöds** är följande funktioner i Office 365 inte tillgängliga: 
  
- Integration av Skype för företag - Online-funktioner för snabbmeddelanden och närvaro med Outlook Web App
    
- Extern kommunikation (federering) med Skype för företag - Online-användare i andra organisationer.
    
- Public Internet Connectivity (PIC) med Skype för företag - Online-användare som loggat in med ett Microsoft-konto (hette tidigare Windows Live ID).
    
 **Om flera CNAME-poster inte stöds** måste du välja mellan följande funktioner för Skype för företag – Online: 
  
- E-postklienter och mobila klienter kan använda Autodiscover för att automatiskt hitta Exchange Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.
    
- Skype för företag - Online-skrivbordsklienter kan använda Autodiscover för att automatiskt hitta Skype för företag - Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.
    
- Skype för företag - Online-klienter på mobila enheter kan använda Autodiscover för att automatiskt hitta Skype för företag - Online-tjänsten så att användarna kan logga in utan att behöva ange ett servernamn.
    
 **Om det inte finns stöd för SPF/TXT-poster** kan andra använda din domän för att skicka skräppost eller annan skadlig e-post. SPF-poster identifierar servrarna som är godkända för att skicka e-post från din domän. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Hur anger eller ändrar jag standarddomänen i Office 365?

Du måste ha minst en egen domän som du har lagt till i Office 365 innan du kan välja en standarddomän.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
2. På sidan **Domäner** väljer du den domän som du vill ange som standard för nya e-postadresser. 
    
3. Välj **Ange som standard**.
    
::: moniker range="o365-worldwide"

Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän. 

::: moniker-end

::: moniker range="o365-germany"

Du kan inte ändra *.onmicrosoft.de* namnet på den ursprungliga .onmicrosoft.de-domänen. 

::: moniker-end

::: moniker range="o365-21vianet"

Du kan inte ändra *.partner.onmschina.cn* namnet på den ursprungliga .partner.onmschina.cn-domänen. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Kan jag lägga till egna underdomäner eller flera domäner i Office 365?

::: moniker range="o365-worldwide"

Ja! Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.

::: moniker-end

::: moniker range="o365-germany"

Ja! Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till underdomäner.

::: moniker-end

Vanligtvis kan du lägga till upp till 900 domäner i en Office 365-prenumeration.
  
Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.
  
När du lägger till en underdomän verifieras den automatiskt baserat på den överordnade domänen som verifieras.
  
När du lägger till flera domäner i Office 365 kan du välja att ha valfri tjänst (t.ex. e-post) på valfri domän du har lagt till.  *När du ändrar din e-post till Office 365 genom att uppdatera en domäns MX-post levereras ALL e-post som skickas till den domänen till Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Om du redan har lagt till en contoso.com domän i en Office 365-klientorganisation kan du också lägga till underdomänen xyz.contoso.com till en annan Office 365-klientorganisation. När du lägger till underdomänen uppmanas du att lägga till en TXT-post i DNS-värdleverantören.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Varför har jag en onmicrosoft.com-domän?

Office 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*när du registrerar dig med tjänsten. Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.com*. 
  
 **Om du vill att din e-post ska se ut som *\@alan contoso.com:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till dina användare och domäner i Office 365](add-domain.md) om du äger den redan. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com. Om du vill använda en annan onmicrosoft.com-domän måste du påbörja en ny prenumeration med Office 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.com domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Office 365 måste behålla den eftersom den används i bakgrunden för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
Du kan emellertid fortsätta använda den första onmicrosoft.com-domänen, även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Varför har jag en "onmicrosoft.de"-domän?

Office 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig med tjänsten. Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.de*. 
  
 **Om du vill att din e-post ska se ut *alan@contoso.de:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till användare och domän i Office 365](add-domain.md) om du redan äger den. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den ursprungliga domänen du valde till exempel var fourthcoffee.onmicrosoft.de kan du inte ändra den till fabrikam.onmicrosoft.de. Om du vill använda en annan onmicrosoft.de domän måste du starta en ny prenumeration med Office 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.de domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Office 365 måste behålla den eftersom den används i bakgrunden för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
Du kan fortsätta använda den ursprungliga onmicrosoft.de domänen även efter att du har lagt till domänen. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hur verifierar jag min ideella organisation eller utbildningsstatus?

1. Välj **Installationsprogrammet** i [administrationscentret](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) för att starta guiden. (Var noga med att logga in på Office 365 först.) 
    
2. Om du vill bli administratör för din skola väljer du alternativet **Bli administratör** i Office 365. 
    
3. Du uppmanas att lägga till en TXT DNS-post på DNS-värdwebbplatsen för din domän. Varför? Eftersom du genom att logga in på DNS-värden och lägga till en post för domänen bevisar du för Office 365 att du äger domännamnet.
    
4. När du har lagt till posten går du tillbaka till Office 365-portalen och bekräftar att du har lagt till den, så att Office 365 kan kontrollera.
    
Har du en ideell organisation och vill skaffa Office 365? [Kontrollera att din organisation kvalificerar sig](https://www.microsoft.com/en-us/nonprofits/eligibility) och sedan registrerar dig för tjänsten. 
  
Vill du veta mer om att bli admin för din skola? [Lär dig allt om det](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>Kan jag testa Office 365 med bara några få e-postadresser från min anpassade domän?

Du kan, men det finns begränsningar:
  
- Din nuvarande e-postleverantör måste tillhandahålla vidarebefordran av e-post.
    
- Du måste hantera dina Office 365-relaterade DNS-poster hos din DNS-värd i stället för att office 365 ska hantera dessa poster åt dig. Mer information om vad det innebär finns i Lägga till din domän i Office 365 när du vill hantera dina egna DNS-poster.
    
- Vissa Office 365-funktioner är inte tillgängliga:
- Användare kan inte se ledig/upptagen-information för de användare som finns på den andra e-postleverantören.
- Administratörer kan inte administrera allas konton från ett ställe.
- Användare kanske inte kan använda skräppostfiltrering i Office 365

### <a name="how-to-set-up-an-office-365-pilot"></a>Konfigurera en Office 365-pilot
    
1. Logga in på administrationscentret för Microsoft 365
    
    1. Logga in på Office 365 med ditt arbets- eller skolkonto.
        
    2. Gå till **Inställningar** \> **Domäner**. 
    
2. Kontrollera att du äger den domän du vill använda
    
    1. På sidan **Domäner** väljer du **Lägg till domän**. 
        
    2. Skriv domänen i det här exemplet cohowinery.com på panelen och välj sedan **Nästa**. 
        
    3. Följ steg-för-steg-anvisningarna på sidan **Verifiera** domän. 
        
    4. Välj din DNS-värd i listrutan och följ instruktionerna för att visa att du äger domänen.
        
    5. Välj **Verifiera**. Det tar mellan några minuter och 72 timmar innan DNS-ändringarna börjar gälla. 
        
    6. När verifieringen lyckas blir du ombedd att ändra dina DNS-poster.
    
3. Markera domänen som delad i Exchange Online
    
    1. Gå till **Administrationscentret** för Exchange (EAC). 
        
    2. Välj **Godkända domäner**i avsnittet **E-postflöde** . 
        
    3. Dubbelklicka på den domän som du vill ändra.
        
    4. Välj **Internt relä**i fönstret som öppnas . 
        
    5. Välj **Spara**. Den här inställningen kan kräva några minuter för att börja gälla. 
    
4. Du kan också häva blockeringen av den befintliga e-postservern
    
    1. Office 365 använder Exchange Online Protection (EOP) för skräppostskydd. Om EOP upptäcker en stor mängd skräppost som vidarebefordras av din nuvarande e-postserver kan det blockera den, vilket skulle förhindra att vidarebefordran fungerar. Om du är säker på det skräppostskydd som din andra e-postleverantör använder kan du vitlista deras server i Office 365. Detta gör det dock också möjligt för skräppost som kommer via den ursprungliga servern att komma fram till Office 365-postlådorna, och du kan inte utvärdera hur väl Office 365 förhindrar skräppost.
    
    2. Gå till Administrationscenter för Exchange (EAC).
        
    3. I EAC väljer du **Skydd**och väljer sedan **Anslutningsfilter**. 
        
    4. I **listan TILLÅT**IP **+** väljer du och lägger till IP-adressen för e-postservern som du kan få från din nuvarande e-postleverantör. 
    
5. Skapa användarkonton och ange den primära (svars)adressen
    
    1. Gå till administrationscentret för Microsoft 365.
        
    2. I det vänstra **navigeringsfältet** \> väljer du Aktiva **användare .** 
        
    3. Skapa användarkontona.
        
    4. För varje konto väljer du **+ (Ny)** och fyller i den information som krävs. 
        
    5. Om du vill att användarens e-post ska vara på samma sätt som för närvarande bör fältet **Användarnamn** vara exakt samma som användarens befintliga e-postadress. 
        
    6. Bredvid Användarnamn väljer du ditt eget domännamn i listrutan.
        
    7. Välj **Skapa** \> **stäng**. 
        
6. Uppdatera DNS-poster hos din DNS-värd
    
    1. Logga in på dns-värdleverantörens webbplats och följ [skapa DNS-poster på valfri DNS-värd för Office 365-steg](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Gör följande undantag:**
    
        1. Skapa inte en ny MX-post eller ändra din befintliga MX-post.
            
        2. Om du redan har en SPF-post (Sender Policy Framework) för din tidigare e-postleverantör, i stället för att skapa en ny SPF-post (TXT) för Exchange Online, lägger du bara till "include:spf.protection.outlook.com" i den aktuella TXT-posten. Till exempel "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".
            
        3. Om du inte har en SPF-post ännu ändrar du den som rekommenderas av Office 365 för att inkludera domänen för din nuvarande e-postleverantör, plus spf.protection.outlook.com. Detta godkänner utgående meddelanden från båda e-postsystemen.
            
7. Konfigurera vidarebefordran av e-post hos din nuvarande leverantör
    
    1. Konfigurera vidarebefordran för användarnas e-postkonton på din nuvarande e-postleverantör till din onmicrosoft.com domän:
        
    2. Användare A:s postlåda ska vidarebefordras till usera@yourcompany.onmicrosoft.com
        
    3. Användare B:s postlåda ska vidarebefordras till userb@yourcompany.onmicrosoft.com
        
    4. När du slutför det här steget:
        
    5. All e-post som skickas till usera@yourcompany.com och userb@yourcompany.com är tillgänglig i Office 365.
    
    6. Kommentarer:
        
        - Kontakta din nuvarande e-postleverantör för de exakta stegen för att konfigurera vidarebefordran.
            
        - Du behöver inte behålla en kopia av meddelanden hos den aktuella e-postleverantören.
            
        - De flesta leverantörer vidarebefordrar e-post och lämnar avsändarens svarsadress intakt, så att svaren går till den ursprungliga avsändaren.
    
8. Testa e-postflöde
    
    1. Logga in i Outlook Web App med autentiseringsuppgifter för användare A.
        
    2. Utför följande tester:
        
    3. Testa lokal Microsoft-e-post. Skicka till exempel ett e-postmeddelande till användare B. Detta e-postmeddelande bör levereras omedelbart. I det här fallet dirigeras meddelandet inte till användare B-postlådan på den ursprungliga servern eftersom Office 365 ser postlådan som lokal.
        
    4. Testa e-post till någon som är på det andra e-postsystemet. Skicka till exempel ett e-postmeddelande till användare C. Det här e-postmeddelandet ska levereras till användare C:s postlåda på den ursprungliga e-postservern.
        
    5. Från ett externt konto eller från en medarbetares e-postkonto i det andra e-postsystemet kontrollerar du att vidarebefordran är korrekt konfigurerad i det andra e-postsystemet. Från användare C:s origninalserverkonto eller ett Hotmail-konto skickar du till exempel ett e-postmeddelande till användare A och verifierar att det kommer till Användare A:s Office 365-postlåda.
        
9. Flytta postlådeinnehåll
    
    1. Eftersom det bara finns två användare att flytta, och eftersom användare A och användare B båda använder Outlook redan, kan e-postmeddelandet flyttas genom att öppna den gamla . PST-fil i den nya Outlook-profilen och kopiera meddelanden, kalenderobjekt, kontakter, etc. som visas i Importera Outlook-objekt från en Outlook-datafil (.pst). När de har organiserats på rätt platser i Office 365-postlådan kan alla objekt nås från vilken enhet som helst, var som helst.
        
    2. När fler postlådor är inblandade, eller om de anställda inte redan använder Outlook, kan du använda de migreringsverktyg som är tillgängliga i administrationscentret för Exchange. Kom igång genom att gå till administrationscentret för Exchange och följa anvisningarna i Migrera e-post från en IMAP-server till Exchange Online-postlådor.
    
