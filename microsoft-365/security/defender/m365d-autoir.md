---
title: Automatiserad undersökning och svar i Microsoft 365 Defender
description: Få en översikt över automatiska undersöknings- och svarsfunktioner, även kallat självbetjäning, i Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: be0423b0af8251347420d9e970dcfe10db0bb72b
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591929"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Automatiserad undersökning och svar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Om din organisation använder [Microsoft 365 Defender](microsoft-365-defender.md)får teamet för säkerhetsåtgärder en avisering när en skadlig eller misstänkt artefakt hittas. Med den till synes oändliga flödet av hot som kommer in ställs säkerhetsteam ofta inför utmaningar med att hantera den stora mängden aviseringar. Som tur är innehåller Microsoft 365 Defender funktioner för automatisk undersökning och åtgärder (AIR) som kan hjälpa din säkerhetsgrupp att hantera hot mer effektivt och effektivare.

Den här artikeln innehåller en översikt över AIR med länkar till nästa steg och ytterligare resurser.

> [!TIP]
> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Så här fungerar automatisk undersökning och självbetjäning

När säkerhetsvarningar utlöses är det upp till ditt säkerhetsteam att titta på varningarna och vidta åtgärder för att skydda din organisation. Det kan ta mycket tid att prioritera och undersöka aviseringar, särskilt när nya aviseringar kommer in medan en undersökning pågår. Säkerhetsåtgärder grupper kan känna sig överhopad av mängden hot de måste övervaka och skydda mot. Med hjälp av automatiska undersöknings- och svarsfunktioner kan Microsoft 365 Defender vara till hjälp.

Titta på följande video för att se hur självbetjäning fungerar: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

I Microsoft 365 Defender fungerar automatisk undersökning och svar med självöverlåtande funktioner på dina enheter, e-& och innehåll och identiteter.
 
> [!TIP]
> I den här artikeln beskrivs hur automatisk undersökning och svar fungerar. Information om hur du konfigurerar dessa funktioner [finns i Konfigurera funktioner för automatisk undersökning och svar i Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Din egen virtuella analytiker

Tänk dig att du har en virtuell analytiker i ditt team för säkerhet på nivå 1 eller nivå 2. Den virtuella analytikern efterliknar de bästa stegen som säkerhetsåtgärder kan vidta för att undersöka och åtgärda hot. Den virtuella assistenten kan arbeta dygnet runt, med obegränsad kapacitet, och ta på sig en stor belastning av undersökningar och hotreparation. En sådan virtuell assistent kan avsevärt minska tiden för att svara, vilket frigör din säkerhetsgrupp för andra viktiga strategiska projekt. Om det här scenariot låter som science fiction är det inte det! En sådan virtuell analytiker är en del av din Microsoft 365 Defender-programsvit, och namnet är *en automatiserad undersökning och svar.*

Med funktionerna för automatiserad undersökning och svar kan ditt säkerhetsteam avsevärt öka organisationens kapacitet för att hantera säkerhetsvarningar och incidenter. Med automatiserad undersökning och svar kan du minska kostnaderna för hantering av undersökning och åtgärder och få ut mesta mesta av din säkerhetssvit för hot. Automatiska undersöknings- och svarsfunktioner hjälper teamet med säkerhetsåtgärder genom att:

1. Avgöra om ett hot kräver åtgärd.
2. Vidta (eller rekommendera) alla nödvändiga åtgärder;
3. Avgöra om och vilka andra undersökningar som ska ske; och
4. Upprepa processen om det behövs för andra aviseringar.

## <a name="the-automated-investigation-process"></a>Automatisk undersökning

En avisering skapar en händelse, som kan påbörja en automatiserad undersökning. Den automatiska undersökningen resulterar i en bedömning för varje bevis. Olika beslut kan vara:
- *Skadlig*;
- *Misstänkt –* om du har en misstänkt e eller 
- *Inga hot hittades*. 

Åtgärdsåtgärder för skadliga eller misstänkta enheter identifieras. Några exempel på åtgärder:
- Skicka en fil till karantän.
- Stoppar en process.
- Isolera en enhet
- Blockera en URL och 
- andra åtgärder. (Se [Åtgärder för åtgärder i Microsoft 365 Defender](m365d-remediation-actions.md).)

Beroende på [hur automatiska undersöknings-](m365d-configure-auto-investigation-response.md) och svarsfunktioner har konfigurerats för organisationen utförs åtgärder automatiskt eller bara om säkerhetsgruppen har godkänt det. Alla åtgärder, väntande eller slutförda, visas i [Åtgärdscenter.](m365d-action-center.md)

Medan en undersökning körs läggs alla andra relaterade aviseringar som uppstår till i undersökningen tills den slutförs. Om en okritisk enhet visas någon annanstans utökar den automatiska undersökningen dess omfattning så att den omfattar den enheten, och undersökningen upprepas. 

I Microsoft 365 Defender korrelerar varje automatisk undersökning signaler i Microsoft Defender för identitet, Microsoft Defender för slutpunkt och Defender för Office 365, enligt sammanfattningen i följande tabell: 

|Enheter |Skyddstjänster för hot  |
|:---------|:---------|
|Enheter (kallas även slutpunkter, och kallas ibland för datorer)     |[Microsoft Defender för Endpoint](../defender-endpoint/automated-investigations.md)<br/>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|E-postinnehåll (e-postmeddelanden som kan innehålla filer och URL:er)     |[Microsoft Defender för Office 365](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> Inte alla aviseringar utlöser en automatiserad undersökning och inte alla undersökningsresultat i automatiserade åtgärdsåtgärder. Det beror på hur automatisk undersökning och svar har konfigurerats för organisationen. Se [Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md)

## <a name="viewing-a-list-of-investigations"></a>Visa en lista över undersökningar

Om du vill visa undersökningar går du till **sidan Incidenter.** Välj en incident och välj sedan **fliken Undersökningar.** Mer information finns i Information [och resultat av en automatiserad undersökning.](m365d-autoir-results.md)


## <a name="next-steps"></a>Nästa steg

- [Se förutsättningarna för automatiserad undersökning och svar i Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Konfigurera automatisk undersökning och svar för organisationen](m365d-configure-auto-investigation-response.md)
- [Läs mer om Åtgärdscenter](m365d-action-center.md)
