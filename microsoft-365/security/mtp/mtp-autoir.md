---
title: Automatiserad undersökning och svar i Microsoft 365 Defender
description: Få en översikt över automatisk undersökning och svarsfunktioner i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd, självbetjäning
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930336"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatiserad undersökning och svar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Så här fungerar automatisk undersökning och självbetjäning

När säkerhetsvarningar utlöses är det upp till teamet för säkerhetsåtgärder att titta på dessa aviseringar och vidta åtgärder för att skydda organisationen. Det kan ta mycket tid att prioritera och undersöka aviseringar, särskilt när nya aviseringar kommer in medan en undersökning pågår. Säkerhetsteam kan känna sig överhopade av mängden hot de måste övervaka och skydda mot. Automatisk undersökning och svarsfunktioner i Microsoft 365 Defender kan vara till hjälp.

Titta på följande video för att se hur självbetjäning fungerar:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

I Microsoft 365 Defender fungerar automatisk undersökning och svar med funktioner för självutskick på dina enheter, e-& och identiteter.
 
> [!TIP]
> I den här artikeln beskrivs hur automatisk undersökning och svar fungerar. Information om hur du konfigurerar de här funktionerna finns i Konfigurera funktioner för [automatisk undersökning och svar i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Din egen virtuella analytiker

Tänk dig att du har en virtuell analytiker i ditt team för säkerhetsåtgärder på nivå 1/nivå 2. Den virtuella analytikern efterliknar de idealiska steg som säkerhetsåtgärder kan vidta för att undersöka och åtgärda hot. Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet, och ta på sig en stor belastning på undersökningar och hotreparation. En sådan virtuell assistent kan minska tiden för att svara, vilket frigör din säkerhetsgrupp för andra viktiga strategiska projekt. Om det här scenariot låter som science fiction är det inte det! En sådan virtuell analytiker är en del av Microsoft 365 Defender-programsviten och namnet är *automatisk undersökning och svar.*

Med automatiserad undersökning och svar kan teamet för säkerhetsåtgärder avsevärt öka organisationens kapacitet för att hantera säkerhetsvarningar och incidenter. Med automatiserad undersökning och svar kan du minska kostnaderna för hantering av undersöknings- och åtgärdsaktiviteter och få ut det mesta av din programsvit för skydd mot hot. automatiserad undersökning och svar hjälper din grupp med säkerhetsåtgärder genom att:

1. Avgöra om ett hot kräver åtgärd.
2. Utföra (eller rekommendera) nödvändiga åtgärdsåtgärder;
3. Fastställa vilka ytterligare undersökningar som ska ske. och
4. Upprepa processen om det behövs för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Den automatiska undersökningen

**Avisering**  >  **incident**  >  **automatiserad undersökning**  >  **bedömning**  >  **åtgärdsåtgärd**

En utlöst avisering skapar en händelse, som kan starta en automatiserad undersökning. Undersökningen kan resultera i en eller flera åtgärder. I Microsoft 365 Defender korrelerar varje automatiserad undersökning signaler till Microsoft Defender för identitet, Microsoft Defender för Endpoint och Defender för Office 365, enligt sammanfattningen i följande tabell: 

|Enheter |Skyddstjänster för hot  |
|---------|---------|
|Enheter (kallas även slutpunkter)     |[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (filer och meddelanden i postlådor)     |[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Varje undersökning genererar en bedömning *(skadlig,* *misstänkt* eller inga hot hittades) för varje bevis som *undersöks.* Beroende på typen av hot och resulterande bedömning, utförs åtgärder automatiskt eller vid godkännande av organisationens säkerhetsteam. Väntande och slutförda åtgärder visas i [Åtgärdscenter.](mtp-action-center.md)

Medan en undersökning körs läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den slutförs. Om en okritisk enhet visas någon annanstans utökar den automatiska undersökningen dess omfattning så att den omfattar den enheten, och en allmän säkerhetsspelbok körs. 

> [!NOTE]
> Inte alla aviseringar utlöser en automatiserad undersökning och inte alla undersökningar resulterar i automatiska åtgärdsåtgärder. Det beror på hur automatisk undersökning och svar har konfigurerats för organisationen. Se [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)


## <a name="next-steps"></a>Nästa steg

- [Se förutsättningarna för automatiserad undersökning och svar i Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurera automatisk undersökning och svar för organisationen](mtp-configure-auto-investigation-response.md)
- [Läs mer om Åtgärdscenter](mtp-action-center.md)
