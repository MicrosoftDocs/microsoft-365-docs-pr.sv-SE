---
title: Snabba uppgifter för att komma igång med Microsoft 365 Efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Läs mer om uppgifter som hjälper dig att snabbt komma igång med efterlevnad i Microsoft 365.
ms.openlocfilehash: 61a057c3666faae51a012dd9db2d4c63ded0f77a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227265"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Snabba uppgifter för att komma igång med Microsoft 365 Efterlevnadscenter

Om du är nybörjare på att Microsoft 365 efterlevnad och undrar var du ska börja, innehåller den här artikeln vägledning om grunderna och prioriterar viktiga efterlevnadsuppgifter. Den här artikeln hjälper dig att snabbt komma igång med att hantera och övervaka dina data, skydda information och minimera Insider-risker.

Den här artikeln är också användbar om du tar reda på hur du bäst hanterar risker, skyddar dina data och förblir kompatibel med bestämmelser och standarder med en nyligen fjärransluten arbetsstyrka. Anställda samarbetar och samarbetar nu med varandra på nya sätt, vilket innebär att befintliga efterlevnadsprocesser och kontroller kan behöva anpassas. Att identifiera och hantera dessa nya efterlevnadsrisker i organisationen är avgörande för att skydda dina data och minimera hot och risker.

När du har utfört de här grundläggande efterlevnadsuppgifterna kan du utöka täckningen för efterlevnad i organisationen genom att implementera ytterligare Microsoft 365 efterlevnadslösningar.

## <a name="task-1-configure-compliance-permissions"></a>Uppgift 1: Konfigurera efterlevnadsbehörigheter

Det är viktigt att hantera vem i organisationen som har åtkomst till Microsoft 365 Efterlevnadscenter visa innehåll och utföra administrativa uppgifter. Microsoft 365 administrativa roller som är specifika för efterlevnad och användning av verktyg som ingår i Microsoft 365 Efterlevnadscenter.

Börja med att tilldela efterlevnadsbehörigheter till personer i organisationen så att de kan utföra dessa uppgifter och förhindra att obehöriga personer får åtkomst till områden utanför deras ansvarsområden. Se till att du har tilldelat rätt personer till  administratörsrollerna  för efterlevnadsdata och efterlevnadsadministratörer innan du börjar konfigurera och implementera efterlevnadslösningar som ingår i Microsoft 365. Du måste också tilldela användare rollen som global Azure Active Directory för att visa data i Efterlevnadshanteraren.

