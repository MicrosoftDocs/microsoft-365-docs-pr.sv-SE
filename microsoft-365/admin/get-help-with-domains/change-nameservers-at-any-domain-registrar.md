---
title: Ändra namnservrar för att konfigurera Microsoft 365 med valfri domän registrator
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
description: Lär dig hur du lägger till och konfigurerar din domän i Microsoft 365 så att dina tjänster som e-post och Skype för företag – Online kan använda ditt eget domän namn.
ms.openlocfilehash: a4218b03e3f23ba8bc39c5eb84b42f87a71b9a65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658605"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Ändra namnservrar för att konfigurera Microsoft 365 med valfri domän registrator

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
Markera [Konfigurera din domän (datorspecifika instruktioner)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) först för att se om vi har anvisningar för din registrator. 
  
Följ dessa instruktioner för att lägga till och konfigurera din domän i Microsoft 365 så att dina tjänster som e-post och team kommer att använda ditt eget domän namn. För att göra det verifierar du din domän och ändrar sedan domänens namnservrar till Microsoft 365 så att rätt DNS-poster kan konfigureras för dig. Följ de här anvisningarna om följande påståenden beskriver din situation:
  
- Du har en egen domän och vill konfigurera den så att den fungerar med Microsoft 365.
    
- Du vill att Microsoft 365 ska hantera dina DNS-poster åt dig. (Du kan även välja att [hantera DNS-posterna själv](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Lägga till en TXT- eller MX-post för verifiering
<a name="BKMK_verify"> </a>

> [!NOTE]
> Du skapar bara en av dessa poster. TXT är den vanligaste posttypen, men den stöds inte av vissa DNS-värdar. I sådana fall skapar du en MX-post istället. 
  
Innan du använder din domän med Microsoft 365, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft 365 att du äger domänen.
  
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
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv.  <br/> |
   
**Om du skapar en MX-post ska du använda följande värden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Record Type**|**Alias** eller **Host Name**|**Värde**|**Prioritet**|**TTL**|
|MX|Skriv antingen **@** eller domännamnet. |MS=ms *XXXXXXXX* > [!NOTE]> Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Microsoft 365.           [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)          |Under **Prioritet** anger du en lägre prioritet än den som eventuella befintliga MX-poster har, för att undvika konflikter med den MX-post som används för e-postflöde. Mer information om prioritet finns i [Vad är MX-prioritet?](../setup/domains-faq.yml) |Ställ in det här värdet på **1 timme** eller till motsvarande minuter ( **60** ), sekunder ( **3600** ) osv. |
   
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
<a name="BKMK_nameservers"> </a>

När du kommer till det sista steget i domän installations guiden i Microsoft 365 har du en aktivitet kvar. Om du vill konfigurera din domän med Microsoft 365-tjänster, till exempel e-post, ändrar du domänens namnserver (eller NS-poster) hos din domän registrator för att hänvisa till Microsoft 365 primära och sekundära namnservrar. Eftersom Microsoft 365 är värd för DNS-tjänsten installeras automatiskt de DNS-poster som krävs för dina tjänster. Du kan uppdatera namnserverposterna själv genom att följa de steg som domänregistratorn tillhandahåller i hjälpavsnitten på sin webbplats (om det finns några). Om du inte är bekant med DNS kontaktar du supporten hos domänregistratorn.

::: moniker range="o365-worldwide"
  
Gör så här om du själv vill ändra domänens namnservrar på din domänregistrators webbplats:
  
1. Hitta området på domän registratorns webbplats där du kan ändra namnservrar för din domän eller ett område där du kan använda anpassade namnservrar.
    
2. Skapa namnserver poster eller ändra de befintliga namnserver posterna så att de matchar följande värden:
    
|||
|:-----|:-----|
|Första namnservern  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Andra namnservern  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Tredje namnserver  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Fjärde namnserver  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > Det bästa är att lägga till alla fyra poster, men om din registrator endast stöder två lägger du till **ns1.bdm.microsoftonline.com** och **ns2.bdm.microsoftonline.com**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Microsoft 365-namnservrar påverkas alla tjänster som är associerade till din domän. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Leta reda på var på domänregistratorns webbplats som du kan redigera namnservrar för din domän.
    
2. Skapa två nya namnserverposter eller ändra de befintliga namnserverposterna så att de stämmer överens med följande värden:
    
|||
|:-----|:-----|
|Första namnservern  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Andra namnservern  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > Du bör använda minst två namnserver poster. Om det finns andra namnservrar i listan kan du antingen ta bort dem eller ändra dem till **NS3.DNS.partner.microsoftonline.cn** och **NS4.DNS.partner.microsoftonline.cn**. 
  
3. Spara ändringarna.
    
> [!CAUTION]
> När du ändrar domänens NS-poster så att de pekar på Office 365 som drivs av 21Vianet namnservrar påverkas alla tjänster som är associerade till din domän. Om du hoppade över något steg i guiden, t.ex. att lägga till e-postadresser, eller om du använder domänen för bloggar, varukorgar eller andra tjänster, måste du vidta ytterligare åtgärder så att ändringen inte innebär att tjänster som åtkomst till e-post och den aktuella webbplatsen slutar fungera. 

::: moniker-end
  
Här följer exempel på några åtgärder som krävs för e-post och webbplatser:
  
- Flytta alla e-postadresser som använder domänen till Microsoft 365 innan du ändrar NS-posterna.
    
- Vill du lägga till en domän som för tillfället används med en webbadress som www.fourthcoffee.com? Du kan göra nedan när du lägger till domänen för att behålla webbplatsen där webbplatsen finns, så att andra fortfarande kan komma till webbplatsen efter att du har ändrat domänens NS-poster så att de pekar på Microsoft 365.

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

2. På sidan **domäner** väljer du domänen och sedan **DNS Records**.

3. Under **DNS-inställningar** väljer du **anpassade poster** och väljer sedan **ny anpassad post**.

4. Välj den typ av DNS-post du vill lägga till och ange informationen för den nya posten.

5. Välj **Spara**.
    
> [!NOTE]
> Det kan ta flera timmar innan ändringarna har uppdaterats genom hela DNS-systemet på Internet. Sedan är din Microsoft-e-post och andra tjänster inställda för att fungera med din domän. 
  
