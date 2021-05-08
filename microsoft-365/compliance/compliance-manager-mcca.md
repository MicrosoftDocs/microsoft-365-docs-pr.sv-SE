---
title: Microsoft Compliance Configuration Analyzer för Efterlevnadshanteraren
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Förstå hur du använder Microsoft Compliance Configuration Analyzer för att snabbt komma igång med Microsoft Compliance Manager.
ms.openlocfilehash: 5d74d9980daf7f6ff7f013578cb11be83d18948e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244642"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Microsoft Compliance Configuration Analyzer för Efterlevnadshanteraren (förhandsversion)

**I den här artikeln:** Lär dig hur du installerar och kör verktyget Microsoft Compliance Configure Analyzer för att snabbt komma igång med Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Översikt över Microsoft Compliance Configuration Analyzer (MCCA) (förhandsversion)

Microsoft Compliance Configuration Analyzer (MCCA) är ett förhandsversionsverktyg som kan hjälpa dig att komma igång med [Microsoft Compliance Manager.](compliance-manager.md) MCCA är ett PowerShell-baserat verktyg som hämtar organisationens aktuella konfigurationer och verifierar dem Microsoft 365 rekommenderade metodtips. Dessa metodtips baseras på en uppsättning kontroller som omfattar viktiga bestämmelser och standarder för dataskydd och datastyrning.

Med MCCA kan du snabbt se vilka förbättringsåtgärder i Efterlevnadshanteraren som gäller för din Microsoft 365 miljö. Varje åtgärd som identifieras av MCCA ger dig rekommendationer om implementering, med direktlänkar till Efterlevnadshanteraren och den tillämpliga lösningen för att börja vidta korrigerande åtgärder.

