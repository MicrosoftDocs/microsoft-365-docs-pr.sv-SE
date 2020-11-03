---
title: Roller och ansvar för Microsoft Hanterat skrivbord
description: I den här artikeln beskrivs de roller och ansvars områden som tillhandahålls av Microsoft för Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: de0bc092c35c7f48c562da8d4218f7a638abe1d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847786"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roller och ansvar för Microsoft Hanterat skrivbord


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Vad gör Microsoft åt dig när din organisation är registrerad på Microsoft Managed Desktop? Och vilka är organisationens ansvar?

## <a name="microsofts-roles-and-responsibilities"></a>Microsofts roller och ansvar

Microsoft tillhandahåller dessa viktiga roller och ansvars områden:

Roll eller ansvar | Beskrivning
--- | ---
Princip hantering för MDM | Microsoft tillämpar MDM-principer enligt bästa praxis och Överväg begär Anden om princip ändringar. Vi kommer även att göra ändringar i din klient organisation enligt vad som anges i [enhets principer](../service-description/device-policies.md).
stöd för användare | Vi tillhandahåller användar stöd för enheter, Windows och Microsoft 365-programmen för företags produkt paketet för alla registrerade användare via appen skaffa hjälp som är förinstallerad på alla Microsoft-hanterade Station ära enheter. 
Stöd för Microsoft Managed Desktop service | Microsoft tillhandahåller support för din IT-avdelning via ett Microsoft Managed Station ära datorer. Det här teamet kommer att stödja teknisk fel sökning, ändrings förfrågningar och ärende hantering för kundens Microsoft-hanterade Skriv bords miljö. Mer information finns i [Administratörs support för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Säkerhets övervakning | Microsoft övervakar dina Microsoft-hanterade Skriv bords enheter med Microsoft Defender för slut punkten. Om Microsoft Managed Desktop Security Operations Center (SOC) upptäcker ett hot meddelar vi dig, isolerar enheten och kan lösa problemet från fjärran. Mer information finns i [säkerhet](../service-description/security.md).
Uppdaterings övervakning och-hantering | Vi övervakar nu dina Microsoft Managed Station ära enheter för att säkerställa att de senaste kvalitets-och funktions uppdateringarna installeras för Microsoft Windows och Microsoft Office. Mer information finns i [hur uppdateringar hanteras](../service-description/updates.md).
Gruppering av användare och enheter | Microsoft Managed Desktop Operations Group skapar och hanterar nödvändiga enheter och användar grupper som en del av IT-operationer. Inga medlemskaps-eller konfigurations ändringar är tillåtna för dessa grupper. Ändring av dessa grupper kan leda till oväntad konfiguration av enheter och funktions nedsättning. För eventuella problem eller frågor kring dessa grupper när de har upprättats kan IT-administratörer kontakta Microsoft Managed Station ära datorer. Mer information finns i [Administratörs support för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Dina roller och behörigheter

Denna ytterligare uppsättning gemensamma roller och ansvar krävs för distribution, men tillhandahålls inte av Microsoft. Det är inte uttömmande men det är lämpligt för de flesta organisationer. Det finns några saker som både du och Microsoft delar ansvaret för. 

Roll eller ansvar | Beskrivning
--- | ---
Ändrings hantering | Microsoft kommer att meddela kunderna i förväg när ändringar måste göras i Microsofts hanterade Skriv bords miljö. Mer information finns i [tjänst ändringar och kommunikation](../service-description/servicechanges.md).<br><br>Du måste ha en egen process för ändrings hantering och ha en kontakt etablerad med Microsoft Managed Desktop-teamet. Du måste också ha resurser för att granska och godkänna dessa ändringar. Mer information finns i [åtgärder och övervakning](../service-description/operations-and-monitoring.md).  
Identitets hantering | Du är ansvarig för att skapa användar konton, tilldela användare till grupper och hålla metadata uppdaterade. 
Microsoft 365-appar för företags konfiguration och-hantering | Microsoft är ansvarigt för att säkerställa att Office-programmen distribueras till användarna och att dessa program hålls uppdaterade. <br><br> Du är ansvarig för att hantera Microsoft 365-tjänster och-principer, inklusive administrations ansvar för Exchange Online:<br>-E-postadministrering<br>-Post låda och regel konfiguration<br>-Lokal hantering av Exchange<br><br>Du är också ansvarig för samarbets verktyg, administration av SharePoint Server, domän hantering och säkerhets-och informations principer som anges i administrations centret för Microsoft 365. 
Användarsupport | Du måste tillhandahålla användar stöd för: <br>-Infrastruktur på plats: alla nätverks-och Internet anslutningar, VPN-infrastruktur och klient konfiguration, lokal konferens rums utrustning, skrivare, proxyserver och konfiguration samt brand väggar.<br><br>-Moln resurser för hela företaget: e-post, SharePoint, samarbets tjänster och annan moln infrastruktur som är kopplad till teknikerna för hela företaget.<br><br>-Affärs område och alla andra företagsspecifika program.
Appar | Roller och ansvars områden varierar lite för de program som tillhandahålls som Microsoft hanterade skriv bord jämfört med de program du tillhandahåller. <br><br>För program som tillhandahålls av Microsoft (Microsoft 365-appar för företag som omfattar Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, teams och OneNote) tillhandahåller **Microsoft** fullständig service för distribution, uppdatering och support. **Du** måste skaffa och tilldela licenser för dessa appar, lägga till användare i säkerhets grupper och hantera livs längd och distribuera eventuella tilläggs komponenter.<br><br>För de program du tillhandahåller (till exempel dina branschspecifika appar), oavsett om du paketerar dem själv eller om du inte vill att Microsoft ska göra det, är **du** ansvarig för dessa åtgärder: <br><br>-Identifiera program som behövs för riktade användar grupper<br>-Skapa och hantera Azure AD-grupper för program distribution<br>-Paketera program för att uppfylla distributions standarder för Microsoft Intune<br>-Laddar upp appar till Microsoft Intune<br>-Testa appar i Microsoft Managed Desktop Environment<br>-Testa appar med dina användare<br>-Hantera och tilldela användare till program<br>-Identifiera och distribuera program uppdateringar via Microsoft Intune<br>-Avinstallerar och tar bort program när de har avvecklats<br>-Proanskaffning och tilldelning av licenser<br>-Ge användar stöd för branschspecifika program<br>-Hantera program inställningar från en fjärrdator<br><br>**Microsoft** tillhandahåller distributions verktyg för Microsoft Intune för att leverera program till fjärrklienter.<br><br>Mer information finns i [program](../get-ready/apps.md).
Säkerhetsövervakning och svar | Du är ansvarig för att undersöka och lösa incidenter för enheter som inte är Microsoft-hanterade Station ära enheter och säkerställer att Microsoft Managed Desktop-avdelningen informeras om eventuella problem som kan påverka tjänsten.
Stöd för operationer | Du måste ange en lista över önskade kontakter och ämnes experter i din organisation. Vi behöver dessa om det rör sig om en åtgärd som inte är relaterad till Microsoft Managed Desktop. <br><br>Du är också ansvarig för att undersöka och lösa incidenter för enheter och tjänster som inte finns på Microsoft Managed Desktop och säkerställer att Microsoft Managed Desktop Operations team alltid informeras.
Nätverks infrastruktur, inklusive VPN | Du är ansvarig för konfiguration, konfiguration och hantering (inklusive fel sökning och problemlösning) för alla nätverksrelaterade infrastrukturer och tjänster, inklusive Internet anslutning, nätverks inställningar, proxykonfiguration och infrastruktur för fjärr anslutning.<br><br>Om en proxyserver är konfigurerad (i maskin vara eller program vara) finns det en samling URL-adresser som måste tillåtas av proxyn. Du är ansvarig för fel sökning av eventuella konflikter eller kompatibilitetsproblem på grund av flera proxyservrar. Du kan lägga till nätverks proxyservrar som är specifika för din organisation med konfigurerbara inställningar. Mer information finns i [Konfigurera inställningar](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Mer information finns i [proxykonfiguration](../get-ready/network.md).
Direktutskrift | Du är ansvarig för att installera, underhålla och administrera skrivare och utskrifts köer. Moln utskrift är en rekommenderad lösning men den är inte nödvändig. 




