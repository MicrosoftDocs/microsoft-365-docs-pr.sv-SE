---
title: Steg 2. Åtgärda den första incidenten
description: Så här kommer du igång med att åtgärda din första incident i Microsoft 365 Defender.
keywords: incidenter, varningar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2fe6c5b1b0feea2163c0a2bcc871921a885abb85
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52115037"
---
# <a name="step-2-remediate-your-first-incident"></a>Steg 2. Åtgärda den första incidenten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Microsoft 365 Defender tillhandahåller inte bara funktioner för identifiering och analys, utan erbjuder även inneslutning och intrång i skadlig programvara. Inneslutning innehåller åtgärder för att minska attackens påverkan, medan säkerställer att alla spårningar av attackersaktivitet tas bort från nätverket.  Microsoft 365 I Defender finns flera åtgärder som du kan konfigurera för att åtgärda automatiskt beroende på operativsystem och attacktyp.

Microsoft 365 Defender erbjuder flera åtgärder som analytiker kan initiera manuellt. Åtgärder är indelade i två kategorier: Åtgärder på enheter och Åtgärder på filer. Vissa åtgärder kan användas för att omedelbart stoppa hoten medan andra åtgärder bidrar till ytterligare analys av konsekvensanalyser.

## <a name="actions-on-devices"></a>Åtgärder på enheter

- **Isolera enheten** – Den här aktiviteten blockerar omedelbart all nätverkstrafik (Internet och intern) för att minimera spridningen av skadlig programvara och tillåta analytiker att fortsätta analysen utan att en illvillig aktör kan fortsätta en attack. Den enda anslutning som tillåts är till Microsoft Defender för identitetstjänstmoln så att Microsoft Defender för identitet kan fortsätta att övervaka enheten. 
- **Begränsa programkörning** – För att hindra ett program från att köras tillämpas en kodintegritetsprincip som bara tillåter att filer körs om de är signerade av ett certifikat som utfärdats av Microsoft. Den här begränsningsmetoden kan förhindra att en attack kontrollerar komprometterade enheter och utför ytterligare skadliga aktiviteter.
- **Kör antivirussökning** – en Microsoft Defender Antivirus kan köras tillsammans med andra antivirusprogram, oavsett om Defender Antivirus är den aktiva antiviruslösningen eller inte. Om en annan antivirusleverantör är den primära lösning för slutpunktsskydd kan du köra Defender Antivirus i passivt läge.
- **Initiera automatisk undersökning** – Du kan påbörja en ny, allmän automatisk undersökning på enheten. Medan en undersökning körs kommer alla andra aviseringar som genereras från enheten att läggas till i en pågående automatiserad undersökning tills undersökningen har slutförts. Om samma hot visas på andra enheter läggs dessa enheter dessutom till i undersökningen.
- **Initiera livesvar** – Live-svar är en funktion som ger dig omedelbar åtkomst till en enhet med hjälp av en fjärranslutning med skal. Det gör att du kan utföra djupgående undersökningsarbete och vidta omedelbart åtgärder för att snabbt identifiera hot i realtid. Med live-svar kan du förbättra undersökningar genom att samla in tekniska data, köra skript, skicka misstänkta enheter för analys, åtgärda hot och proaktivt leta efter nya hot.
- **Paket för insamling** av undersökning – Som en del av undersökningen eller svarsprocessen kan du samla in ett undersökningspaket från en enhet. Genom att samla in undersökningspaketet kan du identifiera enhetens aktuella status och ytterligare förstå de verktyg och tekniker som används av attackeraren. 
- **Kontakta en** expert på hot (finns i både åtgärder på enheter och filer) – Du kan kontakta en Expert på Microsoft-hot för att få mer information om potentiellt komprometterade enheter eller enheter som redan har komprometterats. Microsofts experter kan vara engagerade direkt från Microsoft Defender Säkerhetscenter för att få ett snabbt och korrekt svar. 

## <a name="actions-on-files"></a>Åtgärder för filer

- **Stoppa och sätt filen** i karantän – Den här åtgärden innefattar att stoppa processer, kvartilfiler och ta bort beständiga data, till exempel registernycklar. Den här åtgärden gäller på enheter med Windows 10, version 1703 eller senare, där filen har observerats de senaste 30 dagarna. 
- **Lägga till indikatorer för att blockera eller** tillåta fil – Förhindra ytterligare spridning av en attack i organisationen genom att spärra potentiellt skadliga filer eller misstänkt skadlig kod. Med den här åtgärden förhindras att filen läses, skrivs eller körs på enheter i organisationen.
- **Ladda ned eller samla** in fil – Med den här åtgärden kan analytiker ladda ned en fil i en lösenordsskyddad .zip-arkivfil för vidare analys av organisationen.
- **Djupanalys** – Med den här åtgärden körs en fil i en säker, fullständigt instrumenterad molnmiljö. Djupanalysresultat visar filens aktiviteter, observerade beteenden och tillhörande artefakter, till exempel neds ignorerade filer, registerändringar och kommunikation med IP-adresser. 

Vi fortsätter med exemplet [i Identifiera, hantera och analysera incidenter](first-incident-analyze.md#analyze-your-first-incident)– en analytiker kan åtgärda problemet med följande åtgärder:

1. Återställa lösenordet för användarkontot omedelbart
2. Identifiera enheten i Microsoft 365 Defender tills djupanalys är klar
3. Kontrollera att den skadliga filen satts i karantän från SharePoint
4. Kontrollera vilka slutpunkter som påverkades av skadlig programvara
5. Bygga om system
6. Sök efter liknande Microsoft Cloud App Security aviseringar för andra användare
7. Skapa en anpassad indikator i Microsoft Defender för Slutpunkt för att blockera en Tor IP-adress
8. Skapa en styrningsåtgärd i Microsoft Cloud App Security för den här typen av avisering, till exempel de som visas i följande bild:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Exempel på styrningsåtgärder i Microsoft Cloud App Security portalen"::: 
 
De flesta åtgärder kan tillämpas och spåras i Microsoft 365 Defender. 

## <a name="using-playbooks"></a>Använda spelböcker

Dessutom kan du skapa automatisk åtgärd med hjälp av spelböcker. För närvarande har Microsoft [Playbook-mallar GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) spelböcker som ger spelböcker för följande scenarier:

- Ta bort känslig fildelning efter begäran om användarverifiering
- Auto-triage oregelade landaviseringar
- Begära åtgärder för chefen innan du inaktiverar ett konto
- Inaktivera regler för skadlig inkorg

Spelböcker använder Power Automate för att skapa anpassade automatiseringsflöden för process för att automatisera vissa aktiviteter när vissa villkor har utlösts. Organisationer kan skapa spelböcker från befintliga mallar eller från grunden. 

Här är ett exempel.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Exempel på ett Power Automate anpassat automatiseringsprocessflöde för processer"::: 
 
Spelböcker kan också skapas under granskning [efter incidenter](first-incident-post.md) för att skapa åtgärdsåtgärder från incidenter för snabbare åtgärder. 

## <a name="next-step"></a>Nästa steg

[![Steg 3: Lär dig hur du utför en granskning efter incidenten](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

Lär dig hur [du granskar ett incidenter efter ett incident.](first-incident-post.md)

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Analysera incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
