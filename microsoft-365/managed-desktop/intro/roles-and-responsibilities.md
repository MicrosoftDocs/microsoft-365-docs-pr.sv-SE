---
title: Roller och ansvar för Microsoft Hanterat skrivbord
description: I den här artikeln beskrivs de roller och ansvarsområden som Microsoft tillhandahåller för Microsoft Hanterat skrivbord.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7b9efe1a52c108e3de46429d64f9a5535ad13e4e
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362756"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roller och ansvar för Microsoft Hanterat skrivbord


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Vad gör Microsoft för dig när din Microsoft Hanterat skrivbord registreras i office? Och vilka är din organisations ansvarsområden?

## <a name="microsofts-roles-and-responsibilities"></a>Microsofts roller och ansvarsområden

Microsoft tillhandahåller dessa viktiga roller och ansvarsområden:

Roll eller ansvar | Beskrivning
--- | ---
MDM-policyhantering | Microsoft tillämpar MDM-principer i enlighet med metodtips och överväger förfrågningar om principändringar. Vi kommer också att göra ändringar i din klientorganisation på det sätt som bestämts [i enhetsprinciper.](../service-description/device-policies.md)
Användarsupport | Vi tillhandahåller en mekanism för utökad åtkomst till enheter och för problem att eskalera om det behövs. Mer information finns i [Användarsupport.](../service-description/user-support.md)
Microsoft Hanterat skrivbord tjänstsupport | Microsoft ger support till din IT-avdelning via ett Microsoft Hanterat skrivbord Operations Team. Det här teamet kommer att stödja teknisk felsökning, ändringsförfrågningar och incidenthantering för kundens Microsoft Hanterat skrivbord miljö. Mer information finns i [administratörssupport för Microsoft Hanterat skrivbord](../working-with-managed-desktop/admin-support.md).
Säkerhetsövervakning | Microsoft övervakar dina e Microsoft Hanterat skrivbord enheter med hjälp av Microsoft Defender för Endpoint. Om Microsoft Hanterat skrivbord säkerhetsoperationscenter (SOC) upptäcker ett hot meddelar vi dig, isolerar enheten och åtgärdar problemet på distans. Mer information finns i [Säkerhet](../service-description/security.md).
Uppdatera övervakning och hantering | Vi övervakar aktivt dina Microsoft Hanterat skrivbord enheter för att säkerställa att den senaste kvaliteten och funktionsuppdateringarna installeras för Microsoft Windows och Microsoft Office. Mer information finns i [Hur uppdateringar hanteras.](../service-description/updates.md)
Användar- och enhetsgruppering | Microsoft Hanterat skrivbord kommer att skapa och hantera nödvändiga enhets- och användargrupper som en del av IT-drift. Inga medlemskaps- eller konfigurationsändringar tillåts för dessa grupper. Om du ändrar de här grupperna kan det leda till oväntad konfiguration av enheter och förlust av funktioner. För eventuella problem eller frågor runt de här grupperna, kan IT-administratörer kontakta Microsoft Hanterat skrivbord åtgärder. Mer information finns i [administratörssupport för Microsoft Hanterat skrivbord](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Dina roller och ansvarsområden

Denna uppsättning vanliga roller och ansvarsområden krävs för distribution, men tillhandahålls inte av Microsoft. Den är inte uttömmande men gäller för de flesta organisationer. Det finns några saker som både du och Microsoft ansvarar för. 

Roll eller ansvar | Beskrivning
--- | ---
Ändringshantering | Microsoft meddelar kunderna i förväg när ändringar behöver göras i deras Microsoft Hanterat skrivbord miljö. Mer information finns i [tjänständringar och kommunikation.](../service-description/servicechanges.md)<br><br>Du måste ha en egen hanteringsprocess för ändringar och upprätta en kontakt med Microsoft Hanterat skrivbord Operations Team. Du måste också ha resurser för att granska och godkänna ändringarna. Mer information finns i [Åtgärder och övervakning](../service-description/operations-and-monitoring.md).  
Identitetshantering | Du ansvarar för att skapa användarkonton, tilldela användare till grupper och hålla metadata uppdaterade. 
Microsoft 365-appar för företag konfiguration och hantering | Microsoft ansvarar för Office att program distribueras till användare och att de hålls uppdaterade. <br><br> Du ansvarar för att Microsoft 365 tjänster och principer, Exchange Online bland annat administrativa ansvarsområden:<br>- E-postadministration<br>- Postlåde- och regelkonfiguration<br>- Exchange med lokal hantering<br><br>Du ansvarar även för samarbetsverktyg, SharePoint serveradministration, domänhantering och säkerhets- och informationsprinciper som anges i Administrationscenter för Microsoft 365. 
Användarsupport | Tillhandahålla all användarsupport och teknisk support från första kontakten till lösningen för användaren, antingen av dig eller via en angiven supportpartner. Du måste ge support direkt till användarna eller samarbeta med en partner för att ge support för dessa områden: <br><br>- Infrastruktur på plats: alla nätverk och Internetanslutning, VPN-infrastruktur och klientkonfiguration, lokal konferensrumsutrustning, skrivare, proxyserver och konfiguration samt brandväggar.<br><br>- Företagsomfattande molnresurser: e-SharePoint, SharePoint, samarbetstjänster och annan molninfrastruktur som relaterar till företagets teknikavtryck.<br><br>- Verksamhetsspecifika appar och andra företagsspecifika program.
Appar | Roller och ansvarsområden varierar något för de appar som tillhandahålls som en del av Microsoft Hanterat skrivbord jämfört med de appar du tillhandahåller. <br><br>För appar som tillhandahålls av Microsoft (Microsoft 365-appar för företag som omfattar Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, Teams och OneNote) tillhandahåller **Microsoft** fullständiga tjänster för distribution, uppdatering och support. **Du** måste skaffa och tilldela licenser för programmen, lägga till användare i säkerhetsgrupper och hantera slutet av livscykeln och distribuera de tillägg du behöver.<br><br>För program som du tillhandahåller (till exempel verksamhetsbaserade appar), oavsett om du paketerar dem själv eller engagerar en leverantör som inte är Microsoft-leverantör **för** det, ansvarar du för följande åtgärder: <br><br>- Identifiering av program som krävs för riktade användargrupper<br>- Skapa och hantera Azure AD-grupper för appdistribution<br>- Paketera appar för att uppfylla Microsoft Intune för distribution<br>- Ladda upp appar till Microsoft Intune<br>- Testa appar i Microsoft Hanterat skrivbord miljö<br>- Testa appar med dina användare<br>- Hantera och tilldela användare till program<br>- Identifiera och distribuera programuppdateringar via Microsoft Intune<br>- Avinstallera och ta bort program när de har tagits bort<br>- Införskaffa och tilldela licenser<br>- Tillhandahållande av användarstöd för verksamhetsbaserade appar<br>- Hantera appinställningar på distans<br><br>**Microsoft** tillhandahåller Microsoft Intune för distributionsverktyg för att leverera programmen till fjärrklienter.<br><br>Mer information finns i [Program](../get-ready/apps.md).
Säkerhetsövervakning och svar | Du ansvarar för att undersöka och lösa incidenter för enheter som inte är Microsoft Hanterat skrivbord-enheter och se till att Microsoft Hanterat skrivbord Operations Team är informerad om eventuella problem som kan påverka tjänsten.
Stöd för åtgärder | Du måste ange en lista över önskade kontakter och ämnesexperter i organisationen. Vi behöver de här kontakterna om det finns en drifthändelse som inte är relaterad till Microsoft Hanterat skrivbord. <br><br>Du är också ansvarig för att undersöka och lösa incidenter för enheter och tjänster som inte finns i Microsoft Hanterat skrivbord och se till att Microsoft Hanterat skrivbord Operations Team alltid informeras.
Nätverksinfrastruktur, inklusive VPN | Du ansvarar för konfiguration, konfiguration och hantering (inklusive felsökning och felsökning) av alla nätverksrelaterade infrastrukturer och tjänster, inklusive internetanslutning, nätverkskontroller, proxykonfiguration och infrastruktur för fjärranslutning.<br><br>Om en proxy är konfigurerad (i maskinvara eller programvara) finns det en samling URL-adresser som måste tillåtas av proxyn. Du är ansvarig för att felsöka eventuella konflikter eller inkompatibiliteter på grund av flera proxy. Du kan lägga till nätverksproxier som är specifika för organisationen med konfigurerbara inställningar. Mer information finns i [Konfigurerbara inställningar](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Mer information finns i [Proxykonfiguration](../get-ready/network.md).
Skriva ut | Du är ansvarig för att installera, underhålla och administrera skrivare och utskriftsköer. Molnutskrift är en rekommenderad lösning, men den är inte obligatorisk. 




