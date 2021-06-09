---
title: Vad är nytt i Microsoft Defender för slutpunkt på Mac
description: Läs mer om de viktigaste ändringarna för tidigare versioner av Microsoft Defender för Endpoint på Mac.
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, mac, installation, macos, nyheter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6348d688103c51176fbed36c923a660c77a2258d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842788"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Vad är nytt i Microsoft Defender för slutpunkt på Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler. Om du är en befintlig kund som uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som listas på [den här sidan.](mac-sysext-policies.md)

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- Från och med den här versionen kommer hot som upptäckts under sökning på begäran av antivirus som utlöses via kommandoradsklienten att åtgärdas automatiskt. Hot som upptäckts vid genomsökningar som utlösts via användargränssnittet kräver fortfarande manuell åtgärd.
- `mdatp diagnostic real-time-protection-statistics` stöder nu ytterligare två växlar:
  - `--sort`: Sorterar resultatet fallande efter totalt antal genomsökta filer
  - `--top N`: visar de översta N-resultaten (fungerar bara om `--sort` anges också)
- Prestandaförbättringar (särskilt för när IST. används) & felkorrigeringar

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Åtgärd för att hantera förfallotiden för Apple-certifikat för macOS Catalina och tidigare. Den här korrigeringen återställer & funktioner för sårbarhetshantering (TVM).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender för Slutpunkt på macOS är nu tillgänglig i förhandsversion för kunder inom myndigheter i USA. Mer information finns i [Microsoft Defender för slutpunkt för kunder inom amerikanska myndigheter.](gov.md)
- Prestandaförbättringar (särskilt vid den situation då appen XCode Bugg används) som & programkorrigeringar.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Lade till ett nytt alternativ i kommandoradsverktyget för att visa information om den senaste genomsökningen på begäran. Om du vill visa information om den senaste genomsökningen på begäran kör du `mdatp health --details antivirus`
- Prestandaförbättringar & felkorrigeringar

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Prestandaförbättringar & felkorrigeringar

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Prestandaförbättringar & felkorrigeringar

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> Den gamla kommandoradsverktygets syntax är inaktuell i den här versionen. Mer information om den nya syntaxen finns i [Resurser](mac-resources.md#configuring-from-the-command-line).

- Lade till en ny kommandoradsväxel för att inaktivera nätverkstillägget: `mdatp system-extension network-filter disable` . Det här kommandot kan vara användbart för att felsöka nätverksproblem som kan ha att göra med Microsoft Defender för Slutpunkt på Mac
- Prestandaförbättringar & felkorrigeringar

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Felkorrigeringar

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Förbättrad tillförlitlighet för agenten när du kör på macOS 11 Big Sur
- Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )
- Prestandaförbättringar & felkorrigeringar

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Villkor togs bort när Microsoft Defender för Endpoint utlöste ett fel i macOS 11 (Big Sur) som visar sig i en kernel-panik
- Åtgärdat en minnesläcka i Endpoint Security-systemtillägget när det kördes på mac 11 (Big Sur)
- Felkorrigeringar

## <a name="1011072"></a>101.10.72

- Felkorrigeringar

## <a name="1010961"></a>101.09.61

