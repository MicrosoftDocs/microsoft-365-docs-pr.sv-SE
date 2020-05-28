---
title: Använda självbetjäningsanmäla i din organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Lär dig mer om registreringen av självbetjäningstjänsten för Microsoft 365 och tillgängliga självbetjäningsprogram som Microsoft Power Apps, Microsoft Flow och Dynamics 365 for Financials.
ms.openlocfilehash: d2d4d23eeb3ddeda0dc5b66acfe072a66f4ce267
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399296"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Använda självbetjäningsanmäla i din organisation

Vi lyssnar på din feedback och har gjort det enklare för användare i organisationen att registrera sig för onlinetjänster från Microsoft. Vi kallar den här nya registreringsprocessen "självbetjäningsanteckning" eftersom dina användare kan registrera sig för att använda tjänster som betalas av din prenumeration, eller använda kostnadsfria tjänster, utan att be dig att vidta åtgärder för deras räkning.
  
## <a name="how-self-service-sign-up-works"></a>Så här fungerar självbetjäningsanmälning

I följande exempel beskrivs hur självanmälning fungerar för en skola. Samma process fungerar för alla organisationer som har självbetjäningsprogram aktiverade i sin klientorganisation.
  
1. Elever och fakultetsmedlemmar har e-postadresser till skolan som anger att de är kopplade till din institution. Till exempel kan e-postadressen jakob@uw.edu ange en student från University of Washington.

