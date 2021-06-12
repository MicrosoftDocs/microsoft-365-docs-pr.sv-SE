---
title: Hantera Microsoft Defender för slutpunkt med grupprincipobjekt
description: Lär dig hur du hanterar Microsoft Defender för slutpunkt med grupprincipobjekt
keywords: efter migrering, hantera, åtgärder, underhåll, användning, PowerShell, Microsoft Defender för Endpoint, edr
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
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908299"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Hantera Microsoft Defender för slutpunkt med grupprincipobjekt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Vi rekommenderar att [Microsoft Endpoint Manager](/mem) du använder för att hantera din organisations skyddsfunktioner för hot för enheter (kallas även slutpunkter). Endpoint Manager omfattar [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). **[Läs mer om Endpoint Manager](/mem/endpoint-manager-overview)**. 

Du kan använda grupprincipobjekt i Azure Active Directory Domain Services för att hantera vissa inställningar i Microsoft Defender för Slutpunkt.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Konfigurera Microsoft Defender för slutpunkt med grupprincipobjekt

I följande tabell finns olika uppgifter som du kan utföra för att konfigurera Microsoft Defender för Slutpunkt med grupprincipobjekt.

|Uppgift  |Resurser för att få mer information  |
|---------|---------|
|**Hantera inställningar för användar- och datorobjekt** <br/><br/>*Anpassa inbyggda grupprincipobjekt eller skapa anpassade grupprincipobjekt och organisationsenheter så att de passar organisationens behov.*     |[Administrera grupprinciper i en domän som hanteras Azure Active Directory Domain Services](/azure/active-directory-domain-services/manage-group-policy)   |
|**Konfigurera Microsoft Defender Antivirus** <br/><br/>*Konfigurera antivirusfunktioner & funktioner, inklusive principinställningar, undantag, åtgärder och schemalagda genomsökningar på organisationens enheter (kallas även slutpunkter).*   |[Använda grupprincipinställningar för att konfigurera och hantera Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Använda grupprinciper för att aktivera moln levererat skydd](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Hantera organisationens minskningsregler för attackytor** <br/><br/>*Anpassa dina minskningsregler för attackytan genom att utesluta filer & mappar eller genom att lägga till anpassad text i aviseringar som visas på användarnas enheter.* |[Anpassa minskningsregler för attackytor med grupprincipobjekt](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Hantera inställningar för sårbarhetsskydd**<br/><br/>*Du kan anpassa inställningarna för sårbarhetsskydd, importera en konfigurationsfil och sedan använda grupprincipen för att distribuera konfigurationsfilen.*  |[Anpassa inställningarna för sårbarhetsskydd](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Konfigurationer för att import, export och distribuering av exploateringsskydd](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Distribuera konfigurationen med grupprinciper](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Aktivera nätverksskydd för** att förhindra att anställda använder program som skadligt innehåll på Internet <br/><br/>*Vi rekommenderar att [du först](/microsoft-365/security/defender-endpoint/evaluate-network-protection) använder granskningsläge för nätverksskydd i en testmiljö för att se vilka appar som ska blockeras innan de lanseras.* |[Aktivera nätverksskydd med grupprincip](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Konfigurera kontrollerad mappåtkomst för** att skydda mot utpressningstrojaner <br/><br/>*[Kontrollerad mappåtkomst](/microsoft-365/security/defender-endpoint/controlled-folders) kallas även skydd mot skadlig programvara.*  |[Aktivera reglerad mappåtkomst med grupprincip](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Konfigurera Microsoft Defender SmartScreen** för att skydda mot skadliga webbplatser och filer på Internet.  |[Konfigurera Microsoft Defender SmartScreen grupprincip och MDM-inställningar (Mobile Device Management) med grupprincip](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Konfigurera kryptering BitLocker** skydda information på organisationens enheter som kör Windows |[BitLocker Grupprincipinställningar](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Konfigurera Microsoft Defender Credential Guard för** att skydda mot autentiseringsstöldattacker |[Aktivera Windows Defender Credential Guard med grupprincip](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurera Microsoft Defender Säkerhetscenter

Om du inte redan har gjort det konfigurerar du din Microsoft 365 Defender-portal för att visa aviseringar, konfigurera skyddsfunktioner för hot och visa detaljerad information om organisationens övergripande säkerhetsvarning. Se [Microsoft Defender Säkerhetscenter](microsoft-defender-security-center.md). Du kan också konfigurera om och vilka funktioner slutanvändare kan se i Microsoft 365 Defender-portalen.

- [Översikt över Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/use)

- [Slutpunktsskydd: Microsoft Defender Säkerhetscenter](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nästa steg

- [Få en översikt över Hantering av hot och säkerhetsrisker](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besök instrumentpanelen Microsoft Defender Säkerhetscenter säkerhetsåtgärder](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Hantera Microsoft Defender för slutpunkt med Intune](manage-atp-post-migration-intune.md)
