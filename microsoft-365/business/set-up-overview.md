---
title: Översikt över ställs in
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Översikt av stegen för Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "35086396"
---
# <a name="overview-of-setup"></a>Översikt över inställningar

Kan du göra de flesta av stegen i guiden, men andra alternativ finns.


## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägg till din domän och användare

   - **[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du har köpt din domän under [registrera](sign-up.md)görs redan det här steget.)

    - **Lägga till användare**. Du kan göra detta på något av tre sätt:
        - I [guiden](set-up.md#add-users-in-the-wizard).
        - Använda katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active directory.
        - Du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Ställa in IPSec-principer och konfigurera enheter 

  - Använd [installationsguiden för](set-up.md#set-up-security-policies-and-device-configurations) att konfigurera enheten och säkerhetsprinciper. 
  - Du kan också lägga till fler eller redigera dem senare i [administratörscenter](view-policies-and-devices.md) och [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Förutom att säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:

      - **Skydd mot skadlig programvara för e-post**
      - **Avancerade hot skydd (ATP) Safe länkar**
      - **ATP-säkra bifogade filer**
      - **ATP anti-phishing**
      - **Exchange Online - arkivering**
      - **Förhindra dataförlust (DLP)**
      - **Azure informationsskydd (Plan1**)

          Att komma igång finns i [ställa in avancerade IPSec-principer](set-up-advanced-security.md).

        Se även [top 10 sätt att skydda verksamheten Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt av bästa säkerhetspraxis.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10 enheter

   När du ansluter en enhet med Windows 10 till Azure AD tillämpas principer som angetts i [steg 2](#step-2-set-up-security-policies-and-configure-devices) till den.

   - Windows 10 Pro är en [nödvändig förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 företag, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro din prenumeration ger dig rätt att [Uppgradera till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Använd [installationsguiden för](set-up.md#set-up-security-policies-and-device-configurations) att konfigurera principer för Windows 10 enheter.

## <a name="stes-4-install-office-365-business"></a>Stes 4: Installera Office 365 Business
- Du kan automatiskt installera Office i Windows-enheter med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).
- Automatiskt [installera Office](auto-install-or-uninstall-office.md) admin Center.
- Låt användarna [installera Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Avancerad
- **Använda Autopilot för att skapa nya enheter**
            
     Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) före automatiskt konfigurera **nya** Windows 10-enheter för en användare, men kan det vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) och be en expert moln teknik skapa nya enheter du köper du.

- **Komma åt lokala resurser**

     - Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) att ställa in. Detta är den bästa metoden och enheter i det här tillståndet kallas Hybrid Azure AD anslutna enheter.

    - Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), du kan ge din Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa instruktionerna här: [Access lokal resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).

  