- Lade till en ny hanterad inställning [för att inaktivera alternativet att skicka feedback](mac-preferences.md#show--hide-option-to-send-feedback)
- Statusmenyikonen visar ett felfritt läge när produktinställningarna hanteras. Tidigare visade statusmenyikonen ett varningsmeddelande eller felläge, även om produktinställningarna hanterades av administratören
- Prestandaförbättringar & felkorrigeringar

## <a name="1010950"></a>101.09.50

- Den här produktversionen har validerats på macOS Big Sur 11 beta 9

- Den nya syntaxen `mdatp` för kommandoradsverktyget är nu standard. Mer information om den nya syntaxen finns i [Resurser för Microsoft Defender för Slutpunkt i macOS](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > Syntaxen för det gamla kommandoradsverktyget tas bort från produkten **den 1 januari 2021.**

- Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog
- Prestandaförbättringar & felkorrigeringar

## <a name="1010949"></a>101.09.49

- Förbättringar av användargränssnittet för att skilja på undantag som hanteras av IT-administratören och undantag som definieras av den lokala användaren
- Förbättrad CPU-användning vid genomsökningar på begäran
- Prestandaförbättringar & felkorrigeringar

## <a name="1010723"></a>101.07.23

- Nya fält har lagts till i utdata `mdatp --health` för att kontrollera status för passivt läge och Identifiering och åtgärd på slutpunkt grupp-ID

  > [!NOTE]
  > `mdatp --health` ersätts med `mdatp health` i en framtida produktuppdatering.

- Åtgärdat ett fel där automatisk exempelinskick inte har markerats som hanterat i användargränssnittet
- Nya inställningar för att kontrollera bevarandet av objekt i historiken för antivirussökning har lagts till. Du kan nu [ange antalet dagar för att behålla objekt i genomsökningshistoriken](mac-preferences.md#antivirus-scan-history-retention-in-days) och ange det högsta antalet objekt i [genomsökningshistoriken](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Felkorrigeringar

## <a name="1010663"></a>101.06.63

- Åtgärdat en prestanda regression som introducerades i version `101.05.17` . Regressionen infördes med korrigeringen för att eliminera kernel-panik som en del kunder har observerat vid åtkomst till SMB-resurser. Vi har återställt den här kodändringen och undersöker alternativa sätt att eliminera kernel-panik.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Vi arbetar med en ny och förbättrad syntax `mdatp` för kommandoradsverktyget. Den nya syntaxen är för närvarande standard i uppdateringskanalerna Insider – snabbt och Insider – långsamt. Vi rekommenderar att du använder den nya syntaxen för att använda den här syntaxen.
> 
> Vi fortsätter att stödja den gamla syntaxen parallellt med den nya syntaxen och kommer att ge mer kommunikation om utfasningsplanen för den gamla syntaxen under de kommande månaderna.

- Åtgärdat en kernel-panik som ibland uppstod när man fick åtkomst till SMB-filresurser
- Prestandaförbättringar & felkorrigeringar

## <a name="1010516"></a>101.05.16

- Förbättringar av snabbsökningslogik för att avsevärt minska antalet skannade filer
- Lade [till stöd för Komplettera](mac-resources.md#how-to-enable-autocompletion) automatiskt för kommandoradsverktyget
- Felkorrigeringar

## <a name="1010312"></a>101.03.12

- Prestandaförbättringar & felkorrigeringar

## <a name="1010154"></a>101.01.54

- Förbättringar kring kompatibilitet med Time Machine
- Förbättrade hjälpmedelsfunktioner
- Prestandaförbättringar & felkorrigeringar

## <a name="1010031"></a>101.00.31

- Förbättrad [produktinitiering för Intune-användare](/mem/intune/apps/apps-advanced-threat-protection-macos)
- Undantag [från antivirus har nu stöd för jokertecken](mac-exclusions.md#supported-exclusion-types)
- Lade till möjligheten att utlösa antivirusskanningar från macOS-snabbmenyn. Nu kan du högerklicka på en fil eller en mapp i Finder och välja **Sök med Microsoft Defender för slutpunkt**
- Nedgradering av produkter på plats kommer nu uttryckligen inte att tillåtas av installationsprogrammet. Om du behöver nedgradera måste du först avinstallera den befintliga versionen och konfigurera om enheten
- Andra prestandaförbättringar & felkorrigeringar

## <a name="1009027"></a>100.90.27

- Nu kan du [ange en uppdateringskanal](mac-updates.md#set-the-channel-name) för Microsoft Defender för Slutpunkt i macOS som skiljer sig från den systemomfattande uppdateringskanalen
- Ny produktikon
- Andra förbättringar av användarupplevelsen
- Felkorrigeringar

## <a name="1008692"></a>100.86.92

- Förbättringar kring kompatibilitet med Time Machine
- Åtgärdat ett problem där produkten ibland inte rensade alla filer under `/Library/Application Support/Microsoft/Defender` avinstallationen
- Minskad CPU-användning av produkten när Microsoft-produkter uppdateras via Microsoft AutoUpdate
- Andra prestandaförbättringar & felkorrigeringar

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> För att säkerställa det mest fullständiga skyddet för dina macOS-enheter och i justeringen med Apple kommer den inbyggda säkerhetsuppdateringen av macOS att stoppas för OS-versioner som är äldre än [nuvarande – 2], MDATP för Mac-distribution och uppdateringar stöds inte längre på macOS Sierra [10.12]. MDATP för Mac-uppdateringar och förbättringar levereras till enheter med versionerna Catalina [10.15], Mojave [10.14] och High Sierra [10.13]. 
>
> Om du redan har MDATP för Mac distribuerat till dina Sierra-enheter [10.12] bör du uppgradera till den senaste macOS-versionen för att undvika risken att förlora skydd.

- Prestandaförbättringar & felkorrigeringar

## <a name="1008373"></a>100.83.73

- Fler kontroller för IT-administratörer har [lagts till för hantering av undantag](mac-preferences.md#exclusion-merge-policy), hantering av [hottypsinställningar](mac-preferences.md#threat-type-settings-merge-policy)och [inte tillagd hotåtgärder](mac-preferences.md#disallowed-threat-actions)
- När Fullständig diskåtkomst inte är aktiverat på enheten visas nu en varning i statusmenyn
- Prestandaförbättringar & felkorrigeringar

## <a name="1008260"></a>100.82.60

- Vi har åtgärdat ett problem där produkten inte började följa en definitionsuppdatering.

## <a name="1008042"></a>100.80.42

- Felkorrigeringar

## <a name="1007942"></a>100.79.42

- Åtgärdat ett problem där Microsoft Defender för Slutpunkt på Mac ibland störde Time Machine
- Lade till en ny växel till kommandoradsverktyget för att testa anslutningen med backendtjänsten
  ```bash
  mdatp connectivity test
  ```
- Lade till möjligheten att visa den fullständiga hothistoriken i användargränssnittet (kan nås från vyn **Skyddhistorik)**
- Prestandaförbättringar & felkorrigeringar

## <a name="1007215"></a>100.72.15

- Felkorrigeringar

## <a name="1007099"></a>100.70.99

- Åtgärdat ett problem som påverkar möjligheten för vissa användare att uppgradera till macOS Catalina när realtidsskydd har aktiverats. Det här sporadiska problemet orsakades av Microsoft Defender för att Slutpunktslåsa filer i Catalina-uppgraderingspaket vid genomsökning av dem efter hot, vilket ledde till fel i uppgraderingssekvensen.

## <a name="1006899"></a>100.68.99

- Lade till möjligheten att konfigurera antivirusfunktionen för att köras i [passiv form](mac-preferences.md#enable--disable-passive-mode)
- Prestandaförbättringar & felkorrigeringar

## <a name="1006528"></a>100.65.28

- Tillagt stöd för macOS Catalina

  > [!CAUTION]
  > macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess. Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande. Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.
  >
  > Mekanismen för att bevilja detta medgivande beror på hur du har distribuerat Microsoft Defender för Endpoint:
  >
  > - För manuell distribution finns de uppdaterade instruktionerna i [avsnittet Om manuell](mac-install-manually.md#how-to-allow-full-disk-access) distribution.
  > - För hanterade distributioner, se de uppdaterade anvisningarna i [JAMF-baserad](mac-install-with-jamf.md) [distribution Microsoft Intune distributionsbaserade ämnen.](mac-install-with-intune.md#create-system-configuration-profiles)

- Prestandaförbättringar & felkorrigeringar
