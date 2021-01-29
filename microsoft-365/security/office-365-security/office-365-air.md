---
title: Automatiserad undersökning och svar i Microsoft Defender för Office 365
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/28/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Komma igång med automatisk undersökning och svarsfunktioner i Microsoft Defender för Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee448e31ccbddbf1d1d5653614ec75fa94768b3b
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040538"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatiserad undersökning och svar (AIR) i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender för Office 365](office-365-atp.md) innehåller kraftfulla funktioner för automatisk undersökning och svar (AIR) som kan spara tid och arbete för säkerhetsåtgärder. När aviseringar utlöses är det upp till din säkerhetsgrupp att granska, prioritera och svara på dessa aviseringar. Det kan vara överväldigande att hålla koll på mängden inkommande aviseringar. Att automatisera vissa av uppgifterna kan vara till hjälp.

AIR gör att ditt säkerhetsteam kan arbeta effektivare. AIR-funktioner omfattar automatiserade undersökningsprocesser som svar på välkända hot som finns idag. Lämpliga åtgärder väntar på godkännande, vilket gör det möjligt för teamet för säkerhetsåtgärder att svara effektivt på identifierade hot. Med AIR kan ditt säkerhetsteam fokusera på uppgifter med högre prioritet utan att förlora viktiga aviseringar som utlöses.

I den här artikeln beskrivs:

