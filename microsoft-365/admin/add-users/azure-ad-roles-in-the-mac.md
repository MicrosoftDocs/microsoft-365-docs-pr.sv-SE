---
title: Azure Active Directory-roller i administrationscentret för Microsoft 365
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
description: Hantera dessa Azure-administratörsroller i administrationscentret för Microsoft 365.
ms.openlocfilehash: 7a4e28667bc16d6619fe87451cd48ea77d89c81d
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126111"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Azure Active Directory-roller i administrationscentret för Microsoft 365

I administrationscentret för Microsoft 365 kan du hantera över 30 Azure AD-roller. Dessa roller är bara en underuppsättning av rollerna som finns tillgängliga i Azure-portalen. Om du har ett stort företag kan det finnas roller i Microsoft Azure-portalen som uppfyller organisationens behov. Letar du efter de detaljerade rollbeskrivningarna för Azure Active Directory? Ta en titt på [Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

En användare som har tilldelats en administratörsroll får samma behörigheter till alla molntjänster som organisationen prenumererar på, oavsett om du tilldelar rollen i administrationscentret för Microsoft 365, i Azure-portalen eller med Azure AD-modulen för Windows PowerShell.

::: moniker range="o365-worldwide"

I Administrationscenter för Microsoft 365 går du till **Roller** och väljer sedan en roll för att öppna informationsfönstret. Välj fliken **Behörigheter** om du vill visa en detaljerad lista över vilka behörigheter som administratörer som tilldelats rollen har. Välj fliken **Tilldelad** eller **Tilldelade administratörer** om du vill lägga till användare i roller. Mer information om hur du tilldelar roller i Administrationscenter för Microsoft 365 finns i [Tilldela administratörsroller](assign-admin-roles.md).

::: moniker-end

## <a name="all-azure-ad-roles"></a>Alla Azure Active Directory-roller

Här följer en lista över alla tillgängliga administratörsroller i administrationscentret för Microsoft 365. Letar du efter detaljerade rollbeskrivningar för Microsoft 365-administratörsrollerna? Se [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

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
|Insights-administratör     | Hanterar alla aspekter av programmet Microsoft 365 Insights, läser Azure Active Directory-information och kan övervaka tjänststatus och skapa och hantera tjänstförfrågningar.      |
|Företagsadministratör för Insights     | Läsa rapporter och insikter i programmet Microsoft 365 Insights.      |
|Intune-administratör     | Fullständig åtkomst till Intune, hanterar användare och enheter för att associera principer, skapar och hanterar grupper.      |
|Kaizala-administratör     |    Full tillgång till alla Kaizala-hanteringsfunktioner och data, hanterar tjänsteförfrågningar.     |
|Licensadministratör     |     Tilldelar och tar bort licenser från användare och redigerar deras användningsplatser.    |
|Sekretessläsare i meddelandecenter     |    Åtkomst till datasekretessmeddelanden i meddelandecenter, hämtar e-postmeddelanden.     |
|Meddelandecenter-administratör     | Läser och delar vanliga meddelanden i meddelandecenter, hämtar e-postsammandrag varje vecka, har skrivskyddad åtkomst till användare, grupper, domäner och prenumerationer.     |
|Administratör för Office-program    |   Hanterar molnbaserade principer för Office och nyhetsinnehållet som användarna ser i sina Office-program.   |
|Lösenordsadministratör    |   Återställ lösenord för användare som inte är administratörer eller medlemmar i följande roller: Katalogläsare, gästinbjudare, lösenordsadministratör. Denna roll kan inte ge möjlighet att hantera tjänsteförfrågningar eller övervaka tjänsthälsa.   |
|Power BI-administratör    |   Fullständig åtkomst till Power BI-hanteringsuppgifter, hanterar tjänsteförfrågningar och övervakar tjänstens status.   |
|Administratör för Power Platform     |    Full tillgång till Microsoft Dynamics 365, PowerApps, principer för dataförlustskydd och Microsoft Flow.     |
|Administratör för privilegierad roll     |    Hanterar rolltilldelningar och alla funktioner för åtkomstbehörighet för privilegierad identitetshantering.     |
|Autentiseringsadministratör med privilegier     |    Återställer lösenord, uppdaterar autentiseringsuppgifter andra än lösenord, tvingar användare att logga ut och övervakar tjänstens status samt hanterar tjänstförfrågningar.     |
|Rapportläsare     |   Läser användningsrapporter från rapportkontrollpanelen, PowerBI-innehållspaketet, inloggningsrapporter och rapporterings-API för Microsoft Graph.      |
|Sökadministratör     |    Full tillgång till Microsoft Search, tilldelar rollerna sökadministratör och sökredigerare, hanterar redaktionellt innehåll, övervakar tjänstens status och skapar tjänsteförfrågningar.     |
|Sökredigerare     |    Kan bara skapa, redigera och ta bort innehåll för Microsoft Search som bokmärken, frågor och svar samt platser.     |
|Säkerhetsadministratör     |    Styr organisationens säkerhet, hanterar säkerhetsprinciper, granskar säkerhetsanalyser och rapporter samt övervakar hotbilden.     |
|Säkerhetsoperatör     |    Undersöker och svarar på säkerhetsvarningar, hanterar funktioner i Identity Protection Center, övervakar tjänstens status.     |
|Säkerhetsläsare     |    Skrivskyddad åtkomst till säkerhetsfunktioner, inloggningsrapporter och granskningsloggar.     |
|Supportadministratör för tjänst     |    Skapar tjänsteförfrågningar för Azure, Microsoft 365 och Office 365 samt övervakar tjänstens status.     |
|SharePoint-administratör     |    Full tillgång till SharePoint Online, hanterar Microsoft 365-grupper, hanterar tjänsteförfrågningar och övervakar tjänstens status.     |
|Skype för företag-administratör     | Full tillgång till alla Teams- och Skype-funktioner, Skype-användarattribut, hanterar tjänsteförfrågningar och övervakar tjänstens status.      |
|Teams-administratör     |    Full tillgång till Teams- och Skype-administrationscentret, hanterar Microsoft 365-grupper och tjänsteförfrågningar samt övervakar tjänstens status.     |
|Teams-kommunikationshanterare     |    Tilldelar telefonnummer, skapar och hanterar röst- och mötesprinciper samt läser samtalsanalyser.     |
|Supporttekniker för Teams-kommunikation     |    Läser information om samtal för alla samtalsdeltagare för att felsöka kommunikationsproblem.     |
|Supportspecialist för Teams-kommunikation     |    Läser information om användarsamtal för specifika användare för att felsöka kommunikationsproblem.|
|Användaradministratör     |   Återställer användarlösenord, skapar och hanterar användare och grupper samt filter, hanterar tjänsteförfrågningar och övervakar tjänstens status.|

## <a name="delegated-administration-for-microsoft-partners"></a>Delegerad administration för Microsoft-partners

Om du arbetar med en Microsoft-partner kan du tilldela dem administratörsroller. De kan i sin tur tilldela användare i ditt företag – eller i sitt företag – administratörsroller. Det kanske du vill göra om de till exempel konfigurerar och hanterar din onlineorganisation åt dig.
  
Ett partnerföretag kan tilldela följande roller: 

- Fullständig administrering, som har samma behörigheter som en global administratör, förutom behörighet att hantera flerfaktorautentisering via partnercentret.

- Begränsad administration, som har samma behörigheter som en supportadministratör.

För att partnerföretaget ska kunna tilldela de här rollerna till användare måste du lägga till partnern som delegerad administratör i kontot. Initiativet till en sådan här process tas av en auktoriserad partner. Partnern skickar ett e-postmeddelande till dig med frågan om du vill ge dem behörighet att fungera som delegerad administratör. Anvisningar finns i [Auktorisera eller ta bort partnerrelationer](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Relaterade artiklar

[Om administratörsroller i Microsoft 365](about-admin-roles.md)

[Tilldela administratörsroller](assign-admin-roles.md)
  
[Aktivitetsrapporter i administrationscentret för Microsoft 365](../activity-reports/activity-reports.md)