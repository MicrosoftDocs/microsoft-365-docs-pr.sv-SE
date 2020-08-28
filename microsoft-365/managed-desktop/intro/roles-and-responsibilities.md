---
title: Roller och ansvar för Microsoft Hanterat skrivbord
description: I det här avsnittet beskrivs de roller och ansvars områden som tillhandahålls av Microsoft för Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8cec5a99d2275e451ceac9004a922820e4b3e726
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289751"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roller och ansvar för Microsoft Hanterat skrivbord


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Vad gör Microsoft åt dig när din organisation är registrerad på Microsoft Managed Desktop? Och vilka är organisationens ansvar?

## <a name="microsofts-roles-and-responsibilities"></a>Microsofts roller och ansvar

Nedan följer några viktiga roller och ansvars områden som tillhandahålls av Microsoft.

Roll eller ansvar | Beskrivning
--- | ---
Princip hantering för MDM | Microsoft tillämpar MDM-principer enligt bästa praxis och Överväg begär Anden om princip ändringar. Vi kommer även att göra ändringar i din klient organisation enligt vad som anges i [enhets principer](../service-description/device-policies.md).
stöd för användare | Microsoft tillhandahåller användar stöd för enheter, Windows och Office-programpaket för alla registrerade användare via appen skaffa hjälp som är förinstallerad på alla Microsoft-hanterade enheter. 
Stöd för Microsoft Managed Desktop service | Microsoft tillhandahåller support för kund IT-avdelningar via Microsoft Managed Station ära datorer. Det här teamet kommer att stödja teknisk fel sökning, ändrings förfrågningar och ärende hantering för kundens Microsoft-hanterade Skriv bords miljö. Mer information finns i [Administratörs support för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Säkerhets övervakning | Microsoft övervakar kunder som hanteras av Microsoft med Microsoft Defender ATP. Om ett hot identifieras av Microsoft Managed Desktop Security Operations Center (SOC) kommer Microsoft att meddela kunden, isolera enheten och åtgärda det från fjärran. Mer information finns i [säkerhet](../service-description/security.md).
Uppdaterings övervakning och-hantering | Microsoft kommer aktivt att övervaka Microsoft-hanterade Station ära enheter för att säkerställa att de senaste kvalitets-och funktions uppdateringarna installeras för Microsoft Windows och Microsoft Office. Mer information finns i [hur uppdateringar hanteras](../service-description/updates.md).
Gruppering av användare och enheter | Microsoft Managed Desktop Operations Group skapar och hanterar nödvändiga enheter och användar grupper som en del av IT-operationer. Inga medlemskaps-eller konfigurations ändringar är tillåtna för dessa grupper. Ändring av dessa grupper kan leda till oväntad konfiguration av enheter och funktions nedsättning. För eventuella problem eller frågor kring dessa grupper när de har upprättats kan IT-administratörer kontakta Microsoft Managed Station ära datorer. Mer information finns i [Administratörs support för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Dina roller och behörigheter

Nedan följer en ytterligare uppsättning gemensamma roller och ansvars områden som inte tillhandahålls av Microsoft, men som krävs för en lyckad installation. Det är inte uttömmande men det är lämpligt för de flesta organisationer. Det finns några poster nedan som både Microsoft och kund ansvars områden. 

Roll eller ansvar | Beskrivning
--- | ---
Ändrings hantering | Microsoft kommer att meddela kunderna i förväg när ändringar måste göras i Microsofts hanterade Skriv bords miljö. Mer information finns i [tjänst ändringar och kommunikation](../service-description/servicechanges.md)<br><br>Kunden måste ha sin egen process för ändrings hantering och ha en kontakt som är etablerad med Microsoft Managed Station ära datorer. Kunden måste också ha resurser för att kunna granska och godkänna dessa ändringar. Mer information finns i [åtgärder och övervakning](../service-description/operations-and-monitoring.md).  
Identitets hantering | Kunden är ansvarig för att skapa användar konton, tilldela användare till grupper och hålla metadata uppdaterade. 
Microsoft 365-appar för företags konfiguration och-hantering | Microsoft är ansvarigt för att säkerställa att Office-programmen distribueras till användarna och att dessa program hålls uppdaterade. <br><br> Kunden ansvarar för att hantera Microsoft 365-tjänster och-principer, inklusive Exchange Online administrations ansvar:<br>-E-postadministrering<br>-Post låda och regel konfiguration<br>-Lokal hantering av Exchange<br><br>Kunden är också ansvarig för samarbets verktyg, administration av SharePoint Server, domän hantering, säkerhets-och informations principer som angetts i Microsoft 365 Admin Center. 
Stöd för användare | Kunden ansvarar för att tillhandahålla användar support för: <br>-Webbplats infrastruktur: alla nätverks-och Internet anslutningar, VPN-infrastruktur och klient konfiguration, lokala konferens rum utrustning, skrivare, proxyserver och konfiguration, brand väggar.<br><br>-Moln resurser för hela företaget: e-post, SharePoint, samarbets tjänster och annan moln infrastruktur som är kopplad till teknikerna för hela företaget.<br><br>-Affärs område och alla andra företagsspecifika program.
Appar | Roller och ansvars områden skiljer sig lite åt för de program som tillhandahålls som Microsoft hanterade skriv bord jämfört med de du tillhandahåller. <br><br>För program som tillhandahålls av Microsoft (Microsoft 365-appar för företag som omfattar Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, teams och OneNote) tillhandahåller **Microsoft** fullständig service för distribution, uppdatering och support. **Du** måste skaffa och tilldela licenser för dessa appar, lägga till användare i säkerhets grupper och hantera slut på livet och distribuera eventuella tillägg du behöver.<br><br>För de program du tillhandahåller (till exempel dina branschspecifika appar), oavsett om du paketerar dem själv eller om du inte vill att Microsoft ska göra det, är **du** ansvarig för dessa åtgärder: <br><br>-Identifiera program som behövs för riktade användar grupper<br>-Skapa och hantera Azure AD-grupper för program distribution<br>-Paketera program för att uppfylla distributions standarder för Microsoft Intune<br>-Laddar upp appar till Microsoft Intune<br>-Testa appar i Microsoft Managed Desktop Environment<br>-Testa appar med dina användare<br>-Hantera och tilldela användare till program<br>-Identifiera och distribuera program uppdateringar via Microsoft Intune<br>-Avinstallerar och tar bort program när de har avvecklats<br>-Proanskaffning och tilldelning av licenser<br>-Ge användar stöd för branschspecifika program<br>-Hantera program inställningar från en fjärrdator<br><br>**Microsoft** tillhandahåller distributions verktyg för Microsoft Intune för att leverera program till fjärrklienter.<br><br>Mer information finns i [program](../get-ready/apps.md)
Säkerhetsrevision och svar | Kunden är ansvarig för att undersöka och lösa tillbud för icke-hanterade Skriv bords enheter och se till att Microsoft Managed Desktop-avdelningen informeras om eventuella problem som kan påverka tjänsten.
Stöd för operationer | Kunden är ansvarig för att tillhandahålla en lista över prioriterade kund kontakter och ämnes experter. Microsoft behöver dessa om det finns ett icke-hanterat Skriv bords tillbud som inte hanteras av Microsoft. <br><br>Kunden är också ansvarig för att undersöka och lösa tillbud för icke-hanterade Skriv bords enheter och-tjänster som inte hanteras av Microsoft och säkerställer att Microsoft Managed Desktop Operations-teamet alltid är informerade.
Nätverks infrastruktur, inklusive VPN | Kunden är ansvarig för konfiguration och konfiguration och hantering (inklusive fel sökning och avlusning) av alla nätverksrelaterade infrastrukturer och tjänster, inklusive Internet anslutning, nätverks inställningar, proxykonfiguration och fjärr anslutnings infrastruktur.<br><br>Om en proxyserver är konfigurerad (i maskin vara eller program vara) finns det en samling URL-adresser som måste tillåtas av proxyn. Kunden ansvarar för fel sökning av eventuella konflikter eller kompatibilitetsproblem på grund av flera proxyservrar. Du kan lägga till nätverks proxyservrar som är specifika för din organisation med konfigurerbara inställningar. Mer information finns i [Konfigurera inställningar](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Mer information finns i [proxykonfiguration](../get-ready/network.md).
Direktutskrift | Kunden ansvarar för att installera, underhålla och administrera skrivare och utskrifts köer. Moln utskrift är en rekommenderad lösning men är inte nödvändig. 




