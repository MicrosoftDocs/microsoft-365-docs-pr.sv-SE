---
title: Övervaka och svara på sekretessincidenter för data i din organisation
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
description: Använd gransknings- och aviseringsprinciper och dataförfrågningar för att övervaka och svara på incidenter med personuppgifter.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928430"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Övervaka och svara på sekretessincidenter för data i din organisation

Microsoft 365 funktioner finns tillgängliga så att du kan övervaka, undersöka och svara på datasekretessincidenter i din organisation när du driftiserar relaterade funktioner. Att ha processer, procedurer och annan dokumentation för var och en av dessa kan också vara viktigt för att visa efterlevnad för reglerande myndigheter.

De omfattar: 

- Gransknings- och aviseringsprinciper
- Dataförfrågningar från registrerade personer (inklusive innehållssökning och eDiscovery)
- Ytterligare verktyg för marknadsföring och rapportering

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Sekretessregler för data som påverkar användningen av övervaknings- och svarsverktyg

Här är ett exempel på en lista med regler för datasekretess som kan relatera till kontroller för informationsstyrning:

- LGPD, artikel 46
- LGPD, artikel 48
- GDPR-artikel (5)(1)(f)
- GDPR-artikel (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164,308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164,308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164,312(b))
- CCPA (1798.105(c))

Mer information finns i Utvärdera [datasekretessrisker och identifiera känslig information.](information-protection-deploy-assess.md)

Datasekretessbestämmelser uppmanar vanligtvis till följande för övervakning och svar:

- Granska, meddela och rapportera aktiviteter som rör lagring, delning och bearbetning av personuppgifter
- Möjligheten att svara på en data subject request (DSR) och i vissa fall utföra administrativa åtgärder för att uppfylla sådana begäranden.

Din organisation kan också vilja utföra övervaknings- och svarsaktiviteter för andra ändamål, till exempel för andra efterlevnadsbehov eller av företagsskäl. Att upprätta ett system för övervakning och svar för datasekretess bör göras som en del av den övergripande uppföljnings- och svarsplaneringen, -implementeringen och -hanteringen.

Den här artikeln innehåller användbara funktioner i Microsoft 365 för att hjälpa dig att komma igång med ett övervakning- och svarsschema i Microsoft 365 för bestämmelser om datasekretess: 

- Vilken typ av teknik för övervakning, undersökning och rapportering finns tillgänglig för olika datatyper och källor?
- Vilka mekanismer kommer att behövas för att hantera DSR-begäranden (Data Subject Requests) och alla åtgärder, till exempel anonymisering, redaion och borttagning.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Gransknings- och aviseringsprinciper i Säkerhets- och efterlevnadscenter

Läs följande artiklar för att konfigurera granskning, avancerad granskning och aviseringsprinciper:

- [Enhetlig granskning](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postlådegranskning](../compliance/enable-mailbox-auditing.md)
- [Avancerad granskning](../compliance/advanced-audit.md)
- [Aviseringsprinciper](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Data subject requests for the GDPR and CCPA

Se [Data Subject Requests för GDPR och CCPA för](/compliance/regulatory/gdpr-dsr-Office365) information om hur du svarar på en DSR i Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Hantera borttagna användare i Microsoft Stream

När en användare för Microsoft Stream tas bort från Azure Active Directory (Azure AD), och användarens namn var kopplat till en publicerad Stream-video innan den tidpunkten, förblir deras e-postadress kopplad till videon. Se [Hantera borttagna användare från Microsoft Stream om du vill](/stream/managing-deleted-users) ta bort dem.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Insider-riskhantering som ett effektivt verktyg

[Insider-riskhantering i Microsoft 365](../compliance/insider-risk-management.md) är en funktion i administrationscentret för Microsofts efterlevnad som hjälper dig att minimera den interna risken genom att du kan upptäcka, undersöka och vidta åtgärder för riskaktiviteter i organisationen.