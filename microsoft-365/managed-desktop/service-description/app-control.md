---
title: Appkontroll
description: Så här använder du appkontroll och förtroende för program
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841309"
---
# <a name="app-control"></a>Appkontroll

Appkontroll är en valfri säkerhetsmetod i Microsoft Hanterat skrivbord som begränsar körningen av kod på klientenheter. Den här kontrollen minimerar risken för skadlig programvara eller skadliga skript genom att kräva att endast kod som signerats av en kundgodkänd lista med utgivare kan köras. Det finns många säkerhetsfördelar med den här kontrollen, men den strävar främst efter att skydda data och identitet från klientbaserade sårbarheter.

Microsoft Hanterat skrivbord förenklar hanteringen av principer för appkontroll genom att skapa en basprincip som möjliggör grundläggande produktivitetsscenarier. Du kan utöka förtroende till andra signerare som är specifika för de program och skript i din miljö. 


Alla säkerhetsteknik kräver en balans mellan användarupplevelse, säkerhet och kostnad. Appkontroll minskar risken för skadlig programvara i din miljö, men det finns konsekvenser för användaren och ytterligare åtgärder för IT-administratören.

**Ytterligare säkerhet:**

Appar eller skript som inte är betrodda av programkontrollprincipen blockeras från att köras på enheter.

**Dina ytterligare ansvarsområden:**

- Du ansvarar för att testa dina appar för att ta reda på om de blockeras av programkontrollprincipen.
- Om en app blockeras (eller skulle blockeras) ansvarar du för att identifiera den nödvändiga undertecknarinformationen och begära en ändring via administratörsportalen.

**Microsoft Hanterat skrivbord ansvarsområden:**

- Microsoft Hanterat skrivbord principen som ger möjlighet till grundläggande Microsoft-produkter som M365-appar, Windows, Teams, OneDrive och så vidare.
- Microsoft Hanterat skrivbord infogar betrodda undertecknare och distribuerar den uppdaterade principen på dina enheter.


## <a name="managing-trust-in-applications"></a>Hantera förtroende i program

Microsoft Hanterat skrivbord en basprincip som litar på huvudkomponenterna av Microsoft-tekniker. Sedan kan *du lägga* till förtroende för dina egna program och skript genom att Microsoft Hanterat skrivbord vilka av dem du redan litar på.

### <a name="base-policy"></a>Basprincip

Microsoft Hanterat skrivbord, i samarbete med Microsofts experter på cybersäkerhet, skapar och upprätthåller en standardprincip som gör att de flesta appar distribueras via Microsoft Intune samtidigt som de blockerar skadliga aktiviteter som kodkompilering eller körning av filer som inte är betrodda.

Basprincipen använder följande metod för att begränsa körning av programvara:

- Filer som körs av administratörer tillåts att köras.
- Filer på platser som *inte finns* i användarskrivbara kataloger kan köras.
- Filer har signerats av [en betrodd undertecknare](#signer-requests).
- De flesta filer signerade av Microsoft körs, men vissa blockeras för att förhindra högriskåtgärder som kodkompilering.


Om en annan användare än en administratör kan ha lagt till ett program eller skript på en enhet (d.v.s. den finns i en användarskrivbar katalog) tillåter vi inte att den körs såvida den inte redan har tillåtits av en administratör. Om en användare luras att installera skadlig programvara, om ett problem finns i ett program som användaren kör försöker installera skadlig programvara, eller om en användare avsiktligt försöker köra ett obehörigt program eller skript, stoppar vår princip körningen.

### <a name="signer-requests"></a>Undertecknarbegäranden

Du informerar oss om vilka appar som tillhandahålls av programvaruutgivare som du litar på genom att spara en *undertecknares begäran.* När vi gör det lägger vi till den förtroendeinformationen i kontrollprincipen för originalprogram och tillåter att all programvara som är signerad med den utgivarens certifikat körs på dina enheter.

## <a name="audit-and-enforced-policies"></a>Granska och tillämpa principer

Microsoft Hanterat skrivbord två principer Microsoft Intune för att ge appkontroll:

### <a name="audit-policy"></a>Granskningspolicy
Den här principen skapar loggar för att spela in om ett program eller skript ska blockeras av enforced-principen. Granskningsprinciper upprätthåller inte appkontrollregler och är avsedda för teständamål för att identifiera om ett program kommer att kräva ett undantag från utgivaren. Den loggar varningar (8003- eller 8006-händelser) i Loggboken i stället för att blockera körning eller installation av angivna appar eller skript.

### <a name="enforced-policy"></a>Tillämpad princip
Den här principen blockerar icke betrodda appar och skript från att köras och skapar loggar när ett program eller skript blockeras. Användarprinciper hindrar standardanvändare från att köra appar eller skript som lagras i användar skrivbara kataloger.

Enheter i gruppen Test har en granskningsprincip tillämpad så att du kan använda dem för att verifiera om några program orsakar problem. Alla andra grupper (Första, Snabb och Bred) använder en tillämpad princip, så att användare i de grupperna inte kan köra icke betrodda appar eller skript.







