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
description: Lär dig hur du konfigurerar de olika installations stegen för Microsoft 365 Business Premium, från prenumeration, att lägga till en domän och användare, för att konfigurera säkerhets principer och mycket mer.
ms.openlocfilehash: fa9c02fa9546437c83b9cc6c1f1e6e0d723ec868
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306478"
---
# <a name="overview-of-setup"></a>Översikt över konfiguration

Titta på en kort video om Microsoft 365 Business Premium-inställningar.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

De flesta installations stegen finns i installations guiden, men de andra alternativen visas också.

## <a name="step-1-add-your-domain-and-users"></a>Steg 1: Lägg till domänen och användarna

   - **[Lägga till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du har köpt din domän under [registreringen](sign-up.md)är det här steget redan klart.)

   - **Lägga till användare**. Du kan lägga till användare på något av de tre sätten:
        - I [guiden](set-up.md#add-users-in-the-wizard).
        - Använd katalog-synkronisering för att [lägga till användare med Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) om du har en lokal Active Directory.
        - Du kan också [lägga till användare](add-users-m365b.md) i administrations centret.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Steg 2: Konfigurera säkerhets principer och konfigurera enheter 

  - Använd [installations guiden](set-up.md#protect-your-organization) för att konfigurera enhets principer. 
  - Du kan också lägga till fler eller redigera dem senare i [administrations centret](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Installations guiden kommer även att konfigurera inställningar för skydd mot grundläggande hotet och förhindra data förlust.
  
  Utöver säkerhets inställningarna i installations guiden kan du öka säkerheten genom att lägga till följande inställningar:

- **Skydd mot skadlig program vara**
- **Stöldskydd med ATP**
- **Exchange Online - arkivering**
- **Azure information Protection (Plan1**)

För att komma igång, se [öka hotets skydd](increase-threat-protection.md) och [Konfigurera funktioner för efterlevnad](set-up-compliance.md).

Se även [de 10 bästa sätten att skydda din Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt över bästa säkerhets praxis.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Steg 3: Konfigurera och hantera Windows 10-enheter

När du har kört guiden Konfigurera kan du proctect alla Windows 10-datorer i organisationen.
  
- Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 Business Premium, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8,1 Pro kan ditt abonnemang ge dig en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Följ anvisningarna i [skydda Windows 10-datorer](secure-win-10-pcs.md) för att konfigurera principer för Windows 10-enheter.

När du ansluter till en Windows 10-enhet till Azure AD tillämpas de principer som du angav för Windows 10-datorer. Mer information finns i [Konfigurera Windows-enheter för Microsoft 365-användare](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Steg 4: installera Microsoft 365-appar för företag
- Du kan installera Office automatiskt på Windows-enheter med hjälp av [installations guiden](set-up.md#deploy-office-365-client-apps).
- Låt användare [installera Office-program](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.
     
## <a name="advanced"></a>Tidigareläggas
- **Använda autopilot för att konfigurera nya enheter**
            
     Du kan använda [autopilot för Windows](add-autopilot-devices-and-profile.md) för att automatiskt konfigurera **nya** Windows 10-enheter för en användare, men det kan vara lättare att skaffa en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig. Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en moln teknologi expert att konfigurera nya enheter som du köper.

- **Åtkomst till lokala resurser**

     - Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal inloggning. Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera detta. Det här är den bästa metoden och enheter i det här läget kallas hybrid Azure AD-anslutna enheter.

    - Om ditt företag har en lokal Active Directory-resurs (till exempel fil resurser och skrivare) kan du ge Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa anvisningarna här: [komma åt lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Se även

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
