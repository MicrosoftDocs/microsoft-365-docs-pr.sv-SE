---
title: Komma åt lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 BusinessAccess on-premises resources from an Azure AD-joined device in Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får åtkomst till lokala resurser som affärsappar, filresurser och skrivare från en Azure Active Directory-enhet med Windows 10.
ms.openlocfilehash: 653b53d29e84bbdc91273cb78b9b8407c0f6a209
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593242"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Komma åt lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 BusinessAccess on-premises resources from an Azure AD-joined device in Microsoft 365 Business

Alla Windows 10-enheter som är Azure Active Directory-anslutna har åtkomst till alla molnbaserade resurser, till exempel dina Office 365-appar, och kan skyddas av Microsoft 365 Business. Du kan också tillåta åtkomst till lokala resurser som LOB-appar (Business, file shares och skrivare). Om du vill tillåta åtkomst använder du Azure AD Connect för att synkronisera din lokala Active Directory med Azure Active Directory.To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory. 

Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
Stegen sammanfattas också i följande avsnitt.

> [!IMPORTANT]
> Den här proceduren gäller endast OAuth och NTLM. Kerberos stöds inte.
 
## <a name="run-azure-ad-connect"></a>Kör Azure AD Connect

Utför följande steg för att aktivera organisationens Azure AD-anslutna enheter för åtkomst till lokala resurser.
  
1. Om du vill synkronisera dina användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du guiden Katalogsynkronisering och Azure AD Connect enligt beskrivningen i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD anslutna. Det här steget görs individuellt på varje Windows 10-enhet. Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business-användare.](set-up-windows-devices.md) 
    
3. När Windows 10-enheterna är Azure AD-anslutna måste varje användare starta om sina enheter och logga in med sina Microsoft 365 Business-autentiseringsuppgifter. Alla enheter har nu tillgång till lokala resurser också.
    
Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10. 

Om du har planer på att logga in på AADJ-enheten förutom lösenordsmetoden Like PIN/Bio-metric via WHFB-autentiseringsuppgifter och sedan komma åt lokala resurser (resurser,skrivare.. etc), följhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Om din organisation inte är redo att distribuera i den Azure AD-konfiguration som beskrivs ovan bör du överväga att konfigurera [Hybrid Azure AD Joined-enhetskonfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Överväganden när du ansluter till Windows-enheter till Azure AD

Om Windows-enheten som du Azure-AD-anslutna tidigare var domänansluten eller i en arbetsgrupp bör du tänka på följande begränsningar:
  
- När en enhet Azure AD ansluter skapas en ny användare utan att referera till en befintlig profil. Profiler måste migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och Inställningar för Start-menyn. Ett bästa tillvägagångssätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder Grupprincipobjekt (GPO) kanske vissa grupprincipobjekt inte har någon jämförbar [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [MMAT-verktyget](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara CSP för befintliga grupprincipobjekt.

- Användare kan inte autentisera till program som är beroende av Active Directory-autentisering. Utvärdera den äldre appen och överväg att uppdatera till en app som använder modern Auth, om möjligt.

- Identifiering en active directory-skrivare fungerar inte. Du kan ange direkta skrivarsökvägar för alla användare eller använda [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
