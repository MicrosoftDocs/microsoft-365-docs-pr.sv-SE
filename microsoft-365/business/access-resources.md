---
title: Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig att få åtkomst till lokala resurser som Line Of Business apps, filresurser och skrivare från en Azure Active Directory ingår Windows 10-enhet.
ms.openlocfilehash: 212685bc229f519152e69b09d0a745bfac7a38cd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276890"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business

Alla Windows 10-enheter som är Azure Active Directory ansluten ska ha tillgång till alla cloud-baserade resurser som Office 365-appar och kan vara skyddat av Microsoft 365 Business. Också att få åtkomst till lokala resurser som raden av Business (LOB) apps, filresurser och skrivare måste du synkronisera lokal Active Directory med Azure Active Directory med [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Finns i [Introduktion till hantering av enheter i Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) mer. 
  
## <a name="run-azure-ad-connect"></a>Kör Azure AD Anslut

Utför följande steg om du vill aktivera organisationen Azure AD anslutna enheter åtkomst till lokala resurser.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokal Active Directory till Azure Active Directory, kör du guiden för Directory-synkroniseringen och Azure AD Anslut som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. När directory-synkroniseringen har slutförts kontrollera företagets Windows 10-enheter Azure AD ansluten. Detta görs individuellt på varje Windows 10-enhet. Mer information finns i [ställa in Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) . 
    
3. När Windows 10-enheter Azure AD ansluten, bör varje användare starta om sina enheter och loggar in med sina Microsoft 365 Business-autentiseringsuppgifter. Alla enheter har nu åtkomst till lokala resurser samt.
    
Inga ytterligare åtgärder krävs för att få åtkomst till lokala resurser för Azure AD anslutna enheter. Detta är inbyggda funktioner som är tillgängliga i Windows 10. 
  
Om din organisation inte är redo att distribuera i Azure AD anslutna enhetens konfiguration ovan nätverksdrivrutinernas [konfiguration av Hybrid Azure AD ansluten enhet](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Att tänka på när du ansluter till Windows-enheter till Azure AD

Om du är Azure AD ansluta till en Windows-enhet som tidigare har anslutit till domänen eller i en arbetsgrupp måste du beakta följande begränsningar:
  
- När en enhet Azure AD ansluter till, skapar en ny användare utan hänvisar till en befintlig profil. Lös problemet behöver profiler migreras manuellt. En användarprofil innehåller information, till exempel Favoriter, lokala filer, webbläsarinställningar, inställningar för Start-menyn, etc. Bästa metoden är att hitta ett tredjepartsverktyg för att mappa befintliga filer och inställningar till den nya profilen
    
- Om enheten använder grupprincip-objekt (GPO), kan vissa grupprincipobjekt inte har en jämförbar [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt. 
    
- Användare kommer inte att kunna autentisera till program som bygger på Active Directory-autentisering. För att bekämpa utvärdera med hjälp av en äldre app och överväga en uppdatering till en app som använder moderna autentisering om det är möjligt.
    
- Identifiering av Active Directory skrivaren fungerar inte. Ge alla användare direkt Skrivarsökvägar eller utnyttja [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)åtgärda detta.
    

