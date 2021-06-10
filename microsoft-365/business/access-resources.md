---
title: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du får åtkomst till lokala resurser som verksamhetsappar, filresurser och skrivare från en Azure Active Directory ansluten Windows 10 enhet.
ms.openlocfilehash: 72b3c5ae538cad24fc12e25717dedccb2fdc9017
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843331"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium

Den här artikeln gäller för Microsoft 365 Business Premium.

Alla Windows 10 enheter som Azure Active Directory är ansluten har åtkomst till alla molnbaserade resurser, till exempel dina Microsoft 365-appar, och kan skyddas av Microsoft 365 Business Premium. Du kan också ge åtkomst till lokala resurser som verksamhetsbaserade appar, filresurser och skrivare. Om du vill tillåta åtkomst [använder du Azure AD Anslut](/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory.

Mer information finns i [Introduktion till enhetshantering i Azure Active Directory](/azure/active-directory/device-management-introduction).
Stegen sammanfattas även i följande avsnitt.

## <a name="run-azure-ad-connect"></a>Kör Azure AD Anslut

Gör följande för att aktivera organisationens Azure AD-anslutna enheter för åtkomst till lokala resurser.

1. Om du vill synkronisera användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du guiden Katalogsynkronisering och Azure AD Anslut enligt beskrivningen i Konfigurera katalogsynkronisering [för Office 365.](../enterprise/set-up-directory-synchronization.md)

2. När katalogsynkroniseringen är klar kontrollerar du att organisationens enheter Windows 10 är Azure AD anslutna. Det här steget utförs individuellt på varje enskild Windows 10 enhet. Mer [information finns Windows konfigurera Microsoft 365 Business Premium användarna.](set-up-windows-devices.md)

3. När Azure AD Windows 10 enheterna har anslutits måste alla användare starta om sina enheter och logga in med Microsoft 365 Business Premium autentiseringsuppgifter. Alla enheter har nu även åtkomst till lokala resurser.

Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter. Den här funktionen är inbyggd i Windows 10.

Följ den här artikeln om du har planer på att logga in på en annan AADJ-enhet än lösenordsmetoden Som PIN/Bio-metric via WHFB-autentiseringsuppgifter och sedan åtkomst till lokala resurser (resurser, skrivare [osv.).](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)

Om organisationen inte är redo att distribuera i den Azure AD-sammanskrivna enhetskonfigurationen som beskrivs ovan bör du överväga att konfigurera konfiguration av [hybrid-Azure AD-ansluten enhet.](manage-windows-devices.md)

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Att tänka på när du Windows enheter till Azure AD

Om den Windows som du Azure-AD gick med på tidigare var domänmedlem eller i en arbetsgrupp ska du ta hänsyn till följande begränsningar:

- När en enhet Som Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil. Profiler måste migreras manuellt. En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och inställningar för Start-menyn. Det bästa sättet är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.

- Om enheten använder grupprincipobjekt (GPO) kanske vissa GPOs [](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) inte har en jämförd konfigurationstjänstleverantör (CSP) i Intune. Kör [MMAT-verktyget för att](https://www.microsoft.com/download/details.aspx?id=45520) hitta liknande CSP:er för befintliga GPOs.

- Användare kanske inte kan autentisera till program som är beroende av Active Directory-autentisering. Utvärdera den äldre appen och överväg att uppdatera till en app som använder modern autentisering, om möjligt.

- Det går inte att hitta Active Directory-skrivare. Du kan ange direkt skrivarsökvägar för alla användare eller använda [Universell utskrift.](/universal-print/)

### <a name="related-articles"></a>Relaterade artiklar

[Krav för Azure AD-Anslut](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
