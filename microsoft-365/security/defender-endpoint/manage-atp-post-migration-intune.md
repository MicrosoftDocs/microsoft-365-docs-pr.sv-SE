---
title: Hantera Microsoft Defender för slutpunkt med Intune
description: Lär dig hur du hanterar Microsoft Defender för slutpunkt med Intune
keywords: efter migrering, hantera, åtgärder, underhåll, användning, intune, Microsoft Defender för Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5ca16e125b1eb8377c3a591d039eb7da65b873fb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229101"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Hantera Microsoft Defender för slutpunkt med Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Vi rekommenderar att [du använder Microsoft Endpoint Manager](/mem), vilket inkluderar Microsoft Intune (Intune) för att hantera din organisations skyddsfunktioner för enheter (kallas även slutpunkter). [Läs mer om Endpoint Manager](/mem/endpoint-manager-overview).

I den här artikeln beskrivs hur du hittar dina inställningar för Microsoft Defender för slutpunkt i Intune och en lista med olika uppgifter som du kan utföra.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Hitta dina Microsoft Defender för slutpunktsinställningar i Intune

> [!IMPORTANT]
> Du måste vara global administratör eller tjänstadministratör i Intune för att konfigurera inställningarna som beskrivs i den här artikeln. Mer information finns i **[Typer av administratörer (Intune).](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Gå till Azure Portal ( [https://portal.azure.com](https://portal.azure.com) ) och logga in.

2. Under **Azure Services** väljer du **Intune**.

3. I navigeringsfönstret till vänster väljer du **Enhetskonfiguration och** sedan under **Hantera** väljer du **Profiler.**

4. Välj en befintlig profil eller skapa en ny.

> [!TIP]
> Behöver du hjälp? Se **[Använda Microsoft Defender för Slutpunkt med Intune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Konfigurera Microsoft Defender för slutpunkt med Intune

I följande tabell finns olika uppgifter som du kan utföra för att konfigurera Microsoft Defender för Slutpunkt med Intune. Du behöver inte konfigurera allt på en gång. välj en aktivitet, läs motsvarande resurser och fortsätt sedan.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera din organisations enheter med Intune för att** skydda de enheter och data som lagras på dem     |[Skydda enheter med Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Integrera Microsoft Defender för slutpunkt med Intune** som en lösning för skydd mot mobilhot <br/>*(för Android-enheter och enheter Windows 10 eller senare)*   |[Tillämpa efterlevnad för Microsoft Defender för Slutpunkt med villkorsstyrd åtkomst i Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Använda Villkorsstyrd** åtkomst för att styra vilka enheter och appar som kan ansluta till din e-post och företagets resurser |[Konfigurera villkorsstyrd åtkomst i Microsoft Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Konfigurera Microsoft Defender Antivirus med** hjälp av principkonfigurationstjänsten [(CSP)](/windows/client-management/mdm/policy-configuration-service-provider) |[Enhetsbegränsningar: Microsoft Defender Antivirus](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[Policy CSP – Microsoft Defender för Slutpunkt](/windows/client-management/mdm/policy-csp-defender)  | 
|**Om det behövs anger du undantag för Microsoft Defender Antivirus** <br/><br/>*I allmänhet ska du inte behöva tillämpa undantag. Microsoft Defender Antivirus omfattar ett antal automatiska undantag baserade på kända operativsystemsbeteenden och vanliga hanteringsfiler, till exempel de som används i företagshantering, databashantering och andra företagsscenarier.* |[Rekommendationer om virusskanning för Enterprise-datorer som kör versioner av Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Enhetsbegränsningar: Microsoft Defender Antivirus undantag för Windows 10 enheter](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Konfigurera Microsoft Defender Antivirus undantag i Windows Server 2016 eller 2019](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Konfigurera minskningsregler för attackytan** för att rikta programvarubeteenden som ofta används av attacker<br/><br/>*Konfigurera först dina minskningsregler för attackytan [i granskningsläge](/microsoft-365/security/defender-endpoint/audit-windows-defender) (i minst en vecka och upp till två månader). Du kan övervaka status med Power BI [(](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)skaffa vår mall ) och sedan ställa in dessa regler på aktivt läge när du är redo.* |[Granskningsläge i Microsoft Defender för slutpunkt](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Slutpunktsskydd: Minska attackytan](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Läs mer om minskningsregler för attackytor](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Tech Community-blogginlägg: Avmystifiera minskningsregler för attackytan – del 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Konfigurera nätverksfiltrering** för att blockera utgående anslutningar från valfri app till IP-adresser eller domäner med låga rykten  <br/><br/>*Nätverksfiltrering kallas även [nätverksskydd.](/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Kontrollera att Windows 10 enheter har de senaste [uppdateringarna för program mot skadlig](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) programvara installerade.*|[Slutpunktsskydd: Nätverksfiltrering](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Granska nätverksskyddshändelser i Windows Loggboken](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*[Kontrollerad mappåtkomst](/microsoft-365/security/defender-endpoint/controlled-folders) kallas även skydd mot skadlig programvara.*  |[Slutpunktsskydd: Reglerad mappåtkomst](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivera kontrollerad mappåtkomst i Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Konfigurera sårbarhetsskydd** för att skydda organisationens enheter från skadlig programvara som använder sårbarheter för att sprida och smitta andra enheter <br/><br/> *[Sårbarhetsskydd](/microsoft-365/security/defender-endpoint/exploit-protection) kallas även Exploit Guard.* |[Slutpunktsskydd: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Aktivera sårbarhetsskydd i Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Konfigurera Microsoft Defender SmartScreen** för att skydda mot skadliga webbplatser och filer på Internet. <br/><br/> *Microsoft Edge ska vara installerat på organisationens enheter. Konfigurera sårbarhetsskydd för skydd i Google Chrome- och FireFox-webbläsare.*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Enhetsbegränsningar: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Principinställningar för hantering av SmartScreen i Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Konfigurera Microsoft Defender-brandväggen** för att blockera obehörig nätverkstrafik som går till eller ut från din organisations enheter  |[Slutpunktsskydd: Microsoft Defender-brandväggen](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender-brandväggen med avancerad säkerhet](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Konfigurera kryptering och BitLocker** för att skydda information på organisationens enheter som kör Windows |[Slutpunktsskydd: Windows kryptering](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker för Windows 10 enheter](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Konfigurera Microsoft Defender Credential Guard för** att skydda mot autentiseringsstöldattacker |Mer Windows 10, Windows Server 2016 och Windows Server 2019 finns i [Slutpunktsskydd: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>För Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 och Windows Server 2012 R2, se [Mitigating Pass-the-Hash-attacker (PtH)-attacker och andra autentiseringsstölder, version 1 och 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Konfigurera Microsoft Defender-programkontroll** för att välja om du vill granska eller lita på appar på din organisations enheter <br/><br/>*Microsoft Defender-programkontroll kallas även [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Distribuera programkontrollsprinciper för Microsoft Defender med hjälp av Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Slutpunktsskydd: Microsoft Defender-programkontroll](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker-CSP](/windows/client-management/mdm/applocker-csp)|
|**Konfigurera åtkomst till enhetsstyrning och USB-kringutrustning** för att förhindra hot om obehörig kringutrustning från att komprometteras dina enheter |[Kontrollera USB-enheter och andra flyttbara medium med hjälp av Microsoft Defender för Endpoint och Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du din Microsoft 365 Defender-portal för att visa varningar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande säkerhetsvarning. Se [Microsoft Defender Säkerhetscenter](microsoft-defender-security-center.md). Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft 365 Defender portalen.

- [Översikt över Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nästa steg

- [Få en översikt över Hantering av hot och säkerhetsrisker](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen Microsoft Defender Säkerhetscenter säkerhetsåtgärder](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
