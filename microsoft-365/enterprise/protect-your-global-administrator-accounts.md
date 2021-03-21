---
title: Skydda dina globala Microsoft 365-administratörskonton
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
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: Den här artikeln innehåller information om hur du skyddar global administratörsåtkomst till din Microsoft 365-prenumeration.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ade5fd8070a656f976caa75c16ab92cadb7b64a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929054"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Skydda dina globala Microsoft 365-administratörskonton

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Säkerhetsöverträdelser i Microsoft 365-abonnemang, som informationsattacker och nätfiskeattacker, utförs vanligtvis genom att autentiseringsuppgifter för ett globalt Microsoft 365-administratörskonto kompromettering kompromettering. Säkerheten i molnet är ett samarbete mellan dig och Microsoft:
  
- Microsofts molntjänster bygger på en grund av förtroende och säkerhet. Microsoft tillhandahåller säkerhetskontroller och funktioner som hjälper dig att skydda dina data och program.
    
- Du äger dina data och identiteter och ansvarar för att skydda dem, säkerheten för dina lokala resurser och säkerheten för molnkomponenter som du styr.
    
Microsoft tillhandahåller funktioner som hjälper dig att skydda din organisation, men de är bara effektiva om du använder dem. Om du inte använder dem kan du vara sårbar för angrepp. För att skydda dina globala administratörskonton finns Microsoft här för att hjälpa dig med detaljerade anvisningar för att:
  
1. Skapa dedikerade globala Microsoft 365-administratörskonton och använd dem bara när det behövs.
    
2. Konfigurera multifaktorautentisering för dina dedikerade globala Microsoft 365-administratörskonton och använd den starkaste formen av sekundär autentisering.
    
> [!Note]
> Även om den här artikeln fokuserar på globala administratörskonton bör du överväga om ytterligare konton med omfattande behörigheter för att få åtkomst till data i din prenumeration, till exempel eDiscovery-administratör eller konton för säkerhets- och efterlevnadsadministratörer, ska skyddas på samma sätt. <br > Ett globalt administratörskonto kan skapas utan att några licenser läggs till.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Steg 1. Skapa dedikerade globala Microsoft 365-administratörskonton och använd dem bara när det behövs

Det är ganska få administrativa uppgifter, till exempel tilldelning av roller till användarkonton, som kräver global administratörsbehörighet. I stället för att använda vanliga användarkonton som har tilldelats rollen global administratör gör du följande:
  
1. Fastställ vilka användarkonton som har tilldelats rollen som global administratör. Du kan göra detta i administrationscentret för Microsoft 365 eller med följande Azure Active-katalog (Azure AD) PowerShell för Graph-kommando:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Logga in på Microsoft 365-prenumerationen med ett användarkonto som har tilldelats rollen som global administratör.
    
3. Skapa upp till fyra dedikerade globala administratörsanvändarkonton. **Använd starka lösenord, minst 12 tecken långa.** Mer information [finns i Skapa ett](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) starkt lösenord. Lagra lösenorden för de nya kontona på en säker plats. 
    
4. Tilldela den globala administratörsrollen till vart och ett av de nya, dedikerade globala administratörsanvändarkontona.
    
5. Logga ut från Microsoft 365.
    
6. Logga in med ett av de nya, dedikerade globala administratörsanvändarkontona.
    
7. Gör följande för varje befintligt användarkonto som har tilldelats rollen global administratör från steg 1:
    
  - Ta bort den globala administratörsrollen.
    
  - Tilldela administratörsroller till det konto som är lämpligt för den användarens arbetsuppgifter och ansvar. Mer information om olika administratörsroller i Microsoft 365 finns i [Om administratörsroller.](/office365/admin/add-users/about-admin-roles)
    
8. Logga ut från Microsoft 365.
    
Resultatet ska vara:
  
- De enda användarkonton i prenumerationen som har global administratörsroll är den nya uppsättningen dedikerade globala administratörskonton. Kontrollera detta med följande PowerShell-kommando:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alla andra vanliga användarkonton som hanterar din prenumeration har administratörsroller som är kopplade till deras arbetsuppgifter.
    
Från och med nu loggar du bara in med de dedikerade globala administratörskontona för de uppgifter som kräver global administratörsbehörighet. All annan Microsoft 365-administration måste göras genom att andra administratörsroller tilldelas användarkonton.
  
> [!NOTE]
> Det här kräver ytterligare steg för att logga ut som ditt vanliga användarkonto och logga in med ett dedikerat globalt administratörskonto. Men det behöver bara göras då och då för globala administratörsåtgärder. Tänk på att det krävs många fler steg för att återställa din Microsoft 365-prenumeration efter att ett globalt administratörskonto har brytningar.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Steg 2. Konfigurera multifaktorautentisering för dina dedikerade globala Microsoft 365-administratörskonton

Multifaktorautentisering (MFA) kräver ytterligare information utöver kontonamn och lösenord. Microsoft 365 har stöd för följande verifieringsmetoder:
  
- Microsoft Authenticator-appen

- Ett telefonsamtal
    
- En slumpmässigt genererad verifieringskod som skickas via ett SMS
    
- Ett smartkort (virtuellt eller fysiskt)
    
- En biometrisk enhet
    
