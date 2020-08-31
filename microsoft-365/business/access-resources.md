---
title: Åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
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
description: Lär dig hur du får till gång till lokala resurser som affärs program, fil resurser och skrivare från en Windows 10-enhet med Azure Active Directory.
ms.openlocfilehash: 9b83781afee746b06bbdf90962de0f55ffbcb118
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307502"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium

Den här artikeln gäller Microsoft 365 Business Premium.

Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser, till exempel Microsoft 365-appar och kan skyddas av Microsoft 365 Business Premium. Du kan även tillåta åtkomst till lokala resurser som LOB-appar (Line of Business), fil resurser och skrivare. För att tillåta åtkomst kan du använda [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory. 

Mer information finns i [Introduktion till enhets hantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Stegen sammanfattas i följande avsnitt.

> [!IMPORTANT]
> Den här proceduren kan endast användas för OAuth och NTLM. Kerberos stöds inte.
 
## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Utför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.
  
1. Om du vill synkronisera användare, grupper och kontakter från lokala Active Directory i Azure Active Directory kör du guiden för profilsynkronisering och Azure AD Connect enligt beskrivningen i [Konfigurera katalog-synkronisering för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).
    
2. När Active Directory-synkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-ansluten. Det här steget utförs individuellt på varje Windows 10-enhet. Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) . 
    
3. När Windows 10-enheter är anslutna till Azure AD måste alla användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter. Alla enheter har nu till gång till lokala resurser.
    
Inga ytterligare åtgärder krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10. 

Om du har planer på att logga in på AADJ-enheten annat än lösen ords metod som PIN/bio-metriskt via WHFB-inloggnings uppgifter och sedan åtkomst till lokala resurser (resurser, skrivare. etc), Följ https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Om din organisation inte kan distribueras i konfigurationen för Azure AD med anslutna enheter enligt beskrivningen ovan kan du överväga att konfigurera [hybrid Azure AD-anslutande enhets konfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Att tänka på när du ansluter Windows-enheter till Azure AD

Om Windows-enheten som du Azure-AD anslöt till fungerade tidigare i domänen eller i en arbets grupp bör du tänka på följande:
  
- När en enhet som använder Azure AD ansluter till skapas en ny användare utan att någon befintlig profil refereras. Profiler måste migreras manuellt. En användar profil innehåller information som favoriter, lokala filer, webb läsar inställningar och inställningar för Start-menyn. Ett bra sätt att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder grupprincipobjekten (GPO) kanske vissa grup princip objekt inte har någon jämförbar [konfigurations tjänst leverantör](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grup princip objekt.

- Användarna kan inte autentisera till program som är beroende av Active Directory-autentisering. Utvärdera det äldre programmet och Överväg att uppdatera till ett program som använder modern autentisering, om möjligt.

- Active Directory-skrivaren fungerar inte. Du kan tillhandahålla direkta skrivar vägar för alla användare eller använda [hybrid moln utskrift](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
