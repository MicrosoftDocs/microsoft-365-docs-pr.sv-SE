---
title: Tilldela och slutföra förbättringsåtgärder i Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du utför implementering och testning av kontroller i Microsoft Compliance Manager. Tilldela arbete, lagra dokumentation och exportera rapporter.
ms.openlocfilehash: f2674e24ed38362c5c7563a574e0dba9c81f2584
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149040"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Tilldela och slutföra förbättringsåtgärder i Efterlevnadshanteraren

**I den här artikeln:** I den här artikeln förklaras hur **du hanterar arbetsflödet för efterlevnad** med förbättringsåtgärder. Lär dig hur **du tilldelar förbättringsåtgärder** för implementering och **testning, hanterar** uppdateringar och **exporterar rapporter.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Hantera arbetsflöden för efterlevnad med förbättringsåtgärder

Förbättringsåtgärder centraliserar dina efterlevnadsaktiviteter. Varje förbättringsåtgärd ger detaljerad implementeringsvägledning som hjälper dig att anpassa till dataskyddsföreskrifter och standarder. Åtgärder kan tilldelas användare i organisationen för att utföra implementerings- och testarbete. Du kan också lagra dokumentation, anteckningar och spela in statusuppdateringar i åtgärden.

Alla dina förbättringsåtgärder visas på sidan för förbättringsåtgärder. Läs mer om [att visa förbättringsåtgärder](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Informationssida för förbättringsåtgärder

Varje förbättringsåtgärd har en informationssida som visar aktuell status, relaterade standarder och föreskrifter samt rekommenderad implementeringsvägledning. [Tekniska åtgärder](compliance-score-calculation.md#technical-and-non-technical-actions) innehåller en **Launch now-länk** som tar dig till lämplig lösning för implementering. Du kan bifoga dokumentation om implementering och testning direkt på informationssidan för en förbättringsåtgärd.

Så här visar du informationssidan för en förbättringsåtgärd:

1. Gå till sidan för förbättringsåtgärder.
2. Markera raden för den avsedda förbättringsåtgärden, som öppnar informationssidan.

Du kan enkelt visa nästa eller föregående förbättringsåtgärd i listan genom att välja uppåt- eller nedåtpilen i det övre högra hörnet av skärmen. Om du har filtrerat listan på sidan för förbättringsåtgärder flyttas du upp eller ned till nästa objekt i den filtrerade listan.

## <a name="assign-improvement-actions"></a>Tilldela förbättringsåtgärder

Om du vill börja använda implementering av en förbättringsåtgärd kan du göra arbetet själv eller tilldela det till en annan användare. Den tilldelade personen kan vara:

- En ägare till en affärspolicy
- En IT-implementerare
- En annan anställd med ansvar för att utföra uppgiften

När du har identifierat rätt mottagare bör du se till att de har en tillräcklig [efterlevnadshanteraren-roll](compliance-manager-setup.md#set-user-permissions-and-assign-roles) för att utföra arbetet. Följ sedan anvisningarna nedan för att tilldela förbättringsåtgärden:

1. På sidan för förbättringsåtgärder väljer du **Redigera status** nära skärmens övre vänstra del.

2. I det utfällfältet för redigeringsstatus väljer du **rutan** Tilldelad för att visa **listan Föreslagna** personer med användare. Du kan välja användaren i listan eller skriva e-postadressen till den person som du vill tilldela den till.

3. Välj **Spara och stäng**. Den tilldelade användaren får ett e-postmeddelande som förklarar att förbättringsåtgärden har tilldelats dem, med en direkt länk till förbättringsåtgärden. 
> [!NOTE]
> Kunder i amerikanska Government Community (GCC) High and Department of Defense (DoD) får inte ett e-postmeddelande när de har tilldelats förbättringsåtgärder.

Den tilldelade användaren kan sedan utföra de rekommenderade åtgärderna.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Tilldela flera förbättringsåtgärder till en enskild användare

Du kan tilldela flera förbättringsåtgärder till en användare genom att följa de här stegen:

1. Gå till sidan Förbättringsåtgärder.
2. Markera området till vänster om namnet på förbättringsåtgärden. En rund bcheckikon visas som anger att du har markerat åtgärden. Markera alla åtgärder som du vill tilldela.
3. Välj länken **Tilldela till användare** högst upp i tabellen förbättringsåtgärder.
4. Ett popup-fönster visas. Börja **skriva namnet på** den person som du vill tilldela åtgärderna till i fältet Tilldela till. Du kan också välja från listan med föreslagna personer.
5. När du har fyllt **fältet Tilldela** till med tilldelans namn väljer du **Tilldela**.
6. Därefter visas sidan Förbättringsåtgärder med den nya tilldelad för de åtgärder du just har tilldelat.

## <a name="perform-work-and-store-documentation"></a>Arbeta och lagra dokumentation

Du kan ladda upp filer och anteckningar som rör implementering och testning direkt till **avsnittet Anteckningar och** dokumentation. Den här miljön är en säker, centraliserad lagringsplats där du kan visa att du är nöjd med kontrollerna för att uppfylla standarder och bestämmelser för efterlevnad. Alla användare med skrivskydd kan läsa innehållet i det här avsnittet. Endast användare med redigeringsbehörighet kan ladda upp och ladda ned filer och skriva eller redigera anteckningar.

Avsnittet **Anteckningar och dokumentation** innehåller fält för uppladdade dokument, implementeringsanteckningar, testanteckningar och ytterligare anteckningar.

#### <a name="uploaded-documents"></a>Uppladdade dokument

- Välj **Hantera dokument för** att ladda upp alla relevanta filer.
- När det utfällade fönstret Hantera dokument öppnas **väljer du Lägg till** dokument och väljer sedan filen från systemet. Godkända filtyper:
    - Dokument (.doc, .xls, .ppt, .txt, .pdf)
    - Bilder (.jpg, .png)
    - Video (.mkv)
    - Komprimerade filer (.zip, .rar)
- När filen matchas i fönstret väljer du **Stäng , som** automatiskt sparar den bifogade filen. Filen visas då under Uppladdade **dokument.**
- Om du vill ladda ned eller ta bort **dokumentet väljer du Hantera** dokument under listan med dokument. Markera dokumentraden i det utfällsbara fönstret och välj sedan Ladda **ned eller** Ta **bort.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Implementeringsanteckningar, testanteckningar och ytterligare anteckningar

- Om du vill lägga till anteckningar i något av de här tre fälten väljer du **Redigera implementeringsanteckningar** under något av de här fälten.
- När den utfällramade rutan öppnas anger du anteckningar i textfältet och väljer **sedan Spara och stäng**.
- Om du vill redigera anteckningar **väljer du Redigera implementeringsanteckningar**, gör dina ändringar och **väljer sedan Spara och stäng**.

Det finns ingen teckenbegränsning i anteckningsfälten. Vi rekommenderar att du håller anteckningarna korta så att du enkelt kan visa och redigera dem från informationssidan för förbättringsåtgärder.

## <a name="change-improvement-action-status"></a>Ändra status för förbättringsåtgärd

Du kan registrera implementeringsstatus och -datum samt teststatus och datum för varje förbättringsåtgärd. Fälten **för** **implementerings- och teststatus** kan redigeras av alla användare med redigeringsbehörighet, inte bara av den tilldelade personen.

Om du vill redigera status för en förbättringsåtgärd **väljer du Redigera status** i det övre vänstra avsnittet på informationssidan. Här är de tillgängliga fälten och statusalternativen:

- **Implementeringsstatus**
    - **Inte implementerat** – åtgärder har inte implementerats än
    - **Implementerad** – åtgärd implementerad
    - **Alternativ implementering** – välj det här alternativet om du har använt andra verktyg från tredje part eller har vidta andra åtgärder som inte ingår i Microsofts rekommendationer
    - **Planerat** – en åtgärd har planerats för implementering
    - **Utanför omfattningen –** åtgärden är inte relevant för din organisation och bidrar inte till ditt resultat
- **Implementeringsdatum:** tillgänglig att välja när implementeringsstatus "implementeras" eller "alternativ implementering"
- **Teststatus:** tillgänglig att välja när implementeringsstatus "implementeras" eller "alternativ implementering":
    - **Inte taxering** – åtgärden har inte testats
    - **Godkänd** – implementering har verifierats av en utvärderare
    - **Misslyckades med låg risk** – testning misslyckades, låg risk
    - **Misslyckade medelrisker** – testning misslyckades, medelrisk
    - **Misslyckades med hög risk** – testningen misslyckades, högrisk
    - **Inte omfattning** – åtgärden är inte begränsad till utvärderingen och bidrar inte till ditt resultat
- **Testdatum:** växla mellan kalender-popup för att välja datum

Vanliga åtgärder synkroniseras mellan grupper. När två olika utvärderingar i samma grupp delar förbättringsåtgärder som hanteras av dig kommer alla uppdateringar som du gör av en åtgärds implementeringsinformation eller status automatiskt att synkroniseras till samma åtgärd i någon annan utvärdering i gruppen. Med den här synkroniseringen kan du implementera en förbättringsåtgärd och uppfylla flera krav över flera bestämmelser.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Tilldela förbättringsåtgärd för att utvärderare för slutförande

När du har slutfört arbetet, genomför tester och laddar upp bevis är nästa steg att tilldela förbättringsåtgärden till en utvärderare för validering. Bedömaren validerar arbetet och undersöker dokumentationen och väljer lämplig teststatus.

**Om teststatus är inställd på "Godkänd"**: åtgärden är slutförd och poängen som uppnås visar maximalt antal poäng som har uppnåtts. Poäng räknas sedan in i ditt övergripande efterlevnadsresultat.

**Om teststatus är inställd på "Misslyckades"**: åtgärden uppfyller inte kraven, och utvärderingsanvändaren kan tilldela den till lämplig användare för ytterligare arbete.

## <a name="accepting-updates-to-improvement-actions"></a>Acceptera uppdateringar för förbättringsåtgärder

När det finns en uppdatering för en förbättringsåtgärd visas ett meddelande bredvid namnet. Du kan acceptera uppdateringen eller skjuta upp den till en senare tid.

#### <a name="what-causes-an-update"></a>Vad som orsakar en uppdatering

En uppdatering inträffar när det finns ändringar som rör poäng, automatisering eller omfattning. Ändringar kan innebära ny vägledning för förbättringsåtgärder som baseras på ändringar i lagstiftningen eller kan vara på grund av produktändringar. Endast de förbättringsåtgärder som hanteras av dina organisationer får meddelanden om uppdateringar.

#### <a name="where-youll-see-assessment-update-notifications"></a>Var du ser meddelanden om utvärderingsuppdatering

När en förbättringsåtgärd uppdateras visas  etiketten Väntande uppdatering bredvid namnet på sidan förbättringsåtgärder och på informationssidan för dess relaterade utvärderingar.

Gå till informationssidan för förbättringsåtgärden  och välj knappen Granska uppdatering i den övre banderollen för att granska information om ändringarna och godkänna eller skjuta på uppdateringen.

#### <a name="review-update-to-accept-or-defer"></a>Granska uppdatering för att acceptera eller skjuta på

När du **har valt** Granska uppdatering från sidan information om förbättringsåtgärden visas ett utfällt fönster till höger på skärmen. I det utfällda fönstret finns viktig information om uppdateringen, till exempel vilka utvärderingar som påverkas och ändringar av poäng och omfattning.

Välj **Acceptera uppdatering** för att acceptera alla ändringar i förbättringsåtgärden. **Godkända ändringar är permanenta.**

> [!NOTE]
> När du accepterar en uppdatering av en åtgärd accepterar du även uppdateringar för andra versioner eller instanser av den här åtgärden. Uppdateringar sprids för hela klientorganisationen för tekniska åtgärder, och gruppering sprids för icke-tekniska åtgärder.

Om du **väljer** Avbryt används inte uppdateringen för förbättringsåtgärden. Meddelandet Väntar på uppdatering visas fortfarande **tills** du accepterar uppdateringen.

**Därför rekommenderar vi att du accepterar uppdateringar**

Genom att acceptera uppdateringar får du de senaste råden om hur du använder lösningar och vidtar lämpliga förbättringsåtgärder som hjälper dig att uppfylla kraven för certifieringen.

**Varför det kan vara bra att skjuta på en uppdatering**

Om du håller på att slutföra en utvärdering som innehåller förbättringsåtgärden kanske du vill vara säker på att du har slutfört arbetet med den innan du accepterar uppdateringen. Du kan skjuta upp uppdateringen ett senare tillfälle genom att välja **Avbryt** i den utfällade granskningsuppdateringen.

#### <a name="accept-all-updates-at-once"></a>Acceptera alla uppdateringar på en gång

Om du har flera uppdateringar och vill acceptera dem  alla samtidigt väljer du länken Acceptera alla uppdateringar högst upp i tabellen för förbättringsåtgärder. En utfällingsruta visas med antalet åtgärder som ska uppdateras. Välj knappen **Acceptera uppdateringar** för att tillämpa alla uppdateringar.

Observera att när du återgår till sidan för förbättringsåtgärder kan du se ett meddelande högst upp på sidan där du uppmanas att uppdatera sidan för att slutföra uppdateringarna.

## <a name="export-a-report"></a>Exportera en rapport

Välj **Exportera** i skärmens övre vänstra hörn om du vill hämta ett Excel som innehåller alla förbättringsåtgärder och de filterkategorier som visas på sidan för förbättringsåtgärder.