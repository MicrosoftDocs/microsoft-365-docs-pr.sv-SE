---
title: Skapa indikatorer för filer
ms.reviewer: ''
description: Skapa indikatorer för en filhash som definierar identifiering, skydd och undantag för enheter.
keywords: fil, hash, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730540"
---
# <a name="create-indicators-for-files"></a>Skapa indikatorer för filer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig kod. Om du vet en potentiellt skadlig körbar fil (PE) kan du blockera den. Den här åtgärden gör att den inte kan läsas, skrivas eller köras på enheter i organisationen.

Du kan skapa indikatorer för filer på tre olika sätt:

- Genom att skapa en indikator via inställningssidan
- Genom att skapa en sammanhangsberoende indikator med knappen lägg till indikator från filinformationssidan
- Genom att skapa en indikator via [indikator-API:t](ti-indicator.md)

## <a name="before-you-begin"></a>Innan du börjar

Det är viktigt att förstå följande förutsättningar innan du skapar indikatorer för filer:

- Den här funktionen är tillgänglig om din **organisation använder Microsoft Defender Antivirus (i aktivt läge) och** **molnbaserat skydd är aktiverat.** Mer information finns i [Hantera molnbaserat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- Klientversionen av Antimalware måste vara 4.18.1901.x eller senare. Se [Månadsplattform och motorversioner](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Stöds på enheter med Windows 10, version 1703 eller senare, Windows Server 2016 och 2019.

- För att börja blockera filer måste du först aktivera [funktionen "blockera eller tillåt" i](advanced-features.md) Inställningar.

Den här funktionen är utformad för att förhindra att misstänkt skadlig programvara (eller potentiellt skadliga filer) laddas ned från webben. Det har för närvarande stöd för bärbara körbara (PE) filer, .exe och .dll filer. Täckningen utökas med tiden.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Skapa en indikator för filer från inställningssidan

1. I navigeringsfönstret väljer du Inställningar > **Indikatorer**.

2. Välj fliken **Filhash.**  

3. Välj **Lägg till indikator**.

4. Ange följande information:
    - Indikator – Ange entitetsinformation och definiera indikatorns förfallotid.
    - Åtgärd – Ange vilken åtgärd som ska vidtas och ange en beskrivning.
    - Omfattning – Definiera enhetens omfattning.

5. Granska informationen på fliken Sammanfattning och välj sedan **Spara**.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Skapa en sammanhangsberoende indikator från filinformationssidan

Ett av alternativen när du vidtar [svarsåtgärder för en fil är](respond-file-alerts.md)att lägga till en indikator för   filen. När du lägger till en indikatorhash för en fil kan du välja att avisering ska visas och blockera filen när en enhet i organisationen försöker köra den.

Filer som blockeras automatiskt av en indikator visas inte i filens Åtgärdscenter, men aviseringarna visas fortfarande i kön Aviseringar.

>[!IMPORTANT]
>- Vanligtvis används filblock och tas bort inom några minuter, men det kan ta upp till 30 minuter.
>- Om det finns filindikatorprinciper som står i konflikt tillämpas den säkrare principens tillämpningsprincip. En SHA-256-princip för hash-kod för filer har till exempel företräde framför en MD5-princip för hash-hash-kod för filer om båda hash-typerna definierar samma fil.
>- Om grupprincipen EnableFileHashComputation är inaktiverad minskar blockeringsprecisionen för filens IoC. Men aktivering av EnableFileHashComputation kan påverka enhetens prestanda.
>    - Till exempel kan kopiering av stora filer från en nätverksresurs till din lokala enhet, särskilt via en VPN-anslutning, påverka enhetens prestanda.
>    - Mer information om grupprincipen EnableFileHashComputation finns i [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Hantering av policykonflikter  

Konflikter i hanteringen av certifikat- och fil-IoC-policyer följer nedanstående ordning:

- Om filen inte tillåts av Windows Defender programkontrollen och AppLocker-framtvinga-principen/-principerna blockerar **du**

- Annars om filen tillåts av Microsoft Defender Antivirus och sedan **Tillåt**

- Annars om filen blockeras eller varnas av ett block eller varnar fil-IoC ska du **blockera/varna**

- Annars om filen tillåts av en IoC-princip för filen klickar du på **Tillåt**

- Om filen annars blockeras av ASR-regler, CFA, AV, SmartScreen och sedan **Blockera**  

- Tillåt **annars** (skickar Windows Defender programkontroll & AppLocker-principen, inga IoC-regler gäller för den)

Om det finns IoC-principer i konflikt med samma tillämpningstyp och mål tillämpas principen för den säkrare hashen (vilket innebär längre). En SHA-256-IoC-princip för filshashar vinner till exempel över en MD5-IoC-princip för filshashar om båda hashtyperna definierar samma fil.

Observera att Hantering av hot och säkerhetsrisker blockerat sårbart program använder fil-IoCs för tillämpning och kommer att följa den ordning som beskrivs ovan för hantering av konflikter.

### <a name="examples"></a>Exempel

|Komponent |Tillämpning av komponenter |Filindikatoråtgärd |Resultat
|--|--|--|--|
|Undantag för filsökväg för att minska attackytan |Tillåt |Blockera |Blockera
|Minskningsregel för attackytan |Blockera |Tillåt |Tillåt
|Windows Defender-programreglering |Tillåt |Blockera |Tillåt |
|Windows Defender-programreglering |Blockera |Tillåt |Blockera
|Microsoft Defender Antivirus undantag |Tillåt |Blockera |Tillåt

## <a name="see-also"></a>Se även

- [Skapa indikatorer](manage-indicators.md)
- [Skapa indikatorer för IP:er och URL:er/domäner](indicator-ip-domain.md)
- [Skapa indikatorer baserade på certifikat](indicator-certificates.md)
- [Hantera indikatorer](indicator-manage.md)
