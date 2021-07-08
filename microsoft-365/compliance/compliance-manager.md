---
title: Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager hjälper organisationer att förenkla och automatisera riskutvärderingar och föreslår rekommenderade åtgärder för att hantera risker.
ms.openlocfilehash: 536a1c02a820b0ea36fc4fe39ca1d0d31f7bc994
ms.sourcegitcommit: 48e50a5445c63d397197af2bb7549cbec0bce790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53330947"
---
# <a name="microsoft-compliance-manager"></a>Microsoft Compliance Manager

**I den här artikeln:** Lär dig vad Efterlevnadshanteraren är, hur den förenklar efterlevnad och minskar risker samt nyckelkomponenter.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Vad är nytt: GA-versionen av Efterlevnadshanteraren

Efterlevnadshanteraren är nu allmänt tillgänglig (GA) som en punkt till punkt-lösning för efterlevnadshantering i [Microsoft 365 Efterlevnadscenter.](microsoft-365-compliance-center.md) Med den här versionen slutförs övergången från den tidigare platsen i Microsoft Service Trust Portal. Efterlevnadshanteraren är även tillgänglig för kunder i amerikanska government community (GCC) måttliga, GCC hög och doD-kunder (Department of Defense).

Det som började som den offentliga förhandsversionen av Efterlevnadsresultat har utvecklats till ett centralt verktyg med förbättrade funktioner för efterlevnadshantering och enklare användning.  Med GA-versionen får du en större samling färdiga bedömningar som hjälper dig att anpassa dina efterlevnadsaktiviteter.

