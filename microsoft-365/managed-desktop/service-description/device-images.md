---
title: Enhetsbilder
description: Bildkrav när du beställer nya enheter eller återanvänder befintliga enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 211e26035ad8bdf73defde85c33a631af3a193d0
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300118"
---
# <a name="device-images"></a>Enhetsbilder


Oavsett om du [beställer nya](#new-devices) enheter [eller](#existing-devices) återanvänder befintliga har du flera alternativ för att säkerställa att bilden på enheten uppfyller våra [enhetskrav.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>Nya enheter.
När du beställer en [](device-requirements.md#minimum-requirements)ny enhet från en godkänd tillverkare följer du de här anvisningarna för att se till att de levereras med rätt Microsoft Hanterat skrivbord bild- och programvarukonfiguration. När du planerar att registrera en viss enhetsmodell i tjänsten för första gången bör du testa ett exempel för att säkerställa att den ger den användarupplevelse du förväntar dig. Mer information finns i [Validera nya enheter](/microsoft-365/managed-desktop/get-started/validate-device).

### <a name="dell"></a>Dell
Arbeta direkt med Dell-säljrepresentanten, som ser till att den bild som godkänts av Microsoft Hanterat skrivbord tillämpas på enheter för din beställning. Om du har fler frågor om Dell-enheter, bilden och beställningsprocessen kontaktar du MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
När du beställer nya enheter från HP ska du se till att använda den specifika SKU som listas i avsnittet Ytterligare krav för varje modell som finns på webbplatsen [för Handla Windows 10 Pro-företagsenheter](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) (filtrera vyn för att visa Microsoft Hanterat skrivbord enheter).

Om du beställer en enhet från HP som [](customizing.md) har godkänts som undantag men som för närvarande inte visas på sidan Enhetslista begär du att SKU:n används för din modell. Vi arbetar med HP för att hämta den här informationen till dig genom att använda din undantagsbegäran. Du kan också kontakta HP direkt om du har frågor om instruktionerna för enheter och enhetsbeställning genom att använda de här adresserna:
 
- Amerika: mmd-americas@hp.com
- Europa/Mellanöstern/Afrika: mmd-emea@hp.com
- Asien och Stillahavsområdet/Japan: mmd-apj@hp.com
- Globalt: mmd@hp.com

### <a name="lenovo"></a>Lenovo
När du beställer enheter från Lenovo för användning Microsoft Hanterat skrivbord måste du ange ett specifikt delnummer som en del av beställningen. Kontakta din Lenovo-säljrepresentant eller Lenovo Channel-partner och be dem skapa en "*särskild* budmodell " med ett system som uppfyller våra [enhetskrav](device-requirements.md#minimum-requirements). Om du vill ta med en förinstallerad bild som är kompatibel med Microsoft Hanterat skrivbord ber du säljrepresentanten att hänvisa till "systemets byggblockdelsnummer *SBB0Q94938 – MMD Enablement*."

Följande produkter är för närvarande aktiverade för Microsoft Hanterat skrivbord support:

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Alla Microsoft-enheter som uppfyller enhetskraven har en bild som fungerar med Microsoft Hanterat skrivbord. Inga andra åtgärder krävs.

Om du vill ha den senaste bilden tillgänglig i fabrik på en Microsoft-enhet kan du arbeta med din Surface-specialist för att använda Surface-processen "Pegged PO".

## <a name="existing-devices"></a>Befintliga enheter

Du kan återanvända befintliga enheter så länge de uppfyller både [enhetskraven](device-requirements.md#minimum-requirements) och [programvarukraven.](device-requirements.md#installed-software) Följ de steg som är relevanta för tillverkaren.

Du kan animera enheter med en bild från tillverkaren eller genom att använda Microsoft Hanterat skrivbord "universell bild". Om du vill ha en lämplig bild [](#new-devices) från tillverkaren kan du beställa minst en ny enhet av den modell som du återanvänder. Sedan kan du hämta bilden från enheten och använda den på andra enheter med exakt samma modell.

> [!NOTE]
> Det är du som ansvarar för att skapa, testa och distribuera bilder. Vi rekommenderar också att du använder lämpliga bilder som tillhandahålls av tillverkaren när det är möjligt i stället för anpassade bilder, inklusive "universell bild".

### <a name="hp"></a>HP

Hps kommersiella datorer som levereras med HP Corporate Ready Image innehåller en . WIM-fil för återställning. Du kan använda den här bilden för att tillämpa fabriksåterställningsbilden på andra enheter av samma modell.

Dessa steg tar bort alla data på enheten, så innan du startar bör du backa upp data som du vill behålla.

1. [Skapa en startbar USB-enhet](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) med WinPE.
2. Kopiera de här filerna från C: \\ SOURCES till USB-enheten:
    - WiM-filen för fabriksåterställning (till exempel HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - DISTRIBUERA. CMD
    - ReCreatePartitions.txt
3. [Starta enheten på WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB-enhet.
4. I en kommandotolk kör [ duDiskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references).
5. I Diskpart kör du `list disk` och noterar sedan numret till den primära lagringsdisken (vanligtvis disk 0).
6. Avsluta Diskpart genom att skriva `exit` .
7. I kommandotolken kör du , där sys_disk är disknumret för den primära lagringsskivan du just fastställa `deploy.cmd <sys_disk> <recovery_wim>` *recovery_wim* är filnamnet på .  WIM-fil som du kopierade tidigare.
8. Ta bort USB-enheten och starta sedan om enheten.

### <a name="microsoft"></a>Microsoft 

Microsoft Surface-enheter innehåller bilder av "bare metall [recovery"](https://support.microsoft.com/en-us/surfacerecoveryimage) som är specifika för varje modell. Du kan använda bilderna för att animera enheter.

De här bilderna använder Windows Recovery Environment (WinRE) och det här är en manuell process (inte automatiserad). Följ anvisningarna i [Skapa och använda en USB-återställningsenhet för Surface.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>Universell bild
Microsoft Hanterat skrivbord har skapat en bild som innehåller Windows 10 Pro och Microsoft 365-applikationer för företag som du kan använda med Microsoft Hanterat skrivbord. Det är dock bäst att använda bilder lämpliga för Microsoft Hanterat skrivbord som tillhandahålls av tillverkaren när det är möjligt, även om det innebär en äldre Windows-version som sedan måste uppdateras när användaren loggar in. Att använda Microsoft Hanterat skrivbord Universell bild bör vara ett slutligt alternativ.

- Vi uppdaterar bilden med de senaste Windows månatliga kvalitetsuppdateringarna var 30–60:e dag och Microsoft 365-applikationer för Enterprise-uppdateringar minst två gånger per år.
- Bilden innehåller ett paket för återställningsetablering för att säkerställa att Microsoft 365-applikationer för företag återställs efter Windows återställningsscenarier.
- Du kan distribuera bilden med USB-enheter. Den innehåller en skriptbar process för att infoga drivrutiner (anges i dokumentationen som ingår i bilden).
- Du kan ändra skripten och mapparna som ingår och användas med andra anpassningar, till exempel lägga till specifika kumulativa uppdateringar, kopiera filen eller utföra andra kontroller.
- Drivrutiner och kvalitetsuppdateringar läggs till i Windows under distributionen från USB-enheten.

> [!NOTE]
> Det är ditt ansvar att lägga till alla nödvändiga drivrutiner, utföra alla tester och se till att det inte finns några problem med den slutliga distribuerade bilden. Vi tillhandahåller den universella bilden "som den är", men kommer att ge teknisk vägledning och svara på frågor. Kontakta MMDImage@microsoft.com.

Skicka förfrågningar om innehåll och dokumentation för den universella bilden genom att skapa en ändringsförfrågan i [administrationsportalen.](../get-started/access-admin-portal.md)