- Det [övergripande flödet av AIR](#the-overall-flow-of-air);
- [Skaffa AIR](#how-to-get-air); och
- De [behörigheter som krävs](#required-permissions-to-use-air-capabilities) för att konfigurera eller använda AIR-funktioner.

Den här artikeln innehåller [även nästa steg](#next-steps)och resurser för mer information.

## <a name="the-overall-flow-of-air"></a>Det övergripande flödet av AIR

En avisering utlöses och en säkerhetsspelbok startar en automatiserad undersökning, som resulterar i resultat och rekommenderade åtgärder. Här är det övergripande flödet av AIR steg för steg:

1. En automatiserad undersökning initieras på något av följande sätt:

   - En [avisering utlöses av](#which-alert-policies-trigger-automated-investigations) något misstänkt i ett e-postmeddelande (till exempel ett meddelande, en bifogad fil, en URL eller ett komprometterat användarkonto). En incident skapas och en automatisk undersökning påbörjas.

     --- eller ---

   - En säkerhetsanalytiker startar [en automatiserad undersökning med](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) hjälp av Threat [Explorer.](threat-explorer.md)

2. När en automatiserad undersökning körs samlar den in ytterligare data om e-postmeddelandet i fråga och enheter som är relaterade till e-postmeddelandet. Sådana enheter kan innehålla filer, URL:er och mottagare.  Undersökningens omfattning kan öka allt eftersom nya och relaterade aviseringar utlöses.

3. Under och efter en automatiserad undersökning [kan du](air-view-investigation-results.md) se information och resultat. Resultaten omfattar [rekommenderade åtgärder](air-remediation-actions.md) som kan vidtas för att svara på och åtgärda hot som har hittats. Dessutom finns det en [spelbokslogg](air-view-investigation-results.md#playbook-log) som spårar all undersökningsaktivitet.

4. Ditt säkerhetsteam granskar [undersökningsresultatet och rekommendationerna](air-view-investigation-results.md) [och godkänner eller avvisar åtgärder.](air-review-approve-pending-completed-actions.md)

5. Eftersom väntande åtgärder godkänns (eller avvisas) slutförs den automatiska undersökningen.

> [!IMPORTANT]
> I Microsoft Defender för Office 365 vidtas inga åtgärder automatiskt. Åtgärder vidtas endast vid godkännande av organisationens säkerhetsteam.
>
> AIR-funktioner sparar din grupptid för säkerhetsåtgärder genom att identifiera åtgärder och tillhandahålla den information som behövs för att fatta ett välgrundat beslut.

Under och efter varje automatiserad undersökning kan ditt säkerhetsteam:

- [Visa information om en varning relaterad till en undersökning](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Visa resultatinformation för en undersökning](air-view-investigation-results.md#view-details-of-an-investigation)

- [Granska och godkänna åtgärder som ett resultat av en undersökning](air-review-approve-pending-completed-actions.md)

> [!TIP]
> En mer detaljerad översikt finns i [Hur AIR fungerar.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Skaffa AIR

AIR-funktionerna ingår i [Microsoft Defender för Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)förutsatt att dina principer och aviseringar har konfigurerats. Om du vill ha hjälp med detta [](protect-against-threats.md) följer du vägsvägledning i Skydda mot hot för att konfigurera eller konfigurera följande skyddsinställningar:

1. [Granskningsloggning](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (ska aktiveras)

2. [Principer för program mot skadlig programvara](protect-against-threats.md#part-1---anti-malware-protection)

3. [Skydd mot phishing](protect-against-threats.md#part-2---anti-phishing-protection)

4. [Skydd motspam](protect-against-threats.md#part-3---anti-spam-protection).

5. [Säkra länkar och säkra bifogade filer.](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

6. [Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams.](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)

7. [Nolltimmarsavrensning för e-post.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Dessutom ska du granska [organisationens aviseringsprinciper,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)särskilt [standardprinciperna i kategorin Hothantering.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Vilka aviseringsprinciper utlöser automatiska undersökningar?

Microsoft 365 innehåller många inbyggda aviseringsprinciper som hjälper till att identifiera missbruk av behörigheter för Exchange-administratörer, skadlig aktivitet, potentiella externa och interna hot och risker med informationsstyrning. Flera av [standardaviseringsprinciperna](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan utlösa automatiska undersökningar. I följande tabell beskrivs de varningar som utlöser automatiska undersökningar, deras allvarlighetsgrad i Säkerhetscenter i Microsoft 365 och hur de genereras:

|Avisering|Allvarlighetsgrad|Så här genereras aviseringen|
|:---|:---|:---|
|Ett potentiellt skadligt URL-klick upptäcktes|**Högsta**|Den här aviseringen genereras när något av följande inträffar: <ul><li>En användare som skyddas [av säkra](atp-safe-links.md) länkar i organisationen klickar på en skadlig länk</li><li>Ändringar av bedömning av WEBBADRESSer identifieras av Microsoft Defender för Office 365</li><li>Användarna åsidosätter varningssidor för säkra länkar (baserat på organisationens [princip för säkra länkar).](set-up-atp-safe-links-policies.md)</li></ul> <p> Mer information om händelser som utlöser den här aviseringen finns [i Konfigurera principer för säkra länkar.](set-up-atp-safe-links-policies.md)|
|Ett e-postmeddelande rapporteras av en användare som skadlig kod eller nätt|**Information**|Den här aviseringen genereras när användare i organisationen [](enable-the-report-message-add-in.md) rapporterar meddelanden som nätfiskemeddelanden med hjälp av tilläggen Rapportmeddelande eller [Rapport nätfiske.](enable-the-report-phish-add-in.md)|
|E-postmeddelanden som innehåller skadlig programvara tas bort efter leverans|**Information**|Den här aviseringen genereras när e-postmeddelanden som innehåller skadlig programvara levereras till postlådor i organisationen. Om händelsen inträffar tar Microsoft bort de smittade meddelandena från Exchange Online-postlådorna med automatisk rensning utan [timme.](zero-hour-auto-purge.md)|
|E-postmeddelanden som innehåller phish-URL:er tas bort efter leverans|**Information**|Den här aviseringen genereras när alla meddelanden som innehåller phish levereras till postlådor i din organisation. Om händelsen inträffar tar Microsoft bort de smittade meddelandena från Exchange Online-postlådorna med automatisk rensning utan [timme.](zero-hour-auto-purge.md)|
|Avsändarmönster för misstänkta e-postmeddelanden identifieras|**Medel**|Den här aviseringen genereras när någon i organisationen har skickat misstänkta e-postmeddelanden och riskerar att bli begränsad från att skicka e-post. Det här är en tidig varning om ett beteende som kan indikera att kontot har komprometterats, men inte är tillräckligt allvarligt för att begränsa användaren. <p> Även om det är ovanligt kan en varning som genereras av den här principen vara en avvikelse. Men det kan vara bra att kontrollera [om användarkontot har komprometterats.](responding-to-a-compromised-email-account.md)|
|En användare är begränsad från att skicka e-post|**Högsta**|Den här aviseringen genereras när någon i organisationen är begränsad från att skicka utgående e-post. Det här resulterar vanligtvis i att ett [e-postkonto har komprometterats.](responding-to-a-compromised-email-account.md) <p> Mer information om begränsade användare finns i Ta bort blockerade användare från portalen Begränsade användare [i Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Mer information om aviseringsprinciper och hur du redigerar standardinställningarna finns i [Aviseringsprinciper i Efterlevnadscenter för Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="required-permissions-to-use-air-capabilities"></a>Behörighet som krävs för att använda AIR-funktioner

Behörigheter beviljas genom vissa roller, till exempel de som beskrivs i följande tabell:

|Uppgift|Roll(er) krävs|
|---|---|
|Konfigurera AIR-funktioner|En av följande roller: <ul><li>Global administratör</li><li>Säkerhetsadministratör</li></ul> <p> De här rollerna kan tilldelas [i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)|
|Starta en automatiserad undersökning <p> --- eller --- <p> Godkänna eller avvisa rekommenderade åtgärder|En av följande roller, tilldelade i [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) eller i [Säkerhets- & Efterlevnadscenter:](permissions-in-the-security-and-compliance-center.md) <ul><li>Global administratör</li><li>Säkerhetsadministratör</li><li>Säkerhetsoperatör</li><li>Säkerhetsläsare <br> --- och --- </li><li>Sökning och rensning (den här rollen tilldelas endast i [Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md) Du kanske måste skapa en ny rollgrupp där och lägga till rollen Sök och rensa i den nya rollgruppen.</li></ul>|
|

## <a name="required-licenses"></a>Licenser som krävs

[Licenser för Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bör tilldelas till:

- Säkerhetsadministratörer (inklusive globala administratörer)
- Organisationens säkerhetsteam (inklusive säkerhetsläsare och användare med rollen **Sök och rensning)**
- Slutanvändare:

## <a name="next-steps"></a>Nästa steg

- [Visa information och resultat av en automatiserad undersökning](air-view-investigation-results.md#view-details-of-an-investigation)

- [Granska och godkänna väntande åtgärder](air-remediation-actions.md)

## <a name="see-also"></a>Se även

- [Automatiserad undersökning och åtgärd i Microsoft Defender för Slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatiserad undersökning och svar i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