**Läs mer om GA-versionen:**
- Våra [vanliga frågor går](compliance-manager-faq.yml) igenom utvecklingen i detalj.
- Läs mer om förbättringar av GA-funktioner [i det här blogginlägget.](https://aka.ms/compliancemanager/GAblog)

Titta på videon nedan för att lära dig hur Efterlevnadshanteraren kan förenkla hur organisationen hanterar efterlevnad:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>Vad är Efterlevnadshanteraren

[Microsoft Compliance Manager](https://compliance.microsoft.com/compliancemanager) är en funktion i [Microsoft 365 Efterlevnadscenter](microsoft-365-compliance-center.md) som hjälper dig att hantera organisationens efterlevnadskrav enklare och enklare. Efterlevnadshanteraren kan hjälpa dig under hela resan, från att inventera dina dataskyddsrisker till att hantera komplexiteten i implementeringen av kontroller, hålla dig aktuell med bestämmelser och certifieringar och rapportera till granskare.

Efterlevnadshanteraren hjälper till att förenkla efterlevnad och minska risken genom att tillhandahålla:

- Förbyggda bedömningar av vanliga bransch- och regionala standarder och bestämmelser, eller anpassade utvärderingar för att uppfylla dina unika efterlevnadsbehov (tillgängliga bedömningar beror på ditt licensavtal; [läs mer](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)).

- Arbetsflödesfunktioner som hjälper dig att effektivt slutföra dina riskutvärderingar genom ett enda verktyg.

- Detaljerad steg för steg-vägledning om föreslagna förbättringsåtgärder som hjälper dig att följa de standarder och bestämmelser som är mest relevanta för din organisation. För åtgärder som hanteras av Microsoft ser du implementeringsinformation och granskningsresultat.

- Ett riskbaserat efterlevnadsresultat som hjälper dig att förstå hur efterlevnad ser ut genom att mäta förloppet för att slutföra förbättringsåtgärder.

Instrumentpanelen för Efterlevnadshanteraren visar ditt aktuella efterlevnadsresultat, hjälper dig att se vad som behöver uppmärksammas och vägleder dig till viktiga förbättringsåtgärder. Nedan är ett exempel på hur instrumentpanelen för Efterlevnadshanteraren kommer att se ut:

![Efterlevnadshanteraren – instrumentpanel](../media/compliance-manager-dashboard.png "Instrumentpanel för Efterlevnadshanteraren")

## <a name="understanding-your-compliance-score"></a>Förstå din efterlevnadspoäng

Efterlevnadshanteraren belönar dig för att du har slutfört förbättringsåtgärder som vidtas för att följa en regel, standard eller princip och kombinerar dessa punkter till en övergripande efterlevnadspoäng. Varje åtgärd har olika påverkan på ditt resultat beroende på de potentiella risker som ingår. Din efterlevnadspoäng kan hjälpa dig att prioritera vilken åtgärd du ska fokusera på för att förbättra din övergripande efterlevnad.

Efterlevnadshanteraren ger dig en inledande poäng baserat Microsoft 365 dataskyddsbaslinje. Den här baslinjen är en uppsättning kontroller som innehåller viktiga bestämmelser och standarder för dataskydd och allmän datastyrning.

##### <a name="learn-more"></a>Mer information

[Förstå hur ditt efterlevnadsresultat beräknas](compliance-score-calculation.md).

[Lär dig hur du arbetar med förbättringsåtgärder](compliance-manager-improvement-actions.md).

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Huvudelement: kontroller, utvärderingar, mallar, förbättringsåtgärder

Efterlevnadshanteraren använder flera dataelement som hjälper dig att hantera dina efterlevnadsaktiviteter. När du använder Efterlevnadshanteraren för att tilldela, testa och övervaka efterlevnadsaktiviteter är det bra att ha en grundläggande förståelse för de viktigaste elementen: kontroller, utvärderingar, mallar och förbättringsåtgärder.

### <a name="controls"></a>Kontroller

En kontroll är ett krav för en regel, standard eller princip. Den definierar hur du utvärderar och hanterar systemkonfiguration, organisationsprocess och personer som ansvarar för att uppfylla ett visst krav för en regel, standard eller princip.

Efterlevnadshanteraren håller i följande typer av kontroller:

1. **Microsoft-hanterade** kontroller: kontroller för Microsoft-molntjänster, som Microsoft ansvarar för att implementera
2. **Dina kontroller:** kallas ibland för kund hanterade kontroller, dessa är kontroller implementerade och hanterade av din organisation
3. **Delade kontroller:** det här är kontroller som både din organisation och Microsoft har ansvar för att implementera

##### <a name="learn-more"></a>Mer information

[Övervaka förloppet för dina kontroller.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)

[Lär dig hur Efterlevnadshanteraren kontinuerligt utvärderar kontroller.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>Utvärderingar

En bedömning består av gruppering av kontroller från en viss regel, standard eller princip. Att utföra åtgärder inom en bedömning hjälper dig att uppfylla kraven i en standard, regel eller lag. Du kan till exempel göra en bedömning som gör att dina Microsoft 365-inställningar uppfyller ISO 27001-kraven när du har slutfört alla åtgärder i den.

Utvärderingar innehåller flera komponenter:

- **Tjänster inom omfattningen**: den specifika uppsättningen Microsoft-tjänster som gäller för utvärderingen
- **Hanterade kontroller från Microsoft:** kontroller för Microsoft-molntjänster som Microsoft implementerar åt dig
- **Dina kontroller:** kallas ibland för kund hanterade kontroller, dessa är kontroller implementerade och hanterade av din organisation
- **Delade kontroller:** det här är kontroller som både din organisation och Microsoft har ansvar för att implementera
- **Utvärderingsresultat:** Visar förloppet för att uppnå totalt antal möjliga poäng från åtgärder inom utvärderingen som hanteras av din organisation och av Microsoft

När du skapar utvärderingar tilldelar du dem till en grupp. Du kan konfigurera grupper på det sätt som är mest logiskt för din organisation. Du kan till exempel gruppera utvärderingar efter granskningsår, region, lösning, grupper inom organisationen eller på något annat sätt. När du har skapat grupper kan du [filtrera instrumentpanelen för Efterlevnadshanteraren](compliance-manager-setup.md#filtering-your-dashboard-view) och visa resultatet efter en eller flera grupper.

##### <a name="learn-more"></a>Mer information

[Skapa och hantera utvärderingar i Efterlevnadshanteraren.](compliance-manager-assessments.md)

### <a name="templates"></a>Mallar

Efterlevnadshanteraren innehåller mallar som hjälper dig att snabbt skapa utvärderingar. Du kan ändra de här mallarna för att skapa en utvärdering som är optimerad för dina behov. Du kan också skapa en anpassad bedömning genom att skapa en mall med egna kontroller och åtgärder. Du kanske till exempel vill ha en mall som omfattar en intern affärsprocesskontroll eller en regional dataskyddsstandard som inte omfattas av någon av våra färdiga 325 utvärderingsmallar.

##### <a name="learn-more"></a>Mer information

[Visa listan över utvärderingsmallar som tillhandahålls av Efterlevnadshanteraren.](compliance-manager-templates-list.md)

[Få detaljerade instruktioner för att skapa och ändra mallar för utvärderingar.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Förbättringsåtgärder

Förbättringsåtgärder hjälper till att centralisera efterlevnadsaktiviteter. Varje förbättringsåtgärd ger rekommenderade riktlinjer som är avsedda att hjälpa dig att anpassa till dataskyddsföreskrifter och standarder. Förbättringsåtgärder kan tilldelas till användare i organisationen för att utföra implementerings- och testarbete. Du kan också lagra dokumentation, anteckningar och spela in statusuppdateringar i förbättringsåtgärden.

##### <a name="learn-more"></a>Mer information

[Använd förbättringsåtgärder för att hantera arbetsflödet för efterlevnad.](compliance-manager-improvement-actions.md)

[Läs om hur åtgärder påverkar ditt efterlevnadsresultat](compliance-score-calculation.md#action-types-and-points).

## <a name="supported-languages"></a>Språk som stöds

Efterlevnadshanteraren är tillgänglig på följande språk:

- Engelska
- Bahasa Indonesian
- Bahasa Malajiska
- Kinesiska (förenklad)
- Kinesiska (traditionell)
- Czech
- Danish
- Dutch
- Finnish
- French
- German
- Hebrew
- Hungarian
- Italian
- Japanska
- Koreanska
- Norska
- Polish
- Portugisiska (Brasilien)
- Russian
- Spanish
- Swedish
- Thai
- Turkish

## <a name="next-steps-set-up-and-customize"></a>Nästa steg: konfigurera och anpassa

Läs om hur du loggar in, tilldelar behörigheter och roller, konfigurerar inställningar och anpassar instrumentpanelsvyn i [Kom igång med Efterlevnadshanteraren.](compliance-manager-setup.md)

Börja sedan anpassa Efterlevnadshanteraren så att du kan följa de branschstandarder som är viktigast för din organisation genom [att konfigurera utvärderingar.](compliance-manager-assessments.md)

För att hjälpa dig att följa regler om datasekretess har vi utformat ett arbetsflöde som vägleder dig genom en end-to-end-process för att planera och implementera funktioner i Microsoft 365, inklusive användning av Efterlevnadshanteraren. Mer information finns i [Distribuera informationsskydd för föreskrifter för datasekretess med Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 