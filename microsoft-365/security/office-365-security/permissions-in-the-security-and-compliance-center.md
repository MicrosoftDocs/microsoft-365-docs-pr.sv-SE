---
title: Behörigheter – Säkerhets- & Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Administratörer kan läsa mer om de behörigheter som är tillgängliga i Säkerhets- & kompatibilitetscenter i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 769396dc2c39b5b0efe2f1141f07e6c05f6a43bd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207169"
---
# <a name="permissions-in-the-security--compliance-center"></a>Behörigheter i Säkerhets- och efterlevnadscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Med säkerhets- & efterlevnadscenter kan du bevilja behörigheter till personer som utför efterlevnadsuppgifter, till exempel enhetshantering, skydd mot dataförlust, eDiscovery, bevarande och så vidare. De här personerna kan endast utföra de uppgifter som du uttryckligen beviljar dem åtkomst till. För att få tillgång & säkerhets- och efterlevnadscentret måste användarna vara globala administratörer eller medlemmar i en eller flera rollgrupper & Säkerhets- och efterlevnadscenter.

Behörigheter i Säkerhets- & Säkerhets- och efterlevnadscenter baseras på den rollbaserade behörighetsmodellen (RBAC). RBAC är samma behörighetsmodell som används i Exchange, så om du är bekant med Exchange kommer det att kännas välbekant att bevilja behörigheter i säkerhets- & säkerhets- och efterlevnadscentret. Det är dock viktigt att komma ihåg att rollgrupper i Exchange och säkerhetscenter & inte delar medlemskap eller behörigheter. Även om båda har rollgruppen Organisationshantering är de inte desamma. Behörigheterna de till beviljar och medlemmarna i rollgrupperna skiljer sig åt. Det finns en lista över rollgrupper & Säkerhets- och efterlevnadscenter nedan.

