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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Läs mer om domäner genom att hitta svar på dina vanliga frågor.
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068109"
---
# <a name="domains-faq"></a>Vanliga frågor och svar om domäner

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Den här artikeln innehåller svar på vanliga frågor om domäner i Microsoft 365.

Om du inte hittar ett svar på din fråga här, kan du lämna en kommentar om det så lägger vi till det i listan.

I den här artikeln

- [Vad är MX-prioritet?](#what-is-mx-priority)
- [Hur validerar jag SPF-poster för min domän?](#how-can-i-validate-spf-records-for-my-domain)
- [Vad är ett domännamn?](#what-is-a-domain-name)
- [Vad händer om min DNS-värd inte har stöd för vissa typer av poster?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Varför har jag en onmicrosoft.com-domän?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Varför har jag en "onmicrosoft.de"-domän?](#why-do-i-have-an-onmicrosoftde-domain)
- [Hur verifierar jag min ideella organisation eller utbildningsstatus?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Vad är MX-prioritet?

E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet. 
  
- När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.
    
- Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  . 
    
- Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  . 
    
- Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.
    
- Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hur validerar jag SPF-poster för min domän?

Det är viktigt att du bara har eller skapar **en TXT-post för SPF**. Om du redan har en SPF-post bör du lägga till de nya Microsoft 365-värdena i den i stället för att skapa en ny. När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrollera att syntaxen är korrekt med något av följande verktyg: 
  
- [SPF Record Testing Tools](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig web interface](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Vad är ett domännamn?

A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.* 
  
Genom att använda en anpassad domän som "**rob \@ contoso.com**" med Microsoft 365 kan du skapa trovärdighet och erkännande för ditt varumärke. 
  
Du kan [köpa en domän i Microsoft 365 och vi konfigurerar den automatiskt,](../get-help-with-domains/buy-a-domain-name.md)eller så kan du köpa eller ta med en som du redan äger från en domänregistratorer.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Vad händer om min DNS-värd inte har stöd för vissa typer av poster?

Om du hanterar dina egna DNS-poster och DNS-värden inte stöder alla DNS-poster som Microsoft 365 behöver fungerar inte vissa Microsoft 365-funktioner. Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.
  
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
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Hur ställer jag in eller ändrar standarddomänen i Microsoft 365?

Du måste ha minst en anpassad domän som du har lagt till i Microsoft 365 innan du kan välja en standarddomän.

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

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Kan jag lägga till anpassade underdomäner eller flera domäner i Microsoft 365?

::: moniker range="o365-worldwide"

Ja. Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.

::: moniker-end

::: moniker range="o365-germany"

Ja! Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till underdomäner.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Om du vill lägga till underdomäner måste du hantera dina egna DNS-inställningar på registratorns webbplats. Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till underdomäner.

::: moniker-end

Vanligtvis kan du lägga till upp till 900 domäner i din Microsoft 365-prenumeration.
  
Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.
  
När du lägger till en underdomän verifieras den automatiskt baserat på den överordnade domänen som verifieras.
  
När du lägger till flera domäner i Microsoft 365 kan du vara värd för alla tjänster (som e-post) på någon av de domäner som du har lagt till.  *När du ändrar din e-post till Microsoft 365, genom att uppdatera en domäns MX-post, kommer alla e-postmeddelanden som skickas till den domänen att börja komma till Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Om du har lagt till en contoso.com domän i en Microsoft 365-prenumeration kan du även lägga till underdomänen xyz.contoso.com i en annan Microsoft 365-organisation. När du lägger till underdomänen uppmanas du att lägga till en TXT-post i DNS-värdleverantören.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Varför har jag en onmicrosoft.com-domän?

Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*, när du registrerar dig för tjänsten. Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.com*. 
  
 **Om du vill ha din e-post ser ut som *Alan \@ contoso.com:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller bara följa stegen i [Lägg till dina användare och domän till Microsoft 365](add-domain.md) om du äger den redan. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com. Om du vill använda en annan onmicrosoft.com domän måste du starta en ny prenumeration med Microsoft 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.com domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Varför har jag en "onmicrosoft.de"-domän?

Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig för tjänsten. Användar-ID som du skapar när du registrerar dig innehåller domänen, till exempel *alan@contoso.onmicrosoft.de*. 
  
 **Om du vill att din e-post ska se ut *alan@contoso.de:*** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara stegen i [Lägg till dina användare och domäner till Microsoft 365](add-domain.md) om du äger den redan. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den ursprungliga domänen du valde till exempel var fourthcoffee.onmicrosoft.de kan du inte ändra den till fabrikam.onmicrosoft.de. Om du vill använda en annan onmicrosoft.de domän måste du starta en ny prenumeration med Microsoft 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Webbadressen till gruppwebbplatsen baseras på ditt onmicrosoft.de domännamn. På grund av hur SharePoint Online-arkitekturen fungerar kan du tyvärr inte byta namn på gruppwebbplatsen. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Microsoft 365 måste behålla den eftersom den används bakom kulisserna för din prenumeration. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
Du kan fortsätta använda den ursprungliga onmicrosoft.de domänen även efter att du har lagt till domänen. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hur verifierar jag min ideella organisation eller utbildningsstatus?

1. Välj **Installationsprogrammet** i [administrationscentret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden. (Var noga med att logga in på Microsoft 365 först.) 
    
2. Om du vill bli administratör för din skola väljer du alternativet **Bli administratör** i Microsoft 365. 
    
3. Du uppmanas att lägga till en TXT DNS-post på DNS-värdwebbplatsen för din domän. Varför? Eftersom du genom att logga in hos DNS-värden och lägga till en post för domänen bevisar du för Microsoft 365 att du äger domännamnet.
    
4. När du har lagt till posten går du tillbaka till Microsoft 365-portalen och bekräftar att du har lagt till den, så att Microsoft 365 kan kontrollera.
    
Har du en ideell organisation och vill skaffa Microsoft 365? [Kontrollera att din organisation kvalificerar sig](https://www.microsoft.com/en-us/nonprofits/eligibility) och sedan registrerar dig för tjänsten. 
  
Vill du veta mer om att bli admin för din skola? [Lär dig allt om det](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).