2. Studenter och lärare går till [vår webbplats](https://go.microsoft.com/fwlink/p/?LinkId=536628)och använder sin e-postadress för att registrera dig för de tjänster som din organisation erbjuder, till exempel Microsoft 365 Apps for Enterprise. De kan också registrera dig för andra gratis tjänster som vi erbjuder.

3. Vi validerar deras e-postadress och sedan kan de börja använda Microsoft 365, Power BI eller andra tjänster direkt.

4. Som företagsadministratör ser du vem som har registrerat sig för en prenumeration genom att visa sidan **Dina produkter** i administrationscentret. På så sätt kan du se när det finns nya eller okända licenser för tjänster i din klient. Om du vill styra om användare kan registrera sig för självbetjäningsprenumerationer använder du cmdleten [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell med parametern **AllowAdHocSubscriptions.** Mer information finns i [Hur kontrollerar jag självbetjäningsinställningarna?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Tillgängliga självbetjäningsprogram

Följande är de för närvarande tillgängliga självbetjäningsprogram. Den här listan uppdateras när nya program läggs till.
  
|||||
|:-----|:-----|:-----|:-----|
|**Program** <br/> |**Beskrivning** <br/> |**Ytterligare information** <br/> |Webbplats för självbetjäning registrera dig **** <br/> |
|Office 365 A1**** <br/> |Alla elever eller lärare kan använda en e-postadress till skolan för att registrera dig för kostnadsfria Office 365 och hämta Office-appar för webben, 1 TB OneDrive-molnlagring och SharePoint Online för klass-, grupp- och projektwebbplatser.  <br/> |[Tekniska frågor om Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Utbildning](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Behöriga elever och lärare kan registrera sig för Office 365 A1 Plus, som innehåller allt som nämns ovan plus Microsoft 365 Apps för företag. Microsoft 365 Apps for enterprise är produktivitetsprogram, inklusive Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access och Skype för företag, som är installerat på din stationära eller bärbara dator.  <br/> |[Tekniska frågor om Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Utbildning](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI gör det möjligt för användare att visualisera data, dela upptäckter och samarbeta på nya intuitiva sätt. <br/> Om din organisation redan prenumererar kan du dessutom se licenser för "Power BI Pro Individual User Trial", som erbjuder användarna begränsad, fri tillgång till avancerade funktioner.  <br/> |[Power BI i din organisation](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS för enskilda personer är en kostnadsfri självbetjäningsprenumeration för användare i en organisation som har skickats känsliga filer som har skyddats av Azure Rights Management (Azure RMS), men deras IT-avdelning har inte implementerat Azure Rights Management (Azure RMS) eller Active Directory Rights Management Services (AD RMS).  <br/> |[RMS för enskilda personer och Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management-portalen](https://portal.azure.com/) så att du kan kontrollera om du kan öppna ett visst rättighetsskyddat dokument.  <br/> |
|**Microsoft Power-appar** <br/> |I PowerApps kan du hantera organisationsdata genom att köra en app som du har skapat eller som någon annan har skapat och delat med dig. Appar körs på mobila enheter som telefoner, eller så kan du köra dem i en webbläsare genom att öppna Dynamics 365. Du kan skapa ett oändligt utbud av appar – allt utan att lära dig ett programmeringsspråk som C#.  <br/> |[Självbetjäningsanmälan för PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power-appar](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 för ekonomi** <br/> |Få en komplett lösning för företag och ekonomi för små och medelstora företag. Dynamics 365 for Financials gör det enklare att beställa, sälja, fakturera och rapportera – från och med dag ett.  <br/> |[Microsoft Dynamics 365 för ekonomi](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 för ekonomi](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 för drift** <br/> |Öka din hastighet att göra affärer. De kompletta ERP-verktygen i Dynamics 365 for Operations ger global skalbarhet och digital intelligens som hjälper dig att växa i din takt.  <br/> |[Microsoft Dynamics 365 för drift](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 för drift](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource är en destination för företagsappar som bygger på Microsofts molnplattform. AppSource har hundratals appar, tillägg och innehållspaket som utökar funktionerna i Microsoft-produkter som Azure, Dynamics 365, Office 365 och Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incitament för Microsoft-partner** <br/> |Microsoft Partner Network innehåller tre typer av medlemskap. Varje typ ger en uppsättning fördelar som hjälper ditt företag att växa. När du uppnår dina mål, delta i programmet på den nivå som passar dina unika behov för att få tillgång till fler fördelar och utveckla din relation med oss och andra partners i nätverket.  <br/> |[Incitament för Microsoft-partner](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incitament för Microsoft-partner](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center är en portal för kunder som har gjort inköp via Microsofts produkt- och tjänsteavtal (MPSA). <br/> |[Snabbstart: Registrera dig för Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsofts tjänst för volymlicens** <br/> |Microsoft Volume License Service Center visar licenser som köpts under Enterprise, Select, Education (Campus eller School), Open Value, Open License och ISV Royalty-avtal.  <br/> |[VLSC utbildning och resurser](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Servicecenter för volymlicens](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Utbildning Edition** <br/> |Genom att använda Minecraft som en plattform för lärande kan lärare motivera och inspirera varje elev att uppnå mer och tända en passion för lärande. Gå med i en grupp lärare som lär dig hur du använder Minecraft för att låsa upp elevernas potential.  <br/> |[Minecraft Utbildning Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Utbildning Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Ladda upp och dela videoklipp i hela organisationen för att förbättra kommunikation, delaktighet och inlärning.  <br/> |[Registrera dig &amp; Dag 0-upplevelse](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Strömautomat** <br/> |Power Automate är en produkt som hjälper dig att konfigurera automatiserade arbetsflöden mellan dina favoritappar och tjänster för att synkronisera filer, få aviseringar, samla in data med mera.  <br/> |[Registrera dig och logga in för Power Automate](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Strömautomat](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power virtuella agenter** <br/> |Power Virtual Agents ger teamen möjlighet att enkelt skapa kraftfulla robotar med hjälp av ett guidat grafiskt gränssnitt utan kod utan behov av datavetare eller utvecklare. Power Virtual Agents tar upp många av de stora problemen med bot byggnad i branschen idag. Det eliminerar klyftan mellan ämnet experter och utvecklingsteam bygga bots, och den långa latens mellan lag som erkänner ett problem och uppdatera bot för att ta itu med det.  <br/> |[Information om licensiering och åtkomst](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Registrera dig för Virtuella Power-agenter](https://aka.ms/TryPVA) <br/> |