---
title: Behörigheter i Microsoft 365 Efterlevnadscenter och Microsoft 365 Säkerhetscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Med hjälp av Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter kan du hantera behörigheter centralt för alla uppgifter som är relaterade till säkerhet och efterlevnad.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc2808ffe5d0acd3a5c3c3a6252503ee5e2cf94e
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730990"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Behörigheter i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Din organisation behöver hantera scenarier för efterlevnad och säkerhet som sträcker sig över alla Microsoft 365-tjänster. Du behöver också flexibiliteten att ge rätt administratörsbehörigheter till rätt personer i din organisations IT-grupp. Med hjälp av Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter kan du hantera behörigheter centralt för alla uppgifter som är relaterade till säkerhet och efterlevnad.

När en global administratör lägger till användare i dessa administratörsroller kommer dessa administratörer att ha tillgång till funktioner och data som spänner över alla tjänster i Microsoft 365, till exempel Microsoft 365 säkerhetscenter, Microsoft 365 efterlevnadscenter, Azure, Office 365 och Enterprise Mobility + Säkerhet.

## <a name="what-the-microsoft-365-roles-are"></a>Det här innebär Microsoft 365-rollerna

De roller som visas i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365 är Azure Active Directory-roller. Rollerna är utformade för att passa ihop med jobbfunktioner i din organisations IT-grupp, vilket gör det enkelt att ge en person alla de behörigheter som krävs för att få jobbet gjort.

****

|Roll|Beskrivning|
|---|---|
|**Global administratör**|Användare som har den här rollen har tillgång till alla administrativa funktioner i alla Microsoft 365-tjänster. Det är bara globala administratörer som kan tilldela andra administratörsroller. Mer information finns i [Global administratör / företagsadministratör](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administratör för efterlevnadsdata**|Användare som har den här rollen kan hålla reda på organisationens data i Microsoft 365, se till att de skyddas och få insikter om problem för att minska riskerna. Mer information finns i [Administratör för efterlevnadsdata](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Efterlevnadsadministratör**|Användare som har den här rollen kan hjälpa din organisation att efterleva föreskrifter, hantera eDiscovery-ärenden och underhålla datastyrningsprinciper för Microsoft 365-platser, identiteter och appar. Mer information finns i[ Efterlevnadsadministratör](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Säkerhetsoperatör**|Användare som har den här rollen kan visa, undersöka och reagera på aktiva hot för dina Microsoft 365-användare, enheter och innehåll. Mer information finns i [säkerhetsoperatören](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Säkerhetsläsare**|Användare som har den här rollen kan visa och undersöka aktiva hot mot dina Microsoft 365-användare, enheter och innehåll, men (i motsats till säkerhetsoperatören) har de inte behörighet att svara genom att vidta åtgärder. Mer information finns i [Säkerhetsläsare](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Säkerhetsadministratör**|Användare som har den här rollen kan styra organisationens allmänna säkerhet genom att hantera säkerhetsprinciper, granska säkerhetsanalyser och -rapporter i Microsoft 365-produkter och hålla sig uppdaterade om hotet. Mer information finns i [Säkerhetsadministratör](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Global läsare**|Den skrivskyddade versionen av rollen **Global administratör**. Visa alla inställningar och administrativ information i Microsoft 365. Mer information finns i[ Global läsare](/azure/active-directory/roles/permissions-reference#global-reader).|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Globala administratörer kan hantera roller i Azure Active Directory

I efterlevnadscentret i Microsoft 365 och Microsoft 365 Säkerhetscenter kan du se rollens uppgifter när du väljer en roll. För att kunna hantera de uppgifterna måste du dock gå till Azure Active Directory.

Mer information finns i [Visa och tilldela administratörsroller i Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Länk för att hantera behörigheter i Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Hantera roller i en tjänst istället för i Azure Active Directory

De roller som visas i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365 visas också i de tjänster där de har behörigheter. Du kan till exempel se de här rollerna i Säkerhets- och efterlevnadscenter.

![Roller i Säkerhets- och efterlevnadscenter](../../media/m365-roles-in-o365-scc.png)

Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

### <a name="breaking-inheritance"></a>Bryta arv

När du hanterar de här rollerna i Azure Active Directory är det viktigt att du förstår att du gör det centralt för **alla** Microsoft 365-tjänster. När du hanterar en roll i en specifik tjänst, till exempel Säkerhets- och efterlevnadscenter, hanterar du **enbart** rollen för den angivna tjänsten. Uppgifter och behörigheter för en roll i en tjänst åsidosätter alla behörigheter som har tilldelats Azure Active Directory-rollen.

Det här kan vara användbart. Det här kan vara användbart t. ex. om en person har tilldelats rollen som säkerhetsadministratör men saknar behörighet att hantera händelser. Du kan också använda behörigheterna i Microsoft Defender för Endpoint för att ge dem särskild behörighet för hantering av händelser i den aktuella tjänsten.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Här hittar du rollinformation för respektive Microsoft 365-tjänst

Genom att tilldela en användare någon av rollerna som efterlevnads- eller säkerhetsadministratör i Microsoft 365, ger du användaren behörighet till en uppsättning Microsoft 365-tjänster. Använd länkarna nedan om du vill ha mer information om de olika behörigheterna för en roll i respektive tjänst.

****

|Microsoft 365-tjänsten|Rollinformation|
|---|---|
|Administratörsroller i Office 365 och Microsoft 365 Business-abonnemang|[Administratörsroller i Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Azure Active Directory (Azure AD) och Azure AD-identitetsskydd|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Rollgrupper för Microsoft Defender](/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Efterlevnadshanteraren|[Compliance Manager](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Rollbaserad åtkomstkontroll i Exchange](/exchange/permissions-exo/permissions-exo)|
|Intune|[Rollbaserad åtkomstkontroll i Intune](/intune/role-based-access-control)|
|Hanterat skrivbord|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Rollbaserad åtkomstkontroll](/cloud-app-security/manage-admins)|
|Säkerhets- och efterlevnadscenter|[Administratörsroller i Microsoft 365](permissions-in-the-security-and-compliance-center.md)|
|Priviligierad identitetshantering|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Säkerhetspoäng|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Om SharePoint-administratörsrollen i Office 365](/sharepoint/sharepoint-admin-role)|
|Teams/Skype för företag|[Administratörsroller för Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender för Endpoint|[Rollbaserad åtkomstkontroll för Microsoft Defender för Endpoint](/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>Kommer snart

Vi arbetar fortfarande med behörigheter i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365. Till exempel arbetar vi just nu med support för att:

- Hantera roller i efterlevnadscentret i Microsoft 365 och säkerhetscentret i Microsoft 365, i stället för att gå till Azure Active Directory.
- Anpassa roller genom att lägga till eller ta bort vissa behörigheter.
- Skapa anpassade roller med behörigheter som du väljer.