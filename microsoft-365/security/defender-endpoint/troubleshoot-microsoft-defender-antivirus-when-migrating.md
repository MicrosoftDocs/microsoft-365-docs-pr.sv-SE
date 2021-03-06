---
title: Felsök Microsoft Defender Antivirus när du migrerar från en lösning från tredje part
description: Felsöka vanliga fel vid migrering till Microsoft Defender Antivirus
keywords: händelse, felkod, loggning, felsökning, microsoft defender antivirus, windows defender antivirus, migrering
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924389"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Felsök Microsoft Defender Antivirus när du migrerar från en lösning från tredje part

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)


Du hittar hjälp här om du stöter på problem när du migrerar från en säkerhetslösning från tredje part till Microsoft Defender Antivirus.

## <a name="review-event-logs"></a>Granska händelseloggar

Öppna appen Loggboken genom att välja **sökikonen** i Aktivitetsfältet och söka efter *loggboken*.

Information om Microsoft Defender Antivirus finns under **Program- och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **Windows Defender.** 

Därifrån väljer du **Öppna** under **Drift**.

Om du väljer en händelse i informationsfönstret visas mer information om en händelse i det nedre fönstret, under **flikarna Allmänt** **och** Information.

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivirus startar inte

Det här problemet kan visa sig i form av flera olika händelse-ID, som alla har samma underliggande orsak.

### <a name="associated-event-ids"></a>Associerade händelse-ID

 Händelse-ID | Loggnamn | Beskrivning | Source
-|-|-|-
15 | Program | Uppdaterade Windows Defender statusen för att SECURITY_PRODUCT_STATE_OFF. | Säkerhetscenter
5007 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus Konfigurationen har ändrats.  Om det är en oväntad händelse bör du granska inställningarna eftersom det kan vara resultatet av skadlig programvara.<br /><br />**Gammalt värde:** Default\IsServiceRunning = 0x0<br />**Nytt värde:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Windows Defender Antivirus för spionprogram och annan potentiellt oönskad programvara inaktiveras. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Så här ser du Microsoft Defender Antivirus antivirusprogrammet inte startar eftersom ett antivirusprogram från tredje part är installerat

Om du Windows 10 Microsoft Defender för Endpoint på en Windows 10 enhet och du har ett antivirus installerat från tredje part inaktiveras Microsoft Defender Antivirus automatiskt. Om du använder Microsoft Defender för Endpoint med ett antivirus installerat från tredje Microsoft Defender Antivirus att starta i passiv form, med nedsatt funktionalitet.

> [!TIP]
> Det scenario som beskrivs ovan gäller endast för Windows 10. Andra versioner av Windows har [olika svar på](microsoft-defender-antivirus-compatibility.md) Microsoft Defender Antivirus som körs tillsammans med säkerhetsprogramvara från tredje part.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Använda appen Tjänster för att kontrollera Microsoft Defender Antivirus är inaktiverat

Öppna appen Tjänster genom att välja **sökikonen** i Aktivitetsfältet och söka efter *tjänster.* Du kan också öppna appen från kommandoraden genom att skriva *services.msc.*

Information om Microsoft Defender Antivirus listas i services-appen under **drift Windows Defender**  >  **Drift.** Antivirustjänstens namn är *Windows Defender Antivirus tjänsten.*

När du kontrollerar appen kan det hända att *Windows Defender Antivirus-tjänsten* är inställd på manuell , men när du försöker starta den här tjänsten manuellt får du ett varningsmeddelande om att Windows Defender Antivirus-tjänsten på den lokala datorn har startats och *stoppats. Vissa tjänster stoppas automatiskt om de inte används av andra tjänster eller program.*

Det innebär att Microsoft Defender Antivirus har inaktiverats automatiskt för att bevara kompatibiliteten med ett antivirusprogram från tredje part.

#### <a name="generate-a-detailed-report"></a>Skapa en detaljerad rapport