![Sidan Behörigheter i Säkerhets- & Säkerhets- och efterlevnadscenter](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och rollgrupper

En **roll** ger behörighet att utföra en uppsättning aktiviteter. Med rollen Ärendehantering kan personer till exempel arbeta med eDiscovery-ärenden.

En **rollgrupp** är en uppsättning roller som gör att personer kan göra sitt jobb i säkerhets- & efterlevnadscenter. Rollgruppen efterlevnadsadministratören inkluderar till exempel (bland andra roller) rollerna för Ärendehantering, Innehållssökning och Organisationskonfiguration (plus andra) eftersom någon som är efterlevnadsadministratör behöver behörighet för de uppgifterna för att utföra sitt jobb.

Säkerhets- & efterlevnadscenter innehåller standardrollgrupper för de vanligaste uppgifter och funktioner som du behöver tilldela personer till. Vi rekommenderar att du bara lägger till enskilda **användare som** medlemmar i standardrollgrupperna.

![Diagram som visar relationen mellan rollgrupper och roller och medlemmar](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Behörigheter som krävs för att använda funktioner i & Säkerhets- och efterlevnadscenter

I följande tabell visas de standardrollgrupper som är tillgängliga i Säkerhets- & efterlevnadscenter och de roller som är tilldelade till rollgrupperna som standard. Om du vill ge en användare behörighet att utföra en efterlevnadsuppgift lägger du till dem i rätt rollgrupp & Säkerhets- och efterlevnadscenter.

Hantering av behörigheter i Säkerhets- & efterlevnadscenter ger endast användare tillgång till de efterlevnadsfunktioner som är tillgängliga i själva & säkerhets- och efterlevnadscentret. Om du vill ge behörighet till andra efterlevnadsfunktioner som inte finns i Säkerhets- och efterlevnadscenter för &, till exempel Exchange-e-postflödesregler (kallas även transportregler), måste du använda administrationscentret för Exchange.

Information om hur du beviljar åtkomst till Säkerhets- och & finns i Artikeln om att ge användare åtkomst till administrationscentret för [Microsoft 365 efterlevnad.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Du måste **vara administratör** för att kunna visa fliken Behörigheter & Säkerhets- och efterlevnadscenter. Specifikt måste du tilldelas rollhanteringsrollen och den rollen  tilldelas endast till rollgruppen Organisationshantering i säkerhets- och efterlevnadscentret som standard & säkerhets- och efterlevnadscentret.  Med **rollhanteringsrollen** kan användarna dessutom visa, skapa och ändra rollgrupper.

<br><br>

****

|Rollgrupp|Beskrivning|Tilldelade standardroller|
|---|---|---|
|**Kommunikationsefterlevnad**|Ger behörighet till alla roller för kommunikationsefterlevnad: administratör, analytiker, administratörer och tittare.|Ärendehantering <p> Admin för kommunikationsefterlevnad <p> Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad <p> Undersökning av kommunikationsefterlevnad <p> Visningsprogram för kommunikationsefterlevnad <p> Dataklassificeringsfeedbackleverantör <p> View-Only case|
|**Administratörer för kommunikationsefterlevnad**|Administratörer för kommunikationsefterlevnad som kan skapa/redigera principer och definiera globala inställningar.|Admin för kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad|
|**Analytiker för kommunikationsefterlevnad**|Analytiker av kommunikationsefterlevnad som kan undersöka policymatchningar, visa metadata för meddelanden och vidta åtgärder.|Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad|
|**Kommunikationsefterlevnadsefterlevnadar**|Analytiker av kommunikationsefterlevnad som kan undersöka principmatchningar, visa meddelandeinnehåll och vidta åtgärder.|Ärendehantering <p> Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad <p> Undersökning av kommunikationsefterlevnad <p> Dataklassificeringsfeedbackleverantör <p> View-Only case|
|**Läsare av kommunikationsefterlevnad**|Tittare för kommunikationsefterlevnad som kan komma åt tillgängliga rapporter och widgetar.|Case Management för kommunikationsefterlevnad <p> Visningsprogram för kommunikationsefterlevnad|
|**Efterlevnadsadministratör**<sup>1</sup>|Medlemmarna kan hantera inställningar för enhetshantering, skydd mot dataförlust, rapporter och förvaring.|Ärendehantering <p> Efterlevnadsadministratör <p> Efterlevnadssökning <p> Dataklassificeringsfeedbackleverantör <p> Granskare för dataklassificeringsfeedback <p> Enhetshantering <p> Dispositionshantering <p> DLP-efterlevnadshantering <p> Håll ned <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> RecordManagement <p> Bevarandehantering <p> View-Only granskningsloggar <p> View-Only case <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Dataadministratör för efterlevnad**|Medlemmarna kan hantera inställningar för enhetshantering, dataskydd, skydd mot dataförlust, rapporter och förvaring.|Efterlevnadsadministratör <p> Efterlevnadssökning <p> Enhetshantering <p> DLP-efterlevnadshantering <p> Dispositionshantering <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> RecordManagement <p> Bevarandehantering <p> Administratör för känslighetsetikett <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Efterlevnadshanterarens administratörer**|Hantera skapande och ändring av mallar.|Efterlevnadshanteraren – administration <p> Utvärdering av Efterlevnadshanteraren <p> Bidrag till Efterlevnadshanteraren <p> Efterlevnadshanteraren Läsare|
|**Utvärderare i Efterlevnadshanteraren**|Skapa utvärderingar, implementera förbättringsåtgärder och uppdatera teststatus för förbättringsåtgärder.|Utvärdering av Efterlevnadshanteraren <p> Bidrag till Efterlevnadshanteraren <p> Efterlevnadshanteraren Läsare|
|**Deltagare i Efterlevnadshanteraren**|Skapa utvärderingar och utför arbete för att implementera förbättringsåtgärder.|Bidrag till Efterlevnadshanteraren <p> Efterlevnadshanteraren Läsare|
|**Läsare av Efterlevnadshanteraren**|Visa allt innehåll i Efterlevnadshanteraren utom administratörsfunktioner.|Efterlevnadshanteraren Läsare|
|**Innehållsvisningsprogram för Innehållsutforskaren**|Visa innehållsfilerna i Innehållsutforskaren.|Visningsprogram för dataklassificeringsinnehåll|
|**Visningsprogram för listor i Innehållsutforskaren**|Visa alla objekt i Innehållsutforskaren endast i listformat.|Visningsprogram för dataklassificeringslista|
|**eDiscovery Manager**|Medlemmar kan utföra sökningar och platsplatser i postlådor, SharePoint Online-webbplatser och OneDrive för företag-platser. Medlemmar kan också skapa och hantera eDiscovery-ärenden, lägga till och ta bort medlemmar i ett ärende, skapa och redigera innehållssökningar kopplade till ett ärende samt komma åt ärendedata i Avancerad eDiscovery. <p> En eDiscovery-administratör är medlem i rollgruppen för eDiscovery-hanteraren som har tilldelats ytterligare behörigheter. Förutom de uppgifter som en eDiscovery-hanterare kan utföra kan en eDiscovery-administratör:<ul><li>Visa alla eDiscovery-ärenden i organisationen.</li><li>Hantera alla eDiscovery-fall när de har lagt till sig själva som medlem i ärendet.</li></ul> <p> Den primära skillnaden mellan en eDiscovery-hanterare och en eDiscovery-administratör är att en eDiscovery-administratör kan komma åt alla fall som visas på sidan **eDiscovery-ärenden** i säkerhets- och &-efterlevnadscentret. En eDiscovery-hanterare kan bara komma åt de ärenden de skapat eller de fall där de är medlemmar. Mer information om hur du gör en användare till eDiscovery-administratör finns i Tilldela [eDiscovery-behörigheter](../../compliance/assign-ediscovery-permissions.md)i säkerhets- & efterlevnadscenter.|Ärendehantering <p> Kommunikation <p> Efterlevnadssökning <p> Insikare <p> Exportera <p> Håll ned <p> Förhandsgranska <p> Granska <p> RMS-dekryptera|
|**Global läsare**|Medlemmar har skrivskyddade åtkomst till rapporter, aviseringar och kan se alla konfigurationer och inställningar.<p> Den största skillnaden mellan Global Reader och Säkerhetsläsare är att en global läsare kan komma åt **konfiguration och inställningar.**|Säkerhetsläsare <p> Känslighetsetikettläsare <p> Vyn Tjänstgranskning <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Insider-riskhantering**|Använd den här rollgruppen för att hantera insider-riskhantering för organisationen i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker och administratörer kan du konfigurera behörigheter för Insider-riskhantering i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för Insider-riskhantering. Det här är det enklaste sättet att snabbt komma igång med insider-riskhantering. Det passar bra för organisationer som inte behöver separata behörigheter som definierats för olika användargrupper.|Ärendehantering <p> Insider-riskhanteringsadministratör <p> Insider-riskhanteringsanalys <p> Insider-undersökning av riskhantering <p> View-Only case|
|**Insider-riskhanteringsadministratörer**|Använd den här rollgruppen när du först konfigurerar Insider-riskhantering och senare för att dela upp Insider-riskadministratörer i en definierad grupp. Användare i den här rollgruppen kan skapa, läsa, uppdatera och ta bort principer för insider-riskhantering, globala inställningar och rollgruppstilldelningar.|Ärendehantering <p> Insider-riskhanteringsadministratör <p> View-Only case|
|**Analytiker för hantering av interna risker**|Använd den här gruppen för att tilldela behörigheter till användare som fungerar som insider-riskfallsanalytiker. Användare i den här rollgruppen har åtkomst till alla varningar och mallar för insider-riskhantering, ärenden och meddelanden. De kan inte komma åt Innehållsutforskaren med insiderrisk.|Ärendehantering <p> Insider-riskhanteringsanalys <p> View-Only case|
|**Insider-riskhanteringsgranskningar**|Granskare av Insider-riskhantering som kan visa granskningsloggar för åtgärder som utförts av analytiker, administratörer och administratörer.|Granskning av Insider-riskhantering|
|**Utredare för hantering av interna risker**|Använd den här gruppen för att tilldela behörigheter till användare som ska agera som insider-riskgruppsbehörigheter. Användare i den här rollgruppen kan komma åt alla varningar för insider-riskhantering, ärenden, meddelandemallar och Innehållsutforskaren för alla fall.|Ärendehantering <p> Insider-undersökning av riskhantering <p> View-Only case|
|**IRM-deltagare**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|Permanent bidrag till Insider-riskhantering <p> Temporärt bidrag till Insider-riskhantering|
|**MailFlow-administratör**|Medlemmarna kan övervaka och visa information om e-postflödet och rapporter i Säkerhets- & efterlevnadscenter. Globala administratörer kan lägga till vanliga användare i den här gruppen, men om användaren inte är medlem i Exchange-administratörsgruppen har användaren inte åtkomst till Exchange-administratörsrelaterade uppgifter.|View-Only mottagare|
|**Organisationshantering**<sup>1</sup>|Medlemmar kan kontrollera behörigheter för åtkomst till funktioner i Säkerhets- och efterlevnadscenter för & och även hantera inställningar för enhetshantering, skydd mot dataförlust, rapporter och bevarande. <p> Användare som inte är globala administratörer måste vara Exchange-administratörer för att kunna se och vidta åtgärder på enheter som hanteras av Basic Mobility and Security för Microsoft 365 (tidigare kallat Hantering av mobila enheter eller MDM). <p> Globala administratörer läggs automatiskt till som medlemmar i den här rollgruppen.|Granskningsloggar <p> Ärendehantering <p> Efterlevnadsadministratör <p> Efterlevnadssökning <p> Enhetshantering <p> DLP-efterlevnadshantering <p> Håll ned <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> Karantän <p> RecordManagement <p> Bevarandehantering <p> Rollhantering <p> Sök och rensa <p> Säkerhetsadministratör <p> Säkerhetsläsare <p> Administratör för känslighetsetikett <p> Känslighetsetikettläsare <p> Vyn Tjänstgranskning <p> Tagga deltagare <p> Kodhanteraren <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only case <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Karantänadministratör**|Medlemmar kan komma åt alla åtgärder i karantän. Mer information finns i [Hantera meddelanden i karantän och filer som administratör i EOP](manage-quarantined-messages-and-files.md)|Karantän|
|**Hantering av arkivhandlingar**|Medlemmar kan konfigurera alla aspekter av hantering av arkivhandlingar, inklusive bevarandeetiketter och dispositionsgranskningar.|Dispositionshantering <p> RecordManagement <p> Bevarandehantering|
|**Granskare**|Medlemmar kan komma åt granskningsuppsättningar i [Advanced eDiscovery-ärenden.](../../compliance/overview-ediscovery-20.md) Medlemmar i den här rollgruppen kan visa och öppna listan över ärenden på sidan **eDiscovery > Advanced** i Microsoft 365 efterlevnadscenter som de är medlemmar i. När användaren har åtkomst till ett Avancerat eDiscovery-ärende kan de välja Granska-uppsättningar **för** åtkomst till ärendedata. Med den här rollen kan användaren inte förhandsgranska resultatet av en sökning i en samling som är kopplad till ärendet eller utföra andra åtgärder för sökning eller ärendehantering. Medlemmar i den här rollgruppen kan bara komma åt data i en granskningsuppsättning.|Granska|
|**Säkerhetsadministratör**|Medlemmar har åtkomst till ett antal säkerhetsfunktioner i Identity Protection Center, Privileged Identity Management, Övervaka Microsoft 365-tjänstens hälsa och säkerhets- och & efterlevnadscenter. <p> Som standard verkar den här rollgruppen inte ha några medlemmar. Rollen Säkerhetsadministratör från Azure Active Directory tilldelas dock den här rollgruppen. Den här rollgruppen ärver därför funktionerna och medlemskapet för rollen Säkerhetsadministratör från Azure Active Directory. <p> Om du vill hantera behörigheter centralt lägger du till och tar bort gruppmedlemmar i administrationscentret för Azure Active Directory. Mer information finns i Behörigheter [för administratörsroller i Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Om du redigerar den här rollgruppen i Säkerhets- & efterlevnadscenter (medlemskap eller roller) gäller de ändringarna endast för Säkerhets- & efterlevnadscenter och inte för några andra tjänster. <p> Den här rollgruppen innehåller alla skrivskyddade behörigheter för rollen Säkerhetsläsare, plus ett antal ytterligare administrativa behörigheter för samma tjänster: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Övervaka Microsoft 365-tjänstens hälsa och säkerhets- och & efterlevnadscenter.|Granskningsloggar <p> Enhetshantering <p> DLP-efterlevnadshantering <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Karantän <p> Säkerhetsadministratör <p> Administratör för känslighetsetikett <p> Tagga deltagare <p> Kodhanteraren <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Säkerhetsoperatör**|Medlemmar kan hantera säkerhetsvarningar och även visa rapporter och inställningar för säkerhetsfunktioner.|Efterlevnadssökning <p> Hantera aviseringar <p> Säkerhetsläsare <p> Tagga deltagare <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Säkerhetsläsare**|Medlemmar har skrivskyddad åtkomst till ett antal säkerhetsfunktioner i Identity Protection Center, Privileged Identity Management, Övervaka Microsoft 365-tjänstens hälsa och säkerhets- & efterlevnadscenter. <p> Som standard verkar den här rollgruppen inte ha några medlemmar. Men rollen Säkerhetsläsare från Azure Active Directory tilldelas till den här rollgruppen. Den här rollgruppen ärver därför funktionerna och medlemskapet för rollen Säkerhetsläsare från Azure Active Directory. <p> Om du vill hantera behörigheter centralt lägger du till och tar bort gruppmedlemmar i administrationscentret för Azure Active Directory. Mer information finns i Behörigheter [för administratörsroller i Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Om du redigerar den här rollgruppen i Säkerhets- & efterlevnadscenter (medlemskap eller roller) gäller de ändringarna endast för Säkerhets- & efterlevnadscenter och inte för några andra tjänster.|Säkerhetsläsare <p> Känslighetsetikettläsare <p> Taggläsare <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Tjänstgranskningsanvändare**|Medlemmarna kan komma åt avsnittet Tjänstgranskning i Säkerhets- & Efterlevnadscenter. Tjänstgranskning tillhandahåller rapporter och dokument som beskriver Microsofts säkerhetsrutiner för kunddata som lagras i Microsoft 365. Den tillhandahåller även granskningsrapporter från oberoende tredje part om Microsoft 365. Mer information finns i [Tjänstgranskning i Säkerhets- & Efterlevnadscenter.](../../compliance/service-assurance.md)|Vyn Tjänstgranskning|
|**Övervakande granskning**|Medlemmarna kan skapa och hantera de principer som definierar vilken kommunikation som ska granskas i en organisation. Mer information finns i Konfigurera [principer för kommunikationsefterlevnad för din organisation.](../../compliance/communication-compliance-configure.md)|Övervakande granskningsadministratör|
|

> [!NOTE]
> <sup>1</sup> Den här rollgruppen tilldelar inte medlemmar de behörigheter som krävs för att söka i granskningsloggen eller för att använda rapporter som kan innehålla Exchange-data, till exempel DLP- eller Defender för Office 365-rapporter. En användare måste ha tilldelats behörigheter i Exchange Online för att kunna söka i granskningsloggen eller visa alla rapporter. Det beror på att den underliggande cmdleten som används för att söka i granskningsloggen är en Exchange Online-cmdlet. Globala administratörer kan söka i granskningsloggen och visa alla rapporter eftersom de läggs till automatiskt som medlemmar i rollgruppen Organisationshantering i Exchange Online. Mer information finns i [Söka i granskningsloggen i Säkerhets- & efterlevnadscenter.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Roller i Säkerhets- & Efterlevnadscenter

I följande tabell visas de tillgängliga rollerna och rollgrupperna som de är tilldelade till som standard.

Observera att följande roller inte är tilldelade till rollgruppen Organisationshantering som standard:

- Attack Simulator Admin
- Attack Den här nyttolastförfattaren
- Kommunikation
- Admin för kommunikationsefterlevnad
- Analys av kommunikationsefterlevnad
- Case Management för kommunikationsefterlevnad
- Undersökning av kommunikationsefterlevnad
- Visningsprogram för kommunikationsefterlevnad
- Efterlevnadshanteraren – administration
- Utvärdering av Efterlevnadshanteraren
- Bidrag till Efterlevnadshanteraren
- Efterlevnadshanteraren Läsare
- Insikare
- Visningsprogram för dataklassificeringsinnehåll
- Dataklassificeringsfeedbackleverantör
- Granskare för dataklassificeringsfeedback
- Visningsprogram för dataklassificeringslista
- Dispositionshantering
- Exportera
- Insider-riskhanteringsadministratör
- Insider-riskhanteringsanalys
- Granskning av Insider-riskhantering
- Insider-undersökning av riskhantering
- Permanent bidrag till Insider-riskhantering
- Temporärt bidrag till Insider-riskhantering
- Förhandsgranska
- Granska
- RMS-dekryptera
- Övervakande granskningsadministratör

<br><br>

****

|Roll|Beskrivning|Tilldelningar av standardrollgrupper|
|---|---|---|
|**Attack Simulator Admin**|Används för att skapa och hantera alla aspekter av attack simuleringskampanjer.||
|**Attack Den här nyttolastförfattaren**|Används för att skapa och hantera nyttolaster för attack som kan distribueras av attackadministratören.||
|**Granskningsloggar**|Aktivera och konfigurera granskning för organisationen, visa organisationens granskningsrapporter och exportera rapporterna till en fil.|Organisationshantering <p> Säkerhetsadministratör|
|**Ärendehantering**|Skapa, redigera, ta bort och kontrollera åtkomsten till eDiscovery-ärenden.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnadar <p> Efterlevnadsadministratör <p>eDiscovery Manager <p> Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer <p> Analytiker för hantering av interna risker <p> Utredare för hantering av interna risker <p> Organisationshantering|
|**Kommunikation**|Hantera all kommunikation med de skvarna som identifieras i ett Avancerat eDiscovery-ärende.  Skapa meddelanden som håller i samtal, håller i påminnelser och eskalerar till hantering. Spåra bekräftelse av aviseringar av samtal och hantera åtkomst till den måstee portal som används av varje vårdnadshavare i ett ärende för att spåra meddelanden för de fall där de identifierats som vårdnadshavare.|eDiscovery Manager|
|**Admin för kommunikationsefterlevnad**|Används för att hantera principer i funktionen kommunikationsefterlevnad.|Efterlevnad av kommunikation <p> Administratörer för kommunikationsefterlevnad|
|**Analys av kommunikationsefterlevnad**|Används för att undersöka och åtgärda meddelandefel i funktionen för kommunikationsefterlevnad. Det går bara att visa metadata för meddelanden.|Efterlevnad av kommunikation <p> Analytiker för kommunikationsefterlevnad <p> Kommunikationsefterlevnadsefterlevnadar|
|**Case Management för kommunikationsefterlevnad**|Används för åtkomst till fall där kommunikationsefterlevnad används.|Efterlevnad av kommunikation <p> Administratörer för kommunikationsefterlevnad <p> Analytiker för kommunikationsefterlevnad <p> Kommunikationsefterlevnadsefterlevnadar <p> Läsare av kommunikationsefterlevnad|
|**Undersökning av kommunikationsefterlevnad**|Används för att utföra undersökning, åtgärder och granska meddelandebrott i funktionen för kommunikationsefterlevnad. Kan visa meddelandemetadata och meddelande.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnadar|
|**Visningsprogram för kommunikationsefterlevnad**|Används för att komma åt rapporter och widgetar i funktionen för kommunikationsefterlevnad.|Efterlevnad av kommunikation <p> Läsare av kommunikationsefterlevnad|
|**Efterlevnadsadministratör**|Visa och redigera inställningar och rapporter för efterlevnadsfunktioner.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering|
|**Efterlevnadshanteraren – administration**|Hantera skapande och ändring av mallar.|Efterlevnadshanterarens administratörer|
|**Utvärdering av Efterlevnadshanteraren**|Skapa utvärderingar, implementera förbättringsåtgärder och uppdatera teststatus för förbättringsåtgärder.|Efterlevnadshanterarens administratörer <p> Utvärderare i Efterlevnadshanteraren|
|**Bidrag till Efterlevnadshanteraren**|Skapa utvärderingar och utför arbete för att implementera förbättringsåtgärder.|Efterlevnadshanterarens administratörer <p> Utvärderare i Efterlevnadshanteraren <p> Deltagare i Efterlevnadshanteraren|
|**Efterlevnadshanteraren Läsare**|Visa allt innehåll i Efterlevnadshanteraren utom administratörsfunktioner.|Efterlevnadshanterarens administratörer <p> Utvärderare i Efterlevnadshanteraren <p> Deltagare i Efterlevnadshanteraren <p> Läsare av Efterlevnadshanteraren|
|**Efterlevnadssökning**|Utför sökningar i postlådor och få en uppskattning av resultaten.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p>eDiscovery Manager <p> Organisationshantering <p> Säkerhetsoperatör|
|**Insikare**|Identifiera och hantera avancerad eDiscovery-ärenden och använd informationen från Azure Active Directory och andra källor för att hitta datakällor som är associerade med godtyckliga personer. Associera andra datakällor, till exempel postlådor, SharePoint-webbplatser och Teams, med biblioteksassistenter i ett ärende.  Skapa ett juridiskt bevarande för de datakällor som är associerade med de associerade biblioteken för att bevara innehåll i ett ärende.|eDiscovery Manager|
|**Visningsprogram för dataklassificeringsinnehåll**|Visa på plats-rendering av filer i Innehållsutforskaren.|Innehållsvisningsprogram för Innehållsutforskaren|
|**Dataklassificeringsfeedbackleverantör**|Gör att du kan ge feedback till klassificerare i Innehållsutforskaren.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnadar <p> Efterlevnadsadministratör|
|**Granskare för dataklassificeringsfeedback**|Tillåter granskning av feedback från klassificerare i Feedbackutforskaren.|Efterlevnadsadministratör|
|**Visningsprogram för dataklassificeringslista**|Visa listan över filer i Innehållsutforskaren.|Visningsprogram för listor i Innehållsutforskaren|
|**Enhetshantering**|Visa och redigera inställningar och rapporter för funktioner för enhetshantering.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Säkerhetsadministratör|
|**Dispositionshantering**|Kontrollera behörigheter för åtkomst till manuell disposition i Säkerhets- & Efterlevnadscenter.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Hantering av arkivhandlingar|
|**DLP-efterlevnadshantering**|Visa och redigera inställningar och rapporter för DLP-principer (Data Loss Prevention).|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Säkerhetsadministratör|
|**Exportera**|Exportera postlåde- och webbplatsinnehåll som returneras från sökningar.|eDiscovery Manager|
|**Håll ned**|Placera innehåll i postlådor, webbplatser och gemensamma mappar i en lokal mapp. Vid förvaring lagras en kopia av innehållet på en säker plats. Innehållsägare kan fortfarande ändra eller ta bort det ursprungliga innehållet.|Efterlevnadsadministratör <p>eDiscovery Manager <p> Organisationshantering|
|**IB-efterlevnadshantering**|Visa, skapa, ta bort, ändra och testa informationsbarriärpolicyer.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Säkerhetsadministratör|
|**Insider-riskhanteringsadministratör**|Skapa, redigera, ta bort och kontrollera åtkomsten till Insider-riskhanteringsfunktionen.|Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer|
|**Insider-riskhanteringsanalys**|Få tillgång till alla varningar och mallar för insider-riskhantering, ärenden och meddelanden.|Hantering av insiderrisk <p> Analytiker för hantering av interna risker|
|**Granskning av Insider-riskhantering**|Tillåt visning av Insider Risk-granskningshistorik.|Insider-riskhanteringsgranskningar|
|**Insider-undersökning av riskhantering**|Kom åt alla varningar för Insider-riskhantering, ärenden, meddelandemallar och Innehållsutforskaren för alla fall.|Hantering av insiderrisk <p> Utredare för hantering av interna risker|
|**Permanent bidrag till Insider-riskhantering**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|IRM-deltagare|
|**Temporärt bidrag till Insider-riskhantering**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|IRM-deltagare|
|**Hantera aviseringar**|Visa och redigera inställningar och rapporter för aviseringar.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Organisationskonfiguration**|Köra, visa och exportera granskningsrapporter och hantera efterlevnadsprinciper för DLP, enheter och bevarande.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering|
|**Förhandsgranska**|Visa en lista över objekt som returneras från innehållssökningar och öppna varje objekt i listan för att visa dess innehåll.|eDiscovery Manager|
|**Karantän**|Tillåter visning och frisläppning av e-post i karantän.|Karantänadministratör <p> Säkerhetsadministratör <p> Organisationshantering|
|**RecordManagement**|Visa och redigera konfigurationen av funktionen för hantering av arkivhandlingar.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Hantering av arkivhandlingar|
|**Bevarandehantering**|Hantera bevarandeprinciper, bevarandeetiketter och bevarandeprinciper.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Organisationshantering <p> Hantering av arkivhandlingar|
|**Granska**|Med den här rollen kan användare få åtkomst till granskningsuppsättningar i avancerade eDiscovery-fall. Användare som har tilldelats den här rollen kan se och öppna listan över ärenden på sidan **eDiscovery > Advanced** i Kompatibilitetscenter för Microsoft 365 som de är medlemmar i. När användaren har åtkomst till ett Avancerat eDiscovery-ärende kan de välja Granska-uppsättningar **för** åtkomst till ärendedata. Med den här rollen kan användaren inte förhandsgranska resultatet av en sökning i en samling som är kopplad till ärendet eller utföra andra åtgärder för sökning eller ärendehantering. Användare med den här rollen kan bara komma åt data i en granskningsuppsättning.|eDiscovery Manager <p> Granskare|
|**RMS-dekryptera**|Dekryptera RMS-skyddat innehåll när du exporterar sökresultat.|eDiscovery Manager|
|**Rollhantering**|Hantera medlemskap i rollgrupper och skapa eller ta bort anpassade rollgrupper.|Organisationshantering|
|**Sök och rensa**|Gör att personer kan massbortta data som matchar villkoren för en innehållssökning.|Organisationshantering|
|**Säkerhetsadministratör**|Visa och redigera konfiguration och rapporter för säkerhetsfunktioner.|Organisationshantering <p> Säkerhetsadministratör|
|**Säkerhetsläsare**|Visa konfiguration och rapporter för säkerhetsfunktioner.|Global läsare <p> Organisationshantering <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Administratör för känslighetsetikett**|Visa, skapa, ändra och ta bort känslighetsetiketter.|Dataadministratör för efterlevnad <p> Organisationshantering <p> Säkerhetsadministratör|
|**Känslighetsetikettläsare**|Visa konfiguration och användning av känslighetsetiketter.|Global läsare <p> Organisationshantering <p> Säkerhetsläsare|
|**Vyn Tjänstgranskning**|Ladda ned tillgängliga dokument från avsnittet Tjänstgranskning. Innehållet omfattar oberoende granskning, efterlevnadsdokumentation och förtroenderelaterade riktlinjer för hur du använder Microsoft 365-funktioner för att hantera efterlevnads- och säkerhetsrisker.|Global läsare <p> Organisationshantering <p> Tjänstgranskningsanvändare|
|**Övervakande granskningsadministratör**|Hantera principer för övervakande granskning, inklusive vilka meddelanden som ska granskas och vem som ska göra granskningen.|Övervakande granskning|
|**Tagga deltagare**|Visa och uppdatera medlemskap för befintliga användartaggar.|Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Kodhanteraren**|Visa, uppdatera, skapa och ta bort användartaggar.|Organisationshantering <p> Säkerhetsadministratör|
|**Taggläsare**|Skrivskyddade åtkomst till befintliga användartaggar.|Säkerhetsläsare|
|**Visningsbaserade granskningsloggar**|Visa och exportera granskningsrapporter. Eftersom dessa rapporter kan innehålla känslig information bör du endast tilldela den här rollen till personer med ett uttryckligt behov av att visa den här informationen.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Visningsläge**||Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnadar <p> Efterlevnadsadministratör <p> Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer <p> Analytiker för hantering av interna risker <p> Insider RiskManagement-projektledare <p> Organisationshantering|
|**Enhetshantering, endast visa**|Visa konfiguration och rapporter för funktionen Enhetshantering.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Endast visaDLP-efterlevnadshantering**|Visa inställningar och rapporter för principer för dataförlustskydd (DLP).|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**IB-efterlevnadshantering, endast visa**|Visa konfiguration och rapporter för funktionen Informationsbarriärer.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Hantera aviseringar endast i visningsläge**|Visa konfiguration och rapporter för funktionen Hantera aviseringar.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Endast visa-mottagare**|Visa information om användare och grupper.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global läsare <p> MailFlow-administratör <p> Organisationshantering|
|**Hantering av endast visa-poster**|Visa konfigurationen av funktionen för hantering av arkivhandlingar.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> <p> Global läsare <p> Organisationshantering|
|**Hantering av endast visa-bevarande**|Visa konfigurationen av bevarandeprinciper, bevarandeetiketter och bevarandeprinciper.|Efterlevnadsadministratör <p> Dataadministratör för efterlevnad <p> Global administratör <p> Organisationshantering|
|