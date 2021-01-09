---
title: Säkerhets rekommendationer för prioriterade konton i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: Administratörer kan läsa mer om hur man höjer säkerhets inställningarna och använder rapporter, varningar och undersökningar för prioriterade konton i sina Microsoft 365-organisationer.
ms.openlocfilehash: acd2eba0acd533d0cd8223f2c433cc023fc23287
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790132"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Säkerhets rekommendationer för prioriterade konton i Microsoft 365

Alla användar konton har inte till gång till samma företags information. Vissa konton har till gång till känslig information, till exempel ekonomiska data, produkt utvecklings information, partner åtkomst till viktiga versions system och mycket mer. Konton som har till gång till mycket konfidentiell information utgör ett allvarligt hot om de äventyras. Vi ringer dessa typer av konton med _prioritets_ konton. Med prioritets konton kan du CEOs, CISOs, CFOs, infrastruktur administratörs konton, bygga system konton och mycket mer.

För attackerare är det inte så effektivt med vanliga nät fiske attacker som kastar ett slumpmässigt nät för vanliga eller okända användare. Å andra sidan _Spear nät fiske_ eller _Whaling_ attacker som riktar sig till mål grupps konton. Därför kräver prioritets konton starkare än vanligt skydd för att förhindra konto intrång.

Microsoft 365 och Microsoft Defender för Office 365 innehåller flera viktiga funktioner som ger ytterligare säkerhets nivåer för dina prioritets konton. I den här artikeln beskrivs de här funktionerna och hur du använder dem.

![Sammanfattning av säkerhets rekommendationerna i ikon formuläret](../../media/security-recommendations-for-priority-users.png)

****

|Uppgift|Alla Office 365 Enterprise-abonnemang|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Öka inloggnings säkerhet för prioriterade konton](#increase-sign-in-security-for-priority-accounts)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Använd strikta förvalda säkerhets principer för prioriterade konton](#use-strict-preset-security-policies-for-priority-accounts)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Använda användar koder på prioritets konton](#apply-user-tags-to-priority-accounts)|||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Övervaka prioriterade konton i aviseringar, rapporter och identifieringar](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Öka inloggnings säkerhet för prioriterade konton

Prioritets konton kräver ökad inloggnings säkerhet. Du kan öka sin inloggnings säkerhet genom att kräva multifaktorautentisering (MFA) och inaktivera äldre autentiseringsprotokoll.

Anvisningar finns i [steg 1. Öka inloggnings säkerheten för fjärranställda med MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in). Även om den här artikeln gäller fjärranställda gäller samma koncept för prioriterade användare.

**Obs!** vi rekommenderar starkt att du inaktiverar äldre autentiseringsprotokoll för alla prioriterade användare enligt beskrivningen i föregående artikel. Om dina företags behov hindrar dig från att göra så kan du använda Exchange Online för att begränsa omfattningen av äldre autentiseringsprotokoll:

- Du kan använda [autentiseringsprinciper](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) och [klient åtkomst regler](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) i Exchange Online för att blockera eller tillåta grundläggande autentisering och bakåtkompatibla AUTENTISERINGSPROTOKOLL som POP3, IMAP4 och autentiserad SMTP för specifika användare.

- Du kan inaktivera POP3-och IMAP4-åtkomst för enskilda post lådor. Du kan inaktivera autentiserad SMTP på organisations nivå och aktivera den på specifika post lådor som kräver det. Anvisningar finns i följande avsnitt:
  - [Aktivera eller inaktivera POP3-eller IMAP4-åtkomst för en användare](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Aktivera eller inaktivera SMTP-sändning via autentiserad klient (SMTP AUTH)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Det är också värt att notera att grundläggande verifiering används för att bli inaktuell i Exchange Online för Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 och Remote PowerShell. Mer information finns i det här [blogg inlägget](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Använd strikta förvalda säkerhets principer för prioriterade konton

Prioriterade användare kräver strängare åtgärder för olika skydd som är tillgängliga i Exchange Online Protection (EOP) och Defender för Office 365.

I stället för att skicka meddelanden som klassificerats som skräp post till skräppostmappen, bör du placera dem i samma meddelanden om de är avsedda för prioriterade konton.

Du kan använda den här strikta metoden för prioriterade konton med den strikta profilen i förvalda säkerhets principer.

Förvalda säkerhets principer är en enkel och central plats för att tillämpa våra rekommenderade strikta princip inställningar för alla skydd i EOP och Defender för Office 365. Mer information finns i avsnittet [för förvalda säkerhets principer i EOP och Microsoft Defender för Office 365](preset-security-policies.md).

Information om hur strikta princip inställningar skiljer sig från standardinställningarna för standard och standard princip finns i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Använda användar koder på prioritets konton

User-Taggar i Microsoft Defender för Office 365 abonnemang 2 (som en del av Microsoft 365 E5 eller en tilläggs prenumeration) är ett sätt att snabbt identifiera och klassificera specifika användare eller grupper av användare i rapporter och händelse analyser.

**Prioritets konton** är en typ av inbyggd användar märkning (kallas ett _system märke_) som du kan använda för att identifiera händelser och aviseringar som inbegriper prioriterade konton. Mer information om **prioritets konton** finns i [Hantera och övervaka prioritets konton](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

Du kan också skapa anpassade taggar för att identifiera och klassificera dina prioritets konton. Mer information finns i [User Tags](user-tags.md). Observera att du kan hantera **prioriterade konton** (systemtaggar) i samma gränssnitt som anpassade användar flaggor.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Övervaka prioriterade konton i aviseringar, rapporter och identifieringar

När du har skyddat och taggat dina prioriterade användare kan du använda de tillgängliga rapporterna, varningarna och utredningarna i EOP och Defender för Office 365 för att snabbt identifiera händelser och upptäckter som inbegriper prioriterade konton. De funktioner som stöder användar märkning beskrivs i följande tabell.

<br>

****

|Funktion|Beskrivning|
|---|---|
|Varningar|Användar taggarna för berörda användare är synliga och tillgängliga som filter på sidan **Visa aviseringar** i säkerhets & Compliance Center. Mer information finns i [Visa aviseringar](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).|
|Hotutforskaren <p> Identifiering i realtid|I **Threat Explorer** (Microsoft Defender för Office 365 abonnemang 2) eller **real tids identifiering** (microsoft Defender för Office 365 abonnemang 1) visas användar koder i e-postrutnätet och e-postinformationen. Användar flaggor är också tillgängliga som en filterbar egenskap. Mer information finns i  [taggar i Threat Explorer](threat-explorer.md#tags-in-threat-explorer).|
|Kampanjvyer|User-taggar är en av många filter bara egenskaper i vyn kampanjer i Microsoft Defender för Office 365 abonnemang 2. Mer information finns i [kampanjmallar](campaigns.md).|
|Statusrapport för hotskydd|I alla vyer och detalj tabeller i den här **rapporten** kan du filtrera resultat efter **prioritets konton**. För mer information, se [status rapport för hot skydd](view-email-security-reports.md#threat-protection-status-report).|
|E-postproblem för rapport med prioriterade konton|Rapporten om **e-postproblem för prioriterade konton** i administrations centret för Exchange (UK) innehåller information om ej levererade och fördröjda meddelanden för **prioriterade konton**. Mer information finns i artikeln [om e-postproblem för prioriterade konton](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="see-also"></a>Se även

[Det här skyddar prioritets konto i Microsoft Defender för Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
