---
title: Översikt över installationsprogrammet
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Översikt över installationsstegen för Microsoft 365 Business.
ms.openlocfilehash: 4aca617015cceb85ca35c8d8ada7b83d1416d959
ms.sourcegitcommit: 178ecb21cacdeaf440f3df2fe6e539e9127fcf15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/23/2019
ms.locfileid: "40850813"
---
# <a name="overview-of-setup"></a>Översikt över installationsprogrammet

Titta på en kort video om Microsoft 365 Business setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Om du hittade den här videon till hjälp, kolla in den [kompletta tränings serien för småföretag och de som är nya för Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De flesta av konfigurationsstegen kan göras i installationsguiden, men de andra alternativen visas också.

## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägg till din domän och användare

   - **[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du köpte domänen under [registreringen](sign-up.md)är det här steget redan gjort.)

    - **Lägg till användare**. Du kan lägga till användare på något av de tre sätten:
        - I [guiden](set-up.md#add-users-in-the-wizard).
        - Använd katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active Directory.
        - Du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Konfigurera säkerhetsprinciper och konfigurera enheter 

  - Konfigurera enhetspolicyer med hjälp av [installationsguiden](set-up.md#protect-your-organization) . 
  - Du kan också lägga till fler eller redigera dem senare i [administratörscenter](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Installationsguiden kommer också att ställa in grundläggande skydd mot hot och dataförlust förebyggande inställningar.
  
  Förutom säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:

- **E-malware skydd**
- **ATP anti-phishing**
- **Exchange Online - arkivering**
- **Azure information Protection (Plan1**)

Kom igång genom att läsa [Konfigurera avancerade säkerhetsprinciper](set-up-advanced-security.md).

Se även [de tio bästa sätten att skydda din Microsoft 365-verksamhet](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en färdplan med de främsta säkerhetsmetoderna.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10-enheter

När du har kört guiden Konfigurera kommer du att vilja proctect alla Windwos 10 datorer i din organisation.
  
- Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365-företag, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8,1 Pro berättigar din prenumeration till en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Följ stegen i [säkra Windows 10-datorer](secure-win-10-pcs.md) för att ställa in policyer för Windows 10-enheter.

När du ansluter en Windows 10-enhet till Azure AD, tillämpas de principer som du anger för Windows 10-datorer på den. Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md).

## <a name="step-4-install-office-365-business"></a>Steg 4: installera Office 365 Business
- Du kan installera Office automatiskt på Windows-enheter med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).
- Låt användarna [installera Office-appar](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Avancerade
- **Använda autopilot för att ställa in nya enheter**
            
     Du kan använda [Windows autopilot](add-autopilot-devices-and-profile.md) för att automatiskt förkonfigurera **nya** Windows 10-enheter för en användare, men det kan vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en expert på molnteknik att konfigurera nya enheter som du köper.

- **Komma åt lokala resurser**

     - Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) för att konfigurera detta. Det här är den bästa metoden och enheter i det här tillståndet kallas hybrid Azure AD-anslutna enheter.

    - Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), kan du ge dina Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa stegen här: [åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).

## <a name="see-also"></a>Se även

[Microsoft 365 Business utbildning videor](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
