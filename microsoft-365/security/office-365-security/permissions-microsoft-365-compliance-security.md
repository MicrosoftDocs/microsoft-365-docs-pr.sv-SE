---
title: Aviseringsprinciper i säkerhets- och efterlevnadscenter för Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Med hjälp av Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter kan du hantera behörigheter centralt för alla uppgifter som är relaterade till säkerhet och efterlevnad.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ad17933592b860fb81e469fd55a454c90b71320
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845762"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Behörigheter i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Din organisation behöver hantera säkerhets- och efterlevnadsscenarier som omfattar alla Microsoft 365-tjänster. Du behöver också flexibiliteten att ge rätt administratörsbehörigheter till rätt personer i din organisations IT-grupp. Med hjälp av Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter kan du hantera behörigheter centralt för alla uppgifter som är relaterade till säkerhet och efterlevnad.

När den globala administratören har tilldelat dessa administratörsroller får administratörerna tillgång till funktioner och data som omfattar alla tjänster i Microsoft 365, t. ex. säkerhetscentret i Microsoft 365, efterlevnadscentret i Microsoft 365, Azure, Office 365 och Enterprise Mobility + Security.

## <a name="what-the-microsoft-365-roles-are"></a>Det här innebär Microsoft 365-rollerna

De roller som visas i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365 är Azure Active Directory-roller. Rollerna är utformade för att passa ihop med jobbfunktioner i din organisations IT-grupp, vilket gör det enkelt att ge en person alla de behörigheter som krävs för att få jobbet gjort.

****

|Roll|Beskrivning|
|---|---|
|**Global administratör**|Användare som har den här rollen har tillgång till alla administrativa funktioner i alla Microsoft 365-tjänster. Det är bara globala administratörer som kan tilldela andra administratörsroller.|
|**Administratör för efterlevnadsdata**|Användare som har den här rollen kan hålla reda på organisationens data i Microsoft 365, se till att de skyddas och få insikter om problem för att minska riskerna.|
|**Efterlevnadsadministratör**|Användare som har den här rollen kan hjälpa din organisation att efterleva föreskrifter, hantera eDiscovery-ärenden och underhålla datastyrningsprinciper för Microsoft 365-platser, identiteter och appar.|
|**Säkerhetsoperatör**|Användare som har den här rollen kan visa, undersöka och reagera på aktiva hot för dina Microsoft 365-användare, enheter och innehåll.|
|**Säkerhetsläsare**|Användare som har den här rollen kan visa och undersöka aktiva hot mot dina Microsoft 365-användare, enheter och innehåll, men (i motsats till säkerhetsoperatören) har de inte behörighet att svara genom att vidta åtgärder.|
|**Säkerhetsadministratör**|Användare som har den här rollen kan styra organisationens allmänna säkerhet genom att hantera säkerhetsprinciper, granska säkerhetsanalyser och -rapporter i Microsoft 365-produkter och hålla sig uppdaterade om hotet.|
|

## <a name="what-the-microsoft-365-roles-have-access-to"></a>Det här har Microsoft 365-rollerna tillgång till

Här är de tillgängliga rollerna och vad personer som tilldelats rollerna kan göra.

### <a name="global-administrator"></a>Global administratör

Användare som har den här rollen har tillgång till alla administrativa funktioner i Azure Active Directory, liksom tjänster som använder Azure Active Directory-identiteter som säkerhetscentret i Microsoft 365, efterlevnadscentret i Microsoft 365, Exchange Online, SharePoint Online och Skype för företag – Online. Personen som registrerar sig för Azure Active Directory-klienten blir global administratör. Det är bara globala administratörer som kan tilldela andra administratörsroller. Det kan finnas fler än en global administratör i företaget. Globala administratörer kan återställa lösenordet för valfri användare och alla andra administratörer.

### <a name="compliance-administrator"></a>Efterlevnadsadministratör

Användare som har den här rollen har behörighet att hantera efterlevnadsrelaterade funktioner i Microsoft 365 Efterlevnadscenter, Administrationscenter för Microsoft 365, Azure och Säkerhets- och efterlevnadscenter. Användare kan även hantera alla funktioner i administrationscentret för Exchange och Administrationscenter för Teams och Skype för företag och skapa supportärenden för Azure och Microsoft 365.

