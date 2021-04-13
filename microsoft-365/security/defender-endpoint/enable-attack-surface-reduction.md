---
title: Aktivera regler för minskning av attackytan
description: Aktivera ASR-regler (attack surface reduction) för att skydda dina enheter från attacker som använder makron, skript och vanliga lägre tekniker.
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, aktivera, aktivera
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689173"
---
# <a name="enable-attack-surface-reduction-rules"></a>Aktivera regler för minskning av attackytan

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Minskningsregler för attackytor](attack-surface-reduction.md) (ASR-regler) hjälper till att förhindra åtgärder som ofta används för missbruk av skadlig programvara för att avslöja enheter och nätverk. Du kan ange ASR-regler för enheter med någon av följande versioner och versioner av Windows:
- Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Varje ASR-regel innehåller en av fyra inställningar:

- **Inte konfigurerad:** Inaktivera ASR-regeln
- **Block:** Aktivera ASR-regeln
- **Granskning:** Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras
- **Varna**: Aktivera ASR-regeln men alow slutanvändaren att kringgå blocket

> [!IMPORTANT]
> För närvarande stöds inte varningsläge för tre ASR-regler när du konfigurerar ASR-regler i Microsoft Endpoint Manager (MEM). Mer information finns i [Fall där varningsläge inte stöds.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)

