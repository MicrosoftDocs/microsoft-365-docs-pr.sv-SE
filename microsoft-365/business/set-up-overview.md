---
title: Översikt över inställningar
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig installationsstegen för Microsoft 365 Business, från att prenumerera, lägga till en domän och användare till att skapa säkerhetsprinciper med mera.
ms.openlocfilehash: 9bb536b52981966f6c4c487f8400577b896261e0
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561203"
---
# <a name="overview-of-setup"></a>Översikt över inställningar

Titta på en kort video om installationsprogrammet för Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De flesta installationsstegen kan göras i installationsguiden, men de andra alternativen visas också.

## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägga till din domän och dina användare

   - **[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du köpte din domän under [registreringen](sign-up.md)är det här steget redan klart.)

    - **Lägg till användare**. Du kan lägga till användare på något av de tre sätten:
        - I [guiden](set-up.md#add-users-in-the-wizard).
        - Använd katalogsynkronisering för att lägga till [användare med Hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active-katalog.
        - Du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Konfigurera säkerhetsprinciper och konfigurera enheter 

  - Använd [guiden Konfigurera installationsprogrammet](set-up.md#protect-your-organization) för att konfigurera enhetsprinciper. 
  - Du kan också lägga till fler eller redigera dem senare i [administrationscentret](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Installationsguiden ställer också in grundläggande inställningar för skydd av hot och dataförlust.
  
  Förutom säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:

- **Skydd mot skadlig kod via e-post**
- **ATP-anti-phishing**
- **Exchange Online - arkivering**
- **Azure-informationsskydd (Plan1**)

För att komma igång, se [öka hotskyddet](increase-threat-protection.md) och [ställa in efterlevnadsfunktioner](set-up-compliance.md).

Se även [de 10 bästa sätten att skydda ditt Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en färdplan med bästa säkerhetspraxis.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10-enheter

När du har kört guiden Konfigurera vill du proctect alla Windwos 10-datorer i organisationen.
  
- Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 Business, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro ger din prenumeration dig rätt till en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Följ stegen i [säkra Windows 10-datorer](secure-win-10-pcs.md) för att ställa in principer för Windows 10-enheter.

När du ansluter en Windows 10-enhet till Azure AD tillämpas de principer som du anger för Windows 10-datorer på den. Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md).

## <a name="step-4-install-office-365-business"></a>Steg 4: Installera Office 365 Business
- Du kan installera Office automatiskt på Windows-enheterna med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).
- Låt användarna [installera Office-appar](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Avancerade
- **Använda Autopilot för att konfigurera nya enheter**
            
     Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) för att automatiskt förkonfigurera **nya** Windows 10-enheter för en användare, men det kan vara lättare att skaffa en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en molnteknikexpert att konfigurera nya enheter som du köper.

- **Få tillgång till lokala resurser**

     - Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) för att konfigurera detta. Detta är den metod som föredras och enheter i det här tillståndet kallas Hybrid Azure AD-anslutna enheter.

    - Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa stegen här: [Få tillgång till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
