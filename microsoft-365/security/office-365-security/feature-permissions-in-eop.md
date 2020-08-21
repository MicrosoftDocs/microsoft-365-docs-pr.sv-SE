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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Läs mer om den behörighet som krävs för uppgifter i det fristående Exchange Online Protection
ms.openlocfilehash: f9c0f0549ba5a0a65fa3bbe3af1afbfddc6e735c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826631"
---
# <a name="permissions-in-standalone-eop"></a>Behörigheter i fristående EOP

Fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor använder RBAC-behörighet (rollbaserad åtkomst kontroll) för att enkelt ge administratörer behörigheter. Du kan använda behörighets funktionerna i fristående EOP för att snabbt komma igång med din nya organisation.

Information om hur du tilldelar användare behörigheter finns i [Hantera administratörs roll grupper i EOP](manage-admin-role-group-permissions-in-eop.md).

Mer information om behörigheter i Microsoft 365 finns i [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Rollbaserade behörigheter

Administratörs behörighet som du ger användare baseras på hanterings roller. En hanterings roll definierar de cmdlets som är tillgängliga för en uppsättning uppgifter. Eftersom administrations centret för Exchange (UK) och den fristående EOP-PowerShell använder båda cmdlets ger användare behörighet att utföra relaterade uppgifter i UK eller i fristående EOP PowerShell. Rollen e-postmottagare definierar till exempel de cmdlets som krävs för att ändra e-postanvändare.

I fristående EOP är administrativa roller den enda typ av hanterings roll som är tillgänglig (det finns inga roller för slutanvändare eller roll tilldelning).

## <a name="role-groups"></a>Roll grupper

För att göra det lättare att tilldela roller till användare använder fristående EOP roll grupper. Hanterings roller är tilldelade till roll grupper och roll gruppens medlemmar får de behörigheter som är kopplade till rollerna. Med andra ord är inte lednings roller direkt kopplade till användarna. de har tilldelats roll gruppen. Med den här modellen kan du tilldela många roller till många roll grupps medlemmar samtidigt. Roll grupps medlemmar kan vara e-postanvändare, e-postaktiverade säkerhets grupper, användare från Microsoft 365 Admin Center och andra roll grupper.

Följande bild visar förhållandet mellan användare, roll grupper och roller.

![Relationer mellan roller, rollgrupper och medlemmar](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

De tillgängliga roll grupperna i fristående EOP beskrivs i följande tabell.

****

|Roll grupp|Beskrivning|Standard roller tilldelade|
|---|---|---|
|ComplianceManagement|Konfigurera och hantera inställningar för efterlevnad i organisationen, inklusive data förlust skydd (DLP) om ditt abonnemang har DLP-funktioner. <br/><br/> Medlemmar i rollen [efterlevnad för administratörer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) i Azure AD får automatiskt behörigheterna för den här roll gruppen.|Gransknings loggar <br/><br/> Administration av efterlevnad <br/><br/> Information Rights Management <br/><br/> Hantering av bevarande <br/><br/> Gransknings loggar endast för visning <br/><br/> Skrivskyddad konfiguration <br/><br/> Endast visning-mottagare|
|ContentExplorerContentViewer|Används inte.|Innehålls översikt för data klassificering|
|ContentExplorerListViewer|Används inte.|Visnings program för data klassificering|
|Kontakta|Visa och hantera e-postanvändare.|Återställ lösen ord <br/><br/> Användar alternativ <br/><br/> Endast visning-mottagare|
|HygieneManagement|Hantera skydds funktioner (anti-spam, mot skadlig program vara osv.).|Transport hygien <br/><br/> Skrivskyddad konfiguration <br/><br/> Endast visning-mottagare|
|MailFlowAdministrator|Visa och hantera godkända domäner och kopplingar|Fjärranslutna och godkända domäner <br/><br/> Endast visning-mottagare|
|I|Administratörs åtkomst till hela organisationen och möjligheten att utföra nästan alla uppgifter. <br/><br/> Medlemmar i rollen [Global administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) i Azure AD hämtar automatiskt behörigheterna för den här roll gruppen. <br/><br/> **Viktigt**! eftersom roll gruppen i är en kraftfull roll ska endast användare som utför administrativa uppgifter på arbets nivå vara medlemmar i den här roll gruppen.|Antimalware <br/><br/> AntiSpam <br/><br/> Gransknings loggar <br/><br/> Administratör för efterlevnad <br/><br/> Distributionsgrupper <br/><br/> Information Rights Management <br/><br/> Skapa e-postmottagare <br/><br/> E-postmottagare <br/><br/> Meddelande uppföljning <br/><br/> Migrering <br/><br/> Åtkomst till organisations klient <br/><br/> Organisations konfiguration <br/><br/> Inställningar för organisations transport <br/><br/> Karantän <br/><br/> Mottagar principer <br/><br/> Fjärranslutna och godkända domäner <br/><br/> Återställ lösen ord <br/><br/> Hantering av bevarande <br/><br/> Roll hantering <br/><br/> Säkerhets administratör <br/><br/> Skapa och medlemskap i säkerhets grupper <br/><br/> Säkerhets läsare <br/><br/> Etikett administratör för känslighet <br/><br/> Valt <br/><br/> Transport hygien <br/><br/> Transport regler <br/><br/> Användar alternativ <br/><br/> Skrivskyddat antivirus program <br/><br/> Skrivskyddat AntiSpam <br/><br/> Gransknings loggar endast för visning <br/><br/> Skrivskyddad konfiguration <br/><br/> Endast visning-karantän <br/><br/> Endast visning-mottagare <br/><br/> Skrivskyddad Threat Intelligence|
|QuarantineAdministrator|Hantera meddelanden i karantän för alla mottagare.|Karantän|
|RecipientManagement|Skapa, hantera och ta bort mottagar objekt i organisationen.|Distributionsgrupper <br/><br/> Skapa e-postmottagare <br/><br/> E-postmottagare <br/><br/> Meddelande uppföljning <br/><br/> Migrering <br/><br/> Mottagar principer <br/><br/> Återställ lösen ord|
|RecordsManagement|Konfigurera funktioner för regelefterlevnad, till exempel bevarande princip koder, meddelande klassificeringar och regler för e-postflöde (kallas även transport regler).|Meddelande uppföljning <br/><br/> Hantering av bevarande <br/><br/> Transport regler|
|SecurityAdministrator|Konfigurera alla aspekter av skydd i organisationen (anti-spam, mot skadlig kod, anti-förfalskning, karantän osv.). <br/><br/> Medlemmar i rollen [säkerhets administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) i Azure AD hämtar automatiskt behörigheterna för den här roll gruppen.|Antimalware <br/><br/> AntiSpam <br/><br/> Gransknings loggar <br/><br/> Karantän <br/><br/> Säkerhets administratör <br/><br/> Etikett administratör för känslighet <br/><br/> Skrivskyddat antivirus program <br/><br/> Skrivskyddat AntiSpam <br/><br/> Gransknings loggar endast för visning <br/><br/> Endast visning-karantän <br/><br/> Skrivskyddad Threat Intelligence|
|SecurityReader|Skrivskyddad åtkomst till alla skydds aspekter i organisationen (anti-spam, skadlig program vara, anti-förfalskning, karantän osv.). <br/><br/> Medlemmar i rollen [säkerhets läsare](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) i Azure AD får automatiskt behörigheterna för den här roll gruppen.|Säkerhets läsare <br/><br/> Skrivskyddat antivirus program <br/><br/> Skrivskyddat AntiSpam <br/><br/> Endast visning-karantän <br/><br/> Skrivskyddad Threat Intelligence|
|TenantAdmins|Medlemskap i den här roll gruppen synkroniseras mellan tjänster och hanteras centralt. Den här roll gruppen är som standard inte tilldelad några roller. Det kommer att vara medlem i roll gruppen organisations hantering och kommer att ärva dessa behörigheter.|none (ingen)|
|ViewOnlyOrganizationManagement|Visa mottagare, skydd och konfigurations objekt samt deras egenskaper i organisationen.|Administratör för efterlevnad <br/><br/> Säkerhets administratör <br/><br/> Säkerhets läsare <br/><br/> Etikett administratör för känslighet <br/><br/> Skrivskyddad konfiguration <br/><br/> Endast visning-mottagare|
|

Om du arbetar i en mindre organisation som bara har några få administratörer kan du behöva lägga till dessa användare i roll gruppen organisations hantering och du kan aldrig behöva använda de andra roll grupperna. Om du arbetar i en större organisation kan du ha administratörer som utför specifika uppgifter, till exempel inställningar för mottagare. I sådana fall kan du lägga till en administratör i roll gruppen för mottagar hantering och en annan administratör till roll gruppen organisations hantering. Dessa administratörer kan sedan hantera sina särskilda områden, men de har inte behörighet att hantera områden som de inte ansvarar för.

Om de inbyggda roll grupperna i Exchange Online inte matchar arbets administratörens jobb funktion kan du skapa roll grupper och lägga till roller för dem. Mer information finns i [Hantera roll grupper i fristående EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Role

De inbyggda rollerna som är tillgängliga i fristående EOP beskrivs i följande tabell.

****

|Roll * *|Beskrivning|Standard roll grupp tilldelningar|
|---|---|---|
|Antimalware|Visa och ändra konfiguration och rapporter för funktioner mot skadlig program vara.|I <br/><br/> SecurityAdministrator|
|AntiSpam|Visa och ändra konfiguration och rapporter för skydd mot skräp post.|I <br/><br/> SecurityAdministrator|
|Gransknings loggar|Sök i gransknings loggen för administratörer och se resultatet.|ComplianceManagement <br/><br/> I <br/><br/> SecurityAdministrator|
|Administratör för efterlevnad<sup>\*</sup>||ComplianceManagement <br/><br/> I <br/><br/> ViewOnlyOrganizationManagement|
|Innehålls översikt för data klassificering<sup>\*</sup>||ContentExplorerContentViewer|
|Visnings program för data klassificering<sup>\*</sup>||
|Distributionsgrupper|Skapa och hantera alla distributions grupper, e-postaktiverade säkerhets grupper och medlemmar.|I <br/><br/> RecipientManagement|
|Information Rights Management<sup>\*</sup>||ComplianceManagement <br/><br/> I|
|Skapa e-postmottagare|Skapa och ta bort e-postanvändare.|I <br/><br/> RecipientManagement|
|E-postmottagare|Ändra befintliga e-postanvändare.|I <br/><br/> RecipientManagement|
|Meddelande uppföljning<sup>\*</sup>||I <br/><br/> RecipientManagement <br/><br/> Hantering av Arkiv handlingar|
|Migreringsläge<sup>\*</sup>||I <br/><br/> RecipientManagement|
|MyBaseOptions|Gör det möjligt för användarna att visa sina egna meddelanden i karantän. <br/><br/> Rollen tilldelas automatiskt till användarna och du kan inte tilldela den manuellt.|none (ingen)|
|Åtkomst till organisations klient<sup>\*</sup>||I|
|Organisations konfiguration|Visa rapporter.|I|
|Inställningar för organisations transport<sup>\*</sup>||I|
|Karantän|Hantera alla typer av meddelande i karantän för alla mottagare.|I <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Mottagar principer<sup>\*</sup>||I <br/><br/> RecipientManagement|
|Fjärranslutna och godkända domäner|Hantera fjärrdomäner, godkända domäner och kopplingar.|MailFlowAdministrator <br/><br/> I|
|Återställ lösen ord<sup>\*</sup>||Kontakta <br/><br/> I <br/><br/> RecipientManagement|
|Hantering av bevarande<sup>\*</sup>||ComplianceManagement <br/><br/> I <br/><br/> RecordsManagement|
|Roll hantering|Skapa och hantera roll grupper.|I|
|Säkerhets administratör|Hantera konfigurationen och rapporterna för alla säkerhets-och skydds funktioner.|I <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Skapa och medlemskap i säkerhets grupper|Skapa och hantera e-postaktiverade säkerhets grupper.|I|
|Säkerhets läsare|Visa konfiguration och rapporter för säkerhets-och skydds funktioner.|Organisationshantering <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|Etikett administratör för känslighet<sup>\*</sup>||I <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Valt<sup>\*</sup>||I|
|Transport hygien|Hantera funktioner mot skadlig program vara, skräp post och anti-förfalskningar.|HygieneManagement <br/><br/> I|
|Transport regler|Skapa och hantera regler för e-postflöde (kallas även transport regler).|I <br/><br/> RecordsManagement|
|Användar alternativ|Ändra befintliga e-postanvändare.|Kontakta <br/><br/> I|
|Skrivskyddat antivirus program|Visa konfiguration och rapporter för funktioner mot skadlig program vara.|I <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Skrivskyddat AntiSpam|Visa konfiguration och rapporter för skydd mot skräp post.|I <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Gransknings loggar endast för visning|Sök i gransknings loggen för administratörer och se resultatet.|ComplianceManagement <br/><br/> I <br/><br/> SecurityAdministrator|
|Skrivskyddad konfiguration|Visa alla inställningar för organisationen och e-postflöde (icke-mottagare) i organisationen.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> I <br/><br/> ViewOnlyOrganizationManagement|
|Endast visning-karantän|Visa alla meddelanden i karantän för alla mottagare.|I <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Endast visning-mottagare|Visa egenskaper för mottagare och kör meddelande spårning.|ComplianceManagement <br/><br/> Kontakta <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  I <br/><br/> ViewOnlyOrganizationManagement|
|Skrivskyddad Threat Intelligence<sup>\*</sup>||I <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup> Även om den här rollen är tillgänglig gör den egentligen inget användbart i fristående EOP.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365-behörigheter i fristående EOP

När du skapar en användare i administrations centret för Microsoft 365 kan du välja om du vill tilldela olika administrativa roller, till exempel global administratör, tjänst administratör, lösen ords administratör och så vidare, till användaren. Vissa, men inte alla, Microsoft 365-roller ger administratörs behörighet för användare i EOP.

> [!NOTE]
> Det konto som du använde för att skapa en fristående EOP-organisation tilldelas automatiskt till rollen global administratör.

I följande tabell visas Microsoft 365-roller och de fristående EOP som de motsvarar. Mer information om de här rollerna finns i [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Microsoft 365-roll|Roll gruppen EOP|
|---|---|
|Exchange-administratör|I|
|Global administratör|I <br/><br/> **Obs!** den globala administratörs rollen och i-rolltjänsten är sammankopplade med en speciell roll grupp för företags administratörer. Roll gruppen företags administratörer hanteras internt och kan inte ändras direkt.|
|Lösenordsadministratör|Kontakta|
|Global läsare|ViewOnlyOrganizationManagement|
|Säkerhetsadministratör|SecurityAdministrator|
|Säkerhetsläsare|SecurityReader|
|

Andra Microsoft 365-roller har ingen motsvarande EOP roll grupp och ger inte administratörs behörighet i EOP. Mer information om hur du tilldelar en Microsoft 365-roll till en användare finns i [tilldela administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).

Användare kan beviljas administrativa rättigheter i EOP utan att lägga till dem i Microsoft 365-roller. Det gör du genom att lägga till användaren som medlem i en EOP. Användaren får behörighet i EOP, men de får inte behörighet i andra Microsoft 365-arbetsbelastningar.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrol lera att du har kopierat en roll grupp gör du något av följande:

- Gå **till** \> **Administratörs rollerna**i UK och kontrol lera att roll gruppen är listad (eller inte listad). Välj roll gruppen och kontrol lera inställningarna i informations fönstret eller klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) för att bekräfta inställningarna.

- I Exchange Online PowerShell ersätter du \<Role Group Name\> namnet på roll gruppen och kör följande kommando för att kontrol lera att roll gruppen finns (eller inte existerar) och verifierar inställningarna:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
