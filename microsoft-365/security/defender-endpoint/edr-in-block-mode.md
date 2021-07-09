---
title: Identifiering och svar av slutpunkter i blockläge
description: Läs mer identifiering och åtgärd på slutpunkt i blockläge
keywords: Microsoft Defender för Endpoint, mde, Identifiering och åtgärd på slutpunkt i blockeringsläge, blockering av passivt läge
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
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: ae170ecf0fc0f354c9975300e5f2f7cd014b0c47
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339698"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Identifiering och svar av slutpunkt (Identifiering och åtgärd på slutpunkt) i blockeringsläge

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Vad är Identifiering och åtgärd på slutpunkt i blockeringsläge?

[Identifiering och svar av slutpunkt](overview-endpoint-detection-response.md) (Identifiering och åtgärd på slutpunkt) i blockeringsläge ger skydd mot skadliga artefakter, även när Microsoft Defender Antivirus körs i passiv form. När den är Identifiering och åtgärd på slutpunkt blockeras skadliga artefakter eller beteenden som upptäcks på en enhet. Identifiering och åtgärd på slutpunkt i blockeringsläge fungerar bakom kulisserna för att åtgärda skadliga artefakter som upptäcks efter intrånget. 

Identifiering och åtgärd på slutpunkt i blockeringsläge är också integrerat med [& hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md). Din organisations säkerhetsteam kommer att få en säkerhetsrekommendationer [om](tvm-security-recommendation.md) att aktivera Identifiering och åtgärd på slutpunkt i blockeringsläge om det inte redan är aktiverat. 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="rekommendation att aktivera Identifiering och åtgärd på slutpunkt i blockläge":::

> [!NOTE]
> För att få det bästa skyddet bör du distribuera **[Microsoft Defender för slutpunktsbaslinjer](configure-machines-security-baseline.md)**.

## <a name="what-happens-when-something-is-detected"></a>Vad händer när något identifieras?

