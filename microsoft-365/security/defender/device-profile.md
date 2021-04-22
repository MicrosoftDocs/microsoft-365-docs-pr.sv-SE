---
title: Enhetsprofil i Microsoft 365-säkerhetsportalen
description: Visa risk- och exponeringsnivåer för en enhet i organisationen. Analysera tidigare och aktuella hot och skydda enheten med de senaste uppdateringarna.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, Microsoft 365 Defender, säkerhetscenter, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365, Microsoft Defender för identitet, enhetssida, enhetsprofil, datorsida, datorprofil
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 8e2788fd9163a27b41bd3788facf5fc9623b0543
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935671"
---
# <a name="device-profile-page"></a>Profilsida för enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


På Microsoft 365-säkerhetsportalen finns profilsidor för enheter, så att du snabbt kan bedöma status och status för enheter i nätverket.

> [!IMPORTANT]
> Sidan med enhetsprofilen kan se något annorlunda ut beroende på om enheten är registrerad i Microsoft Defender för Slutpunkt, Microsoft Defender för identitet eller båda.

Om enheten är registrerad i Microsoft Defender för Endpoint kan du också använda sidan med enhetsprofilen för att utföra några vanliga säkerhetsuppgifter.

## <a name="navigating-the-device-profile-page"></a>Navigera på enhetens profilsida

Profilsidan är uppdelad i flera breda avsnitt.

![Bild av enhetens profilsida med (1) tabbområde (2) sidofält och (3) åtgärder markerade i rött](../../media/mtp-device-profile/hybrid-device-overall.png)

I sidofältet (1) finns grundläggande information om enheten.

Huvudinnehållsområdet (2) innehåller flikar som du kan växla mellan för att visa olika typer av information om enheten.

Om enheten är registrerad i Microsoft Defender för Endpoint visas även en lista över svarsåtgärder (3). Med svarsåtgärder kan du utföra vanliga säkerhetsrelaterade uppgifter.

## <a name="sidebar"></a>Sidofält

Bredvid huvudinnehållsområdet på sidan med enhetsprofilen finns sidofältet.

