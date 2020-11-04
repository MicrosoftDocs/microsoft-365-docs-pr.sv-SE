---
title: Använda automatisk registrering i din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Läs mer om Microsoft 365 Self-Service-anmälan och tillgängliga självbetjänings program, till exempel Microsoft Power Apps, Microsoft Flow och Dynamics 365 för finansiering.
ms.openlocfilehash: 21e41661141a817a1751c80608035d839d2e3952
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906579"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Använda automatisk registrering i din organisation

Med självbetjäning blir det enklare för användare i organisationen att registrera sig för online tjänster från Microsoft. Vi ringer upp själv registrerings processen "själv anmälan" för att användarna ska kunna registrera sig för att använda tjänster som betalas av din prenumeration, eller använda kostnads fria tjänster utan att be dig att vidta någon åtgärd för deras räkning.
  
## <a name="how-self-service-sign-up-works"></a>Så här fungerar själv-anmälan

I följande exempel beskrivs hur själv registrerar sig i skolan. Samma sak fungerar för organisationer som har självbetjänings program aktiverade i sin klient organisation.
  
1. Studenter och lärare har skolans e-postadresser som visar att de är kopplade till din institution. Exempelvis kan e-postadressen jakob@uw.edu ange en elev hos University of Washington.
2. Studenter och lärare går till [vår webbplats](https://go.microsoft.com/fwlink/p/?LinkId=536628)och använder sin e-postadress för att registrera sig för de tjänster som organisationen erbjuder, till exempel Microsoft 365-appar för företag. De kan också registrera sig för andra gratis tjänster som vi tillhandahåller.
3. Vi verifierar sin e-postadress och sedan kan de komma igång med Microsoft 365, Power BI eller andra tjänster direkt.
4. Som företags administratör kan du se vem som har registrerat dig för ett abonnemang genom att välja prenumerationen på **licensierings** sidan i administrations centret för Microsoft 365. På det sättet kan du se när det finns nya eller okända licenser för tjänster i din klient organisation. Om du vill kontrol lera om användare kan registrera sig för självbetjänings prenumerationer använder du cmdleten [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell med parametern **AllowAdHocSubscriptions** . Mer information finns i [Hur styr jag självbetjänings inställningar?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Tillgängliga självbetjänings program

Nedan finns de självbetjänings program som är tillgängliga för närvarande. Den här listan uppdateras när nya program läggs till.
  
| Information <br/> | Beskrivning <br/> | Ytterligare information <br/> | Webbplats för självbetjänings registrering <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 a1 * * * * <br/> |Alla elever och lärare kan använda en e-postadress för skolan för att registrera dig för en kostnads fri Office 365 och hämta Office-appar för webben, 1 TB moln lagring i OneDrive och SharePoint Online för klass-, grupp-och projekt webbplatser.  <br/> |[Office 365 Education – tekniska frågor](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 plus** <br/> |Berättigade studenter och lärare kan registrera sig för Office 365 a1 plus, vilket omfattar allting ovan plus Microsoft 365-appar för företag. Microsoft 365-appar för företag är produktivitets program, inklusive Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access och Skype för företag, som är installerat på din station ära eller bärbara dator.  <br/> |[Office 365 Education – tekniska frågor](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI gör att användare kan visualisera data, dela upptäckter och samar beta på nya och intuitiva sätt. <br/> Om din organisation redan abonnerar kan du även se licenser för "Power BI Pro individuell User utvärdering", som ger användarna begränsad åtkomst till avancerade funktioner.  <br/> |[Power BI i organisationen](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS (Rights Management Services)** <br/> |RMS för enskilda personer är ett kostnads fritt självbetjänings abonnemang för användare i en organisation som har skickat känsliga filer som har skyddats av Azure Rights Management (Azure RMS), men IT-avdelningen har inte implementerat Azure Rights Management (Azure RMS) eller AD RMS (Active Directory Rights Management Services).  <br/> |[RMS för enskilda personer och Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management-portalen](https://portal.azure.com/) gör att du kan kontrol lera om du kan öppna ett tilldelat rättighetsskyddade dokument.  <br/> |
|**Microsoft Power Apps** <br/> |I PowerApps kan du hantera organisationsinformation genom att köra ett program som du har skapat eller som någon annan har skapat och delat med dig. Appar körs på mobila enheter, till exempel telefoner, eller så kan du köra dem i en webbläsare genom att öppna Dynamics 365. Du kan skapa en oändlig mängd olika appar – helt utan att lära dig ett programmeringsspråk, till exempel C#.  <br/> |[Själv registrering för PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 för ekonomiska räkenskaper** <br/> |Skaffa en komplett företags-och ekonomisk hanterings lösning för små och medel stora företag. Dynamics 365 för ekonomiska kostnader gör det enklare att beställa, sälja, fakturera och rapportera: från dag ett.  <br/> |[Microsoft Dynamics 365 för ekonomiska räkenskaper](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 för ekonomiska räkenskaper](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 för åtgärder** <br/> |Gör affärer mer effektivt. De fullständiga ERP-verktygen i Dynamics 365 för operationer ger globala skalbarhets-och digital Intelligence-funktioner som hjälper dig att växa i takt.  <br/> |[Microsoft Dynamics 365 för åtgärder](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 för åtgärder](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource är ett mål för program vara-as-service-affärsappar som bygger på Microsofts moln plattform. AppSource har funktioner för hundratals appar, tillägg och innehålls paket som utökar funktionerna i Microsoft-produkter som Azure, Dynamics 365, Office 365 och Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsofts partner incitament** <br/> |I Microsoft Partner Network finns det tre typer av medlemskap. Varje typ ger en uppsättning fördelar som underlättar verksamheten. När du uppnår dina mål kan du delta i programmet på den nivå som passar dina unika behov för att få till gång till fler fördelar och utveckla ditt förhållande till oss och andra partners i nätverket.  <br/> |[Microsofts partner incitament](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsofts partner incitament](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center är portalen för kunder som har gjort köp via Microsofts produkter och service avtal (MPSA). <br/> |[Snabb start: registrera dig för Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume licenstjänster-Center** <br/> |I Microsoft Volume Licensing Service Center visas licenser som köpts under Enterprise, väljer, utbildning (Campus eller skola), Open Value, Open licens and ISV royalty-avtal.  <br/> |[VLSC utbildning och resurser](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Service Center för volym licens](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education-version** <br/> |Genom att använda Minecraft som en plattform för inlärning kan lärare motivera och inspirera varje elev för att få mer och göra en passion för inlärning. Delta i ett community-utbildningsprogram lär dig hur du kan använda Minecraft för att låsa upp elevernas potential.  <br/> |[Minecraft Education-version](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education-version](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Ladda upp och dela videor i organisationen för att förbättra kommunikation, medverkan och utbildning.  <br/> |[Registrera dig på &amp; dag 0](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Automatisk strömförsörjning** <br/> |Power automatisering är en produkt som hjälper dig att konfigurera automatiserade arbets flöden mellan dina favorit program och-tjänster för att synkronisera filer, få aviseringar, samla in data och mycket mer.  <br/> |[Registrera dig och logga in för Power autoautomatisera](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Automatisk strömförsörjning](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual-agenter** <br/> |Power Virtual-agenter gör det enkelt för team att skapa kraftfulla robotar med hjälp av ett guidat, grafiskt gränssnitt utan att behöva använda forskare eller utvecklare. Power Virtual-agenter löser många av de vanligaste problemen med bot-byggnad i branschen idag. Det eliminerar luckan mellan ämnets experter och utvecklings teamen som bygger på robotar, och den långa svars tiden mellan Teams som identifierar ett problem och uppdaterar roboten för att adressera den.  <br/> |[Licens-och åtkomst information](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Registrera dig för Power Virtual-agenter](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Med samarbete i Azure Active Directory (Azure AD) Business-till-företag kan du bjuda in externa användare (eller "gäst användare") för att använda dina betalda Azure AD-tjänster. Vissa funktioner är gratis, men för alla betalda Azure AD-funktioner kan du bjuda in upp till fem gäst användare för varje Azure AD Edition-licens som du äger för en anställd eller icke-gäst användare i klient organisationen. <br/> |[Själv service för Azure AD B2B-samarbete](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Vägledning för samarbete för Azure Active Directory B2B Collaboration](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |
