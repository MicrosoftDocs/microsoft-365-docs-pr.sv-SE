---
title: Distribuera hot Protection-funktioner i Microsoft 365
description: Lär dig hur du distribuerar hot Protection Services och funktioner i Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 312df25bf4fe2b91bb60b4122378b4457b25723c
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588190"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Distribuera hot Protection-funktioner i Microsoft 365

[Skadlig program](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)vara och sofistikerade cyberattacks, till exempel [Filskydd](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), är ofta en vanlig förekomst. Företagen måste skydda sig själva och deras kunder. Cyberterrorism säkerhets attacker kan orsaka större problem i din organisation, från förlust av förtroende till ekonomisk woes, Business-hotar nertid och mer. Det är viktigt att skydda mot hot, men det kan vara svårt att avgöra var du ska fokusera din organisations tid, ansträngning och resurser. 

Microsoft Security Solutions är inbyggda i våra produkter och tjänster. Automatiserings-och maskin inlärnings funktioner minskar belastningen på dina säkerhets team för att se till att rätt objekt adresseras. Och styrkan hos Microsoft Security Solutions bygger på biljon tals won som vi behandlar varje dag i vårt [intelligenta säkerhets diagram](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph). Microsoft 365-säkerhetslösningar innehåller [hot mot Microsoft Threat](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)som sammankopplar dina e-postmeddelanden, data, enheter och identiteter för att måla en bild av avancerade hot mot din organisation.

Titta på den här videon för en översikt över distributions processen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Använd den här artikeln som en guide för implementering av skydds lösning för hotet.

## <a name="threat-protection-in-microsoft-365-e5"></a>Hot Protection in Microsoft 365 E5

Med [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kan du skydda din organisation med anpassningsbar, inbyggd intelligens. Med hotet Protection-funktionerna i Microsoft 365 E5 kan du upptäcka och undersöka avancerade hot, kompromissade identiteter och illasinnade åtgärder i din lokala och moln miljö.

I Microsoft 365 E5 är skydds funktionerna för hotet som standard integrerade. Signaler från varje kapacitet till helhet för att upptäcka och reagera på hot. Den kombinerade uppsättningen funktioner ger det bästa skyddet för organisationer, särskilt flera nationella organisationer, jämfört med produkter som inte kommer från Microsoft. Följande bild illustrerar hotet Protection Services och funktioner i Microsoft 365 E5 som beskrivs i den här artikeln.

![Översikt över skydd mot Microsoft Threat](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Så fort du har distribuerat någon av de avancerade skydds funktionerna kan du aktivera skyddet mot Microsoft Threats, vilket gör att signalerna och data samlas på ett och samma ställe. 

![Koncept bild av instrument panelen för Microsoft Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

Följande bild visar en rekommenderad sökväg för distribution av de här enskilda funktionerna. 

![M365 hot Protection-signaler](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Lösning/funktioner  |Beskrivning  |
|---------|---------|
|Multifaktorautentisering och villkorlig åtkomst     |Skydda mot kompromissade identiteter och enheter. Börja med det här skyddet eftersom det är grundläggande. Konfigurationen som rekommenderas i den här vägledningen inkluderar ett krav för Azure AD Identity-skydd.     |
|Azure Advanced Threat Protection     |  En molnbaserad säkerhets lösning som använder dina lokala Active Directory-signaler för att identifiera, upptäcka och undersöka avancerade hot, kompromissade identiteter och skadliga Insider-åtgärder som riktas till din organisation. Fokusera på Avancerat Azure-skydd eftersom det skyddar din lokala och moln infrastrukturen, har inga beroenden eller förutsättningar och kan ge omedelbara fördelar.       | 
|Office 365 Avancerat skydd     | Skyddar din organisation mot illasinnade hot via e-postmeddelanden, länkar (URL: er) och samarbets verktyg. Skydd mot skadlig program vara, nätfiske, förfalskning och andra typer av attacker. Konfigurera Office 365 Avancerat skydd rekommenderas nästa eftersom ändrings kontroll, migrering av inställningar från systemet och andra överväganden kan ta längre tid att distribuera. <br><br>Obs! se till att konfigurera hot skydds funktionerna som ingår i alla Office 365-prenumerationer (Exchange Online Protection).       |
|Microsoft Defender Avancerat skydd    | En Endpoint Protection-plattform som hjälper till att förhindra, upptäcka, undersöka och svara på avancerade hot. Microsoft Defender Avancerat skydd kan ta lite tid att distribuera, men konfigurationen kan göras parallellt med andra funktioner.   |
|Microsoft Cloud App Security     |   En säkerhets koordinator för moln åtkomst för identifiering, undersökning och styrning. Du kan aktivera Microsoft Cloud App Security för att börja samla in data och insikter. Att implementera information och annat riktat skydd i dina SaaS-program inkluderar planering och kan ta längre tid.       | 

> [!TIP]
> Organisationer med flera säkerhets team kan implementera dessa funktioner parallellt.

## <a name="deploy-your-threat-protection-solution"></a>Distribuera skydds lösning för hotet

Om du vill vara säker på att organisationen har bästa möjliga skydd kan du ställa in och distribuera din säkerhets lösning så här:

1. [Konfigurera principer för multifaktorautentisering och villkorsstyrd åtkomst](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurera Avancerat skydd för Azure](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [Aktivera Microsoft Hotskydd](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [Konfigurera Office 365 Avancerat skydd](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [Konfigurera Microsoft Defender Avancerat skydd](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Konfigurera säkerhet för Microsoft Cloud App](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Övervaka status och utför åtgärder](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Utbilda användare](deploy-threat-protection-configure.md#step-8-train-users)

Skydds funktionerna för hotet kan konfigureras parallellt, så om du har flera säkerhets team ansvariga för olika tjänster kan de konfigurera organisationens skydds funktioner samtidigt. Följande diagram illustrerar den omfattande processen för distribution av skydds funktioner. 

![Process för distribution av hot Protection-funktioner](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


