---
title: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får tillgång till lokala resurser som line of Business-appar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: 4a2ff28107c6e2ec4473859c75bf720df7662747
ms.sourcegitcommit: 58a7bd70a4bcf52530baf5f82507fd5dc4455fd9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2019
ms.locfileid: "39668797"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business

Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser, till exempel Office 365-apparna, och kan skyddas av Microsoft 365 Business. Du kan också tillåta åtkomst till lokala resurser som line of Business (LOB) appar, filresurser och skrivare. Om du vill tillåta åtkomst använder [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory. 

Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Stegen sammanfattas också i följande avsnitt.

> [!IMPORTANT]
> Den här proceduren gäller endast för OAuth och NTLM. Kerberos stöds inte.
 
## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Slutför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure AD Connect som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna. Det här steget görs individuellt på varje Windows 10-enhet. Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) . 
    
3. När Windows 10-enheter är Azure AD-anslutna, måste varje användare starta om sina enheter och logga in med sina autentiseringsuppgifter för Microsoft 365 Business. Alla enheter har nu även tillgång till lokala resurser.
    
Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10. 

Om du har planer på att logga in på AADJ enheten annat än lösenord metod som PIN/bio-Metric via WHFB autentiseringsuppgifter inloggning och sedan komma åt lokala resurser (aktier, skrivare.. etc), vänligen följhttps://docs.microsoft.com/en-us/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Om din organisation inte är redo att distribuera i Azure AD-anslutna enhetskonfigurationen som beskrivs ovan, Överväg att konfigurera [hybrid Azure AD-ansluten enhetskonfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Överväganden när du ansluter Windows-enheter till Azure AD

Om den Windows-enhet som du anslöt till Azure-AD tidigare var domänansluten eller i en arbetsgrupp bör du tänka på följande begränsningar:
  
- När en enhet Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil. Profiler måste migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och start-menyinställningar. Ett bra sätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder Grupprincip-objekt (GPO), kanske vissa grupprincipobjekt inte har en jämförbar [konfiguration tjänstprovider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt.

- Användare kan inte autentisera till program som är beroende av Active Directory-autentisering. Utvärdera äldre app och Överväg att uppdatera till en app som använder modern auth, om möjligt.

- Identifiering av Active Directory-skrivare fungerar inte. Du kan ange direkta skrivar Sök vägar för alla användare eller använda [hybrid molnutskrift](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