>[!Note]
>I organisationer som måste följa National Institute of Standards and Technology (NIST) är användningen av ett telefonsamtal eller SMS-baserade ytterligare verifieringsmetoder begränsad. Klicka [här](https://pages.nist.gov/800-63-FAQ/#q-b01) för mer information.
>

Om du har ett litet företag som använder användarkonton som endast lagras i molnet (den molnbaserade identitetsmodellen) konfigurerar du MFA för att konfigurera [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) med ett telefonsamtal eller med en verifieringskod i ett SMS som skickas till en smartphone för varje dedikerat globalt administratörskonto.
    
Om du är en större organisation som använder en Microsoft 365-hybrididentitetsmodell har du fler verifieringsalternativ. Om du redan har säkerhetsinfrastrukturen på plats för en starkare sekundär autentiseringsmetod konfigurerar du [MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) och konfigurerar varje dedikerat globalt administratörskonto för lämplig verifieringsmetod.
  
Om säkerhetsinfrastrukturen för den önskade, starkare verifieringsmetoden inte finns på plats och är fungerande för Microsoft 365 MFA rekommenderar vi starkt att du konfigurerar dedikerade globala administratörskonton med MFA med hjälp av Microsoft Authenticator-appen, ett telefonsamtal eller en verifieringskod i ett SMS som skickas till en smartphone för dina globala administratörskonton som en tillfällig säkerhetsåtgärd. Lämna inte dina dedikerade globala administratörskonton utan det extra skydd som MFA ger.
  
Mer information finns i [MFA för Microsoft 365.](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
  
Information om hur du ansluter till Microsoft 365-tjänster med MFA och PowerShell finns i följande artiklar:

- [PowerShell för Microsoft 365 för användarkonton, grupper och licenser](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype för företag Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Ytterligare skydd för företag

Använd de här metoderna för att säkerställa att ditt globala administratörskonto och konfigurationen du utför med det är så säker som möjligt.
  
### <a name="privileged-access-workstation"></a>Arbetsstation med privilegierad åtkomst

Använd en arbetsstation med behörighet (SÅ SNART SOM MÖJLIGT) för att säkerställa att körningen av aktiviteter med hög behörighet är så säker som möjligt. EN ÄR EN dedikerad dator som endast används för känsliga konfigurationsuppgifter, till exempel Microsoft 365-konfiguration som kräver ett globalt administratörskonto. Eftersom den här datorn inte används dagligen för surfning på Internet eller e-post är den bättre skyddad mot Internetattacker och -hot.
  
Anvisningar om hur du ställer in en TIDE finns i [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) .

Mer information om hur du konfigurerar PIM för Azure AD-klientorganisationen och administratörskonton finns i [stegen för att konfigurera PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

Mer information om hur du skapar en omfattande översikt för att skydda skyddad åtkomst för cyberangripare finns i [Säker åtkomst för åtkomst för hybrid- och molndistributioner i Azure AD](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure Active Directory Privileged Identity Management

I stället för att ha globala administratörskonton permanent tilldelade den globala administratörsrollen kan du använda PIM (Azure AD Privileged Identity Management) för att aktivera tilldelning på begäran och i tid av den globala administratörsrollen när det behövs.
  
Dina globala administratörskonton går från att vara permanenta administratörer till behöriga administratörer. Rollen som global administratör är inaktiv tills någon behöver den. Sedan slutför du aktiveringen och lägger till den globala administratörsrollen i det globala administratörskontot under en förutbestämd tidsperiod. När tiden går ut tar PIM bort rollen som global administratör från det globala administratörskontot.
  
Genom att använda PIM och den här processen minskar avsevärt tiden som dina globala administratörskonton är sårbara för angrepp och användning av skadliga användare.

PIM finns i Azure Active Directory Premium P2, som ingår i Microsoft 365 E5. Alternativt kan du köpa enskilda Azure Active Directory Premium P2-licenser för dina administratörskonton.
  
Mer information finns i Azure [AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management aktiveras genom att principer konfigureras som ställer in just-in-time-åtkomst för uppgiftsbaserade aktiviteter i klientorganisationen. Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar. Du kan t.ex. konfigurera en Privileged Access Management-princip som kräver uttryckligt godkännande för åtkomst till och ändring av inställningar för organisationens postlådor i klientorganisationen.

I det här steget ska du aktivera Privileged Access Management i din klientorganisation och konfigurera principer för privilegierad åtkomst som ger ytterligare säkerhet för aktivitetsbaserad åtkomst till data- och konfigurationsinställningar för din organisation. Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i din organisation:

- Skapa en godkännargrupp
- Aktivera privilegierad åtkomst
- Skapa godkännandeprinciper

Med hantering av privilegierad åtkomst kan organisationen agera utan några stående behörigheter och skapa ett skyddslager mot svagheter som uppstår på grund av sådan administrativ åtkomst. Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip. Användare som behöver utföra uppgifter som ingår i godkännandeprincipen måste begära åtkomstgodkännande.

Information om hur du aktiverar hantering av privilegierad åtkomst finns [i Konfigurera hantering av behörighetsbehörighet.](/office365/securitycompliance/privileged-access-management-configuration)

Mer information finns i Hantera [privilegierad åtkomst.](/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Säkerhetsinformation och händelsehanteringsprogram (SIEM) för Microsoft 365-loggning

SIEM-programvara som körs på en server utför analyser i realtid av säkerhetsvarningar och händelser som skapats av program och nätverksmaskinvara. För att tillåta att din SIEM-server inkluderar Microsoft 365 säkerhetsvarningar och händelser i sina analys- och rapporteringsfunktioner integrerar du Azure AD i SEIM. Se [Introduktion till Azure-loggintegrering.](/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>Nästa steg

Om du vill konfigurera identitet för Microsoft 365-prenumerationen kan du läsa:

- [Molnidentiteter](cloud-only-identities.md) om du använder molnidentitet
- [Förbereda för katalogsynkronisering](prepare-for-directory-synchronization.md) om du använder hybrididentitet

  
## <a name="see-also"></a>Se även

[Microsoft 365 säkerhetsöversikt](/office365/securitycompliance/security-roadmap)