---
title: Identifiering och svar av slutpunkter i blockläge
description: Läs mer om identifiering av slutpunkter och svar i blockläge
keywords: Microsoft Defender för Endpoint, mde, EDR i blockläge, blockering i passivt läge
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: a2fbb8f1b48dacb27468f8f088f5000da9fcb3b9
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893571"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Identifiering av slutpunkt och svar (EDR) i blockeringsläge

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Vad är EDR i blockläge?

[Identifiering av slutpunkt och svar](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) i blockeringsläge ger skydd mot skadliga artefakter, även när Microsoft Defender Antivirus körs i passiv form. När EDR är aktiverat blockerar EDR i blockläge skadliga artefakter eller beteenden som identifieras på en enhet. EDR i blockläge arbetar bakom kulisserna för att åtgärda skadliga artefakter som upptäcks efter intrånget. 

EDR i blockläge är också integrerat med hot [& sårbarhetshantering](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt). Din organisations säkerhetsteam får en säkerhetsrekommendationer om [att](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) aktivera EDR i blockläge om det inte redan är aktiverat. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="rekommendation att aktivera EDR i blockläge":::

> [!NOTE]
> För att få det bästa skyddet bör du distribuera **[Microsoft Defender för slutpunktsbaslinjer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**.

## <a name="what-happens-when-something-is-detected"></a>Vad händer när något identifieras?

När EDR i blockläge är aktiverat och en skadlig artefakt upptäcks blockerar och åtgärdar Microsoft Defender för Slutpunktsblock och åtgärdar den artefakten. Du ser identifieringsstatus som **Blockerad eller** **Förhindrad som** slutförda åtgärder i [Åtgärdscenter.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)

Följande bild visar en instans av oönskad programvara som har upptäckts och blockerats via EDR i blockeringsläge:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR i blockläge har upptäckt något":::


## <a name="enable-edr-in-block-mode"></a>Aktivera EDR i blockläge

> [!IMPORTANT]
> Se till att [kraven](#requirements-for-edr-in-block-mode) uppfylls innan du slår på EDR i blockläge.

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in. 

2. Välj **Inställningar**  >  **Avancerade funktioner**.

3. Aktivera **EDR i blockläge**.

> [!NOTE]
> EDR i blockeringsläge kan endast aktiveras i Microsoft Defender Säkerhetscenter. Du kan inte använda registernycklar, Intune eller grupprinciper för att aktivera eller inaktivera EDR i blockeringsläge.

## <a name="requirements-for-edr-in-block-mode"></a>Krav för EDR i blockläge

|Krav  |Information  |
|---------|---------|
|Behörigheter |Rollen global administratör eller säkerhetsadministratör tilldelad i [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Se [Grundläggande behörigheter.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Operativsystem     |Någon av följande versioner: <br/>– Windows 10 (alla versioner) <br/>- Windows Server, version 1803 eller senare <br/>- Windows Server 2019         |
|Registrering i Windows E5     |Windows E5 ingår i följande prenumerationer: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 tillsammans med erbjudandet & Identity Protection <br/><br/>Se [Komponenter](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) [och funktioner för varje abonnemang.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus måste installeras och köras i antingen aktivt läge eller passivt läge. (Du kan använda Microsoft Defender Antivirus tillsammans med en antiviruslösning som inte är en Microsoft-lösning.) [Kontrollera att Microsoft Defender Antivirus är i aktivt eller passivt läge](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode). |
|Molnbaserat skydd |Se till att Microsoft Defender Antivirus är konfigurerat så att [moln levererat skydd är aktiverat.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|Microsoft Defender Antivirus-klienten mot skadlig programvara |Kontrollera att din klient är uppdaterad. Med PowerShell kör du [cmdleten Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) som administratör. I **raden AMProductVersion** bör du se **4.18.2001.10** eller högre. |
|Microsoft Defender Antivirus-motor |Kontrollera att motorn är uppdaterad. Med PowerShell kör du [cmdleten Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) som administratör. På **raden AMEngineVersion** bör du se **1.1.16700.2** eller högre. |

> [!IMPORTANT]
> För att få bästa möjliga skydd ser du till att antiviruslösningen är konfigurerad för att ta emot regelbundna uppdateringar och viktiga funktioner och att [undantagen är konfigurerade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) EDR i blockeringsläge tar hänsyn till undantag som har definierats för Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Måste jag aktivera EDR i blockeringsläge även när jag kör Microsoft Defender Antivirus på enheter?

Vi rekommenderar att du håller EDR i blockeringsläge aktiverat, oavsett om Microsoft Defender Antivirus körs i passiv form eller i aktivt läge. EDR i blockläge ger ytterligare ett skyddslager med Microsoft Defender för Endpoint. Det gör att Defender för Endpoint kan vidta åtgärder baserat på EDR-identifiering efter intrång. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Kommer EDR i blockläge att ha någon inverkan på en användares antivirusskydd? 

EDR i blockeringsläge påverkar inte antivirusskyddet från tredje part som körs på användarnas enheter. EDR i blockeringsläge fungerar om den primära antiviruslösningen missar något, eller om det finns en identifiering efter intrång. EDR i blockläge fungerar precis som [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)i passiv form , förutom att det även blockerar och åtgärdar skadliga artefakter eller beteenden som upptäcks. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Varför måste jag hålla Microsoft Defender Antivirus uppdaterat? 

Eftersom Microsoft Defender Antivirus identifierar och åtgärdar skadliga objekt är det viktigt att hålla det uppdaterat. För att EDR i blockläge ska vara effektivt används de senaste utbildningmodellerna för enheter, beteendeidentifiering och heuristik. Defender [för Slutpunkt-stacken](https://docs.microsoft.com/windows/security/threat-protection) med funktioner fungerar på ett integrerat sätt. För att få bästa möjliga skydd ska du hålla Microsoft Defender Antivirus uppdaterat.  

### <a name="why-do-we-need-cloud-protection-on"></a>Varför behöver vi molnskydd på? 

Molnskydd krävs för att aktivera funktionen på enheten. Molnskydd gör [att Defender](https://docs.microsoft.com/windows/security/threat-protection) för Endpoint kan tillhandahålla det senaste och bästa skyddet baserat på vår bredd och djup av säkerhetsinformation, tillsammans med modeller för beteende och enhetsinlärning.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hur ställer jag in Microsoft Defender Antivirus på passiv form?

Se [Aktivera Microsoft Defender Antivirus och bekräfta att det är i passivt läge.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hur bekräftar jag att Microsoft Defender Antivirus är i aktivt eller passivt läge?

Om du vill kontrollera om Microsoft Defender Antivirus körs i aktivt eller passivt läge kan du använda Kommandotolken eller PowerShell på en enhet med Windows.

#### <a name="use-powershell"></a>Använda PowerShell

1. Välj Start-menyn, börja `PowerShell` skriva och öppna sedan Windows PowerShell i resultatet.

2. Typ `Get-MpComputerStatus`.

3. Leta efter något av följande värden i resultatlistan på raden **AMRunningMode:**   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

Mer information finns i [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).

#### <a name="use-command-prompt"></a>Använda Kommandotolken

1. Välj Start-menyn, börja skriva `Command Prompt` och öppna sedan Windows Kommandotolken i resultatet.

2. Typ `sc query windefend`.

3. I resultatlistan, på raden **DELSTAT,** bekräftar du att tjänsten körs.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hur mycket tid tar det för EDR i blockläge att inaktiveras?
Om du väljer att inaktivera EDR i blockläge kan det ta upp till 30 minuter för systemet att inaktivera den här funktionen.

## <a name="see-also"></a>Se även

- [Tech Community-blogg: Introduktion till EDR i blockläge: Stoppa attacker i deras spår](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Beteendeblockering och inneslutning](behavioral-blocking-containment.md)
- [Bättre tillsammans: Microsoft Defender Antivirus och Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