Du kan generera en detaljerad rapport om för närvarande  aktiva gruppprinciper genom att öppna en kommandotolk i läget Kör som administratör och sedan ange följande kommando:

```powershell
GPresult.exe /h gpresult.html
```

En rapport som finns på *./gpresult.html* skapas. Öppna den här filen så kan du se följande resultat, beroende på hur Microsoft Defender Antivirus var inaktiverat.

##### <a name="group-policy-results"></a>Grupprincipresultat

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Om säkerhetsinställningarna implementeras via grupprincip (GPO) på domännivå eller lokal nivå, eller via System Center Configuration Manager (SCCM)

I gpResults-rapporten, under rubriken *Windows Components/Windows Defender Antivirus,* kanske du ser något i enlighet med följande post, som anger att Microsoft Defender Antivirus är inaktiverat.

Princip | Inställning | Vinnande GPO
-|-|-
Inaktivera Windows Defender Antivirus | Aktiverad | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Om säkerhetsinställningarna implementeras via grupprincipinställning (GPP)

Under rubriken Registerobjekt *(Nyckelsökväg: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Värdenamn: DisableAntiSpyware)* kan det se ut ungefär så här, som visar att Microsoft Defender Antivirus är inaktiverat.

DisableAntiSpyware | -
-|-
Vinnande GPO | Win10-Workstations
Resultat: Lyckades | 
**Allmänt** | 
Åtgärd | Update
**Egenskaper** | 
Registreringsdatafil | HKEY_LOCAL_MACHINE
Nyckelsökväg | SOFTWARE\Policies\Microsoft\Windows Defender
Värdenamn | DisableAntiSpyware
Värdetyp | REG_DWORD
Värdedata | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Om säkerhetsinställningarna implementeras via registernyckeln

Rapporten kan innehålla följande text, som anger att Microsoft Defender Antivirus är inaktiverat:
 
> Register (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Om säkerhetsinställningarna anges i Windows eller i Windows Serveravbildningen

Den imaginära administratören kan ha angett säkerhetsprincipen **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, lokalt via *GPEdit.exe*, *LGPO.exe* eller genom att ändra registret i aktivitetssekvensen. Du kan [konfigurera en betrodd bildidentifierare](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) för Microsoft Defender Antivirus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Aktivera Microsoft Defender Antivirus igen

Microsoft Defender Antivirus att aktiveras automatiskt om inget annat antivirusprogram är aktivt. Du måste inaktivera antivirusprogrammet från tredje part helt för att säkerställa att Microsoft Defender Antivirus kan köras med fullständiga funktioner.

> [!WARNING]
> Lösningar som föreslår  att du redigerar Windows Defender-startvärdena för *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* och *windefend* i HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services stöds inte och kan tvinga dig att avbildninga systemet igen.

Passiv form är tillgängligt om du börjar använda Microsoft Defender för Endpoint och ett antivirus från tredje part tillsammans med Microsoft Defender Antivirus. Med passivt läge kan Microsoft Defender söka igenom filer och uppdatera sig själv, men det åtgärdar inte hot. Dessutom är inte övervakning av beteende via [realtidsskydd](configure-real-time-protection-microsoft-defender-antivirus.md) tillgängligt under passivt läge, om inte [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) har distribuerats.

En annan funktion, som [kallas begränsad regelbunden](limited-periodic-scanning-microsoft-defender-antivirus.md)genomsökning, är tillgänglig för slutanvändare när Microsoft Defender Antivirus är inställd på att inaktiveras automatiskt. Med den här Microsoft Defender Antivirus du söka igenom filer regelbundet tillsammans med ett antivirusprogram från tredje part med ett begränsat antal identifieringar.

> [!IMPORTANT]
> Begränsad regelbunden genomsökning rekommenderas inte i företagsmiljöer. De funktioner för identifiering, hantering och rapportering som är tillgängliga när Microsoft Defender Antivirus i det här läget minskar jämfört med aktivt läge.

### <a name="see-also"></a>Se även

* [Microsoft Defender Antivirus kompatibilitet](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivirus i Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md)