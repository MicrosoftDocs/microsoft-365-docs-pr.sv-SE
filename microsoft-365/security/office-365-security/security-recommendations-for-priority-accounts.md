---
title: Säkerhetsrekommendationer för prioriterade konton i Microsoft 365, prioritetskonton, prioritetskonton i Office 365, prioritetskonton i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: Administratörer kan lära sig att höja säkerhetsinställningarna och använda rapporter, aviseringar och undersökningar för prioriterade konton i Microsoft 365-organisationer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 814ca47ee48e844e313f7d75640643a0b659c527
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166375"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Säkerhetsrekommendationer för prioriterade konton i Microsoft 365

Alla användarkonton har inte tillgång till samma företagsinformation. Vissa konton har tillgång till känslig information, till exempel ekonomiska data, utvecklingsinformation, partneråtkomst till kritiska utvecklingssystem och mycket mer. Om de har komprometterats utgör konton som har tillgång till mycket konfidentiell information ett allvarligt hot. Vi kallar den här typen av _kontons prioritetskonton._ Prioritetskonton omfattar (men är inte begränsade till) CEOs, CISOs, CFOs, infrastrukturadministratörskonton, skapa systemkonton och mycket mer.

Vid attacker är vanliga nätfiskeattacker som visar ett slumpmässigt net för vanliga eller okända användare ineffektiva. Å andra sidan är _nätfiske-_ och _whalingattacker_ som prioriterade konton är mycket givande för attacker. Prioritetskonton kräver därför starkare än vanligt skydd för att förhindra kontokompromettering.

Microsoft 365 och Microsoft Defender för Office 365 innehåller flera viktiga funktioner som ger ytterligare säkerhetsnivåer för dina prioriterade konton. I den här artikeln beskrivs de här funktionerna och hur du använder dem.

![Sammanfattning av säkerhetsrekommendationerna i ikonformulär](../../media/security-recommendations-for-priority-users.png)

****

