---
title: Aktivera spärr vid första synen för att upptäcka skadlig programvara efter bara några sekunder
description: Aktivera funktionen för blockering vid första synen för att identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanna, BAFS, skadlig programvara, visas först, första synen, molnet, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765761"
---
# <a name="turn-on-block-at-first-sight"></a>Aktivera block vid första synen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Blockering vid första synen är ett sätt att identifiera och blockera ny skadlig programvara inom några sekunder. Skyddet aktiveras som standard när vissa nödvändiga inställningar är aktiverade. De här inställningarna omfattar moln levererat skydd, en angiven tidsgräns för sändning (t.ex. 50 sekunder) och en nivå av hög filblockering. I de flesta företag är de här inställningarna aktiverade som standard med distributioner av Microsoft Defender Antivirus. 

Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen. Du kan också [anpassa meddelandet som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras. Du kan ändra företagets namn, kontaktinformation och meddelande-URL.

>[!TIP]
>Besök microsoft Defender för slutpunktens demowebbplats på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) bekräfta att funktionerna fungerar och se hur de fungerar.

## <a name="how-it-works"></a>Så här fungerar det

När Microsoft Defender Antivirus stöter på en misstänkt men oupptäckta fil, uppstår ett problem i vårt molnskyddsbackend. I molnbackend används heuristics, maskininlärning och automatiserad analys av filen för att avgöra om filerna är skadliga eller inte som ett hot.

Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, intelligent och realtidsskydd. Mer information finns i den här bloggen: Lär känna den avancerade tekniken som ligger till grund för nästa generations skydd [i Microsoft Defender för Slutpunkt.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)  

I Windows 10, version 1803 eller senare, kan blockering vid första anblicken blockera icke-bärbara körbara filer (t.ex. JS, VBS eller makron) samt körbara filer.

Spärr vid första anblicken använder bara molnskyddsbackend för körbara filer och icke-bärbara körbara filer som laddas ned från Internet eller som kommer från Internetzonen. Ett hashvärde för EXE-filen kontrolleras via molnbackend för att fastställa om filen är en tidigare oupptäckta fil.

Om molnbackend inte kan avgöra något låses filen och en kopia laddas upp till molnet av Microsoft Defender Antivirus. Molnet utför ytterligare analyser för att nå ett avgörande innan det antingen gör det möjligt att köra filen eller blockerar den i alla framtida möten, beroende på om filen är skadlig eller säker.

I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Aktivera blockera vid första synen med Microsoft Intune

> [!TIP]
> Microsoft Intune ingår nu i Microsoft Endpoint Manager.

