---
title: Välkomstprogrammet med Autopilot och sidan Registreringsstatus
description: Hur du distribuerar ESP-funktioner, vilka inställningar som används och konfigurations ändringar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7337dd28f7940256d1753cd4c0b6309406fab2d1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305276"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Välkomstprogrammet med Autopilot och sidan Registreringsstatus

Microsoft Managed Desktop använder både [Windows autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) och Microsoft Intunes [registrerings status sida (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) för att tillhandahålla den bästa möjliga upplevelsen för förstagångskörningen för användarna.

Sidan registrerings status är för närvarande i offentlig för hands version.

## <a name="initial-deployment"></a>Inledande distribution

För att tillhandahålla ESP-gränssnittet måste du registrera enheter på Microsoft Managed Desktop-tjänsten. Mer information om registrering finns i [registrera nya enheter själv](../get-started/register-devices-self.md) eller [steg för att registrera enheter](../get-started/register-devices-partner.md).

När dina enheter har registrerats med tjänsten kan du aktivera ESP för dina Microsoft-hanterade Skriv bords enheter genom att arkivera ett support ärende via [administrations portalen](https://portal.azure.com/). Vi distribuerar först ESP-konfigurationen till test gruppen när du arkiverar biljetten. Den distribueras till de andra kommande distributions grupperna (första, snabba och breda) varje dygn. Om du vill pausa distributionen kan du spara en fil i en annan biljett.

## <a name="autopilot-profile-settings"></a>Profil inställningar för autopilot

Microsoft Managed Desktop använder de här inställningarna i den autopilot-profil som används för användarnas enheter:


|Inställning  |Value  |
|---------|---------|
|Distributions läge |  Användare drivna       |
|Anslut till Azure AD som     |  Azure AD-ansluten       |
|Språk (region)     | Standard operativ system        |
|Konfigurera tangent bord automatiskt     | Nej        |
|Licens villkor för program vara från Microsoft     |  Gömma       |
|Sekretess inställningar     | Gömma        |
|Dölj alternativ för att ändra konto     | Så        |
|Typ av användar konto     |  Standard       |
|Tillåt vit Glove OOBE     |  Ja       |
|Använda mallen enhets namn     | Ja        |
|Ange ett namn     | MMD-% SLUMP: 11%        |

> [!NOTE]
> När "vit Glove"-etablering är aktive rad för kunder med ESP aktiverat stöds den för närvarande inte i Microsoft Managed Desktop.

## <a name="enrollment-status-page-settings"></a>Inställningar för status sidan för anmälan

Microsoft Managed Desktop använder de här inställningarna för registrerings status sidans funktion:


|Inställning  |Value  |
|---------|---------|
|Visa konfigurations förlopp för appar och profiler     | Ja        |
|Visa ett fel när installationen tar längre tid än angivet antal minuter     |  60       |
|Visa anpassat meddelande när tids gräns felet inträffar     |  Ja       |
|Fel meddelande     | Ja, det tar lite längre tid att konfigurera enheten än förväntat. Klicka nedan för att komma igång så slutförs konfigurationen i bakgrunden        |
|Tillåt att användare samlar in loggar om installations fel     |  Ja       |
|Visa endast sidan för enheter som tillhandahålls av OOBE (out-of-Box Experience)     | Ja        |
|Blockera enhets användning tills alla appar och profiler är installerade     |  Ja       |
|Tillåt att användare återställer enheter om installations fel inträffar     |  Ja       |
|Tillåt användare att använda enhet om installations fel uppstår     |  Ja       |
|Blockera enhets användning tills dessa program är installerade om de är tilldelade till användaren/enheten     |  Modern arbets plats – tids korrigering       |



Status sidan för anmälan visas i tre faser. Mer information finns i [spårnings informationen för registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

Det här händer så här:

1. Autopilot-upplevelsen startas och användaren anger deras autentiseringsuppgifter.
2. Enheten öppnar sidan registrerings status och fortsätter genom enhets förberedelse och enheter för installation. Det tredje steget (konto inställningar) är *för närvarande inte aktiverat* i konfigurationen för Microsoft Managed Desktop eftersom användare ESP är inaktiverat. Enheten startas om.
3. När du har startat om enheten öppnas inloggnings sidan för Windows med **andra användare**.
4. Användarna anger deras autentiseringsuppgifter igen och skriv bordet öppnas.

> [!NOTE]
> Win32-appar distribueras bara under ESP om Windows 10-versionen är 1903 eller senare.

![Start sida med autopilot-inställningar som visar "enhets förberedelse" och "enhets inställningar".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Vit Glove-etablering

Microsoft Managed Desktop stöder för närvarande inte "vit Glove" för Windows autopilot.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Ändra inställningarna för statusen autopilot och status sidan för anmälan

Om installations programmet som hanteras av Microsoft Managed Desktop inte exakt motsvarar dina behov kan du arkivera ett support ärende via [administrations portalen](https://portal.azure.com/). Här är några exempel på de typer av konfigurationer som du kan behöva:

### <a name="autopilot-settings-change"></a>Ändring av inställningar för autopilot

Du kanske vill begära en annan mall för enhets namn. Du kan inte ändra distributions läge, ansluta till Azure som, sekretess inställningar eller användar konto typen.

### <a name="enrollment-status-page-settings-change"></a>Inställningar för registrerings status sidan ändras

- Längre antal minuter för inställningen "Visa ett fel när installationen tar längre än angivet antal minuter".
- Det fel meddelande som visas
- Lägga till eller ta bort program i "blockera enhets användning tills dessa program är installerade om de har tilldelats inställningen användare/enhet".

## <a name="required-applications"></a>Program som krävs

- Du måste inrikta dig på program i den moderna arbets plats *enhets grupperna* test, första, fast och breda. Program måste installeras i "system kontexten". Se till att slutföra testning med ESP i test gruppen innan du tilldelar dem till alla grupper.
- Inga program bör kräva att enheten startas om. Vi rekommenderar att program är inställt på "gör ingenting" när du skapar programpaketet om de kräver en omstart.
- Begränsa nödvändiga program till enbart de grundläggande program som en användare behöver omedelbart när de loggar in på enheten.
- Behåll den totala storleken på alla tillämpningar tillsammans under 1 GB för att undvika tids gränser under program installations fasen.
- Helst bör appar inte ha några beroenden. Om du har appar som *måste* ha samband kan du se till att du konfigurerar, testar och validerar dem som en del av din ESP-utvärdering.
- Inga program som kräver "användar kontexten" (till exempel team) kan ingå i den offentliga för hands versionen av ESP.
