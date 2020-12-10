---
title: Tillåta medlemmar att skicka som eller skicka för en grupp
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Lär dig hur du tillåter att medlemmar skickar e-post som en Microsoft 365-grupp eller skickar e-post åt en Microsoft 365-grupp.
ms.openlocfilehash: 2abf0668411ccd08db5bbd8408605dcd0aa2d832
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613578"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Tillåta medlemmar att skicka som eller skicka för en grupp

En medlem i en Microsoft 365-grupp som har behörighet att **Skicka som** eller **Skicka för ombud** kan skicka e-post som grupp eller åt gruppen. I den här artikeln förklaras hur en administratör kan ange behörigheter.
  
Om till exempel Megan Bowen är en del av Microsoft 365-gruppen **utbildning** och har **Send as** -behörighet för gruppen, om hon skickar ett e-postmeddelande som grupp, ser det ut som **utbildnings** gruppen skickade e-postmeddelandet. 
  
Med behörigheten **Skicka åt** kan en användare skicka e-post åt en Microsoft 365-grupp. Till exempel, om Alex Wilber är en del av Microsoft 365-gruppen för **marknadsföring** och har behörigheten **Skicka för** användare och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det har skickats av **Alex Wilber för marknadsförings räkning**.

> [!IMPORTANT]
> Du kan konfigurera **Skicka som** eller **Skicka** för en given användare, men inte båda. Om du konfigurerar båda är det standard att **Skicka som**.

> [!TIP]
> Mer information om hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp finns i [skicka e-post från eller på uppdrag av en Microsoft 365-grupp](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) .
    
## <a name="allow-members-to-send-email-as-a-group"></a>Tillåt att medlemmar skickar e-post som en grupp

I det här avsnittet förklaras hur du tillåter att användare skickar e-post som en grupp i [administrations centret för Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (UK) i Exchange Online.
  
1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>går du till gruppen **mottagare** \> .
    
2. Välj **Redigera** ![ ikonen Redigera grupp ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i gruppen som du vill tillåta användare att skicka som.   
    
3. Välj **gruppdelegering**.
    
4. I avsnittet **Skicka som** väljer du **+** tecknet för att lägga till de användare som du vill skicka som grupp. 
    
    ![Skärm bild av dialog rutan Skicka som](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv för att söka eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Tillåt att medlemmar skickar e-post åt en grupp

I det här avsnittet förklaras hur du tillåter att användare skickar e-post för en grupp i administrations centret för Exchange (UK) i Exchange Online.
  
1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>går du till gruppen **mottagare** \> .
    
2. Välj **Redigera** ![ ikonen Redigera grupp ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i gruppen som du vill tillåta användare att skicka som. 
    
3. Välj **gruppdelegering**.
    
4. I avsnittet Skicka för väljer du **+** tecknet för att lägga till de användare som du vill skicka som grupp. 
    
    ![Skärm bild av dialog rutan Skicka för](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv för att söka eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Relaterade artiklar

[Planerings steg-för-steg-samarbete för samarbets styrning](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa en plan för hantering av samarbete](collaboration-governance-first.md)

[Lär dig mer om Microsoft 365-grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-Unifiedgrouphttps](https://go.microsoft.com/fwlink/p/?LinkId=616189)
