---
title: Skydda dina Microsoft 365-globala administratörs konton
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: I den här artikeln finns information om hur du skyddar global administratör till din Microsoft 365-prenumeration.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bcc1a09ca8e7c57d4d6c69400925df3531c53c4f
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357812"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Skydda dina Microsoft 365-globala administratörs konton

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Säkerhets brott för en Microsoft 365-prenumeration, inklusive information om att skörda och nätfiske-attacker, görs normalt genom att kompromissa med autentiseringsuppgifterna för ett globalt administratörs konto för Microsoft 365. Säkerhet i molnet är ett samarbete mellan dig och Microsoft:
  
- Microsofts moln tjänster bygger på förtroende och säkerhet. Microsoft tillhandahåller säkerhets kontroller och funktioner som hjälper dig att skydda dina data och program.
    
- Du äger dina data och identiteter och ansvaret för att skydda dem, säkerheten för dina lokala resurser och säkerheten för de moln komponenter du kontrollerar.
    
Microsoft tillhandahåller funktioner för att skydda din organisation, men de gäller bara om du använder dem. Om du inte använder dem kan du vara utsatt för angrepp. För att skydda dina globala administratörs konton finns Microsoft här för att hjälpa dig med detaljerade instruktioner för att:
  
1. Skapa dedikerade Microsoft 365-globala administratörs konton och Använd dem bara när det behövs.
    
2. Konfigurera multifaktorautentisering för dina dedikerade Microsoft 365-globala administratörs konton och Använd den starkaste formen av sekundär verifikation.
    
> [!Note]
> Även om den här artikeln är inriktad på globala administratörs konton bör du överväga om ytterligare konton med behörighet att komma åt data i ditt abonnemang, till exempel en eDiscovery-administratör eller säkerhets-eller efterlevnad administratörs konton, ska skyddas på samma sätt. <br > Ett globalt administratörs konto kan skapas utan att några licenser läggs till.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Steg 1. Skapa dedikerade Microsoft 365-globala administratörs konton och Använd dem bara när det behövs

Det finns relativt få administrativa uppgifter, till exempel tilldela roller till användar konton, som kräver globala administratörs behörigheter. I stället för att använda vardagliga användar konton som har tilldelats rollen som global administratör gör du därför följande:
  
1. Bestäm vilka användar konton som har tilldelats rollen som global administratör. Du kan göra detta i administrations centret för Microsoft 365 eller med följande Azure Active (Azure AD)-katalog PowerShell för kommandot Graph:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Logga in på din Microsoft 365-prenumeration med ett användar konto som har tilldelats rollen som global administratör.
    
3. Skapa upp till fyra dedikerade globala administratörs konton. **Använd starka lösen ord som är minst 12 tecken långa.** Mer information finns i [skapa ett starkt lösen ord](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) . Lagra lösen orden för de nya kontona på en säker plats. 
    
4. Tilldela den globala administratörs rollen till alla nya dedikerade globala administratörs konton.
    
5. Logga ut från Microsoft 365.
    
6. Logga in med ett av de nya dedikerade globala administratörs kontona.
    
7. För varje befintligt användar konto som har tilldelats rollen global administratör från steg 1:
    
  - Ta bort rollen som global administratör.
    
  - Tilldela administratörs roller till det konto som är lämpligt för den användarens jobb funktion och ansvar. Mer information om olika administrativa roller i Microsoft 365 finns i [om administratörs roller](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).
    
8. Logga ut från Microsoft 365.
    
Resultaten ska vara:
  
- De enda användar konton i prenumerationen som har rollen global administratör är den nya uppsättningen globala administratörs konton. Verifiera detta med följande PowerShell-kommando:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alla andra användar konton som hanterar ditt abonnemang har administratörs roller kopplade till deras arbets ansvar.
    
Från och med nu loggar du in med de dedikerade globala administratörs kontona för aktiviteter som kräver globala administratörs behörigheter. All annan Microsoft 365-administration måste göras genom att tilldela andra administrativa roller till användar konton.
  
> [!NOTE]
> Detta kräver ytterligare åtgärder för att logga ut som ditt användar konto och logga in med ett dedikerat globalt administratörs konto. Men detta behöver du bara göra ibland för globala administratörer. Överväg att återställa ditt Microsoft 365-abonnemang efter det att ett globalt administratörs konto bryter mot en mängd olika steg.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Steg 2. Konfigurera multifaktorautentisering för dina dedikerade Microsoft 365-globala administratörs konton

Multifaktorautentisering kräver ytterligare information utöver konto namn och lösen ord. Microsoft 365 har stöd för följande ytterligare verifierings metoder:
  
- Microsoft Authenticator-appen

- Ett telefonsamtal
    
- En slumpvis genererad verifierings kod som skickas via ett textmeddelande
    
- Ett smartkort (virtuellt eller fysiskt)
    
- En biometrisk enhet
    
