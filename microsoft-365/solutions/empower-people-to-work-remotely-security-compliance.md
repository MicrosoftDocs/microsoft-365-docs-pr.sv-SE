---
title: 'Steg 3: Använd säkerhet och efterlevnad för hybridarbetare'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Använd säkerhets- och efterlevnadstjänsterna i Microsoft 365 för att skydda dina appar, data och enheter för hybridarbetare.
ms.openlocfilehash: 3de458f99ce1c83132d193cae523a49353b6956c
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229401"
---
# <a name="step-3-deploy-security-and-compliance-for-hybrid-workers"></a>Steg 3: Använd säkerhet och efterlevnad för hybridarbetare

För hybridarbetare, vilka vissa aldrig eller väldigt sällan är på kontoret, är säkerhet och efterlevnad en viktig del av den övergripande lösningen. All deras kommunikation sker via Internet i stället för att begränsas till organisationens intranät.

Det finns saker du och dina medarbetare kan göra för att fortsätta vara produktiva och minska cybersäkerhetsriskerna, och upprätthålla efterlevnaden av interna principer och dataföreskrifter.

För distansarbetare krävs följande säkerhets- och efterlevnadselement:

- Kontrollerad åtkomst till de produktivitetsapparna som hybridarbetarna använder, t.ex. Microsoft Teams
- Kontrollerad åtkomst till och skydd för de data som hybridarbetarna skapar och använder, t.ex. chattar eller delade filer
- Skydd för Windows 10-enheter mot skadlig programvara och andra typer av cyberattacker
- Skydd för e-post, filer och webbplatser med konsekvent etikettering för känslighets- och skyddsnivåer
- Förhindrande av dataläckage
- Iakttagande av regionala dataföreskrifter

Här är de funktioner i Microsoft 365 som tillhandahåller säkerhets- och efterlevnadstjänster för hybridarbetare.

![Använd dessa Microsoft 365-tjänster för att hålla dig säker och uppfylla efterlevnaden](../media/empower-people-to-work-remotely/remote-workers-security-compliance-grid.png)

## <a name="security"></a>Säkerhet

Skydda dina program och data med de här säkerhetsfunktionerna i Microsoft 365.

| Resurs eller funktion | Varför jag behöver det | Licensiering |
|:-------|:-----|:-------|
| Microsoft Defender för Office 365 | Skydda dina Microsoft 365-appar och data – t.ex. e-postmeddelanden, Office-dokument och samarbetsverktyg – från angrepp. <br><br> Microsoft Defender för Office 365 samlar in och analyserar signaler från dina appar för identifiering, undersökning och åtgärd av säkerhetsrisker och skyddar din organisation mot skadliga hot som uppstår genom e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Det ger också automatisk utvärdering av klientorganisationens konfiguration och konfigurationsverktyg för standard och strikt säkerhetsstatus. | Microsoft 365 E3 eller E5 |
| Skydd mot skadlig programvara | ‎Windows Defender Antivirus och Device Guard tillhandahåller enhetsbaserat skydd mot skadlig programvara. <br><br> SharePoint‎ Online skannar automatiskt igenom filuppladdningar efter känd skadlig kod.<br><br> Exchange Online Protection‎ (‎EOP‎) skyddar molnpostlådor. | Microsoft 365 E3 eller E5 |
| Microsoft Defender för Endpoint | Skydda din organisationsenheter mot cyberhot och dataintrång och identifiera, undersök och reagera på avancerade hot. | Microsoft 365 E5 |
| Cloud App Security | Skydda dina molnbaserade tjänster – både Microsoft 365 och andra SaaS-appar – från angrepp. | Microsoft 365 E5 eller individuella Cloud App Security-licenser |
| Azure AD Identity Protection  | Automatisera identifiering och åtgärder för identitetsbaserade risker. <br><br>Skapa riskbaserade principer för villkorsstyrd åtkomst för att kräva multifaktorautentisering (MFA) för riskfyllda inloggningar. | Microsoft 365 E5 eller E3 med Azure AD Premium P2-licenser |
||||

