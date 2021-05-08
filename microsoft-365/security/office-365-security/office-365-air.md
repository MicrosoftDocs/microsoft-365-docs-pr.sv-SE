---
title: Automatisk undersökning och svar i Microsoft Defender för Office 365
keywords: AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Kom igång med automatisk undersökning och svarsfunktioner i Microsoft Defender för Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c9cd9ef649ec60fc8d880ae525469980a00f69b2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275006"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatisk undersökning och svar (AIR) i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender för Office 365](defender-for-office-365.md) innehåller kraftfulla funktioner för automatisk undersökning och svar (AIR) som kan spara tid och arbete för dina säkerhetsåtgärder. När aviseringar utlöses är det upp till ditt säkerhetsteam att granska, prioritera och svara på dessa aviseringar. Det kan vara överväldigande att hålla koll på mängden inkommande aviseringar. Att automatisera vissa av dessa uppgifter kan vara till hjälp.

AIR gör att ditt säkerhetsteam kan samarbeta mer effektivt. AIR-funktioner omfattar automatiserade undersökningsprocesser som svar på välkända hot som finns idag. Lämpliga åtgärdsåtgärder väntar på godkännande, vilket gör det möjligt för teamet med säkerhetsåtgärder att agera effektivt mot identifierade hot. Med AIR kan ditt säkerhetsteam fokusera på uppgifter med högre prioritet utan att viktiga aviseringar som utlöses går förlorade.

I den här artikeln beskrivs:

