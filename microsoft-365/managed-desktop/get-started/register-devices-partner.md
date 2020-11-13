---
title: Steg för partner för att registrera enheter
description: Så här kan partners registrera enheter så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071449"
---
# <a name="steps-for-partners-to-register-devices"></a>Steg för partner för att registrera enheter


I det här avsnittet beskrivs de partners som du följer för att registrera enheter. Processen för att registrera enheter själv är dokumenterad i [registrera enheter på Microsoft Managed Desktop](register-devices-self.md).



## <a name="prepare-for-registration"></a>Förbereda inför registrering 
Innan registreringen av en kund är klar måste du först upprätta en relation med dem hos [partner centret](https://partner.microsoft.com/dashboard). Se [dokumentationen för godkännande](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) för mer information om den processen. Alla CSP-partners kan lägga till enheter åt vilken kund som helst, förutsatt att kunden samtycker. Du kan också läsa mer om partner relationer och autopilot-behörigheter i [partner Center-hjälpen](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Denna dokumentation är endast för partner och OEM-tillverkare. Processen för själv registrering är dokumenterad i [registrera enheter på Microsoft Managed Desktop](register-devices-self.md).


## <a name="register-devices-by-using-partner-center"></a>Registrera enheter med hjälp av Partner Center

När du har fastställt relationen till kunderna kan du använda Partner Center för att lägga till enheter till autopilot för de kunder som du har en relation till genom att följa de här stegen:

1. Navigera till [partner Center](https://partner.microsoft.com/dashboard)
2. Välj **kunder** i menyn Partner Center och välj sedan den kund vars enheter du vill hantera.
3. Välj **enheter** på kundens informations sida.
4. Under **Använd profiler** på enheter väljer du **Lägg till enheter**.
5. Ange **Microsoft365Managed_Autopilot** för grupp namnet och välj sedan **Bläddra** för att överföra kundens lista (i CSV-format) till Partner Center.


> [!IMPORTANT]
> Grupp namnet måste matcha **Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken. Detta gör att de nyligen registrerade enheterna kan kopplas till den autopilot-profil för Microsoft Managed Desktop.

>[!NOTE]
> Du bör ha tagit emot denna. csv-fil med din enhets köp. Om du inte får en. csv-fil kan du skapa en själv genom att följa anvisningarna i [lägga till enheter i Windows autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). Windows PowerShell-skriptet skiljer sig från det som används för [Microsoft Managed Desktop admin-portalen](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). Partner bör använda [Get-windowsautopilotinfohttps:](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att registrera enheter för Microsoft Managed Desktop-enheter i Partner Center.

Om du får ett fel meddelande när du försöker överföra. csv-filen bör du kontrol lera fil formatet. Kontrol lera att kolumn beställningen matchar vad som beskrivs i [använda Windows autopilot-profiler på nya enheter för att anpassa en kunds välkomst upplevelse](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account). Du kan också använda exempel filen. csv från länken bredvid **Lägg till enheter** för att skapa en enhets lista. 

Mer information om autopilot i partner scenarier finns i [lägga till enheter till en kunds konto](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrera enheter med hjälp av OEM API

Innan registreringen av en kund är klar måste du först etablera en relation med dem. Du bör ha en unik länk för dina kunder. Lär dig [hur du etablerar OEM-relationer](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

När du har fastställt relationen kan du börja registrera enheter för kunder som använder grupp tag gen **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> Grupp namnet måste matcha **Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken. Detta gör att de nyligen registrerade enheterna kan kopplas till den autopilot-profil för Microsoft Managed Desktop.
