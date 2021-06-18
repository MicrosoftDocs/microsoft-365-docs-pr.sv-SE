---
title: Aktivera Blockera när det först påträffas när du vill identifiera skadlig programvara på några sekunder
description: Aktivera funktionen Blockera när det först påträffas när du vill identifiera och blockera skadlig programvara inom några sekunder.
keywords: skanna, blockera när det först påträffas, skadlig programvara, påträffas, moln, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007407"
---
# <a name="turn-on-block-at-first-sight"></a>Aktivera Blockera när det först påträffas

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs antivirus-/antimalware-funktionen som kallas Blockera när det först påträffas och hur du aktiverar Blockera när det först påträffas för din organisation. 

> [!TIP]
> Den här artikeln är avsedd för företagsadministratörer och IT-tekniker som hanterar säkerhetsinställningar för organisationer. Om du inte är företagsadministratör eller IT-tekniker, men har frågor om Blockera när det först påträffas kan du läsa avsnittet[Är du inte företagsadministratör eller IT-tekniker?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Vad är Blockera när det först påträffas?

Blockera när det först påträffas är en nästa generations funktion som skyddar mot hot genom att identifiera ny skadlig programvara och blockera den på några sekunder. Blockera när det först påträffas aktiveras när vissa säkerhetsinställningar är aktiverade. Inställningarna omfattar:

- molnbaserat skydd 
- en angiven tidsgräns för sändning av exempel (t.ex. 50 sekunder) och 
- en hög filblockeringsnivå. 

I de flesta företag konfigureras inställningarna som krävs för att aktivera Blockera när det först påträffas i samband med Microsoft Defender Antivirus-distributioner. 

## <a name="how-it-works"></a>Så här fungerar det

När Microsoft Defender Antivirus stöter på en misstänkt men oidentifierad fil, skickas en fråga till serverdelen för molnskydd. I serverdelen för molnskydd tillämpas heuristik, maskininlärning och automatiska analyser på filen för att avgöra om den är skadlig eller inte.

Microsoft Defender Antivirus använder flera tekniker för identifiering och skydd för att ge exakt och intelligent skydd i realtid. 

![Lista över motorer för Microsoft Defender Antivirus](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Mer information finns i [ (Blogg) Lär känna de avancerade teknikerna i Microsoft Defender för Endpoint – nästa generations skydd](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Några saker du bör veta om Blockera när det först påträffas

- I Windows 10, version 1803 och senare, kan Blockera när det först påträffas blockera icke-portabla körbara filer (t.ex. JS, VBS eller makron) och körbara filer.

- Blockera när det först påträffas använder bara serverdelen för molnskydd för körbara filer och icke-portabla körbara filer som laddas ned från internet eller som kommer från internetzonen. Ett hashvärde för .exe-filen kontrolleras via den molnbaserade serverdelen för att avgöra om filen inte har identifierats tidigare.

- Om molnserverdelen inte kan fastställa det kommer Microsoft Defender Antivirus att låsa filen och ladda upp en kopia till molnet. I molnet utförs fler analyser för att fatta ett beslut om filen ska köras eller blockeras när den identifieras i framtiden, beroende på om den är skadlig eller inte.

- I många fall kan den här processen minska svarstiden för ny skadlig programvara från timmar till sekunder.

- Du kan [ange hur länge en fil ska förhindras från att köras](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) medan den molnbaserade skyddstjänsten analyserar filen. Du kan även [anpassa det meddelande som visas på användarnas skrivbord](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) när en fil blockeras. Du kan ändra företagets namn, kontaktinformation och meddelande-URL.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Aktivera Blockera när det först påträffas med Microsoft Intune

> [!TIP]
> Microsoft Intune är nu en del av Microsoft Endpoint Manager.

1. I administrationscentret för Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) går du till **Enheter** > **Konfigurationsprofiler**.

2. Markera eller skapa en profil med profiltypen **Enhetsbegränsningar**.

3. I **Konfigurationsinställningar** för profilen Enhetsbegränsningar, anger eller bekräftar du följande inställningar under **Microsoft Defender Antivirus**:

   - **Molnbaserat skydd**: aktiverat 
   - **Filblockeringsnivå**: hög
   - **Tidstillägg för genomsökning av filer via molnet**: 50
   - **Fråga användare innan exempel skickas**: skicka alla data utan att fråga

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Konfigurationsblockering för Intune vid första anblicken":::

4. Spara dina inställningar.

> [!TIP]
> - Om du ställer in filblockeringsnivån på **Hög** används en hög identifieringsnivå. Om filblockering mot förmodan leder till falsk positiv identifiering av legitima filer kan säkerhetsteamet [återställa filer i karantän](./restore-quarantined-files-microsoft-defender-antivirus.md).
> - Mer information om hur du konfigurerar enhetsbegränsningar för Microsoft Defender Antivirus i Intune finns i [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).
> - En lista över enhetsbegränsningar för Microsoft Defender Antivirus i Intune finns i [Inställningar för enhetsbegränsning i Windows 10 (och senare) i Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Aktivera Blockera när det först påträffas med Microsoft Endpoint Manager

> [!TIP]
> Om du letar efter Microsoft Endpoint Configuration Manager så ingår det nu som en del av Microsoft Endpoint Manager.

1. I Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) går du till **Slutpunktssäkerhet** > **Antivirus**.

2. Markera en princip eller skapa en ny princip med profiltypen **Microsoft Defender Antivirus**.

3. Ange eller bekräfta följande konfigurationsinställningar:

   - **Aktivera molnbaserat skydd**: ja
   - **Skyddsnivå som levereras i molnet**: hög
   - **Utökad tidsgräns i Defender-moln i sekunder**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Inställningar för Blockera när det först påträffas Endpoint Manager":::

4. Tillämpa Microsoft Defender Antivirus-profilen på en grupp, till exempel **Alla användare**, **Alla enheter** eller **Alla användare och enheter**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Aktivera Blockera när det först påträffas med en grupprincip

> [!NOTE]
> Vi rekommenderar att du använder Intune eller Microsoft Endpoint Manager för att aktivera Blockera när det först påträffas. 

1. På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**. 

2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** > **Administrativa mallar** > **Windows-komponenter** > **Microsoft Defender Antivirus** > **MAPS**. 

3. I MAPS-avsnittet dubbelklickar du på **Konfigurera funktionen Blockera när det först påträffas**, anger **Aktiverad** och väljer **OK**.

    > [!IMPORTANT]
    > Om du väljer **Fråga alltid (0)** minskas skyddet på enheten. Om du väljer **Skicka aldrig (2)** kommer Blockera när det först påträffas inte att fungera.

4. I MAPS-avsnittet dubbelklickar du på **Skicka filexempel när ytterligare analys krävs** och anger **Aktiverat**. Under **Skicka filexempel när ytterligare analys krävs** väljer du **Skicka alla exempel** och sedan **OK**.

5. Distribuera grupprincipobjektet i nätverket som vanligt.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Bekräfta att Blockera när det först påträffas är aktiverat på enskilda klientenheter

Du kan kontrollera att Blockera när det först påträffas är aktiverat på enskilda klientenheter med Windows-säkerhetsappen. Blockera när det först påträffas aktiveras automatiskt så länge **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.

1. Öppna Windows-säkerhetsappen.

2. Välj **Skydd mot virus och hot** och under **Inställningar för skydd mot virus och hot** väljer du **Hantera inställningar**.

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Skärmbild av inställningsetiketten för Skydd mot hot och virus i appen Windows-säkerhet":::

3. Kontrollera att **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.

> [!NOTE]
> - Om de nödvändiga inställningarna konfigureras och distribueras med grupprinciper är inställningarna som beskrivs i det här avsnittet nedtonade och inte tillgängliga för användning på enskilda slutpunkter. 
> - Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.

## <a name="validate-block-at-first-sight-is-working"></a>Kontrollera att Blockera när det först påträffas fungerar

Om du vill verifiera att funktionen fungerar laddar du ned exempelfilen [Blockera exempelfil vid första anblicken](https://demo.wd.microsoft.com/Page/BAFS). Om du vill ladda ned filen behöver du ett konto i Azure AD som har tilldelats rollen säkerhetsadministratör eller global administratör.

Kontrollera att funktionen Molnaktiverat skydd fungerar följer du instruktionerna i [Verifiera anslutningar mellan ditt nätverk och molnet](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud). 

## <a name="turn-off-block-at-first-sight"></a>Inaktivera Blockera när det först påträffas

> [!CAUTION]
> Om du inaktiverar Blockera när det först påträffas sänks skyddet för dina enheter och nätverket.

Du kan välja att inaktivera Blockera när det först påträffas om du vill behålla de nödvändiga inställningarna utan att använda Blockera när det först påträffas. Du kan tillfälligt inaktivera Blockera när det först påträffas för att se hur funktionen påverkar nätverket. Vi rekommenderar dock inte att du inaktiverar Blockera när det först påträffas permanent.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Inaktivera Blockera när det först påträffas med Microsoft Endpoint Manager

1. Gå till administrationscentret för Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) och logga in.

2. Gå till **Slutpunktssäkerhet** > **Antivirusprogram** och välj din princip för Microsoft Defender Antivirus.

3. Under **Hantera** väljer du **Egenskaper**.

4. Välj **Redigera** bredvid **Konfigurationsinställningar**.

5. Ändra en eller flera av följande inställningar:

   - Ställ in **Aktivera molnbaserat skydd** på **Nej** eller **Inte konfigurerat**.
   - Ställ in **Skyddsnivå som levereras i molnet** på **Inte konfigurerat**.
   - Avmarkera kryssrutan för **Utökad tidsgräns i Defender-moln i sekunder**.

6. Granska och spara inställningarna.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Inaktivera Blockera när det först påträffas med en grupprincip

1. På datorn för hantering av grupprinciper öppnar du [konsolen Grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), högerklickar på det grupprincipobjekt som du vill konfigurera och väljer **Redigera**.

2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Öppna trädstrukturen via **Windows-komponenter** > **Microsoft Defender Antivirus** > **MAPS**.

4. Dubbelklicka på **Konfigurera funktionen Blockera när det först påträffas** och ställ in alternativet på **Inaktiverat**.

    > [!NOTE]
    > Nödvändiga grupprinciper inaktiveras eller ändras inte när du inaktiverar Blockera när det först påträffas.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Är du inte företagsadministratör eller IT-tekniker?

Om du inte är företagsadministratör eller IT-tekniker, men har frågor om Blockera när det först påträffas är det här avsnittet för dig. Blockera när det först påträffas skyddar mot hot genom att identifiera och blockera skadlig programvara på några sekunder. Även om det inte finns en inställning som kallas Blockera när det först påträffas, aktiveras funktionen när vissa inställningar konfigureras på enheten.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Så här aktiverar och inaktiverar du Blockera när det först påträffas på din enhet

Om du har en privat enhet som inte hanteras av en organisation kanske du undrar hur du aktiverar eller inaktiverar Blockera när det först påträffas. Du kan hantera Blockera när det först påträffas med Windows-säkerhetsappen.

1. Öppna Windows-säkerhetsappen på Windows 10-datorn.

2. Välj **Skydd mot virus och hot**.

3. Välj **Hantera inställningar** under **Inställningar för skydd mot virus och hot**.

4. Gör något av följande:

   - Om du vill aktivera Blockera när det först påträffas ska du se till att både **Molnbaserat skydd** och **Skicka exempel automatiskt** är aktiverade.

   - Om du vill inaktivera Blockera när det först påträffas inaktiverar du **Molnbaserat skydd** eller **Skicka exempel automatiskt**. <br/>
    
     > [!CAUTION]
     > Om du inaktiverar Blockera när det först påträffas sänks skyddsnivån för enheten. Vi rekommenderar inte att du permanent inaktiverar Blockera när det först påträffas. 


## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Skydda dig med Windows-säkerhet](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