1. Gå till Konfigurationsprofiler för enheter i administrationscentret för Microsoft Endpoint [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  **Manager**( ).

2. Välj eller skapa en profil med **profiltypen** Enhetsbegränsningar.

3. I **konfigurationsinställningarna** för profilen För enhetsbegränsningar anger eller bekräftar du följande inställningar under **Microsoft Defender Antivirus:**

   - **Moln levererat skydd**: Aktiverat
   - **Blockeringsnivå för filer:** hög
   - **Tidstillägg för filsökning i molnet:** 50
   - **Fråga användarna innan exempel skickas:** Skicka alla data utan att fråga

   ![Intune-konfiguration](images/defender/intune-block-at-first-sight.png)

4. Spara inställningarna.

> [!TIP]
> - Om du ställer in blockeringsnivån **Hög** tillämpas en stark identifieringsnivå. Om filblockering orsakar en falsk positiv identifiering av legitima filer kan du återställa filer i karantän om så inte är [möjligt.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Mer information om hur du konfigurerar begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Konfigurera inställningar [för enhetsbegränsning i Microsoft Intune.](/intune/device-restrictions-configure)
> - En lista över begränsningar för Microsoft Defender Antivirus-enheter i Intune finns i Enhetsbegränsning för [Windows 10-inställningar (och nyare) i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Aktivera block vid första synen med Microsoft Endpoint Manager

> [!TIP]
> Om du letar efter Microsoft Endpoint Configuration Manager är det nu en del av Microsoft Endpoint Manager.

1. Gå till Slutpunktssäkerhetsantivirusprogram i Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com)   >  ).

2. Välj en befintlig princip eller skapa en ny princip med profiltypen **Microsoft Defender** Antivirus.

3. Ange eller bekräfta följande konfigurationsinställningar:

   - **Aktivera moln levererat skydd**: Ja
   - **Moln levererat skyddsnivå**: Hög
   - **Utökad tidsgräns för Defender Cloud på några sekunder**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Inställningar för spärr vid första synen i Slutpunktshanteraren":::

4. Använd Microsoft Defender Antivirus-profilen för en grupp, till exempel **Alla användare,** **Alla enheter** eller Alla användare **och enheter.**

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Aktivera blockera vid första synen med Grupprincip

> [!NOTE]
> Vi rekommenderar att du använder Intune eller Microsoft Endpoint Manager för att aktivera block vid första synen. 

1. Öppna grupprinciphanteringskonsolen på datorn för [grupprinciphantering,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.** 

2. Med **redigeraren för hantering av grupprinciper** går du **till Administrativa mallar** för  >    >  **datorkonfiguration Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **MAPS**. 

3. I avsnittet KARTOR dubbelklickar du på Konfigurera funktionen "Blockera vid första **synen"** och ställer in den på **Aktiverad**. Välj sedan **OK.**

    > [!IMPORTANT]
    > Om du **ställer in på Fråga alltid (0)** sänks enhetens skyddstillstånd. Inställning till **Skicka aldrig (2) innebär** att blocket vid första synen inte fungerar.

4. I avsnittet KARTOR dubbelklickar du på **Skicka filexempel när vidare analys krävs** och ställer in det på **Aktiverad**. Under **Skicka filexempel när ytterligare analys krävs väljer** du Skicka alla **exempel** och klickar sedan på **OK.**

5. Om du har ändrat några inställningar distribuerar du grupprincipobjektet igen över nätverket för att säkerställa att alla slutpunkter täcks.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>Bekräfta att blocket vid första synen är aktiverat för enskilda klienter

Du kan kontrollera att blocket vid första synen är aktiverat för enskilda klienter med windows säkerhetsinställningar.

Spärr vid första synen aktiveras automatiskt så länge som **moln levererat skydd och** automatisk **sändning** av stickprov är aktiverade.

1. Öppna Windows-säkerhetsappen.

2. Välj **Virus & skydd mot hot** och välj sedan Hantera & inställningar för skydd mot **&** **virushot**.

   ![Skärmbild av etiketten för & för skydd mot virus i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. Bekräfta att **skydd mot moln levererat och** automatisk **exempelinskickning** båda är aktiverat.

> [!NOTE]
> - Om de nödvändiga inställningarna konfigureras och distribueras med grupprincip kommer inställningarna som beskrivs i det här avsnittet att vara nedtonade och inte tillgängliga för användning i enskilda slutpunkter. 
> - Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningar.

## <a name="validate-block-at-first-sight-is-working"></a>Verifiera att blocket vid första synen fungerar

Verifiera att funktionen fungerar genom att följa instruktionerna i [Verifiera anslutningar mellan nätverket och molnet.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>Inaktivera block vid första synen

> [!CAUTION]
> Om du stänger av block vid första synen sänks skyddstillståndet för dina enheter och ditt nätverk.

Du kan välja att inaktivera blocket vid första synen om du vill behålla de nödvändiga inställningarna utan att använda skydd vid första synen. Du kan tillfälligt stänga av blocket vid första synen om du har problem med svarstiden eller om du vill testa funktionens påverkan på nätverket. Vi rekommenderar dock inte att spärrskyddet för första synen inaktiveras permanent.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Inaktivera blocket vid första synen med Microsoft Endpoint Manager

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Gå till **Endpoint Security**  >  **Antivirus** och välj sedan din Microsoft Defender Antivirus-policy.

3. Välj **Egenskaper** under **Hantera**.

4. Välj **Redigera bredvid** **Konfigurationsinställningar.**

5. Ändra en eller flera av följande inställningar:

   - Ställ **in Aktivera moln levererat skydd till** **Nej** eller **Inte konfigurerat.**
   - Ställ **in skyddsnivån Moln levererat till** Ej **konfigurerad**.
   - Avmarkera kryssrutan **Utökad tidsgräns för Defender Cloud på några** sekunder.

6. Granska och spara inställningarna.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Inaktivera blocket vid första synen med Grupprincip

1. På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar sedan på **Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet med **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **MAPS**.

4. Dubbelklicka på Konfigurera **funktionen "Spärr vid första synen"** och ställ in alternativet på **Inaktiverad**.

    > [!NOTE]
    > Om du inaktiverar blocket vid första synen inaktiveras inte nödvändiga gruppprinciper.

## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Aktivera moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)