När Identifiering och åtgärd på slutpunkt i blockeringsläge är aktiverat och en skadlig artefakt upptäcks, blockerar och åtgärdar Microsoft Defender för Slutpunktsblock och åtgärdar artefakten. Ditt team för säkerhetsåtgärder ser identifieringsstatus **som Blockerad** eller **Förhindrad** i Åtgärdscenter , som visas som slutförda åtgärder. [](respond-machine-alerts.md#check-activity-details-in-action-center)

Följande bild visar en instans av oönskad programvara som har upptäckts och blockerats i Identifiering och åtgärd på slutpunkt i blockeringsläge:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="Identifiering och åtgärd på slutpunkt något i blockeringsläge":::


## <a name="enable-edr-in-block-mode"></a>Aktivera Identifiering och åtgärd på slutpunkt i blockeringsläge

> [!IMPORTANT]
> Kontrollera att kraven [uppfylls](#requirements-for-edr-in-block-mode) innan du Identifiering och åtgärd på slutpunkt i blockläge.

1. Gå till [Microsoft 365 Defender och](microsoft-defender-security-center.md) logga in. 

2. Välj **Inställningar**  >  **Avancerade funktioner**.

3. Aktivera Identifiering och åtgärd på slutpunkt **i blockläge**.

> [!NOTE]
> Identifiering och åtgärd på slutpunkt i blockeringsläge kan endast aktiveras i Microsoft 365 Defender portalen. Du kan inte använda registernycklar, Intune eller grupprinciper för att aktivera eller Identifiering och åtgärd på slutpunkt i blockeringsläge.

## <a name="requirements-for-edr-in-block-mode"></a>Krav för Identifiering och åtgärd på slutpunkt i blockläge

|Krav  |Information  |
|---------|---------|
|Behörigheter |Rollen global administratör eller säkerhetsadministratör tilldelad i [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Se [Grundläggande behörigheter.](basic-permissions.md) |
|Operativsystem     |Någon av följande versioner: <br/>- Windows 10 (alla versioner) <br/>- Windows Server, version 1803 eller senare <br/>- Windows Server 2019 <br/>- Windows Server 2016 (endast när Microsoft Defender Antivirus är i aktivt läge)     |
|Windows E5-registrering     |Windows E5 ingår i följande prenumerationer: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 tillsammans med erbjudandet om & och skydd mot hot <br/><br/>Se [Komponenter](/microsoft-365/enterprise/microsoft-365-overview#components) [och funktioner för varje abonnemang.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Microsoft Defender Antivirus  |Microsoft Defender Antivirus måste installeras och köras i antingen aktivt läge eller passivt läge. (Du kan använda Microsoft Defender Antivirus tillsammans med en antiviruslösning som inte är en Microsoft-lösning.) [Kontrollera Microsoft Defender Antivirus är i aktivt eller passivt läge](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode). |
|Molnbaserat skydd |Se till Microsoft Defender Antivirus är konfigurerat så att [moln levererat skydd är aktiverat.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivirus mot skadlig programvara |Kontrollera att din klient är uppdaterad. Med PowerShell kör du [cmdleten Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) som administratör. I **raden AMProductVersion** bör du se **4.18.2001.10** eller högre. |
|Microsoft Defender Antivirus motor |Kontrollera att motorn är uppdaterad. Med PowerShell kör du [cmdleten Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) som administratör. På **raden AMEngineVersion** bör du se **1.1.16700.2** eller högre. |

> [!IMPORTANT]
> För att få bästa möjliga skydd ser du till att antiviruslösningen är konfigurerad för att ta emot regelbundna uppdateringar och viktiga funktioner och att [undantagen är konfigurerade.](configure-exclusions-microsoft-defender-antivirus.md) Identifiering och åtgärd på slutpunkt i blockeringsläge följer undantag som har definierats för Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Måste jag aktivera Identifiering och åtgärd på slutpunkt även när jag har aktiverat Microsoft Defender Antivirus på enheter?

Vi rekommenderar att Identifiering och åtgärd på slutpunkt i blockeringsläge på, oavsett Microsoft Defender Antivirus körs i passiv form eller i aktivt läge. Identifiering och åtgärd på slutpunkt i blockläge ger ytterligare ett skyddslager med Microsoft Defender för Endpoint. Det gör att Defender för Endpoint kan vidta åtgärder baserat på efterbrottsbeteenden Identifiering och åtgärd på slutpunkt identifieringar. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>Kommer Identifiering och åtgärd på slutpunkt i blockeringsläge att ha någon inverkan på en användares antivirusskydd? 

Identifiering och åtgärd på slutpunkt i blockeringsläget påverkar inte antivirusskyddet från tredje part som körs på användarnas enheter. Identifiering och åtgärd på slutpunkt i blockeringsläge fungerar om den primära antiviruslösningen missar något, eller om det finns en identifiering efter intrång. Identifiering och åtgärd på slutpunkt i blockläge fungerar precis som Microsoft Defender Antivirus i passivt läge, förutom att det även blockerar och åtgärdar skadliga artefakter eller beteenden som upptäcks.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Varför måste jag hålla Microsoft Defender Antivirus mig uppdaterad? 

Eftersom Microsoft Defender Antivirus identifierar och åtgärdar skadliga objekt är det viktigt att hålla den uppdaterad. För Identifiering och åtgärd på slutpunkt i blockläge är effektivt används de senaste utbildningsmodellerna för enheter, beteendeidentifiering och heuristik. Defender [för Slutpunkt-stacken](microsoft-defender-endpoint.md) med funktioner fungerar på ett integrerat sätt. För att få bästa möjliga skydd bör du Microsoft Defender Antivirus hålla dig uppdaterad. Se [Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Varför behöver vi molnskydd på? 

Molnskydd krävs för att aktivera funktionen på enheten. Molnskydd gör [att Defender](microsoft-defender-endpoint.md) för Endpoint kan tillhandahålla det senaste och bästa skyddet baserat på vår bredd och djup av säkerhetsinformation, tillsammans med modeller för beteende och enhetsinlärning.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Hur ställer jag in Microsoft Defender Antivirus passivt läge?

När enheter som kör en lösning som inte är en Microsoft-antivirus-/antimalware-lösning förs in i Defender för Endpoint kan Microsoft Defender Antivirus automatiskt gå in i passivt läge. Mer information finns i Hur [Microsoft Defender Antivirus påverkar Defender för Slutpunkt-funktioner.](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Hur bekräftar jag att Microsoft Defender Antivirus i aktivt eller passivt läge?

Om du vill Microsoft Defender Antivirus i aktivt eller passivt läge kan du använda Kommandotolken eller PowerShell på en enhet som kör Windows.


|Metod  |Förfarande  |
|---------|---------|
| PowerShell     | 1. Markera Start-menyn, börja skriva `PowerShell` och öppna Windows PowerShell i resultatet. <p>2. Skriv `Get-MpComputerStatus` . <p>3. Leta efter något av följande värden i resultatlistan på raden **AMRunningMode:** <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Mer information finns i [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Kommandotolken     | 1. Markera Start-menyn, börja skriva `Command Prompt` och öppna Windows kommandotolken i resultatet. <p>2. Skriv `sc query windefend` . <p>3. I resultatlistan, på **raden DELSTAT,** bekräftar du att tjänsten körs.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Hur lång tid tar det för Identifiering och åtgärd på slutpunkt i blockeringsläget att inaktiveras?

Om du väljer att Identifiering och åtgärd på slutpunkt i blockläge kan det ta upp till 30 minuter för systemet att inaktivera den här funktionen.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>Stöds Identifiering och åtgärd på slutpunkt i blockeringsläge på Windows Server 2016?

Om Microsoft Defender Antivirus i aktivt läge eller passivt läge stöds Identifiering och åtgärd på slutpunkt i blockeringsläge av följande versioner av Windows:

- Windows 10 (alla versioner)
- Windows Server, version 1803 eller senare 
- Windows Server 2019 

Om Windows Server 2016 har Microsoft Defender Antivirus i aktivt läge och slutpunkten är onboarded till Defender för Endpoint stöds Identifiering och åtgärd på slutpunkt i blockeringsläge tekniskt. Men funktionen Identifiering och åtgärd på slutpunkt i blockläge är avsedd att vara extra skydd när Microsoft Defender Antivirus inte är den primära antiviruslösningen på en slutpunkt. I sådana fall Microsoft Defender Antivirus i passiv form. För närvarande stöds Microsoft Defender Antivirus i passivt läge inte på Windows Server 2016. Mer information finns i artikeln om Microsoft Defender Antivirus antivirus- och [antimalwarelösningar från Microsoft.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

## <a name="see-also"></a>Mer information finns även i

- [Tech Community-blogg: Identifiering och åtgärd på slutpunkt i blockläge: stoppa attacker i deras spår](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Beteendeblockering och inneslutning](behavioral-blocking-containment.md)

