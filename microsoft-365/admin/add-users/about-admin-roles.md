---
title: Om administratörsroller i administrationscentret för Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Administratörsroller som Tjänsteadministratör mappar till affärsfunktioner och ger behörighet att utföra särskilda uppgifter i administrationscentret.
ms.openlocfilehash: 801a5a85479e431b46883c69e75b1ea909892ca1
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964578"
---
# <a name="about-admin-roles"></a>Om administratörsroller

Microsoft 365- eller Office 365-prenumeration innehåller en uppsättning administratörsroller som du kan tilldela användare i din organisation i Administrationscenter för Microsoft 365. Varje administratörsroll mappar till vanliga affärsfunktioner och ger personerna i organisationen behörighet att utföra särskilda uppgifter i administrationscentret.

I Administrationscenter för Microsoft 365 kan du hantera Azure Active Directory-roller och Microsoft Intune-roller. Dessa roller är dock en deluppsättning av rollerna som finns tillgängliga i Azure Active Directory-portalen och administrationscentret för Intune.

## <a name="before-you-begin"></a>Innan du börjar

Vill du ha en komplett lista över detaljerade Azure AD-rollbeskrivningar som du kan hantera i administrations centret för Microsoft 365? Ta en titt på Administratörens rollbehörigheter i Azure Active Directory. [Administratörens rollbehörigheter i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Vill du ha en komplett lista över detaljerade Intune-rollbeskrivningar som du kan hantera i administrations centret för Microsoft 365?  Ta en titt på [Rollbaserad åtkomstkontroll (RBAC) med Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Mer information om hur du tilldelar roller i Administrationscenter för Microsoft 365 finns i [Tilldela administratörsroller](assign-admin-roles.md).

## <a name="watch-what-is-an-admin"></a>Titta: Vad är en administratör?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Säkerhetsriktinjer för tilldelning av roller

Eftersom administratörer har tillgång till känsliga data och filer rekommenderar vi att du följer dessa riktlinjer för att skydda organisationens data.

| Rekommendation                  | Varför är det viktigt?                 |
| :------------------- | :------------------- |
| Ha 2 till 4 globala administratörer  | Eftersom det bara är en global administratör som kan återställa lösenordet för en annan global administratör så rekommenderar vi att du har minst 2 globala administratörer i organisationen i händelse av kontoutelåsning. Men globala administratörer har nästan obegränsad åtkomst till organisationens inställningar och de flesta data, därför rekommenderar vi att du inte har fler än fyra globala administratörer eftersom det är ett säkerhetshot. |
| Tilldela *begränsade* roller     | Genom att tilldela *begränsade* roller får administratörerna bara den behörighet som behövs för att få jobbet gjort. Om du till exempel vill att någon ska återställa lösenord för anställda bör du inte tilldela den obegränsade rollen som global administratör, i stället kan du tilldela en begränsad roll som lösenordsadministratör eller supportadministratör. På så sätt skyddar du dina data.                 |
| Konfigurera multifaktorautentisering för administratörer                  |    Det är en bra idé att kräva MFA för alla användare, men administratörer i synnerhet bör använda MFA för att logga in. MFA gör att användarna måste använda ytterligare en identifieringsmetod för att verifiera sin identitet. Administratörer kan ha tillgång till stora mängder kund- och personaldata och om du använder MFA är själva lösenordet oanvändbart utan en andra verifiering i händelse av att administratörslösenordet äventyras.  <br><br>När du aktiverar MFA måste användaren ange en alternativ e-postadress och ett telefonnummer för kontoåterställning nästa gång användaren loggar in.  <br> [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Om du får ett meddelande i administrationscentret om att du inte har behörighet att redigera inställningar eller sidor beror det på att du har tilldelats en roll som inte har den behörigheten.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Vanliga roller för administrationscenter för Microsoft 365

I Administrationscenter för Microsoft 365 går du till **Roller** och väljer sedan en roll för att öppna informationsfönstret. Välj fliken **Behörigheter** om du vill visa en detaljerad lista över vilka behörigheter som administratörer som tilldelats rollen har. Välj fliken **Tilldelad** eller **Tilldelade administratörer** om du vill lägga till användare i roller.

Du behöver antagligen bara tilldela följande roller i organisationen. Som standard visar vi först de roller som de flesta organisationer använder. Om du inte hittar någon roll går du till slutet av listan och väljer **Visa alla efter kategori**. Om du letar efter detaljerad information, inklusive cmdlets som är kopplade till en roll, kan du läsa [Behörigheter för administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

|Administratörsroll     |Vem ska ha tilldelas denna roll?  |
|---------|---------|
|Faktureringsadministratör     |   Tilldela rollen faktureringsadministratör till användare som gör inköp, hanterar prenumerationer och tjänsteförfrågningar och övervakar tjänststatus. <br><br> Faktureringsadministratörer kan även:<br> – Hantera alla aspekter av fakturering <br> – Skapa och hantera supportärenden i Azure Portal <br>  |
|Exchange-administratör     |   Tilldela rollen som Exchange-administratör till användare som behöver visa och hantera postlådor, Microsoft 365-grupper och Exchange Online som tillhör din användare. <br><br> Exchange-administratörer kan även:<br> – Återskapa borttagna objekt i en användares postlåda <br> – Konfigurera ombud av typerna "Skicka som" och "Skicka för" <br>  |
|Global administratör     |   Tilldela rollen som global administratör till användare som behöver global åtkomst till de flesta hanteringsfunktioner och data i Microsoft Online Services. <br><br> Att ge för många användare global åtkomst är en säkerhetsrisk och vi rekommenderar att du har mellan två och fyra globala administratörer. <br><br> Det är bara globala administratörer som kan:<br> – Återställa lösenord för alla användare <br> – Lägga till och hantera domäner <br> <br> **Obs!** Den person som har registrerat sig för Microsoft Online Services blir automatiskt global administratör. |
|Global läsare    |   Tilldela rollen global läsare till användare som behöver visa administratörsfunktioner och -inställningar i administrationscenter som den globala administratören kan visa. Den globala läsaradministratören kan inte ändra några inställningar.   |
|Grupper-administratör     |   Tilldelar gruppadministratörsrollen till användare som behöver hantera alla gruppinställningar i olika administrationscenter, inklusive administrationscentret för Microsoft 365 och Azure Active Directory-portalen. <br><br> Grupper-administratörer kan:<br> – Skapa, redigera, ta bort och återställa Microsoft 365-grupper <br> – Skapa och uppdatera skapande, upphörande och namngivningsprinciper för grupper <br> – Skapa, redigera, ta bort och återställa Azure Active Directory-säkerhetsgrupper| 
|Supportadministratör     |   Tilldela rollen som supportadministratör till användare som behöver göra följande:<br> – Återställa lösenord <br> – Tvinga att användare loggar ut <br> – Hantera tjänsteförfrågningar <br> – Övervaka tjänstens status <br> <br> **Obs**! Supportadministratören kan bara hjälpa användare som inte är administratörer och användare som tilldelats följande roller: katalogläsare, gästinbjudare, supportadministratör, meddelandecenter-administratör och rapportläsare.      |
|Licensadministratör    |   Tilldela rollen licensadministratör till användare som behöver tilldela och ta bort licenser från användare och redigera deras användningsplats. <br/><br/> Licensadministratörer kan även: <br> – Omarbeta licensuppdrag för gruppbaserad licensiering <br> – Tilldela produktlicenser till grupper för gruppbaserad licensiering  |
|Administratör för Office-program    |   Tilldela rollen som administratör för Office-program till användare som behöver göra följande: <br> – Använda tjänsten för molnprinciper i Office för att skapa och hantera molnbaserade principer för Office <br> – Skapa och hantera tjänsteförfrågningar <br> – Hantera nyhetsinnehållet som användarna ser i sina Office-program   <br> – Övervaka tjänstens status  |
|Lösenordsadministratör  |   Tilldela rollen lösenordsadministratör till en användare som behöver återställa lösenord för icke-administratörer och lösenordsadministratörer.   |
|Läsare i Meddelandecenter |   Tilldela rollen som rapportläsare till användare som behöver göra följande: <br> – Övervaka meddelanden i meddelandecentret <br> – Få veckovisa e-postmeddelanden med inlägg och uppdateringar i meddelandecentret <br> – Dela inlägg i Meddelandecenter <br> – Ha skrivskyddad åtkomst till Azure AD-tjänster, till exempel användare och grupper|
|Administratör för Power Platform |   Tilldela rollen som rapportläsare till användare som behöver göra följande: <br> – Hantera alla administrativa funktioner för PowerApps, Power Automate och dataförlustskydd <br> – Skapa och hantera tjänsteförfrågningar <br> – Övervaka tjänstens status  |
|Rapportläsare |   Tilldela rollen som rapportläsare till användare som behöver göra följande: <br> – Visa användningsdata och aktivitetsrapporterna i administrationscentret för Microsoft 365 <br> – Få tillgång till innehållspaketet för införande av Power BI <br> – Få åtkomst till inloggningsrapporter och -aktivitet i Azure AD <br> – Visa data som returneras av rapporterings-API i Microsoft Graph|
|Supportadministratör för tjänst   |   Tilldela rollen Tjänstsupportadministratör som en extra-roll för administratörer eller användare som behöver göra följande utöver deras vanliga administratörsroll: <br> – Öppna och hantera tjänsteförfrågningar <br> – Visa och dela inlägg från meddelandecenter <br> – Övervaka tjänstens status   |
|SharePoint-administratör    |   Tilldela SharePoint-administratörsrollen till användare som behöver åtkomst till och behöver hantera administrationscentret för SharePoint Online. <br><br>SharePoint-administratörer kan även: <br> – Skapa och ta bort webbplatser <br> – Hantera webbplatssamlingar och globala SharePoint-inställningar   |
|Teams-tjänstadministratör    |   Tilldela Teams-tjänstadministratörsrollen till användare som behöver åtkomst till och behöver hantera administrationscentret för Teams. <br><br>Teams-tjänstadministratörer kan också: <br> – Hantera möten <br> – Hantera konferensbryggor <br> – Hantera alla organisationsomfattande inställningar, inklusive inställningar för federation, team-uppgradering och team-klienter   |
|Användaradministratör     |    Tilldela rollen som användaradministratör till användare som behöver göra följande för alla användare: <br> – Lägga till användare och grupper <br> – Tilldela licenser <br> – Hantera de flesta användaregenskaper <br> – Skapa och hantera användarvyer <br> – Uppdatera giltighetsprinciper för lösenord <br> – Hantera tjänsteförfrågningar <br> – Övervaka tjänstens status <br><br>  Användaradministratören kan också utföra följande åtgärder för användare som inte är administratörer och för användare som har tilldelats följande roller: katalogläsare, gästinbjudare, supportadministratör, meddelandecenter-administratör, rapportläsare: <br> – Hantera användarnamn<br> – Ta bort och återställa användare<br> – Återställa lösenord <br> – Tvinga att användare loggar ut <br> – Uppdatera enhetsnycklar (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Delegerad administration för Microsoft-partners

Om du arbetar med en Microsoft-partner kan du tilldela dem administratörsroller. De kan i sin tur tilldela användare i ditt företag, eller i sitt företag, administratörsroller. Det kanske du vill göra om de till exempel konfigurerar och hanterar din onlineorganisation åt dig.
  
Ett partnerföretag kan tilldela följande roller: 
  
- **Administratörsagent** Behörigheter som en global administratör, förutom behörighet att hantera flerfaktorautentisering via partnercentret.

- **Supportagent** Behörigheter som en supportadministratör.

För att partnerföretaget ska kunna tilldela de här rollerna till användare måste du lägga till partnern som delegerad administratör i kontot. Initiativet till en sådan här process tas av en auktoriserad partner. Partnern skickar ett e-postmeddelande till dig med frågan om du vill ge dem behörighet att fungera som delegerad administratör. Anvisningar finns i [Auktorisera eller ta bort partnerrelationer](../misc/add-partner.md).
  
## <a name="related-content"></a>Relaterat innehåll

[Tilldela administratörsroller](assign-admin-roles.md) (artikel)\
[Azure AD-roller i administrationscentret för Microsoft 365](azure-ad-roles-in-the-mac.md) (artikel)\
[Aktivitetsrapporter i Administrationscentret för Microsoft 365](../activity-reports/activity-reports.md) (artikel)\
[Administratörsrollen i Exchange Online](about-exchange-online-admin-role.md) (artikel)
