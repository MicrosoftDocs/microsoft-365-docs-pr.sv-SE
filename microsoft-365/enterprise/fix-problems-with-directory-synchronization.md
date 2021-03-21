---
title: Åtgärda problem med katalogsynkronisering for Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Här beskrivs vanliga orsaker till problem med katalogsynkronisering i Office 365 samt några metoder för att felsöka och åtgärda dem.
ms.openlocfilehash: c6d810bd2f98df2c8df1c0e7fc942502c32d07f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922442"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Åtgärda problem med katalogsynkronisering for Office 365

Med Katalogsynkronisering kan du fortsätta att hantera användare och grupper lokalt och synkronisera tillägg, borttagningar och ändringar i molnet. Men konfigurationen är lite komplicerad och det kan ibland vara svårt att identifiera problemkällan. Vi har resurser som kan hjälpa dig att identifiera potentiella problem och åtgärda dem.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>Hur vet jag om något är fel?

Det första tecknet på att något är fel är när DirSync-statuspanelen i Microsoft 365 administrationscenter indikerar ett problem.
  
Du får även ett e-postmeddelande (till din alternativa e-postadress och din e-postadress som administratör) från Microsoft 365 som anger att det har uppstått katalogsynkroniseringsfel på klientorganisationen. Mer information finns i [Identifiera katalogsynkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>Hur får jag verktyget Azure Active Directory Connect?

I [Microsoft 365 administrationscenter](https://admin.microsoft.com), gå till **Användare** \> **Aktiva användare**. Klicka på menyn **Mer (tre punkter)** och välj **Katalogsynkronisering**.. 
  
Följ [anvisningarna i guiden](set-up-directory-synchronization.md) för att ladda ned Azure AD Connect. 
  
Om du fortfarande använder Azure Active Directory (Azure AD)-synkroniseringsverktyget (DirSync) läser du [Så här felsöker du felmeddelanden för installationen av och konfigurationsguiden för Azure Active Directory-synkroniseringsverktyget i Microsoft 365](/troubleshoot/azure/active-directory/installation-configuration-wizard-errors). Där finns information om systemkraven för att installera dirsync, vilken behörighet du behöver och hur du felsöker vanliga fel. 
  
För Information om hur du uppdaterar från Azure AD-Synkronisering till Azure AD Connect se [Uppgraderingsinstruktioner](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Vanliga orsaker till problem med katalogsynkronisering i Office 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Synkroniserade objekt visas eller uppdateras inte online, eller jag får rapporter om synkroniseringsfel från tjänsten.

- [Identitetssynkronisering och flexibilitet för dubblettattribut](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Jag har en avisering i administrationscenter, eller får automatiska e-postmeddelanden om att det inte har skett en synkronisering på sistone
- [Felsöka anslutningsproblem med Azure AD Connect](/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Azure AD Connect-konton och -behörigheter](/azure/active-directory/hybrid/reference-connect-accounts-permissions)
- [Azure AD Connect-synkronisering: Hantera Azure AD-tjänstkontot](/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [Katalogsynkronisering med Azure Active Directory avslutas eller så får du en varning om att synkronisering inte registrerats på mer än en dag](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Lösenordshashar synkroniseras inte, eller jag ser en varning i administrationscenter om att det inte har skett någon synkronisering av lösenordshash på sistone 
- [Implementera synkronisering av lösenordshash med Azure AD Connect-synkronisering](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Ett meddelande om att objektkvoten har överskridits visas
- Vi har en inbyggd objektkvot för att skydda tjänsten. Om du har för många objekt i katalogen som måste synkroniseras till Microsoft 365 måste du [Kontakta supporten för företags produkter ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)för att öka din kvot.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Jag behöver veta vilka attribut som synkroniseras
- En lista över alla attribut som synkroniseras till molnet finns [här](https://go.microsoft.com/fwlink/p/?LinkId=396719).

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>Jag kan inte hantera eller ta bort objekt som har synkroniserats till molnet
- Är du redo att hantera objekt endast i molnet? Eller finns det ett objekt som har tagits bort lokalt, men fastnat i molnet? Ta en titt på den här [Felsökningsfel under synkronisering ](/azure/active-directory/hybrid/tshoot-connect-sync-errors) och [Supportartikel](/troubleshoot/azure/active-directory/cannot-manage-objects) för vägledning om hur du löser problemen.

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Jag fick ett felmeddelande om att företaget har överskridit det antal objekt som går att synkronisera
- Du kan läsa mer om problemet [här](/troubleshoot/azure/active-directory/exceed-number-objects-synced).
   
## <a name="other-resources"></a>Andra resurser

- [Skript för att åtgärda dubbletter av UPN-namn](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Så här förbereder du en icke-dirigerbar domän som .lokal domän för katalogsynkronisering](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Skript för att räkna totalt antal synkroniserade objekt](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Felsöka AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Använda PowerShell för att åtgärda tomma DisplayName-attribut för e-postgrupper](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Använda PowerShell för att åtgärda UPN-dubbletter](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Använda PowerShell för att åtgärda dubbletter av e-postadresser](https://go.microsoft.com/fwlink/p/?LinkId=396731)