Ytterligare en resurs för att förstå MCCA är genom att gå till [README-anvisningarna på GitHub](https://github.com/OfficeDev/MCCA#overview). På den här sidan finns detaljerad information om krav och fullständiga installationsanvisningar. Du behöver inte ett konto GitHub komma åt den här sidan.

**Tillgänglighet:** MCCA är tillgängligt för alla organisationer med Office 365- och Microsoft 365-licenser och kunder med amerikanska Government Community (GCC) Måttliga, GCC High och Department of Defense (DoD).

## <a name="install-mcca-and-run-a-report"></a>Installera MCCA och kör en rapport

Du kan installera MCCA-verktyget med Windows PowerShell. När du har laddat ned och installerat verktyget behöver du inte upprepa dessa steg för att kunna köra rapporter. Varje gång du öppnar MCCA uppmanas du att logga in och en ny, uppdaterad rapport skapas.

#### <a name="step-1-install-windows-powershell"></a>Steg 1: Installera Windows PowerShell
För att börja behöver du den Exchange Online PowerShell-modul (v2.0.3 eller senare) som finns tillgänglig i PowerShell-galleriet. [Få installationsanvisningar.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Steg 2: Installera MCCA

Installera MCCA genom att börja med att använda PowerShell i administratörsläge. Följ stegen nedan:

1. Välj Windows **Start.**
2. Skriv **PowerShell**, högerklicka på **Windows PowerShell** välj sedan Kör som **administratör.**
1. I kommandotolken skriver du:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Steg 3: Kör en rapport

När du har installerat MCCA kan du köra MCCA och generera en rapport. Så här kör du en rapport:

1. Öppna PowerShell
2. Kör cmdleten:

    ```powershell
    Get-MCCAReport
    ```

   Om du är en GCC High-kund måste du ange en ytterligare indataparameter för att köra rapporten:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. När MCCA körs gör den en första versionskontroll och begär autentiseringsuppgifter. I meddelandet Ange användarnamn loggar du in med e-postadressen för Microsoft 365 konto (visa rollerna[som är kvalificerade för att skapa rapporter).](#role-based-reporting) Ange sedan lösenordet när du uppmanas att ange lösenordet.

Det tar sedan ungefär 2–5 minuter att generera rapporten. När det är klart öppnas ett webbläsarfönster med HTML-rapporten. Varje gång du kör verktyget begär den dina autentiseringsuppgifter och skapar en ny rapport. Den här rapporten lagras lokalt i följande katalog:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Du kan komma åt tidigare skapade rapporter från den här katalogen.

## <a name="understanding-your-report"></a>Förstå rapporten

I rapporten återges data baserat på datum och tid då de skapades. I det övre avsnittet finns information om när den skapades, organisationens namn och klientorganisations-ID.

#### <a name="geolocation-based-reporting"></a>Geolokaliseringsbaserad rapportering

Avsnittet **Anteckning** visar att rapporten är anpassad baserat på klientorganisationens geografiska position. Rekommendationer som visas i verktyget är specifika för ditt land eller din region.

Ditt geolokaliseringsval används för att bedöma typer av känslig information (SITs) som är relevanta för den geolokaliseringen och generera en rapport som passar ditt land eller din region. Välj geolokaliseringar baserat på data som finns i klientorganisationen.

Om du vill ändra rapportens platsinformation måste du ange en geolokaliseringsparameter (-Geo). Du kan välja en eller flera geolokaliseringar som gäller för din klientorganisation.

Följ de här anvisningarna om du vill köra en rapport baserat på en viss plats:

1. Öppna PowerShell
2. Om du vill ange en viss region kör du en cmdlet med siffrorna i tabellen nedan som motsvarar landet eller regionen. Ange flera tal genom att avgränsa dem med kommatecken. Cmdleten nedan kör till exempel en anpassad rapport för Asia-Pacific och Japan:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Inmatning |  Land eller region | 
  | :------------- | :------------: |
  | 1 | Asia-Pacific |
  | 2 | Australien |
  | 3 | Kanada |
  | 4 | Europa (undantaget Frankrike) / Mellanöstern/Afrika |
  | 5 | Frankrike |
  | 6 | Indien |
  | 7 | Japan  |
  | 8 | Korea  |
  | 9 | Nordamerika (exklusive Kanada) |
  | 10 | Sydamerika |
  | 11 | Sydafrika |
  | 12 | Schweiz |
  | 13 | Förenade Arabemiraten |
  | 14 | Storbritannien |


 > [!NOTE]
> Rapporten kommer alltid att innehålla internationella typer av känslig information som stöds av MCCA, till exempel SWIFT-kod, kreditkortsnummer osv.

#### <a name="role-based-reporting"></a>Rollbaserad rapportering

Rapporten anpassas också efter din roll.

I tabellen nedan visas vilka roller som har åtkomst till vilka avsnitt i rapporten. Andra roller i organisationen (som inte visas i tabellen nedan) kanske inte kan köra verktyget, eller så kan de köra verktyget och har begränsad åtkomst till information i den slutliga rapporten.

![MCCA – roller](../media/compliance-manager-mcca-roles.png "MCCA-roller")

Undantag:
1. Användarna kan inte generera rapporten om IP förutom avsnittet "Använd IRM för Exchange Online".
2. Användarna kan generera rapporten om IP förutom avsnittet "Använd IRM för Exchange Online".
3. Användarna kommer att kunna generera en rapport om IP förutom avsnittet "Aktivera kommunikationsefterlevnad i O365".
4. Användarna kan inte generera rapporter för IP förutom avsnittet "Aktivera granskning i Office 365".
5. Användarna kan generera rapporten för IP förutom avsnittet "Aktivera granskning i Office 365".

#### <a name="solutions-summary-section"></a>Avsnittet Sammanfattning av lösningar

I **avsnittet Sammanfattning av** lösningar i rapporten finns en översikt över de förbättringsåtgärder som din organisation kan vidta i Efterlevnadshanteraren för att förbättra kompatibiliteten.

![MCCA – sammanfattning av lösningar](../media/compliance-manager-mcca-solutions.png "Sammanfattningsskärm för MCCA-lösningar")

MCCA utvärderar dina aktuella konfigurationer mot rekommenderade förbättringsåtgärder i Efterlevnadshanteraren. Eventuella förbättringsåtgärder som identifieras av MCCA-verktyget som behöver uppmärksammas visas i det här avsnittet.

Bredvid varje Microsoft-lösning finns färgkodade rutor som anger antalet objekt som motsvarar förbättringsåtgärder i Efterlevnadshanteraren. Åtgärderna delas in i tre statustillstånd:

- **OK:** de åtgärder som uppfyller rekommenderade villkor och som inte behöver uppmärksammas just nu
- **Förbättring:** åtgärder som behöver uppmärksammas
- **Rekommendation:** åtgärder som inte behöver uppmärksammas, men som vi rekommenderar metodtips för
 
Markera en ruta för att visa förbättringar och rekommendationer.

**Objekt med förbättringsstatus**

Välj listrutan bredvid etiketten **Förbättring** till höger om förbättringsåtgärden. Du ser en snabbsammanfattning och information om dina aktuella inställningar och rekommenderade förbättringsåtgärder. Sammanfattningen innehåller direktlänkar till Efterlevnadshanteraren, den tillämpliga lösningen i Microsoft 365 kompatibilitetscenter och relevant dokumentation.

Om du klickar på länken Efterlevnadshanteraren visas en filtrerad vy över alla förbättringsåtgärder i lösningen som du ännu inte har implementerat. Därifrån kan du se antalet punkter du kan uppnå för att öka ditt efterlevnadsresultat [,](compliance-score-calculation.md)och de utvärderingar som de gäller för, samt tillämpliga bestämmelser och certifieringar.

För DLP finns knappen **Åtgärdsskript** som ger dig ett förgenererat PowerShell-skript baserat på vad som rekommenderas. Du kan kopiera och klistra in den direkt i PowerShell-konsolen. En DLP-princip skapas i testläge

**Objekt med rekommendationsstatus**

Välj listrutan bredvid etiketten **Rekommendation** till höger om förbättringsåtgärden. En sammanfattning av organisationens aktuella användningsmiljö Microsoft 365 förbättringsåtgärden visas tillsammans med rekommenderade metodtips.

## <a name="resources"></a>Resurser

Mer detaljerad information om att installera, konfigurera och använda MCCA finns i [README-anvisningarna](https://github.com/OfficeDev/MCCA#overview) för GitHub (inget GitHub konto krävs).

Mer information om Windows PowerShell finns i Så [här använder du PowerShell-dokumentationen.](/powershell/scripting/how-to-use-docs?view=powershell-7) Se även [Windows PowerShell.](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)
