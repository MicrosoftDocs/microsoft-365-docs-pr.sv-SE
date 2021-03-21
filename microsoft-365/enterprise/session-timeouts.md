---
title: Tidsgränser för sessioner för Microsoft 365
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
description: Lär dig hur tidsgränser för sessioner används för att balansera säkerhet och hjälpmedel i Microsoft 365-klientappar.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924922"
---
# <a name="session-timeouts-for-microsoft-365"></a>Tidsgränser för sessioner för Microsoft 365

Sessionslivslängder är en viktig del av autentisering för Microsoft 365 och är en viktig komponent i balansering av säkerhet och antalet gånger som användare uppmanas att ange sina autentiseringsuppgifter.

## <a name="session-times-for-microsoft-365-services"></a>Sessionstider för Microsoft 365-tjänster

När användarna autentiseras i någon av Microsoft 365-webbapparna eller mobilapparna upprättas en session. Under hela sessionen behöver användarna inte autentisera sig igen. Sessioner kan upphöra att gälla när användare är inaktiva, när de stänger webbläsaren eller fliken, eller när deras autentiseringstoken upphör att gälla av andra orsaker, till exempel när lösenordet har återställts. Microsoft 365-tjänsterna har olika tidsgränser för sessioner för att motsvara normal användning av varje tjänst.

I följande tabell visas sessionslivslängderna för Microsoft 365-tjänster:

| Microsoft 365-tjänsten | Tidsgräns för session |
|:-----|:-----|
|Administrationscenter för Microsoft 365  <br/> |Du ombeds att ange autentiseringsuppgifter för administrationscentret var 8:e timme.  <br/> |
|SharePoint Online  <br/> |5 dagars inaktivitet så länge användarna väljer Jag **vill hålla mig inloggad.** Om användaren öppnar SharePoint Online igen när det har gått 24 timmar eller längre sedan föregående inloggning återställs tidsgränsen till 5 dagar.  <br/> |
|Outlook-webbprogrammet  <br/> |6 timmar.  <br/> Du kan ändra det här värdet med hjälp av parametern _ActivityBasedAuthenticationTimeoutInterval_ i cmdleten [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)  <br/> |
|Azure Active Directory  <br/> (Används av Office- och Microsoft 365-program i Windows-klienter med modern autentisering aktiverad)  <br/> | Modern autentisering använder åtkomsttoken och uppdateringstoken för att bevilja användaråtkomst till Microsoft 365-resurser med Azure Active Directory. En åtkomsttoken är en JSON Web Token som tillhandahålls efter en lyckad autentisering och är giltig i 1 timme. En uppdateringstoken med längre livslängd tillhandahålls också. När åtkomsttoken upphör att gälla använder Office-klienter en giltig uppdateringstoken för att erhålla en ny åtkomsttoken. Det här bytet fungerar om användarens initiala autentisering fortfarande är giltig.  <br/>  Uppdateringstoken är giltiga i 90 dagar och med kontinuerlig användning kan de vara giltiga tills de återkallas.  <br/>  Uppdateringstoken kan bli ogiltiga på grund av flera händelser, till exempel:  <br/>  Användarens lösenord har ändrats sedan uppdateringstoken utfärdades.  <br/>  En administratör kan använda villkorsstyrda åtkomstprinciper som begränsar åtkomsten till den resurs som användaren försöker komma åt.  <br/> |
|SharePoint- och OneDrive-mobilappar för Android, iOS och Windows 10  <br/> |Standardlivslängd för åtkomsttoken är 1 timme. Maximal inaktiv standardtid för uppdateringstoken är 90 dagar.  <br/> [Läs mer om token och hur du konfigurerar tokenlivslängd](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Om du vill återkalla uppdateringstoken kan du återställa användarens Microsoft 365-lösenord  <br/> |
|Yammer med Microsoft 365-Sign-In  <br/> |Livslängd i webbläsaren. Om användarna stänger webbläsaren och öppnar Yammer i en ny webbläsare autentiserar Yammer dem igen med Microsoft 365. Om användarna använder webbläsare från tredje part där cookies cachelagras kanske de inte behöver autentiseras igen när de öppnar webbläsaren igen.  <br/> > [!NOTE]> Detta gäller endast för nätverk med Microsoft 365-Sign-In för Yammer.           |