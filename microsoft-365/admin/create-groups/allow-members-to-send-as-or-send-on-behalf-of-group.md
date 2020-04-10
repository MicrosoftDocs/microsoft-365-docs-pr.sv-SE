---
title: Tillåt medlemmar att skicka som eller skicka för en grupp
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Lär dig hur du tillåter medlemmar att skicka e-post som en Office 365-grupp eller skicka e-post för en Office 365-grupp.
ms.openlocfilehash: b85b0318587058f1c3eb4d681086ccfcad7f1d8d
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212111"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Tillåt medlemmar att skicka som eller skicka för en grupp

En medlem i en Office 365-grupp som har beviljats **send as** eller **Skicka för räkning** kan skicka e-post som grupp eller för gruppens räkning. I det här avsnittet beskrivs hur en administratör kan ange dessa behörigheter.
  
Om Megan Bowen till exempel ingår i gruppen **Utbildningskontor** 365 och har **Skicka som** behörigheter för gruppen, om hon skickar ett e-postmeddelande som grupp, ser det ut som att gruppen **Utbildning** har skickat e-postmeddelandet. 
  
Med behörigheten **Skicka för räkning** kan en användare skicka e-post för en Office 365-grupp. Om Alex Wilber till exempel ingår i gruppen **Marknadsföringskontor** 365 och har behörigheter **för skicka för räkning** och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det skickades av Alex **Wilber för marknadsföring**.

> [!IMPORTANT]
> Du kan konfigurera **Skicka som** eller **Skicka för** en viss användare, men inte båda. Om du konfigurerar båda, kommer det att standard **skicka som**.

> [!TIP]
> Se [Skicka e-post från eller på uppdrag av en Office 365-grupp](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) om du vill lära dig hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Tillåt medlemmar att skicka e-post som en grupp

I det här avsnittet beskrivs hur du tillåter användare att skicka e-post som en grupp i [Administrationscenter](https://go.microsoft.com/fwlink/p/?linkid=2059104) för Exchange (EAC) i Exchange Online.
  
1. Gå till Mottagare **grupper**i \> **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange</a>.
    
2. Välj **Ikonen**![Redigera](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera grupp i gruppen som du vill tillåta användare att skicka som.   
    
3. Välj **gruppdelegering**.
    
4. I avsnittet **Skicka som** **+** markerar du tecknet för att lägga till de användare som du vill skicka som grupp. 
    
    ![Välj plustecknet för att lägga till de användare som du vill skicka som Office 365-grupp](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv om du vill söka eller välja en användare i listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Tillåt medlemmar att skicka e-post för en grupp

I det här avsnittet beskrivs hur du tillåter användare att skicka e-post för en grupp i Administrationscenter för Exchange (EAC) i Exchange Online.
  
1. Gå till Mottagare **grupper**i \> **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange</a>.
    
2. Välj **Edit** ![Ikonen Redigera](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera grupp på den grupp som du vill tillåta användare att skicka som. 
    
3. Välj **gruppdelegering**.
    
4. I avsnittet Skicka för räkning **+** väljer du tecknet för att lägga till de användare som du vill skicka som grupp. 
    
    ![Välj plustecknet för att lägga till de användare som du vill skicka som Office 365-grupp](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv om du vill söka eller välja en användare i listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Relaterade artiklar

[Läs mer om Office 365-grupper](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[TilläggstilläggPrebehörigheter](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
