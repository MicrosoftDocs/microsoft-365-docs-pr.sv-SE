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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får tillgång till lokala resurser som line of Business-appar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: 26ba0ffb64ddce32369002120657456e47ac0c7f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287364"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business

Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser som dina Office 365-appar och kan skyddas av Microsoft 365 Business. Om du även vill tillåta åtkomst till lokala resurser som line of Business (LOB) appar, filresurser och skrivare, måste du synkronisera din lokala Active Directory med Azure Active Directory med hjälp av [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). 

Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) .
Stegen sammanfattas också i följande avsnitt.

## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Slutför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure AD Connect som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. När katalogsynkroniseringen har slutförts kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna. Det här steget görs individuellt på varje Windows 10-enhet. Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) . 
    
3. När Windows 10-enheter är Azure AD-anslutna, bör varje användare starta om sina enheter och logga in med sina Microsoft 365 Business autentiseringsuppgifter. Alla enheter har nu även tillgång till lokala resurser.
    
Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Detta är inbyggda funktioner som är tillgängliga i Windows 10. 
  
Om din organisation inte är redo att distribuera i Azure AD-anslutna enhetskonfigurationen som beskrivs ovan, Överväg att konfigurera [hybrid Azure AD-ansluten enhetskonfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Överväganden när du ansluter dina Windows-enheter till Azure AD

Om du är Azure AD som ansluter till en Windows-enhet som tidigare har domänanslutna eller i en arbetsgrupp, måste du överväga följande begränsningar:
  
- När en enhet Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil. För att åtgärda detta måste profilerna migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar, start-menyinställningar osv. Ett bra sätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen

- Om enheten använder Grupprincip-objekt (GPO), kanske vissa grupprincipobjekt inte har en jämförbar [konfiguration tjänstprovider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt.

- Användare kommer inte att kunna autentisera till program som är beroende av Active Directory-autentisering. För att hantera den här utvärderingen med hjälp av en äldre app och Överväg att uppdatera till en app som använder modern auth om möjligt.

- Identifiering av Active Directory-skrivare fungerar inte. Åtgärda detta genom att tillhandahålla direkta skrivar Sök vägar för alla användare eller utnyttja [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
