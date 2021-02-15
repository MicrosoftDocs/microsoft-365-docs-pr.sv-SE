---
title: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får åtkomst till lokala resurser som verksamhetsappar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233849"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium

Den här artikeln gäller Microsoft 365 Business Premium.

Alla Windows 10-enheter som är Azure Active Directory-medlemmar har tillgång till alla molnbaserade resurser, till exempel Microsoft 365-appar, och kan skyddas av Microsoft 365 Business Premium. Du kan också ge åtkomst till lokala resurser som verksamhetsbaserade appar, filresurser och skrivare. Om du vill tillåta åtkomst [använder du Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory. 

Mer information finns i [introduktionen till enhetshantering i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)
Stegen sammanfattas även i följande avsnitt.
 
## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Utför följande steg för att aktivera din organisations Azure AD-anslutna enheter för åtkomst till lokala resurser.
  
1. Om du vill synkronisera användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du katalogsynkroniseringsguiden och Azure AD Connect enligt beskrivningen i Konfigurera katalogsynkronisering för [Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
    
2. När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna. Det här steget utförs individuellt på varje Windows 10-enhet. Mer [information finns i Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare.](set-up-windows-devices.md) 
    
3. När Windows 10-enheterna har anslutits till Azure AD måste alla användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter. Alla enheter har nu även åtkomst till lokala resurser.
    
Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10. 

Om du har planer på att logga in på AADJ-enheten på något annat sätt än lösenordsmetoden Som PIN/Bio-metric via VAFB-inloggning med autentiseringsuppgifter och sedan åtkomst till lokala resurser (resurser,skrivare.). o.s.v.), följ https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Om din organisation inte är redo att distribuera i konfigurationen av azure AD-ansluten enhet som beskrivs ovan kan det vara bra att konfigurera konfiguration av [Azure AD-ansluten hybridenhet.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Att tänka på när du ansluter Windows-enheter till Azure AD

Om den Windows-enhet som du Azure-AD-ansluten till tidigare var domän ansluten eller i en arbetsgrupp ska du ta hänsyn till följande begränsningar:
  
- När en enhet Azure AD ansluts, skapas en ny användare utan att referera till en befintlig profil. Profiler måste migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och inställningar för Start-menyn. Det bästa sättet är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder en grupprincip GPO kanske vissa GPOs inte [](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) har en jämförlig leverantör av konfigurationstjänster (CSP) i Intune. Kör [MMAT-verktyget för att](https://www.microsoft.com/download/details.aspx?id=45520) hitta liknande csps för befintliga GPOs.

- Användare kanske inte kan autentisera till program som är beroende av Active Directory-autentisering. Utvärdera den äldre appen och överväg att uppdatera till en app som använder modern autentisering, om möjligt.

- Identifiering av Active Directory-skrivare fungerar inte. Du kan ange direkt skrivarsökvägar för alla användare eller använda [Universal Print.](https://aka.ms/UPDocs)