|Uppgift|Alla Office 365 Enterprise-abonnemang|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Öka inloggningssäkerheten för prioriterade konton](#increase-sign-in-security-for-priority-accounts)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Använda strikta förinställda säkerhetsprinciper för prioriterade konton](#use-strict-preset-security-policies-for-priority-accounts)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Använda användartaggar på prioritetskonton](#apply-user-tags-to-priority-accounts)|||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Övervaka prioriterade konton i aviseringar, rapporter och identifieringar](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Utbilda användare](#train-users)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Öka inloggningssäkerheten för prioriterade konton

Prioriterade konton kräver ökad inloggningssäkerhet. Du kan öka deras inloggningssäkerhet genom att kräva multifaktorautentisering (MFA) och inaktivera äldre autentiseringsprotokoll.

Instruktioner finns i [steg 1. Öka inloggningssäkerheten för fjärranslutna medarbetare med MFA.](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in) Även om den här artikeln handlar om fjärranslutna medarbetare gäller samma begrepp för prioriterade användare.

**Obs!** Vi rekommenderar starkt att du inaktiverar äldre autentiseringsprotokoll för alla prioriterade användare globalt enligt beskrivningen i föregående artikel. Om ditt företagskrav hindrar dig från att göra det erbjuder Exchange Online följande kontroller för att begränsa omfattningen av äldre autentiseringsprotokoll:

- Du kan använda [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) [autentiseringsprinciper](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) och klientåtkomstregler i Exchange Online för att blockera eller tillåta grundläggande autentisering och äldre autentiseringsprotokoll som POP3, IMAP4 och autentiserad SMTP för specifika användare.

- Du kan inaktivera åtkomst via POP3 och IMAP4 för enskilda postlådor. Du kan inaktivera autentiserad SMTP på organisationsnivå och aktivera det för specifika postlådor som fortfarande kräver det. Anvisningar finns i följande avsnitt:
  - [Aktivera eller inaktivera POP3- eller IMAP4-åtkomst för en användare](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Aktivera eller inaktivera autentiserad SMTP-sändning (SMTP AUTH)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Det är också värt att notera att grundläggande autentisering håller på att bli inaktuell i Exchange Online för Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 och fjärr-PowerShell. Mer information finns i det [här blogginlägget.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Använda strikta förinställda säkerhetsprinciper för prioriterade konton

För prioriterade användare krävs striktare åtgärder för de olika skydd som finns tillgängliga i Exchange Online Protection (EOP) och Defender för Office 365.

I stället för att leverera meddelanden som klassificerats som skräppost till mappen Skräppost bör du till exempel sätta dem i karantän om de är avsedda för prioriterade konton.

Du kan implementera den här strikta metoden för prioriterade konton genom att använda profilen Strikt i förinställda säkerhetsprinciper.

Förinställda säkerhetsprinciper är en bekväm och central plats där du kan använda våra rekommenderade strikt principinställningar för alla skydd i EOP och Defender för Office 365. Mer information finns i [Förinställda säkerhetsprinciper i EOP och Microsoft Defender för Office 365.](preset-security-policies.md)

Mer information om hur strikt principinställningar skiljer sig från standardinställningarna och standardprincipinställningarna finns i Rekommenderade inställningar för EOP och Microsoft Defender för [Office 365-säkerhet.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="apply-user-tags-to-priority-accounts"></a>Använda användartaggar på prioritetskonton

Användartaggar i Microsoft Defender för Office 365 abonnemang 2 (som en del av Microsoft 365 E5 eller en tilläggsprenumeration) är ett sätt att snabbt identifiera och klassificera specifika användare eller grupper av användare i rapporter och incidentundersökningar.

**Prioritetskonton** är en typ av inbyggd användartagg (kallas _systemtagg)_ som du kan använda för att identifiera incidenter och aviseringar som omfattar prioriterade konton. Mer information om **prioritetskonton finns** i Hantera [och övervaka prioritetskonton.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

Du kan också skapa anpassade taggar för att ytterligare identifiera och klassificera dina prioriterade konton. Mer information finns i [Användartaggar.](user-tags.md) Observera att du kan hantera **prioritetskonton** (systemtaggar) i samma gränssnitt som anpassade användartaggar.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Övervaka prioriterade konton i aviseringar, rapporter och identifieringar

När du har säkrat och tagga dina prioriterade användare kan du använda tillgängliga rapporter, aviseringar och undersökningar i EOP och Defender för Office 365 för att snabbt identifiera incidenter eller identifieringar som omfattar prioriterade konton. De funktioner som har stöd för användartaggar beskrivs i följande tabell.

<br>

****

|Funktion|Beskrivning|
|---|---|
|Varningar|Användartaggarna för påverkade användare är synliga  och tillgängliga som filter på sidan Visa aviseringar i Säkerhets- & Efterlevnadscenter. Mer information finns i Visa [aviseringar.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|Hotutforskaren <p> Identifiering i realtid|I **Threat Explorer** (Microsoft Defender för Office 365 abonnemang 2) eller identifieringar i realtid (Microsoft Defender för Office 365 abonnemang 1) visas användartaggar i rutnätsvyn för e-post och den utfällbara informationen om **e-post.** Användartaggar är också tillgängliga som en filtrerbar egenskap. Mer information finns i Taggar [i Hotutforskaren.](threat-explorer.md#tags-in-threat-explorer)|
|Kampanjvyer|Användartaggar är en av många filterbara egenskaper i kampanjvyer i Microsoft Defender för Office 365 abonnemang 2. Mer information finns i [Kampanjvyer.](campaigns.md)|
|Statusrapport för hotskydd|I praktiskt taget alla vyer och detaljtabeller i **rapporten om skydd mot hot** kan du filtrera resultaten efter **prioritetskonton.** Mer information finns i rapporten [om skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)|
|Rapport om e-postproblem för prioriterade konton|Rapporten **E-postproblem för prioriterade** konton i administrationscentret för Exchange (EAC) innehåller information om olevererade och fördröjda meddelanden för prioriterade **konton.** Mer information finns i rapporten [E-postproblem för prioritetskonton.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="train-users"></a>Utbilda användare

Utbildning av användare med prioriterade konton kan hjälpa till att spara dessa användare och ditt säkerhetsteam mycket tid och frustration. Smarta användare har mindre chans att öppna bifogade filer eller klicka på länkar i tveksama e-postmeddelanden, och det är troligare att de undviker misstänkta webbplatser.

The Cape School [Cybersecurity Campaign Handbook är](https://www.belfercenter.org/CyberPlaybook) en utmärkt vägledning för att etablera en stark säkerhetskultur inom organisationen, inklusive utbildning av användare för att identifiera nätfiskeattacker.

I Microsoft 365 finns följande resurser för att informera användarna i organisationen:

<br>

****

|Begrepp|Resurser|Beskrivning|
|---|---|---|
|Microsoft 365|[Anpassningsbara utbildningsvägar](https://docs.microsoft.com/office365/customlearning/)|De här resurserna kan hjälpa dig att samla utbildning för användare i organisationen.|
|Microsoft 365-säkerhet|[Learning module: Secure your organization with built-in, intelligent security from Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365)|I den här modulen kan du beskriva hur säkerhetsfunktionerna i Microsoft 365 fungerar tillsammans och att uttrycka fördelarna med dessa säkerhetsfunktioner.|
|Multifaktorautentisering|[Tvåstegsverifiering: Vad är ytterligare verifieringssida?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i organisationen.|
|Utbildning i attacksimulering|[Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)|Med utbildning om attackbedrägerier i Microsoft Defender för Office 365 abonnemang 2 kan administratörer konfigurera, starta och spåra simulerade nätfiskeattacker mot särskilda grupper av användare.|

Dessutom rekommenderar Microsoft att användare gör som beskrivs i den här artikeln: Skydda ditt konto och dina [enheter från hackare och skadlig programvara.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Dessa åtgärder omfattar:

- Använda starka lösenord
- Skydda enheter
- Aktivera säkerhetsfunktioner på PC-datorer med Windows 10 och Mac (för ohanterade enheter)

## <a name="see-also"></a>Se även

[Meddelande om prioriterat kontoskydd i Microsoft Defender för Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
