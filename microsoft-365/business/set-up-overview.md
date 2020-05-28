---
title: Översikt över konfiguration
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig installationsstegen för Microsoft 365 Business Premium, från att prenumerera, lägga till en domän och användare, till att konfigurera säkerhetsprinciper med mera.
ms.openlocfilehash: 80243fac6ca2efcfca030b6ee1c1113c026a80ce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402987"
---
# <a name="overview-of-setup"></a>Översikt över konfiguration

Titta på en kort video om installationsprogrammet för Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De flesta installationsstegen kan göras i installationsguiden, men de andra alternativen visas också.

## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägg till din domän och dina användare

   - **[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du köpte domänen under [registreringen](sign-up.md)är det här steget redan gjort.)

    - **Lägg till användare**. Du kan lägga till användare på något av de tre sätten:
        - I [guiden](set-up.md#add-users-in-the-wizard).
        - Använd katalogsynkronisering för att lägga till [användare med hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active-katalog.
        - Du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Konfigurera säkerhetsprinciper och konfigurera enheter 

  - Använd [installationsguiden](set-up.md#protect-your-organization) för att konfigurera enhetsprinciper. 
  - Du kan också lägga till fler eller redigera dem senare i [administrationscentret](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Installationsguiden ställer också in grundläggande inställningar för hotskydd och dataförlustskydd.
  
  Förutom säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:

- **Skydd mot skadlig programvara via e-post**
- **ATP anti-phishing**
- **Exchange Online - arkivering**
- **Azure-informationsskydd (plan1)**

För att komma igång, se [öka skydd för hot](increase-threat-protection.md) och ställa in [efterlevnadsfunktioner](set-up-compliance.md).

Se även [de 10 bästa sätten att skydda Din Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt över bästa säkerhetspraxis.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10-enheter

När du har kört guiden Konfigurera vill du ta fram alla Windwos 10-datorer i organisationen.
  
- Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 Business Premium, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger din prenumeration dig rätt till en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Följ stegen i [säkra Windows 10-datorer](secure-win-10-pcs.md) för att konfigurera principer för Windows 10-enheter.

När du ansluter en Windows 10-enhet till Azure AD tillämpas de principer som du anger för Windows 10-datorer på den. Mer information finns i [Konfigurera Windows-enheter för Microsoft 365-användare](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Steg 4: Installera Microsoft 365-appar för företag
- Du kan automatiskt installera Office i Windows-enheterna med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).
- Låt användare [installera Office-program](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Avancerade
- **Använd Autopilot för att konfigurera nya enheter**
            
     Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) för att automatiskt förkonfigurera **nya** Windows 10-enheter för en användare, men det kan vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en molnteknikexpert att konfigurera nya enheter som du köper.

- **Åtkomst till lokala resurser**

     - Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera detta. Det här är den metod som föredras och enheter i det här tillståndet kallas Hybrid Azure AD-anslutna enheter.

    - Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa stegen här: [Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
