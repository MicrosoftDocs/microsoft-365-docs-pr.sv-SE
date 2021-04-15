---
title: Microsoft Defender Antivirus i Windows-säkerhetsappen
description: Med Microsoft Defender Antivirus ingår nu i Windows-säkerhetsappen kan du granska, jämföra och utföra vanliga uppgifter.
keywords: wdav, antivirus, brandvägg, säkerhet, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765329"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus i Windows-säkerhetsappen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I Windows 10, version 1703 och senare är appen Windows Defender en del av Windows-säkerhet.

Inställningar som tidigare ingick i Windows Defender-klienten och de huvudsakliga Windows-inställningarna har kombinerats och flyttats till den nya appen, som installeras som standard i Windows 10, version 1703.

> [!IMPORTANT]
> Om du inaktiverar Windows Säkerhetscenter-tjänsten inaktiveras inte Microsoft Defender Antivirus eller [Windows Defender-brandväggen.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) De inaktiveras automatiskt när ett antivirusprogram eller en brandvägg för tredje part installeras och hålls uppdaterade.
>
> Om du inaktiverar Windows Säkerhetscenter-tjänsten eller konfigurerar tillhörande grupprincipinställningar så att den inte startas eller körs kan Windows-säkerhetsappen visa inaktuell eller felaktig information om antivirus- eller brandväggsprodukter som du har installerat på enheten.
> Det kan också förhindra att Microsoft Defender Antivirus aktiverar sig själv om du har ett gammalt eller inaktuellt antivirusprogram från tredje part eller om du avinstallerar antivirusprodukter från tredje part som du kanske har installerat tidigare.
> Det här minskar skyddet på enheten avsevärt och kan leda till skadlig kod.

Mer information [om andra säkerhetsfunktioner](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) i Windows som kan övervakas i appen finns i artikeln om Windows-säkerhet.

Appen Windows-säkerhet är ett klientgränssnitt i Windows 10, version 1703 och senare. Det är inte microsoft Defender Säkerhetscenter-webbportalen som används för att granska och hantera [Microsoft Defender för slutpunkt.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Granska inställningarna för skydd mot virus och hot i Windows-säkerhetsappen

![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

1. Öppna appen Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Defender på **startmenyn.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).
   
I följande avsnitt beskrivs hur du utför några av de vanligaste uppgifterna när du granskar eller interagerar med hotskyddet som tillhandahålls av Microsoft Defender Antivirus i Windows-säkerhetsappen.

> [!NOTE]
> Om de här inställningarna konfigureras och distribueras med grupprincip kommer inställningarna som beskrivs i det här avsnittet att vara nedtonade och inte tillgängliga för användning i enskilda slutpunkter. Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningar. I [avsnittet Konfigurera användarinteraktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) beskrivs hur du kan konfigurera åsidosättningsinställningar för lokala policyer.

## <a name="run-a-scan-with-the-windows-security-app"></a>Köra en genomsökning med Windows-säkerhetsappen

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på **startmenyn** och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Välj **Snabbsökning**. Du kan också köra en fullständig genomsökning genom att **välja Skanningsalternativ** och sedan välja ett alternativ, till exempel **Fullständig sökning**.

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Granska uppdateringsversionen av säkerhetsintelligens och ladda ned de senaste uppdateringarna i Windows-säkerhetsappen

![Information om versionsnumret för säkerhetsintelligens](images/defender/wdav-wdsc-defs.png)

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på *startmenyn* och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Välj **Uppdateringar & skydd mot virus .** Den installerade versionen visas tillsammans med en del information om när den laddades ned. Du kan kontrollera din aktuella version mot den senaste versionen som finns tillgänglig för manuell nedladdning eller granska ändringsloggen för den versionen. Se [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

4. Välj **Sök efter uppdateringar för** att ladda ned nya skyddsuppdateringar (om det finns några).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Se till att Microsoft Defender Antivirus är aktiverat i Windows-säkerhetsappen

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på *startmenyn* och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Välj **Inställningar & för skydd mot virushot**.

4. Ändra **realtidsskyddet till** **På**.

    > [!NOTE]
    > Om du **inaktiverar realtidsskyddet** aktiveras det automatiskt igen efter en kort fördröjning. Detta är för att säkerställa att du är skyddad från skadlig programvara och hot.
    > Om du installerar ett annat antivirusprogram inaktiverar Microsoft Defender Antivirus automatiskt sig självt och visas som sådant i Windows-säkerhetsappen. En inställning visas som gör att du kan aktivera [begränsad regelbunden genomsökning.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Lägga till undantag för Microsoft Defender Antivirus i Windows-säkerhetsappen

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på *startmenyn* och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Under Hantera **inställningar väljer** du Inställningar & för skydd mot **virus .**

4. Under inställningen **Undantag väljer** du Lägg till eller ta **bort undantag.** 

5. Välj plusikonen **+** () om du vill välja typ och ange alternativ för varje undantag. 

I följande tabell sammanfattas undantagstyper och vad som händer:

|Exkluderingstyp  |Definieras av  |Vad som händer  |
|---------|---------|---------|
|**Fil** |Plats <br/>Exempel: `c:\sample\sample.test` |Den specifika filen hoppas över av Microsoft Defender Antivirus. |
|**Mapp**    |Plats <br/>Exempel: `c:\test\sample`       |Alla objekt i den angivna mappen hoppas över av Microsoft Defender Antivirus.         |
|**Filtyp**   |Filnamnstillägg <br/>Exempel: `.test` |Alla filer med tillägget `.test` var som helst på enheten hoppas över av Microsoft Defender Antivirus.         |
|**Process**     |Körbar sökväg <br>Exempel: `c:\test\process.exe`         |Den specifika processen och alla filer som öppnas av den processen hoppas över av Microsoft Defender Antivirus.         |

Mer information finns i följande resurser:
- [Konfigurera och validera undantag baserat på filtillägg och mappplats](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Konfigurera undantag för filer som öppnas av processer](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Granska historik för identifiering av hot i appen Windows Defender Säkerhetscenter

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på *startmenyn* och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Välj **Skyddshistorik**. Eventuella tidigare objekt visas.

## <a name="set-ransomware-protection-and-recovery-options"></a>Ange alternativ för utpressningstrojaner och återställning

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på *startmenyn* och sedan välja **Windows-säkerhet.**

2. Välj panelen **& skydd mot hot** (eller sköldikonen på den vänstra menyraden).

3. Under **Utpressningstrojanskydd** väljer du **Hantera utpressningstrojanskydd**.

4. Information om hur **du ändrar inställningarna för kontrollerad** mappåtkomst finns i Skydda viktiga mappar med [kontrollerad mappåtkomst.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Om du vill konfigurera återställningsalternativ för  utpressningstrojaner väljer du Konfigurera **under** Återställning av utpressningstrojandata och följer anvisningarna för att länka eller konfigurera ditt OneDrive-konto så att du enkelt kan återställa efter en utpressningstrojanattack.

## <a name="see-also"></a>Se även
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)