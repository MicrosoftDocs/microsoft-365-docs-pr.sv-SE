---
title: Aktivera spärr vid första synen för att upptäcka skadlig programvara efter bara några sekunder
description: Aktivera funktionen för blockering vid första synen för att identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanning, blockera vid första synen, skadlig kod, första synen, molnet, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079209"
---
# <a name="turn-on-block-at-first-sight"></a>Aktivera blockera direkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs en antivirus-/antimalware-funktion som kallas "block vid första synen" och beskriver hur du aktiverar blockering vid första synen för organisationen. 

> [!TIP]
> Den här artikeln är avsedd för företagsadministratörer och IT-proffs som hanterar säkerhetsinställningar för organisationer. Om du inte är en enteprise-administratör eller IT-proffs men har frågor om block vid första anblicken, se Inte företagsadministratör eller [IT-proffs?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Vad är "block vid första synen"?

Blockera vid första synen är en skyddfunktion i nästa generations skydd som identifierar ny skadlig programvara och blockerar den inom några sekunder. Blockera vid första synen är aktiverat när vissa säkerhetsinställningar är aktiverade. Dessa inställningar omfattar:

- Moln levererat skydd; 
- Ett angivet exempel på en tidsgräns för sändning (t.ex. 50 sekunder). och 
- En hög filblockeringsnivå. 

I de flesta företag är de inställningar som krävs för att aktivera spärr vid första anblicken konfigurerade med Microsoft Defender Antivirus-distributioner. 

## <a name="how-it-works"></a>Så här fungerar det

När Microsoft Defender Antivirus stöter på en misstänkt men oupptäckta fil, uppstår ett problem i vårt molnskyddsbackend. I molnbackend används heuristics, maskininlärning och automatiserad analys av filen för att avgöra om filerna är skadliga eller inte som ett hot.

Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, intelligent och realtidsskydd. 

![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Mer information finns i den här bloggen: Lär känna den avancerade tekniken som ligger till grund för nästa generations skydd [i Microsoft Defender för Slutpunkt.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Några saker du bör veta om block vid första synen

- I Windows 10, version 1803 eller senare, kan block vid första anblicken blockera icke-bärbara körbara filer (t.ex. JS, VBS eller makron) och körbara filer.

- Spärr vid första anblicken använder bara molnskyddsbackend för körbara filer och icke-bärbara körbara filer som laddas ned från Internet eller som kommer från Internetzonen. Ett hashvärde för EXE-filen kontrolleras via molnbackend för att fastställa om filen är en tidigare oupptäckta fil.

- Om molnbackend inte kan avgöra något låses filen och en kopia laddas upp till molnet av Microsoft Defender Antivirus. Molnet utför mer analys för att nå ett avgörande innan det antingen gör det möjligt att köra filen eller blockerar den i alla framtida möten, beroende på om filen är skadlig eller inte som ett hot.

- I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.

- Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen. Du kan också [anpassa meddelandet som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras. Du kan ändra företagets namn, kontaktinformation och meddelande-URL.

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
> - Om du ställer in blockeringsnivån **Hög** tillämpas en stark identifieringsnivå. Om en filblockering orsakar en falsk positiv identifiering av legitima filer kan ditt säkerhetsteam återställa filer i karantän som då [blockeras.](./restore-quarantined-files-microsoft-defender-antivirus.md)
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

4. I avsnittet KARTOR dubbelklickar du på **Skicka filexempel när vidare analys krävs** och ställer in det på **Aktiverad**. Under **Skicka filexempel när ytterligare analys krävs** väljer du Skicka alla **exempel** och väljer sedan **OK.**

5. Distribuera om grupprincipobjektet i nätverket på det sätt du brukar.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Bekräfta att blocket vid första synen är aktiverat på enskilda klientenheter

Du kan bekräfta att blocket vid första synen är aktiverat på enskilda klientenheter med hjälp av Windows-säkerhetsappen. Spärr vid första synen aktiveras automatiskt så länge som **moln levererat skydd och** automatisk **sändning** av stickprov är aktiverade.

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

Du kan välja att inaktivera blocket vid första synen om du vill behålla de nödvändiga inställningarna utan att använda skydd vid första synen. Du kan tillfälligt stänga av spärren vid första synen för att se hur den här funktionen påverkar nätverket. Vi rekommenderar dock inte att spärrskyddet för första synen inaktiveras permanent.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Inaktivera blocket vid första synen med Microsoft Endpoint Manager

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Gå till **Endpoint Security**  >  **Antivirus** och välj sedan din Microsoft Defender Antivirus-policy.

3. Välj **Egenskaper** under **Hantera**.

4. Välj **Redigera bredvid** **Konfigurationsinställningar.**

5. Ändra en eller flera av följande inställningar:

   - Ställ **in Aktivera moln levererat skydd till** **Nej** eller **Inte konfigurerat.**
   - Ställ **in skyddsnivån Moln levererat till** Ej **konfigurerad**.
   - Avmarkera kryssrutan för den utökade **tidsgränsen för Defender Cloud efter några sekunder.**

6. Granska och spara inställningarna.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Inaktivera blocket vid första synen med Grupprincip

1. På datorn för grupprinciphantering öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och väljer **sedan Redigera.**

2. Med **grupprinciphanteringsredigeraren går** du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet med **Windows-komponenterna**  >  **Microsoft Defender Antivirus**  >  **MAPS**.

4. Dubbelklicka på Konfigurera **funktionen "Spärr vid första synen"** och ställ in alternativet på **Inaktiverad**.

    > [!NOTE]
    > Om du inaktiverar blocket vid första synen inaktiveras inte nödvändiga gruppprinciper.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Är du inte företagsadministratör eller IT-proffs?

Om du inte är företagsadministratör eller IT-proffs, men har frågor om block vid första anblicken, är det här avsnittet för dig. Blockera vid första synen är en skyddfunktion för hot som identifierar och blockerar skadlig programvara inom några sekunder. Även om det inte finns en viss inställning som kallas "Blockera vid första anblicken" är funktionen aktiverad när vissa inställningar är konfigurerade på enheten.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Hur du hanterar blockering vid första synen på eller av på din egen enhet

Om du har en personlig enhet som inte hanteras av en organisation kanske du undrar hur du aktiverar eller inaktiverar blockering vid första anblicken. Du kan använda Windows-säkerhetsappen för att hantera blocket vid första synen.

1. Öppna appen Windows-säkerhet på din Windows 10-dator.

2. Välj **Skydd mot & och hot**.

3. Under **Inställningar & skydd mot virus och** hot väljer du Hantera **inställningar**.

4. Gör något av följande:

   - För att aktivera spärr vid första synen ska du se till att både **molnskydd och** **automatisk sändning** av stickprov är aktiverat.

   - Inaktivera blocket vid första synen genom att inaktivera **moln levererat skydd eller** automatisk **exempelindata**. <br/>
    
     > [!CAUTION]
     > Om du stänger av block vid första synen sänks skyddsnivån för din enhet. Vi rekommenderar inte att blocket inaktiveras permanent vid första synen. 


## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aktivera moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Skydda dig med Windows-säkerhet](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)