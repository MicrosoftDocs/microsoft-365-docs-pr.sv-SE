---
title: Behörigheter för funktioner i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Läs mer om den behörighet som krävs för uppgifter i fristående Exchange Online Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c24c6f57ea9a7c0e1b3332d2f4b518b232ec0c2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288305"
---
# <a name="permissions-in-standalone-eop"></a>Behörigheter i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

Fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor använder behörighetsmodellen Rollbaserad åtkomstkontroll (RBAC) för att enkelt ge behörigheter till administratörer. Du kan använda behörighetsfunktionerna i fristående EOP för att komma igång snabbt och komma igång med den nya organisationen.

Information om hur du beviljar behörigheter till användare [finns i Hantera administratörsrollgrupper i EOP.](manage-admin-role-group-permissions-in-eop.md)

Mer information om behörigheter i Microsoft 365 finns i [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)

## <a name="role-based-permissions"></a>Rollbaserade behörigheter

Administratörsbehörigheterna du till användarna är baserade på hanteringsroller. En hanteringsroll definierar cmdlets som är tillgängliga för en uppsättning aktiviteter. Eftersom både Exchange admin center (EAC) och fristående EOP PowerShell använder cmdlets ger bevilja åtkomst till en cmdlet användaren behörighet att utföra relaterade uppgifter i EAC eller i fristående EOP PowerShell. Till exempel definierar rollen E-postmottagare de cmdlets som krävs för att ändra e-postanvändare.

I fristående EOP är administrativa roller den enda typ av hanteringsroll som är tillgänglig (det finns inga slutanvändareroller eller rolltilldelningsprinciper).

## <a name="role-groups"></a>Rollgrupper

Fristående EOP använder rollgrupper för att göra det enklare att tilldela användare roller. Hanteringsroller tilldelas rollgrupper och rollgruppsmedlemmarna får de behörigheter som är kopplade till rollerna. Med andra ord är hanteringsroller inte direkt tilldelade till användare. de har tilldelats till rollgruppen. Med den här modellen kan du tilldela många roller till många rollgruppmedlemmar samtidigt. Rollgruppsmedlemmar kan vara e-postanvändare, e-postaktiverade säkerhetsgrupper, användare från administrationscentret för Microsoft 365 och andra rollgrupper.

I följande bild visas förhållandet mellan användare, rollgrupper och roller.

