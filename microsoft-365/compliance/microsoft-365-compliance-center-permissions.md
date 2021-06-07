---
title: Behörigheter i Microsoft 365 efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Läs mer om hur du hanterar behörigheter Microsoft 365 i Kompatibilitetscenter.
ms.collection: M365-security-compliance
ms.openlocfilehash: 72575fce5f7d43354715c77016a8f444e539887f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772543"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Behörigheter i Microsoft 365 efterlevnadscenter

Kom Microsoft 365 kompatibilitetscenter har nyligen uppdaterats och har nu stöd för direkt hantering av behörigheter för användare som utför efterlevnadsuppgifter i Microsoft 365. Den här uppdateringen innebär att du inte längre behöver använda Säkerhets- Office 365 säkerhets- & för att hantera behörigheter för efterlevnadslösningar. Med den **nya** sidan Behörigheter i efterlevnadscentret för Microsoft 365 kan du hantera behörigheter för användare för efterlevnadsuppgifter i funktioner som enhetshantering, skydd mot dataförlust, eDiscovery, insider-riskhantering, kvarhållning och många fler. Användare kan bara utföra de efterlevnadsuppgifter som du uttryckligen beviljar dem åtkomst till.

För att  visa fliken Behörigheter i Microsoft 365 efterlevnadscenter måste användarna vara globala  administratörer eller ha tilldelats rollhanteringsrollen (en roll är endast tilldelad till rollgruppen *Organisationshantering).* Med *rollhanteringsrollen* kan användarna visa, skapa och ändra rollgrupper.

![Sidan Behörigheter i Microsoft 365 efterlevnadscenter](../media/m365-compliance-center-permissions.png)

Behörigheter i Microsoft 365 är baserade på den rollbaserade behörighetsmodellen (RBAC). RBAC är samma behörighetsmodell som används av de flesta Microsoft 365-tjänster, så om du är bekant med behörighetsstrukturen i de här tjänsterna känner du till att bevilja behörigheter i Microsoft 365 efterlevnadscenter. Det är viktigt att komma ihåg att de behörigheter som hanteras i Microsoft 365 efterlevnadscenter inte omfattar hanteringen av alla behörigheter som krävs för varje enskild tjänst. Du måste fortfarande hantera vissa tjänstspecifika behörigheter i administrationscentret för den specifika tjänsten. Om du till exempel behöver tilldela behörigheter för arkivering, granskning och bevarandeprinciper måste du hantera de här behörigheterna i administrationscentret Exchange arkivering.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relation mellan medlemmar, roller och rollgrupper

En roll ger behörighet att utföra en uppsättning aktiviteter. Med rollen Ärendehantering kan användarna till exempel arbeta med eDiscovery-ärenden.

En rollgrupp är en uppsättning roller som gör att användare kan göra sitt jobb med efterlevnadslösningar Microsoft 365 efterlevnadscenter. Genom att lägga till användare i rollgruppen *Insider-riskhantering* konfigureras till exempel administratörer, analytiker, ekonomier och granskare för de nödvändiga behörigheterna för Insider-riskhantering i en enda grupp. I Microsoft 365 kompatibilitetscenter finns standardrollgrupper för uppgifter och funktioner för varje efterlevnadslösning som du måste tilldela personer till. I allmänhet rekommenderar vi att du bara lägger till enskilda användare som medlemmar i rollgrupperna för standardefterlevnad efter behov.

