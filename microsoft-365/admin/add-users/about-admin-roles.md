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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Administratörsroller mappar till affärsfunktioner och ger behörighet att utföra särskilda uppgifter i administrationscentret. Tjänstadministratören öppnar till exempel supportbegäranden hos Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 446af9ad49649487f4df1982613f8e84fdf39910
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857197"
---
# <a name="about-admin-roles"></a>Om administratörsroller

Din prenumeration innehåller en uppsättning administratörsroller som du kan tilldela användare i organisationen. Varje administratörsroll mappar till vanliga affärsfunktioner och ger personerna i organisationen behörighet att utföra särskilda uppgifter i administrationscentret. Mer information finns i [Tilldela administratörsroller](assign-admin-roles.md)

> [!TIP] 
> Letar du efter de detaljerade rollbeskrivningarna? Ta en titt på [Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## <a name="things-to-consider"></a>Saker att tänka på...

Eftersom administratörer har tillgång till känsliga data och filer rekommenderar vi att du följer dessa riktlinjer för att skydda organisationens data.

| Rekommendation                  | Varför är det viktigt?                 |
| :------------------- | :------------------- |
| Ha 2 till 4 globala administratörer  | Eftersom det bara är en global administratör som kan återställa lösenordet för en annan global administratör så rekommenderar vi att du har minst 2 globala administratörer i organisationen i händelse av kontoutelåsning. Men globala administratörer har nästan obegränsad åtkomst till organisationens inställningar och de flesta data, därför rekommenderar vi att du inte har fler än fyra globala administratörer eftersom det är ett säkerhetshot. |
| Tilldela *begränsade* roller     | Genom att tilldela *begränsade* roller får administratörerna bara den behörighet som behövs för att få jobbet gjort. Om du till exempel vill att någon ska återställa lösenord för anställda bör du inte tilldela den obegränsade rollen som global administratör, i stället kan du tilldela en begränsad roll som lösenordsadministratör eller supportadministratör. På så sätt skyddar du dina data.                 |
| Konfigurera multifaktorautentisering för administratörer                  |    Det är en bra idé att kräva MFA för alla användare, men administratörer i synnerhet bör använda MFA för att logga in. MFA gör att användarna måste använda ytterligare en identifieringsmetod för att verifiera sin identitet. Administratörer kan ha tillgång till stora mängder kund- och personaldata och om du använder MFA är själva lösenordet oanvändbart utan en andra verifiering i händelse av att administratörslösenordet äventyras.  <br><br>När du aktiverar MFA måste användaren ange en alternativ e-postadress och ett telefonnummer för kontoåterställning nästa gång användaren loggar in.  <br> [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)          |

  
## <a name="some-roles-are-missing-from-active-users--manage-admin-roles-where-did-they-go"></a>Vissa roller saknas i Aktiva användare > Hantera administratörsroller. Var finns de?
Som standard visar vi först de roller som de flesta organisationer använder. Om du inte hittar någon roll går du till slutet av listan och väljer **Visa fler roller**.

## <a name="how-can-i-tell-which-permissions-are-assigned-to-me"></a>Hur ser jag vilka behörigheter som jag tilldelats?
Om du får ett meddelande i administrationscentret om att du inte har behörighet att redigera inställningar eller sidor beror det på att du har tilldelats en roll som inte har den behörigheten.

## <a name="what-about-the-azure-active-directory-roles"></a>Vad gäller för Azure Active Directory-roller? 

Azure-portalen har fler roller än de som finns tillgängliga i administrationscentret för Microsoft 365. Om du har ett stort företag kan det finnas roller i Azure-portalen som uppfyller organisationens behov.

En lista och beskrivning av alla Azure Active Directory-roller finns i [Behörigheter för administratörsroller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

En användare som har tilldelats en administratörsroll får samma behörigheter till alla molntjänster som organisationen prenumererar på, oavsett om du tilldelar rollen i administrationscentret för Microsoft 365, i Azure-portalen eller med Azure AD-modulen för Windows PowerShell.
  
## <a name="roles-available-in-the-microsoft-365-admin-center"></a>Tillgängliga roller i administrationscentret för Microsoft 365

I administrationscentret för Microsoft 365 kan du hantera över 30 Azure AD-roller. Dessa roller är bara en underuppsättning av rollerna som finns tillgängliga i Azure-portalen.

::: moniker range="o365-worldwide"

I administrationscentret kan du gå till **Roller** och välj sedan en roll för att öppna informationsfönstret. Välj fliken **Behörigheter** om du vill visa en detaljerad lista över vilka behörigheter som administratörer som tilldelats rollen har. 

::: moniker-end

Du behöver antagligen bara tilldela följande roller i organisationen. Om du letar efter detaljerad information, inklusive cmdlets som är kopplade till en roll, kan du läsa [Behörigheter för administratörsroller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

|Administratörsroll     |Vem ska ha tilldelas denna roll?  |
|---------|---------|
|Exchange-administratör     |   Tilldela rollen som Exchange-administratör till användare som behöver visa och hantera postlådor, Office 365-grupper och Exchange Online som tillhör din användare. <br><br> Exchange-administratörer kan även:<br> – Återskapa borttagna objekt i en användares postlåda <br> – Konfigurera ombud av typerna "Skicka som" och "Skicka för" <br>  |
|Global administratör     |   Tilldela rollen som global administratör till användare som behöver global åtkomst till de flesta hanteringsfunktioner och data i Microsoft Online Services. <br><br> Att ge för många användare global åtkomst är en säkerhetsrisk och vi rekommenderar att du har mellan två och fyra globala administratörer. <br><br> Det är bara globala administratörer som kan:<br> – Återställa lösenord för alla användare <br> – Lägga till och hantera domäner <br> <br> **Obs!** Den person som har registrerat sig för Microsoft Online Services blir automatiskt global administratör. |
|Global läsare    |   Tilldela rollen global läsare till användare som behöver visa administratörsfunktioner och -inställningar i administrationscenter som den globala administratören kan visa. Den globala läsaradministratören kan inte redigera några inställningar.   |
|Grupper-administratör     |   Tilldelar gruppadministratörsrollen till användare som behöver hantera alla gruppinställningar i olika administrationscenter, inklusive administrationscentret för Microsoft 365 och Azure Active Directory-portalen. <br><br> Grupper-administratörer kan:<br> – Skapa, redigera, ta bort och återställa Office 365 Grupper <br> – Skapa och uppdatera skapande, upphörande och namngivningsprinciper för grupper <br> – Skapa, redigera, ta bort och återställa Azure Active Directory-säkerhetsgrupper| 
|Supportadministratör     |   Tilldela rollen som supportadministratör till användare som behöver göra följande:<br> – Återställa lösenord <br> – Tvinga att användare loggar ut <br> – Hantera tjänsteförfrågningar <br> – Övervaka tjänstens status <br> <br> **Obs**! Supportadministratören kan bara hjälpa användare som inte är administratörer och användare som tilldelats följande roller: katalogläsare, gästinbjudare, supportadministratör, meddelandecenter-administratör och rapportläsare.      |
|Administratör för Office-program    |   Tilldela rollen som administratör för Office-program till användare som behöver göra följande: <br> – Använda tjänsten för molnprinciper i Office för att skapa och hantera molnbaserade principer för Office <br> – Skapa och hantera tjänsteförfrågningar <br> – Hantera nyhetsinnehållet som användarna ser i sina Office-program   <br> – Övervaka tjänstens status  |
|Tjänstadministratör    |   Tilldela tjänstadministratörsrollen som en ytterligare roll för administratörer och användare vars roll inte inkluderar följande, men som ändå måste göra följande: <br> – Öppna och hantera tjänsteförfrågningar <br> – Visa och dela inlägg från meddelandecenter   |
|SharePoint-administratör    |   Tilldela SharePoint-administratörsrollen till användare som behöver åtkomst till och behöver hantera administrationscentret för SharePoint Online. <br><br>SharePoint-administratörer kan även: <br> – Skapa och ta bort webbplatser <br> – Hantera webbplatssamlingar och globala SharePoint-inställningar   |
|Teams-tjänstadministratör    |   Tilldela Teams-tjänstadministratörsrollen till användare som behöver åtkomst till och behöver hantera administrationscentret för Teams. <br><br>Teams-tjänstadministratörer kan också: <br> – Hantera möten <br> – Hantera konferensbryggor <br> – Hantera alla organisationsomfattande inställningar, inklusive inställningar för federation, team-uppgradering och team-klienter   |
|Användaradministratör     |    Tilldela rollen som användaradministratör till användare som behöver göra följande för alla användare: <br> – Lägga till användare och grupper <br> – Tilldela licenser <br> – Hantera de flesta användaregenskaper <br> – Skapa och hantera användarvyer <br> – Uppdatera giltighetsprinciper för lösenord <br> – Hantera tjänsteförfrågningar <br> – Övervaka tjänstens status <br><br>  Användaradministratören kan också utföra följande åtgärder för användare som inte är administratörer och för användare som har tilldelats följande roller: katalogläsare, gästinbjudare, supportadministratör, meddelandecenter-administratör, rapportläsare: <br> – Hantera användarnamn<br> – Ta bort och återställa användare<br> – Återställa lösenord <br> – Tvinga att användare loggar ut <br> – Uppdatera enhetsnycklar (FIDO)   |

### <a name="all-roles"></a>Alla roller

 Här följer en lista över alla tillgängliga administratörsroller i administrationscentret för Microsoft 365.

|Administratörsroll     |Beskrivning  |
|---------|---------|
|Programadministratör     |    Full tillgång till företagsprogram, programregistreringar och inställningar för proxyinställningar för program.     |
|Programutvecklare     |    Skapa programregistreringar och bevilja appåtkomst för egen räkning.     |
|Autentiseringsadministratör     |    Kan begära att användare registrerar om autentisering för användaruppgifter utan lösenord, t.ex. MFA.     |
|Azure Information Protection-administratör     |   Hanterar etiketter för Azure information Protection-principen, hanterar skyddsmallar och aktiverar skydd.       |
|Faktureringsadministratör     |    Gör inköp, hanterar prenumerationer, hanterar tjänsteförfrågningar och övervakar tjänstens status.     |
|Molnprogramsadministratör     | Full tillgång till företagsprogram och programregistreringar. Ingen programproxy.     |
|Molnenhetsadministratör     |    Aktiverar, inaktiverar och tar bort enheter samt kan läsa Windows 10 BitLocker-nycklar.     |
|Efterlevnadsadministratör     |    Hanterar regelkrav och eDiscovery-ärenden samt underhåller datastyrning för platser, identiteter och appar.     |
|Efterlevnadsdataadministratör     |    Håller ordning på data, ser till att de skyddas, får information om problem och hjälper till att minska risken.     |
|Administratör för villkorsstyrd åtkomst     |   Hanterar inställningar för villkorsstyrd åtkomst i Azure Active Directory, men inte Exchange ActiveSync-principer för villkorsstyrd åtkomst.      |
|Customer Lockbox-åtkomstgodkännare     |      Hanterar förfrågningar om Customer Lockbox, kan aktivera och inaktivera Customer Lockbox.   |
|Desktop Analytics-administratör     |   Kan komma åt och hantera Desktop-hanteringsverktyg och tjänster.      |
|Dynamics 365-administratör     |  Full tillgång till Microsoft Dynamics 365 online, hanterar tjänsteförfrågningar och övervakar tjänstens status.       |
|Exchange-administratör     |  Full tillgång till Exchange Online, skapar och hanterar grupper, hanterar tjänsteförfrågningar och övervakar tjänstens status.    |
|Administratör för extern identitetsleverantör    |     Konfigurerar identitetsleverantörer för användning med direkt federering.    |
|Global administratör     |    Har obegränsad åtkomst till alla hanteringsfunktioner och de flesta data i alla administrationscenter.     |
|Global läsare     |    Har skrivskyddad åtkomst till alla hanteringsfunktioner och de flesta uppgifter i administrationscenter. En detaljerad beskrivning av behörighet och begränsningar för den här rollen finns i [administratörs behörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Grupper-administratör   |Skapar grupper och hanterar alla Grupper-inställningar i olika administrationscenter.|
|Gästinbjudare     |    Hanterar Azure Active Directory B2B-inbjudningar till gästanvändare.     |
|Supportadministratör     | Återställer lösenord och omautentiseringar för alla icke-administratörer och vissa administratörsroller, hanterar tjänsteförfrågningar och övervakar tjänstens status.      |
|Intune-administratör     | Fullständig åtkomst till Intune, hanterar användare och enheter för att associera principer, skapar och hanterar grupper.      |
|Kaizala-administratör     |    Full tillgång till alla Kaizala-hanteringsfunktioner och data, hanterar tjänsteförfrågningar.     |
|Licensadministratör     |     Tilldelar och tar bort licenser från användare och redigerar deras användningsplatser.    |
|Sekretessläsare i meddelandecenter     |    Åtkomst till datasekretessmeddelanden i meddelandecenter, hämtar e-postmeddelanden.     |
|Meddelandecenter-administratör     | Läser och delar vanliga meddelanden i meddelandecenter, hämtar e-postsammandrag varje vecka, har skrivskyddad åtkomst till användare, grupper, domäner och prenumerationer.     |
|Administratör för Office-program    |   Hanterar molnbaserade principer för Office och nyhetsinnehållet som användarna ser i sina Office-program.   |
|Power BI-administratör    |   Fullständig åtkomst till Power BI-hanteringsuppgifter, hanterar tjänsteförfrågningar och övervakar tjänstens status.   |
|Administratör för Power Platform     |    Full tillgång till Microsoft Dynamics 365, PowerApps, principer för dataförlustskydd och Microsoft Flow.     |
|Administratör för privilegierad roll     |    Hanterar rolltilldelningar och alla funktioner för åtkomstbehörighet för privilegierad identitetshantering.     |
|Rapportläsare     |   Läser användningsrapporter från rapportkontrollpanelen, PowerBI-innehållspaketet, inloggningsrapporter och rapporterings-API för Microsoft Graph.      |
|Sökadministratör     |    Full tillgång till Microsoft Search, tilldelar rollerna sökadministratör och sökredigerare, hanterar redaktionellt innehåll, övervakar tjänstens status och skapar tjänsteförfrågningar.     |
|Sökredigerare     |    Kan bara skapa, redigera och ta bort innehåll för Microsoft Search som bokmärken, frågor och svar samt platser.     |
|Säkerhetsadministratör     |    Styr organisationens säkerhet, hanterar säkerhetsprinciper, granskar säkerhetsanalyser och rapporter samt övervakar hotbilden.     |
|Säkerhetsoperatör     |    Undersöker och svarar på säkerhetsvarningar, hanterar funktioner i Identity Protection Center, övervakar tjänstens status.     |
|Säkerhetsläsare     |    Skrivskyddad åtkomst till säkerhetsfunktioner, inloggningsrapporter och granskningsloggar.     |
|Supportadministratör för tjänst     |    Skapar tjänsteförfrågningar för Azure, Microsoft 365 och Office 365 samt övervakar tjänstens status.     |
|SharePoint-administratör     |    Full tillgång till SharePoint Online, hanterar Office 365-grupper, hanterar tjänsteförfrågningar och övervakar tjänstens status.     |
|Skype för företag-administratör     | Full tillgång till alla Teams- och Skype-funktioner, Skype-användarattribut, hanterar tjänsteförfrågningar och övervakar tjänstens status.      |
|Teams-administratör     |    Full tillgång till Teams- och Skype-administrationscentret, hanterar Office 365-grupper och tjänsteförfrågningar samt övervakar tjänstens status.     |
|Teams-kommunikationshanterare     |    Tilldelar telefonnummer, skapar och hanterar röst- och mötesprinciper samt läser samtalsanalyser.     |
|Supporttekniker för Teams-kommunikation     |    Läser information om samtal för alla samtalsdeltagare för att felsöka kommunikationsproblem.     |
|Supportspecialist för Teams-kommunikation     |    Läser information om användarsamtal för specifika användare för att felsöka kommunikationsproblem.|
|Användaradministratör     |   Återställer användarlösenord, skapar och hanterar användare och grupper samt filter, hanterar tjänsteförfrågningar och övervakar tjänstens status.|

## <a name="delegated-administration-for-microsoft-partners"></a>Delegerad administration för Microsoft-partners

Om du arbetar med en Microsoft-partner kan du tilldela dem administratörsroller. De kan i sin tur tilldela användare i ditt företag – eller i sitt företag – administratörsroller. Det kanske du vill göra om de till exempel konfigurerar och hanterar din onlineorganisation åt dig.
  
Ett partnerföretag kan tilldela följande roller: 
  
- Fullständig administrering, som har samma behörigheter som en global administratör, förutom behörighet att hantera flerfaktorautentisering via partnercentret.
    
- Begränsad administration, som har samma behörigheter som en supportadministratör.

För att partnerföretaget ska kunna tilldela de här rollerna till användare måste du lägga till partnern som delegerad administratör i kontot. Initiativet till en sådan här process tas av en auktoriserad partner. Partnern skickar ett e-postmeddelande till dig med frågan om du vill ge dem behörighet att fungera som delegerad administratör. Anvisningar finns i [Auktorisera eller ta bort partnerrelationer](https://support.office.com/article/201ccb3b-6011-4bf1-a6b2-84e7cc1ee2d0.aspx).
  
## <a name="related-articles"></a>Relaterade artiklar

[Tilldela administratörsroller](assign-admin-roles.md)
  
[Aktivitetsrapporter i administrationscentret för Microsoft 365](../activity-reports/activity-reports.md)
