---
title: Beräkning av efterlevnadsresultat
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Förstå hur Microsoft Compliance Manager beräknar ett personligt poängresultat utifrån åtgärder som vidtas för att hantera risker och förbättra kompatibiliteten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 756ce207b1e9583bf63f19351e85955950487404
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162405"
---
# <a name="compliance-score-calculation"></a>Beräkning av efterlevnadsresultat

**I den här artikeln:** Lär dig hur Efterlevnadshanteraren beräknar en efterlevnadspoäng för din organisation. I den här artikeln förklaras **hur** du tolkar poängen , vad som ingår i utvärderingen av **dataskyddsbaslinjen,** kontinuerlig övervakning och hur olika typer av åtgärder hanteras och poäng **görs.** 

> [!IMPORTANT]
> Rekommendationer från Compliance Manager ska inte tolkas som en garanti för överensstämmelse. Det är upp till dig att utvärdera och verifiera hur effektiv kundkontrollerna är i olika regelverk. Dessa tjänster omfattas av de allmänna villkoren i [villkoren för onlinetjänster.](https://go.microsoft.com/fwlink/?linkid=2108910) Se även [Microsoft 365 om säkerhet och efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>Så här läser du efterlevnadsresultatet

Instrumentpanelen för Efterlevnadshanteraren visar ditt övergripande efterlevnadsresultat. Det här poängresultatet mäter förloppet för att utföra rekommenderade förbättringsåtgärder i kontroller. Ditt poängresultat kan hjälpa dig att förstå din aktuella efterlevnad. Det kan också hjälpa dig att prioritera åtgärder utifrån deras möjlighet att minska risken.

Ett poängvärde tilldelas på tre nivåer:

1. **Resultat för förbättringsåtgärd:** Varje åtgärd har olika påverkan på ditt resultat beroende på den potentiella risk som ingår

2. **Kontrollpoäng**: det här resultatet är summan av poäng som du fått genom att utföra förbättringsåtgärder i kontrollen. Denna summa tillämpas i sin helhet på din övergripande efterlevnadspoäng när kontrollen uppfyller båda följande villkor:
    - **Implementeringsstatus** är **lika med Implementerad** **eller Alternativ implementering** och
    - **Testresultat** är lika med **Godkänd**.

3. **Utvärderingsresultat**: det här är summan av dina kontrollresultat. Det beräknas med hjälp av resultat från olika åtgärder. Varje Microsoft-åtgärd och varje förbättringsåtgärd som hanteras av din organisation räknas en gång, oavsett hur ofta den refereras till i en kontroll.

Övergripande efterlevnadsresultat beräknas med hjälp av åtgärdsresultat, där varje Microsoft-åtgärd räknas en gång, varje teknisk åtgärd du hanterar räknas en gång och varje icke-teknisk åtgärd du hanterar räknas en gång per grupp. Den här logiken är utformad för att ge en så exakt redovisning som möjligt av hur åtgärder implementeras och testas i organisationen. Du kanske märker att det kan leda till att ditt övergripande efterlevnadsresultat skiljer sig från genomsnittet av dina utvärderingsresultat. Läs mer nedan om [hur åtgärder poängas](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Första poäng baserad Microsoft 365 dataskyddsbaslinje
  
Efterlevnadshanteraren ger dig en inledande poäng baserat Microsoft 365 dataskyddsbaslinje. Den här baslinjen är en uppsättning kontroller som innehåller viktiga bestämmelser och standarder för dataskydd och allmän datastyrning. Den här baslinjen ritar främst element från NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) och ISO (International Organization for Standardization), samt från FedRAMP (Federal Risk and Authorization Management Program) och GDPR (General Data Protection Regulation of the Eu).

Ditt första resultat beräknas enligt standardutvärderingen av dataskydd som tillhandahålls till alla organisationer. Vid ditt första besök samlar Compliance Manager redan in signaler från dina Microsoft 365 lösningar. Du kan direkt se hur organisationen fungerar i förhållande till viktiga standarder och bestämmelser för dataskydd, och se förslag på förbättringsåtgärder att vidta.

Eftersom alla organisationer har särskilda behov använder Efterlevnadshanteraren dig för att konfigurera och hantera utvärderingar för att minimera och minimera risker så omfattande som möjligt.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Hur efterlevnadshanteraren kontinuerligt utvärderar kontroller

Efterlevnadshanteraren söker automatiskt igenom din Microsoft 365 och upptäcker systeminställningarna, kontinuerligt och automatiskt uppdaterar din tekniska åtgärdsstatus. Microsoft Secure Score är den underliggande motor som utför övervakning.

Din åtgärdsstatus uppdateras på instrumentpanelen en gång per dygn. När du följer en rekommendation om att implementera en kontroll ser du vanligtvis kontrollstatusen uppdaterad nästa dag.

Om du till exempel aktiverar multifaktorautentisering (MFA) i Azure AD-portalen identifierar Efterlevnadshanteraren inställningen och återspeglar den i informationen om kontrollåtkomstlösningen. Om du däremot inte aktiverar MFA flaggas det som en rekommenderad åtgärd för dig att vidta.

Läs mer om [Secure Score och hur det fungerar.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Åtgärdstyper och punkter

Efterlevnadshanteraren spårar två typer av åtgärder:

1. **Dina förbättringsåtgärder:** åtgärder som din organisation hanterar.
2. **Microsoft-åtgärder:** åtgärder som Microsoft hanterar.

Båda typerna av åtgärder har poäng som räknas mot din totala poäng när den är slutförd.

### <a name="technical-and-non-technical-actions"></a>Tekniska och icke-tekniska åtgärder

Åtgärder grupperas efter vare sig de är tekniska eller icke-tekniska. Vilken poäng som varje åtgärd får varierar beroende på typ.

- **Tekniska åtgärder** implementeras genom att interagera med tekniken i en lösning (t.ex. genom att ändra en konfiguration). Poängen för tekniska åtgärder beviljas en gång per åtgärd, oavsett hur många grupper den tillhör.

- **Icke-tekniska åtgärder** hanteras av din organisation och implementeras på andra sätt än att arbeta med tekniken i en lösning. Det finns två typer av icke-tekniska åtgärder: **dokumentation** och **drift.** Punkterna för de här åtgärderna tillämpas på efterlevnadsresultatet på en gruppnivå. Det innebär att om en åtgärd finns i flera grupper får du punktvärdet för åtgärden varje gång du implementerar den inom en grupp.

**Exempel på poäng för tekniska och icke-tekniska åtgärder:**

Anta att du har en teknisk åtgärd värd 3 poäng som finns i 5 grupper och att du har en icke-teknisk åtgärd värd 3 poäng som finns i samma 5 grupper.

Om du lyckas implementera den tekniska åtgärden är det totala antalet poäng som du får 3. Det beror på att du bara behöver implementera åtgärden en gång för klientorganisationen. Implementerings- och teststatus för den tekniska åtgärden visas på samma sätt i alla instanser av den åtgärden, i varje grupp den tillhör.

Om du lyckas implementera den icke-tekniska åtgärden i var och en av de fem grupperna är det totala antalet poäng som du får 15. Det beror på att du måste implementera åtgärden i varje grupp. Implementerings- och teststatus för den icke-tekniska åtgärden skiljer sig åt mellan grupper eftersom åtgärden implementeras separat inom varje grupp.

Den här poänglogiken är utformad för att ge en så exakt redovisning som möjligt av hur åtgärder implementeras och testas i organisationen.

### <a name="how-score-values-are-determined"></a>Hur poängvärden bestäms
 
Åtgärder tilldelas ett poängvärde baserat på om de är obligatoriska eller godtyckliga, och om de är preventativa, godtyckliga eller korrigerande.

### <a name="mandatory-and-discretionary-actions"></a>Obligatoriska och godtyckliga åtgärder

 - **Obligatoriska åtgärder** kan inte åsidosättas, antingen avsiktligt eller av misstag. Ett exempel på en obligatorisk åtgärd är en centralt hanterad lösenordsprincip som ställer in krav på lösenordslängd, komplexitet och förfallodatum. Användarna måste följa de här kraven för att få åtkomst till systemet.
  
 - **Godtyckliga åtgärder förlitar** sig på att användarna förstår och följer en princip. En princip som till exempel kräver att användarna låser sin dator när de lämnar den är en godtycklig åtgärd eftersom den förlitar sig på användaren.
  
### <a name="preventative-detective-and-corrective-actions"></a>Preventativa, vidtas och korrigerande åtgärder
  
 - **Preventativa åtgärder** åtgärdar specifika risker. Till exempel är skydd av information i vila med hjälp av kryptering en preventativ åtgärd mot attacker och överträdelser. Att separera uppgifter är en förebyggande åtgärd för att hantera intressekonflikter och bevaka bedrägerier.
  
 - **Åtgärder av** intrång övervakar aktivt system för att identifiera felaktiga villkor eller beteenden som representerar risker eller som kan användas för att upptäcka intrång eller intrång. Det finns till exempel systemåtkomstgranskning och administrativa åtgärder som är behöriga. Granskningar av regelefterlevnad är en typ av åtgärd som används för att hitta processproblem.
  
- **Korrigerande** åtgärder försöker minimera de negativa effekterna av en säkerhetshändelse, vidta korrigerande åtgärder för att minska den omedelbart effekt och återställa skadan om möjligt. Svar på sekretesstillbud är en korrigerande åtgärd för att begränsa skador och återställa system till drifttillstånd efter ett brott.
  
Varje åtgärd har ett tilldelat värde i Efterlevnadshanteraren baserat på den risk den representerar:

|**Typ**|**Tilldelat poäng**|
|:-----|:-----|
| Preventativ obligatoriskt | 27 |
| Preventative discretionary | 9 |
| Obligatorisk obligatoriskt | 3 |
| Godtyckligt omdöme | 1 |
| Korrigerande obligatoriskt | 3 |
| Godtyckliga korrigerande | 1 |
  
![Värden i åtgärdspunkten i Efterlevnadshanteraren](../media/compliance-score-action-scoring.png "Värden i åtgärdspunkten i Efterlevnadshanteraren")