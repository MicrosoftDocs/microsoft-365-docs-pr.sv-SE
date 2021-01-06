---
title: Steg 4. Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
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
description: Använd Microsoft Endpoint Manager för att hantera dina hanteringsenheter, datorer och andra slutpunkter.
ms.openlocfilehash: bca3e8e79264a2218dd1036e50be1c9ab29d2b8a
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749605"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Steg 4. Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter

Med distansarbetare måste du ha stöd för ett ökande antal personliga enheter. Slutpunktshantering är en principbaserad metod för säkerhet som kräver att enheter följer specifika villkor innan de beviljas åtkomst till resurser. Microsoft Endpoint Manager tillhandahåller moderna hanteringsfunktioner för att skydda dina data i molnet och lokalt. 

[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) tillhandhåller tjänster och verktyg för hantering av mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar genom att kombinera följande tjänster som du kanske redan känner till och använder.

![Komponenterna i slutpunktshantering för Microsoft 365](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune är en molnbaserad tjänst som fokuserar på hantering av mobila enheter (MDM) och hantering av mobila program (MAM) som ingår i Microsoft 365. 

- **MDM:** för enheter som ägs av organisationen kan du utnyttja fullständig kontroll, t. ex. inställningar, funktioner och säkerhet. Enheter "registreras" i Intune där de får Intune-principer med regler och inställningar. Du kan till exempel ange krav på lösenord och PIN-kod, skapa en VPN-anslutning, konfigurera skydd med hot och mycket mer.

- **MAM:** distansmedarbetare kanske inte vill att du ska ha fullständig kontroll över deras personliga enheter, även kallat bring-your-own device (BYOD). Du kan erbjuda dina distansmedarbetare alternativ och fortfarande skydda din organisation. Distansmedarbetare kan till exempel registrera sina enheter om de vill ha full tillgång till organisationens resurser. Om de här användarna bara vill ha tillgång till e-post eller Microsoft Teams kan du använda skyddsprinciper för appar som kräver multifaktorautentisering (MFA) för att använda de här apparna.

Mer information finns i det här [översikt över Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager är en lokal hanteringslösning för hantering av stationära datorer, servrar och bärbara datorer som finns på nätverket eller är internet-baserade. Använd Configuration Manager för att distribuera appar, programvaruuppdateringar och operativ system. Du kan också övervaka efterlevnad, läsa och åtgärda klienter i realtid och mycket mer. Du kan moln-aktivera den för att integrera med Intune, Azure Active Directory, Microsoft Defender för Endpoint och andra molntjänster. 

Mer information finns i den här [översikt över Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Samhantering

Med hjälp av samhantering slås din befintliga lokala investeringar i Configuration Manager med molnet med hjälp av Intune och andra Microsoft 365-molntjänster. Du kan välja om Configuration Manager eller Intune ska vara hanteringsauktoritet för olika arbetsbelastning. 

I Co-Management används Intune-baserade molnfunktioner, t. ex. villkorlig åtkomst och framtvingande av enhetskompatibilitet. Du har kvar några uppgifter lokalt medan du kör andra uppgifter i molnet.

Mer information finns i den här [översikt över samhantering](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics är en molnbaserad tjänst som integreras med Configuration Manager och ger dig insyn och intelligens så att du kan fatta välgrundade beslut om dina Windows-klienter. Den kombinerar data från din organisation med data aggregerade från miljontals andra enheter som är anslutna till Microsofts molntjänster. 

Med Desktop Analytics kan du:

- Skapa en inventering av appar som körs i din organisation.
- Utvärdera apparnas kompatibilitet med de senaste funktionsuppdateringarna för Windows 10.
- Identifiera kompatibilitetsproblem och få förslag på problem med hjälp av molnbaserade datainsikter.
- Skapa pilotgrupper som representerar hela programmet och fastigheten i en minimal uppsättning enheter.
- Distribuera Windows 10 till pilotprojekt och Production Managed-enheter.

Mer information finns i den här [översikt över Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot är en plattform för Windows-driftsättning med låg vikt. Den innehåller en samling tekniker som används för att konfigurera och förinstallera nya enheter och för att förbereda för effektiv användning. Du kan också använda Windows Autopilot för att återställa, återanvända enheter. 

Windows Autopilot låter IT-avdelningen förkonfigurera enheter med liten till ingen infrastruktur för hantering, med en process som är enkel och lätt. 

- Från användarens perspektiv är det bara några få enkla åtgärder för att göra deras enhet redo för användning. 
- Från IT-proffsens perspektiv är den enda interaktion som krävs för slutanvändarna att ansluta till ett nätverk och för att verifiera deras autentiseringsuppgifter.

Mer information finns i den här [översikt över Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Tekniska IT-resurser för slutpunktshantering

- [Översikt över enhetshantering för Microsoft 365](../enterprise/device-management-roadmap-microsoft-365.md)
- [Registrera olika typer av enheter för hantering av mobila enheter](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Hur du utbildar dina slutanvändare om Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>Resultat i steg 4

Du använder paketet med Endpoint Manager-funktioner och -förmågor för att hantera mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar.

## <a name="next-step"></a>Nästa steg

[![Steg 5: Distribuera produktivitetsappar och tjänster för distansarbetare](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)

Fortsätt med [Steg 5](empower-people-to-work-remotely-teams-productivity-apps.md) för att få dina distansmedarbetare att använda Microsoft 365 produktivitetsappar som Microsoft Teams.
