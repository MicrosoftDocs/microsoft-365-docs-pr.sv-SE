---
title: Aktivera molnskydd i Microsoft Defender Antivirus
description: Aktivera molnskydd för att dra nytta av snabba och avancerade skyddsfunktioner.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, moln, blockera vid första anblicken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572063"
---
# <a name="turn-on-cloud-delivered-protection"></a>Aktivera molnbaserat skydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Den Microsoft Defender Antivirus molntjänsten är en mekanism för att leverera uppdaterat skydd till ditt nätverk och punkter. Även om det kallas en molntjänst är det inte bara skydd för filer som lagras i molnet; I stället används distribuerade resurser och maskininlärning för att leverera skydd till dina punkter i en hastighet som är mycket snabbare än traditionella Security Intelligence-uppdateringar.

Microsoft Defender Antivirus använder flera detekterings- och förebyggande tekniker för att leverera korrekt, realtids- och intelligent skydd. [Lär känna de avancerade teknikerna i kärnan av Microsoft Defender för Endpoint nästa generations skydd](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

Du kan aktivera Microsoft Defender Antivirus molnskydd på eller av på flera sätt:

- Microsoft Intune
- Microsoft Endpoint Manager
- Grupprincip
- PowerShell cmdlets.

 Du kan också aktivera eller inaktivera den i enskilda klienter med Windows-säkerhet appen.

Se [Använda Microsofts molnbaserade skydd](cloud-protection-microsoft-defender-antivirus.md) för en översikt över Microsoft Defender Antivirus ett molnskydd.

Mer information om de specifika kraven för nätverksanslutning för att säkerställa att slutpunkterna kan ansluta till den molnbaserade skyddstjänsten finns i [Konfigurera och validera nätverksanslutningar](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> I Windows 10 finns det ingen skillnad mellan alternativen grundläggande **och** **avancerad rapportering som beskrivs** i det här avsnittet. Detta är en äldre distinktion och att välja någon av inställningen kommer att resultera i samma nivå av molnskydd. Det finns ingen skillnad i vilken typ eller mängd information som delas. Mer information om vad vi samlar in finns i [Microsofts sekretesspolicy](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Använd Intune för att aktivera molnskydd

1. Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Enhetskonfiguration** för **enhetsprofiler i > fönstret**.

3. Välj den **profiltyp för** enhetsbegränsningar som du vill konfigurera. Om du behöver skapa en ny **profiltyp för enhetsbegränsningar** kan du [se Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).

4. Välj **inställningar för**  >  **egenskapskonfiguration:** Redigera  >  **Microsoft Defender Antivirus**.

5. Välj Aktivera **på den molnbaserade** skyddsbrytaren. 

6. I **listrutan Fråga användare före exempelöverföring** väljer **du Skicka alla data automatiskt**.

Mer information om Intune-enhetsprofiler, inklusive hur du skapar och konfigurerar deras inställningar, [finns i Microsoft Intune enhetsprofiler?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Använd Microsoft Endpoint Manager för att aktivera molnskydd

1. Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Säkerhets antivirus för**  >  **slutpunkt**.

3. Välj en antivirusprofil. (Om du inte har en ännu eller om du vill skapa en ny profil kan du se [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure).

4. Välj **Egenskaper**. Välj sedan Redigera bredvid  **Konfigurationsinställningar**.

5. Expandera **molnskydd** och välj sedan något av följande i listan **Molnskyddsnivå:**
   - **Hög**: Tillämpar en stark detektionsnivå.
   - **Högt plus:** Använder **hög nivå** och tillämpar ytterligare skyddsåtgärder (kan påverka klientens prestanda).
   - **Nolltolerans**: Blockerar alla okända körbara filer.

6. Välj **Granska + spara** och välj sedan **Spara**.

Mer information om hur du konfigurerar Microsoft Endpoint Configuration Manager finns i [Så här skapar och distribuerar du principer för skadlig kod: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Använd grupprincip för att aktivera molnskydd

1. Öppna konsolen Grupprinciphantering på [grupprinciphanteringskonsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))och högerklicka på det grupprincipobjekt som du vill konfigurera och välj **Redigera**.

2. Gå till **Datorkonfiguration i Redigeraren** **för grupprinciphantering**.

3. Välj **Administrativa mallar**.

4. Expandera trädet **Windows komponenter > Microsoft Defender Antivirus > MAPS**

5. Dubbelklicka **på Gå med i Microsoft MAPS**. Kontrollera att alternativet är aktiverat och inställt på **Grundläggande KARTOR** eller **Avancerade KARTOR**. Välj **OK**.

6. Dubbelklicka **på Skicka filexempel när ytterligare analys krävs**. Kontrollera att det första alternativet är inställt på **Aktiverat** och att de andra alternativen är inställda på antingen:

    1. **Skicka säkra prover** (1)
    2. **Skicka alla prover** (3)

        >[!NOTE]
        > Alternativet **Skicka säkra prover** (1) innebär att de flesta prover skickas automatiskt. Filer som sannolikt innehåller personlig information kommer fortfarande att fråga och kräva ytterligare bekräftelse.
        > Om du ställer in **alternativet Till Fråga** alltid (0) sänks enhetens skyddstillstånd. Om du ställer **in den** på Skicka (2) betyder det att funktionen [Blockera vid](configure-block-at-first-sight-microsoft-defender-antivirus.md) första ögonkastet i Microsoft Defender för slutpunkt inte fungerar.

7. Välj **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Använd PowerShell-cmdlets för att aktivera molnskydd

Följande cmdletar kan aktivera molnskydd:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i [Använda PowerShell-cmdletar för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdletar](/powershell/module/defender/). [Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) har också mer information specifikt om [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Du kan också ställa **in -SubmitSamplesConsent** till `SendSafeSamples` (standardinställningen), `NeverSend` eller `AlwaysPrompt` . Inställningen `SendSafeSamples` innebär att de flesta exempel skickas automatiskt. Filer som sannolikt innehåller personlig information kommer fortfarande att fråga och kräva ytterligare bekräftelse.

>[!WARNING]
> Inställning **-SubmitSamplesConsent** `NeverSend` till eller sänker `AlwaysPrompt` enhetens skyddsnivå. Om du ställer in den `NeverSend` på betyder det dessutom att funktionen Blockera [vid](configure-block-at-first-sight-microsoft-defender-antivirus.md) första ögonkastet i Microsoft Defender för slutpunkt inte fungerar.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Använd Windows Management Instruction (WMI) för att aktivera molnskydd

Använd [ **klassen Set** för **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) för följande egenskaper:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Mer information om tillåtna parametrar finns i [Windows Defender WMIv2 API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Aktivera molnskydd för enskilda klienter med den Windows-säkerhet appen

> [!NOTE]
> Om inställningen **Konfigurera lokal inställning för rapportering av Microsoft MAPS-grupprincipinställning** är inaktiverad **blir** **den molnbaserade** skyddsinställningen i Windows Inställningar nedtonad och otillgänglig. Ändringar som görs via ett grupprincipobjekt måste först distribueras till enskilda slutpunkter innan inställningen uppdateras i Windows-inställningarna.

1. Öppna appen Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka på startmenyn för **Defender**.

2. Välj **viruspanelen & hotskydd** (eller sköldikonen på den vänstra menyraden) **och sedan etiketten Virus & hotskydd:**

    ![Skärmbild på inställningsetiketten för Skydd mot virus och hot i Windows-säkerhetsappen](images/defender/wdav-protection-settings-wdsc.png)

3. Bekräfta att **molnbaserat skydd och** automatisk **provöverföring är** växlade till **På**.

> [!NOTE]
> Om automatisk exempelöverföring har konfigurerats med Grupprincip blir inställningen nedtonad och otillgänglig.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera tidsgräns för blockering i molnet](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Konfigurera block vid första anblicken](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Använd cmdlets från PowerShell för att hantera Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Hjälp till Windows skydda datorer Endpoint Protection för Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender cmdlets](/powershell/module/defender/)
- [Använd Microsofts molnskydd i Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Så här skapar och distribuerar du principer mot skadlig kod: Molnskyddstjänst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
