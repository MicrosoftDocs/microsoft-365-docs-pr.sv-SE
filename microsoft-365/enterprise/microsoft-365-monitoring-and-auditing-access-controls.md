---
title: Microsoft 365 övervakning och granskning av Access-kontroller
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 'Sammanfattning: en sammanfattning av de olika kontroll-och gransknings kontroller som finns tillgängliga i Microsoft 365.'
ms.openlocfilehash: f1302c4056bfd605e35aae08d8f5355f8d204db2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694645"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a>Övervaka och granska Access-kontroller i Microsoft 365

Microsoft utför omfattande övervakning och granskning av alla delegeringar, behörigheter och åtgärder som sker i Microsoft 365. Microsoft 365 Access Control är en automatiserad process som är inbyggd i principen om minst privilegium och som innehåller kontroller för data åtkomst och granskningar:

- Alla tillåtna åtkomster går att spåra till en unik användare. Det är möjligt för administratörer att hantera kund innehåll.
- Förfrågningar om åtkomst kontroll, godkännande och administrativa åtgärder sparas för att analysera säkerhets-och illvilliga händelser.
- Åtkomst nivåer granskas i nära real tid baserat på medlemskap i säkerhets grupper för att säkerställa att endast användare som har godkänt företags berättigande och uppfyller villkoren för berättigande åtkomst till systemen.
- Microsoft 365, dess Access-kontroller och stöd tjänster, inklusive Azure Active Directory och fysiska data Center, granskas regelbundet av oberoende tredje parter för att uppfylla [ISO/iec 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)och andra [standarder](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).
- Microsoft 365-tekniker måste vidta årlig säkerhetsutbildning, granska utökade åtkomst rekommendationer och bekräfta Microsofts säkerhets-och integritets policyer för att underhålla tjänsten.

Automatiska larm utlöses när misstänkt aktivitet identifieras, till exempel flera misslyckade inloggningar inom en kort tids period. Microsoft 365 Security Response-teamet använder dator inlärning och omfattande data analys för att granska och analysera aktivitet, leta efter oregelbunden åtkomst mönster och proaktiva reagera på avvikande och olagliga aktiviteter. Microsoft samarbetar också med en särskild grupp av utträngda testare och deltar i det återkommande röda teamet och blå grupp-övningar för att hitta säkerhets-och åtkomst kontroll problem i tjänsten. Kunder kan kontrol lera effektiviteten hos åtkomst kontroll systemen genom att använda gransknings rapporter och API: et för hanterings aktivitet som tillhandahålls av Microsoft 365.

Mer information finns i [referens för hanterings aktivitet](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) och [granskning och rapportering 365 av aktiviteter i](microsoft-365-auditing-and-reporting-overview.md)Office 365.
