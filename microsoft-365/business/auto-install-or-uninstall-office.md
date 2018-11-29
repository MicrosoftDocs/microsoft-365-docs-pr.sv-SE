---
title: Installera och avinstallera Office automatiskt på Windows 10-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Installera eller avinstallera Office på Windows 10 enheter från Microsoft 365 Business administratörscenter. '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983339"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Installera och avinstallera Office automatiskt på Windows 10-enheter

Du kan snabbt och enkelt installera Office på datorer med Windows 10 från Microsoft 365 Business Administrationscenter.
  
Om du vill veta mer om hur det fungerar med tidigare installerade Office-program kan du läsa [Förbered för installation av Office-klienten](prepare-for-office-client-deployment.md) innan du sätter igång. 
  
## <a name="manage-office-deployments"></a>Hantera Office-distribution

1. Logga in på [Administrationscenter](https://aka.ms/bcsportal) som global administratör. 
    
2. Välj **Hantera distribution av Office**på **enheter** -kort.    Om du inte ser **enheten åtgärder** -kort klickar du på **Lägg till** (+) om du vill lägga till den i hemmet admin admin center **Hem** på sidan.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. I fönstret **Hantera Office distribution** som öppnas väljer du **Lägg till en grupp** och markerar de grupper som du vill använda.
    
4. När du har lagt till den eller de grupper som du vill använda väljer du antingen **Installera Office så snart som möjligt** eller **Avinstallera Office** i listrutan **Distributionsåtgärd**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Välj **Nästa** \> granska inställningarna och välj sedan **Bekräfta**.
    
32-bitarsversionen av Office installeras/avinstalleras automatiskt på de enheter som ägs av användare som ingår i gruppen eller grupperna du valde.
  
För att bekräfta åtgärden kan du öppna Aktivitetshanteraren på en dator som har angivits för Office-installation och leta processen Microsoft Office Klicka-och-kör.
  


