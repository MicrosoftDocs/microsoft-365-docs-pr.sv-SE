---
title: Steg för partner för att registrera enheter
description: Hur partners kan registrera enheter så att de kan hanteras av Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689239"
---
# <a name="steps-for-partners-to-register-devices"></a>Steg för partner för att registrera enheter


I den här artikeln beskrivs stegen som partner kan följa för att registrera enheter. Hur du registrerar enheter själv finns i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Förbereda för registrering 
Innan du kan slutföra registreringen för en kund måste du först upprätta en relation med kunden i [Partnercenter.](https://partner.microsoft.com/dashboard) Mer information [om processen](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) finns i dokumentationen till medgivandet. Partner som är partner för CSP kan lägga till enheter åt en kund, så länge kunden har gett sitt samtycke. Du kan också läsa mer om partnerrelationer och Autopilot-behörigheter i [Hjälp om Partnercenter.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Den här dokumentationen gäller endast partner och OEM-maskiner. Processen för självregistrering har dokumenterats i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrera enheter med hjälp av Partnercenter

När du har upprättat relationen med dina kunder kan du använda Partnercenter och lägga till enheter på Autopilot för alla kunder som du har en relation med genom att följa de här stegen:

1. Gå till [Partnercenter](https://partner.microsoft.com/dashboard)
2. Välj **Kunder** på Menyn Partnercenter och välj sedan den kund vars enheter du vill hantera.
3. Välj Enheter på kundens **informationssida.**
4. Under **Använd profiler på** enheter väljer du Lägg till **enheter**.
5. Ange rätt grupptagg för den enhetsprofil du har valt (enligt följande  tabell) och välj sedan Bläddra för att ladda upp kundens lista (i CSV-filformat) till Partner Center.

|[Enhetsprofil](../service-description/profiles.md)  |Grupptagg  |
|---------|---------|
|Känsliga data     |**Microsoft365Managed \_ SensitiveData**    |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> Gruppnamnet måste matcha de som anges i tabellen exakt, inklusive versaler och specialtecken. Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.

>[!NOTE]
> Du borde ha fått den här CSV-filen med ditt enhetsköp. Om du inte har fått någon CSV-fil kan du skapa en själv genom att följa stegen i Lägga till [enheter i Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Windows PowerShell-skriptet är inte samma som det som används för [Microsoft Managed Desktop Admin-portalen.](./register-devices-self.md#obtain-the-hardware-hash) Partners bör använda [Get-WindowsAutoPilotInfo för](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) att registrera enheter för Microsoft Managed Desktop-enheter i Partner Center.

Om du får ett felmeddelande när du försöker ladda upp CSV-filen kontrollerar du formatet på filen. Se till att kolumnordningen stämmer överens med vad som beskrivs i Använda [Windows Autopilot-profiler](/partner-center/autopilot#add-devices-to-a-customers-account)på nya enheter för att anpassa en kunds användning. Du kan också använda csv-exempelfilen från länken bredvid Lägg **till enheter för** att skapa en enhetslista. 

Mer information om Autopilot i partnerscenarier finns i [Lägga till enheter till en kunds konto.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrera enheter med hjälp av OEM API

Innan du slutför registreringen för en kund måste du först upprätta en relation med kunden. Du bör ha en unik länk som du kan ge till dina respektive kunder. Se [Så här upprättar du EN OEM-relation.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

När du har upprättat relationen kan du börja registrera enheter för kunder med hjälp av rätt grupptagg för varje enhetsprofil som de har valt:


|Enhetsprofil  |Grupptagg  |
|---------|---------|
|Känsliga data     | **Microsoft365Managed \_ SensitiveData**     |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> Grupptaggarna måste matcha de som anges i tabellen exakt, inklusive versaler och specialtecken. Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.