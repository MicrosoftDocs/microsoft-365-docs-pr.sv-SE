---
title: Översikt över Microsoft 365 Business Premium Security
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs mer om de säkerhetsfunktioner som ingår i Microsoft 365 för företag.
ms.openlocfilehash: c0890f097177848ef5a75c7c139c7dbc69e4eba1
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007099"
---
# <a name="overview-of-security"></a>Översikt över säkerhet

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premium tillhandahåller skydd mot hot, dataskydd och funktioner för enhetshantering som hjälper dig att skydda företaget mot onlinehot och obehörig åtkomst, samt att skydda och hantera företagsdata på telefoner, surfplattor och datorer.

|![Skydd mot hot](../media/m365-business-security-threat-protection.png)<br/>[Skydd mot hot](#threat-protection)|![Samarbeta med en klient](../media/m365-business-security-data-protection.png) <br/>[Dataskydd](#data-protection) | ![Enhetshantering](../media/m365-business-security-device-management.png) <br/>[Enhetshantering](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>Skydd mot hot

Microsoft 365 Business Premium inkluderar [Office 365 Advanced Threat Protection (ATP),](safe-links.md)en molnbaserad e-postfiltreringstjänst som skyddar dig från skadlig programvara, utpressningstrojaner, skadliga länkar med mera. ATP – säkra länkar skyddar dig från skadliga URL:er i e-postmeddelanden och Office-dokument. ATP – säkra bifogade filer skyddar dig mot skadlig programvara och virus som bifogas i meddelanden eller dokument.

[Multifaktorautentisering (MFA)](turn-on-mfa.md)eller tvåstegsverifiering kräver att du presenterar en andra form av autentisering, till exempel en verifieringskod, för att bekräfta din identitet innan du kan komma åt resurser.

[Windows Defender](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10) ger omfattande skydd mot virus, skadlig programvara, spionprogram och andra hot och ditt system, dina filer och onlineaktiviteter.

## <a name="data-protection"></a>Dataskydd

Dataskyddsfunktionerna i Microsoft 365 Business Premium hjälper till att säkerställa att viktiga data förblir säkra och att endast behöriga personer har åtkomst till dem.

Du kan använda principer för dataförlustskydd [(DLP)](set-up-dlp.md) för att identifiera och hantera känslig information, till exempel personnummer eller kreditkortsnummer, så att den inte delas av misstag.

[Meddelandekryptering i Office 365](/microsoft-365/compliance/ome) kombinerar krypterings- och åtkomstbehörighetsfunktioner för att säkerställa att endast tilltänkta mottagare kan visa meddelandeinnehållet. Meddelandekryptering i Office 365 fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster.

[Exchange Online – arkivering](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description) är en molnbaserad arkiveringslösning som fungerar med Microsoft Exchange eller Exchange Online för att tillhandahålla avancerade arkiveringsfunktioner, inklusive kvarlighet och dataredundans. Du kan använda bevarandeprinciper för att minska organisationens ansvar som är kopplade till e-post och annan kommunikation. Om ditt företag måste behålla kommunikation relaterad till rättstvist kan du använda bevarande av In-Place och bevarande av juridiska skäl för att bevara relaterad e-post.

## <a name="device-management"></a>Enhetshantering

Med avancerade enhetshanteringsfunktioner i Microsoft 365 Business Premium kan du övervaka och styra vad användare kan göra med registrerade enheter. Dessa funktioner omfattar villkorlig åtkomst, [hantering av mobila enheter (MDM),](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)BitLocker och automatiska uppdateringar.

Du kan använda villkorsstyrda åtkomstprinciper för att kräva ytterligare säkerhetsåtgärder för vissa användare och uppgifter. Du kan till exempel kräva [multifaktorautentisering (MFA)](/microsoft-365/business-video/turn-on-mfa) eller blockera klienter som inte stöder villkorsstyrd åtkomst.

Med MDM kan du skydda och hantera användarnas mobila enheter som iPhone, iPad, Android och Windows Phone. Du kan skapa och hantera säkerhetsprinciper för enheter, fjärrensa en enhet för att ta bort alla företagsdata, återställa en enhet till fabriksinställningarna och visa detaljerade enhetsrapporter.

Du kan aktivera BitLocker-kryptering för att skydda data i händelse av att en enhet försvinner eller blir stulen, och aktivera Windows Exploit Guard för att ge avancerat skydd mot utpressningstrojaner.

Du kan konfigurera automatiska uppdateringar så att de senaste säkerhetsfunktionerna och uppdateringarna tillämpas på alla användarenheter.

## <a name="recommended-security-guidance"></a>Rekommenderad säkerhetsvägledning

Det snabbaste sättetföretag att konfigurera säkerhet och börja samarbeta säkert för dig med Microsoft Business Premium är att följa vägledningen i det här biblioteket: [Microsoft 365 för mindre företag och kampanjer](../campaigns/index.md). Den här vägledningen har utvecklats i samarbete med teamet för Microsoft Defending Democracy för att skydda alla kunder med småföretag mot cyberhot från avancerade hackare.
