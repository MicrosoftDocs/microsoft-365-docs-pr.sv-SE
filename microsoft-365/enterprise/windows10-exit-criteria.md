---
title: 'Fas 3: Avslutsvillkor för Windows 10 Enterprise-infrastruktur'
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise villkor för Windows 10 Enterprise.
ms.openlocfilehash: 42d8ec912a70aecef49672682c25f5e42c4bbe21
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808592"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>Fas 3: Avslutsvillkor för Windows 10 Enterprise-infrastruktur

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Kontrollera att din Windows 10 Enterprise-infrastruktur uppfyller följande krav och överväg om du vill använda de valfria alternativen.

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>Obligatoriskt: Dina Microsoft 365-domäner har lagts till och verifierats

Azure AD-klienten för dina Office 365- och Intune-prenumerationer har konfigurerats med dina Internetdomännamn (till exempel contoso.com), i stället för bara ett domännamn som innehåller ”onmicrosoft.com”. 

Om du inte gör det begränsas autentiseringsmetoderna som du kan konfigurera. Direktautentisering och federerad autentisering kan till exempel inte använda domännamnet ”onmicrosoft.com”.

Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta krav.

## <a name="optional-your-users-are-added-and-licensed"></a>Valfritt: Användarna har lagts till och fått licenser

Dina användares konton har lagts till, antingen direkt till din Azure AD-klient för dina Office 365- och Intune-prenumerationer, eller från katalogsynkronisering från din lokala AD DS (Active Directory Domain Services).

När användarna har lagts till kan du tilldela dem Microsoft 365 Enterprise-licenser, antingen direkt som global administratör eller användaradministratör, eller automatiskt via gruppmedlemskap.

Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta alternativ.

## <a name="optional-diagnostics-are-enabled"></a>Valfritt: Diagnostik har aktiverats

Du har aktiverat inställningar för diagnostikdata med hjälp av grupprincip, Microsoft Intune, Registereditorn eller i kommandotolken.

Vid behov kan [Steg 1](windows10-prepare-your-org.md) hjälpa dig med detta alternativ.

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>Obligatoriskt för uppgradering på plats: En aktivitetssekvens för 
Configuration Manager har skapats för distribution av operativsystem

Om du vill starta en aktivitetssekvens för Configuration Manager för att göra en uppgradering på plats på en enhet som kör Windows 7 eller Windows 8.1 måste du ha:

- Konfigurerat rätt nivå för Windows-diagnostikdata.
- Verifierat att enheten är redo för Windows-uppgradering.
- Skapat en aktivitetssekvens för Configuration Manager som omfattar en enhetssamling och en distribution av operativsystem med en Windows 10 OS-avbildning.

När det är klart kan du utföra uppgraderingar på plats på enheter som är redo för Windows-uppgradering. För att få ut så mycket som möjligt av Microsoft 365 Enterprise kan du uppgradera så många enheter som kör Windows 7 och Windows 8.1 som möjligt. 

Enheter som kör Windows 10 Enterprise kan få tillgång till fördelarna med den integrerade lösningen Microsoft 365 Enterprise. Andra enheter som kör Windows 7 eller Windows 8.1 kan inte använda den molnbaserade tekniken eller de avancerade säkerhetsfunktionerna i Windows 10 Enterprise.

Vid behov kan [Steg 2](windows10-deploy-inplaceupgrade.md) hjälpa dig med detta krav.

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>Obligatoriskt för nya enheter: Konfigurerad Windows Autopilot

Om du vill distribuera och anpassa Windows 10 Enterprise på en ny enhet med Windows Autopilot måste du ha:

- Konfigurerat rätt nivå för Windows-diagnostikdata.
- Konfigurerat förutsättningarna för Windows Autopilot, som:
   - Enhetsregistrering och OOBE-anpassning.
   - Företagsanpassning för OOBE.
   - Automatisk MDM-registrering i Microsoft Intune.
   - Nätverksanslutning till molntjänster som används av Windows Autopilot.
- Enheter som har Windows 10, version 1703 eller senare förinstallerat.
- Valt distributionsprogrammet Windows Autopilot för organisationen.

När Windows Autopilot-konfigurationen har gjorts kan du använda den för att konfigurera och anpassa Windows 10 Enterprise för välkomstupplevelsen (OOBE) för:

- Nya enheter.
- Enheter som redan har slutfört en OOBE-konfiguration i din organisation. 

Windows Autopilot konfigurerar enheten och ansluter den till Azure AD.

Utan Windows Autopilot måste du manuellt konfigurera nya enheter, även anslutningen till Azure AD.

Vid behov kan [Steg 3](windows10-deploy-autopilot.md) hjälpa dig med detta krav.

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>Valfritt: Du övervakar Windows 10 Enterprise-baserade enheter med enhetshälsotillstånd i Windows Analytics

Du har använt informationen från övervakningen av enheternas hälsotillstånd för att identifiera och åtgärda problem som påverkar slutanvändarna. Genom att snabbt åtgärda problem för slutanvändare kan du minska supportkostnaderna och visa dina användare IT-åtagandet för Windows 10 Enterprise. Det kan stödja införandet i hela organisationen. 

Vid behov kan [Steg 4](windows10-enable-windows-analytics.md) hjälpa dig med detta alternativ.

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>Obligatoriskt: Du använder Windows Defender Antivirus eller din egen lösning mot skadlig kod

Du har distribuerat Windows Defender Antivirus eller din egen antiviruslösning för att skydda dina enheter som kör Windows 10 Enterprise mot skadlig programvara. Om du har distribuerat Windows Defender Antivirus har du implementerat en rapporteringsmetod, t.ex. Microsoft Endpoint Configuration Manager eller Microsoft Intune, för att övervaka antivirushändelser och aktiviteter.

Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-av) hjälpa dig med detta krav.

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>Obligatoriskt: Du använder Windows Defender Exploit Guard

Du har distribuerat Windows Defender Exploit Guard för att skydda dina enheter som kör Windows 10 Enterprise mot intrång och har implementerat en rapporteringsmetod, t.ex. Configuration Manager eller Microsoft Intune, för att övervaka intrångshändelser och aktiviteter.

Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-eg) hjälpa dig med detta krav.

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>Obligatoriskt: Du använder Microsoft Defender Avancerat skydd (endast Microsoft 365 E5)

Du har distribuerat Microsoft Defender Avancerat skydd (ATP) för att identifiera, undersöka och åtgärda avancerade hot mot ditt nätverk och enheter som kör Windows 10 Enterprise. 

Du kan även ha integrerat Microsoft Defender ATP med andra verktyg för att utöka funktionerna.

Vid behov kan [Steg 5](windows10-enable-security-features.md#windows10-sec-atp) hjälpa dig med detta krav.

## <a name="results-and-next-steps"></a>Resultat och nästa steg

Windows 10 Enterprise-infrastruktur har förberetts för att påbörja installationen på nya enheter och uppgraderingar på plats på enheter som kör tidigare versioner av Windows, och du använder huvudfunktionerna för säkerhet i Windows 10 Enterprise.

|||
|:-------|:-----|
|![Fas 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| Om du följer faserna för distribution av Microsoft 365 Enterprise från slutpunkt till slutpunkt, är nästa fas [Office 365 ProPlus](office365proplus-infrastructure.md). |