Ditt första steg bör vara att lära dig om och använda [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score).

Mer information finns i [De 12 viktigaste uppgifterna för säkerhetsteam för att stödja arbete hemifrån](../security/top-security-tasks-for-remote-work.md).

Information om säkerhet i Microsoft 365 finns i [dokumentation för Microsoft 365 Säkerhet](/microsoft-365/security).

## <a name="compliance"></a>Efterlevnad

Uppfyll de interna principerna eller regelkraven med dessa efterlevnadsfunktioner i Microsoft 365.

| Resurs eller funktion | Varför jag behöver det | Licensiering |
|:-------|:-----|:-------|
| Känslighetsetiketter | Med hjälp av etiketter med olika nivåer av skydd för e-post, filer och webbplatser kan du klassificera och skydda din organisations data utan att hindra användarnas produktivitet och möjligheter att samarbeta. | Microsoft 365 E3 eller E5 |
| Dataförlustskydd (DLP) | Identifiera, varna för och blockera riskfylld, oavsiktlig eller olämplig delning, t.ex. av data som innehåller personuppgifter, både internt och externt. | Microsoft 365 E3 eller E5 |
| Programkontroll med villkorsstyrd åtkomst | Förhindra att känsliga data laddas ned till användarnas personliga enheter. | Microsoft 365 E3 eller E5 |
| Etiketter och principer för kvarhållning av data | Implementera kontrollerna för informationsstyrning, t.ex. hur länge data ska behållas och kraven för lagring av personuppgifter för kunder, för att uppfylla organisationens principer och dataföreskrifter. | Microsoft 365 E3 eller E5 |
| Meddelandekryptering i Office (OME) | Skicka och ta emot krypterade e-postmeddelanden som innehåller reglerade data, t.ex. personliga data om kunder, mellan personer i och utanför din organisation. | Microsoft 365 E3 eller E5 |
| Efterlevnadshanteraren | Hantera regelefterlevnad som rör Microsofts molntjänster med detta arbetsflödesbaserade verktyg för riskbedömning i Microsoft Service Trust Portal. | Microsoft 365 E3 eller E5 |
| Efterlevnadshanteraren | Se en övergripande poäng för din nuvarande konfiguration och rekommendationer för att förbättra den i Microsoft 365 Efterlevnadscentret. | Microsoft 365 E3 eller E5 |
| Efterlevnad av kommunikation  | Identifiera, fånga och vidta reparationsåtgärder för olämpliga meddelanden i organisationen. | Microsoft 365 E5 eller Microsoft 365 E3 med tilläggen för efterlevnad och Insider-riskhantering |
| Hantering av insiderrisk |  Identifiera, undersöka och åtgärda skadliga och oavsiktliga risker i organisationen. Microsoft 365 kan upptäcka sådana typer av risker även om en arbetstagare använder en ohanterad enhet. | Microsoft 365 E5 eller Microsoft 365 E3 med tilläggen för efterlevnad och Insider-riskhantering |
||||

Mer information finns i artikeln om [snabbuppgifter för att komma igång med Microsoft 365-efterlevnad](../compliance/compliance-quick-tasks.md).

## <a name="results-of-step-3"></a>Resultat av steg 3

För dina hybridarbetare har du implementerat:

- Säkerhet
  - Kontrollerad åtkomst till appar och data som distansarbetarna använder för att kommunicera och samarbeta
  - Skydd mot skadlig programvara för molntjänstdata, e-post och Windows 10-enheter
- Efterlevnad
  - Konsekvent etikettering för känslighets- och skyddsnivåer
  - Principer för att förhindra dataläckage
  - Iakttagande av regionala dataföreskrifter

## <a name="next-step"></a>Nästa steg

[![Steg 4: Hantera enheter, datorer och andra slutpunkter](../media/empower-people-to-work-remotely/remote-workers-step-grid-4.png)](empower-people-to-work-remotely-manage-endpoints.md)

Fortsätt med [Steg 4](empower-people-to-work-remotely-manage-endpoints.md) för att hantera enheter, datorer och andra slutpunkter.
