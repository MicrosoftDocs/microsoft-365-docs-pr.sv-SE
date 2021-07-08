---
title: Kör en utvärderingsversion av Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Lär dig hur du planerar och kör ett testpilotprogram för SharePoint Syntex i organisationen.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327148"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Kör en utvärderingsversion av Microsoft SharePoint Syntex

I den här artikeln beskrivs hur du set up and run a trial pilot program to deploy SharePoint Syntex in your organization. Vi rekommenderar även metodtips för utvärderingsversionen.

## <a name="sign-up-for-a-trial"></a>Registrera dig för en utvärderingsversion

Utvärderingsversionen SharePoint Syntex 300 användare i 30 dagar.

> [!NOTE]
> Upp till 300 användare ingår i utvärderingsversionen för att säkerställa att 1 miljon AI Builder-krediter automatiskt tillräknas. Du behöver inte inkludera 300 användare för att en utvärderingsversion ska lyckas.

Du kan hämta utvärderingsversionen från någon av följande källor:

- Sidan [SharePoint Syntex produkt](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- Administrationscenter för Microsoft 365 [](https://admin.microsoft.com)
    1.  Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
    2.  Gå till **Tjänster för**  >  **faktureringsköp.**
    3.  Rulla ned till **avsnittet** Tillägg.
    4.  På panelen SharePoint Syntex väljer du **Information**.
    5.  Välj **Hämta kostnadsfri utvärderingsversion**.
    6.  Bekräfta utvärderingsversionen genom att följa de återstående stegen i guiden.

Du måste vara global Microsoft 365 eller faktureringsadministratör för att aktivera en utvärderingsversion.

### <a name="who-should-be-involved-in-a-trial"></a>Vem bör vara involverad i en utvärderingsversion

|Roll  |Aktivitet  |
|---------|---------|
|Microsoft 365 global administratör eller faktureringsadministratör    |     Aktivera utvärderingsversionen och tilldela licenser    |
|Microsoft 365 global administratör SharePoint administratör     |   Konfigurera SharePoint Syntex och skapa innehållscenter      |
|Företagsanvändare     |    Skapa och testa modeller     |

### <a name="before-you-activate-a-trial"></a>Innan du aktiverar en utvärderingsversion

Om du vill planera SharePoint Syntex utvärderingsversion bör du tänka på följande:

- De mest meningsfulla testerna slutförs på verkliga scenarier och data.
- Du kan bara aktivera en SharePoint Syntex en gång per klientorganisation.

En test- eller demoklientorganisation kan användas som "torr körning" för att gå igenom aktiveringsstegen och administrativa kontroller. Men det är förmodligen bäst att utvärdera modellbygget på en produktionsklientorganisation.

För att maximera värdet för en utvärderingsversion av en produktionsklient är det viktigt att planera och engagera företaget. Du bör engagera ett eller flera affärsområden för att identifiera tre till sex användningsfall som potentiellt skulle kunna hanteras av SharePoint Syntex. Dessa användningsfall bör:

- Inkludera scenarier som kan lösas med hjälp av antingen formulärbearbetnings- eller dokument förstå modellen.
- Förstå tydligt syftet med extraherade metadata. Visa till exempel formatering eller automatisering genom att använda Power Automate. Medan SharePoint Syntex fokuserar på att klassificera dokument och extrahera metadata, är det värde som ska mätas vad dessa metadata möjliggör.
- Baseras på en definierad uppsättning data. till exempel specifika SharePoint webbplatser eller bibliotek. En vanlig missuppfattning av SharePoint Syntex är att modeller av allmänna ändamål kan tillämpas i hela organisationens innehåll. En mer exakt vy är att modeller är byggda för att hjälpa till att lösa specifika affärsproblem på riktade platser.

Alla dessa användningsfall kanske inte passar bra för SharePoint Syntex. Syftet med en kvalitets utvärderingsversion är inte att bevisa att SharePoint Syntex kommer att passa alla scenarier. I stället bör utvärderingsversionen hjälpa dig att bättre förstå produktvärdet.

Identifiera användare som är ämnesexperter i relaterat innehåll eller relaterad process för vart och ett av de planerade användningsfallen. Skapandet av SharePoint Syntex är fokuserat på domänexperter i innehållet i stället för på IT-personal eller utvecklarresurser.

## <a name="activate-a-trial"></a>Aktivera en utvärderingsversion

När du påbörjar en utvärderingsversion måste du:

- Tilldela licenser till relevanta användare.
- Utför [ytterligare konfiguration av SharePoint Syntex](set-up-content-understanding.md).
    - Du kanske vill skapa [ytterligare innehållscenter](create-a-content-center.md).

När utvärderingsversionen har aktiverats kan du skapa modeller och processfiler. Se [vägledning för att skapa modeller.](create-a-content-center.md)

## <a name="during-a-trial"></a>Under en utvärderingsversion

Utvärderingsperioder är begränsade, så det är bäst att först fokusera på SharePoint Syntex kan klassificera dokument och extrahera metadata för de definierade användningsfallen. När utvärderingsperioden är slut kan du utvärdera hur metadata kan utnyttjas.

## <a name="after-a-trial"></a>Efter en utvärderingsversion

Baserat på resultatet av utvärderingsversionen kan du bestämma om du vill fortsätta med produktionsanvändningen av SharePoint Syntex.

### <a name="proceed-to-production-use"></a>Fortsätt till produktionsanvändning

För att säkerställa kontinuiteten i tjänsten behöver du köpa antalet licenser som krävs och tilldela licenserna till användarna. Utvärderingsanvändare som inte har en fullständig licens i slutet av utvärderingsperioden kommer inte att kunna använda hela SharePoint Syntex.

Du kan behöva uppskatta din beräknade användning av formulärbearbetning och planera för det förväntade antalet AI Builder-krediter. Mer information finns i [Uppskatta den AI Builder-kapacitet som är rätt för dig.](https://powerapps.microsoft.com/ai-builder-calculator/)

### <a name="dont-proceed-to-production-use"></a>Fortsätt inte till produktionsanvändning

Om du inte köper licenser efter utvärderingsversionen:

- Du kommer inte att kunna skapa nya modeller.
- Bibliotek som körde modeller kommer inte längre att automatiskt klassificera filer eller extrahera modeller.
- Tidigare klassificerade filer eller extraherade metadata påverkas inte. 
- Innehållscenter och dokumentförståelsemodeller tas inte bort automatiskt. De kommer att vara tillgängliga för användning om du bestämmer dig för att köpa licenser i framtiden.
- Modeller som bearbetas i formulär lagras i CDS-instansen (Common Data Services) av standardmiljön för Power Platform. De kan användas med framtida licensiering för SharePoint Syntex eller med AI Builder-funktioner i Power-plattformen.

## <a name="see-also"></a>Se även

[Införande av Microsoft SharePoint Syntex: Kom igång](adoption-getstarted.md)
