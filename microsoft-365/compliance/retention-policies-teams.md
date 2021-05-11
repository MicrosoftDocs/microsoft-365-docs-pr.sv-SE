---
title: Mer information om kvarhållning för Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Läs mer om de kvarhållningsprinciper som gäller för Microsoft Teams.
ms.openlocfilehash: db167894f32bcc1e30054b9cc4738af300b6d704
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280805"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Mer information om kvarhållning för Microsoft Teams

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Om du ser ett meddelande i Teams om att chattar eller meddelanden har tagits bort av en kvarhållningsprincip kan du läsa [Teams-meddelanden om bevarandeprinciper](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Informationen på den här sidan är avsedd för IT-administratörer som hanterar de här kvarhållningsprinciperna.

Den här artikeln kompletterar avsnittet [Mer information om kvarhållning](retention.md) eftersom den innehåller mer specifik information om Microsoft Teams-meddelanden.

För övriga arbetsbelastningar finns information i:

- [Mer information om kvarhållning för SharePoint och OneDrive](retention-policies-sharepoint.md)
- [Lär dig mer om kvarhållning för Yammer](retention-policies-yammer.md)
- [Lär dig mer om kvarhållning för Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Vad omfattas för kvarhållning och borttagning

Teams-chattmeddelanden och Teams-kanalmeddelanden kan tas bort med hjälp av kvarhållningsprinciper för Teams, och utöver texten i meddelandena kan följande objekt bevaras av efterlevnadsskäl: Inbäddade bilder, tabeller, hypertextlänkar, länkar till andra Teams-meddelanden och -filer och [kortinnehåll](/microsoftteams/platform/task-modules-and-cards/what-are-cards). I chattmeddelanden ingår alla namn på personer i chatten, och i kanalmeddelanden ingår teamets namn och meddelanderubriken (om de har angetts). 

> [!NOTE]
> Möjligheten att ta med kortinnehåll i en kvarhållningsprincip för Teams lades till ganska nyligen. Mer information finns i [Microsoft 365 compliance capabilities for Adaptive Card content through apps in Teams now available](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

Kvarhållningsprinciper kan för närvarande inte användas för Teams-meddelanden i privata kanaler. Kodfragment, inspelade röstmeddelanden från Teams-mobilklienten, miniatyrer, meddelandebilder och reaktioner från andra i form av uttryckssymboler bevaras inte när du använder kvarhållningsprinciper för Teams.

E-postmeddelanden och filer som du använder med Teams omfattas inte av kvarhållningsprinciper för Teams. Dessa objekt har egna kvarhållningsprinciper.

## <a name="how-retention-works-with-microsoft-teams"></a>Så fungerar kvarhållning för Microsoft Teams

I det här avsnittet beskrivs hur lagringen och processerna på serverdelen uppfyller dina efterlevnadskrav, och varför de bör verifieras med eDiscovery-verktyg i stället för med de meddelanden som för närvarande visas i Teams-appen.

Du kan bevara data från chattar och kanalmeddelanden i Teams, och ta bort dessa chattar och meddelanden, med hjälp av en kvarhållningsprincip. Bakom kulisserna används Exchange-postlådor för att lagra data som kopieras från dessa meddelanden. Data från Teams-chattar lagras i en dold mapp i postlådan för varje användare som ingår i chatten, och en liknande dold mapp i en gruppostlåda används för Teams-kanalmeddelanden. De dolda mapparna är inte avsedda att vara direkt tillgängliga för användare eller administratörer, utan för att lagra data som efterlevnadsadministratörer kan söka i med eDiscovery-verktyg.

Postlådorna visas med sitt RecipientTypeDetails-attribut:

- **UserMailbox**: I de här postlådorna lagras meddelandedata för molnbaserade Teams-användare.
- **MailUser**: I de här postlådorna lagras meddelandedata för [lokala Teams-användare](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: I de här postlådorna lagras meddelandedata för Teams-kanaler.

Kvarhållningsprinciper för Teams kan inte användas med andra postlådetyper som RoomMailbox, som används för Teams-konferensrum.

I Teams används en Azure-baserad chattjänst som primär lagringsplats för alla meddelanden (chattar och kanalmeddelanden). Om du behöver ta bort Teams-meddelanden av efterlevnadsskäl kan du använda kvarhållningsprinciper för Teams till att ta bort meddelanden efter en viss tidsperiod, baserat på när de skapades. Meddelandena tas sedan bort permanent från både de Exchange-postlådor där de lagras för efterlevnadsåtgärder och från den primära lagringsplatsen som används av den underliggande Azure-baserade chattjänsten. Mer information om den underliggande arkitekturen finns i [Säkerhet och efterlevnad i Microsoft Teams](/MicrosoftTeams/security-compliance-overview), och mer specifikt i avsnittet om [arkitektur för informationsskydd](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Trots att data från Teams-chattar och Teams-kanalmeddelanden lagras i postlådor måste du konfigurera en kvarhållningsprincip för platserna **Teams-kanalmeddelanden** och **Teams-chattar**. Teams-chattar och Teams-kanalmeddelanden ingår inte i de kvarhållningsprinciper som är konfigurerade för Exchange-postlådor för användare eller grupper.

> [!NOTE]
> Om en användare ingår i en aktiv kvarhållningsprincip som bevarar Teams-meddelanden och du tar bort en postlåda för en användare som ingår i den här principen, konverteras postlådan till en [inaktiv postlåda](inactive-mailboxes-in-office-365.md) för att bevara Teams-data. Om du inte behöver bevara Teams-data för användaren ska du exkludera användarkontot från kvarhållningsprincipen innan du tar bort postlådan.

När en kvarhållningsprincip har konfigurerats för chatt- och kanalmeddelanden utvärderar ett tidsinställt jobb från Exchange-tjänsten regelbundet objekt i den dolda mappen där dessa Teams-meddelanden lagras. Det tidsinställda jobbet tar normalt en till sju dagar att köra. När objekten har upphört att gälla flyttas de till mappen Program, en annan dold mapp i varje användar- eller gruppostlåda där "mjukt borttagna" objekt lagras innan de tas bort permanent. 

Meddelanden finns kvar i mappen SubstrateHolds i minst en dag, och om de sedan är kvalificerade för borttagning tas de bort permanent nästa gång det tidsinställda jobbet körs.

När en kvarhållningsprincip har konfigurerats för chatt- och kanalmeddelanden beror sökvägarna till innehållet på om kvarhållningsprincipen är inställd på att bevara och sedan ta bort, endast bevara eller endast ta bort meddelanden.

När kvarhållningsprincipen är inställd på att behålla och sedan ta bort meddelanden gör du följande:

![Diagram över kvarhållningsflödet för Teams chatt- och kanalmeddelanden](../media/teamsretentionlifecycle.png)

För de två sökvägarna i diagrammet:

1. **Om ett chatt- eller kanalmeddelande redigeras eller tas bort** av en användare under kvarhållningsperioden kopieras det ursprungliga meddelandet (om det redigeras) eller flyttas (om det tas bort) till mappen SubstrateHolds. Meddelandet lagras där i minst en dag. När kvarhållningsperioden går ut tas meddelandet bort permanent nästa gång det tidsinställda jobbet körs (normalt efter 1–7 dagar).

2. **Om ett chatt- eller kanalmeddelande inte tas bort** av en användare och för aktuella meddelanden efter redigering flyttas meddelandet till mappen SubstrateHolds efter att det har gått ut. Den här åtgärden tar normalt mellan en till sju dagar från utgångsdatumet. När meddelandet finns i mappen SubstrateHolds lagras det där i minst en dag. Meddelandet tas sedan bort permanent nästa gång det tidsinställda jobbet körs (normalt mellan en till sju dagar). 

> [!NOTE]
> Meddelanden som lagras i postlådor, inklusive dolda mappar, är sökbara med eDiscovery-verktyg. Meddelandena förblir sökbara med eDiscovery-verktyg tills de tas bort permanent från mappen SubstrateHolds.

När meddelanden tas bort permanent från mappen SubstrateHolds skickas ett meddelande om borttagningsåtgärden till Azure-chattjänsten på serverdelen som sedan vidarebefordrar denna åtgärd till Teams-klientappen. Fördröjningar i den här kommunikationen eller cachelagringen kan förklara varför användare under en kort tid fortfarande kan se de här meddelandena i Teams-appen men inga data från meddelandena returneras i eDiscovery-sökningar. Meddelanden som visas i Teams-appen ger inte en korrekt bild av om de bevaras eller tas bort permanent för efterlevnadskrav.

När kvarhållningsprincipen endast ska behålla eller endast ta bort, är innehållssökvägarna varianter av behålla eller ta bort.

### <a name="content-paths-for-retain-only-retention-policy"></a>Innehållssökvägar för kvarhållningsprincip för endast kvarhållning

1. **Om ett chatt- eller kanalmeddelande redigeras eller tas bort** av en användare under kvarhållningsperioden kopieras det ursprungliga meddelandet (om det redigeras) eller flyttas (om det tas bort) till mappen SubstrateHolds. Meddelandet bevaras där i minst en dag. Om kvarhållningsprincipen är konfigurerad för att bevara meddelandet permanent finns objektet kvar där. Om kvarhållningsprincipen har ett slutdatum för kvarhållningsperioden och den går ut, tas meddelandet bort permanent nästa gång det tidsinställda jobbet körs (normalt efter en till sju dagar).

2. **Om chatt- eller kanalmeddelandet inte ändras eller tas bort** av en användare och för aktuella meddelanden efter redigering under kvarhållningsperioden händer ingenting före och efter kvarhållningsperioden och meddelandet förblir på sin ursprungliga plats.

### <a name="content-paths-for-delete-only-retention-policy"></a>Innehållssökvägar för kvarhållningsprincip för endast borttagning

1. **Om ett chatt- eller kanalmeddelande redigeras eller tas bort** av en användare under kvarhållningsperioden kopieras det ursprungliga meddelandet (om det redigeras), eller så flyttas det (om det tas bort) till mappen SubstrateHolds. Meddelandet bevaras där i minst en dag och tas bort permanent nästa gång det tidsinställda jobbet körs (normalt efter en till sju dagar).

2. **Om ett chatt- eller kanalmeddelande inte tas bort** av en användare under kvarhållningsperioden flyttas meddelandet till mappen SubstrateHolds när kvarhållningsperioden har gått ut. Den här åtgärden tar normalt mellan en till sju dagar från utgångsdatumet. Meddelandet bevaras där i minst en dag och tas sedan bort permanent nästa gång det tidsinställda jobbet körs (normalt efter en till sju dagar).

#### <a name="example-flows-and-timings-for-retention-policies"></a>Exempel på flöden och tidsinställningar för kvarhållningsprinciper

I följande exempel kan du se hur de processer och tidsinställningar som beskrevs i föregående avsnitt tillämpas för kvarhållningsprinciper som har följande konfigurationer:

- [Exempel 1: Endast kvarhållning i sju år](#example-1-retain-only-for-7-years)
- [Exempel 2: Bevara i 30 dagar och ta sedan bort](#example-2-retain-for-30-days-and-then-delete)
- [Exempel 3: Endast borttagning efter en dag](#example-3-delete-only-after-1-day)

För alla exempel som gäller permanent borttagning, enligt [kvarhållningsprinciperna](retention.md#the-principles-of-retention-or-what-takes-precedence), inaktiveras den här åtgärden om meddelandet är underställt en annan kvarhållningsprincip som innebär att objektet bevaras eller om det omfattas av ett eDiscovery-undantag.

##### <a name="example-1-retain-only-for-7-years"></a>Exempel 1: Endast kvarhållning i sju år

Dag ett skapar en användare ett chatt- eller kanalmeddelande.

Dag fem redigerar användaren meddelandet.

Dag 30 tar användaren bort det aktuella meddelandet.

Kvarhållningsresultat:

- För det ursprungliga meddelandet:
    - Dag fem kopieras meddelandet till mappen SubstrateHolds där det fortfarande är sökbart med eDiscovery-verktyg i minst sju år från dag ett (kvarhållningsperioden).

- För det aktuella (redigerade) meddelandet:
    - Dag 30 flyttas meddelandet till mappen SubstrateHolds där det fortfarande är sökbart med eDiscovery-verktyg i minst sju år från dag ett (kvarhållningsperioden).

Om användaren hade tagit bort det aktuella meddelandet efter den angivna kvarhållningsperioden, i stället för inom kvarhållningsperioden, hade meddelandet ändå flyttats till mappen SubstrateHolds. Men efter att kvarhållningsperioden har gått ut tas i det här fallet meddelandet bort permanent efter minst en dag och sedan normalt inom en till sju dagar.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Exempel 2: Bevara i 30 dagar och ta sedan bort

Dag ett skapar en användare ett chatt- eller kanalmeddelande.

Dag tio redigerar användaren meddelandet.

Användaren gör inga ytterligare redigeringar och tar inte bort meddelandet.

Kvarhållningsresultat:

- För det ursprungliga meddelandet:
    - Dag tio kopieras meddelandet till mappen SubstrateHolds där det fortfarande är sökbart med eDiscovery-verktyg.
    - I slutet av kvarhållningsperioden (efter 30 dagar från dag ett) tas meddelandet bort permanent normalt inom en till sju dagar efter minst en dag och returneras inte längre i eDiscovery-sökningar.

- För det aktuella (redigerade) meddelandet:
    - I slutet av kvarhållningsperioden (efter 30 dagar från dag ett) flyttas meddelandet till mappen SubstrateHolds (normalt inom en till sju dagar) där det fortfarande är sökbart med eDiscovery-verktyg.
    - Meddelandet tas sedan bort permanent, normalt inom en till sju dagar efter minst en dag, och returneras sedan inte längre i eDiscovery-sökningar.

##### <a name="example-3-delete-only-after-1-day"></a>Exempel 3: Endast borttagning efter en dag

> [!NOTE]
> Eftersom den här konfigurationen har en kort varaktighet på en dag och kvarhållningsprocesser som körs inom en till sju dagar innehåller det här avsnittet exempel på tidsinställningar som ligger inom typiska tidsintervall.

Dag ett skapar en användare ett chatt- eller kanalmeddelande.

Exempel på kvarhållningsresultat om användaren inte redigerar eller tar bort meddelandet:

- Dag 5 (normalt 1-7 dagar efter att kvarhållningsperioden börjat dag 2):
    - Meddelandet flyttas till mappen SubstrateHolds och finns kvar där i minst 1 dag där det fortfarande kan genomsökas med eDiscovery-verktyg.

- Dag 9 (normalt en till sju dagar efter minst en dag i mappen SubstrateHolds):
    - Meddelandet tas bort permanent och returneras därmed inte i eDiscovery-sökningar.

Som detta exempel visar, även om du kan konfigurera en kvarhållningsprincip för att ta bort meddelanden efter bara en dag, genomgår tjänsten flera processer för att säkerställa en kompatibel borttagning. När en borttagningsåtgärd utförs efter 1 dag kan det därför ta 16 dagar innan meddelandet tas bort permanent och inte längre returneras i eDiscovery-sökningar.

## <a name="skype-for-business-and-teams-interop-chats"></a>Interop-chattar för Skype för företag och Teams

När en Skype för företag-chatt kommer till Teams blir den ett meddelande i en Teams-chattråd och matas in i rätt postlåda. Kvarhållningsprinciperna för Teams gäller för dessa meddelanden från Teams-tråden. 

Men om konversationshistorik har aktiverats för Skype för företag och den historiken sparas i en postlåda från Skype för företag-klientsidan, hanteras dessa chattdata inte av kvarhållningsprincipen för Teams. För det innehållet använder du en kvarhållningsprincip som är konfigurerad för Skype för företag.

## <a name="meetings-and-external-users"></a>Möten och externa användare

Kanalmötesmeddelanden lagras på samma sätt som kanalmeddelanden. För dessa data väljer du platsen **Teams-kanalmeddelanden** när du konfigurerar kvarhållningsprincipen.

Meddelanden för improviserade och schemalagda möten lagras på samma sätt som gruppchattmeddelanden. För dessa data väljer du platsen **Teams-chattar** när du konfigurerar kvarhållningsprincipen.

När externa användare ingår i ett möte som organisationen är värd för:

- Om en extern användare ansluter med hjälp av ett gästkonto i din klientorganisation har användaren en skuggpostlåda som kan omfattas av organisationens kvarhållningsprincip för Teams. Alla meddelanden från mötet lagras både i användarnas postlåda och i skuggpostlådan. 

- Om en extern användare ansluter med ett annat konto från en annan Microsoft 365-organisation kan dina kvarhållningsprinciper inte ta bort meddelandena för den här användaren eftersom de lagras i användarens postlåda i en annan klientorganisation. Däremot kan kvarhållningsprinciperna ta bort meddelanden för dina användare.

## <a name="when-a-user-leaves-the-organization"></a>När en användare lämnar organisationen 

Om en användare som har en postlåda i Exchange Online lämnar organisationen och användarens Microsoft 365-konto tas bort lagras de chattmeddelanden som kan behållas i en inaktiv postlåda. Chattmeddelandena omfattas fortfarande av de kvarhållningsprinciper som angetts för användaren innan postlådan inaktiverades, och innehållet är tillgängligt för eDiscovery-sökningar. Mer information finns under [Inaktiva postlådor i Exchange Online](inactive-mailboxes-in-office-365.md). 

Om användaren har lagrat några filer i Teams kan du se [motsvarande avsnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) för SharePoint och OneDrive.

## <a name="limitations"></a>Begränsningar

Vi arbetar kontinuerligt med att optimera kvarhållningsfunktionen i Teams. Under tiden bör du vara medveten om följande begränsning när du använder kvarhållningsprinciper för Teams-kanalmeddelanden och Teams-chattar:

- **Problem med felaktig visning i Outlook**. Om du skapar kvarhållningsprinciper för Skype- eller Teams-platser visas en av dessa principer som standardmapprincip när en användare visar egenskaperna för en postlådemapp i skrivbordsversionen av Outlook. Det här är en felaktig visning i Outlook och [ett känt problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). I stället bör du titta på kvarhållningsprincipen för postlådan som tillämpas på mappen. Kvarhållningsprincipen för Skype eller Teams tillämpas inte på användarens postlåda.

## <a name="configuration-guidance"></a>Konfigurationsvägledning

Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).

Se [Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md) om du vill konfigurera en kvarhållningsprincip för Teams.