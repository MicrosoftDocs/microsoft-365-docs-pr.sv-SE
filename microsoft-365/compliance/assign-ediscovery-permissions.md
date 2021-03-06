---
title: Tilldela eDiscovery-behörigheter i Microsoft 365 Efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: Tilldela de behörigheter som krävs för att utföra eDiscovery-relaterade uppgifter med hjälp av Microsoft 365 Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e75a18c338d2634ae3be93514ee518d9e91860
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194679"
---
# <a name="assign-ediscovery-permissions-in-the-microsoft-365-compliance-center"></a>Tilldela eDiscovery-behörigheter i Microsoft 365 Efterlevnadscenter

Om du vill att andra ska använda något av [de eDiscovery-relaterade](ediscovery.md) verktygen i Microsoft 365 Efterlevnadscenter måste du tilldela dem rätt behörigheter. Det enklaste sättet är att lägga till personen i lämplig rollgrupp på **sidan Behörigheter** i efterlevnadscentret. I det här avsnittet beskrivs behörigheterna som krävs för att utföra eDiscovery-uppgifter.
  
Den primära eDiscovery-relaterade rollgruppen i Microsoft 365 Efterlevnadscenter kallas **eDiscovery Manager.** Det finns två undergrupper i den här rollgruppen.
  
- **eDiscovery-hanterare** – en eDiscovery-hanterare kan använda eDiscovery-sökverktyg för att söka efter innehållsplatser i organisationen och utföra olika sökrelaterade åtgärder som exempelvis förhandsgranska och exportera sökresultat. Medlemmar kan också skapa och hantera ärenden i Grundläggande e-dataidentifiering och Advanced eDiscovery, lägga till och ta bort medlemmar i ett ärende, skapa fallande ärenden, köra sökningar kopplade till ett ärende och åtkomstfallsdata. eDiscovery-hanterare kan bara komma åt och hantera de fall som de skapar. De kan inte komma åt eller hantera ärenden som skapats av andra eDiscovery-hanterare.
  