![Diagram som visar relationen mellan rollgrupper och roller och medlemmar](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Behörigheter som krävs för att använda funktioner Microsoft 365 efterlevnadscenter

Om du vill visa alla standardrollgrupper som är tillgängliga i efterlevnadscentret för Microsoft 365 och de roller som rollgrupperna har tilldelats som standard går du till Behörigheter i säkerhets- och efterlevnadscentret för [&.](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Hantering av behörigheter Microsoft 365 efterlevnadscenter ger endast användare tillgång till de efterlevnadsfunktioner som är tillgängliga i Microsoft 365 efterlevnadscenter. Om du vill ge behörighet till andra funktioner som inte finns i Microsoft 365 efterlevnadscenter, till exempel Exchange e-postflödesregler (kallas även transportregler), måste du använda Exchange-administrationscentret.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Azure-roller i Microsoft 365 efterlevnadscenter

De roller som visas i avsnittet **Azure**  >  **AD-roller** på sidan Behörigheter Microsoft 365 **efterlevnadscenter** är Azure Active Directory roller. Rollerna är utformade för att passa ihop med jobbfunktioner i din organisations IT-grupp, vilket gör det enkelt att ge en person alla de behörigheter som krävs för att få jobbet gjort. Du kan visa de användare som för närvarande har tilldelats varje roll genom att välja en administratörsroll och visa information i rollpanelen. Om du vill hantera medlemmar med en Azure AD-roll väljer du Hantera medlemmar i Azure AD. Det här valet omdirigerar dig till Azure Management Portal.

|Roll|Beskrivning|
|:---|:----------|
|**Global administratör**|Användare som har den här rollen har tillgång till alla administrativa funktioner i alla Microsoft 365-tjänster. Det är bara globala administratörer som kan tilldela andra administratörsroller. Mer information finns i [Global administratör / företagsadministratör](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administratör för efterlevnadsdata**|Användare som har den här rollen kan hålla reda på organisationens data i Microsoft 365, se till att de skyddas och få insikter om problem för att minska riskerna. Mer information finns i [Administratör för efterlevnadsdata](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Efterlevnadsadministratör**|Användare som har den här rollen kan hjälpa din organisation att efterleva föreskrifter, hantera eDiscovery-ärenden och underhålla datastyrningsprinciper för Microsoft 365-platser, identiteter och appar. Mer information finns i[ Efterlevnadsadministratör](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Säkerhetsoperatör**|Användare som har den här rollen kan visa, undersöka och reagera på aktiva hot för dina Microsoft 365-användare, enheter och innehåll. Mer information finns i [säkerhetsoperatören](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Säkerhetsläsare**|Användare som har den här rollen kan visa och undersöka aktiva hot mot dina Microsoft 365-användare, enheter och innehåll, men (i motsats till säkerhetsoperatören) har de inte behörighet att svara genom att vidta åtgärder. Mer information finns i [Säkerhetsläsare](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Säkerhetsadministratör**|Användare som har den här rollen kan styra organisationens allmänna säkerhet genom att hantera säkerhetsprinciper, granska säkerhetsanalyser och -rapporter i Microsoft 365-produkter och hålla sig uppdaterade om hotet. Mer information finns i [Säkerhetsadministratör](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Global läsare**|Den skrivskyddade versionen av rollen **Global administratör**. Visa alla inställningar och administrativ information i Microsoft 365. Mer information finns i[ Global läsare](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Simuleringsadministratör för attack**|Skapa och hantera alla aspekter av att skapa attackspel, starta/schemalägga en simulering och granska simuleringsresultat. Mer information finns i Attack [simuleringsadministratör](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Författare av attack av nyttolast**|Skapa attack payloads men inte starta eller schemalägga dem. Mer information finns i Attack [Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Lägga till användare i en rollgrupp för efterlevnad

Följ anvisningarna nedan om du vill lägga till användare i en rollgrupp för efterlevnad:

1. Logga in i behörighetsområdet i [Microsoft 365 med autentiseringsuppgifter](https://compliance.microsoft.com/permissions) för ett administratörskonto i din Microsoft 365 organisation.
2. Gå till Microsoft 365 i säkerhets- och **efterlevnadscentret.** Välj länken för att visa och hantera efterlevnadsroller i Microsoft 365.
3. Expandera avsnittet **Efterlevnadscenter** och välj **Roller.**
4. På sidan **Roller i efterlevnadscenter** väljer du en rollgrupp för efterlevnad som du vill lägga till användare i och väljer **sedan Redigera rollgrupp** i informationsfönstret.
5. Välj **Välj medlemmar** i det vänstra navigeringsfönstret och välj sedan **Redigera**.
6. Välj **Lägg** till och markera sedan kryssrutan för alla användare som du vill lägga till i rollgruppen.
7. Välj **Lägg** till och välj sedan **Klar**.
8. Välj **Spara** för att lägga till användare i rollgruppen. Välj **Stäng** för att slutföra stegen.

## <a name="remove-users-from-a-compliance-role-group"></a>Ta bort användare från en rollgrupp för efterlevnad

Följ anvisningarna nedan om du vill ta bort användare från en rollgrupp för efterlevnad:

1. Logga in i behörighetsområdet i [Microsoft 365 med autentiseringsuppgifter](https://compliance.microsoft.com/permissions) för ett administratörskonto i din Microsoft 365 organisation.
2. Gå till Microsoft 365 i säkerhets- och **efterlevnadscentret.** Välj länken för att visa och hantera efterlevnadsroller i Microsoft 365.
3. Expandera avsnittet Efterlevnadscenter och välj **Roller.**
4. På sidan **Roller i efterlevnadscenter** väljer du en rollgrupp för efterlevnad som du vill ta bort användare från och väljer sedan **Redigera rollgrupp** i informationsfönstret.
5. Välj **Välj medlemmar** i det vänstra navigeringsfönstret och välj sedan **Redigera**.
6. Markera **Ta** bort och markera sedan kryssrutan för alla användare som du vill ta bort från rollgruppen.
7. Välj **Ta** bort och välj sedan **Klar**.
8. Välj **Spara** för att ta bort användare från rollgruppen. Välj **Stäng** för att slutföra stegen.