![Bild av fliken sidofält för enhetsprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

I sidofältet visas enhetens fullständiga namn och exponeringsnivå. Den innehåller även viktig grundläggande information i små avsnitt som kan vara öppna eller stängda, till exempel:

* **Taggar** – Alla Microsoft Defender för Slutpunkt, Microsoft Defender för identitet eller anpassade taggar som är kopplade till enheten. Taggar från Microsoft Defender för identitet kan inte redigeras.
* **Säkerhetsinformation** – Öppna incidenter och aktiva aviseringar. Enheter som är registrerade i Microsoft Defender för Endpoint visar också exponeringsnivå och risknivå.

> [!TIP]
> Exponeringsnivån relaterar till hur mycket enheten uppfyller säkerhetsrekommendationer, medan risknivån beräknas utifrån ett antal faktorer, inklusive typer och allvarlighetsgrad för aktiva varningar.

* **Enhetsinformation** – domän, OS, tidsstämpel för när enheten först sågs, IP-adresser, resurser. Enheter som är registrerade i Microsoft Defender för Endpoint visar även hälsotillstånd. Enheter som är registrerade i Microsoft Defender för identitet visar SAM-namn och en tidsstämpel för när enheten skapades första gången.
* **Nätverksaktivitet** – Tidsstämplar för första och senaste gången enheten sågs i nätverket.
* **Katalogdata** (*endast för enheter som är registrerade i Microsoft Defender för* identitet) – [UAC-flaggor,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPN:er](/windows/win32/ad/service-principal-names)och gruppmedlemskap.

## <a name="response-actions"></a>Svarsåtgärder

Svarsåtgärder är ett snabbt sätt att försvara sig mot och analysera hot.

![Bild av åtgärdsfältet för enhetsprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Svarsåtgärder](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) är bara tillgängliga om enheten är registrerad i Microsoft Defender för Endpoint.
> * Enheter som är registrerade i Microsoft Defender för Endpoint kan visa olika antal svarsåtgärder, baserat på enhetens operativsystem och versionsnummer.

Åtgärder som är tillgängliga på sidan med enhetsprofilen är:

* **Hantera taggar** – Uppdaterar anpassade taggar som du har tillämpat på den här enheten.
* **Identifiera enhet** – Isolerar enheten från organisationens nätverk samtidigt som den håller den ansluten till Microsoft Defender för Slutpunkt. Du kan välja att tillåta att Outlook, Teams och Skype för företag körs medan enheten isoleras, i kommunikationssyfte.
* **Åtgärdscenter** – visa status för skickade åtgärder. Endast tillgängligt om en annan åtgärd redan har markerats.
* **Begränsa programkörning** – Förhindrar att program som inte är signerade av Microsoft körs.
* **Kör antivirussökning** – Uppdaterar definitioner för Windows Defender Antivirus och kör omedelbart en antivirussökning. Välj mellan Snabbsökning eller Fullständig sökning.
* **Paket för insamling** av undersökning – samlar in information om enheten. När undersökningen är klar kan du ladda ned den.
* **Initiera Live Response-session** – Läser in ett fjärrgränssnitt på enheten [för ingående säkerhetsundersökning.](/microsoft-365/security/defender-endpoint/live-response)
* **Initiera automatisk undersökning** – [undersöker och åtgärdar automatiskt hot.](../office-365-security/office-365-air.md) Även om du manuellt kan utlösta automatiska undersökningar från den här sidan [utlöser](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) vissa aviseringsprinciper automatiska undersökningar på egen hand.
* **Åtgärdscenter** – Visar information om alla svarsåtgärder som körs för närvarande.

## <a name="tabs-section"></a>Avsnittet Flikar

Med flikarna för enhetsprofilen kan du växla mellan en översikt över säkerhetsinformation om enheten och tabeller som innehåller en lista med aviseringar.

Enheter som är registrerade i Microsoft Defender för Endpoint visar även flikar som innehåller en tidslinje, en lista med säkerhetsrekommendationer, en inventering av programvara, en lista över identifierade säkerhetsproblem och saknade KBs (säkerhetsuppdateringar).

### <a name="overview-tab"></a>Fliken Översikt

Standardfliken är **Översikt.** Den ger en snabb översikt över den viktigaste säkerhets information om enheten.

![Bild av översiktsfliken för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Här kan du snabbt se enhetens aktiva aviseringar och inloggade användare.

Om enheten är registrerad i Microsoft Defender för Endpoint visas även enhetens risknivå och alla tillgängliga data om säkerhetsutvärderingar. Säkerhetsutvärderingarna beskriver enhetens exponeringsnivå, ger säkerhetsrekommendationer och listar påverkade program samt upptäckta svagheter.

### <a name="alerts-tab"></a>Fliken Aviseringar

Fliken **Aviseringar** innehåller en lista med aviseringar som har höjts på enheten från både Microsoft Defender för identitet och Microsoft Defender för slutpunkt.

![Bild på fliken Aviseringar för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Du kan anpassa antalet objekt som visas och vilka kolumner som visas för varje objekt. Standardbeteendet är att lista trettio objekt per sida.

Kolumnerna på den här fliken innehåller information om allvarlighetsgraden för det hot som utlöste aviseringen, samt status, undersökningsstatus och vem aviseringen har tilldelats.

Kolumnen *påverkade enheter* refererar till den enhet (entitet) vars profil du visar för närvarande, plus alla andra enheter i nätverket som påverkas.

Om du väljer ett objekt i den här listan öppnas en utfällande meny som innehåller ännu mer information om den markerade aviseringen.

Listan kan filtreras efter allvarlighetsgrad, status eller vem aviseringen har tilldelats.

### <a name="timeline-tab"></a>Fliken Tidslinje

Fliken **Tidslinje** innehåller ett interaktivt, kronologiskt diagram över alla händelser upphöjda på enheten. Genom att flytta det markerade området i diagrammet åt vänster eller höger kan du visa händelser över olika tidsperioder. Du kan också välja ett anpassat datumintervall i den nedrullningsbara menyn mellan det interaktiva diagrammet och listan med händelser.

Under diagrammet finns en lista med händelser för det valda datumintervallet.

![Bild av fliken Tidslinje för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

Både antalet objekt som visas och kolumnerna i listan kan anpassas. I standardkolumnerna visas händelsetiden, aktiv användare, åtgärdstyp, enheter (processer) och ytterligare information om händelsen.

Om du väljer ett objekt i den här listan öppnas en utfällningslistebild som visar diagrammet Händelseenheter, som visar de överordnade och underordnade processerna som ingår i händelsen.

Listan kan filtreras efter den specifika typen av händelse. Till exempel registerhändelser eller smartskärmshändelser.

Listan kan också exporteras till en CSV-fil för nedladdning. Även om filen inte begränsas av antalet händelser är det maximala intervallet du kan välja att exportera sju dagar.

### <a name="security-recommendations-tab"></a>Fliken Säkerhetsrekommendationer

Fliken **Säkerhetsrekommendationer** innehåller åtgärder du kan vidta för att skydda enheten. Om du väljer ett objekt i den här listan öppnas en utfällad meny där du hittar anvisningar om hur du använder rekommendationen.

![Bild av fliken säkerhetsrekommendationer för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Precis som på föregående flikar går det att anpassa antalet objekt som visas per sida och vilka kolumner som är synliga.

Standardvyn innehåller kolumner som beskriver säkerheten, det associerade hotet, den relaterade komponent eller programvara som påverkas av hotet och mycket mer. Objekt kan filtreras efter rekommendationens status.

### <a name="software-inventory"></a>Programvaruinventering

På **fliken För inventering** av programvara visas programvara som är installerad på enheten.

![Bild på fliken för programvaruinventering för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

I standardvyn visas programvaruleverantören, installerat versionsnummer, antal kända programvaruinsikter, hotinsikter, produktkod och taggar. Antalet objekt som visas och vilka kolumner som visas kan båda anpassas.

Om du väljer ett objekt från den här listan öppnas en utfällning med mer information om den valda programvaran samt sökväg och tidsstämpel för den senaste gången programvaran hittades.

Den här listan kan filtreras efter produktkod.

### <a name="discovered-vulnerabilities-tab"></a>Flik för upptäckta säkerhetsproblem

På **fliken Identifierade säkerhetsproblem** visas eventuella vanliga säkerhetsproblem och sårbarheter (CVEs) som kan påverka enheten.

![Bild av fliken för identifierade säkerhetsproblem för enhetsprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

I standardvyn visas allvarlighetsgraden för CVE, Common Vulnerability Score (CVS), programvaran relaterad till CVE, när CVE publicerades, när CVE uppdaterades senast och hot kopplade till CVE.

Precis som på föregående flikar kan du anpassa antalet objekt som visas och vilka kolumner som är synliga.

Om du väljer ett objekt i den här listan öppnas en utfällning som beskriver CVE.

### <a name="missing-kbs"></a>Saknade KBs

På **fliken Saknade KB** visas alla Microsoft-uppdateringar som ännu inte har tillämpats på enheten. De "KBs" som är i fråga [är Knowledge Base-artiklar](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) som beskriver dessa uppdateringar. till exempel [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Bild på fliken kbs som saknas för enhetsprofilen](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

I standardvyn visas anslagsbulletin som innehåller uppdateringarna, OS-versionen, berörda produkter, cv:er som är adresserade, KB-nummer och taggar.

Antalet objekt som visas per sida och vilka kolumner som visas kan anpassas.

Om du markerar ett objekt öppnas en utfällblad som länkar till uppdateringen.

## <a name="related-topics"></a>Relaterade ämnen

* [Översikt över Microsoft 365 Defender](microsoft-365-defender.md)
* [Aktivera Microsoft 365 Defender](m365d-enable.md)
* [Undersök enheter på enheter med hjälp av live-svar](../defender-endpoint/live-response.md)
* [Automatiserad undersökning och svar (AIR) i Office 365](../office-365-security/office-365-air.md)
