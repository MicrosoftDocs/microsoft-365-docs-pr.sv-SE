---
title: Distribuera skyddsfunktioner för hot i hela Microsoft 365
description: Få en översikt över skyddstjänster för hot och säkerhetsfunktioner i Microsoft 365 E5. Skydda dina användarkonton, enheter, e-postinnehåll med mera med Microsoft 365 E5.
keywords: microsoft threat protection, defender, setup, advanced threat protection, security, microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583226"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Distribuera skyddsfunktioner för hot i hela Microsoft 365 E5

Den här lösningen beskriver kraftfulla skyddsfunktioner i Microsoft 365 E5 och varför skydd mot hot är viktigt. Få en översikt över skydd mot hot i Microsoft 365 E5 och se hur du kan närmar dig konfiguration och konfiguration för din organisation.

## <a name="why-threat-protection-is-important"></a>Varför skydd mot hot är viktigt 

[Skadlig](/windows/security/threat-protection/intelligence/understanding-malware)programvara och avancerade cyberattacker, till exempel [fillösa hot,](/windows/security/threat-protection/intelligence/fileless-threats)är vanligt förekommande. Företag måste skydda sig själva och sina kunder med effektiva IT-säkerhetsfunktioner. Cyberattacker kan orsaka stora problem för organisationen, allt från förlust av förtroende till ekonomiska problem, verksamhetsproblem och mycket mer. Det är viktigt att skydda mot hot, men det kan vara svårt att avgöra var du ska fokusera organisationens tid, arbete och resurser. Microsoft 365 E5 kan hjälpa dig. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Skydd mot hot i Microsoft 365 E5

Microsofts säkerhetslösningar är inbyggda i våra produkter och tjänster. Automatiserings- och maskininlärningsfunktionerna minskar belastningen på dina säkerhetsteam för att se till att rätt objekt hanteras. Styrkan hos Microsoft-säkerhetslösningar bygger på signalerna vi bearbetar varje dag i vår [intelligenta Graph.](/graph/security-concept-overview) Microsoft 365-säkerhetslösningarna ingår [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), en lösning som sammanför signaler via e-post, data, enheter och identiteter för att måla en bild av avancerade hot mot din organisation.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) hjälper dig att skydda organisationen med anpassningsbar, inbyggd intelligens. Med säkerhetsfunktionerna i Microsoft 365 E5 kan du identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga åtgärder i din miljö (lokalt och i molnet).

## <a name="better-protection-with-integration"></a>Bättre skydd med integrering

I Microsoft 365 E5 är skyddsfunktioner för hot integrerade som standard. Signaler från varje funktion ger en hållfasthet för den övergripande möjligheten att upptäcka och reagera på hot. Den kombinerade uppsättningen funktioner ger det bästa skyddet för organisationer, särskilt multinationella organisationer, jämfört med att köra produkter som inte är från Microsoft. I följande bild visas de skyddstjänster för hot och funktioner som beskrivs i den här artikeln.

![Översikt över Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender samlar signalerna och data till ett [enhetligt Microsoft 365 säkerhetscenter](/microsoft-365/security/defender/overview-security-center). 

> [!div class="mx-imgBorder"]
> ![Konceptuell illustration av Microsoft 365 Defender-instrumentpanelen](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Distributionsöversikt

I följande bild visas en rekommenderad väg för att distribuera de här enskilda funktionerna. 

> [!div class="mx-imgBorder"]
> ![M365-hotskyddssignaler](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Titta på den här videon för att få en översikt över distributionsprocessen.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

I följande tabell beskrivs de olika lösningar/funktioner som du kan konfigurera och vad de gör.

|Steg |Lösning/funktioner  |Beskrivning  |
|--|---------|---------|
| 1 |[Multifaktorautentisering och Villkorsstyrd åtkomst](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Skydda mot komprometterade identiteter och enheter. Börja med det här skyddet eftersom det är grundligt. Den konfiguration som rekommenderas i den här vägledningen inkluderar Azure AD Identity Protection som en förutsättning. Mer information finns i [Azure AD Identity Protection.](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  En molnbaserad säkerhetslösning som använder dina lokala AD DS-signaler (Active Directory Domain Services) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktad mot organisationen. Fokusera sedan på Microsoft Defender för identitet eftersom det skyddar din lokala infrastruktur och molninfrastruktur, har inga beroenden eller krav och kan ge omedelbar säkerhetsfördelar. Mer information finns i [Vad är identitetsskydd?](/azure/active-directory/identity-protection/overview-identity-protection). | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Kombinerar signal- och satellitkapaciteter till en enda lösning. Gör det möjligt för säkerhetspersonal att samla ihop hotsignaler och fastställa ett hots fullständiga omfattning och påverkan. Microsoft 365 Defender vidtar automatiska åtgärder för att förhindra eller stoppa attacken och själv berörda postlådor, slutpunkter och användaridentiteter. Mer information finns i [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). |
| 4 |[Microsoft Defender för Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Skyddar mot skadlig programvara, nätfiske, förfalskning och andra attacktyper. Vi rekommenderar att du Office 365 Microsoft Defender för företag eftersom det kan ta längre tid att distribuera genom att ändra kontroll, migrera inställningar från klientsystemet och andra överväganden. Mer information finns i [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365).       |
| 5 |[Microsoft Defender för Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Hjälper till att förhindra, identifiera, undersöka och svara på avancerade hot på olika enheter (kallas även slutpunkter). Defender för Endpoint är ett kraftfullt skydd mot hot. Mer information finns i [Microsoft Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).  |
| 6 |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | En säkerhetsförmedlare för molnåtkomst för identifiering, undersökning och styrning. Du kan aktivera Microsoft Cloud App Security tidigt för att börja samla in data och insikter. Att implementera information och annat riktat skydd i SaaS-apparna innebär planering och kan ta längre tid. Mer information finns i [Vad är Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Organisationer som har flera säkerhetsteam kan implementera funktioner parallellt. Ett team kan till exempel konfigurera Defender för Office 365 medan ett annat team konfigurerar Defender för Slutpunkt. Konfigurationen behöver inte exakt följa vår föreslagna ordning. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planera att distribuera din lösning för hotskydd

I följande diagram visas en översiktsprocess för distribution av skyddsfunktioner mot hot. 

![Process för distribution av skyddsfunktioner för hot](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Se till att din organisation har bästa möjliga skydd genom att konfigurera och [distribuera din säkerhetslösning](deploy-threat-protection-configure.md) med en process som innehåller följande steg:

1. [Konfigurera principer för multifaktorautentisering och Villkorsstyrd åtkomst.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurera Microsoft Defender för identitet](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Aktivera Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Konfigurera Defender för Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Konfigurera Microsoft Defender för Slutpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Konfigurera Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Övervaka status och vidta åtgärder](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).
8. [Utbilda användare](deploy-threat-protection-configure.md#step-8-train-users).

Dina skyddsfunktioner för hot kan konfigureras parallellt, så om du har flera nätverkssäkerhetsgrupper som ansvarar för olika tjänster kan de konfigurera din organisations skyddsfunktioner samtidigt.

## <a name="next-step"></a>Nästa steg

Fortsätt till [Konfigurera skyddsfunktioner för hot i hela Microsoft 365.](deploy-threat-protection-configure.md)


