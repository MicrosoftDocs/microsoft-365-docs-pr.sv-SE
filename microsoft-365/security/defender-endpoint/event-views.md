---
title: Visa händelser för minskning av attackytan
description: Importera anpassade vyer för att se minskningar av attackytor.
keywords: händelsevy, sårbarhetsskydd, granskning, granskning, händelser
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0a2ec16685ede2e625528fc3944943923bba3fc9
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51569749"
---
# <a name="view-attack-surface-reduction-events"></a>Visa händelser för minskning av attackytan

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Granska händelser för att minska attackytan i Loggboken för att övervaka vilka regler eller inställningar som fungerar. Du kan också bestämma om några inställningar är för "bullriga" eller påverkar det dagliga arbetsflödet.

Det kan vara användbart att granska händelser när du utvärderar funktionerna. Du kan aktivera granskningsläge för funktioner eller inställningar och sedan granska vad som skulle ha hänt om de var aktiverade.

Den här artikeln innehåller alla händelser, deras associerade funktion eller inställning och beskriver hur du skapar anpassade vyer för att filtrera efter specifika händelser.

Få detaljerad rapportering om händelser och block som en del av Windows-säkerhet om du har en E5-prenumeration och använder [Microsoft Defender för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Använda anpassade vyer för att granska funktioner för att minska attackytan

Skapa anpassade vyer i Windows loggboken för att bara visa händelser för specifika funktioner och inställningar. Det enklaste sättet är att importera en anpassad vy som en XML-fil. Du kan kopiera XML-koden direkt från den här sidan.

Du kan också manuellt navigera till det händelseområde som motsvarar funktionen.

### <a name="import-an-existing-xml-custom-view"></a>Importera en befintlig ANPASSAD XML-vy

1. Skapa en tom TXT-fil och kopiera XML-koden för den anpassade vyn som du vill använda till TXT-filen. Gör så här för var och en av de anpassade vyer som du vill använda. Byt namn på filerna på följande sätt (kontrollera att du ändrar typen från .txt till .xml):
    - Kontrollerad mappåtkomsthändelser, anpassad vy: *cfa-events.xml*
    - Den anpassade vyn för sårbarhetsskyddshändelser: *ep-events.xml*
    - Anpassad vy för minskning av attackytor: *asr-events.xml*
    - Anpassad vy för nätverks- och skyddshändelser: *np-events.xml*

2. Skriv **händelsevisare** på Start-menyn och öppna **Loggboken**.

3. Välj **Anpassad**  >  **vy för åtgärdsimport...**

    ![Animeringsmarkering Importera anpassad vy till vänster om fönstret Jämn visningsprogram](/windows/security/threat-protection/images/events-import)

4. Gå till den plats där du extraherade XML-filen för den anpassade vy du vill använda och markera den.

5. Välj **Öppna**.

6. Den skapar en anpassad vy som filtrerar för att bara visa händelser relaterade till den funktionen.

### <a name="copy-the-xml-directly"></a>Kopiera XML direkt

1. Skriv **händelsevisare** på Start-menyn och öppna Windows **loggboken.**

2. I den vänstra panelen under **Åtgärder väljer** du Skapa **anpassad vy...**

    ![Animering som markerar alternativet Skapa anpassad vy i fönstret Loggboken](/windows/security/threat-protection/images/events-create)

3. Gå till fliken XML och välj **Redigera fråga manuellt**. Ett varningsmeddelande visas om att du inte kan redigera frågan med hjälp av **fliken Filter** om du använder alternativet XML. Välj **Ja**.

4. Klistra in XML-koden för den funktion du vill filtrera händelser från i XML-avsnittet.

5. Välj **OK**. Ange ett namn för filtret.

6. Den skapar en anpassad vy som filtrerar för att bara visa händelser relaterade till den funktionen.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML för händelser för attackytans minskningsregel

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML för styrda mappåtkomsthändelser

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML för sårbarhetsskyddshändelser

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML för nätverksskyddshändelser

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Lista över minskningar av attackytor

Alla minskningar av attackytor finns under Program- och tjänstloggar **> Microsoft > Windows** och sedan mappen eller leverantören som anges i följande tabell.

Du kan komma åt dessa händelser i Windows händelsevisare:

1. Öppna **Start-menyn,** skriv **loggboken** och välj sedan **resultatet för Loggboken.**
2. Expandera **Loggar för program och tjänster > Microsoft > Windows** och gå sedan till mappen som visas under **Leverantör/källa** i tabellen nedan.
3. Dubbelklicka på underobjektet för att visa händelser. Bläddra igenom händelserna för att hitta den du letar efter.

   ![Animering som visar hur du använder Loggboken](/windows/security/threat-protection/images/event-viewer)

Funktion | Leverantör/källa | Händelse-ID | Beskrivning
:-|:-|:-:|:-
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 1 | ACG-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 2 | ACG- enforce
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 3 | Tillåt inte granskning av underordnade processer
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 4 | Tillåt inte blockering av underordnade processer
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 5 | Blockera bilder med låg integritet
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 6 | Blockera bilder med låg integritet
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 7 | Blockera fjärrbildergranskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 8 | Blockera fjärrbilderblock
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 9 | Inaktivera granskning av win32k-systemsamtal
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 10 | Inaktivera win32k-systemsamtalsblockering
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 11 | Kodintegritetsskyddsgranskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 12 | Kodintegritetsskyddsblock
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 13 | EAF-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 14 | EAF-framtvinga
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 15 | EAF+-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 16 | EAF+ framtvinga
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 17 | IAF-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 18 | IAF-framtvinga
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 19 | ROP StackPivot-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 20 | ROP StackPivot-rop-rop
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 21 | ROP-callerCheck-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 22 | ROP-anropskontrollera
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 23 | ROP SimExec-granskning
Exploateringsskydd | Security-Mitigations (Kernel-läge/användarläge) | 24 | ROP SimExec-framtvinga
Exploateringsskydd | WER-Diagnostics | 5 | CFG-block
Exploateringsskydd | Win32K (drift) | 260 | Teckensnitt som inte är betrodd
Nätverksskydd | Windows Defender (drift) | 5007 | Händelse när inställningar ändras
Nätverksskydd | Windows Defender (drift) | 1125 | Händelse när nätverksskydd aktiveras i granskningsläge
Nätverksskydd | Windows Defender (drift) | 1126 | Händelse när nätverksskydd aktiveras i blockläge
Kontrollerad mappåtkomst | Windows Defender (drift) | 5007 | Händelse när inställningar ändras
Kontrollerad mappåtkomst | Windows Defender (drift) | 1124 | Granskad reglerad mappåtkomsthändelse
Kontrollerad mappåtkomst | Windows Defender (drift) | 1123 | Händelse för blockerad reglerad mappåtkomst
Kontrollerad mappåtkomst | Windows Defender (drift) | 1127 | Skrivblockshändelse för blockerad reglerad mappåtkomstsektor
Kontrollerad mappåtkomst | Windows Defender (drift) | 1128 | Kontrollerad skrivningsblockshändelse för mappåtkomstsektor granskad
Minska attackytan | Windows Defender (drift) | 5007 | Händelse när inställningar ändras
Minska attackytan | Windows Defender (drift) | 1122 | Händelse när en regel aktiveras i granskningsläge
Minska attackytan | Windows Defender (drift) | 1121 | Händelse när en regel ut sätts i blockläge
