---
title: Skapa och redigera AutoPilot-profiler
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Lär dig att skapa, redigera, ta bort eller ta bort AutoPilot profiler. '
ms.openlocfilehash: 85fc897b2f428afae8d55feeb577021adaa30f72
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277177"
---
# <a name="create-and-edit-autopilot-profiles"></a>Skapa och redigera AutoPilot-profiler

## <a name="create-a-profile"></a>Skapa en profil

En profil gäller för en enhet eller en grupp enheter.
  
1. Välj **enheter** i Microsoft 365 Business Admin center, \> **AutoPilot**.
  
2. Välj fliken **profiler** på sidan **AutoPilot** \> **Skapa profil**.
    
3. På sidan **Skapa profil** anger du ett namn för profilen som kan hjälpa dig att identifiera den, till exempel Marknadsföring. Aktivera inställningen som du vill använda (mer information finns i [Om AutoPilot-profilinställningar](autopilot-profile-settings.md)) och välj **Spara**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Använda profil på en enhet

När du har skapat en profil kan du använda den på en enhet eller en grupp av enheter. Du kan välja en befintlig profil i [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) och använda den på nya enheter, eller så kan du ersätta en befintlig profil för en enhet eller en grupp av enheter. 
  
1. På sidan för att **förbereda Windows** väljer du fliken **Enheter**. 
    
2. Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan en profil i listrutan **Tilldelad profil** \> **Spara**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Redigera eller ta bort en profil

När du har tilldelat en profil till en enhet kan du uppdatera den, även om du redan har gett enheten till en användare. När enheten ansluts till internet laddar den ned den senaste versionen av profilen under installationen. Om användaren återställer enheten till de förvalda inställningarna hämtar enheten på nytt de senaste uppdateringarna av profilen. 
  
### <a name="edit-a-profile"></a>Redigera en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Profiler**. 
    
2. Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** uppdaterar du någon av de tillgängliga inställningarna \> **Spara**.
    
    Om du gör detta innan någon användare ansluter enheten till internet används profilen för installationen.
    
### <a name="delete-a-profile"></a>Radera en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Profiler**. 
    
2. Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** klickar du på **Ta bort profil** \> **Spara**.
    
    När du raderar en profil tas den bort från en enhet eller en grupp av enheter som den var tilldelad till.
    
### <a name="remove-a-profile"></a>Ta bort en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Enheter**. 
    
2. Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan **Ingen** i listrutan **Tilldelad profil** \> **Spara**.
    
