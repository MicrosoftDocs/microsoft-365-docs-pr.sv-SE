---
title: Tids gränser för session för Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Lär dig hur tids gränser för sessioner används för att balansera säkerheten och hjälpmedel i Microsoft 365-klientprogram.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769298"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tids gränser för session för Microsoft 365

Livstiden för en session är en viktig del av autentisering för Microsoft 365 och är en viktig komponent för att balansera säkerheten och hur många gånger användarna uppmanas att uppge sina autentiseringsuppgifter.

## <a name="session-times-for-microsoft-365-services"></a>Tids perioder för Microsoft 365-tjänster

När användare autentiseras i någon av Microsoft 365-webbapparna eller mobilappen upprättas en session. För varaktigheten för sessionen behöver användare inte autentisera igen. Sessioner kan upphöra att gälla när användare är inaktiva, när de stänger webbläsaren eller fliken, eller när deras autentiseringstoken upphör att gälla av andra skäl, till exempel när lösen ordet har återställts. Microsoft 365-tjänsterna har olika tids gränser för sessioner för att motsvara typisk användning för varje tjänst.

I följande tabell finns en lista med livstider för sessionerna för Microsoft 365-tjänster:

| Microsoft 365-tjänsten | Tids gräns för session |
|:-----|:-----|
|Administrationscenter för Microsoft 365  <br/> |Du uppmanas att ange autentiseringsuppgifter för administrations centret var 8: e timme.  <br/> |
|SharePoint Online  <br/> |5 dagar av inaktivitet så länge användarna väljer **Håll mig inloggad** . Om användaren har åtkomst till SharePoint online igen efter 24 eller fler timmar har passerat från föregående inloggning återställs timeoutvärdet till 5 dagar.  <br/> |
|Outlook-webbprogrammet  <br/> |sex timmar.  <br/> Du kan ändra det här värdet genom att använda parametern  _ActivityBasedAuthenticationTimeoutInterval_ i cmdleten [set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .  <br/> |
|Azure Active Directory  <br/> (Används av Office-och Microsoft 365-program i Windows-klienter med modern aktive rad användning)  <br/> | För modern användning används åtkomst-tokens och uppdateringstoken för att bevilja användar åtkomst till Microsoft 365-resurser med Azure Active Directory. En åtkomsttoken är en JSON Web token efter en lyckad autentisering och är giltig i 1 timme. En uppdateringstoken med en längre livs längd tillhandahålls också. När Access-token går ut använder Office-klienter en giltig uppdateringstoken för att få en ny åtkomsttoken. Det här utbytet fungerar om användarens initiala verifiering fortfarande är giltig.  <br/>  Refresh token är giltiga i 90 dagar och med kontinuerlig användning kan de vara giltiga tills de återkallas.  <br/>  Uppdatering av token kan ogiltig förklaras av flera händelser, till exempel:  <br/>  Användarens lösen ord har ändrats sedan uppdateringstoken utfärdades.  <br/>  En administratör kan tillämpa villkorsstyrda åtkomst principer som begränsar åtkomsten till resursen som användaren försöker komma åt.  <br/> |
|SharePoint-och OneDrive-mobilappar för Android, iOS och Windows 10  <br/> |Standard livs längden för åtkomsttoken är 1 timme. Den maximala högsta inaktiva tiden för uppdateringstoken är 90 dagar.  <br/> [Läs mer om tokens och hur du konfigurerar livs längd för token](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Om du vill återkalla uppdateringstoken kan du återställa användarens Microsoft 365-lösenord  <br/> |
|Yammer med Microsoft 365 Sign-In  <br/> |Webbläsarens livs längd. Om användarna stänger webbläsaren och får åtkomst till Yammer i en ny webbläsare kommer Yammer att autentisera dem igen med Microsoft 365. Om användarna använder webbläsare från tredje part som cachelagrar cookies kanske de inte behöver verifiera igen när de öppnar om webbläsaren.  <br/> > [!NOTE]> det här gäller endast för nätverk som använder Microsoft 365 Sign-In för Yammer.           |

