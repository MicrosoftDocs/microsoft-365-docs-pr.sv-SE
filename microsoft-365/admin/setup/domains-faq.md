---
title: Vanliga frågor och svar om domäner
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
description: Lär dig mer om domäner genom att hitta svar på vanliga frågor.
ms.openlocfilehash: b51b5fe56bbae56dd473dd831ec91e629d9233f3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644590"
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
- [Hur ställer jag in eller ändrar standard domänen i Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Kan jag lägga till egna under domäner eller flera domäner i Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Hur överför jag en domän från Microsoft 365 till en annan värd?](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [Varför har jag en onmicrosoft.com-domän?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Varför har jag en "onmicrosoft.de"-domän?](#why-do-i-have-an-onmicrosoftde-domain)
- [Hur verifierar jag min status som inte vinst eller utbildning?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>Vad är MX-prioritet?

E-post levereras till Exchange-servern med lägst företrädesnummer (högst prioritet). Därför ska den MX-post som du använder för e-postdirigering ha det lägsta företrädesnumret, vanligtvis 0, eller  *hög*  prioritet. 
  
- När du skapar en MX-post måste du ange ett företrädesnummer för de flesta DNS-värdar.
    
- Vissa kallar rutan för  *företräde*  , andra för  *prioritet*  . 
    
- Vissa kräver ett nummer medan andra ber dig att välja mellan  *låg*  ,  *mellan*  eller  *hög*  . 
    
- Om du bara har en MX-post går det bra med vilket värde som helst för prioritet eller företräde.
    
- Om du har fler än en ser du till att MX-posten för e-postdirigering har högre prioritet än den som används för att verifiera att du äger domänen.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Hur validerar jag SPF-poster för min domän?

Det är viktigt att du har eller  **bara skapar en TXT-post för SPF**. Om du redan har en SPF-post ska du lägga till de nya Microsoft 365-värdena i stället för att skapa en ny. När du har lagt till eller uppdaterat SPF-posten för Microsoft-e-post bör du kontrol lera att syntaxen stämmer med något av följande verktyg: 
  
- [SPF Record Testing Tools](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig web interface](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>Vad är ett domännamn?

En domän är ett unikt namn som visas efter **@** -tecknet i e-postadresser och efter **www.** i webbadresser. Det består vanligen av organisationens namn och ett vanligt Internetsuffix, till exempel  *företagsnamn.com*  eller  *universitetsnamn.edu*  . 
  
Om du använder en egen domän som "**anders \@ contoso.com**" med Microsoft 365 kan du skapa trovärdighet och igenkänning för varumärket. 
  
Du kan [köpa en domän i Microsoft 365 och ställa in den automatiskt](../get-help-with-domains/buy-a-domain-name.md), eller så kan du köpa eller ta med en du redan äger från en domän registrator.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>Vad händer om min DNS-värd inte har stöd för vissa typer av poster?

Om du hanterar dina egna DNS-poster och din DNS-värd inte har stöd för alla DNS-poster som Microsoft 365 behöver kommer vissa funktioner i Microsoft 365 inte att fungera. Vi rekommenderar att du för över din domän till en registrator som har stöd för alla DNS-poster som krävs.
  
Värdar som har stöd för alla DNS-poster som krävs:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Hur ställer jag in eller ändrar standard domänen i Microsoft 365?

Du måste ha minst en egen domän som du har lagt till i Microsoft 365 innan du kan välja en standard domän.

::: moniker range="o365-worldwide"

1. I administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till **Inställningar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a>.

::: moniker-end
    
2. På sidan **domäner** väljer du den domän som du vill ange som standard för nya e-postadresser. 
    
3. Välj **Ange som standard**.
    
::: moniker range="o365-worldwide"

Du kan inte ändra namnet på din ursprungliga  *.onmicrosoft.com*  -domän. 

::: moniker-end

::: moniker range="o365-germany"

Du kan inte ändra namnet på din initiala  *onmicrosoft.de*  -domän. 

::: moniker-end

::: moniker range="o365-21vianet"

Du kan inte ändra namnet på din initiala  *partner.onmschina.cn*  -domän. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Kan jag lägga till egna under domäner eller flera domäner i Microsoft 365?

::: moniker range="o365-worldwide"

Ja. Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till under domäner.

::: moniker-end

::: moniker range="o365-germany"

Ja! Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats. Om du låter Microsoft hantera dina DNS-inställningar med NS-poster, eller om du har köpt domänen från Microsoft, kan du inte lägga till under domäner.

::: moniker-end

::: moniker range="o365-21vianet"

Ja! Om du vill lägga till under domäner måste du hantera dina egna DNS-inställningar hos registratorns webbplats. Om du låter 21Vianet hantera dina DNS-inställningar med NS-poster kan du inte lägga till under domäner.

::: moniker-end

Vanligt vis kan du lägga till upp till 900-domäner i din Microsoft 365-prenumeration.
  
Du kan till exempel lägga till domänerna contoso.com och contosomarketing.com, och sedan lägga till underdomänerna www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com och så vidare.
  
När du lägger till en under domän verifieras den automatiskt baserat på den överordnade domänen som verifieras.
  
När du lägger till flera domäner i Microsoft 365 kan du hantera alla tjänster (som e-post) på någon av de domäner som du har lagt till.  *När du ändrar din e-post till Microsoft 365 genom att uppdatera en domäns MX-post kommer ALL e-post som skickas till domänen att komma till Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Om du har lagt till en contoso.com-domän i en Microsoft 365-prenumeration kan du också lägga till under domäns xyz.contoso.com till en annan Microsoft 365-organisation. När du lägger till under domänen uppmanas du att lägga till en TXT-post i DNS-värden.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Hur överför jag en domän från Microsoft 365 till en annan värd?

Information om hur du överför en domän finns i [överföra en domän från Microsoft till en annan värd](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>Pilot Microsoft 365 från min anpassade domän

Anvisningar för hur du piloterar Microsoft 365-e-postfunktioner från en anpassad domän till en Microsoft 365-postlåda finns i [pilot Microsoft 365 From My Custom Domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Varför har jag en onmicrosoft.com-domän?

Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.com*, när du registrerar dig för tjänsten. Det användar-ID som du skapar när du registrerar dig inkluderar domänen, till exempel *Alan@contoso.onmicrosoft.com*. 
  
 **Om du vill att e-postmeddelandet ska se ut som *Alan \@ contoso.com*:** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ instruktionerna i [lägga till användare och domän till Microsoft 365](add-domain.md) om du redan har den. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den initiala domänen du valde till exempel var fourthcoffee.onmicrosoft.com, kan du inte ändra den till fabrikam.onmicrosoft.com. Om du vill använda en annan onmicrosoft.com-domän måste du starta en ny prenumeration med Microsoft 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Din grupp webbplats URL baseras på ditt onmicrosoft.com-domän namn. Tyvärr kan du inte byta namn på grupp webbplatsen på grund av hur SharePoint Online-arkitekturen fungerar. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Microsoft 365 måste hålla det nära eftersom det används bakom dina abonnemangs scener. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
Du kan emellertid fortsätta använda den första onmicrosoft.com-domänen, även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Varför har jag en "onmicrosoft.de"-domän?

Microsoft 365 skapar en domän åt dig, till exempel *contoso.onmicrosoft.de*, när du registrerar dig för tjänsten. Det användar-ID som du skapar när du registrerar dig inkluderar domänen, till exempel *Alan@contoso.onmicrosoft.de*. 
  
 **Om du vill att ditt e-postmeddelande ska se ut som *Alan@contoso.de*:** [köp domänen](../get-help-with-domains/buy-a-domain-name.md) eller följ bara anvisningarna i [lägga till användare och domän i Microsoft 365](add-domain.md) om du redan har den. 
  
- **Du kan inte byta namn på onmicrosoft-domänen efter registreringen.** Om den första domänen du väljer är fourthcoffee.onmicrosoft.de kan du till exempel inte ändra den till att vara fabrikam.onmicrosoft.de. Om du vill använda en annan onmicrosoft.de-domän måste du starta en ny prenumeration med Microsoft 365. 
    
- **Du kan inte byta namn på din gruppwebbplats-URL.** Din grupp webbplats URL baseras på ditt onmicrosoft.de-domän namn. Tyvärr kan du inte byta namn på grupp webbplatsen på grund av hur SharePoint Online-arkitekturen fungerar. 
    
- **Du kan inte ta bort domänen onmicrosoft.** Microsoft 365 måste hålla det nära eftersom det används bakom dina abonnemangs scener. Men du behöver inte använda domänen när du har lagt till en egen domän. 
    
Du kan fortsätta att använda den initiala onmicrosoft.de-domänen även efter att du har lagt till din domän. Den fungerar fortfarande för e-post och andra tjänster, så det är upp till dig.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Hur verifierar jag min status som inte vinst eller utbildning?

1. Välj **Inställningar** i [administrations centret](https://docs.microsoft.com/microsoft-365/admin/admin-home) för att starta guiden. (Kontrol lera att du loggar in på Microsoft 365 först.) 
    
2. Om du vill bli administratör för skolan markerar du alternativet  **bli administratör** i Microsoft 365. 
    
3. Du uppmanas att lägga till en TXT DNS-post på DNS-värd webbplatsen för din domän. Varför? På grund av att du loggar in på DNS-värden och lägger till en post för din domän bekräftar du att du har Microsoft 365 som du äger domän namnet.
    
4. När du har lagt till posten går du tillbaka till Microsoft 365-portalen och bekräftar att du har lagt till den, så att Microsoft 365 kan kontrol lera det.
    
Har du ingen vinst och vill skaffa Microsoft 365? [Kontrol lera att din organisation uppfyller](https://www.microsoft.com/en-us/nonprofits/eligibility) och registrera dig för tjänsten. 
  
Vill du veta mer om hur du blir administratör för skolan? [Lär dig allt](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).