---
title: Översikt över konfiguration
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Läs om konfigurationsstegen för Microsoft 365 Business Premium, från att prenumerera, till att lägga till en domän och användare, till att konfigurera säkerhetsprinciper och mycket mer.
ms.openlocfilehash: 008a5c51698589667acc0d01649f67dab33b4c58
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245073"
---
# <a name="overview-of-setup"></a>Översikt över konfiguration

Titta på en kort video om Microsoft 365 Business Premium konfiguration.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../business-video/index.yml).

De flesta konfigurationsstegen kan utföras i den guidade installationen, men de andra alternativen visas också.

## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägg till din domän och dina användare

   - **[Lägg till din](set-up.md#add-your-domain-to-personalize-sign-in)** domän (om du köpte domänen [vid registrering](sign-up.md)är det här steget redan klart).)

   - **Lägg till användare.** Du kan lägga till användare på något av följande tre sätt:
        - I den [guidade installationen](set-up.md#add-users-in-the-wizard).
        - Använd katalogsynkronisering [för att lägga till användare med hjälp av Azure AD Anslut](../enterprise/set-up-directory-synchronization.md) om du har en lokal Active Directory.
        - Du kan också [lägga till användare](../admin/add-users/add-users.md) senare i administrationscentret.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Konfigurera säkerhetsprinciper och konfigurera enheter 

  - Använd den [guidade installationen för](set-up.md#protect-your-organization) att konfigurera enhetsprinciper. 
  - Du kan också lägga till fler eller redigera dem senare i [administrationscentret](view-policies-and-devices.md) och i [Intune-portalen.](/intune/tutorial-walkthrough-intune-portal)
  - Installationsguiden kommer också att konfigurera grundläggande inställningar för skydd mot hot och dataförlustskydd.
  
  Förutom säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:

- **Skydd mot skadlig programvara för e-post**
- **Skydd mot nätfiske i Defender för Office 365**
- **Exchange Online - arkivering**
- **Azure Information Protection (Plan1**)

Läs mer om att öka [skyddet mot hot och](increase-threat-protection.md) konfigurera efterlevnadsfunktioner för att komma [igång.](set-up-compliance.md)

I de [10 bästa sätten att skydda Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) finns en karta över metodtips.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10 enheter

När du har slutfört den guidade installationen bör du skydda alla Windows 10 i organisationen.
  
- Windows 10 Pro krävs för [](pre-requisites-for-data-protection.md) Microsoft 365 Business Premium, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro har din prenumeration rätt att uppgradera till [Windows 10 Pro.](./upgrade-to-windows-pro-creators-update.md)
- Följ stegen i skydda [Windows 10-datorer för](secure-win-10-pcs.md) att konfigurera principer för Windows 10 enheter.

När du ansluter Windows 10 enhet till Azure AD tillämpas de principer Windows 10 för datorer på den. Mer information finns i [Konfigurera Windows enheter för Microsoft 365 användare.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Steg 4: Installera Microsoft 365-applikationer för affärsverksamhet
- Du kan automatiskt Office i Windows-enheter med hjälp av [installationsguiden.](set-up.md#deploy-office-365-client-apps)
- Låt användarna [installera Office appar](/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Avancerat
- **Använda Autopilot för att konfigurera nya enheter**
            
     Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) till att automatiskt förkonfigurera nya **Windows 10-enheter** för en användare, men det kan vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå [till Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en expert på molnteknik att konfigurera nya enheter som du köper.

- **Åtkomst till lokala resurser**

     - Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering. Följ anvisningarna i [Aktivera domän-Windows 10 enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) konfigurera detta. Det här är den rekommenderade metoden, och enheter i det här läget kallas för Hybrid Azure AD-anslutna enheter.

    - Om ditt företag har en lokal Active Directory-enhet som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa stegen här: Få åtkomst till lokala resurser från en [Azure AD-ansluten](access-resources.md)enhet i Microsoft 365 Business Premium.

## <a name="related-content"></a>Relaterat innehåll

[Microsoft 365 om utbildningsvideor för företag](../business-video/index.yml) (länksida)