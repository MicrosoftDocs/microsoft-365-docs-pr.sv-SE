---
title: Steg 3. Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Använd Microsoft Endpoint Manager för att hantera dina hanteringsenheter, datorer och andra slutpunkter.
ms.openlocfilehash: 4bc467b3da76a846d6d86e8812c542aa33f5e8b1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141468"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Steg 3. Distribuera slutpunktshantering för enheter, datorer och andra slutpunkter

Med distansarbetare måste du ha stöd för ett ökande antal personliga enheter. Slutpunktshantering är en principbaserad metod för säkerhet som kräver att enheter följer specifika villkor innan de beviljas åtkomst till resurser. Microsoft Endpoint Manager tillhandahåller en modern arbetsplats och moderna hanteringsfunktioner för att skydda dina data i molnet och lokalt. 

Microsoft Endpoint Manager tillhandhåller tjänster och verktyg för hantering av mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar genom att kombinera följande tjänster som du kanske redan känner till och använder.

![Komponenter för slutpunktshantering](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Intune har utformats för att hjälpa dig att skydda data när du inte hanterar enheter som används för att få åtkomst till organisationens data. Skyddsprinciper för Intune-appar kombinerat med villkorlig åtkomst i Azure Active Directory ger detaljerad kontroll över data på mobila enheter. Intune gör det också möjligt att definiera fullständiga principer som gör att bara rätt personer har tillgång till dina företagsdata och säkerställa att data förblir skyddade genom att kontrollera hur de använder dem i Office, Outlook och andra mobilappar.

Mer information finns i det här [översikt över Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager är en lokal hanteringslösning för hantering av stationära datorer, servrar och bärbara datorer som finns på nätverket eller är internet-baserade. Du kan moln-aktivera den för att integrera med Intune, Azure Active Directory, Microsoft Defender Avancerat skydd och andra molntjänster. Använd Configuration Manager för att distribuera appar, programvaruuppdateringar och operativ system. Du kan också övervaka efterlevnad, läsa och åtgärda klienter i realtid och mycket mer.

Mer information finns i den här [översikt över Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Samhantering

Med hjälp av samhantering slås din befintliga lokala investeringar i Configuration Manager med molnet med hjälp av Intune och andra Microsoft 365-molntjänster. Du kan välja om Configuration Manager eller Intune ska vara hanteringsauktoritet för sju olika arbetsbelastningsgrupper.

Som en del av Endpoint Manager använder samhantering molnfunktioner, inklusive villkorsstyrd åtkomst. Du har kvar några uppgifter lokalt medan du kör andra uppgifter i molnet med Intune.

Mer information finns i den här [översikt över samhantering](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Desktop Analytics

Desktop Analytics är en molnbaserad tjänst som integreras med Configuration Manager och ger dig insyn och intelligens så att du kan fatta välgrundade beslut om dina Windows-klienter. Den kombinerar data från din organisation med data aggregerade från miljontals enheter som är anslutna till Microsofts molntjänster. Med Desktop Analytics kan du skapa en inventering av appar som körs i din organisation, utvärdera programkompatibilitet med de senaste funktionerna i Windows 10, identifiera kompatibilitetsproblem och få förslag på problem beroende på molnbaserade datainsikter, skapa pilotgrupper som representerar hela programmet och din enhets plats i en minimal uppsättning enheter och distribuera Windows 10 till pilotprojekt och produktionshanterade enheter.

Mer information finns i den här [översikt över Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot är en plattform för Windows-driftsättning med låg vikt. Den innehåller en samling tekniker som används för att konfigurera och förinstallera nya enheter och för att förbereda för effektiv användning. Du kan också använda Windows Autopilot för att återställa, återanvända enheter. Med den här lösningen kan IT-avdelningen uppnå ovanstående med liten till ingen infrastruktur för hantering, med en process som är enkel och lätt. Från användarens perspektiv är det bara några få enkla åtgärder för att göra deras enhet redo för användning. Från IT-proffsens perspektiv är den enda interaktion som krävs för slutanvändarna att ansluta till ett nätverk och för att verifiera deras autentiseringsuppgifter.

Mer information finns i den här [översikt över Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Tekniska IT-resurser för slutpunktshantering

- [Registrera hanterade enheter för säkerhet, använd programinställningar för ohanterade enheter och använda principer för appar och enheter](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Registrera olika typer av enheter för hantering av mobila enheter (MDM)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Hur du utbildar dina slutanvändare om Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Resultat i steg 3

Du använder paketet med Endpoint Manager-funktioner och -förmågor för att hantera mobila enheter, stationära datorer, virtuella datorer, inbäddade enheter och servrar.

## <a name="next-step"></a>Nästa steg

Fortsätt med [Steg 4](empower-people-to-work-remotely-teams-productivity-apps.md) om du vill tillhandahålla fjärråtkomst till lokala appar och tjänster.
