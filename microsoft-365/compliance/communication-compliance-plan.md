---
title: Planera för kommunikationsefterlevnad
description: Lär dig mer om hur du planerar att använda kommunikationsefterlevnad i din organisation.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "52161607"
---
# <a name="plan-for-communication-compliance"></a>Planera för kommunikationsefterlevnad

Innan du kommer igång [med kommunikationsefterlevnad](communication-compliance.md) i organisationen finns det viktiga planeringsaktiviteter och överväganden som bör granskas av dina grupper för informationsteknik och efterlevnadshantering. Genom att noggrant förstå och planera för distribution inom följande områden kan du säkerställa att din implementering och användning av funktionerna för kommunikationsefterlevnad går smidigt och överensstämmer med metodtipsen för lösningen.

## <a name="work-with-stakeholders-in-your-organization"></a>Arbeta med intressenter i organisationen

Identifiera rätt intressenter i organisationen för att samarbeta för att vidta åtgärder för aviseringar om kommunikationsefterlevnad. Några rekommenderade intressenter att överväga att ta med [](communication-compliance.md#workflow) i den inledande planeringen och arbetsflödet för att säkerställa att meddelanden efterlevs är personer från följande områden i organisationen:

- Informationsteknik
- Efterlevnad
- Sekretess
- Säkerhet
- Personalavdelningen
- Juridiskt

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planera för undersöknings- och åtgärdsarbetsflödet

Välj dedikerade intressenter för att övervaka och granska aviseringar och ärenden regelbundet i [Microsoft 365 efterlevnadscenter.](https://compliance.microsoft.com/) Se till att du förstår hur du tilldelar användare och intressenter till olika rollgrupper för kommunikationsefterlevnad i organisationen.

Beroende på hur du vill hantera kommunikationsprinciper och aviseringar måste du tilldela användare en eller flera rollgrupper för administratörer, granskare och administratörer. Du har möjlighet att tilldela användare till specifika rollgrupper för att hantera olika uppsättningar av funktioner för kommunikationsefterlevnad. Eller så kanske du bestämmer dig för att tilldela alla användare som använder kommunikationsefterlevnad till rollgruppen för kommunikationsefterlevnad. Använd en rollgrupp eller flera grupper för att bäst passa kraven på efterlevnadshantering.

Planera att välja bland de här rollgruppsalternativen när du konfigurerar kommunikationsefterlevnad:

|**Roll**|**Rollbehörigheter**|
|:-----|:-----|
| **Kommunikationsefterlevnad** | Använd den här rollgruppen för att hantera kommunikationsefterlevnad för organisationen i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker, slutanvändare och läsare kan du konfigurera behörigheter för kommunikationsefterlevnad i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för kommunikationsefterlevnad. Den här konfigurationen är det enklaste sättet att snabbt komma igång med kommunikationsefterlevnad och är en god passform för organisationer som inte behöver separata behörigheter som definierats för olika användargrupper. |
| **Admin för kommunikationsefterlevnad** | Använd den här rollgruppen till att först konfigurera kommunikationsefterlevnad och senare för att avgränsa administratörer för kommunikationsefterlevnad i en definierad grupp. Användare som tilldelats den här rollgruppen kan skapa, läsa, uppdatera och ta bort principer för kommunikationsefterlevnad, globala inställningar och tilldelningar av rollgrupper. Användare som tilldelats den här rollgruppen kan inte visa meddelandeaviseringar. |
| **Analytiker för kommunikationsefterlevnad** | Använd den här gruppen för att tilldela behörigheter till användare som fungerar som kommunikationsefterlevnadsanalytiker. Användare som har tilldelats den här rollgruppen kan visa principer där de har tilldelats som granskare, visa metadata för meddelanden (inte meddelandeinnehåll), eskalera till ytterligare granskare eller skicka meddelanden till användare. Analytiker kan inte lösa väntande aviseringar. |
| **Communication Compliance Investigator** | Använd den här gruppen för att tilldela behörigheter till användare som ska agera som kommunikationsefterlevnad. Användare som har tilldelats den här rollgruppen kan visa metadata och innehåll för meddelanden, eskalera till ytterligare granskare, eskalera till ett Advanced eDiscovery-ärende, skicka meddelanden till användare och lösa aviseringen. |
| **Visningsprogram för kommunikationsefterlevnad** | Använd den här gruppen för att tilldela behörigheter till användare som hanterar kommunikationsrapporter. Användare som har tilldelats den här rollgruppen har åtkomst till alla rapportwidgetar på kommunikationsefterlevnadens startsida och kan visa alla rapporter om kommunikationsefterlevnad. |

## <a name="plan-for-policies"></a>Planera för principer

Att skapa principer för kommunikationsefterlevnad är snabbt och enkelt [med de fördefinierade](communication-compliance-feature-reference.md#policy-templates) mallarna för anstötligt språk, känslig information och regelefterlevnad. Anpassade principer för kommunikationsefterlevnad ger flexibiliteten för att identifiera och undersöka problem som är specifika för din organisation och dina krav.

Tänk på följande områden när du planerar för principer för kommunikationsefterlevnad:

- Överväg att lägga till alla användare i organisationen som omfattas av principer för kommunikationsefterlevnad. Att identifiera specifika användare som inom omfattningen för enskilda principer är användbart i vissa fall, men de flesta organisationer bör inkludera alla användare i principer för kommunikationsefterlevnad som är optimerade för trakasserier eller upptäckt av intrång.
- Du kan förenkla konfigurationen genom att skapa grupper för personer som behöver granska sin kommunikation. Om du använder grupper. du kan behöva flera. Till exempel om du vill söka igenom kommunikationen mellan två distinkta grupper av personer, eller om du vill ange en grupp som inte övervakas.
- Konfigurera den procentandel av kommunikationen som ska granskas till 100 % för att säkerställa att alla problem som rör organisationens kommunikationer fångas upp.
- Du kan söka igenom meddelanden från [tredjepartskällor efter](communication-compliance-feature-reference.md#supported-communication-types) data som importerats till postlådor i Microsoft 365 organisation. Om du vill granska kommunikationen på de här plattformarna måste du konfigurera en anslutning till de här tjänsterna innan meddelandena övervakas av kommunikationspolicyn.
- Principer kan ha stöd för andra språk än engelska i anpassade principer för kommunikationsefterlevnad. Skapa en [egen nyckelordsordlista](communication-compliance-feature-reference.md#custom-keyword-dictionaries) med anstötliga ord på valbart språk eller skapa en egen maskininlärningsmodell med hjälp av utbildare [i](classifier-get-started-with.md) Microsoft 365.
- Alla organisationer har olika kommunikationsstandarder och policybehov. Övervaka specifika nyckelord med användning av villkor för [kommunikationsefterlevnad](communication-compliance-feature-reference.md#conditional-settings) eller övervaka för specifika typer av information [med anpassade typer av känslig information.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Är du redo att börja?

Information om hur du konfigurerar kommunikationsefterlevnad för din Microsoft 365-organisation finns i Konfigurera kommunikationsefterlevnad för [Microsoft 365](communication-compliance-configure.md) eller ta en titta på fallstudien för [Contoso](communication-compliance-case-study.md) och hur de snabbt konfigurerade en kommunikationsefterlevnadsprincip för att övervaka för anstötligt språk i Microsoft Teams, Exchange Online och Yammer-kommunikation.
