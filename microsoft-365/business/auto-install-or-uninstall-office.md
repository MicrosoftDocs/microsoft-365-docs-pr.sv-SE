---
title: Installera och avinstallera Office automatiskt på Windows 10-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Installera eller avinstallera Office på Windows 10-enheter från Microsoft 365 Business Admin Center. '
ms.openlocfilehash: 70fd2f1ded87e04f506b1ba415c820af5d535938
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37121267"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Installera och avinstallera Office automatiskt på Windows 10-enheter

[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Du kan snabbt och enkelt installera Office på datorer med Windows 10 från Microsoft 365 Business Administrationscenter.
  
Om du vill veta mer om hur det fungerar med tidigare installerade Office-program kan du läsa [Förbered för installation av Office-klienten](prepare-for-office-client-deployment.md) innan du sätter igång. 
  
## <a name="manage-office-deployments"></a>Hantera Office-distribution

1. Logga in på [Administrationscenter](https://aka.ms/bcsportal) som global administratör. 
    
2. På kortet **Enheter** väljer du **Hantera Office-distribution**.
      Om **enhets åtgärds** kortet inte visas klickar du på **Lägg** till (+) på **Start** sidan för administratörscenter för att lägga till det i administratörs hemmet.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. I fönstret **Hantera Office distribution** som öppnas väljer du **Lägg till en grupp** och markerar de grupper som du vill använda.
    
4. När du har lagt till den eller de grupper som du vill använda väljer du antingen **Installera Office så snart som möjligt** eller **Avinstallera Office** i listrutan **Distributionsåtgärd**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Välj **Nästa** \> granska inställningarna och välj sedan **Bekräfta**.
    
32-bitarsversionen av Office installeras/avinstalleras automatiskt på de enheter som ägs av användare som ingår i gruppen eller grupperna du valde.
  
För att bekräfta åtgärden kan du öppna Aktivitetshanteraren på en dator som har angivits för Office-installation och leta processen Microsoft Office Klicka-och-kör.
  


