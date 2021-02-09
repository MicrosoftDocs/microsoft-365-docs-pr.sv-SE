---
title: Behörigheter – Säkerhets- & Efterlevnadscenter
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
description: Administratörer kan läsa mer om behörigheterna som är tillgängliga i Säkerhets- & Efterlevnadscenter i Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 316f5ea742684a18c6ab531843cc4fef85d74896
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150225"
---
# <a name="permissions-in-the-security--compliance-center"></a>Behörigheter i Säkerhets- och efterlevnadscentret

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Med Säkerhets- & Efterlevnadscenter kan du bevilja behörigheter till personer som utför efterlevnadsuppgifter, till exempel enhetshantering, skydd mot dataförlust, eDiscovery, bevarande och så vidare. De här personerna kan endast utföra de uppgifter som du uttryckligen ger dem åtkomst till. För att få åtkomst & Säkerhets- och efterlevnadscenter måste användarna vara globala administratörer eller medlemmar i en eller flera rollgrupper & Säkerhets- och efterlevnadscenter.

Behörigheter i Säkerhets- & Efterlevnadscenter baseras på den rollbaserade behörighetsmodellen (RBAC). RBAC är samma behörighetsmodell som används i Exchange, så om du är bekant med Exchange kommer det att kännas ungefär som att bevilja behörigheter i Säkerhets- & Efterlevnadscenter. Det är dock viktigt att komma ihåg att rollgrupperna i Exchange och säkerhetscentret i & inte delar medlemskap eller behörigheter. Även om båda har rollgruppen Organisationshantering är de inte desamma. Behörigheterna som de tillerer och medlemmar i rollgrupperna skiljer sig åt. Det finns en lista över rollgrupper & Säkerhets- och efterlevnadscenter nedan.

