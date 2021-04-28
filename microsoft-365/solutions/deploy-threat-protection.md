---
title: Distribuera skyddsfunktioner för hot i Microsoft 365
description: Få en översikt över skyddstjänster för hot och säkerhetsfunktioner i Microsoft 365 E5. Skydda dina användarkonton, enheter, e-postinnehåll med mera med Microsoft 365 E5.
keywords: avancerat skydd mot hot, säkerhet, microsoft 365 E5, lösning, skydda enheter, defender
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
ms.openlocfilehash: 0edc3847d6b832f254c6f289355570a3a044b1f4
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061043"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Distribuera skyddsfunktioner för hot i Microsoft 365 E5

Den här lösningen beskriver kraftfulla skyddsfunktioner i Microsoft 365 E5 och varför dessa funktioner är viktiga. Läs den här lösningen för att få en översikt över vad som ingår i Microsoft 365 E5, hur skyddsfunktioner för hot fungerar och hur du konfigurerar skydd mot hot i din organisation.

## <a name="why-threat-protection-is-important"></a>Varför skydd mot hot är viktigt 

[Skadlig](/windows/security/threat-protection/intelligence/understanding-malware)programvara och avancerade cyberattacker, till exempel [fillösa hot,](/windows/security/threat-protection/intelligence/fileless-threats)är vanligt förekommande. Företag måste skydda sig själva och sina kunder med effektiva IT-säkerhetsfunktioner. Cyberattacker kan orsaka stora problem för organisationen, allt från förlust av förtroende till ekonomiska problem, verksamhetsproblem och mycket mer. Det är viktigt att skydda mot hot, men det kan vara svårt att avgöra var du ska fokusera organisationens tid, arbete och resurser. Microsoft 365 E5 kan hjälpa dig. 

Microsofts säkerhetslösningar är inbyggda i våra produkter och tjänster. Automatiserings- och maskininlärningsfunktionerna minskar belastningen på dina säkerhetsteam för att se till att rätt objekt hanteras. Och styrkan hos Microsoft-säkerhetslösningar bygger på att vi använder signalerna vi bearbetar varje dag i vår [Intelligenta säkerhetsdiagram.](/graph/security-concept-overview) Microsoft 365-säkerhetslösningar är bland annat [Microsoft 365 Defender,](../security/defender/microsoft-365-defender.md)en lösning som för samman signaler i din e-post, dina data, enheter och identiteter för att måla en bild av avancerade hot mot din organisation.

Titta på den här videon för att få en översikt över distributionsprocessen.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a>Skydd mot hot i Microsoft 365 E5

[Med Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kan du skydda organisationen med anpassningsbar, inbyggd intelligens. Med funktionerna för skydd mot hot i Microsoft 365 E5 kan du identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga åtgärder i din lokala och molnbaserade miljö.

I Microsoft 365 E5 är skyddsfunktioner integrerade som standard. Signaler från varje funktion ger en hållfasthet för den övergripande möjligheten att upptäcka och reagera på hot. Den kombinerade uppsättningen funktioner ger det bästa skyddet för organisationer, särskilt multinationella organisationer, jämfört med att köra produkter som inte är från Microsoft. I följande bild visas skyddstjänster för hot och funktioner i Microsoft 365 E5 som beskrivs i den här artikeln.

![Översikt över Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender för samman signalerna och data till ett [enhetligt Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Konceptbild av Microsoft 365 Defender-instrumentpanelen](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

I följande bild visas en rekommenderad väg för att distribuera de här enskilda funktionerna. 

> [!div class="mx-imgBorder"]
> ![M365-hotskyddssignaler](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Lösning/funktioner  |Beskrivning  |
|---------|---------|
|Multifaktorautentisering och Villkorsstyrd åtkomst     |Skydda mot komprometterade identiteter och enheter. Börja med det här skyddet eftersom det är grundligt. Den konfiguration som rekommenderas i den här vägledningen inkluderar Azure AD Identity Protection som en förutsättning.     |
|Microsoft Defender for Identity     |  En molnbaserad säkerhetslösning som utnyttjar dina lokala AD DS-signaler (Active Directory Domain Services) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktad mot organisationen. Fokusera sedan på Microsoft Defender för identitet eftersom det skyddar din lokala infrastruktur och molninfrastruktur, har inga beroenden eller krav och kan ge omedelbar säkerhetsfördelar. | 
|Microsoft Defender för Office 365     | Skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Skydd mot skadlig programvara, nätfiske, förfalskning och andra attacktyper. Vi rekommenderar sedan att du konfigurerar Microsoft Defender för Office 365 eftersom det kan ta längre tid att distribuera om du ändrar kontrollen, migrerar inställningar från ett system för miljön och andra överväganden. <p>**OBS!** Konfigurera funktionerna för skydd mot hot som ingår i alla Office 365-prenumerationer (Exchange Online Protection).       |
|Microsoft Defender för Endpoint    | En plattform för slutpunktsskydd som hjälper till att förhindra, upptäcka, undersöka och hantera avancerade hot.  Defender för Endpoint kan ta lite tid att distribuera, men konfigurationen kan göras parallellt med andra funktioner.   |
|Microsoft Cloud App Security     |   En säkerhetsförmedlare för molnåtkomst för identifiering, undersökning och styrning. Du kan aktivera Microsoft Cloud App Security tidigt för att börja samla in data och insikter. Att implementera information och annat riktat skydd i SaaS-apparna innebär planering och kan ta längre tid.       | 

> [!TIP]
> Organisationer som har flera säkerhetsteam kan implementera dessa funktioner parallellt. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planera att distribuera din lösning för hotskydd

I följande diagram visas en översiktsprocess för distribution av skyddsfunktioner mot hot. 

![Process för distribution av skyddsfunktioner för hot](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Se till att din organisation har bästa möjliga skydd genom att konfigurera och distribuera din säkerhetslösning genom att använda en process som innehåller följande steg:

1. [Konfigurera principer för multifaktorautentisering och Villkorsstyrd åtkomst.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurera Microsoft Defender för identitet](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Aktivera Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Konfigurera Defender för Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Konfigurera Microsoft Defender för Slutpunkt](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Konfigurera Microsoft Cloud App-säkerhet](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Övervaka status och vidta åtgärder](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).
8. [Utbilda användare](deploy-threat-protection-configure.md#step-8-train-users).

Dina skyddsfunktioner för hot kan konfigureras parallellt, så om du har flera nätverkssäkerhetsgrupper som ansvarar för olika tjänster kan de konfigurera din organisations skyddsfunktioner samtidigt.

## <a name="next-step"></a>Nästa steg

Gå vidare [till Konfigurera skyddsfunktioner för hot i Microsoft 365.](deploy-threat-protection-configure.md)


