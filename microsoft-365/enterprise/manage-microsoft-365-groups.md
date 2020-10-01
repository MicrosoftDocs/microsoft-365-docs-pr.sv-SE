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
description: Lär dig mer om hur du hanterar Microsoft 365-grupper.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328552"
---
# <a name="manage-microsoft-365-groups"></a>Hantera Microsoft 365-grupper

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan hantera Microsoft 365-grupper på flera olika sätt, beroende på konfigurationen. Du kan hantera användar konton i [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, i AD DS (Active Directory Domain Services) eller i [administrations centret för Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal). 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planera var och hur du ska hantera dina grupper

Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365. De två övergripande modellerna är endast molnbaserade och hybrid.
  
### <a name="cloud-only"></a>Endast molnet

Du skapar och hanterar grupper med:

- [Administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Administrations Center för Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Hybrid

AD DS-grupper synkroniseras med Microsoft 365 från AD DS, så du måste använda lokala AD DS-verktyg för att hantera dessa grupper.

Du kan också skapa och hantera Azure AD-grupper som är åtskilda från AD DS-grupper men som kan innehålla användare och grupper från AD DS. I det här fallet kan du använda:

- [Administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Administrations Center för Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Användare kan skapa och hantera sina egna grupper

Azure AD tillåter grupper som kan hanteras av grupp ägare i stället för IT-administratörer. Funktionen kallas för *grupphantering via självbetjäning* där gruppägare som inte har tilldelats någon administratörsroll kan skapa och hantera säkerhetsgrupper. 

Användarna kan begära medlemskap i en säkerhetsgrupp och begäran skickas till gruppens ägare, i stället för IT-administratören. Det innebär att den dagliga kontrollen av gruppmedlemskap blir delegerad till team-, projekt- eller företagsägare som förstår gruppens användningsområden och kan hantera medlemskapen.

>[!Note]
>Grupphantering via självbetjäning finns endast för Azure AD-säkerhetsgrupper och Microsoft 365-grupper. Det är inte tillgängligt för e-postaktiverade grupper, distributions listor eller någon grupp som har synkroniserats från AD DS.
>

Mer information finns i [anvisningarna om att konfigurera en Azure AD-grupp för självbetjäningshantering](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Konfigurera dynamiskt gruppmedlemskap

Azure AD har stöd för att konfigurera en serie regler som automatiskt lägger till eller tar bort användar konton som medlemmar i en Azure AD-grupp. Detta kallas för ett *dynamiskt gruppmedlemskap*. Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.

Så här tillämpas reglerna:

- Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.
- Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.
- Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.
- Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.

Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut. Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.

I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Konfigurera automatisk licensiering

Du kan konfigurera säkerhets grupper i Azure AD så att de automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna tilldelar en lämplig Microsoft 365 Enterprise-licens.

Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera gruppbaserad licensiering för grupper som innehåller konton för Azure B2B.
>

Mer information finns i avsnittet [om grundläggande licenser i Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Se [anvisningarna för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).