Vi rekommenderar starkt att du använder ASR-regler med en Windows E5-licens (eller liknande licens-SKU) för att dra nytta av de avancerade funktionerna för övervakning och rapportering i [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för slutpunkt (Defender för slutpunkt). Men för andra licenser som Windows Professional eller E3 som inte har tillgång till avancerade funktioner för övervakning och rapportering kan du utveckla dina egna övervaknings- och rapporteringsverktyg ovanpå händelser som genereras vid varje slutpunkt när ASR-regler utlöses (t.ex. vidarebefordran av händelse).

> [!TIP]
> Mer information om Windows-licensiering finns i [Windows 10-licensiering](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) och volymlicensieringsguiden [för Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

Du kan aktivera minskningsregler för attackytan med någon av följande metoder:

- [Microsoft Intune](#intune)
- [Hantering av mobila enheter (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Grupprincip](#group-policy)
- [PowerShell](#powershell)

Hantering på företagsnivå, till exempel Intune eller Microsoft Endpoint Manager, rekommenderas. Hantering på företagsnivå skriver över eventuella grupprincipinställningar eller PowerShell-inställningar som är i konflikt vid start.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Undanta filer och mappar från ASR-regler

Du kan utesluta filer och mappar från att utvärderas av de flesta minskningsregler för attackytor. Det innebär att även om en ASR-regel bestämmer att filen eller mappen innehåller skadligt beteende blockerar den inte filen från att köras. Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter.

Du kan även utesluta ASR-regler från utlösare baserat på certifikat och filshashar genom att tillåta angiven Defender för Slutpunktsfil och certifikatindikatorer. (Se [Hantera indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> Att utesluta filer eller mappar kan allvarligt minska skyddet som ges av ASR-regler. Undantagna filer tillåts köras och ingen rapport eller händelse registreras.
> Om ASR-reglerna identifierar filer som du inte anser ska identifieras bör du först använda granskningsläge [för att testa regeln.](evaluate-attack-surface-reduction.md)


Du kan ange enskilda filer eller mappar (med hjälp av mappsökvägar eller fullständigt kvalificerade resursnamn), men du kan inte ange vilka regler undantagen ska gälla för. Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas. Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.

ASR-regler stöder miljövariabler och jokertecken. Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Följande procedurer för att aktivera ASR-regler innehåller instruktioner för hur du utesluter filer och mappar.

## <a name="intune"></a>Intune

1. Välj **Profiler för**  >  **enhetskonfiguration**. Välj en befintlig profil för slutpunktsskydd eller skapa en ny. Om du vill skapa en ny väljer du **Skapa profil och** anger information om den här profilen. För **Profiltyp** väljer du **Slutpunktsskydd**. Om du har valt en befintlig profil väljer du **Egenskaper** och sedan **Inställningar**.

2. I fönstret **Slutpunktsskydd** väljer du **Windows Defender Exploit Guard och** sedan Attack Surface **Reduction**. Välj önskad inställning för varje ASR-regel.

3. Ange **enskilda filer och mappar** under Undantag för minskning av attackytan. Du kan också välja **Importera om du** vill importera en CSV-fil som innehåller filer och mappar som ska undantas från ASR-regler. Varje rad i CSV-filen ska vara formaterad på följande sätt:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Välj **OK** i de tre konfigurationsrutorna. Välj sedan **Skapa** om du skapar en ny slutpunktsskyddsfil eller **Spara** om du redigerar en befintlig.

## <a name="mdm"></a>MDM

Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) för att individuellt aktivera och ställa in läget för varje regel.

Följande är ett exempel för referens där [GUID-värden för ASR-regler används.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

Värdena som du aktiverar (blockera), inaktiverar, varnar eller aktiverar i granskningsläge är:

- 0: Inaktivera (Inaktivera ASR-regeln)
- 1: Blockera (aktivera ASR-regeln)
- 2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)
- 6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)

Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.

Exempel:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Se till att ange OMA-URI-värden utan blanksteg.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Slutpunktsskydd för**  >  **efterlevnad** Windows Defender  >  **Exploit Guard**.

2. Välj **Home**  >  **Create Exploit Guard-policy**.

3. Ange ett namn och en beskrivning, välj **Attack Surface Reduction** och välj **Nästa**.

4. Välj vilka regler som ska blockera eller granska åtgärder och välj **Nästa.**

5. Granska inställningarna och välj **Nästa för** att skapa principen.

6. När principen har skapats stänger **du**.

## <a name="group-policy"></a>Grupprincip

> [!WARNING]
> Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller någon annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella grupprincipinställningar som står i konflikt vid start.

1. Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**

2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Microsoft Defender  >  **Sårbarhetsskydd-** minskning av  >  **attackytan**.

4. Välj **Konfigurera minskningsregler för attackytan** och välj **Aktiverad**. Sedan kan du ange enskilda tillstånd för varje regel i alternativavsnittet.

   Välj **Visa...** och ange regel-ID i **kolumnen Värdenamn** och ditt valda tillstånd **i kolumnen Värde** enligt följande:

   - 0: Inaktivera (Inaktivera ASR-regeln)
   - 1: Blockera (aktivera ASR-regeln)
   - 2: Granska (Utvärdera hur ASR-regeln skulle påverka organisationen om den skulle aktiveras)
   - 6: Varna (Aktivera ASR-regeln men tillåta slutanvändaren att kringgå blocket)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-regler i grupprincip":::

5. Om du vill utesluta filer och  mappar från ASR-regler markerar du inställningen Exkludera filer och sökvägar från reglerna för att minska attackytan och ställer in alternativet **Aktiverad.** Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.** Ange **0** i **värdekolumnen** för varje objekt.

> [!WARNING]
> Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Om du hanterar dina datorer och enheter med Intune, Konfigurationshanteraren eller en annan hanteringsplattform på företagsnivå skriver hanteringsprogramvaran över eventuella motstridande PowerShell-inställningar vid start. Om du vill låta användare definiera värdet med hjälp av PowerShell använder du alternativet "Användardefinierad" för regeln på hanteringsplattformen.

1. Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör.**

2. Skriv in följande cmdlet:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Om du vill aktivera ASR-regler i granskningsläge använder du följande cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Om du vill aktivera ASR-regler i varningsläge använder du följande cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    Om du vill inaktivera ASR-regler använder du följande cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > Du måste ange en delstat individuellt för varje regel, men du kan kombinera regler och tillstånd i en kommaavgränsad lista.
    >
    > I följande exempel aktiveras de två första reglerna, den tredje regeln inaktiveras och den fjärde regeln aktiveras i granskningsläge:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    Du kan också använda `Add-MpPreference` PowerShell-verbet för att lägga till nya regler i den befintliga listan.

    > [!WARNING]
    > `Set-MpPreference` kommer alltid att skriva över den befintliga uppsättningen regler. Om du vill lägga till i den befintliga uppsättningen använder du `Add-MpPreference` istället.
    > Du kan få en lista över regler och deras aktuella status med hjälp av `Get-MpPreference` .

3. Om du vill utesluta filer och mappar från ASR-regler använder du följande cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler filer och mappar i listan.

    > [!IMPORTANT]
    > Används `Add-MpPreference` för att lägga till eller lägga till appar i listan. Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

## <a name="related-articles"></a>Relaterade artiklar

- [Minska attackytor med minskningsregler för attackytan](attack-surface-reduction.md)

- [Utvärdera minskning av attackytan](evaluate-attack-surface-reduction.md)

- [Vanliga frågor och svar för minskning av attackytan](attack-surface-reduction.md)
