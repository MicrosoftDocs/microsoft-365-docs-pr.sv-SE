---
title: Tillåta medlemmar att skicka som eller skicka för en grupp
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: Lär dig hur du tillåter att gruppmedlemmar skickar e-post som Microsoft 365-grupp eller skickar e-post åt en Microsoft 365 grupp.
ms.openlocfilehash: 437040700361c6a09b107a87d8228d2a156375d1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926145"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Tillåta medlemmar att skicka som eller skicka för en grupp

En medlem i Microsoft 365 grupp som har  beviljats  behörigheten Skicka som eller Skicka för kan skicka e-post som gruppen eller åt hela gruppen. (Gäster i gruppen kan inte beviljas de här behörigheterna.)

I den här artikeln förklaras hur en Exchange administratör kan ange de här behörigheterna.
  
Om Till exempel Bow Bowen ingår i gruppen Utbildning  **Microsoft 365** och har behörigheten Skicka som för gruppen, och hon  skickar ett e-postmeddelande som gruppen, ser det ut som att gruppen Utbildning har skickat e-postmeddelandet. 
  
Med **behörigheten Skicka för** kan användare skicka e-post åt en Microsoft 365 grupp. Om exempelvis Alex Wilber ingår i gruppen Marknadsföring **Microsoft 365** och  har behörigheten Skicka för och skickar ett e-postmeddelande som gruppen, ser e-postmeddelandet ut som om det skickades av Alex Wilber på uppdrag av **Marknadsföring.**

> [!IMPORTANT]
> Du kan konfigurera **Skicka som** eller Skicka **för en** viss användare, men inte båda. Om du konfigurerar båda inställningarna används Skicka **som som som standard.**

> [!TIP]
> Läs [Skicka e-post från](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) eller åt en Microsoft 365-grupp om du vill veta hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Tillåt medlemmar att skicka e-post som en grupp

I det här avsnittet förklaras hur du tillåter att användare skickar [e-post som](https://go.microsoft.com/fwlink/p/?linkid=2059104) en grupp Exchange administrationscentret (EAC) i Exchange Online.
  
1. Gå <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">till Exchange i</a> **administrationscentret.** \> 
    
2. Välj **Redigera** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) grupp-ikonen för den grupp som du vill tillåta användare att skicka som.   
    
3. Välj **gruppdelegering**.
    
4. I avsnittet **Skicka som** väljer du tecknet för att lägga till de användare som du vill skicka **+** som grupp. 
    
    ![Skärmbild av dialogrutan Skicka som](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv om du vill söka efter eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Tillåta medlemmar att skicka e-post för en grupp

I det här avsnittet förklaras hur du tillåter att användare skickar e-post för en grupp i administrationscentret för Exchange (EAC) i Exchange Online.
  
1. Gå <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">till Exchange i</a> **administrationscentret.** \> 
    
2. Välj **Redigera** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) grupp-ikonen för den grupp som du vill tillåta användare att skicka som. 
    
3. Välj **gruppdelegering**.
    
4. I avsnittet Skicka för väljer du tecknet **+** för att lägga till de användare som du vill skicka som grupp. 
    
    ![Skärmbild av dialogrutan Skicka för](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv om du vill söka efter eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Relaterade artiklar

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Läs mer om Microsoft 365 grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)