- Det [övergripande flödet av AIR](#the-overall-flow-of-air);
- [Skaffa AIR](#how-to-get-air); och
- Behörighet [som krävs för](#required-permissions-to-use-air-capabilities) att konfigurera eller använda AIR-funktioner.
- Ändringar som kommer snart till ditt säkerhetscenter

Den här artikeln innehåller [även nästa steg](#next-steps), och resurser för mer information.

## <a name="the-overall-flow-of-air"></a>Den övergripande flödet av AIR

En avisering utlöses och en säkerhetsspelbok startar en automatiserad undersökning, som resulterar i resultat och rekommenderade åtgärder. Här är det övergripande flödet av AIR, steg för steg:

1. En automatiserad undersökning initieras på något av följande sätt:
   - Antingen [utlöses en avisering](#which-alert-policies-trigger-automated-investigations) av något misstänkt i e-postmeddelanden (t.ex. ett meddelande, en bifogad fil, en URL eller ett komprometterat användarkonto). En incident skapas och en automatisk undersökning påbörjas. eller
   - En säkerhetsanalytiker startar [en automatiserad undersökning med hjälp](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) av Threat [Explorer.](threat-explorer.md)
2. Även om en automatiserad undersökning körs samlar den in data om e-postmeddelandet i fråga och enheter relaterade till e-postmeddelandet. Sådana enheter kan inkludera filer, URL:er och mottagare. Undersökningens omfattning kan öka allt eftersom nya och relaterade aviseringar utlöses.
3. Under och efter en automatiserad undersökning [finns information och](air-view-investigation-results.md) resultat tillgängliga att visa. Resultaten omfattar [rekommenderade](air-remediation-actions.md) åtgärder som kan vidtas för att svara på och åtgärda eventuella hot som hittades.
4. Din säkerhetsgrupp granskar [undersökningsresultatet och rekommendationerna](air-view-investigation-results.md) [och godkänner eller avvisar åtgärder.](air-review-approve-pending-completed-actions.md)
5. När väntande åtgärder godkänns (eller avvisas) slutförs den automatiska undersökningen.

I Microsoft Defender Office 365 åtgärder vidtas inga åtgärder automatiskt. Åtgärdsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam. AIR-funktioner sparar din grupptid för säkerhetsåtgärder genom att identifiera åtgärdsåtgärder och tillhandahålla den information som behövs för att fatta ett välgrundat beslut.

Under och efter varje automatisk undersökning kan ditt säkerhetsteam:

- [Visa information om en avisering relaterad till en undersökning](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Visa resultatinformation för en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)
- [Granska och godkänna åtgärder som ett resultat av en undersökning](air-review-approve-pending-completed-actions.md)

> [!TIP]
> En mer detaljerad översikt finns i Hur [AIR fungerar.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Skaffa AIR

AIR-funktionerna ingår i [Microsoft Defender för Office 365,](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)förutsatt att dina principer och aviseringar har konfigurerats. Behöver du hjälp? Följ instruktionerna i [Skydda mot hot för](protect-against-threats.md) att konfigurera eller konfigurera följande skyddsinställningar:

- [Granskningsloggning](../../compliance/turn-audit-log-search-on-or-off.md) (ska aktiveras)
- [Principer för program mot skadlig programvara](protect-against-threats.md#part-1---anti-malware-protection)
- [Skydd mot virus](protect-against-threats.md#part-2---anti-phishing-protection)
- [Skydd motspam](protect-against-threats.md#part-3---anti-spam-protection)
- [Valv Länkar och Valv bilagor](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Automatisk rensning utan timme för e-post](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Dessutom bör du granska [organisationens aviseringsprinciper,](../../compliance/alert-policies.md)särskilt [standardprinciperna i kategorin Hothantering.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Vilka aviseringsprinciper utlöser automatiska undersökningar?

Microsoft 365 innehåller många inbyggda aviseringsprinciper som hjälper till att identifiera missbruk av Exchange administratörsbehörighet, skadlig programvara, potentiella externa och interna hot samt informationsstyrningsrisker. Flera av [standardaviseringsprinciperna](../../compliance/alert-policies.md#default-alert-policies) kan utlösa automatiska undersökningar. I följande tabell beskrivs aviseringarna som utlöser automatiska undersökningar, deras allvarlighetsgrad i Microsoft 365 säkerhetscenter och hur de genereras:

|Varning|Allvarlighetsgrad|Så här genereras aviseringen|
|---|---|---|
|Ett potentiellt skadligt URL-klick upptäcktes|**Hög**|Den här aviseringen genereras när något av följande inträffar: <ul><li>En användare som skyddas [Valv organisationens](safe-links.md) länkar klickar på en skadlig länk</li><li>Ändringar av bedömning av webbadresser identifieras av Microsoft Defender för Office 365</li><li>Användarna åsidosätter Valv länkar till varningssidor (baserat på organisationens [Valv Länkar).](set-up-safe-links-policies.md)</li></ul> <p> Mer information om händelser som utlöser den här aviseringen finns [i Konfigurera Valv principer för länkar.](set-up-safe-links-policies.md)|
|Ett e-postmeddelande rapporteras av en användare som skadlig kod eller nätt|**Informativ**|Den här varningen genereras när användare i organisationen [](enable-the-report-message-add-in.md) rapporterar meddelanden som nätfiskemeddelanden med hjälp av tilläggen Rapportmeddelande eller [Rapportera nätfiske.](enable-the-report-phish-add-in.md)|
|E-postmeddelanden som innehåller skadlig programvara tas bort efter leverans|**Informativ**|Den här aviseringen genereras när e-postmeddelanden som innehåller skadlig programvara levereras till postlådor i organisationen. Om den här händelsen inträffar tar Microsoft bort de smittade meddelandena Exchange Online postlådor med automatisk [rensning på nolltimmar.](zero-hour-auto-purge.md)|
|E-postmeddelanden som innehåller webbadresser tas bort efter leverans|**Informativ**|Den här aviseringen genereras när några meddelanden som innehåller phish levereras till postlådor i din organisation. Om den här händelsen inträffar tar Microsoft bort de smittade meddelandena Exchange Online postlådor med automatisk [rensning på nolltimmar.](zero-hour-auto-purge.md)|
|Mönster för att skicka misstänkta e-postmeddelanden identifieras|**Medel**|Den här aviseringen genereras när någon i organisationen har skickat misstänkta e-postmeddelanden och riskerar att bli begränsad från att skicka e-post. Aviseringen är en tidig varning om beteende som kan indikera att kontot har komprometterats, men inte tillräckligt allvarligt för att begränsa användaren. <p> Även om det är ovanligt kan en varning som genereras av den här principen vara en avvikande avvikelse. Du bör dock kontrollera om [användarkontot har komprometterats.](responding-to-a-compromised-email-account.md)|
|En användare är begränsad från att skicka e-post|**Hög**|Den här aviseringen genereras när någon i din organisation är begränsad från att skicka utgående e-post. Den här aviseringen resulterar vanligtvis när ett [e-postkonto har komprometterats](responding-to-a-compromised-email-account.md). <p> Mer information om begränsade användare finns i [Ta bort blockerade användare från portalen Begränsade användare i Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Mer information om aviseringsprinciper och hur du redigerar standardinställningarna finns [i Aviseringsprinciper i Microsoft 365 kompatibilitetscenter.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Behörighet som krävs för att använda AIR-funktioner

Behörigheter beviljas genom vissa roller, till exempel de som beskrivs i följande tabell:

|Uppgift|Roll(er) krävs|
|---|---|
|Konfigurera AIR-funktioner|En av följande roller: <ul><li>Global administratör</li><li>Säkerhetsadministratör</li></ul> <p> De här rollerna kan [tilldelas i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)|
|Starta en automatiserad undersökning <p> --- eller --- <p> Godkänna eller avvisa rekommenderade åtgärder|En av följande roller, tilldelad i [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [Säkerhets- & Efterlevnadscenter:](permissions-in-the-security-and-compliance-center.md) <ul><li>Global administratör</li><li>Säkerhetsadministratör</li><li>Säkerhetsoperatör</li><li>Säkerhetsläsare <br> --- och --- </li><li>Sökning och rensning (den här rollen tilldelas endast i [säkerhets- och & Säkerhets- och efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md) Du kanske måste skapa en ny rollgrupp där och lägga till rollen Sök och rensa i den nya rollgruppen.</li></ul>|

## <a name="required-licenses"></a>Licenser som krävs

[Licenser för Microsoft Defender Office 365 abonnemang 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bör tilldelas till:

- Säkerhetsadministratörer (inklusive globala administratörer)
- Organisationens team för säkerhetsåtgärder (inklusive säkerhetsläsare och de med rollen **Sök och Rensning)**
- Slutanvändare:

## <a name="changes-are-coming-soon-in-your-security-center"></a>Ändringar kommer snart i ditt säkerhetscenter

Om du redan använder AIR-funktionerna i Microsoft Defender för Office 365 kommer du att se några ändringar i det [Microsoft 365 säkerhetscentret.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Enhetligt åtgärdscenter":::

Det nya och förbättrade säkerhetscentret sammanför AIR-funktionerna i [Microsoft Defender för Office 365](defender-for-office-365.md) och i Microsoft Defender för [slutpunkt.](../defender-endpoint/automated-investigations.md) Med de här uppdateringarna och förbättringarna kommer säkerhetsgruppen att kunna visa information om automatiska undersökningar och åtgärder som gäller för e-post, samarbetsinnehåll, användarkonton och enheter, allt på ett och samma ställe.

> [!TIP]
> Det nya Microsoft 365 säkerhetscentret <https://security.microsoft.com> () ersätter följande center:
>
> - Office 365 Säkerhets- & Efterlevnadscenter <https://protection.office.com> ()
> - Microsoft Defender Säkerhetscenter ( <https://securitycenter.windows.com> )
>
> Förutom att URL-adressen ändras finns ett nytt utseende som är utformat för att ge din säkerhetsgrupp en mer smidig upplevelse, med synlighet för fler identifieringar av hot på ett och samma ställe.

### <a name="what-to-expect"></a>Vad du kan förvänta dig

Följande tabell innehåller ändringar och förbättringar som kommer till AIR i Microsoft Defender för Office 365.

|Objekt|Vad är det som förändras?|
|---|---|
|**Sidan Undersökningar**|Den uppdaterade **sidan** undersökningar överensstämmer bättre med vad du ser i [Microsoft Defender för Slutpunkt](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations). Du kommer att se några allmänna format- och ändringsändringar som överensstämmer med den nya, enhetliga **vyn Undersökningar.** Undersökningsdiagrammet har till exempel ett mer enhetligt format.|
|**Fliken** Användare|Fliken **Användare** är nu **fliken Postlådor.** Information om användare visas på **fliken** Postlåda.|
|**Fliken E-post**|Fliken **E-post** har tagits bort. Gå till fliken **Enheter** om du vill se en lista över e-post- och e-postkluster.|
|**Fliken Enheter**|Fliken **Enheter** har ett flikformat med en sammanfattningsvy och möjligheten att filtrera efter entitetstyp. Fliken **Enheter** innehåller nu alternativet **Sök** efter förutom alternativet Öppna **i Utforskaren.** Nu kan du använda [antingen Threat Explorer](threat-explorer.md) [eller avancerad sökning](../defender-endpoint/advanced-hunting-overview.md) för att hitta enheter och hot och filtrera på resultat.|
|**Fliken** Åtgärder|Den uppdaterade **fliken** Åtgärder innehåller nu fliken **Väntande åtgärder** och fliken **Åtgärdshistorik.** Åtgärder kan godkännas (eller avvisas) i ett sidofönster som öppnas när du väljer en väntande åtgärd.|
|**Fliken Bevis**|På den **nya fliken** Bevis visas nyckelentitetsresultat som är relaterade till åtgärder. Åtgärder relaterade till varje bevis kan godkännas (eller avvisas) i ett sidofönster som öppnas när du väljer en väntande åtgärd.|
|**Åtgärdscenter**|I det **uppdaterade åtgärdscentret** [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () samlas väntande och slutförda åtgärder via e-post, enheter och identiteter. Mer information finns i Åtgärdscenter. (Mer information finns [i Åtgärdscenter](../defender/m365d-action-center.md).)|
|**Sidan Incidenter**|Sidan **Incidenter** korrelerar nu flera undersökningar för att ge en bättre konsoliderad vy över undersökningar. ([Läs mer om incidenter](../defender/incidents-overview.md).)|
|

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat av en automatiserad undersökning](air-view-investigation-results.md#view-details-of-an-investigation)
- [Granska och godkänna väntande åtgärder](air-remediation-actions.md)
