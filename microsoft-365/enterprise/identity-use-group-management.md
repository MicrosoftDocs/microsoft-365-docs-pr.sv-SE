---
title: 'Steg 5: Använda grupper för hantering'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Du kan använda grupper för att automatisera hanteringen av vissa administrativa uppgifter.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810397"
---
# <a name="step-5-use-groups-for-management"></a>Steg 5: Använda grupper för hantering

![Fas 2 – Identitet ](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Användare kan skapa och hantera sina egna grupper

*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

I avsnittet identifierar du de Azure Active Directory-grupper som kan hanteras av gruppägare i stället för IT-administratörer. Funktionen kallas för *grupphantering via självbetjäning* där gruppägare som inte har tilldelats någon administratörsroll kan skapa och hantera säkerhetsgrupper. 

Användarna kan begära medlemskap i en säkerhetsgrupp och begäran skickas till gruppens ägare, i stället för IT-administratören. Det innebär att den dagliga kontrollen av gruppmedlemskap blir delegerad till team-, projekt- eller företagsägare som förstår gruppens användningsområden och kan hantera medlemskapen.

>[!Note]
>Grupphantering via självbetjäning finns endast för vissa Azure AD-säkerhetsgrupper och Office 365-grupper. Den är inte tillgänglig för e-postaktiverade grupper, distributionslistor eller grupper som har synkroniserats från lokala Active Directory Domain Services (AD DS).
>

Mer information finns i [anvisningarna om att konfigurera en Azure AD-grupp för självbetjäningshantering](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-self-service-groups) för det här avsnittet.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Konfigurera dynamiskt gruppmedlemskap

*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

I avsnittet kan du skapa en serie regler som automatiskt lägger till eller tar bort användarkonton som är medlemmar i en Azure AD-grupp. Detta kallas för ett *dynamiskt gruppmedlemskap*. Reglerna baseras på användarkontonas attribut, till exempel Avdelning eller Land.

Så här tillämpas reglerna:

- Om ett nytt användarkonto matchar alla regler för gruppen, blir det en medlem.
- Om ett användarkonto inte är medlem i gruppen, men dess attribut ändras så att det matchar alla regler för gruppen, blir det medlem i gruppen.
- Om ett användarkonto inte matchar alla regler för gruppen, läggs det inte till i gruppen.
- Om ett användarkonto är medlem i gruppen, men dess attribut ändras så att det inte längre matchar alla regler för gruppen, tas det bort som medlem i gruppen.

Om du vill använda dynamiskt medlemskap, måste du först bestämma vilka grupper som ska ha en gemensam uppsättning av användarkontoattribut. Alla medlemmar på säljavdelningen kan t.ex. ingå i gruppen Azure AD-försäljning, baserat på användarkontoattributet Avdelning som är inställd på ”Försäljning”.

I [anvisningarna finns information om hur du skapar och konfigurerar reglerna för en dynamisk Azure AD-grupp](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Resultatet från det här avsnittet är:

- En uppsättning Azure AD-grupper som kan konfigureras för dynamiskt medlemskap
- En uppsättning regler för varje dynamisk grupp

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Automatisera licenser och gruppmedlemskap](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-dyn-groups) för det här avsnittet.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Konfigurera automatisk licensiering

*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*

I avsnittet konfigurerar du att säkerhetsgrupper i Azure AD automatiskt tilldelar licenser från en uppsättning prenumerationer till alla medlemmar i gruppen. Det här kallas för *gruppbaserad licensiering*. Om du lägger till eller tar bort ett användarkonto från gruppen, kommer licenserna för gruppens prenumerationer att tilldelas eller tas bort automatiskt från användarkontot.

För Microsoft 365 Enterprise konfigurerar du att Azure AD-säkerhetsgrupperna tilldelar en lämplig Microsoft 365 Enterprise-licens.

Kontrollera att du har tillräckligt med licenser för alla gruppmedlemmar. Om licenserna tar slut kommer nya användare inte att tilldelas några licenser förrän licenserna blir tillgängliga.

>[!Note]
>Du bör inte konfigurera *gruppbaserad licensiering* för grupper som innehåller konton för Azure B2B.
>

Se mer information om [Grunderna i gruppbaserad licensiering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Se [stegen för att konfigurera gruppbaserad licensiering för en Azure-säkerhetsgrupp](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Resultatet från det här avsnittet är:

- Du har identifierat vilka säkerhetsgrupper som är lämpliga för gruppbaserad licensiering.
- Du har konfigurerat dessa grupper för gruppbaserad licensiering.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Automatisera licenser och gruppmedlemskap](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-group-license) för det här avsnittet.

|||
|:-------|:-----|
|![Steg 6](../media/stepnumbers/Step6.png)| [Konfigurera Identity Governance](identity-configure-identity-governance.md) |