****

|I den här tjänsten...|Kan efterlevnadsadministratören...|
|---|---|
|[**Efterlevnadscentret i Microsoft 365**](https://compliance.microsoft.com/)|Skydda och hantera organisationens data i Microsoft 365-tjänsterna. <br/><br/> Hantera aviseringar om efterlevnad.|
|[**Compliance Manager**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|Spåra, tilldela och verifiera organisationens aktiviteter för regelefterlevnad.|
|[**Säkerhets- och efterlevnadscenter**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Hantera datastyrning. <br/><br/> Utföra rätts- och dataundersökningar. <br/><br/> Hantera begäran från registrerad person.|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Visa alla Intune-granskningsdata.|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Har skrivskyddad behörighet och kan hantera aviseringar. <br/><br/> Kan skapa och ändra filprinciper och tillåta åtgärder för filstyrning. <br/><br/> Kan visa alla inbyggda rapporter under datahantering.|
|

### <a name="compliance-data-administrator"></a>Administratör för efterlevnadsdata

Användare som har den här rollen har behörighet att skydda och spåra data i efterlevnadscentret i Microsoft 365, Administrationscenter för Microsoft 365 och Azure. Användare kan också hantera alla funktioner i Exchange administratörscenter, Compliance Manager och Teams och Skype for Business administratörscenter och skapa supportbiljetter för Azure och Microsoft 365.

****

|I den här tjänsten...|Kan administratören för efterlevnadsdata...|
|---|---|
|[**Efterlevnadscentret i Microsoft 365**](https://compliance.microsoft.com/)|Skydda och hantera organisationens data i Microsoft 365-tjänsterna. <br/><br/> Hantera aviseringar om efterlevnad. <br/><br/> Hantera känslighetsetiketter|
|[**Compliance Manager**](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager)|Spåra, tilldela och verifiera organisationens aktiviteter för regelefterlevnad.|
|[**Säkerhets- och efterlevnadscenter**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Hantera datastyrning. <br/><br/> Utföra rätts- och dataundersökningar. <br/><br/> Hantera begäran från registrerad person. <br/><br/> Hantera känslighetsetiketter|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control) (kommer snart)|Visa alla Intune-granskningsdata.|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Använda läsbehörigheter för att visa information. <br/>Hantera aviseringar. <br/><br/> Skapa och ändra filprinciper och tillåta åtgärder för filstyrning. <br/><br/> Visa alla inbyggda rapporter under datahantering.|
|

### <a name="security-administrator"></a>Säkerhetsadministratör

Användare som har den här rollen har behörighet att hantera säkerhetsrelaterade funktioner i Microsoft 365 Säkerhetscenter, Azure Active Directory Identity Protection, Azure Information Protection och Säkerhets- och efterlevnadscenter.

****

|I den här tjänsten...|Kan säkerhetsadministratören...|
|---|---|
|[**Microsoft 365 Säkerhetscenter**](https://security.microsoft.com/)|Övervaka säkerhetsrelaterade principer i Microsoft 365-tjänster. <br/><br/>  Hantera säkerhetshot och aviseringar. <br/><br/> Visa rapporter. <br/><br/> Hantera känslighetsetiketter.|
|**Identity Protection Center**|Utföra allt som säkerhetsläsarrollen kan samt utföra alla åtgärder i Identity Protection Center, utom att återställa lösenord.|
|[**Priviligierad identitetshantering**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Utföra allt som säkerhetsläsarrollen kan. <br/><br/> **Kan inte** hantera rolltilldelningar och inställningar för Azure AD.|
|[**Säkerhets- och efterlevnadscenter**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Hantera säkerhetsprinciper. <br/><br/> Visa, undersöka och reagera på säkerhetshot <br/><br/> Visa rapporter. <br/><br/> Hantera känslighetsetiketter.|
|**Microsoft Defender for Identity**|Övervaka och svara på misstänkt säkerhetsaktivitet.|
|**Microsoft Defender för Endpoint och EDR**|Tilldela roller. <br/><br/> Hantera datorgrupper. <br/><br/> Konfigurera identifiering av slutpunktshot och automatisk reparation. <br/><br/> Visa, undersöka och reagera på aviseringar.|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Visar information om användare, enheter, registrering, konfiguration och program. <br/><br/> **Kan inte** göra ändringar i Intune.|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Lägga till administratörer, lägga till principer och inställningar, ladda upp loggar och utföra styrningsåtgärder.|
|[**Azure Defender** _](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles) (kommer snart)|Visa säkerhetsprinciper, visa säkerhetstillstånd, redigera säkerhetsprinciper, visa aviseringar och rekommendationer, stänga av varningar och rekommendationer.|
|[_ *Office 365-tjänststatus**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Visa status för Office 365-tjänster.|
|

### <a name="security-operator"></a>Säkerhetsoperatör

Användare som har den här rollen kan hantera aviseringar och har global skrivskyddad åtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 Säkerhetscenter, Azure Active Directory, Identity Protection, Privileged Identity Management och möjlighet att läsa Azure Active Directory-inloggningsrapporter och granskningsloggar samt i Säkerhets- och efterlevnadscenter.

****

|I den här tjänsten...|Kan säkerhetsoperatören...|
|---|---|
|[**Microsoft 365 Säkerhetscenter**](https://security.microsoft.com/)|Utföra allt som säkerhetsläsarrollen kan. <br/><br/> Visa, undersöka och reagera på säkerhetshot.|
|**Identity Protection Center** (kommer snart)|Utföra allt som säkerhetsläsarrollen kan.|
|[**Priviligierad identitetshantering**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Utföra allt som säkerhetsläsarrollen kan.|
|[**Säkerhets- och efterlevnadscenter**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Utföra allt som säkerhetsläsarrollen kan. <br/><br/> Visa, undersöka och reagera på säkerhetshot|
|**Microsoft Defender för Endpoint och EDR**|Utföra allt som säkerhetsläsarrollen kan. <br/><br/> Visa, undersöka och reagera på aviseringar.|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Visar information om användare, enheter, registrering, konfiguration och program. <br/><br/> **Kan inte** göra ändringar i Intune.|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Utföra allt som säkerhetsläsarrollen kan, plus visa och stänga av varningar.|
|[**Office 365-tjänststatus**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Visa status för Office 365-tjänster.|
|

### <a name="security-reader"></a>Säkerhetsläsare

Användare som har den här rollen har global skrivskyddad åtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 Säkerhetscenter, Azure Active Directory, Identity Protection, Privileged Identity Management och möjlighet att läsa Azure Active Directory-inloggningsrapporter och granskningsloggar samt i Säkerhets- och efterlevnadscenter.

****

|I den här tjänsten...|Kan säkerhetsläsaren...|
|---|---|
|[**Microsoft 365 Säkerhetscenter**](https://security.microsoft.com/)|Visa säkerhetsrelaterade principer i Microsoft 365-tjänster. <br/><br/> Visa säkerhetshot och aviseringar. <br/><br/> Visa rapporter.|
|**Identity Protection Center**|Läsa alla säkerhetsrapporter och inställningsinformation för säkerhetsfunktioner: skydd mot skräppost, kryptering, skydd mot dataförlust (DLP), skydd mot skadlig programvara, Defender för Office 365, skydd mot nätfiske och regler för e-postflöde (kallas även för transportregler).|
|[**Priviligierad identitetshantering**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Använda skrivskyddad åtkomst för att visa all information som finns i Azure AD PIM: principer och rapporter för Azure AD-resurstilldelningar, säkerhetsgranskningar och (i framtiden) principdata och -rapporter för andra scenarier än rolltilldelning i Azure AD. <br/><br/> **Kan inte** registrera sig för Azure AD PIM eller göra ändringar i tjänsten. I PIM-portalen eller via PowerShell kan någon med den här rollen aktivera ytterligare roller (till exempel global administratör eller administratör för privilegierad roll), om användaren är behörig.|
|[**Säkerhets- och efterlevnadscenter**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Visa säkerhetsprinciper. <br/><br/> Visa och undersöka säkerhetshot. <br/><br/> Visa rapporter.|
|**Microsoft Defender för Endpoint och EDR**|Visa och undersöka varningar.|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Visar information om användare, enheter, registrering, konfiguration och program. <br/><br/> **Kan inte** göra ändringar i Intune.|
|[**Cloud App Security**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Använda läsbehörigheter för att visa information. <br/><br/> Hantera aviseringar.|
|[**Azure Defender** _](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles)|Visa rekommendationer och aviseringar. <br/><br/> Visa säkerhetsprinciper. <br/><br/> Visa säkerhets tillstånd, men kan inte göra ändringar.|
|[_ *Office 365-tjänststatus**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Visa status för Office 365-tjänster.|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Globala administratörer kan hantera roller i Azure Active Directory

I efterlevnadscentret i Microsoft 365 och Microsoft 365 Säkerhetscenter kan du se rollens uppgifter när du väljer en roll. För att kunna hantera de uppgifterna måste du dock gå till Azure Active Directory.

Mer information finns i [Visa och tilldela administratörsroller i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Länk för att hantera behörigheter i Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Hantera roller i en tjänst istället för i Azure Active Directory

De roller som visas i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365 visas också i de tjänster där de har behörigheter. Du kan till exempel se de här rollerna i Säkerhets- och efterlevnadscenter.

![Roller i Säkerhets- och efterlevnadscenter](../../media/m365-roles-in-o365-scc.png)

### <a name="breaking-inheritance"></a>Bryta arv

När du hanterar de här rollerna i Azure Active Directory är det viktigt att du förstår att du gör det centralt för **alla** Microsoft 365-tjänster. När du hanterar en roll i en specifik tjänst, till exempel Säkerhets- och efterlevnadscenter, hanterar du **enbart** rollen för den angivna tjänsten. Uppgifter och behörigheter för en roll i en tjänst åsidosätter alla behörigheter som har tilldelats Azure Active Directory-rollen.

Det här kan vara användbart t. ex. om en person har tilldelats rollen som säkerhetsadministratör men saknar behörighet att hantera händelser. Du kan också använda behörigheterna i Microsoft Defender för Endpoint för att ge dem särskild behörighet för hantering av händelser i den aktuella tjänsten.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Här hittar du rollinformation för respektive Microsoft 365-tjänst

Genom att tilldela en användare någon av rollerna som efterlevnads- eller säkerhetsadministratör i Microsoft 365, ger du användaren behörighet till en uppsättning Microsoft 365-tjänster. Använd länkarna nedan om du vill ha mer information om de olika behörigheterna för en roll i respektive tjänst.

****

|Microsoft 365-tjänsten|Rollinformation|
|---|---|
|Administratörsroller i Office 365 och Microsoft 365 Business-abonnemang|[Administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)|
|Azure Active Directory (Azure AD) och Azure AD-identitetsskydd|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Rollgrupper för Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Efterlevnadshanteraren|[Compliance Manager](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager-setup#set-user-permissions-and-assign-roles)|
|Exchange Online|[Rollbaserad åtkomstkontroll i Exchange](https://docs.microsoft.com/exchange/understanding-role-based-access-control-exchange-2013-help)|
|Intune|[Rollbaserad åtkomstkontroll i Intune](https://docs.microsoft.com/intune/role-based-access-control)|
|Hanterat skrivbord|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Rollbaserad åtkomstkontroll](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|Säkerhets- och efterlevnadscenter|[Administratörsroller i Microsoft 365](permissions-in-the-security-and-compliance-center.md)|
|Priviligierad identitetshantering|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Säkerhetspoäng|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <br/><br/> [Om SharePoint-administratörsrollen i Office 365](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype för företag|[Administratörsroller för Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender för Endpoint|[Rollbaserad åtkomstkontroll för Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="what-is-coming-soon"></a>Det här kommer snart

Vi arbetar fortfarande med behörigheter i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365. Till exempel arbetar vi just nu med support för att:

- Hantera roller i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365, i stället för att gå till Azure Active Directory.

- Anpassa roller genom att lägga till eller ta bort vissa behörigheter.

- Skapa anpassade roller med behörigheter som du väljer.
