---
title: Roller och ansvarsområden för Microsoft Managed Desktop
description: I det här avsnittet beskrivs roller och ansvarsområden som tillhandahålls av Microsoft för Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0288dfd2ee84f406c4bcdf4a604d1370afeefed7
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/22/2019
ms.locfileid: "42806791"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roller och ansvarsområden för Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Vad gör Microsoft för dig när din organisation är registrerad på Microsoft Managed Desktop? Och vad har din organisations ansvar?

## <a name="microsofts-roles-and-responsibilities"></a>Microsofts roller och ansvarsområden

Nedan finns några viktiga roller och ansvarsområden som kommer att ges till dig av Microsoft.

Roll eller ansvar | Beskrivning
--- | ---
Mdm-principhantering | Microsoft tillämpar MDM-principer enligt bästa praxis och överväger begäranden om principändringar. Vi kommer också att göra ändringar i din klientorganisation enligt vad som föreskrivs i [Enhetsprinciper.](../service-description/device-policies.md)
Stöd för slutanvändare | Microsoft tillhandahåller stöd för slutanvändare för enheter, Windows och Office-produktpaket för alla inskrivna användare via appen Hämta hjälp som är förinstallerad på alla Microsoft Managed Desktop-enheter. 
Support för Microsoft Managed Desktop-tjänsten | Microsoft kommer att ge support till it-avdelningar för kunder via ett Microsoft Managed Desktop Operations Team. Det här teamet kommer att stödja teknisk felsökning, ändringsbegäranden och incidenthantering för kundens Microsoft Managed Desktop-miljö. Mer information finns i [Administratörssupport för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Övervakning av säkerhet | Microsoft övervakar kunden Microsoft Managed Desktop-enheter med Microsoft Defender ATP. Om ett hot upptäcks av Soc (Microsoft Managed Desktop Security Operations Center) meddelar Microsoft kunden, isolerar enheten och åtgärdar problemet på distans. Mer information finns i [Säkerhet](../service-description/security.md).
Uppdatera övervakning och hantering | Microsoft övervakar aktivt kundenmicrosoft managed desktop-enheter för att säkerställa att de senaste kvalitets- och funktionsuppdateringarna installeras för Microsoft Windows och Microsoft Office. Mer information finns i [Hur uppdateringar hanteras](../service-description/updates.md).
Användar- och enhetsgruppering | Microsoft Managed Desktop-driftteamet skapar och hanterar nödvändiga enhets- och användargrupper som en del av IT-åtgärder. Inga medlemskap eller konfigurationsändringar tillåts i dessa grupper. Om du ändrar dessa grupper kan det leda till oväntad konfiguration av enheter och funktionsbortfall. För eventuella problem eller frågor runt dessa grupper när de väl har upprättats kan IT-administratörer kontakta Microsoft Managed Desktop-åtgärder. Mer information finns i [Administratörssupport för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Dina roller och ansvarsområden

Nedan följer ytterligare en uppsättning gemensamma roller och ansvarsområden som inte tillhandahålls av Microsoft, men som krävs för en lyckad distribution. Det är inte uttömmande men gäller för de flesta organisationer. Det finns några objekt under att både Microsoft och kunden delar ansvar. 

Roll eller ansvar | Beskrivning
--- | ---
Ändra hantering | Microsoft meddelar kunderna i förväg när ändringar måste göras i deras Microsoft Managed Desktop-miljö. Mer information finns i [serviceändringar och kommunikation](../service-description/servicechanges.md)<br><br>Kunden måste ha en egen förändringshanteringsprocess och ha en kontakt upprättad med Microsoft Managed Desktop Operations team. Kunden måste också ha resurser för att granska och godkänna dessa ändringar. Mer information finns i [Operationer och övervakning](../service-description/operations-and-monitoring.md).  
Identitetshantering | Kunden ansvarar för att skapa användarkonton, tilldela användare till grupper och hålla metadata uppdaterade. 
Office 365 ProPlus-konfiguration och hantering | Microsoft ansvarar för att Office-program distribueras till slutanvändare och dessa program hålls uppdaterade. <br><br> Kunden ansvarar för att hantera Office 365-tjänster och policyer, inklusive Administrationsansvar för Exchange Online:<br>- E-postadministration<br>- Konfiguration av postlåda och regel<br>- Utbyte lokal förvaltning<br><br>Kunden ansvarar också för samarbetsverktyg, SharePoint-serveradministration, domänhantering, säkerhet och information i administrationsportalen för Office 365. 
Stöd för slutanvändare | Kunden ansvarar för att tillhandahålla slutanvändarsupport för: <br>- På plats infrastruktur: alla nätverks-och internetanslutning, VPN-infrastruktur och klientkonfiguration, lokal konferensrumutrustning, skrivare, proxyserver och konfiguration, brandväggar.<br><br>- Företagsomfattande molnresurser: e-post, SharePoint, samarbetstjänster och annan molninfrastruktur som relaterar till företagets tekniska fotavtryck.<br><br>- Bransch och alla andra företagsspecifika applikationer.
Apps | Roller och ansvarsområden varierar något för de appar som tillhandahålls som en del av Microsoft Managed Desktop jämfört med de du tillhandahåller. <br><br>För appar som tillhandahålls av Microsoft (Office 365 ProPlus som består av Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, team och OneNote) tillhandahåller **Microsoft** full service för distribution, uppdatering och support. **Du** måste skaffa och tilldela licenser för dessa appar, lägga till användare i säkerhetsgrupper och hantera uttjänta och distribuera alla Office 365-tillägg du behöver.<br><br>För appar som du tillhandahåller (till exempel dina företagsappar), oavsett om du paketerar dem själv eller anlitar en leverantör som inte kommer från Microsoft för att göra det, är **du** ansvarig för dessa åtgärder: <br><br>- Identifiera program som behövs för riktade användargrupper<br>- Skapa och hantera Azure AD-grupper för appdistribution<br>- Paketera appar för att uppfylla Microsoft Intune-distributionsstandarder<br>- Ladda upp appar till Microsoft Intune<br>- Testa appar i Microsoft Managed Desktop-miljö<br>- Testa appar med slutanvändarna<br>- Hantera och tilldela användare till program<br>- Identifiera och distribuera programuppdateringar via Microsoft Intune<br>- Avinstallera och ta bort program när de har gått i pension<br>- Upphandling och tilldelning av licenser<br>- Ge slutanvändarsupport för företagsspecifika appar<br>- Hantera appinställningar på distans<br><br>**Microsoft** tillhandahåller Microsoft Intune-distributionsverktyg för att leverera programmen till fjärrklienter.<br><br>Mer information finns i [Appar](../get-ready/apps.md)
Övervakning och svar på säkerhet | Kunden ansvarar för att undersöka och lösa incidenter för enheter som inte har hanterat svara på Microsoft-skrivbordsenheter och se till att Microsoft Managed Desktop Operations Team informeras om eventuella problem som kan påverka tjänsten.
Driftstöd | Kunden ansvarar för att tillhandahålla en lista över föredragna kundkontakter och ämnesexperter. Microsoft behöver dessa om det finns en driftincident som inte kommer från Microsoft Managed Desktop. <br><br>Kunden ansvarar också för att undersöka och lösa incidenter för enheter och tjänster som inte är Microsoft Managed Desktop och se till att Microsoft Managed Desktop Operations Team alltid informeras .
Nätverksinfrastruktur, inklusive VPN | Kunden ansvarar för installation, konfiguration och hantering (inklusive felsökning och felsökning) av all nätverksrelaterad infrastruktur och tjänster, inklusive internetanslutning, nätverkskontroller, proxykonfiguration och fjärranslutning anslutningsinfrastruktur.<br><br>Om en proxy är konfigurerad (i maskinvara eller programvara) finns det en samling webbadresser som måste tillåtas av proxyn. Kunden ansvarar för felsökning av eventuella konflikter eller inkompatibiliteter på grund av flera proxyservrar. Du kan lägga till nätverksproxyservrar som är specifika för din organisation med hjälp av konfigurerbara inställningar. Mer information finns i [Konfigurera inställningar](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Mer information finns i [Proxykonfiguration](../get-ready/network.md).
Utskrift | Kunden ansvarar för att installera, underhålla och administrera skrivare och skriva ut köer. Molnutskrift är en rekommenderad lösning, men krävs inte. 




