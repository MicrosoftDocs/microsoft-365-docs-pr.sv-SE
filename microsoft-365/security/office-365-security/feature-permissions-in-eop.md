---
title: Behörigheter för funktioner i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Läs mer om den behörighet som krävs för uppgifter i fristående Exchange Online Protection
ms.openlocfilehash: 0138bd4716d831a33fa4b5a0fbdce0f154d62776
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208877"
---
# <a name="permissions-in-standalone-eop"></a>Behörigheter i fristående EOP

Fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor använder rbac-behörighetsmodellen (Role Based Access Control) för att enkelt bevilja behörigheter till administratörerna. Du kan använda behörighetsfunktionerna i fristående EOP för att få igång din nya organisation snabbt.

Information om hur du beviljar behörigheter till användare finns [i Hantera administratörsrollgrupper i EOP](manage-admin-role-group-permissions-in-eop.md).

Mer information om behörigheter i Microsoft 365 finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Rollbaserade behörigheter

De administratörsbehörigheter som du beviljar användare baseras på hanteringsroller. En hanteringsroll definierar de cmdlets som är tillgängliga för en uppsättning angivna aktiviteter. Eftersom administrationscentret för Exchange (EAC) och fristående EOP PowerShell båda använder cmdlets, ger beviljandet av åtkomst till en cmdlet användaren behörighet att utföra relaterade uppgifter i EAC eller i fristående EOP PowerShell. Rollen Mottagare av e-post definierar till exempel de cmdletar som krävs för att ändra e-postanvändare.

I fristående EOP är administrativa roller den enda typen av hanteringsroll som är tillgänglig (det finns inga principer för slutanvändare eller rolltilldelning).

## <a name="role-groups"></a>Rollgrupper

För att göra det enklare att tilldela roller till användare använder fristående EOP rollgrupper. Hanteringsroller tilldelas rollgrupper och rollgruppsmedlemmarna får de behörigheter som är associerade med rollerna. Med andra ord tilldelas inte hanteringsroller direkt till användarna. de är tilldelade till rollgruppen. Med den här modellen kan du tilldela många roller till många rollgruppsmedlemmar samtidigt. Rollgruppsmedlemmar kan vara e-postanvändare, e-postaktiverade säkerhetsgrupper, användare från Microsoft 365-administrationscentret och andra rollgrupper.

Följande bild visar förhållandet mellan användare, rollgrupper och roller.

