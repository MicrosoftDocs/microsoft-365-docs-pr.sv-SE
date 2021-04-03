---
title: Anpassa regler för minskning av attackytan
description: Individuellt ange regler i gransknings-, block- eller inaktiverade lägen och lägga till filer och mappar som ska undantas från reglerna för att minska attackytan
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, anpassa, konfigurera, utesluta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570357"
---
# <a name="customize-attack-surface-reduction-rules"></a>Anpassa regler för minskning av attackytan

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

[Minskningsregler för attackytan](enable-attack-surface-reduction.md) hjälper till att förhindra programvarubeteenden som ofta missbrukeras för att avslöja din enhet eller ditt nätverk. En attackerare kan till exempel försöka köra ett osignerat skript från en USB-enhet eller ha ett makro i ett Office-dokument som ringer samtal direkt till Win32 API. Minskning av attackytan kan begränsa dessa typer av riskfyllda beteenden och förbättra organisationens grundbeteende.

Lär dig hur du kan [](#exclude-files-and-folders) anpassa regler för att minska attackytan genom att utesluta filer och mappar eller lägga till anpassad [text](#customize-the-notification) i meddelandemeddelandet som visas på en användares dator.

Du kan ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:
- Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows Server, [version 1803 (Halvårskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) eller senare
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Du kan använda grupprincip-, PowerShell- och MDM-konfigurationstjänstleverantörer (Mobile Device Management) för att konfigurera de här inställningarna.

## <a name="exclude-files-and-folders"></a>Undanta filer och mappar

Du kan välja att undanta filer och mappar från att utvärderas med hjälp av minskningsregler för attackytan. När filen har uteslutits blockeras den inte från att köras även om en minskningsregel för attackytan identifierar att filen innehåller skadligt beteende.

> [!WARNING]
> Det kan potentiellt tillåta att osäkra filer körs och smittar dina enheter. Att utesluta filer eller mappar kan allvarligt minska skyddet som tillhandahålls av minskningsregler för attackytan. Filer som skulle ha blockerats av en regel tillåts köras och ingen rapport eller händelse registreras.

Ett undantag gäller för alla regler som tillåter undantag. Du kan ange en enskild fil, mappsökväg eller det fullständigt kvalificerade domännamnet för en resurs. Du kan dock inte begränsa ett undantag till en viss regel.

Ett undantag tillämpas endast när det undantagna programmet eller tjänsten startas. Om du till exempel lägger till ett undantag för en uppdateringstjänst som redan körs fortsätter uppdateringstjänsten att utlösa händelser tills tjänsten stoppas och startas om.

Minskning av attackytan stöder miljövariabler och jokertecken. Information om hur du använder jokertecken finns i använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Om du stöter på problem med regler för att identifiera filer som du tror inte ska identifieras kan du använda [granskningsläge för att testa regeln.](evaluate-attack-surface-reduction.md)

Regelbeskrivning | GUID
-|-|-
Blockera alla Office-program från att skapa underordnade processer | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
Blockera körning av potentiellt oönskade skript | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Blockera Win32 API-anrop från Office-makro | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Blockera Office-program från att skapa körbart innehåll | 3B576869-A4EC-4529-8536-B80A7769E899
Blockera Office-program från att mata in kod i andra processer | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
Blockera JavaScript eller VBScript från att starta hämtat körbart innehåll | D3E037E1-3EB8-44C8-A917-57927947596D
Blockera körbart innehåll från e-postklient och webbaserad e-post | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Blockera körbara filer från att köras såvida de inte uppfyller villkoren för en vän, ålder eller ett betrott listvillkor | 01443614-cd74-433a-b99e-2ecdc07bfc25
Använd avancerat skydd mot utpressningstrojaner | c1db55ab-c21a-4637-bb3f-a12568109d35
Blockera att autentiseringsuppgifter stjäls från Windows lokala säkerhetsutfärdares undersystem (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Blockera processskapanden som kommer från PSExec- och WMI-kommandon | d1e49aac-8f56-4280-b9ba-993a6d77406c
Blockera icke betrodda och osignerade processer som körs från USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Blockera Office-kommunikationsprogram från att skapa underordnade processer | 26190899-1602-49e8-8b27-eb1d0a1ce869
Blockera Adobe Reader från att skapa underordnade processer | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Blockera beständighet via WMI-händelseprenumeration | e6db77e5-3df2-4cf1-b95a-636979351e5b

Mer information [om varje regel](attack-surface-reduction.md) finns i avsnittet för att minska attackytan.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Använda grupprinciper för att utesluta filer och mappar

1. Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](https://technet.microsoft.com/library/cc731212.aspx)högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender  >  **Sårbarhetsskydd-minskning** av  >  **attackytan**.

4. Dubbelklicka på inställningen Exkludera **filer och sökvägar från minskningsregler för attackytan** och ange alternativet **Aktiverad.** Välj **Visa** och ange varje fil eller mapp i **kolumnen Värdenamn.** Ange **0** i **värdekolumnen** för varje objekt.

> [!WARNING]
> Använd inte citattecken eftersom de inte stöds för antingen **värdenamnskolumnen** eller **värdekolumnen.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>Använda PowerShell för att utesluta filer och mappar

1. Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**
2. Ange följande cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Fortsätt att använda `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` för att lägga till fler mappar i listan.

> [!IMPORTANT]
> Används `Add-MpPreference` för att lägga till eller lägga till appar i listan. Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Använda MDM-csP:er för att utesluta filer och mappar

Använd [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions-konfigurationstjänsten](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) för att lägga till undantag.

## <a name="customize-the-notification"></a>Anpassa meddelandet

Du kan anpassa meddelandet för när en regel utlöses och spärra en app eller fil. Se [artikeln om Windows-säkerhet.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Relaterade ämnen

* [Minska attackytor med minskningsregler för attackytan](attack-surface-reduction.md)
* [Aktivera regler för minskning av attackytan](enable-attack-surface-reduction.md)
* [Utvärdera regler för minskning av attackytan](evaluate-attack-surface-reduction.md)
* [Vanliga frågor och svar för minskning av attackytan](attack-surface-reduction.md)
