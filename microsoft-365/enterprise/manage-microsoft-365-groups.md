---
title: Hantera Microsoft 365-grupper
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Läs mer om hur du hanterar Microsoft 365-grupper.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911013"
---
# <a name="manage-microsoft-365-groups"></a>Hantera Microsoft 365-grupper

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan hantera Microsoft 365-grupper på flera olika sätt, beroende på din konfiguration. Du kan hantera användarkonton i administrationscentret för [Microsoft 365](../admin/add-users/index.yml), PowerShell, Active Directory Domain Services (AD DS) eller i administrationscentret för [Azure Active Directory (Azure AD).](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planera för var och hur du ska hantera grupperna

Var och hur du kan hantera användarkonton beror på vilken identitetsmodell du vill använda för Microsoft 365. De två övergripande modellerna är enbart moln- och hybridmodeller.
  
### <a name="cloud-only"></a>Endast molnet

Du skapar och hanterar grupper med:

- [Administrationscentret för Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Administrationscenter för Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Hybrid

AD DS-grupper synkroniseras med Microsoft 365 från AD DS, så du måste använda lokala AD DS-verktyg för att hantera grupperna.

Du kan också skapa och hantera Azure AD-grupper som är separata från AD DS-grupper men som kan innehålla användare och grupper från AD DS. I det här fallet kan du använda:

- [Administrationscentret för Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Administrationscenter för Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Användare kan skapa och hantera sina egna grupper

Med Azure AD kan grupper hanteras av gruppägare i stället för IT-administratörer. Funktionen kallas för *grupphantering via självbetjäning* där gruppägare som inte har tilldelats någon administratörsroll kan skapa och hantera säkerhetsgrupper. 

Användarna kan begära medlemskap i en säkerhetsgrupp och begäran skickas till gruppens ägare, i stället för IT-administratören. Det innebär att den dagliga kontrollen av gruppmedlemskap blir delegerad till team-, projekt- eller företagsägare som förstår gruppens användningsområden och kan hantera medlemskapen.

>[!Note]
>Grupphantering via självbetjäning finns endast för Azure AD-säkerhetsgrupper och Microsoft 365-grupper. Den är inte tillgänglig för e-postaktiverade grupper, distributionslistor eller grupper som har synkroniserats från AD DS.
>

Mer information finns i [anvisningarna om att konfigurera en Azure AD-grupp för självbetjäningshantering](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Konfigurera dynamiskt gruppmedlemskap

Azure AD har stöd för konfiguration av en serie regler som automatiskt lägger till eller tar bort användarkonton som medlemmar i en Azure AD-grupp. Detta kallas för ett *dynamiskt gruppmedlemskap*. Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.

Så här tillämpas reglerna:

- Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.
- Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.
- Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.
- Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.

Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut. Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.

I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Konfigurera automatisk licensiering

Du kan konfigurera säkerhetsgrupper i Azure AD för att automatiskt tilldela licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna tilldelar en lämplig Microsoft 365 Enterprise-licens.

Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.
>

Mer information finns i [Grundläggande om gruppbaserad licensiering i Azure AD.](/azure/active-directory/active-directory-licensing-whatis-azure-portal)

Se [anvisningarna för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)