![Relationer mellan roller, rollgrupper och medlemmar](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De tillgängliga rollgrupperna i fristående EOP beskrivs i följande tabell.

||||
|---|---|---|
|**Rollgrupp**|**Beskrivning**|**Standardroller tilldelade**|
|EfterlevnadHanagement|Konfigurera och hantera efterlevnadsinställningar inom organisationen, inklusive dataförlustskydd (DLP) om din prenumeration har DLP-funktioner. <br/><br/> Medlemmar i rollen [efterlevnadsadministratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) i Azure AD får automatiskt behörigheterna för den här rollgruppen.|Granskningsloggar <br/><br/> Administration av efterlevnad <br/><br/> Information Rights Management <br/><br/> Hantering av kvarhållning <br/><br/> Granskningsloggar med endast visa <br/><br/> Endast visningskonfiguration <br/><br/> Endast visningsmottagare|
|InnehållUtforskaContentViewer|Används inte.|Innehållsvisaren för dataklassificering|
|InnehållExplorerListViewer|Används inte.|Visningsprogram för dataklassificeringslista|
|Helpdesk|Visa och hantera e-postanvändare.|Återställa lösenord <br/><br/> Användaralternativ <br/><br/> Endast visningsmottagare|
|HygienHantering|Hantera skyddsfunktioner (anti-spam, anti-malware, etc.).|Transport Hygien <br/><br/> Endast visningskonfiguration <br/><br/> Endast visningsmottagare|
|MailFlowAdministrator|Visa och hantera accepterade domäner och kopplingar|Fjärr- och accepterade domäner <br/><br/> Endast visningsmottagare|
|OrganisationManagement|Administratörsåtkomst till hela organisationen och möjligheten att utföra nästan alla uppgifter. <br/><br/> Medlemmar i rollen [Global Administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) i Azure AD får automatiskt behörigheterna för den här rollgruppen. <br/><br/> **Viktigt**: Eftersom rollgruppen OrganisationManagement är en kraftfull roll bör endast användare som utför administrativa uppgifter på organisationsnivå vara medlemmar i den här rollgruppen.|Antimalware <br/><br/> Antispam <br/><br/> Granskningsloggar <br/><br/> Administratör för efterlevnad <br/><br/> Distributionsgrupper <br/><br/> Information Rights Management <br/><br/> Skapa e-postmottagare <br/><br/> Mottagare av e-post <br/><br/> Meddelandespårning <br/><br/> Migrering <br/><br/> Åtkomst till organisationens klient <br/><br/> Organisationskonfiguration <br/><br/> Inställningar för transport för organisation <br/><br/> Karantän <br/><br/> Mottagarprinciper <br/><br/> Fjärr- och accepterade domäner <br/><br/> Återställa lösenord <br/><br/> Hantering av kvarhållning <br/><br/> Rollhantering <br/><br/> Säkerhetsadministratör <br/><br/> Skapande och medlemskap i säkerhetsgrupper <br/><br/> Säkerhetsläsare <br/><br/> Administratör för känslighetsetikett <br/><br/> Övervakning <br/><br/> Transport Hygien <br/><br/> Transportregler <br/><br/> Användaralternativ <br/><br/> Visa endast antimalware <br/><br/> Visa endast AntiSpam <br/><br/> Granskningsloggar med endast visa <br/><br/> Endast visningskonfiguration <br/><br/> Endast visnings karantän <br/><br/> Endast visningsmottagare <br/><br/> Endast visning av hotinformation|
|KarantänAdministrator|Hantera meddelanden i karantän för alla mottagare.|Karantän|
|MottagareHanagement|Skapa, hantera och ta bort mottagarobjekt i organisationen.|Distributionsgrupper <br/><br/> Skapa e-postmottagare <br/><br/> Mottagare av e-post <br/><br/> Meddelandespårning <br/><br/> Migrering <br/><br/> Mottagarprinciper <br/><br/> Återställa lösenord|
|Arkivhandlingar|Konfigurera efterlevnadsfunktioner, till exempel bevarandeprinciptaggar, meddelandeklassificeringar och regler för e-postflöde (kallas även transportregler).|Meddelandespårning <br/><br/> Hantering av kvarhållning <br/><br/> Transportregler|
|SäkerhetAdministrator|Konfigurera alla aspekter av skydd i organisationen (anti-spam, anti-malware, anti-spoofing, karantän, etc.). <br/><br/> Medlemmar i rollen [Säkerhetsadministratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) i Azure AD får automatiskt behörigheterna för den här rollgruppen.|Antimalware <br/><br/> Antispam <br/><br/> Granskningsloggar <br/><br/> Karantän <br/><br/> Säkerhetsadministratör <br/><br/> Administratör för känslighetsetikett <br/><br/> Visa endast antimalware <br/><br/> Visa endast AntiSpam <br/><br/> Granskningsloggar med endast visa <br/><br/> Endast visnings karantän <br/><br/> Endast visning av hotinformation|
|Säkerhetsläsare|Visa endast tillgång till alla aspekter av skydd i organisationen (anti-spam, anti-malware, anti-spoofing, karantän, etc.). <br/><br/> Medlemmar i [säkerhetsläkarrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) i Azure AD får automatiskt behörigheterna för den här rollgruppen.|Säkerhetsläsare <br/><br/> Visa endast antimalware <br/><br/> Visa endast AntiSpam <br/><br/> Endast visnings karantän <br/><br/> Endast visning av hotinformation|
|TenantAdmins|Medlemskap i den här rollgruppen synkroniseras mellan tjänster och hanteras centralt. Som standard tilldelas den här rollgruppen inga roller. Den kommer dock att vara medlem i rollgruppen Organisationshantering och ärver dessa behörigheter.|none (ingen)|
|ViewOnlyOrganizationManagement|Visa mottagar-, skydds- och konfigurationsobjekt och deras egenskaper i organisationen.|Administratör för efterlevnad <br/><br/> Säkerhetsadministratör <br/><br/> Säkerhetsläsare <br/><br/> Administratör för känslighetsetikett <br/><br/> Endast visningskonfiguration <br/><br/> Endast visningsmottagare|
|

Om du arbetar i en liten organisation som bara har ett fåtal administratörer kan du behöva lägga till dessa användare i rollgruppen Organisationshantering, och du kanske aldrig behöver använda de andra rollgrupperna. Om du arbetar i en större organisation kan du ha administratörer som utför specifika uppgifter, till exempel mottagarkonfiguration. I sådana fall kan du lägga till en administratör i rollgruppen Mottagarehantering och en annan administratör i rollgruppen Organisationshantering. Dessa administratörer kan sedan hantera sina specifika områden, men de har inte behörighet att hantera områden som de inte är ansvariga för.

Om de inbyggda rollgrupperna i Exchange Online inte matchar jobbfunktionen för dina administratörer kan du skapa rollgrupper och lägga till roller i dem. Mer information finns i [Hantera rollgrupper i fristående EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Roller

De inbyggda rollerna som är tillgängliga i fristående EOP beskrivs i följande tabell.

||||
|---|---|---|
|**Roll**|**Beskrivning**|**Standardrollgrupptilldelningar**|
|Antimalware|Visa och ändra konfigurationen och rapporterna för funktioner mot skadlig kod.|OrganisationManagement <br/><br/> SäkerhetAdministrator|
|Antispam|Visa och ändra konfigurationen och rapporterna för funktioner mot skräppost.|OrganisationManagement <br/><br/> SäkerhetAdministrator|
|Granskningsloggar|Sök i administratörsgranskningsloggen och visa resultaten.|EfterlevnadHanagement <br/><br/> OrganisationManagement <br/><br/> SäkerhetAdministrator|
|Administratör för efterlevnad<sup>\*</sup>||EfterlevnadHanagement <br/><br/> OrganisationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Innehållsvisaren för dataklassificering<sup>\*</sup>||InnehållUtforskaContentViewer|
|Visningsprogram för dataklassificeringslista<sup>\*</sup>||
|Distributionsgrupper|Skapa och hantera alla distributionsgrupper, e-postaktiverade säkerhetsgrupper och medlemmar.|OrganisationManagement <br/><br/> MottagareHanagement|
|Hantering av informationsrättigheter<sup>\*</sup>||EfterlevnadHanagement <br/><br/> OrganisationManagement|
|Skapa e-postmottagare|Skapa och ta bort e-postanvändare.|OrganisationManagement <br/><br/> MottagareHanagement|
|Mottagare av e-post|Ändra befintliga e-postanvändare.|OrganisationManagement <br/><br/> MottagareHanagement|
|Meddelandespårning<sup>\*</sup>||OrganisationManagement <br/><br/> MottagareHanagement <br/><br/> Hantering av arkivhandlingar|
|Migration<sup>\*</sup>||OrganisationManagement <br/><br/> MottagareHanagement|
|MyBaseOptions|Tillåter användare att visa sina egna meddelanden i karantän. <br/><br/> Den här rollen tilldelas automatiskt till användare och du kan inte tilldela den manuellt.|none (ingen)|
|Åtkomst till organisationens klient<sup>\*</sup>||OrganisationManagement|
|Organisationskonfiguration|Visa rapporter.|OrganisationManagement|
|Inställningar för transport för organisation<sup>\*</sup>||OrganisationManagement|
|Karantän|Hantera alla typer av meddelanden i karantän för alla mottagare.|OrganisationManagement <br/><br/> KarantänAdministrator <br/><br/> SäkerhetAdministrator|
|Mottagarprinciper<sup>\*</sup>||OrganisationManagement <br/><br/> MottagareHanagement|
|Fjärr- och accepterade domäner|Hantera fjärrdomäner, accepterade domäner och anslutningsappar.|MailFlowAdministrator <br/><br/> OrganisationManagement|
|Återställa lösenord<sup>\*</sup>||Helpdesk <br/><br/> OrganisationManagement <br/><br/> MottagareHanagement|
|Hantering av kvarhållning<sup>\*</sup>||EfterlevnadHanagement <br/><br/> OrganisationManagement <br/><br/> Arkivhandlingar|
|Rollhantering|Skapa och hantera rollgrupper.|OrganisationManagement|
|Säkerhetsadministratör|Hantera konfigurationen och rapporterna för alla säkerhets- och skyddsfunktioner.|OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Skapande och medlemskap i säkerhetsgrupper|Skapa och hantera e-postaktiverade säkerhetsgrupper.|OrganisationManagement|
|Säkerhetsläsare|Visa konfigurationen och rapporterna för säkerhets- och skyddsfunktioner.|Organisationshantering <br/><br/> Säkerhetsläsare <br/><br/> ViewOnlyOrganizationManagement|
|Administratör för känslighetsetikett<sup>\*</sup>||OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Övervakning<sup>\*</sup>||OrganisationManagement|
|Transport Hygien|Hantera funktioner mot skadlig kod, skräppost och förfalskningsfunktioner.|HygienHantering <br/><br/> OrganisationManagement|
|Transportregler|Skapa och hantera regler för e-postflöde (kallas även transportregler).|OrganisationManagement <br/><br/> Arkivhandlingar|
|Användaralternativ|Ändra befintliga e-postanvändare.|Helpdesk <br/><br/> OrganisationManagement|
|Visa endast antimalware|Visa konfigurationen och rapporterna för funktioner mot skadlig kod.|OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> Säkerhetsläsare|
|Visa endast AntiSpam|Visa konfigurationen och rapporterna för funktioner mot skräppost.|OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> Säkerhetsläsare|
|Granskningsloggar med endast visa|Sök i administratörsgranskningsloggen och visa resultaten.|EfterlevnadHanagement <br/><br/> OrganisationManagement <br/><br/> SäkerhetAdministrator|
|Endast visningskonfiguration|Visa alla inställningar för organisation och e-postflöde (ej mottagare) i organisationen.|EfterlevnadHanagement <br/><br/> HygienHantering <br/><br/> OrganisationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Endast visnings karantän|Visa alla meddelanden i karantän för alla mottagare.|OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> Säkerhetsläsare|
|Endast visningsmottagare|Visa mottagaregenskaper och kör meddelandespårning.|EfterlevnadHanagement <br/><br/> Helpdesk <br/><br/> HygienHantering <br/><br/> MailFlowAdministrator <br/><br/>  OrganisationManagement <br/><br/> ViewOnlyOrganizationManagement|
|Endast visning av hotinformation<sup>\*</sup>||OrganisationManagement <br/><br/> SäkerhetAdministrator <br/><br/> Säkerhetsläsare|
|

<sup>\*</sup>Även om denna roll är tillgänglig, gör den i princip inget användbart i fristående EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-behörigheter i fristående EOP

När du skapar en användare i administrationscentret för Microsoft 365 kan du välja om du vill tilldela olika administrativa roller, till exempel Global administratör, Tjänstadministratör, Lösenordsadministratör och så vidare, till användaren. Vissa, men inte alla, Microsoft 365-roller ger användaren administratörsbehörighet i EOP.

> [!NOTE]
> Kontot som du använde för att skapa din fristående EOP-organisation tilldelas automatiskt rollen Global admin.

I följande tabell visas de Microsoft 365-roller och fristående EOP-rollgrupper som de motsvarar. Mer information om dessa roller finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

|||
|---|---|
|**Microsoft 365-roll**|**EOP-rollgrupp**|
|Exchange-administratör|OrganisationManagement|
|Global administratör|OrganisationManagement <br/><br/> **Rollen**Global administratör och rollgruppen OrganizationManagement binds samman med hjälp av en särskild rollgrupp för företagsadministratör. Rollgruppen Företagsadministratör hanteras internt och kan inte ändras direkt.|
|Lösenordsadministratör|Helpdesk|
|Global läsare|ViewOnlyOrganizationManagement|
|Säkerhetsadministratör|SäkerhetAdministrator|
|Säkerhetsläsare|Säkerhetsläsare|
|

Andra Microsoft 365-roller har ingen motsvarande EOP-rollgrupp och beviljar inte administratörsbehörighet i EOP. Mer information om hur du tilldelar en Microsoft 365-roll till en användare finns i [Tilldela administratörsroller](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles).

Användare kan beviljas administrativa rättigheter i EOP utan att lägga till dem i Microsoft 365-roller. Du gör detta genom att lägga till användaren som medlem i en EOP-rollgrupp. Användaren får behörigheter i EOP, men de får inte behörigheter i andra Microsoft 365-arbetsbelastningar.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har kopierat en rollgrupp:

- Gå till **Administratörsroller** för behörigheter och kontrollera att \> **Admin Roles**rollgruppen visas (eller inte visas). Markera rollgruppen och kontrollera inställningarna i informationsfönstret eller klicka på **Redigera** ![ redigera ikon för att verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- I Exchange Online PowerShell ersätter du \< Rollgruppsnamnet \> med namnet på rollgruppen och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och verifiera inställningarna:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