![Sidan Behörigheter i Säkerhets- & Efterlevnadscenter](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och rollgrupper

En **roll** beviljar behörighet att utföra en uppsättning uppgifter. Med rollen Ärendehantering kan personer till exempel arbeta med eDiscovery-ärenden.

En **rollgrupp** är en uppsättning roller som gör att personer kan göra sitt arbete i Säkerhets- & Efterlevnadscenter. Till exempel innehåller rollgruppen efterlevnadsadministratör (bland andra roller) roller för ärendehantering, innehållssökning och organisationskonfiguration (plus andra) eftersom någon som är efterlevnadsadministratör behöver behörighet för att uppgifterna ska utföra sina arbetsuppgifter.

Säkerhets- & efterlevnadscenter innehåller standardrollgrupper för de vanligaste uppgifterna och funktionerna som du behöver tilldela personer till. Vi rekommenderar att du bara lägger till enskilda **användare som** medlemmar i standardrollgrupperna.

![Diagram som visar relationen mellan rollgrupper och roller och medlemmar](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Behörigheter som krävs för att använda funktioner i Säkerhets- & Efterlevnadscenter

I följande tabell visas de standardrollgrupper som är tillgängliga i Säkerhets- & Efterlevnadscenter och de roller som är tilldelade till rollgrupperna som standard. Om du vill ge en användare behörighet att utföra en efterlevnadsuppgift lägger du till dem i rollgruppen & Säkerhets- och efterlevnadscenter.

Genom att hantera behörigheter & Säkerhets- och efterlevnadscenter får användarna endast åtkomst till de efterlevnadsfunktioner som finns tillgängliga i & Säkerhets- och efterlevnadscenter. Om du vill ge behörigheter till andra efterlevnadsfunktioner som inte finns i Säkerhets- & och efterlevnadscenter, till exempel Exchange-e-postflödesregler (kallas även transportregler), måste du använda administrationscentret för Exchange.

Information om hur du beviljar åtkomst till Säkerhets- & Efterlevnadscenter finns i Ge användare åtkomst till administrationscentret för [Microsoft 365-efterlevnad.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Du måste **vara** administratör för att visa fliken Behörigheter & Säkerhets- och efterlevnadscenter. Specifikt måste du tilldelas  rollen Rollhantering & och den  rollen tilldelas endast rollgruppen Organisationshantering i Säkerhets- och efterlevnadscenter som standard. Med **rollhanteringsrollen** kan användarna dessutom visa, skapa och ändra rollgrupper.

<br><br>

****

|Rollgrupp|Beskrivning|Tilldelade standardroller|
|---|---|---|
|**Kommunikationsefterlevnad**|Ger behörighet till alla roller för kommunikationsefterlevnad: administratör, analytiker, projektledare och tittare.|Ärendehantering <p> Admin för kommunikationsefterlevnad <p> Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad <p> Undersökning av kommunikationsefterlevnad <p> Visningsprogram för kommunikationsefterlevnad <p> Dataklassificeringsfeedbackleverantör <p> View-Only ärende|
|**Administratörer för kommunikationsefterlevnad**|Administratörer för kommunikationsefterlevnad som kan skapa/redigera principer och definiera globala inställningar.|Admin för kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad|
|**Kommunikationsefterlevnadsanalytiker**|Analytiker av kommunikationsefterlevnad som kan undersöka principmatchningar, visa metadata för meddelanden och vidta åtgärder.|Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad|
|**Kommunikationsefterlevnadsefterlevnad**|Analytiker av kommunikationsefterlevnad som kan undersöka principmatchningar, visa meddelandeinnehåll och vidta åtgärder.|Ärendehantering <p> Analys av kommunikationsefterlevnad <p> Case Management för kommunikationsefterlevnad <p> Undersökning av kommunikationsefterlevnad <p> Dataklassificeringsfeedbackleverantör <p> View-Only ärende|
|**Läsare av kommunikationsefterlevnad**|Visare för kommunikationsefterlevnad som kan komma åt tillgängliga rapporter och widgetar.|Case Management för kommunikationsefterlevnad <p> Visningsprogram för kommunikationsefterlevnad|
|**Efterlevnadsadministratör**<sup>1</sup>|Medlemmarna kan hantera inställningar för enhetshantering, skydd mot dataförlust, rapporter och förvaring.|Ärendehantering <p> Efterlevnadsadministratör <p> Efterlevnadssökning <p> Dataklassificeringsfeedbackleverantör <p> Granskare av dataklassificeringsfeedback <p> Enhetshantering <p> Dispositionshantering <p> DLP-efterlevnadshantering <p> Håll ned <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> RecordManagement <p> Bevarandehantering <p> View-Only granskningsloggar <p> View-Only ärende <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Efterlevnadsdataadministratör**|Medlemmarna kan hantera inställningar för enhetshantering, dataskydd, skydd mot dataförlust, rapporter och förvaring.|Efterlevnadsadministratör <p> Efterlevnadssökning <p> Enhetshantering <p> DLP-efterlevnadshantering <p> Dispositionshantering <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> RecordManagement <p> Bevarandehantering <p> Känslighetsetikettsadministratör <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Efterlevnadshanteraren-administratörer**|Hantera skapande och ändring av mallar.|Administration av Efterlevnadshanteraren <p> Utvärdering av Efterlevnadshanteraren <p> Efterlevnadshanterarens bidrag <p> Efterlevnadshanteraren Läsare|
|**Utvärderare för Efterlevnadshanteraren**|Skapa utvärderingar, implementera förbättringsåtgärder och uppdatera teststatus för förbättringsåtgärder.|Utvärdering av Efterlevnadshanteraren <p> Efterlevnadshanterarens bidrag <p> Efterlevnadshanteraren Läsare|
|**Deltagare i Efterlevnadshanteraren**|Skapa utvärderingar och utför arbete för att implementera förbättringsåtgärder.|Efterlevnadshanterarens bidrag <p> Efterlevnadshanteraren Läsare|
|**Läsare av Efterlevnadshanteraren**|Visa allt innehåll i Efterlevnadshanteraren utom administratörsfunktioner.|Efterlevnadshanteraren Läsare|
|**Innehållsvisningsprogram för Innehållsutforskaren**|Visa innehållsfilerna i Innehållsutforskaren.|Visningsprogram för dataklassificeringsinnehåll|
|**Visningsprogram för listor i Innehållsutforskaren**|Visa alla objekt i Innehållsutforskaren endast i listformat.|Visningsprogram för dataklassificeringslista|
|**eDiscovery Manager**|Medlemmar kan utföra sökningar och spärrade filer på postlådor, SharePoint Online-webbplatser och OneDrive för företag-platser. Medlemmar kan också skapa och hantera eDiscovery-ärenden, lägga till och ta bort medlemmar i ett ärende, skapa och redigera innehållssökningar kopplade till ett ärende samt få åtkomst till ärendedata i Avancerad eDiscovery. <p> En eDiscovery-administratör är medlem i rollgruppen för eDiscovery Manager som har tilldelats ytterligare behörigheter. Utöver de uppgifter som en eDiscovery-hanterare kan utföra kan en eDiscovery-administratör:<ul><li>Visa alla eDiscovery-ärenden i organisationen.</li><li>Hantera e-dataidentifieringsfall när de har lagt till sig själva som medlem i ärendet.</li></ul> <p> Den primära skillnaden mellan en eDiscovery-hanterare och en eDiscovery-administratör är att en eDiscovery-administratör kan komma åt alla ärenden som visas på sidan **eDiscovery-ärenden** i Säkerhets- & efterlevnadscenter. En eDiscovery-hanterare kan bara komma åt de ärenden som de skapat eller ärenden som de är medlemmar i. Mer information om hur du gör en användare till eDiscovery-administratör finns i Tilldela eDiscovery-behörigheter i Säkerhets- [& Efterlevnadscenter.](../../compliance/assign-ediscovery-permissions.md)|Ärendehantering <p> Kommunikation <p> Efterlevnadssökning <p> Det här är en bra dag, men <p> Exportera <p> Håll ned <p> Förhandsgranska <p> Granska <p> RMS-dekryptering|
|**Global läsare**|Medlemmar har skrivskyddade åtkomst till rapporter, aviseringar och kan se alla konfigurationer och inställningar.<p> Den största skillnaden mellan Global Reader och Säkerhetsläsare är att en global läsare kan komma åt **konfiguration och inställningar.**|Säkerhetsläsare <p> Känslighetsetikettläsare <p> Vyn Tjänstgranskning <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Insider-riskhantering**|Använd den här rollgruppen för att hantera insider-riskhantering för din organisation i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker och berättelser kan du konfigurera insider-riskhanteringsbehörigheter i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för Insider-riskhantering. Det här är det enklaste sättet att snabbt komma igång med insider-riskhantering. Det är en god passform för organisationer som inte behöver separata behörigheter som definierats för olika grupper av användare.|Ärendehantering <p> Insider-riskhanteringsadministratör <p> Insider-riskhanteringsanalys <p> Insider-riskhanteringsundersökning <p> View-Only ärende|
|**Insider-riskhanteringsadministratörer**|Använd den här rollgruppen för att först konfigurera insiderriskhantering och senare för att dela upp insiderriskadministratörer i en definierad grupp. Användare i den här rollgruppen kan skapa, läsa, uppdatera och ta bort insider-riskhanteringsprinciper, globala inställningar och rollgruppstilldelningar.|Ärendehantering <p> Insider-riskhanteringsadministratör <p> View-Only ärende|
|**Analytiker för hantering av interna risker**|Använd den här gruppen för att tilldela behörigheter till användare som fungerar som insider-riskfallsanalytiker. Användare i den här rollgruppen kan komma åt alla varningar, ärenden och meddelandemallar för Insider-riskhantering. De kan inte komma åt Insider-risken i Innehållsutforskaren.|Ärendehantering <p> Insider-riskhanteringsanalys <p> View-Only ärende|
|**Insider-riskhanteringsgranskningar**|Granskare av Insider-riskhantering som kan visa granskningsloggar för åtgärder som utförts av analytiker, administratörer och administratörer.|Granskning av Insider-riskhantering|
|**Utredare för hantering av interna risker**|Använd den här gruppen för att tilldela behörigheter till användare som ska agera som insiderriskdatasknare. Användare i den här rollgruppen kan komma åt alla varningar för Insider-riskhantering, fall, meddelandemallar och Innehållsutforskaren för alla fall.|Ärendehantering <p> Insider-riskhanteringsundersökning <p> View-Only ärende|
|**IRM-deltagare**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|Permanent bidrag till Insider-riskhantering <p> Tillfälligt bidrag till Insider-riskhantering|
|**MailFlow-administratör**|Medlemmar kan övervaka och visa information om e-postflöde och rapporter i Säkerhets- & Efterlevnadscenter. Globala administratörer kan lägga till vanliga användare i den här gruppen, men om användaren inte är medlem i administratörsgruppen i Exchange har användaren inte tillgång till exchange-administratörsrelaterade uppgifter.|View-Only mottagare|
|**Organisationshantering**<sup>1</sup>|Medlemmar kan styra behörigheter för åtkomst till funktioner i Säkerhets- och & Efterlevnadscenter och även hantera inställningar för enhetshantering, skydd mot dataförlust, rapporter och förvaring. <p> Användare som inte är globala administratörer måste vara Exchange-administratörer för att kunna se och vidta åtgärder på enheter som hanteras av Basic Mobility and Security för Microsoft 365 (kallades tidigare Hantering av mobila enheter eller MDM). <p> Globala administratörer läggs automatiskt till som medlemmar i den här rollgruppen.|Granskningsloggar <p> Ärendehantering <p> Efterlevnadsadministratör <p> Efterlevnadssökning <p> Enhetshantering <p> DLP-efterlevnadshantering <p> Håll ned <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Organisationskonfiguration <p> Karantän <p> RecordManagement <p> Bevarandehantering <p> Rollhantering <p> Sök och rensa <p> Säkerhetsadministratör <p> Säkerhetsläsare <p> Känslighetsetikettsadministratör <p> Känslighetsetikettläsare <p> Vyn Tjänstgranskning <p> Tagga deltagare <p> Tagghanteraren <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only ärende <p> View-Only Hantera aviseringar <p> View-Only mottagare <p> View-Only posthantering <p> View-Only med bevarandehantering|
|**Karantänadministratör**|Medlemmarna kan komma åt alla åtgärder i karantän. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)|Karantän|
|**Hantering av arkivhandlingar**|Medlemmar kan konfigurera alla aspekter av hantering av arkivhandlingar, inklusive bevarandeetiketter och dispositionsgranskningar.|Dispositionshantering <p> RecordManagement <p> Bevarandehantering|
|**Granskare**|Medlemmar kan komma åt uppsättningar av granskning [i Advanced eDiscovery-ärenden.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) Medlemmar i den här rollgruppen kan se och öppna listan över ärenden på sidan **eDiscovery > Advanced** i Efterlevnadscenter för Microsoft 365 som de är medlemmar i. När användaren har åtkomst till ett Avancerat eDiscovery-ärende kan de välja Granskningsuppsättningar **för åtkomst** till ärendedata. Den här rollen tillåter inte att användaren förhandsgranskar resultatet av en samlingssökning som är kopplad till ärendet eller utför andra åtgärder för sökning eller ärendehantering. Medlemmar i den här rollgruppen kan bara komma åt data i en granskningsuppsättning.|Granska|
|**Säkerhetsadministratör**|Medlemmar har tillgång till ett antal säkerhetsfunktioner i Identity Protection Center, Privileged Identity Management, Övervaka Microsoft 365-tjänstens hälsa och säkerhets- & Efterlevnadscenter. <p> Som standard verkar den här rollgruppen inte ha några medlemmar. Rollen Säkerhetsadministratör från Azure Active Directory tilldelas dock till den här rollgruppen. Den här rollgruppen ärver därför funktionerna och medlemskapet för rollen Säkerhetsadministratör från Azure Active Directory. <p> Om du vill hantera behörigheter centralt lägger du till och tar bort gruppmedlemmar i administrationscentret för Azure Active Directory. Mer information finns i [administratörsrollbehörigheter i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Om du redigerar den här rollgruppen i Säkerhets- & Efterlevnadscenter (medlemskap eller roller) gäller ändringarna endast för Säkerhets- & Efterlevnadscenter och inte för andra tjänster. <p> Den här rollgruppen innehåller alla skrivskyddade behörigheter för rollen Säkerhetsläsare, samt ett antal ytterligare administrativa behörigheter för samma tjänster: Azure Information Protection, Identity Protection Center, Privileged Identity Management, Övervaka Tjänstens hälsa för Microsoft 365 och Säkerhets- & Efterlevnadscenter.|Granskningsloggar <p> Enhetshantering <p> DLP-efterlevnadshantering <p> IB-efterlevnadshantering <p> Hantera aviseringar <p> Karantän <p> Säkerhetsadministratör <p> Känslighetsetikettsadministratör <p> Tagga deltagare <p> Tagghanteraren <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Säkerhetsoperatör**|Medlemmar kan hantera säkerhetsvarningar och även visa rapporter och inställningar för säkerhetsfunktioner.|Efterlevnadssökning <p> Hantera aviseringar <p> Säkerhetsläsare <p> Tagga deltagare <p> Taggläsare <p> View-Only granskningsloggar <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Säkerhetsläsare**|Medlemmar har skrivskyddad åtkomst till ett antal säkerhetsfunktioner i Identity Protection Center, Privileged Identity Management, Övervaka Microsoft 365-tjänstens hälsa och säkerhets- & Efterlevnadscenter. <p> Som standard verkar den här rollgruppen inte ha några medlemmar. Men rollen Säkerhetsläsare från Azure Active Directory tilldelas till den här rollgruppen. Den här rollgruppen ärver därför funktionerna och medlemskapet för rollen Säkerhetsläsare från Azure Active Directory. <p> Om du vill hantera behörigheter centralt lägger du till och tar bort gruppmedlemmar i administrationscentret för Azure Active Directory. Mer information finns i [administratörsrollbehörigheter i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Om du redigerar den här rollgruppen i Säkerhets- & Efterlevnadscenter (medlemskap eller roller) gäller ändringarna endast för Säkerhets- & Efterlevnadscenter och inte för andra tjänster.|Säkerhetsläsare <p> Känslighetsetikettläsare <p> Taggläsare <p> View-Only enhetshantering <p> View-Only DLP-efterlevnadshantering <p> View-Only IB-efterlevnadshantering <p> View-Only Hantera aviseringar|
|**Tjänstgranskningsanvändare**|Medlemmar kan komma åt avsnittet Tjänstgranskning i Säkerhets- & Efterlevnadscenter. Tjänstgranskning tillhandahåller rapporter och dokument som beskriver Microsofts säkerhetsrutiner för kunddata som lagras i Microsoft 365. Den tillhandahåller även oberoende granskningsrapporter från tredje part om Microsoft 365. Mer information finns i [Tjänstgranskning i Säkerhets- & Efterlevnadscenter.](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)|Vyn Tjänstgranskning|
|**Övervakande granskning**|Medlemmarna kan skapa och hantera principerna som definierar vilken kommunikation som ska granskas i en organisation. Mer information finns i Konfigurera [principer för kommunikationsefterlevnad för din organisation.](../../compliance/communication-compliance-configure.md)|Övervakande granskningsadministratör|
|

> [!NOTE]
> <sup>1</sup> Den här rollgruppen tilldelar inte medlemmar de behörigheter som krävs för att söka i granskningsloggen eller för att använda rapporter som kan innehålla Exchange-data, till exempel DLP- eller Defender för Office 365-rapporter. En användare måste ha tilldelats behörigheter i Exchange Online för att kunna söka i granskningsloggen eller visa alla rapporter. Det beror på att den underliggande cmdleten som används för att söka i granskningsloggen är en Exchange Online-cmdlet. Globala administratörer kan söka i granskningsloggen och visa alla rapporter eftersom de automatiskt läggs till som medlemmar i rollgruppen Organisationshantering i Exchange Online. Mer information finns i Söka [i granskningsloggen i Säkerhets- & Efterlevnadscenter.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

## <a name="roles-in-the-security--compliance-center"></a>Roller i Säkerhets- & Efterlevnadscenter

I följande tabell visas tillgängliga roller och rollgrupper som de är tilldelade till som standard.

Observera att följande roller inte är tilldelade rollgruppen Organisationshantering som standard:

- Attack Simulator Admin
- AttackTat Payload Author
- Kommunikation
- Admin för kommunikationsefterlevnad
- Analys av kommunikationsefterlevnad
- Case Management för kommunikationsefterlevnad
- Undersökning av kommunikationsefterlevnad
- Visningsprogram för kommunikationsefterlevnad
- Administration av Efterlevnadshanteraren
- Utvärdering av Efterlevnadshanteraren
- Efterlevnadshanterarens bidrag
- Efterlevnadshanteraren Läsare
- Det här är en bra dag, men
- Visningsprogram för dataklassificeringsinnehåll
- Dataklassificeringsfeedbackleverantör
- Granskare av dataklassificeringsfeedback
- Visningsprogram för dataklassificeringslista
- Dispositionshantering
- Exportera
- Insider-riskhanteringsadministratör
- Insider-riskhanteringsanalys
- Granskning av Insider-riskhantering
- Insider-riskhanteringsundersökning
- Permanent bidrag till Insider-riskhantering
- Tillfälligt bidrag till Insider-riskhantering
- Förhandsgranska
- Granska
- RMS-dekryptering
- Övervakande granskningsadministratör

<br><br>

****

|Roll|Beskrivning|Tilldelningar av standardrollgrupper|
|---|---|---|
|**Attack Simulator Admin**|Används för att skapa och hantera alla aspekter av attacksimuleringskampanjer.||
|**AttackTat Payload Author**|Används för att skapa och hantera nyttolaster för angrepp som kan distribueras av attackadministratören.||
|**Granskningsloggar**|Aktivera och konfigurera granskning för organisationen, visa organisationens granskningsrapporter och exportera sedan rapporterna till en fil.|Organisationshantering <p> Säkerhetsadministratör|
|**Ärendehantering**|Skapa, redigera, ta bort och kontrollera åtkomsten till eDiscovery-ärenden.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnad <p> Efterlevnadsadministratör <p>eDiscovery Manager <p> Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer <p> Analytiker för hantering av interna risker <p> Utredare för hantering av interna risker <p> Organisationshantering|
|**Kommunikation**|Hantera all kommunikation med de identifierande sökarna i ett Avancerat eDiscovery-ärende.  Skapa aviseringar om att hålla, håll påminnelser och eskalering till hantering. Spåra den bekräftande bekräftelsen av hold-meddelanden och hantera åtkomst till den kommunikationsportal som används av varje vårdnadshavare i ett fall för att spåra meddelanden för de fall där de identifierades som vårdnadshavare.|eDiscovery Manager|
|**Admin för kommunikationsefterlevnad**|Används för att hantera principer i funktionen Kommunikationsefterlevnad.|Efterlevnad av kommunikation <p> Administratörer för kommunikationsefterlevnad|
|**Analys av kommunikationsefterlevnad**|Används för att utföra undersökning, åtgärd av meddelandeöverträdelser i funktionen Kommunikationsefterlevnad. Det går bara att visa metadata för meddelanden.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsanalytiker <p> Kommunikationsefterlevnadsefterlevnad|
|**Case Management för kommunikationsefterlevnad**|Används för åtkomst till fall där kommunikationsefterlevnad används.|Efterlevnad av kommunikation <p> Administratörer för kommunikationsefterlevnad <p> Kommunikationsefterlevnadsanalytiker <p> Kommunikationsefterlevnadsefterlevnad <p> Läsare av kommunikationsefterlevnad|
|**Undersökning av kommunikationsefterlevnad**|Används för att utföra undersökning, åtgärd och granska meddelandebrott i funktionen Kommunikationsefterlevnad. Kan visa metadata och meddelande för meddelanden.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnad|
|**Visningsprogram för kommunikationsefterlevnad**|Används för att komma åt rapporter och widgetar i funktionen Kommunikationsefterlevnad.|Efterlevnad av kommunikation <p> Läsare av kommunikationsefterlevnad|
|**Efterlevnadsadministratör**|Visa och redigera inställningar och rapporter för efterlevnadsfunktioner.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering|
|**Administration av Efterlevnadshanteraren**|Hantera skapande och ändring av mallar.|Efterlevnadshanteraren-administratörer|
|**Utvärdering av Efterlevnadshanteraren**|Skapa utvärderingar, implementera förbättringsåtgärder och uppdatera teststatus för förbättringsåtgärder.|Efterlevnadshanteraren-administratörer <p> Utvärderare för Efterlevnadshanteraren|
|**Efterlevnadshanterarens bidrag**|Skapa utvärderingar och utför arbete för att implementera förbättringsåtgärder.|Efterlevnadshanteraren-administratörer <p> Utvärderare för Efterlevnadshanteraren <p> Deltagare i Efterlevnadshanteraren|
|**Efterlevnadshanteraren Läsare**|Visa allt innehåll i Efterlevnadshanteraren utom administratörsfunktioner.|Efterlevnadshanteraren-administratörer <p> Utvärderare för Efterlevnadshanteraren <p> Deltagare i Efterlevnadshanteraren <p> Läsare av Efterlevnadshanteraren|
|**Efterlevnadssökning**|Utför sökningar i postlådor och få en uppskattning av resultaten.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p>eDiscovery Manager <p> Organisationshantering <p> Säkerhetsoperatör|
|**Det här är en bra dag, men**|Identifiera och hantera källinformation för Advanced eDiscovery-fall och använd informationen från Azure Active Directory och andra källor för att hitta datakällor som är associerade med godtyckliga användare. Associera andra datakällor, till exempel postlådor, SharePoint-webbplatser och Teams, med medarbetare i ett fall.  Skapa ett juridiskt bevarande för de datakällor som är associerade med de som är registrerade för att bevara innehåll i ett ärende.|eDiscovery Manager|
|**Visningsprogram för dataklassificeringsinnehåll**|Visa rendering på plats av filer i Innehållsutforskaren.|Innehållsutforskaren|
|**Dataklassificeringsfeedbackleverantör**|Gör att du kan ge feedback till klassificerare i Innehållsutforskaren.|Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnad <p> Efterlevnadsadministratör|
|**Granskare av dataklassificeringsfeedback**|Tillåter granskning av feedback från klassificerare i Feedback Explorer.|Efterlevnadsadministratör|
|**Visningsprogram för dataklassificeringslista**|Visa listan med filer i Innehållsutforskaren.|Visningsprogram för listor i Innehållsutforskaren|
|**Enhetshantering**|Visa och redigera inställningar och rapporter för funktioner för enhetshantering.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Säkerhetsadministratör|
|**Dispositionshantering**|Styr behörigheter för åtkomst till manuell disposition i Säkerhets- & Efterlevnadscenter.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Hantering av arkivhandlingar|
|**DLP-efterlevnadshantering**|Visa och redigera inställningar och rapporter för principer för skydd mot dataförlust (DLP).|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Säkerhetsadministratör|
|**Exportera**|Exportera postlåde- och webbplatsinnehåll som returneras från sökningar.|eDiscovery Manager|
|**Håll ned**|Placera innehåll i postlådor, webbplatser och offentliga mappar som är på plats. Vid förvaring lagras en kopia av innehållet på en säker plats. Innehållsägare kan fortfarande ändra eller ta bort det ursprungliga innehållet.|Efterlevnadsadministratör <p>eDiscovery Manager <p> Organisationshantering|
|**IB-efterlevnadshantering**|Visa, skapa, ta bort, ändra och testa informationsbarriärsprinciper.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Säkerhetsadministratör|
|**Insider-riskhanteringsadministratör**|Skapa, redigera, ta bort och kontrollera åtkomsten till Insider Risk Management-funktionen.|Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer|
|**Insider-riskhanteringsanalys**|Få tillgång till alla varningar och mallar för insider-riskhantering, ärenden och meddelanden.|Hantering av insiderrisk <p> Analytiker för hantering av interna risker|
|**Granskning av Insider-riskhantering**|Tillåt visning av Insider-riskspår.|Insider-riskhanteringsgranskningar|
|**Insider-riskhanteringsundersökning**|Få tillgång till alla varningar för Insider-riskhantering, ärenden, meddelandemallar och Innehållsutforskaren för alla fall.|Hantering av insiderrisk <p> Utredare för hantering av interna risker|
|**Permanent bidrag till Insider-riskhantering**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|IRM-deltagare|
|**Tillfälligt bidrag till Insider-riskhantering**|Den här rollgruppen är synlig, men används endast av bakgrundstjänster.|IRM-deltagare|
|**Hantera aviseringar**|Visa och redigera inställningar och rapporter för aviseringar.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Organisationskonfiguration**|Kör, visa och exportera granskningsrapporter och hantera efterlevnadsprinciper för DLP, enheter och förvaring.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering|
|**Förhandsgranska**|Visa en lista över objekt som returneras från innehållssökningar och öppna varje objekt i listan för att visa dess innehåll.|eDiscovery Manager|
|**Karantän**|Tillåter visning och frisläppning av e-post i karantän.|Karantänadministratör <p> Säkerhetsadministratör <p> Organisationshantering|
|**RecordManagement**|Visa och redigera konfigurationen av funktionen för hantering av arkivhandlingar.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Hantering av arkivhandlingar|
|**Bevarandehantering**|Hantera bevarandeprinciper, bevarandeetiketter och bevarandeprinciper för etiketter.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Organisationshantering <p> Hantering av arkivhandlingar|
|**Granska**|Med den här rollen kan användare komma åt uppsättningar av granskning i Advanced eDiscovery-fall. Användare som har tilldelats den här rollen kan se och öppna listan över ärenden på sidan Avancerat för **eDiscovery >** i efterlevnadscentret för Microsoft 365 som de är medlemmar i. När användaren har åtkomst till ett Avancerat eDiscovery-ärende kan de välja Granskningsuppsättningar **för åtkomst** till ärendedata. Den här rollen tillåter inte att användaren förhandsgranskar resultatet av en samlingssökning som är kopplad till ärendet eller utför andra åtgärder för sökning eller ärendehantering. Användare med den här rollen kan bara komma åt data i en granskningsuppsättning.|eDiscovery Manager <p> Granskare|
|**RMS-dekryptering**|Dekryptera RMS-skyddat innehåll när du exporterar sökresultat.|eDiscovery Manager|
|**Rollhantering**|Hantera medlemskap i rollgrupper och skapa eller ta bort anpassade rollgrupper.|Organisationshantering|
|**Sök och rensa**|Gör att personer kan massbortta data som matchar villkoren för en innehållssökning.|Organisationshantering|
|**Säkerhetsadministratör**|Visa och redigera konfiguration och rapporter för säkerhetsfunktioner.|Organisationshantering <p> Säkerhetsadministratör|
|**Säkerhetsläsare**|Visa konfiguration och rapporter för säkerhetsfunktioner.|Global läsare <p> Organisationshantering <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Känslighetsetikettsadministratör**|Visa, skapa, ändra och ta bort känslighetsetiketter.|Efterlevnadsdataadministratör <p> Organisationshantering <p> Säkerhetsadministratör|
|**Känslighetsetikettläsare**|Visa konfiguration och användning av känslighetsetiketter.|Global läsare <p> Organisationshantering <p> Säkerhetsläsare|
|**Vyn Tjänstgranskning**|Ladda ned tillgängliga dokument från avsnittet Tjänstgranskning. Innehållet omfattar oberoende granskning, dokumentation om efterlevnad och förtroenderelaterad vägledning för hur du använder Microsoft 365-funktioner för att hantera efterlevnads- och säkerhetsrisker.|Global läsare <p> Organisationshantering <p> Tjänstgranskningsanvändare|
|**Övervakande granskningsadministratör**|Hantera principer för övervakande granskning, inklusive vilka meddelanden som ska granskas och vem som ska göra granskningen.|Övervakande granskning|
|**Tagga deltagare**|Visa och uppdatera medlemskap för befintliga användartaggar.|Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Tagghanteraren**|Visa, uppdatera, skapa och ta bort användartaggar.|Organisationshantering <p> Säkerhetsadministratör|
|**Taggläsare**|Skrivskyddsåtkomst till befintliga användartaggar.|Säkerhetsläsare|
|**Endast visa granskningsloggar**|Visa och exportera granskningsrapporter. Eftersom dessa rapporter kan innehålla känslig information, bör du endast tilldela den här rollen till personer som uttryckligen behöver visa den här informationen.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör|
|**Endast visningsfall**||Efterlevnad av kommunikation <p> Kommunikationsefterlevnadsefterlevnad <p> Efterlevnadsadministratör <p> Hantering av insiderrisk <p> Insider-riskhanteringsadministratörer <p> Analytiker för hantering av interna risker <p> Insider RiskManagement-projektledare <p> Organisationshantering|
|**Enhetshantering, endast visa**|Visa konfiguration och rapporter för funktionen Enhetshantering.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Visningsläge för DLP-efterlevnadshantering**|Visa inställningar och rapporter för principer för dataförlustskydd (DLP).|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**IB-efterlevnadshantering, endast visa**|Visa konfiguration och rapporter för funktionen Informationsbarriärer.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Hantera aviseringar endast i visningsläge**|Visa konfiguration och rapporter för funktionen Hantera aviseringar.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> Organisationshantering <p> Säkerhetsadministratör <p> Säkerhetsoperatör <p> Säkerhetsläsare|
|**Endast visa mottagare**|Visa information om användare och grupper.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global läsare <p> MailFlow-administratör <p> Organisationshantering|
|**Posthantering, endast visa**|Visa konfigurationen av funktionen för hantering av arkivhandlingar.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> <p> Global läsare <p> Organisationshantering|
|**Bevarandehantering, endast visa**|Visa konfigurationen av bevarandeprinciper, bevarandeetiketter och bevarandeprinciper.|Efterlevnadsadministratör <p> Efterlevnadsdataadministratör <p> Global administratör <p> Organisationshantering|
|
