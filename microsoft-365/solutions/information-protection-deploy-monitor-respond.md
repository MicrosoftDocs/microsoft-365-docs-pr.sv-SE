---
title: Övervaka och svara på datasekretessincidenter i din organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Använd gransknings- och varningspolicyer och förfrågningar från registrerade för att övervaka och svara på personuppgiftsincidenter.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522079"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Övervaka och svara på datasekretessincidenter i din organisation

Microsoft 365-funktioner är tillgängliga för att hjälpa dig att övervaka, undersöka och svara på datasekretessincidenter i organisationen när du operationaliserar relaterade funktioner. Att ha processer, förfaranden och annan dokumentation för var och en av dessa kan också vara viktigt för att visa att tillsynsorganen följer reglerna.

De omfattar: 

- Gransknings- och varningsprinciper
- Förfrågningar från registrerade (inklusive innehållssökning och eDiscovery)
- Ytterligare utredningsverktyg och rapportering

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Bestämmelser om datasekretess som påverkar användningen av övervaknings- och svarsverktyg

Här är ett exempel på datasekretessregler som kan relatera till informationsstyrningskontroller:

- LGPD Artikel 46
- LGPD Artikel 48
- GDPR Artikel 5.1 f
- GDPR Artikel 15.1 e
- HIPAA-HITECH (45 C.F.R. 164.308 a.1 ii(D))
- HIPAA-HITECH (45 C.F.R. 164.308 a.6 ii
- HIPAA-HITECH (45 C.F.R. 164.312 b)
- CCPA (1798.105(c))

Mer information finns i [Bedöma datasekretessrisker och identifiera känslig information](information-protection-deploy-assess.md).

Reglerna för datasekretess kräver i allmänhet följande för övervakning och svar:

- Granskning, registrering och rapportering för aktiviteter som rör lagring, delning och behandling av personuppgifter
- Möjligheten att svara på en registrerad begäran (DSR) och i vissa fall utföra utredningsåtgärder och andra administrativa åtgärder för att uppfylla sådana förfrågningar.

Din organisation kan också vilja utföra övervaknings- och svarsaktiviteter för andra ändamål, till exempel andra efterlevnadsbehov eller av affärsmässiga skäl. Upprätta ditt övervaknings- och svarssystem för datasekretess bör göras som en del av övergripande övervaknings- och svarsplanering, implementering och hantering.

För att hjälpa dig att komma igång med ett övervaknings- och svarsschema i Microsoft 365 för datasekretessbestämmelser innehåller den här artikeln en lista över användbara funktioner i Microsoft 365 för att svara på frågor som: 

- Vilken typ av daglig övervaknings-, utrednings- och rapporteringsteknik finns tillgänglig för de olika datatyperna och källorna?
- Vilka mekanismer kommer att behövas för att hantera registrerade förfrågningar (DSRs) och eventuella avhjälpande åtgärder, till exempel anonymisering, bortredigeringsverktyg och radering.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Gransknings- och varningsprinciper i säkerhets- och efterlevnadscentret

Se de här artiklarna för att konfigurera gransknings-, avancerade gransknings- och varningsprinciper:

- [Enhetlig granskning](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postlådegranskning](../compliance/enable-mailbox-auditing.md)
- [Avancerad granskning](../compliance/advanced-audit.md)
- [Aviseringsprinciper](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Registrerades begäran om GDPR och CCPA

Se [Registrerade förfrågningar om GDPR och CCPA](../compliance/gdpr-dsr-office365.md) för information om hur du svarar på en DSR i Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Hantera borttagna användare i Microsoft Stream

När en användare tas bort från Azure Active Directory (Azure AD) för Microsoft Stream, om deras namn var associerat med en postad Stream-video före den punkten, förblir deras e-postadress associerad med videon. Se [Hantera borttagna användare från Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) om du vill ta bort den.

## <a name="additional-investigative-tools"></a>Ytterligare utredningsverktyg

Här är ytterligare två verktyg som kan vara användbara för att övervaka, undersöka och åtgärda datasekretessrelaterade incidenter i organisationen:

- [Insider-riskhantering i Microsoft 365](../compliance/insider-risk-management.md), en funktion i Microsoft Compliances administrationscenter för att minimera interna risker genom att du kan identifiera, undersöka och vidta åtgärder för riskfyllda aktiviteter i organisationen.
- [Dataundersökningar i Microsoft 365](../compliance/overview-data-investigations.md), en funktion i Microsoft Compliance admin center för att söka efter känsliga, skadliga eller felplacerade data över Microsoft 365, och sedan undersöka vad som hände med att vidta lämpliga åtgärder för att åtgärda händelsen.
