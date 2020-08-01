---
title: Appkontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f11c7a4aa69c96232a33c565e7bf20d04b96d1f7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529977"
---
# <a name="app-control"></a>Appkontroll

Appkontroll är en valfri säkerhetspraxis i Microsoft Managed Desktop som begränsar körningen av kod på klientenheter. Den här kontrollen minskar risken för skadlig kod eller skadliga skript genom att kräva att endast kod som signeras av en kundgodkänd lista över utgivare kan köras. Det finns många säkerhetsfördelar med denna kontroll, men det syftar främst till att skydda data och identitet från kundbaserade bedrifter.

Microsoft Managed Desktop förenklar hanteringen av appkontrollprinciper genom att skapa en basprincip som möjliggör grundläggande produktivitetsscenarier. Du kan utöka förtroendet till ytterligare undertecknare som är specifika för appar och skript i din miljö. 


All säkerhetsteknik kräver en balans mellan användarupplevelse, säkerhet och kostnad. Appkontrollen minskar risken för skadlig programvara i din miljö, men det får konsekvenser för slutanvändaren och ytterligare åtgärder för IT-administratören.

**Ytterligare säkerhet:**

Appar eller skript som inte är betrodda av appkontrollprincipen blockeras från att köras på enheter.

**Dina extra ansvarsområden:**

- Du är ansvarig för att testa dina appar för att identifiera om de skulle blockeras av programkontrollprincipen.
- Om en app blockeras (eller skulle blockeras) är du ansvarig för att identifiera de uppgifter som behövs undertecknare och begära en ändring via adminportalen.

**Microsoft Hanterade skrivbordsansvar:**

- Microsoft Managed Desktop underhåller basprincipen som aktiverar centrala Microsoft-produkter som M365 Apps, Windows, Teams, OneDrive och så vidare.
- Microsoft Managed Desktop infogar dina betrodda undertecknare och distribuerar den uppdaterade principen till dina enheter.


## <a name="managing-trust-in-applications"></a>Hantera förtroende för program

Microsoft Managed Desktop ger en basprincip som litar på kärnkomponenterna i Microsoft-teknik. Du *lägger* sedan till förtroende för dina egna program och skript genom att informera Microsoft Managed Desktop vilken av dem du redan litar på.

### <a name="base-policy"></a>Baspolicy

Microsoft Managed Desktop skapar och underhåller i samarbete med Microsofts cybersäkerhetsexperter en standardprincip som gör att de flesta appar som distribueras via Microsoft Intune kan blockeras samtidigt som farliga aktiviteter som kodkompilering eller körning av ej betrodda filer blockeras.

Grundprincipen har följande metod för att begränsa programkörning:

- Filer som körs av administratörer tillåts att köras.
- Filer på platser som *inte* finns i användardokumentade kataloger tillåts att köras.
- Filer signeras av en [betrodd undertecknare](#signer-requests).
- De flesta filer som signeras av Microsoft kommer att köras, men vissa är blockerade för att förhindra högriskåtgärder som kodkompilering.


Om en annan användare än en administratör kunde ha lagt till en app eller ett skript på en enhet (det vill säga den finns i en katalog som kan skrivas av användaren) tillåter vi inte att den körs om den inte redan har tillåtits specifikt av en administratör. Om en användare luras att försöka installera skadlig kod, om ett säkerhetsproblem i en app användaren kör försöker installera skadlig kod, eller om en användare avsiktligt försöker köra en obehörig app eller skript, kommer vår policy att stoppa körningen.

### <a name="signer-requests"></a>Begäran om undertecknare

Du informerar oss om vilka appar som tillhandahålls av programvaruleverantörer som du litar på genom att lämna in en *undertecknarbegäran.* På så sätt lägger vi till att lita på information i principen för grundläggande programkontroll och tillåter all programvara som signerats med utgivarens certifikat att köras på dina enheter.

## <a name="audit-and-enforced-policies"></a>Gransknings- och verkställda principer

Microsoft Managed Desktop använder två Microsoft Intune-principer för att tillhandahålla appkontroll:

### <a name="audit-policy"></a>Revisionspolicy
Den här principen skapar loggar för att registrera om en app eller ett skript skulle blockeras av principen Tvingande. Granskningsprinciper tillämpar inte appkontrollregler och är avsedda för testning för att identifiera om ett program kräver ett undantag från utgivaren. Den loggar varningar (8003 eller 8006 händelser) i Loggboken i stället för att blockera körningen eller installationen av angivna appar eller skript.

### <a name="enforced-policy"></a>Tvingande policy
Den här principen blockerar ej betrodda appar och skript från att köras och skapar loggar när en app eller ett skript blockeras. Tvingande principer hindrar standardanvändare från att köra appar eller skript som lagras i användarskrivna kataloger.

Enheter i gruppen Test har en granskningsprincip tillämpad så att du kan använda dem för att verifiera om några program orsakar problem. Alla andra grupper (Första, Fasta och Breda) använder en tvingande princip, så att slutanvändare i dessa grupper inte kan köra ej betrodda appar eller skript.







