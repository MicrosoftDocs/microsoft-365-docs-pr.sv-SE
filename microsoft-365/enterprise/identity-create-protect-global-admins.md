---
title: 'Steg 1: Skapa och skydda dina globala administratörskonton'
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
description: Dina globala administratörskonton kräver särskild hantering för att skydda dem från obehörig inloggning.
ms.openlocfilehash: c23a5730bc4c6af1f7fd829a40b63cc7ccc89184
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621312"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>Steg 1: Skapa och skydda dina globala administratörskonton

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>Skydda globala administratörskonton

*Det här är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

I det här avsnittet hjälper du till att förhindra digitala attacker mot din organisation genom att se till att dina administratörskonton är så säkra som möjligt. För att göra det måste du göra följande:

- Skapa fler än ett dedikerat globalt administratörskonto med [starka lösenord](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) och använd dem bara när det behövs.
- Utför daglig administration genom att tilldela specifika administratörsroller, t. ex. Exchange-administratör eller Lösenordsadministratör, till andra dedikerade konton för rollerna eller till användarkonton som tillhör IT-personalen efter behov.

För dina dedikerade globala administratörskonton måste du även:

1. Testa MFA-inställningar baserat på användarkonto eller villkorlig åtkomst på en testanvändare för att säkerställa att MFA fungerar på rätt sätt och på ett förutsägbart sätt. MFA kräver en sekundär typ av autentisering, t.ex. en verifieringskod som skickas till en smartphone.
2. Skapa och aktivera en princip för villkorlig åtkomst för dina globala administratörskonton som kräver MFA och som använder den starkaste formen av sekundär autentisering som är tillgänglig i din organisation. Mer information finns i [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts).

Fler skydd finns i [Skydda dina globala administratörskonton](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations).

> [!Note]
> Nödkonton för akuta scenarier, t.ex. en cyberattack, bör endast vara molnbaserade. Du kan även ha globala administratörskonton (kvalificerade eller permanenta) som inte endast är molnbaserade. Mer information finns i [Hantera administratörskonton för nödåtkomst i Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).

Resultatet från det här avsnittet är:

- De enda användarkonton i din prenumeration som har global administratörsroll ska nu vara de dedikerade globala administratörskontona. Verifiera det här med följande kommando i Azure Active Directory PowerShell för Graph: 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- Alla övriga användarkonton som hanterar dina prenumerationstjänster har administratörsroller som stämmer överens med deras arbetsuppgifter.

> [!Note]
> Mer information om hur du installerar Azure Active Directory PowerShell för Graph-moduler och loggar in finns under [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Skydda globala administratörskonton – testlabbguide](protect-global-administrator-accounts-microsoft-365-test-environment.md). |
|||

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-global-admin) för det här avsnittet.


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>Konfigurera administratörer på begäran

*Det här är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*

I det här avsnittet konfigurerar du Azure AD priviligierade identitetshantering (PIM) för att minska tiden som dina administratörskonton drabbas av angrepp från illvilliga användare. PIM tillhandahåller på begäran- och just-in-time-tilldelning av administratörsrollerna vid behov.  

I stället för att dina administratörskonton permanent har administratörsrättigheter får de kvalificerade administratörsrättigheter. Rollen som administratör är inaktiv tills någon behöver den. Därefter slutför du en aktiveringsprocess för att lägga till administratörsrollen i administratörskontot under en viss tid. När tiden går ut tar PIM bort rollen som administratör från administratörskontot.

PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 E5. Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina administratörskonton.

Mer information om hur du konfigurerar PIM för Azure AD-klientorganisationen och administratörskonton finns i [stegen för att konfigurera PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Mer information om hur du skapar en omfattande översikt för att skydda skyddad åtkomst för cyberangripare finns i [Säker åtkomst för åtkomst för hybrid- och molndistributioner i Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pim) för det här avsnittet.


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management aktiveras genom att principer konfigureras som ställer in just-in-time-åtkomst för uppgiftsbaserade aktiviteter i klientorganisationen. Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar. Du kan t.ex. konfigurera en Privileged Access Management-princip som kräver uttryckligt godkännande för åtkomst till och ändring av inställningar för organisationens postlådor i klientorganisationen.

I det här steget ska du aktivera Privileged Access Management i din klientorganisation och konfigurera principer för privilegierad åtkomst som ger ytterligare säkerhet för aktivitetsbaserad åtkomst till data- och konfigurationsinställningar för din organisation. Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i din organisation:

- Skapa en godkännargrupp
- Aktivera privilegierad åtkomst
- Skapa godkännandeprinciper

När du har konfigurerat Privileged Access Management kan din organisation fungera helt utan ständiga privilegier, och ger ett skydd mot säkerhetsproblem som uppstår på grund av sådan ständig administratörsåtkomst. Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip. Användare som behöver utföra aktiviteter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att få behörigheter för att utföra aktiviteter som definierats i principen.

Information om hur du aktiverar Privileged Access Management finns i avsnittet [Konfigurera Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Mer information finns i avsnittet [Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Privileged Access Management – testlabbguide](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pam) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 2](../media/stepnumbers/Step2.png)| [Skydda dina lösenord](identity-secure-your-passwords.md) |

