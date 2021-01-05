---
title: Övervaka och svara på data integritets incidenter i din organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Använd gransknings-och larm principer och data subjekt förfrågningar för att övervaka och svara på frågor om person uppgifter.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749593"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Övervaka och svara på data integritets incidenter i din organisation

Microsoft 365-funktioner är tillgängliga för att hjälpa dig att övervaka, undersöka och svara på data integritets incidenter i din organisation när du operationalize relaterade funktioner. Att ha processer, procedurer och annan dokumentation för var och en av dessa kan också vara viktiga för att påvisa efterlevnad av myndighets organ.

De omfattar: 

- Principer för granskning och avisering
- Data subjekt begär Anden (inklusive innehålls sökning och eDiscovery)
- Ytterligare verktyg och rapporter

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Data integritets regler som påverkar användning av övervaknings-och svars verktyg

Här är ett exempel på en lista över data integritets regler som kan gälla för informations styrnings kontroller:

- LGPD artikel 46
- LGPD artikel 48
- GDPR-artikel (5) (1) (f)
- GDPR-artikel (15) (1) (e)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (6) (II)
- HIPAA-HITECH (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Mer information finns i [utvärdera data integritets risker och identifiera känslig information](information-protection-deploy-assess.md).

Reglerna för data integritet tar vanligt vis upp följande för övervakning och svar:

- Granskning, avisering och rapportering för aktiviteter relaterade till lagring, delning och bearbetning av person uppgifter
- Möjligheten att svara på en fråga om data som kan besvaras (DSR) och i vissa fall genomföra utredning och andra administrativa åtgärder för att uppfylla sådana önskemål.

Organisationen kan också välja att utföra övervakning och svars aktiviteter i andra syften, till exempel andra behov eller av affärs skäl. Att fastställa övervaknings-och svars schema för data integritet ska utföras som en del av övergripande övervakning och svars planering, implementering och hantering.

För att hjälpa dig att komma igång med ett övervaknings-och svars schema i Microsoft 365 för data integritets regler, visar den här artikeln användbara funktioner i Microsoft 365 för att besvara frågor som: 

- Vilken sorts daglig övervakning, undersöknings-och rapporterings teknik finns tillgängliga för de olika data typerna och källorna?
- Vilka mekanismer behövs för att hantera data ämnes förfrågningar (DSRs) och eventuella hjälp åtgärder, till exempel anonymisering, bortredigering och borttagning.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Principer för granskning och larm i säkerhets-och kompatibilitetstillstånd

Se de här artiklarna för att konfigurera granskning, avancerad granskning och aviserings principer:

- [Enhetlig granskning](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postlådegranskning](../compliance/enable-mailbox-auditing.md)
- [Avancerad granskning](../compliance/advanced-audit.md)
- [Aviseringsprinciper](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Data subjekt begär Anden för GDPR och CCPA

Information om hur du svarar på en DSR-data i Microsoft 365 finns i artikeln om [GDPR och CCPA](../compliance/gdpr-dsr-office365.md) .

## <a name="manage-deleted-users-in-microsoft-stream"></a>Hantera borttagna användare i Microsoft Stream

För Microsoft Stream, när en användare tas bort från Azure Active Directory (Azure AD), om deras namn var kopplad till en bokförd direkt uppspelnings video innan den punkten förblir e-postadressen kopplad till videon. Se [Hantera borttagna användare från Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) för att ta bort den.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Insider riskhantering som ett undersöknings verktyg

[Insider riskhantering i microsoft 365](../compliance/insider-risk-management.md) är en funktion i Microsoft Support Administration Center som hjälper dig att minimera intern risken genom att låta dig upptäcka, undersöka och vidta åtgärder för riskfyllda aktiviteter i din organisation.
