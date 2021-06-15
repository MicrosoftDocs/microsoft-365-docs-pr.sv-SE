---
title: Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Lär dig att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Skype för företag Online använder ditt eget domännamn.
ms.openlocfilehash: 9c26f9afcf17857c4b3b8f05b89253272cf20e56
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924509"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Ändra namnservrar för att konfigurera Microsoft 365 med valfri domänregistrator

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Följ de här anvisningarna för att lägga till och konfigurera din domän i Microsoft 365 så att tjänster som e-post och Teams använder ditt eget domännamn. Det gör du genom att verifiera domänen och sedan ändra domänens namnservrar till Microsoft 365 så att rätt DNS-poster kan ställas in åt dig. Följ de här anvisningarna om följande påståenden beskriver din situation:
  
- Du har en egen domän och vill konfigurera den så att den fungerar med Microsoft 365.
    
- Du vill Microsoft 365 att hantera dina DNS-poster åt dig. (Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Lägga till en TXT- eller MX-post för verifiering

> [!NOTE]
> Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället. 
  
Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Ta reda på var på din DNS-värds webbplats som du kan skapa en ny post

1. Logga in på din DNS-värds webbplats.
    
2. Välj din domän.
    
3. Gå till den sida där du kan redigera DNS-poster för din domän.
    
### <a name="create-the-record"></a>Skapa posten

Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:
  
**Om du skapar en TXT-post använder du följande värden:**
    

|Record type<br/> |Alias eller värdnamn <br/> |Värde <br/> |TTL<br/> |
|:-----|:-----|:-----|:-----|
|TXT  <br/> |Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.  <br/> > [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.           
|MS=ms *XXXXXXXX*  <br/>**Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.  <br/> |
   
**Om du skapar en MX-post ska du använda följande värden:**
    
|Record type|Alias eller värdnamn|Värde|Prioritet|TTL|
|:-----|:-----|:-----|:-----|:-----|
|MX|Skriv antingen **@** eller domännamnet. |MS=ms *XXXXXXXX Obs!* **Det** här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde. Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv. |
   
### <a name="save-the-record"></a>Spara posten

Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.
  
När Microsoft 365 hittar rätt TXT-post är din domän verifierad.
  

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
  
3. På sidan **Setup** väljer du **Start setup**.
 
  
4. På sidan **Verify domain** väljer du **Verify**.
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)

När du kommer till det sista steget i domäninstallationsguiden i Microsoft 365 har du en uppgift kvar. Om du vill konfigurera domänen med Microsoft 365-tjänster som e-post kan du ändra domänens namnserverposter (eller NS-poster) hos domänregistratorn så att de pekar på Microsoft 365 primära och sekundära namnservrar. Eftersom DNS Microsoft 365 inte är värd för, konfigureras sedan de nödvändiga DNS-posterna för dina tjänster automatiskt. Du kan uppdatera namnserverposterna själv genom att följa de steg som domänregistratorn tillhandahåller i hjälpavsnitten på sin webbplats (om det finns några). Om du inte är bekant med DNS kontaktar du supporten hos domänregistratorn.

::: moniker range="o365-worldwide"
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan ändra namnservrar för din domän eller ett område där du kan använda anpassade namnservrar.
    
2. Skapa namnserverposter eller redigera de befintliga namnserverposterna så att de matchar följande värden:

    - Första namnserver: ns1.bdm.microsoftonline.com
    - Andra namnserver: ns2.bdm.microsoftonline.com
    - Tredje namnserver: ns3.bdm.microsoftonline.com
    - Fjärde namnserver: ns4.bdm.microsoftonline.com
      
   
   > [!TIP]
   > Det är bäst att lägga till alla fyra posterna, men om din registrator bara har stöd för två lägger du **ns1.bdm.microsoftonline.com** och **ns2.bdm.microsoftonline.com**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> Om du ändrar domänens NS-poster så att de pekar Microsoft 365 namnservrarna påverkas alla tjänster som är kopplade till domänen. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:

   - Första namnserver: ns1.dns.partner.microsoftonline.cn
   - Andra namnserver: ns2.dns.partner.microsoftonline.cn
    
   > [!TIP]
   > Du bör använda minst två namnserverposter. Om det finns andra namnservrar listade kan du antingen ta bort dem eller ändra dem till **ns3.dns.partner.microsoftonline.cn** och **ns4.dns.partner.microsoftonline.cn**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> Om du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet-namnservrarna påverkas alla tjänster som är kopplade till domänen. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end
  
Här följer exempel på några åtgärder som krävs för e-post och webbplatser:
  
- Flytta alla e-postadresser som använder din domän Microsoft 365 du ändrar NS-posterna.
    
- Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com? När du lägger till domänen kan du vidta åtgärder nedan för att se till att webbplatsen ligger kvar på samma plats så att personer fortfarande kan komma till webbplatsen när du har ändrat domänens NS-poster så att de pekar Microsoft 365.

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

2. Välj en domän på sidan **Domäner**.

3. På sidan med domäninformation väljer du **fliken DNS-poster.**
 
4. Välj **Add record**.

5. Välj A **(Address)** i listrutan Type i fönstret **Add** **a custom DNS record.**

6. I rutan **Host name eller Alias** skriver du **@** .

7. I rutan **IP-adress** skriver du den statiska IP-adressen för den webbplats där den för närvarande finns. Till exempel 172.16.140.1.
    
> [!IMPORTANT]
>  Det måste vara en _statisk_ IP-adress för webbplatsen, inte en _dynamisk_ IP-adress. Kontrollera med webbplatsen som är värd för din webbplats om du vill se till att du får en statisk IP-adress till den offentliga webbplatsen.
   
8. Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.** Fortsätt annars till steg 9.
    
9. Välj **Spara**. 
    
Du kan dessutom skapa en CNAME-post för att kunderna lättare ska kunna hitta till webbplatsen.
  
1.  Välj **Add record**.

3.  Välj **CNAME (Alias)** i listrutan Type i fönstret **Add** **a custom DNS record.**
4.  I rutan **Host name eller Alias** skriver du **www**.
5.  Skriv det **fullständigt kvalificerade** domännamnet (FQDN) för din webbplats i rutan Pekar på adress. Till exempel **contoso.com**.
6.  Om du vill ändra TTL-inställningen för posten väljer du en ny tidslängd i **listrutan TTL.** Fortsätt annars till steg 6.
7.  Välj **Spara**.

När namnserverposterna har uppdaterats så att de pekar på Microsoft är domänkonfigurationen slutförd. E-post dirigeras till Microsoft och trafiken till din webbplatsadress fortsätter att gå till din nuvarande webbplatsvärd.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda på att fungera med din domän. 
  
## <a name="related-content"></a>Relaterat innehåll

[Lägg till DNS-poster för att ansluta din domän](create-dns-records-at-any-dns-hosting-provider.md) (artikel)\
[Hitta och åtgärda problem när du har lagt till din domän eller DNS-register](find-and-fix-issues.md) (artikel)\
[Hantera domäner](index.yml) (länksida)