![Relationer mellan roller, rollgrupper och medlemmar](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De tillgängliga rollgrupperna i fristående EOP beskrivs i följande tabell.

****

|Rollgrupp|Beskrivning|Tilldelade standardroller|
|---|---|---|
|ComplianceManagement|Konfigurera och hantera efterlevnadsinställningar inom organisationen, inklusive skydd mot dataförlust (DLP) om prenumerationen har DLP-funktioner. <p> Medlemmar med rollen [Efterlevnadsadministratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) i Azure AD får automatiskt behörigheterna för rollgruppen.|Granskningsloggar <p> Efterlevnadsadministration <p> Information Rights Management <p> Bevarandehantering <p> View-Only granskningsloggar <p> View-Only konfiguration <p> View-Only mottagare|
|ContentExplorerContentViewer|Används inte.|Visningsprogram för dataklassificeringsinnehåll|
|ContentExplorerListViewer|Används inte.|Visningsprogram för dataklassificeringslista|
|HelpDesk|Visa och hantera e-postanvändare.|Återställa lösenord <p> Användaralternativ <p> View-Only mottagare|
|Det här är Enmanagement|Hantera skyddsfunktioner (skydd mot skräppost, skadlig programvara osv.).|Transport Ende sn s <p> View-Only konfiguration <p> View-Only mottagare|
|MailFlowAdministrator|Visa och hantera godkända domäner och kopplingar|Fjärrdomäner och godkända domäner <p> View-Only mottagare|
|OrganizationManagement|Administratörsåtkomst till hela organisationen och möjligheten att utföra nästan vilken uppgift som helst. <p> Medlemmar med rollen [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) i Azure AD får automatiskt behörigheterna för rollgruppen. <p> **Viktigt:** Eftersom rollgruppen Organisationsmanagement är en kraftfull roll är det endast användare som utför administrativa uppgifter på organisationsnivå som ska vara medlemmar i den här rollgruppen.|AntiMalware <p> AntiSpam <p> Granskningsloggar <p> Efterlevnadsadministratör <p> Distributionsgrupper <p> Information Rights Management <p> Skapa e-postmottagare <p> E-postmottagare <p> Meddelandespårning <p> Migrering <p> Klientåtkomst för organisationen <p> Organisationskonfiguration <p> Inställningar för organisationstransport <p> Karantän <p> Principer för mottagare <p> Fjärrdomäner och godkända domäner <p> Återställa lösenord <p> Bevarandehantering <p> Rollhantering <p> Säkerhetsadministratör <p> Skapa och medlemskap i säkerhetsgrupper <p> Säkerhetsläsare <p> Känslighetsetikettsadministratör <p> Överövervakning <p> Transport Ende sn s <p> Transportregler <p> Användaralternativ <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only granskningsloggar <p> View-Only konfiguration <p> View-Only karantän <p> View-Only mottagare <p> View-Only Threat Intelligence|
|QuarantineAdministrator|Hantera meddelanden i karantän för alla mottagare.|Karantän|
|RecipientManagement|Skapa, hantera och ta bort mottagarobjekt i organisationen.|Distributionsgrupper <p> Skapa e-postmottagare <p> E-postmottagare <p> Meddelandespårning <p> Migrering <p> Principer för mottagare <p> Återställa lösenord|
|RecordsManagement|Konfigurera efterlevnadsfunktioner, till exempel bevarandeprinciptaggar, meddelandeklassificerings- och e-postflödesregler (kallas även transportregler).|Meddelandespårning <p> Bevarandehantering <p> Transportregler|
|SecurityAdministrator|Konfigurera alla aspekter av skydd i organisationen (skydd mot skräppost, skadlig programvara, förfalskning, karantän osv.). <p> Medlemmar med rollen [Säkerhetsadministratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) i Azure AD får automatiskt behörigheterna för rollgruppen.|AntiMalware <p> AntiSpam <p> Granskningsloggar <p> Karantän <p> Säkerhetsadministratör <p> Känslighetsetikettsadministratör <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only granskningsloggar <p> View-Only karantän <p> View-Only Threat Intelligence|
|SecurityReader|Enkel åtkomst till alla aspekter av skyddet i organisationen (skydd mot skräppost, skadlig programvara, förfalskning, karantän osv.). <p> Medlemmar med rollen [Säkerhetsläsare](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) i Azure AD får automatiskt behörigheterna för rollgruppen.|Säkerhetsläsare <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only karantän <p> View-Only Threat Intelligence|
|TenantAdmins|Medlemskap i den här rollgruppen synkroniseras mellan tjänster och hanteras centralt. Som standard tilldelas den här rollgruppen inte några roller. Den blir dock medlem i rollgruppen Organisationshantering och ärver behörigheterna.|none (ingen)|
|ViewOnlyOrganizationManagement|Visa mottagare, skydd och konfigurationsobjekt och deras egenskaper i organisationen.|Efterlevnadsadministratör <p> Säkerhetsadministratör <p> Säkerhetsläsare <p> Känslighetsetikettsadministratör <p> View-Only konfiguration <p> View-Only mottagare|
|

Om du arbetar i en liten organisation som bara har ett fåtal administratörer kan du behöva lägga till de användarna endast i rollgruppen Organisationshantering, och du kanske aldrig behöver använda de andra rollgrupperna. Om du arbetar i en större organisation kan det hända att du har administratörer som utför specifika uppgifter, till exempel mottagarens konfiguration. I så fall kan du lägga till en administratör i rollgruppen Mottagarhantering och en annan administratör i rollgruppen Organisationshantering. Administratörerna kan sedan hantera sina specifika områden, men de har inte behörighet att hantera områden som de inte ansvarar för.

Om de inbyggda rollgrupperna i Exchange Online inte stämmer överens med jobbfunktionen för administratörerna kan du skapa rollgrupper och lägga till roller i dem. Mer information finns i Hantera [rollgrupper i fristående EOP.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>Roller

De inbyggda rollerna som är tillgängliga i fristående EOP beskrivs i följande tabell.

****

|Roll**|Beskrivning|Tilldelningar av standardrollgrupper|
|---|---|---|
|AntiMalware|Visa och ändra konfiguration och rapporter för funktioner mot skadlig programvara.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Visa och ändra konfiguration och rapporter för skydd mot skräppost.|OrganizationManagement <p> SecurityAdministrator|
|Granskningsloggar|Sök i administratörens granskningslogg och visa resultaten.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Efterlevnadsadministratör<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Visningsprogram för dataklassificeringsinnehåll<sup>\*</sup>||ContentExplorerContentViewer|
|Visningsprogram för dataklassificeringslista<sup>\*</sup>||
|Distributionsgrupper|Skapa och hantera alla distributionsgrupper, e-postaktiverade säkerhetsgrupper och medlemmar.|OrganizationManagement <p> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Skapa e-postmottagare|Skapa och ta bort e-postanvändare.|OrganizationManagement <p> RecipientManagement|
|E-postmottagare|Ändra befintliga e-postanvändare.|OrganizationManagement <p> RecipientManagement|
|Meddelandespårning<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Hantering av arkivhandlingar|
|Migrering<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Tillåter användare att visa sina egna meddelanden i karantän. <p> Den här rollen tilldelas automatiskt till användare och du kan inte tilldela den manuellt.|none (ingen)|
|Klientåtkomst för organisationen<sup>\*</sup>||OrganizationManagement|
|Organisationskonfiguration|Visa rapporter.|OrganizationManagement|
|Inställningar för organisationstransport<sup>\*</sup>||OrganizationManagement|
|Karantän|Hantera alla typer av meddelanden i karantän för alla mottagare.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Principer för mottagare<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Fjärrdomäner och godkända domäner|Hantera fjärrdomäner, godkända domäner och kopplingar.|MailFlowAdministrator <p> OrganizationManagement|
|Återställa lösenord<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Bevarandehantering<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Rollhantering|Skapa och hantera rollgrupper.|OrganizationManagement|
|Säkerhetsadministratör|Hantera konfiguration och rapporter för alla säkerhets- och skyddsfunktioner.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Skapa och medlemskap i säkerhetsgrupper|Skapa och hantera e-postaktiverade säkerhetsgrupper.|OrganizationManagement|
|Säkerhetsläsare|Visa konfiguration och rapporter för säkerhets- och skyddsfunktioner.|Organisationshantering <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Känslighetsetikettsadministratör<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Överövervakning<sup>\*</sup>||OrganizationManagement|
|Transport Ende sn s|Hantera skydd mot skadlig programvara, skydd mot skräppost och skydd mot förfalskning.|Det här är Enmanagement <p> OrganizationManagement|
|Transportregler|Skapa och hantera e-postflödesregler (kallas även transportregler).|OrganizationManagement <p> RecordsManagement|
|Användaralternativ|Ändra befintliga e-postanvändare.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Visa konfiguration och rapporter för funktioner mot skadlig programvara.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Visa konfiguration och rapporter för funktioner som är skräppostskyddade.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only granskningsloggar|Sök i administratörens granskningslogg och visa resultaten.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|View-Only konfiguration|Visa alla inställningar för organisation och e-postflöde (icke-mottagare) i organisationen.|ComplianceManagement <p> Det här är Enmanagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only karantän|Visa alla meddelanden i karantän för alla mottagare.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only mottagare|Visa mottagaregenskaper och köra meddelandespårning.|ComplianceManagement <p> HelpDesk <p> Det här är Enmanagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Threat Intelligence<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Även om den här rollen är tillgänglig så har den i princip ingenting användbart i fristående EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-behörigheter i fristående EOP

När du skapar en användare i administrationscentret för Microsoft 365 kan du välja om du vill tilldela olika administrativa roller, till exempel global administratör, tjänstadministratör, lösenordsadministratör och så vidare, till användaren. Vissa, men inte alla, Microsoft 365-roller beviljar administrativa användarbehörigheter i EOP.

> [!NOTE]
> Det konto som du använde för att skapa en fristående EOP-organisation tilldelas automatiskt rollen Global administratör.

I följande tabell visas Microsoft 365-roller och de fristående EOP-rollgrupper som de motsvarar. Mer information om de här rollerna finns i [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)

****

|Microsoft 365-roll|EOP-rollgrupp|
|---|---|
|Exchange-administratör|OrganizationManagement|
|Global administratör|OrganizationManagement <p> **Obs!** Rollen Global administratör och rollgruppen Organisationsmanagement är knutna till varandra med hjälp av en särskild rollgrupp som företagsadministratör. Rollgruppen Företagsadministratör hanteras internt och kan inte ändras direkt.|
|Lösenordsadministratör|HelpDesk|
|Global läsare|ViewOnlyOrganizationManagement|
|Säkerhetsadministratör|SecurityAdministrator|
|Säkerhetsläsare|SecurityReader|
|

Andra Microsoft 365-roller har inte en motsvarande EOP-rollgrupp och beviljar inte administrativa behörigheter i EOP. Mer information om hur du tilldelar en Microsoft 365-roll till en användare finns i [Tilldela administratörsroller.](../../admin/add-users/assign-admin-roles.md)

Användare kan beviljas administrativ behörighet i EOP utan att lägga till dem i Microsoft 365-roller. Det gör du genom att lägga till användaren som medlem i en EOP-rollgrupp. Användaren får behörigheter i EOP, men de får inte behörigheter i andra Microsoft 365-arbetsbelastningar.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har kopierat en rollgrupp genom att göra något av följande:

- Gå till Behörigheter för  administratörsroller i EAC och kontrollera \> att rollgruppen visas (eller inte visas). Markera rollgruppen och kontrollera inställningarna i informationsfönstret eller klicka på **Redigera** ikon för ![ att verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- I Exchange Online PowerShell ersätter du med namnet på rollgruppen och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och verifiera \<Role Group Name\> inställningarna:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```
