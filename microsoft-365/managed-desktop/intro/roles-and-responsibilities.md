---
title: Microsoft hanterade skrivbordsroller och ansvarsområden
description: I det här avsnittet beskrivs de roller och ansvarsområden som tillhandahålls av Microsoft för Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 02a0b11a1a210367d76e73c75ac5c1fc7a66f94f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636214"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft hanterade skrivbordsroller och ansvarsområden


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Vad gör Microsoft åt dig när din organisation är registrerad på Microsoft Managed Desktop? Och vad är din organisations ansvar?

## <a name="microsofts-roles-and-responsibilities"></a>Microsofts roller och ansvarsområden

Nedan följer några viktiga roller och ansvarsområden som kommer att ges till dig av Microsoft.

Roll eller ansvar | Beskrivning
--- | ---
Hantering av MDM-policyer | Microsoft tillämpar MDM-principer enligt bästa praxis och överväger begäranden om policyändringar. Vi kommer också att göra ändringar i din klient enligt vad som föreskrivs i [Enhetspolicyer.](../service-description/device-policies.md)
Support för slutanvändare | Microsoft tillhandahåller slutanvändarsupport för enheter, Windows och Office-produktpaket för alla registrerade användare via appen Hämta hjälp som är förinstallerad på alla Microsoft Managed Desktop-enheter. 
Servicesupport för Microsoft Managed Desktop | Microsoft tillhandahåller support till kundens IT-avdelningar via ett Microsoft Managed Desktop Operations Team. Det här teamet stöder teknisk felsökning, ändringsbegäranden och incidenthantering för kundens Microsoft Managed Desktop-miljö. Mer information finns i [Administratörsstöd för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Övervakning av säkerhet | Microsoft övervakar kundens Microsoft-hanterade stationära enheter med Microsoft Defender ATP. Om ett hot upptäcks av Microsoft Managed Desktop Security Operations Center (SOC) meddelar Microsoft kunden, isolerar enheten och åtgärdar problemet på distans. Mer information finns i [Säkerhet](../service-description/security.md).
Uppdatera övervakning och hantering | Microsoft övervakar aktivt kundens Microsoft-hanterade stationära enheter för att säkerställa att de senaste kvalitets- och funktionsuppdateringarna är installerade för Microsoft Windows och Microsoft Office. Mer information finns i [Hur uppdateringar hanteras](../service-description/updates.md).
Gruppering av användare och enheter | Microsoft Managed Desktop operationsteam skapar och hanterar nödvändiga enhets- och användargrupper som en del av IT-driften. Inga medlemskap eller konfigurationsändringar tillåts för dessa grupper. Om du ändrar dessa grupper kan det leda till oväntad konfiguration av enheter och funktionsförlust. Om du har problem eller frågor runt dessa grupper när de väl har upprättats kan IT-administratörer kontakta Microsoft Managed Desktop-åtgärder. Mer information finns i [Administratörsstöd för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Dina roller och ansvarsområden

Nedan finns ytterligare en uppsättning gemensamma roller och ansvarsområden som inte tillhandahålls av Microsoft, men som krävs för en lyckad distribution. Det är inte uttömmande men gäller för de flesta organisationer. Det finns några punkter nedan som både Microsoft och kunden delar ansvar. 

Roll eller ansvar | Beskrivning
--- | ---
Förändringsledning | Microsoft meddelar kunderna i förväg när ändringar måste göras i microsofts hanterade skrivbordsmiljö. Mer information finns i [serviceändringar och kommunikation](../service-description/servicechanges.md)<br><br>Kunden måste ha en egen ändringshanteringsprocess och ha en kontakt med Microsoft Managed Desktop Operations-teamet. Kunden måste också ha resurser för att granska och godkänna dessa ändringar. Mer information finns i [Operationer och övervakning](../service-description/operations-and-monitoring.md).  
Identitetshantering | Kunden ansvarar för att skapa användarkonton, tilldela användare till grupper och hålla metadata uppdaterade. 
Microsoft 365-appar för företagskonfiguration och företagshantering | Microsoft ansvarar för att Office-program distribueras till slutanvändare och att dessa program hålls uppdaterade. <br><br> Kunden ansvarar för att hantera Microsoft 365-tjänster och policyer, inklusive administrationsansvar för Exchange Online:<br>- E-postadministration<br>- Postlåda och regelkonfiguration<br>- Utbyte av lokal förvaltning<br><br>Kunden ansvarar också för samarbetsverktyg, SharePoint-serveradministration, domänhantering, säkerhets- och informationsprinciper som anges i Microsoft 365-administrationscentret. 
Support för slutanvändare | Kunden ansvarar för att tillhandahålla slutanvändarsupport för: <br>- På plats infrastruktur: alla nätverk och internet-anslutning, VPN-infrastruktur och klientkonfiguration, lokal konferensrum utrustning, skrivare, proxyserver och konfiguration, brandväggar.<br><br>- Molnresurser för hela företaget: e-post, SharePoint, samarbetstjänster och annan molninfrastruktur som relaterar till det företagsomfattande teknikavtrycket.<br><br>- Bransch och alla andra företagsspecifika applikationer.
Apps | Rollerna och ansvarsområdena varierar något för de appar som tillhandahålls som en del av Microsoft Managed Desktop jämfört med de du tillhandahåller. <br><br>För appar som tillhandahålls av Microsoft (Microsoft 365 Apps for enterprise bestående av Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, Teams och OneNote) tillhandahåller **Microsoft** full service för distribution, uppdatering och support. **Du** måste skaffa och tilldela licenser för dessa appar, lägga till användare i säkerhetsgrupper och hantera uttjänt och distribuera eventuella tillägg som du behöver.<br><br>För appar som du tillhandahåller (till exempel dina affärsappar), oavsett om du paketerar dem själv eller anlitar en leverantör som inte kommer från Microsoft för att göra det, är **du** ansvarig för dessa åtgärder: <br><br>- Identifiera program som behövs för riktade användargrupper<br>- Skapa och hantera Azure AD-grupper för appdistribution<br>- Paketera appar för att uppfylla Microsoft Intune-distributionsstandarder<br>- Ladda upp appar till Microsoft Intune<br>- Testa appar i Microsoft Managed Desktop-miljö<br>- Testa appar med slutanvändarna<br>- Hantera och tilldela användare till applikationer<br>- Identifiera och distribuera programuppdateringar via Microsoft Intune<br>- Avinstallera och ta bort program när de har dragits tillbaka<br>- Upphandla och tilldela licenser<br>- Ge slutanvändare stöd för line-of-business apps<br>- Hantera appinställningar på distans<br><br>**Microsoft** tillhandahåller Distributionsverktyg för Microsoft Intune för att leverera programmen till fjärrklienter.<br><br>Mer information finns i [Appar](../get-ready/apps.md)
Övervakning och reaktion vid säkerhet | Kunden ansvarar för att undersöka och lösa incidenter för enheter som inte är microsoft hanterade stationära enheter och se till att Microsoft Managed Desktop Operations Team informeras om eventuella problem som kan påverka tjänsten.
Driftstöd | Kunden ansvarar för att tillhandahålla en lista över föredragna kundkontakter och ämnesexperter. Microsoft behöver dessa om det finns en icke-Microsoft Managed Desktop operativ incident. <br><br>Kunden ansvarar också för att utreda och lösa incidenter för enheter och tjänster som inte kommer från Microsofts hanterade skrivbord och tjänster och se till att Microsoft Managed Desktop Operations Team alltid informeras.
Nätverksinfrastruktur, inklusive VPN | Kunden ansvarar för installation, konfiguration och hantering (inklusive felsökning och felsökning) av all nätverksrelaterad infrastruktur och alla nätverksrelaterade infrastrukturer och tjänster, inklusive internetanslutning, nätverkskontroller, proxykonfiguration och fjärranslutningsinfrastruktur.<br><br>Om en proxy är konfigurerad (i maskinvara eller programvara) finns det en samling webbadresser som måste tillåtas av proxyn. Kunden är ansvarig för felsökning av eventuella konflikter eller inkompatibiliteter på grund av flera proxyservrar. Du kan lägga till nätverksproxyservrar som är specifika för din organisation med konfigurerbara inställningar. Mer information finns i [Konfigurera inställningar](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Mer information finns i [Proxykonfiguration](../get-ready/network.md).
Utskrift | Kunden ansvarar för att installera, underhålla och administrera skrivare och skriva ut köer. Molnutskrift är en rekommenderad lösning, men krävs inte. 




