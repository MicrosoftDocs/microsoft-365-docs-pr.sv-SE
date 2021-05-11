---
title: Översikt över Microsoft 365 Business Premium säkerhet
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
ms.openlocfilehash: a1195ee1296936f3f0106b845f641aa5aaad0dac
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311442"
---
# <a name="overview-of-security"></a>Översikt över säkerhet

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premium tillhandahåller skydd mot hot, dataskydd och funktioner för enhetshantering som hjälper dig att skydda företaget från onlinehot och obehörig åtkomst, samt att skydda och hantera företagsdata på telefoner, surfplattor och datorer.

|![Skydd mot hot](../media/m365-business-security-threat-protection.png)<br/>[Skydd mot hot](#threat-protection)|![Samarbeta med en klient](../media/m365-business-security-data-protection.png) <br/>[Dataskydd](#data-protection) | ![Enhetshantering](../media/m365-business-security-device-management.png) <br/>[Enhetshantering](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>Skydd mot hot

Microsoft 365 Business Premium omfattar [Office 365 ATP (Advanced Threat Protection),](safe-links.md)en molnbaserad e-postfiltreringstjänst som skyddar dig mot skadlig programvara, utpressningstrojaner, skadliga länkar med mera. ATP Valv skyddar dig från skadliga URL:er i e-post Office dokument. ATP Valv bifogade filer skyddar dig från skadlig programvara och virus som är kopplade till meddelanden eller dokument.

[Multifaktorautentisering (MFA)](turn-on-mfa.md)eller tvåstegsverifiering kräver att du presenterar en andra form av autentisering, till exempel en verifieringskod, för att bekräfta din identitet innan du kan komma åt resurser.  

[Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10) skydd mot virus, skadlig programvara, spionprogram och andra hot online för system-, fil- och onlineaktiviteter.

## <a name="data-protection"></a>Dataskydd

Dataskyddsfunktionerna i Microsoft 365 Business Premium att säkerställa att viktiga data förblir säkra och att endast behöriga personer har åtkomst till dem.

Du kan använda principer för dataförlustskydd [(DLP)](set-up-dlp.md) för att identifiera och hantera känslig information, till exempel personnummer eller kreditkortsnummer, så att den inte delas av misstag. 

[Meddelandekryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/ome) kombinerar krypterings- och åtkomstbehörighetsfunktioner för att säkerställa att endast tilltänkta mottagare kan visa meddelandeinnehållet. Meddelandekryptering i Office 365 fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster.

[Exchange Online - arkivering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description) är en molnbaserad arkiveringslösning som fungerar med Microsoft Exchange eller Exchange Online för att tillhandahålla avancerade arkiveringsfunktioner, inklusive kvarlighet och dataredundans. Du kan använda bevarandeprinciper för att minska organisationens ansvar som är kopplade till e-post och annan kommunikation. Om ditt företag måste behålla kommunikation relaterad till rättstvist kan du använda bevarande av In-Place och bevarande av juridiska skäl för att bevara relaterad e-post.

## <a name="device-management"></a>Enhetshantering

Microsoft 365 Business Premium avancerade enhetshanteringsfunktioner kan du övervaka och styra vad användare kan göra med registrerade enheter. Dessa funktioner omfattar villkorlig åtkomst, [hantering av mobila enheter (MDM),](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)BitLocker och automatiska uppdateringar.

Du kan använda villkorsstyrda åtkomstprinciper för att kräva ytterligare säkerhetsåtgärder för vissa användare och uppgifter. Du kan till exempel kräva multifaktorautentisering (MFA) eller blockera klienter som inte stöder villkorsstyrd åtkomst.

Med MDM kan du skydda och hantera användarnas mobila enheter som iPhone, iPad, Android och Windows telefoner. Du kan skapa och hantera säkerhetsprinciper för enheter, fjärrensa en enhet för att ta bort alla företagsdata, återställa en enhet till fabriksinställningarna och visa detaljerade enhetsrapporter. 

Du kan aktivera BitLocker kryptering för att skydda data i händelse av att en enhet försvinner eller blir stulen, och aktivera Windows Exploit Guard för att ge avancerat skydd mot utpressningstrojaner.

Du kan konfigurera automatiska uppdateringar så att de senaste säkerhetsfunktionerna och uppdateringarna tillämpas på alla användarenheter. 

## <a name="recommended-security-guidance"></a>Rekommenderad säkerhetsvägledning

Det snabbaste sättetföretag att konfigurera säkerhet och börja samarbeta säkert för dig med Microsoft Business Premium är att följa vägledningen i det här biblioteket: [Microsoft 365 för mindre företag och kampanjer](../campaigns/index.md). Den här vägledningen har utvecklats i samarbete med teamet för Microsoft Defending Democracy för att skydda alla kunder med småföretag mot cyberhot från avancerade hackare.