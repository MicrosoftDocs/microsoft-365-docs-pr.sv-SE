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
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289133"
---
# <a name="app-control"></a>Appkontroll

App Control är en valfri säkerhets metod på Microsoft Managed Desktop som begränsar körning av kod på klient enheter. Den här kontrollen minskar risken för skadliga program eller skadliga skript genom att kräva att endast kod som är signerad av en kund godkänd lista över utgivare kan köras. Det finns många säkerhets fördelarna med den här kontrollen, men det är främst att skydda data och identitet från klientbaserade sårbarheter.

Med Microsoft Managed Station ära datorer blir det enklare att hantera program kontroll principer genom att skapa en bas policy som möjliggör grundläggande produktivitets scenarier. Du kan utöka förtroendet till ytterligare undertecknare som är specifika för appar och skript i miljön. 


Alla säkerhets tekniker kräver en avvägning mellan användar upplevelse, säkerhet och kostnad. Program kontroll minskar risken för skadliga program i miljön, men det finns konsekvenser för användaren och ytterligare åtgärder för IT-administratören.

**Ytterligare säkerhet:**

Appar eller skript som inte är betrodda av program kontroll principen blockeras från att köras på enheter.

**Dina ytterligare ansvars områden:**

- Du är ansvarig för att testa dina program för att identifiera om de blockeras av program kontroll principen.
- Om ett program är (eller skulle bli) blockerat är du ansvarig för att identifiera de uppgifter som behövs och begära en ändring via administrations portalen.

**Microsoft Managed Desktop ansvars område:**

- Microsoft Managed Desktop har grundläggande policy som gör att du kan använda de grundläggande Microsoft-produkterna som M365-appar, Windows, teams, OneDrive och så vidare.
- Microsoft Managed Desktop infogar betrodda undertecknare och distribuerar den uppdaterade principen på dina enheter.


## <a name="managing-trust-in-applications"></a>Hantera förtroende i program

Microsoft Managed Desktop-granskare en bas policy som är betrodd för huvud komponenterna i Microsoft Technologies. Sedan kan du *lägga till* förtroende för dina egna program och skript genom att informerar Microsoft Managed Desktop, vilket du redan har förtroende för.

### <a name="base-policy"></a>Bas policy

Microsoft Managed Desktop, i samarbete med Microsoft Cybersecurity experter, skapar och hanterar en standard policy som gör att de flesta program som distribueras via Microsoft Intune blockerar farliga aktiviteter, till exempel kodning eller körning av obetrodda filer.

Bas policyn har följande metod för att begränsa program körning:

- Filer som körs av administratörer kan köras.
- Filer på platser som *inte* finns i användarnas skrivbara kataloger kommer att tillåtas att köras.
- Filer är signerade av en [betrodd undertecknare](#signer-requests).
- De flesta filer som är signerade med Microsoft körs, men vissa blockeras för att förhindra högrisk åtgärder, till exempel kod kompilering.


Om en annan användare än en administratör har lagt till en app eller ett skript till en enhet (det vill säga att det är i en användardefinierad katalog) tillåter vi inte att den körs såvida den inte redan har tillåtits av en administratör. Om en användare luras att försöka installera skadlig program vara, om ett säkerhets problem i en app som användaren kör försöker installera skadlig program vara, eller om en användare medvetet försöker köra en otillåten app eller skript, kommer vår policy att sluta utföra.

### <a name="signer-requests"></a>Signerings förfrågningar

Du informerar dig om vilka appar som tillhandahålls av program varu leverantörer som du litar på genom att arkivera en *registreringsbegäran*. Genom att göra så lägger vi till den förtroende information i princip policyn för program kontroll och gör att program vara som är signerad med den utgivarens certifikat körs på dina enheter.

## <a name="audit-and-enforced-policies"></a>Gransknings-och genomdrivta principer

Microsoft Managed Desktop använder två Microsoft Intune-principer för att tillhandahålla program kontroll:

### <a name="audit-policy"></a>Gransknings princip
Med den här principen kan du ange om en app eller ett skript ska blockeras av den tvingande principen. Gransknings principer tvingar inte program kontroll regler och är avsedda för testning för att avgöra om ett program kräver ett undantag från utgivaren. Den loggar varningar (8003 eller 8006) i logg boken i stället för att blockera körning eller installation av angivna appar eller skript.

### <a name="enforced-policy"></a>Tvingande princip
Denna princip blockerar icke betrodda appar och skript att köra och skapar loggar när en app eller ett skript blockeras. Tillämpade principer hindrar vanliga användare från att köra appar eller skript som lagras i användarnas skrivbara kataloger.

Enheter i test gruppen har en gransknings princip som tillämpas så att du kan använda dem för att kontrol lera om några program orsakar problem. Alla andra grupper (första, snabba och breda) använder en tvingande princip, så att användare i dessa grupper inte kan köra icke betrodda appar eller skript.