- **eDiscovery-administratörer** – en eDiscovery-administratör är medlem i rollgruppen för eDiscovery Manager och kan utföra samma innehållssöknings- och ärendehanteringsrelaterade uppgifter som en eDiscovery-hanterare kan utföra. En eDiscovery-administratör kan dessutom:
  
  - Få åtkomst till alla ärenden som listas **på core-eDiscovery-** **Advanced eDiscovery-sidorna** i Microsoft 365 Efterlevnadscenter.

  - Access case data in Advanced eDiscovery for any case in the organization.
  
  - Hantera alla eDiscovery-fall när de har lagt till sig själva som medlem i ärendet.
  
  Anledningar till varför du kanske vill använda eDiscovery-administratörer i organisationen finns i [Mer information.](#more-information)

> [!NOTE]
> För att kunna analysera en användares data med hjälp Advanced eDiscovery måste användaren (den som upptog informationen) tilldelas en licens Office 365 E5 eller Microsoft 365 E5 licens. Alternativt kan användare med en Office 365 E1- eller Office 365- eller Microsoft 365 E3-licens tilldelas en tilläggslicens för Microsoft 365 E5 Compliance eller Microsoft 365 eDiscovery och audit. Administratörer, efterlevnadsansvariga och juridisk personal som tilldelas ärenden som medlemmar och använder Advanced eDiscovery för att samla in, visa och analysera data behöver inte en E5-licens. Mer information om hur Advanced eDiscovery finns i [Prenumerationer och licensiering i Advanced eDiscovery](overview-ediscovery-20.md#subscriptions-and-licensing).
  
## <a name="before-you-assign-permissions"></a>Innan du tilldelar behörigheter

- Du måste vara medlem i rollgruppen Organisationshantering eller ha tilldelats rollhanteringsrollen för att tilldela eDiscovery-behörigheter i Microsoft 365 Efterlevnadscenter.

- Du kan använda cmdleten [Add-RoleGroupMember](/powershell/module/exchange/Add-RoleGroupMember) i Security & Compliance Center PowerShell för att lägga till en e-postaktiverad säkerhetsgrupp som medlem i undergruppen för eDiscovery-hanterare i rollgruppen för eDiscovery-hanteraren. Du kan dock inte lägga till en e-postaktiverad säkerhetsgrupp i undergruppen eDiscovery-administratörer. Mer information finns i [Mer information.](#more-information) 
  
## <a name="assign-ediscovery-permissions"></a>Tilldela eDiscovery-behörigheter

1. Gå till <https://compliance.microsoft.com> och logga in med ett konto som kan tilldela behörigheter.
  
2. I det vänstra fönstret i Microsoft 365 Efterlevnadscenter väljer du **Behörigheter**.

3. På sidan **Behörigheter & Roller,** under **Efterlevnadscenter,** klickar du på **Roller**.

4. Välj  **eDiscovery Manager på sidan Roller i efterlevnadscenter.**
  
5. På den **utfällande sidan för eDiscovery Manager** gör du något av följande baserat på de eDiscovery-behörigheter som du vill tilldela.
  
    **Så här gör du en användare till eDiscovery-hanterare:** Bredvid **eDiscovery Manager** väljer du **Redigera**. På sidan **Välj guiden För eDiscovery-hanteraren** klickar du på ![ Lägg till ikon lägg ](../media/ITPro-EAC-AddIcon.gif) **till.** Välj den användare du vill lägga till som eDiscovery-hanterare och välj sedan Lägg **till**. När du är klar med att lägga till användare väljer du **Klar**. På sidan **Redigeringsvälj eDiscovery Manager**  i guiden väljer du Spara för att spara ändringarna i eDiscovery Manager-medlemskapet.
  
    **Så här gör du en användare till eDiscovery-administratör:** Bredvid **eDiscovery-administratören** väljer du **Redigera.** Klicka på Lägg till ikon lägg till på sidan Välj **eDiscovery-administratör.** ![ ](../media/ITPro-EAC-AddIcon.gif)  Välj den eller de användare du vill lägga till som **eDiscovery-administratör och** lägg sedan  **till**. När du är klar med att lägga till användare väljer du **Klar**. Välj Spara på **sidan Redigeringsvälj eDiscovery-administratör** för eDiscovery-administratör för att spara ändringarna i eDiscovery-administratörsmedlemskapet. 
  
> [!NOTE]
> Du kan också använda cmdleten **Add-eDiscoveryCaseAdmin** för att göra en användare till eDiscovery-administratör. Men användaren måste vara tilldelad rollen Ärendehantering innan du kan använda den här cmdleten för att göra dem till eDiscovery-administratör. Mer information finns i [Add-eDiscoveryCaseAdmin.](/powershell/module/exchange/add-ediscoverycaseadmin) 
  
På sidan **Behörigheter** i Microsoft 365 Efterlevnadscenter kan du också tilldela användare eDiscovery-relaterade behörigheter genom att lägga till dem i rollgrupperna Efterlevnadsadministratör, Organisationshantering och Granskare. En beskrivning av de eDiscovery-relaterade RBAC-rollerna som tilldelats var och en av dessa rollgrupper finns i [RBAC-roller relaterade till eDiscovery.](#rbac-roles-related-to-ediscovery)

## <a name="rbac-roles-related-to-ediscovery"></a>RBAC-roller relaterade till eDiscovery

I följande tabell visas de eDiscovery-relaterade rollerna för rollbaserade dataidentifieringsroller i Microsoft 365 Efterlevnadscenter och anger de inbyggda rollgrupper som varje roll är tilldelad till som standard.
  
| Roll | Efterlevnadsadministratör | eDiscovery Manager & administratör | Organisationshantering | Granskare |
|:-----|:-----:|:-----:|:-----:|:-----:|
|Ärendehantering <br/> |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> |
|Kommunikation <br/> | <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> | <br/> |
|Efterlevnadssökning <br/> |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> |
|Insikare <br/> | <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> | <br/> |
|Exportera <br/> | <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> | <br/> |
|Håll ned <br/>  |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> |
|Förhandsgranska <br/>  | <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> | <br/> |
|Granska <br/>  | <br/> |![Bockmarkering](../media/checkmark.png) <br/> | <br/> |![Bockmarkering](../media/checkmark.png) <br/> |
|RMS-dekryptera <br/>  ||![Bockmarkering](../media/checkmark.png) <br/> |||
|Sök och rensa <br/> | <br/> | <br/> |![Bockmarkering](../media/checkmark.png)           <br/> | <br/> |
||||
  
I följande avsnitt beskrivs var och en av de eDiscovery-relaterade RBAC-rollerna som listas i föregående tabell.

### <a name="case-management"></a>Ärendehantering

Med den här rollen kan användare skapa, redigera, ta bort och kontrollera åtkomsten till grundläggande eDiscovery och Advanced eDiscovery-ärenden i Microsoft 365 Efterlevnadscenter. Som tidigare förklarats måste en användare tilldelas rollen Ärendehantering innan du kan använda cmdleten **Add-eDiscoveryCaseAdmin** till att göra dem till eDiscovery-administratör.

Mer information finns i:

- [Kom igång med Core eDiscovery](get-started-core-ediscovery.md)

- [Kom igång med Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

### <a name="communication"></a>Kommunikation

Den här rollen gör att användare kan hantera all kommunikation med de personer som identifieras i Advanced eDiscovery fall. Det handlar bland annat om att skapa aviseringar om väntande samtal, hålla påminnelser och eskalera till hantering. Användaren kan också spåra bekräftelse på att ett samtal har uppmärksammats på is och hantera åtkomst till den användarportal som används av varje vårdnadshavare för att spåra kommunikation för de fall där de identifierats som vårdnadshavare.

Mer information finns i [Arbeta med kommunikation i Advanced eDiscovery](managing-custodian-communications.md).

### <a name="compliance-search"></a>Efterlevnadssökning

Med den här rollen kan användarna köra verktyget Innehållssökning i Microsoft 365 Efterlevnadscenter för att söka i postlådor och gemensamma mappar, SharePoint Online-webbplatser, OneDrive för företag-webbplatser, Skype för företag-konversationer, Microsoft 365-grupper, Microsoft Teams och Yammer-grupper. Med den här rollen kan användaren få en uppskattning av sökresultaten och skapa exportrapporter, men andra roller krävs för att initiera innehållssökningsåtgärder som förhandsgranskning, export eller borttagning av sökresultat.

I Innehållssökning och Bas-eDiscovery kan användare som har tilldelats rollen Efterlevnadssökning men inte har rollen Förhandsgranska förhandsgranska resultatet av en sökning där förhandsgranskningsåtgärden har initierats av en användare som har tilldelats rollen Förhandsgranska. Användaren utan rollen Förhandsgranska kan förhandsgranska resultat i upp till två veckor efter att den första förhandsgranskningsåtgärden skapades.

På samma sätt kan användare med innehållssökning och bas-eDiscovery som har tilldelats rollen Efterlevnadssökning men inte har exportrollen ladda ned resultatet av en sökning där exportåtgärden initierades av en användare som har tilldelats exportrollen. Användaren utan exportrollen kan hämta resultatet av en sökning i upp till två veckor efter att den första exportåtgärden skapades. Därefter kan de inte ladda ned resultaten om inte någon med rollen Exportera startar om exporten.

Respitperioden på två veckor för förhandsgranskning och export av sökresultat (utan motsvarande sök- och exportroller) gäller inte för Advanced eDiscovery. Användarna måste ha förhandsgransknings- och exportroller för att förhandsgranska och exportera innehåll i Advanced eDiscovery.

### <a name="custodian"></a>Insikare

Med den här rollen kan användare identifiera och hantera användare för Advanced eDiscovery fall och använda informationen från Azure Active Directory och andra källor för att hitta datakällor som är associerade med användare. Användaren kan associera andra datakällor, till exempel postlådor, e SharePoint och Teams med medarbetare i ett ärende. Användaren kan också skapa ett juridiskt bevarande för de datakällor som är associerade med biblioteksanvändare för att bevara innehåll i ett ärende.

Mer information finns i Arbeta [med vårdnadshavare i Advanced eDiscovery](managing-custodians.md).

### <a name="export"></a>Exportera

Med den här rollen kan användare exportera resultatet av en innehållssökning till en lokal dator. De kan också förbereda sökresultatet för analys i Advanced eDiscovery.

Mer information om hur du exporterar sökresultat finns [i Exportera sökresultat från Microsoft 365 Efterlevnadscenter](export-search-results.md).

### <a name="hold"></a>Håll ned

Med den här rollen kan användare placera innehåll i postlådor, gemensamma mappar, webbplatser, Skype för företag konversationer och Microsoft 365 grupper. När innehåll är undantaget kan innehållsägare fortfarande ändra eller ta bort det ursprungliga innehållet, men innehållet behålls tills undantaget tas bort eller tills undantaget upphör att gälla.

Mer information om spärrade uppgifter finns i:

- [Skapa ett hold in Core eDiscovery](create-ediscovery-holds.md) 

- [Skapa ett håll i Advanced eDiscovery](add-custodians-to-case.md)

### <a name="preview"></a>Förhandsgranska

Med den här rollen kan användare visa en lista över objekt som returnerats från en innehållssökning. De kan också öppna och visa varje objekt i listan för att visa innehållet.

### <a name="review"></a>Granska

Med den här rollen kan användare komma åt granskningsuppsättningar [i Advanced eDiscovery](overview-ediscovery-20.md). Användare som har tilldelats den här rollen kan se och öppna listan över ärenden på sidan **eDiscovery > Advanced** i Microsoft 365 Efterlevnadscenter där de är medlemmar. När användaren har åtkomst till ett Advanced eDiscovery ärende kan de välja Granska uppsättningar **för åtkomst** till ärendedata. Med den här rollen kan användaren inte förhandsgranska resultatet av en sökning i en samling som är kopplad till ärendet eller utföra andra åtgärder för sökning eller ärendehantering. Användare med den här rollen kan bara komma åt data i en granskningsuppsättning.

### <a name="rms-decrypt"></a>RMS-dekryptera

Med den här rollen kan användarna se rättighetsskyddade e-postmeddelanden när de förhandsgranskar sökresultat och exporterar dekrypterade rättighetsskyddade e-postmeddelanden. Med den här rollen kan användare också visa (och [](encryption.md) exportera) en fil som är krypterad med en Microsoft-krypteringsteknik när den krypterade filen bifogas till ett e-postmeddelande som ingår i resultatet av en eDiscovery-sökning. Med den här rollen kan användare dessutom granska och köra frågor för krypterade e-postbilagor som läggs till i en granskningsuppsättning Advanced eDiscovery. Mer information om dekryptering i eDiscovery finns i [Dekryptering i Microsoft 365 eDiscovery-verktyg](ediscovery-decryption.md).

### <a name="search-and-purge"></a>Sök och rensa

Med den här rollen kan användarna utföra massborttagning av data som matchar villkoren för en innehållssökning. Mer information finns i Söka [efter och ta bort e-postmeddelanden i organisationen.](search-for-and-delete-messages-in-your-organization.md)

## <a name="more-information"></a>Mer information

- **Varför skapa en eDiscovery-administratör?** Som tidigare förklarats är en eDiscovery-administratör medlem i rollgruppen för eDiscovery Manager som kan visa och komma åt alla eDiscovery-ärenden i organisationen. Den här möjligheten att komma åt alla eDiscovery-ärenden har två viktiga syften:

  - Om en person som är den enda medlemmen i ett eDiscovery-ärende lämnar organisationen kan ingen (inklusive medlemmar i rollgruppen organisationshantering eller någon annan medlem i rollgruppen för eDiscovery-hanteraren) komma åt det eDiscovery-ärendet eftersom de inte är medlemmar i ett ärende. I det här fallet skulle det inte finnas något sätt att komma åt data. Men eftersom en eDiscovery-administratör har åtkomst till alla eDiscovery-ärenden i organisationen kan de visa ärendet och lägga till sig själva eller en annan eDiscovery-hanterare som medlem i ärendet.

  - Eftersom en eDiscovery-administratör kan visa och få åtkomst till alla grundläggande eDiscovery- och Advanced eDiscovery-fall kan de granska och övervaka alla fall och tillhörande efterlevnadssökningar. Det kan förhindra felaktig användning av sökningar efter efterlevnad eller eDiscovery-fall. Eftersom eDiscovery-administratörer kan komma åt potentiellt känslig information i resultatet av en sökning efter efterlevnad, bör du begränsa antalet personer som är eDiscovery-administratörer.

- **Kan jag lägga till en grupp som medlem i rollgruppen för eDiscovery-hanteraren?** Som tidigare förklarats kan du lägga till en e-postaktiverad säkerhetsgrupp som medlem i undergruppen för eDiscovery-hanterare i rollgruppen för eDiscovery Manager med hjälp av cmdleten **Add-RoleGroupMember** i Security & Compliance Center PowerShell. Du kan till exempel köra följande kommando för att lägga till en e-postaktiverad säkerhetsgrupp i rollgruppen för eDiscovery Manager. 

  ```powershell
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    Exchange inte Microsoft 365 distributionsgrupper eller distributionsgrupper. Du måste använda en e-postaktiverad säkerhetsgrupp som du kan skapa i Exchange Online PowerShell genom att köra `New-DistributionGroup -Type Security` . Du kan också skapa en e-postaktiverad säkerhetsgrupp (och lägga till medlemmar) Exchange administrationscentret eller i Administrationscenter för Microsoft 365. Det kan ta upp till 60 minuter efter att du skapat den för att en ny e-postaktiverad säkerhet ska vara tillgänglig att lägga till i rollgruppen för eDiscovery-hanterare. 

    Som tidigare nämnts kan du inte göra en e-postaktiverad säkerhetsgrupp till eDiscovery-administratör med hjälp av cmdleten **Add-eDiscoveryCaseAdmin** i Security & Compliance Center PowerShell. Du kan bara lägga till enskilda användare som eDiscovery-administratörer.

    Du kan inte heller lägga till en e-postaktiverad säkerhetsgrupp som medlem i ett ärende.