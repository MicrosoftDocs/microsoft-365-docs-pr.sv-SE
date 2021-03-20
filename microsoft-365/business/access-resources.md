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
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913531"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Få tillgång till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium

Den här artikeln gäller Microsoft 365 Business Premium.

Alla Windows 10-enheter som är Azure Active Directory-medlemmar har åtkomst till alla molnbaserade resurser, till exempel dina Microsoft 365-appar, och kan skyddas av Microsoft 365 Business Premium. Du kan också ge åtkomst till lokala resurser som verksamhetsbaserade appar, filresurser och skrivare. Om du vill tillåta åtkomst [använder du Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory. 

Mer information finns i [Introduktion till enhetshantering i Azure Active Directory.](/azure/active-directory/device-management-introduction)
Stegen sammanfattas även i följande avsnitt.
 
## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Gör följande för att aktivera organisationens Azure AD-anslutna enheter för åtkomst till lokala resurser.
  
1. Om du vill synkronisera användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du katalogsynkroniseringsguiden och Azure AD Connect enligt beskrivningen i Konfigurera katalogsynkronisering för [Office 365.](../enterprise/set-up-directory-synchronization.md)
    
2. När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna. Det här steget utförs individuellt på varje Windows 10-enhet. Mer [information finns i Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare.](set-up-windows-devices.md) 
    
3. När Windows 10-enheterna har anslutits till Azure AD måste alla användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter. Alla enheter har nu även åtkomst till lokala resurser.
    
Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10. 

Om du har planer på att logga in på en annan AADJ-enhet än lösenordsmetoden Som PIN/Bio-metric via WHFB-inloggning för autentiseringsuppgifter och sedan åtkomst till lokala resurser (resurser,skrivare.). o.s.v.), följ https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Om organisationen inte är redo att distribuera i den Azure AD-sammanskrivna enhetskonfigurationen som beskrivs ovan bör du överväga att konfigurera konfiguration av [hybrid-Azure AD-ansluten enhet.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Att tänka på när du ansluter Windows-enheter till Azure AD

Om den Windows-enhet som du Azure-AD gick med i tidigare var domän-ansluten eller i en arbetsgrupp ska du ta hänsyn till följande begränsningar:
  
- När en enhet Som Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil. Profiler måste migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och inställningar för Start-menyn. Det bästa sättet är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder grupprincipobjekt (GPO) kanske vissa GPOs [](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) inte har en jämförd konfigurationstjänstleverantör (CSP) i Intune. Kör [MMAT-verktyget för att](https://www.microsoft.com/download/details.aspx?id=45520) hitta liknande CSP:er för befintliga GPOs.

- Användare kanske inte kan autentisera till program som är beroende av Active Directory-autentisering. Utvärdera den äldre appen och överväg att uppdatera till en app som använder modern autentisering, om möjligt.

- Det går inte att hitta Active Directory-skrivare. Du kan ange direkt skrivarsökvägar för alla användare eller använda [Universell utskrift.](/universal-print/)