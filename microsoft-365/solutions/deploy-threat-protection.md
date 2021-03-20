---
title: Distribuera skyddsfunktioner för hot i Microsoft 365
description: Lär dig hur du distribuerar skyddstjänster för hot och säkerhetsfunktioner i Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 3156e6bc7715db9847b295add7850dcbd0ff6642
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918412"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Distribuera skyddsfunktioner för hot i Microsoft 365

[Skadlig](/windows/security/threat-protection/intelligence/understanding-malware)programvara och avancerade cyberattacker, till exempel [fillösa hot,](/windows/security/threat-protection/intelligence/fileless-threats)är vanligt förekommande. Företag måste skydda sig själva och sina kunder med effektiva IT-säkerhetsfunktioner. Cyberattacker kan orsaka stora problem för organisationen, allt från förlust av förtroende till ekonomiska problem, verksamhetsproblem och mycket mer. Det är viktigt att skydda mot hot, men det kan vara svårt att avgöra var du ska fokusera organisationens tid, arbete och resurser. 

Microsofts säkerhetslösningar är inbyggda i våra produkter och tjänster. Automatiserings- och maskininlärningsfunktionerna minskar belastningen på dina säkerhetsteam för att se till att rätt objekt hanteras. Och styrkan hos Microsoft-säkerhetslösningar bygger på att vi använder signalerna vi bearbetar varje dag i vår [Intelligenta säkerhetsdiagram.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Microsoft 365-säkerhetslösningar är bland annat [Microsoft 365 Defender,](../security/mtp/microsoft-threat-protection.md)en lösning som för samman signaler i din e-post, dina data, enheter och identiteter för att måla en bild av avancerade hot mot din organisation.


Titta på den här videon för att få en översikt över distributionsprocessen.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Använd den här artikeln som en guide för att implementera din lösning för hotskydd.

## <a name="threat-protection-in-microsoft-365-e5"></a>Skydd mot hot i Microsoft 365 E5

[Med Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kan du skydda organisationen med anpassningsbar, inbyggd intelligens. Med funktionerna för skydd mot hot i Microsoft 365 E5 kan du identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga åtgärder i din lokala och molnbaserade miljö.

I Microsoft 365 E5 är skyddsfunktioner integrerade som standard. Signaler från varje funktion ger en hållfasthet för den övergripande möjligheten att upptäcka och reagera på hot. Den kombinerade uppsättningen funktioner ger det bästa skyddet för organisationer, särskilt multinationella organisationer, jämfört med att köra produkter som inte är från Microsoft. I följande bild visas skyddstjänster för hot och funktioner i Microsoft 365 E5 som beskrivs i den här artikeln.

![Översikt över Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Så snart du har distribuerat någon av Defender för Office 365-funktionerna kan du aktivera Microsoft 365 Defender, som samlar signalerna och data på ett ställe. 

![Konceptbild av Microsoft 365 Defender-instrumentpanelen](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

I följande bild visas en rekommenderad väg för att distribuera de här enskilda funktionerna. 

![M365-hotskyddssignaler](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Lösning/funktioner  |Beskrivning  |
|---------|---------|
|Multifaktorautentisering och Villkorsstyrd åtkomst     |Skydda mot komprometterade identiteter och enheter. Börja med det här skyddet eftersom det är grundligt. Den konfiguration som rekommenderas i den här vägledningen inkluderar Azure AD Identity Protection som en förutsättning.     |
|Microsoft Defender for Identity     |  En molnbaserad säkerhetslösning som utnyttjar dina lokala AD DS-signaler (Active Directory Domain Services) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktad mot organisationen. Fokusera sedan på Microsoft Defender för identitet eftersom det skyddar din lokala infrastruktur och molninfrastruktur, har inga beroenden eller krav och kan ge omedelbar säkerhetsfördelar. | 
|Microsoft Defender för Office 365     | Skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Skydd mot skadlig programvara, nätfiske, förfalskning och andra attacktyper. Vi rekommenderar sedan att du konfigurerar Microsoft Defender för Office 365 eftersom det kan ta längre tid att distribuera om du ändrar kontrollen, migrerar inställningar från ett system för miljön och andra överväganden. <br><br>Obs! Se till att konfigurera funktionerna för skydd mot hot som ingår i alla Office 365-prenumerationer (Exchange Online Protection).       |
|Microsoft Defender för Endpoint    | En plattform för slutpunktsskydd som hjälper till att förhindra, upptäcka, undersöka och hantera avancerade hot.  Defender för Endpoint kan ta lite tid att distribuera, men konfigurationen kan göras parallellt med andra funktioner.   |
|Microsoft Cloud App Security     |   En säkerhetsförmedlare för molnåtkomst för identifiering, undersökning och styrning. Du kan aktivera Microsoft Cloud App Security tidigt för att börja samla in data och insikter. Att implementera information och annat riktat skydd i SaaS-apparna innebär planering och kan ta längre tid.       | 

> [!TIP]
> Organisationer med flera säkerhetsteam kan implementera dessa funktioner parallellt.

## <a name="deploy-your-threat-protection-solution"></a>Distribuera din lösning för skydd mot hot

Se till att din organisation har bästa möjliga skydd genom att konfigurera och distribuera din säkerhetslösning så att följande steg ingår:

1. [Konfigurera principer för multifaktorautentisering och villkorsstyrd åtkomst](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurera Microsoft Defender för identitet](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Aktivera Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Konfigurera Defender för Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Konfigurera Microsoft Defender för slutpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Konfigurera Microsoft Cloud App-säkerhet](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Övervaka status och vidta åtgärder](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Utbilda användare](deploy-threat-protection-configure.md#step-8-train-users)

Dina skyddsfunktioner för hot kan konfigureras parallellt, så om du har flera nätverkssäkerhetsgrupper som ansvarar för olika tjänster kan de konfigurera din organisations skyddsfunktioner samtidigt. I följande diagram visas en översiktsprocess för distribution av skyddsfunktioner mot hot. 

![Process för distribution av skyddsfunktioner för hot](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)