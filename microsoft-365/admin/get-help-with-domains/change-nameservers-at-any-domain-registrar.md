---
title: Ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator
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
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Läs om hur du lägger till och konfigurerar din domän i Office 365 så att dina tjänster som e-post och Skype för företag – Online använder ditt eget domännamn.
ms.custom: okr_smb
ms.openlocfilehash: 838025002443ec35787ea91775c60d3829545af4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210498"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>Ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Kontrollera [Konfigurera din domän (värdspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) först för att se om vi har instruktioner för din registrator. 
  
Följ de här anvisningarna om du vill lägga till och konfigurera din domän i Office 365 så att ditt eget domännamn används för tjänster som e-post och Skype för företag - Online. För att göra det måste du verifiera din domän och sedan ändra domänens namnservrar till Office 365, så att rätt DNS-poster kan ställas in åt dig. Följ dessa steg om följande påståenden beskriver din situation:
  
- Du har en egen domän och vill konfigurera den så att den fungerar tillsammans med Office 365.
    
- Du vill att Office 365 ska hantera DNS-poster åt dig. (Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Lägga till en TXT- eller MX-post för verifiering
<a name="BKMK_verify"> </a>

> [!NOTE]
> Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället. 
  
Innan du använder din domän med Office 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Hitta området på din DNS-värds webbplats där du kan skapa en ny post

1. Logga in på din DNS-värds webbplats.
    
2. Välj din domän.
    
3. Gå till den sida där du kan redigera DNS-poster för din domän.
    
### <a name="create-the-record"></a>Skapa posten

Beroende på om du skapar en TXT-post eller en MX-post gör du något av följande:
  
**Om du skapar en TXT-post använder du följande värden:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Record Type** <br/> |**Alias** eller **Host Name** <br/> |**Värde** <br/> |**TTL** <br/> |
|TXT  <br/> |Gör något av följande: skriv **@**, lämna fältet tomt eller skriv domännamnet.  <br/> > [!NOTE]> Olika DNS-värdar har olika krav för det här fältet.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.          [Hur hittar jag detta?](../get-help-with-domains/information-for-dns-records.md)          |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.  <br/> |
   
**Om du skapar en MX-post ska du använda följande värden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** eller **Host Name**|**Värde**|**Prioritet**|**TTL**|
|MX|Skriv antingen **@** eller domännamnet. |MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365.          [Hur hittar jag detta?](../get-help-with-domains/information-for-dns-records.md)          |Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde. Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.md#what-is-mx-priority) |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv. |
   
### <a name="save-the-record"></a>Spara posten

Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Office 365 och begär att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.
    
2. På sidan **Domains** väljer du den domän du verifierar. 
    
  
3. På sidan **Setup** väljer du **Start setup**.
 
    
  
4. På sidan **Verify domain** väljer du **Verify**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Ändra domänens namnserverposter (NS)
<a name="BKMK_nameservers"> </a>

När du kommer till det sista steget i domäninställningsguiden i Office 365 har du en sak kvar att göra. Du slutför konfigurationen av domänen med Office 365-tjänster, t.ex. e-post, genom att ändra namnserverposterna (NS-poster) hos domänregistratorn så att de pekar på de primära och sekundära Office 365-namnservrarna. Eftersom Office 365 fungerar som DNS-värd konfigureras de DNS-poster som behövs för tjänsterna automatiskt. Du kan uppdatera namnserverposterna själv genom att följa anvisningarna från domänregistratorn. Om du inte är bekant med DNS kontaktar du domänregistratorns support.

::: moniker range="o365-worldwide"
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:
    
|||
|:-----|:-----|
|Första namnservern  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Andra namnservern  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > Du bör använda minst två namnserverposter. Om det finns andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **ns3.bdm.microsoftonline.com** och **ns4.bdm.microsoftonline.com**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> Om du ändrar domänens NS-poster så att de pekar mot Office 365-namnservrarna påverkas alla tjänster som är kopplade till domänen. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:
    
|||
|:-----|:-----|
|Första namnservern  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Andra namnservern  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > Du bör använda minst två namnserverposter. Om det finns andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **ns3.dns.partner.microsoftonline.cn** och **ns4.dns.partner.microsoftonline.cn**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet-namnservrar påverkas alla tjänster som för närvarande är associerade med domänen. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end
  
Här följer exempel på några åtgärder som krävs för e-post och webbplatser:
  
- Flytta alla e-postadresser som använder din domän till Office 365 innan du ändrar NS-posterna.
    
- Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com? Du kan vidta följande åtgärder medan du lägger till domänen för att hålla sin webbplats värd där webbplatsen finns nu så att andra fortfarande kan komma till webbplatsen när du har ändrat domänens NS-poster så att den pekar på Office 365.

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

3. Välj en domän på sidan Domäner.

4. Under **DNS-inställningar**väljer du **Anpassade poster**och väljer sedan Ny anpassad **post**.

5. Välj den typ av DNS-post som du vill lägga till och skriv informationen för den nya posten.

6. Välj **Spara**.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Office 365 e-post och andra tjänster klara att fungera med din domän. 
  

