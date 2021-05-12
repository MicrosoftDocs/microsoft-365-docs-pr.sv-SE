---
title: Använda självbetjäning för registrering i organisationen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Lär dig mer om Självbetjänings registrera dig för Microsoft 365 och tillgängliga självbetjäningsprogram som Microsoft Power Apps, Microsoft Flow och Dynamics 365 för ekonomi.
ms.date: 03/17/2021
ms.openlocfilehash: f3427294a94875e21a5e6b99a09056617a7dea99
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332384"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Använda självbetjäning för registrering i organisationen

Registrering med självbetjäning gör det enklare för användarna i organisationen att registrera sig för onlinetjänster från Microsoft. Vi kallar den här registreringsprocessen "självbetjäning för registrering" eftersom dina användare kan registrera sig för att använda tjänster som betalas i ditt abonnemang eller använda kostnadsfria tjänster utan att be dig vidta åtgärder för deras räkning.
  
## <a name="how-self-service-sign-up-works"></a>Så här fungerar självbetjäning för registrering

I följande exempel beskrivs hur självinlärning fungerar för en skola. Samma process fungerar för alla organisationer som har självbetjäningsprogram aktiverade i klientorganisationen.
  
1. Studenter och lärare har e-postadresser för skolan som anger att de är kopplade till din institution. Till exempel kan e-postadressen jakob@uw.edu ange en elev på University of Washington.
2. Studenter och lärare [](https://go.microsoft.com/fwlink/p/?LinkId=536628)går till vår webbplats och använder sin e-postadress för att registrera sig för de tjänster som din organisation erbjuder, till exempel Microsoft 365-appar för företag. De kan även registrera sig för andra kostnadsfria tjänster som vi erbjuder.
3. Vi validerar deras e-postadress och sedan kan de börja använda Microsoft 365, Power BI eller andra tjänster direkt.
4. Som företagsadministratör kan du se vem som har registrerat sig  för en prenumeration genom att välja prenumerationen på sidan Licensiering i administrationscentret för Microsoft 365. På så sätt kan du se när det finns nya eller okända licenser för tjänster i klientorganisationen. Om du vill styra om användare kan registrera sig för prenumerationer med självbetjäning använder du powershell-cmdleten [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) med **parametern AllowAdHocSubscriptions.** Mer information finns i [Hur styr jag självbetjäningsuppgifter?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Tillgängliga självbetjäningsprogram

Här följer de för närvarande tillgängliga självbetjäningsprogram som finns tillgängliga. Den här listan uppdateras när nya program läggs till.
  
| Program <br/> | Beskrivning <br/> | Ytterligare information <br/> | Webbplats för självbetjäning vid registrering <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Alla elever eller lärare kan använda en e-postadress för skolan för att registrera sig kostnadsfritt Office 365 och få Office-program för webben, 1 TB molnlagring på OneDrive och SharePoint Online för klass-, grupp- och projektwebbplatser.  <br/> |[Vanliga frågor och svar om tekniska frågor om Office 365 Education](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Kvalificerade elever och lärare kan registrera sig för Office 365 A1 Plus, inklusive allt som nämns ovan plus Microsoft 365-program för företag. Microsoft 365-appar för företag är produktivitetsprogram för bland annat Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access och Skype för företag, som är installerade på din stationära eller bärbara dator.  <br/> |[Vanliga frågor och svar om tekniska frågor om Office 365 Education](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Med Power BI kan användare visualisera data, dela upptäckter med andra och samarbeta på nya och intuitiva sätt. <br/> Om din organisation redan prenumererar kan du dessutom se licenser för "Provperiod för enskilda användare av Power BI Pro", som ger användare begränsad, fri tillgång till avancerade funktioner.  <br/> |[Power BI i organisationen](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS (Rights Management Services)** <br/> |RMS för individer är en kostnadsfri prenumeration på självbetjäning för användare i en organisation som har skickat känsliga filer som har skyddats av Azure Rights Management (Azure RMS), men IT-avdelningen har inte implementerat Azure Rights Management (Azure RMS) eller AD RMS (Active Directory Rights Management Services).  <br/> |[RMS för individer och Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management-portalen](https://portal.azure.com/) så att du kan kontrollera om du kan öppna ett visst rättighetsskyddat dokument.  <br/> |
|**Microsoft Power-appar** <br/> |I PowerApps kan du hantera organisationsdata genom att köra ett program som du har skapat eller som någon annan har skapat och delat med dig. Appar kan köras på mobila enheter, till exempel telefoner, eller så kan du köra dem i en webbläsare genom att öppna Dynamics 365. Du kan skapa en oändlig mängd olika program – allt utan att lära dig ett programmeringsspråk som C#.  <br/> |[Självbetjäning för registrering för PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power-appar](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 för ekonomi** <br/> |Få en komplett lösning för företags- och ekonomihantering för små och medelstora företag. Dynamics 365 for Financials gör det enklare att ordna, sälja, fakturering och rapportera – från och med dag ett.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Öka hastigheten med att göra affärer. De kompletta ERP-verktygen i Dynamics 365 for Operations ger global skalbarhet och digital intelligens som hjälper dig att växa i din takt.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource är en destination för företagsappar med programvara som en tjänst som bygger på Microsofts molnplattform. AppSource innehåller hundratals appar, tillägg och innehållspaket som ger fler funktioner i Microsoft-produkter som Azure, Dynamics 365, Office 365 och Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft-partnerincitament** <br/> |Microsoft Partner Network tillhandahåller tre typer av medlemskap. Varje typ ger en uppsättning fördelar som hjälper ditt företag att växa. När du uppnår dina mål kan du delta i programmet på den nivå som passar dina unika behov för att få tillgång till fler fördelar och utveckla din relation med oss och andra partner i nätverket.  <br/> |[Microsoft-partnerincitament](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft-partnerincitament](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center är en portal för kunder som har gjort inköp via MPSA (Microsoft Products and Services Agreement). <br/> |[Snabbstart: Registrera dig för Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |I Microsofts volymlicensservicecenter visas licenser som köpts under Enterprise, Select, Education (Campus eller School), Open Value, Open License och ISV Royalty- avtal.  <br/> |[VLSC-utbildning och -resurser](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Volume License Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Genom att använda Minecraft som en utbildningsplattform kan lärare inspirera och inspirera alla elever till att uppnå mer, och antända en passion för utbildning. Gå med i en community av lärare och lär dig använda Minecraft för att låsa upp elevernas potential.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Ladda upp och dela videor i organisationen för att förbättra kommunikation, deltagande och inlärning.  <br/> |[Registrera dig &amp; för dag 0](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate är en produkt som hjälper dig att konfigurera automatiska arbetsflöden mellan dina favoritappar och tjänster för att synkronisera filer, få meddelanden, samla in data och mycket mer.  <br/> |[Registrera dig och logga in för Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Virtuella poweragenter** <br/> |Med Power Virtual Agents kan team enkelt skapa kraftfulla robotar med hjälp av ett guidat grafiskt gränssnitt utan att det behövs någon datadelad eller utvecklare. Virtuella Power Agents åtgärdar många av de stora problemen med robotbygge i branschen idag. Det eliminerar skillnaden mellan ämnesexperter och utvecklingsteamen som bygger robotar, och den långa svarstiden mellan team som känner igen ett problem och uppdaterar roboten för att åtgärda det.  <br/> |[Information om licensiering och åtkomst](/power-virtual-agents/requirements-licensing) <br/> |[Registrera dig för virtuella Power Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Med B2B-samarbete i Azure Active Directory (Azure AD) kan du bjuda in externa användare (eller "gästanvändare") att använda dina betalda Azure AD-tjänster. Vissa funktioner är kostnadsfria, men för alla betalda Azure AD-funktioner kan du bjuda in upp till fem gästanvändare för varje Azure AD-utgåvalicens som du äger för en anställd eller en användare som inte är gäst i klientorganisationen. <br/> |[Självbetjäning för B2B-samarbetsinb-registrering för Azure AD](/azure/active-directory/b2b/self-service-portal) <br/> |[Licensieringsvägledning för B2B-samarbete i Azure Active Directory](/azure/active-directory/b2b/licensing-guidance) <br/> |
