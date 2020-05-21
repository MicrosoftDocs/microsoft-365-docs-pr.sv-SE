---
title: Steg för partner för att registrera enheter
description: Så här registrerar partner enheter så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327062"
---
# <a name="steps-for-partners-to-register-devices"></a>Steg för partner för att registrera enheter


I det här avsnittet beskrivs stegen för partner att följa för att registrera enheter. Processen för att registrera enheter själv dokumenteras själv i [Registrera enheter i Microsoft Managed Desktop själv](register-devices-self.md).



## <a name="prepare-for-registration"></a>Förbered för registrering 
Innan du slutför registreringen för en kund måste du först upprätta en relation med dem i [Partnercenter](https://partner.microsoft.com/dashboard). Mer information om den processen finns i dokumentationen för [medgivande.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) Alla CSP-partner kan lägga till enheter för alla kunders räkning, så länge kunden samtycker. Du kan också läsa mer om partnerrelationer och autopilotbehörigheter på [Partner Center hjälp](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Den här dokumentationen är endast för partners och OEM-tillverkare. Processen för självregistrering dokumenteras [själv](register-devices-self.md)i Registrera enheter i Microsoft Managed Desktop själv .


## <a name="register-devices-by-using-partner-center"></a>Registrera enheter med hjälp av Partner center

När du har etablerat relationen med dina kunder kan du utnyttja Partner Center för att lägga till enheter i Autopilot för någon av de kunder som du har en relation med genom att följa dessa steg:

1. Navigera till [Partnercenter](https://partner.microsoft.com/dashboard)
2. Välj **Kunder** på Partnercenter-menyn och välj sedan den kund vars enheter du vill hantera.
3. På kundens detaljsida väljer du **Enheter**.
4. Under **Använd profiler** på enheter väljer du Lägg till **enheter**.
5. Ange **Microsoft365Managed_Autopilot** för gruppnamnet och välj sedan **Bläddra** för att överföra kundens lista (i CSV-filformat) till Partnercenter.


> [!IMPORTANT]
> Gruppnamnet måste matcha **Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken. Detta gör det möjligt att tilldela de nyligen registrerade enheterna med Microsoft Managed Desktop Autopilot-profilen.

>[!NOTE]
> Du skulle ha fått den här CSV-filen när du köpte enheten. Om du inte har fått en CSV-fil kan du skapa en själv genom att följa stegen i [Lägga till enheter](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)i Windows Autopilot . Windows PowerShell-skriptet skiljer sig från det som används för [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). Partner bör använda [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att registrera enheter för Microsoft Managed Desktop-enheter i Partner Center.

Om du får ett felmeddelande när du försöker ladda upp CSV-filen kontrollerar du filens format. Du kan bara använda maskinvaruhhhen, oem-namn, serienummer och modell (i den kolumnordningen) eller Windows-produkt-ID. Du kan också använda exempelfilen CSV som finns från länken bredvid Lägg till **enheter** för att skapa en enhetslista. 

Mer information om Autopilot i partnerscenarier finns i [Lägga till enheter i en kunds konto](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrera enheter med hjälp av OEM-API:et

Innan du slutför registreringen för en kund måste du först upprätta en relation med dem. Du bör ha en unik länk för att ge till dina respektive kunder. Se [Hur du upprättar OEM-relation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

När du har etablerat relationen kan du börja registrera enheter **Microsoft365Managed_Autopilot**för kunder med Microsoft365Managed_Autopilot grupptagg.

> [!IMPORTANT]
> Gruppnamnet måste stämma **överens Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken. Detta gör det möjligt att tilldela de nyligen registrerade enheterna med Microsoft Managed Desktop Autopilot-profilen.