Stegvisa instruktioner för hur du konfigurerar behörigheter och tilldelar personer administratörsroller finns i Behörigheter i Säkerhets- & [efterlevnadscenter.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Uppgift 2: Känna till statusen för efterlevnad

Det är svårt att veta vart du ska gå om du inte vet var du är. När du uppfyller dina efterlevnadsbehov måste du förstå din aktuella risknivå och vilka uppdateringar som kan behövas under dessa tider. Oavsett om organisationen uppfyller alla efterlevnadskrav eller har djupgående erfarenhet av standarder och bestämmelser som styr din bransch är det enda du kan göra för att förbättra efterlevnad att förstå var din organisation står.

[Microsoft Compliance Manager kan](compliance-manager.md) hjälpa dig att förstå organisationens efterlevnadsförbättringar och framhäva områden som kan behöva förbättras. Efterlevnadshanteraren använder en centraliserad instrumentpanel för att beräkna ett riskbaserat resultat, som mäter hur långt du kommit med att slutföra åtgärder som hjälper till att minska risker för dataskydd och regelstandarder. Du kan också använda Efterlevnadshanteraren som ett verktyg för att spåra alla dina riskhanteringsbedömningar. Det innehåller arbetsflödesfunktioner som hjälper dig att effektivt slutföra dina riskutvärderingar via ett vanligt verktyg.

Stegvisa instruktioner för hur du kommer igång med Efterlevnadshanteraren finns i [Komma igång med Efterlevnadshanteraren.](compliance-manager-setup.md)

> [!IMPORTANT]
> Säkerhet och efterlevnad är nära integrerade för de flesta organisationer. Det är viktigt att din organisation tar itu med grundläggande säkerhets-, hotskydd och identitets- och åtkomsthanteringsområden för att bidra till ett bättre skydd för både säkerhet och efterlevnad.
>
> Kontrollera ditt [Microsoft 365 Secure Score](../security/defender/microsoft-secure-score.md) i Microsoft 365 säkerhetscenter och slutföra uppgifter som beskrivs i följande artiklar:
>
> - [Säkerhetsöversikt – Högsta prioritet de första 30 dagarna, 90 dagarna och därefter](../security/office-365-security/security-roadmap.md)
> - [De 12 viktigaste uppgifterna för säkerhetsteam att stödja arbetet hemifrån](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Uppgift 3: Aktivera granskning för organisationen

Nu när du har fastställt organisationens aktuella status och vem som kan hantera efterlevnadsfunktioner är nästa steg att se till att du har de data som finns för att utföra efterlevnadsundersökningar och generera rapporter för nätverks- och användaraktiviteter i organisationen. Att aktivera granskning är också en viktig förutsättning för efterlevnadslösningar som beskrivs senare i den här artikeln.

Insights som tillhandahålls av granskningsloggen är ett värdefullt verktyg som hjälper dig att matcha dina efterlevnadskrav med lösningar som kan hjälpa dig att hantera och övervaka efterlevnadsområden som behöver förbättras. Granskningsloggning måste vara aktiverad innan aktiviteter registreras och innan du kan söka i granskningsloggen. När den är aktiverad registreras användar- och administratörsaktiviteten från organisationen i granskningsloggen och sparas i 90 dagar, och upp till ett år beroende på vilken licens som tilldelats användarna.

Stegvisa instruktioner för hur du aktiverar granskning finns i [Aktivera eller inaktivera granskningsloggsökning.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Uppgift 4: Skapa principer för att varna dig om potentiella efterlevnadsproblem

Microsoft tillhandahåller flera inbyggda aviseringsprinciper som hjälper till att identifiera missbruk av administratörsbehörigheter, skadlig programvara, potentiella externa och interna hot och informationsstyrningsrisker. Dessa principer är aktiverat som standard, men du kan behöva konfigurera anpassade aviseringar för att hantera efterlevnadskrav som är specifika för din organisation.

Använd verktyg för aviseringsprincip och instrumentpanel för aviseringar för att skapa anpassade aviseringsprinciper och visa aviseringar som genereras när användare utför aktiviteter som matchar principvillkoren. Några exempel kan vara att använda aviseringsprinciper för att spåra användar- och administratörsaktiviteter som påverkar efterlevnadskrav, behörigheter och incidenter för dataförlust i organisationen.

Stegvisa instruktioner för hur du skapar anpassade aviseringsprinciper finns [i Aviseringsprinciper i säkerhets- och efterlevnadscentret.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Uppgift 5: Klassificera och skydda känsliga data

För att få jobbet gjort samarbetar personer i organisationen med andra personer både inom och utanför organisationen. Det här leder till att innehållet inte längre ligger bakom en brandvägg – det kan överföras överallt, på olika enheter och i olika appar och tjänster. När det överförs på det här sättet behöver du se till att det gör det på ett säkert och skyddat sätt som följer organisationens affärs- och efterlevnadsprinciper.

[Med känslighetsetiketter](sensitivity-labels.md) kan du klassificera och skydda organisationens data, samtidigt som du ser till att användarproduktiviteten och möjligheten att samarbeta inte hindras. Använd känslighetsetiketter för att tillämpa kryptering och användningsbegränsningar tillämpa visuella markeringar och skydda information på plattformar och enheter, lokalt och i molnet.

Stegvisa instruktioner för hur du konfigurerar och använder känslighetsetiketter finns i [Komma igång med känslighetsetiketter.](get-started-with-sensitivity-labels.md) Information om känslighetsetikettslicensiering finns [i Microsoft 365 om licensieringsvägledning för & kompatibilitet.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="task-6-configure-a-retention-policy"></a>Uppgift 6: Konfigurera en bevarandeprincip

Med [en bevarandeprincip](retention.md) kan du proaktivt bestämma om du vill behålla innehåll, ta bort innehåll eller både och – behålla och sedan ta bort innehållet i slutet av en angiven bevarandeperiod. Dessa åtgärder kan behövas för att följa branschföreskrifter och interna principer, samt för att minska risken för tvister eller säkerhetsintrång.

När innehållet omfattas av en bevarandeprincip kan användare fortsätta att redigera och arbeta med innehållet som om ingenting skulle ändras. Innehållet sparas på dess ursprungliga plats. Men om någon redigerar eller tar bort innehåll som omfattas av bevarandeprincipen sparas en kopia av det ursprungliga innehållet på en säker plats där den bevaras medan bevarandeprincipen för innehållet gäller.

Du kan snabbt skapa en bevarandeprincip för flera platser i Microsoft 365-miljön, till exempel Exchange-e-post, SharePoint-webbplatser, OneDrive-konton och Microsoft 365 grupper. Det finns inga begränsningar för antalet postlådor eller webbplatser som principen kan inkludera automatiskt. Men om du behöver få fler selektiva kan du göra det genom att konfigurera en bevarandeprincip för specifika platser och inkludera eller exkludera webbplatser eller användare.

Stegvisa instruktioner för hur du konfigurerar en bevarandeprincip finns i [Skapa och konfigurera bevarandeprinciper.](create-retention-policies.md) Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Uppgift 7: Konfigurera principer för känslig information och stötande språk

Att skydda känslig information och identifiera och agera på arbetsplatsens trakasserier är en viktig del av efterlevnad av interna principer och standarder. [Kommunikationsefterlevnad](communication-compliance-feature-reference.md) i Microsoft 365 hjälper till att minimera dessa risker genom att snabbt upptäcka, fånga in och vidta åtgärder för e-Microsoft Teams kommunikation. Det omfattar olämplig kommunikation som innehåller svordomar, hot, trakasserier och kommunikationer som delar känslig information inom och utanför organisationen.

Med en fördefinierad *policymall* för anstötligt språk och skydd mot trakasserier kan du söka igenom intern och extern kommunikation efter principmatchningar så att de kan behandlas av angivna granskare. Granskare kan undersöka skannad e-post, Microsoft Teams, Yammer eller kommunikation från tredje part i organisationen och vidta lämpliga åtgärder för att säkerställa att de följer organisationens standarder.

Med den fördefinierade principmallen för känslig *information* kan du snabbt skapa en princip för att skanna e-post och Microsoft Teams-kommunikationer som innehåller definierade typer av känslig information eller nyckelord för att säkerställa att viktiga data inte delas med personer som inte ska ha åtkomst. Dessa aktiviteter kan omfatta obehörig kommunikation om konfidentiella projekt eller branschspecifika regler för Insider-handel eller andra sorteringsaktiviteter.

Stegvisa instruktioner för hur du planerar och konfigurerar kommunikationsefterlevnad finns i Planera för [kommunikationsefterlevnad](communication-compliance-plan.md) och [Komma igång med kommunikationsefterlevnad.](communication-compliance-configure.md) Information om licensiering för kommunikationsefterlevnad finns [Microsoft 365 vägledning för licensiering för säkerhet och & efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Uppgift 8: Se vad som händer med känsliga objekt

Känslighetsetiketter, typer av känslig information, kvarhållningsetiketter och utbildande klassificerare kan användas för att klassificera och märka känsliga objekt i olika Exchange, SharePoint och OneDrive som du har sett i tidigare uppgifter. Det sista steget i din snabba uppgiftsresa är att se vilka objekt som har etiketterats och vilka åtgärder dina användare vidtar för dessa känsliga objekt. [innehållsutforskaren](data-classification-content-explorer.md) [och aktivitetsutforskaren](data-classification-activity-explorer.md) ger denna synlighet.

### <a name="content-explorer"></a>Innehållsutforskaren
 Med Innehållsutforskaren kan du visa alla objekt som har klassificerats som en typ av känslig information eller tillhör en viss klassificering av en utbildare som klassificerare, samt alla objekt som är känslighets- eller bevarandeetiketter tillämpade.

Stegvisa instruktioner för hur du använder Innehållsutforskaren finns i Avsnittet Känner till dina [data – översikt](data-classification-overview.md)över dataklassificering och [Komma igång med Innehållsutforskaren.](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Aktivitetsutforskare
Med Aktivitetsutforskaren kan du övervaka vad som görs med dina klassificerade och etiketterade känsliga objekt:
- SharePoint
- Exchange
- OneDrive

Det finns över 30 olika filter att använda och några är:

- datumintervall
- aktivitetstyp
- plats
- användare
- känslighetsetikett
- bevarandeetikett
- filsökväg
- DLP-princip

Stegvisa instruktioner för hur du använder aktivitetsutforskaren finns i [Komma igång med aktivitetsutforskaren.](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Nästa steg

Nu när du har konfigurerat grunderna för efterlevnadshantering för din organisation kan du överväga följande efterlevnadslösningar i Microsoft 365 för att hjälpa dig att skydda känslig information och identifiera och agera mot ytterligare Insider-risker.

### <a name="configure-retention-labels"></a>Konfigurera bevarandeetiketter

Bevarandeprinciper gäller på behållarnivå för platser som SharePoint och Exchange-postlådor, men bevarandeetiketter ger ett mer specifikt mål för bevarande- och borttagningsprinciper. [](retention.md#retention-labels) På dokument- eller e-postnivå kan till exempel slutanvändarna tillämpa manuellt utöver automatiska program av administratörer. Du kan också använda en bevarandeetikett för ett dokumentbibliotek, en mapp eller ett dokument som finns i SharePoint, så att alla dokument som lagras på den platsen ärver standardetiketten för bevarande.

Bevarandeetiketter har dessutom stöd för [hantering av arkivhandlingar](records-management.md) för att markera innehåll som en arkivpost. När detta händer lägger etiketten ytterligare begränsningar på innehållet som kan behövas för att hjälpa din organisation att uppfylla kraven i lagstiftningen.

Stegvisa instruktioner för hur du skapar och publicerar bevarandeetiketter finns i följande vägledning:
- [Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)
- [Använda en kvarhållningsetikett för innehåll automatiskt](apply-retention-labels-automatically.md)

Information om hur du kommer igång med hantering av arkivhandlingar finns [i Komma igång med hantering av arkivhandlingar.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identifiera och definiera typer av känslig information

Definiera typer av känslig information baserat på det mönster som finns i informationen i organisationens data. Använd [inbyggda typer av känslig information för](./sensitive-information-type-entity-definitions.md) att identifiera och skydda kreditkortsnummer, bankkontonummer, passnummer och mycket mer. Eller skapa dina egna [typer av känslighetsinformation som](create-a-custom-sensitive-information-type.md) är specifika för din organisation.

Stegvisa anvisningar för hur du definierar anpassade typer av känslig information finns i Skapa en anpassad typ av känslig information i Säkerhets- & [Efterlevnadscenter.](./create-a-custom-sensitive-information-type.md)

### <a name="prevent-data-loss"></a>Förhindra dataförlust

[Med DLP-principer (Data Loss Prevention)](dlp-learn-about-dlp.md) kan du identifiera, övervaka och automatiskt skydda känslig information i hela Microsoft 365 organisation. Använd DLP-principer för att identifiera känsliga objekt i Microsoft-tjänster, förhindra att känsliga objekt delas av misstag och hjälpa användarna att lära sig hur de följer reglerna utan att avbryta arbetsflödet.

Stegvisa instruktioner för hur du konfigurerar DLP-principer finns [i Skapa, testa och finjustera en DLP-princip.](create-test-tune-dlp-policy.md) Information om licensiering för dataförlusthantering finns [i Microsoft 365 om licensieringsvägledning för & säkerhet och efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Upptäcka och agera på Insider-risker

Fler och fler medarbetare har växande tillgång till att skapa, hantera och dela data över en bred skala av plattformar och tjänster. I de flesta fall har organisationer begränsade resurser och verktyg för att identifiera och minimera risker för hela organisationen samtidigt som de uppfyller efterlevnadskrav och sekretessstandarder för anställda. Dessa risker kan vara datastöld genom att avgående anställda och dataläckor för information utanför organisationen kan vara en oavsiktlig överformning eller skadliga avsikter.

[Insider-riskhantering](insider-risk-management-policies.md) i Microsoft 365 använder tjänstens fullständiga bredd och indikatorer från tredje part för att snabbt identifiera, hantera och agera på riskabel användaraktivitet. Genom att använda loggar från Microsoft 365 och Microsoft Graph kan du med insider-riskhantering definiera specifika principer för att identifiera riskindikatorer och vidta åtgärder för att minimera dessa risker.

Stegvisa instruktioner för att planera och konfigurera insider-riskhanteringsprinciper finns i [Planera för insider-riskhantering](insider-risk-management-plan.md) och [Komma igång med Insider-riskhantering.](insider-risk-management-configure.md) Information om insider-riskhanteringslicensiering finns [Microsoft 365 vägledning för säkerhet och & efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)