>[!Note]
>För organisationer som måste följa nationella institutet för standarder och teknik (NIST) är det bara att använda ett telefonsamtal eller SMS-baserade ytterligare verifierings metoder. Klicka [här](https://pages.nist.gov/800-63-FAQ/#q-b01) för mer information.
>

Om du har ett litet företag som bara använder användar konton som lagras i molnet (den molnbaserade identitets modellen) konfigurerar du [MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) för att konfigurera MFA med ett telefonsamtal eller en verifierings kod för SMS till en smart telefon för varje dedikerat globalt administratörs konto.
    
Om du är en större organisation som använder en Microsoft 365-Hybrid identitets modell har du fler verifierings alternativ. Om du inte redan har säkerhets infrastrukturen på plats för en starkare metod för fast autentisering konfigurerar du [MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) och konfigurerar varje dedikerat globalt administratörs konto för lämplig verifierings metod.
  
Om säkerhets infrastrukturen för den önskade starkare verifierings metoden inte är avsedd för Microsoft 365 MFA rekommenderar vi starkt att du konfigurerar dedikerade globala administratörs konton med MFA med hjälp av Microsoft Authenticator-appen, ett telefonsamtal eller en verifierings kod för SMS till en smart telefon för dina globala administratörs konton som en interimistisk säkerhets åtgärd. Lämna inte dina dedikerade globala administratörs konton utan ytterligare skydd från MFA.
  
Mer information finns i [MFA för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
  
Om du vill ansluta till Microsoft 365-tjänster med MFA och PowerShell kan du läsa följande artiklar:

- [PowerShell för Microsoft 365 för användar konton, grupper och licenser](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype för företag Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Ytterligare skydd för företags organisationer

Använd följande metoder för att kontrol lera att ditt globala administratörs konto och konfigurationen som du utför använder det är så säkert som möjligt.
  
### <a name="privileged-access-workstation"></a>Privilegie rad åtkomst arbets Station

Använd en privilegie rad arbets Station (PAW) för att säkerställa att det är så säkert som möjligt att köra mycket privilegierade uppgifter. En PAW är en dedikerad dator som endast används för känsliga konfigurations uppgifter, till exempel Microsoft 365-konfiguration som kräver ett globalt administratörs konto. Eftersom den här datorn inte används dagligen för Internet-surfning eller e-post skyddas den bättre mot Internet attacker och hot.
  
Instruktioner om hur du konfigurerar en PAW finns i [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Mer information om hur du konfigurerar PIM för Azure AD-klientorganisationen och administratörskonton finns i [stegen för att konfigurera PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Mer information om hur du skapar en omfattande översikt för att skydda skyddad åtkomst för cyberangripare finns i [Säker åtkomst för åtkomst för hybrid- och molndistributioner i Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure Active Directory Privileged Identity Management

I stället för att låta globala administratörs konton vara kopplade till rollen som global administratör kan du använda Azure AD privilegierad identitets hantering (PIM) för att aktivera vid begäran, direkt tilldelning av den globala administratörs rollen när det behövs.
  
Dina globala administratörs konton kommer från att bli permanent administratörer för kvalificerade administratörer. Rollen som global administratör är inaktiv tills någon behöver den. Därefter utför du en aktiverings process för att lägga till rollen global administratör till det globala administratörs kontot för en förutbestämd tid. När tiden går ut tar PIM bort rollen som global administratör från det globala administratörskontot.
  
Om du använder PIM och den här processen minskar avsevärt hur länge dina globala administratörs konton drabbas av attacker och användning av illvilliga användare.

PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 E5. Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina administratörskonton.
  
Mer information finns i [Azure AD-privilegierad identitets hantering](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management aktiveras genom att principer konfigureras som ställer in just-in-time-åtkomst för uppgiftsbaserade aktiviteter i klientorganisationen. Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar. Du kan t.ex. konfigurera en Privileged Access Management-princip som kräver uttryckligt godkännande för åtkomst till och ändring av inställningar för organisationens postlådor i klientorganisationen.

I det här steget ska du aktivera Privileged Access Management i din klientorganisation och konfigurera principer för privilegierad åtkomst som ger ytterligare säkerhet för aktivitetsbaserad åtkomst till data- och konfigurationsinställningar för din organisation. Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i din organisation:

- Skapa en godkännargrupp
- Aktivera privilegierad åtkomst
- Skapa godkännandeprinciper

Hanteringen av privilegierade åtkomst gör det möjligt för din organisation att fungera med nollvärden och ger ett försvar mot säkerhets problem som beror på den ständiga administrativa åtkomsten. Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip. Användare som behöver utföra uppgifter som ingår i godkännande policyn måste begära och godkänna åtkomst godkännande.

Information [om](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)hur du aktiverar hantering av privilegierade

Mer information finns i [Hantera privilegierad åtkomst](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Säkerhets information och SIEM program vara för Microsoft 365-loggning

SIEM program vara körs på en server utför en analys i real tid av säkerhets varningar och händelser som skapas av program och nätverks maskin vara. För att din SIEM-Server ska innehålla Microsoft 365-säkerhets varningar och-händelser i dess analys-och rapporterings funktioner integrerar du Azure AD i dig SEIM. Se [Introduktion till Azure logg integrering](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Nästa steg

Om du konfigurerar identitet för din Microsoft 365-prenumeration, se:

- [Endast moln identiteter](cloud-only-identities.md) om du använder moln-Only-identitet
- [Förbereda för Active Directory-synkronisering](prepare-for-directory-synchronization.md) om du använder hybrid identitet

  
## <a name="see-also"></a>Se även

[Säkerhets översikt för Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
