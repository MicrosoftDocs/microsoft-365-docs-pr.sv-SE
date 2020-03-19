---
title: Tillåt medlemmar att skicka som eller skicka på uppdrag av en grupp
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
description: Läs om hur du tillåter medlemmar att skicka e-post som en Office 365-grupp eller skicka e-post för en Office 365-grupp.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808315"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Tillåt medlemmar att skicka som eller skicka på uppdrag av en grupp

En medlem i en Office 365-grupp som har beviljats behörigheten **Skicka som** eller **Skicka för** kan nu skicka e-post som gruppen eller åt hela gruppen. I det här avsnittet beskrivs hur en administratör kan ange dessa behörigheter.
  
Om Megan Bowen till exempel ingår i **utbildningsoffice** 365-gruppen och har **Skicka som** behörigheter för gruppen, om hon skickar ett e-postmeddelande som grupp, kommer det att se ut som **att utbildningsgruppen** har skickat e-postmeddelandet. 
  
Med behörigheten **Skicka för** kan användare skicka e-post för Office 365-gruppens räkning. Om Alex Wilber till exempel är en del av **Marketing** Office 365 Group och har **behörigheten Skicka för räkning** och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det skickades av Alex **Wilber på uppdrag av Marknadsföring**.

> [!IMPORTANT]
> Du kan konfigurera **Skicka som** eller **Skicka för** en viss användare, men inte båda. Om du konfigurerar båda, kommer det som standard att **skicka som**.

> [!TIP]
> Läs stegen i [Skicka e-post från eller på uppdrag av en Office 365-grupp](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) om du vill lära dig hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Tillåt medlemmar att skicka e-post som grupp

I det här avsnittet beskrivs hur du tillåter användare att skicka e-post som grupp i [Administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2059104) för Exchange (EAC) i Exchange Online.
  
1. Gå till **mottagargrupper**i \> **administrationscentret** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">för Exchange.</a>
    
2. Välj **Redigera**![gruppikon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i Grupp som du vill tillåta användare att skicka som.   
    
3. Välj **gruppdelegering**.
    
4. Markera **Send As** tecknet **+** i avsnittet Skicka som om du vill lägga till de användare som du vill skicka som gruppen. 
    
    ![Välj plustecknet om du vill lägga till de användare som du vill skicka som Office 365-grupp](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv för att söka eller välja en användare från listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Tillåt medlemmar att skicka e-post för en grupps räkning

I det här avsnittet beskrivs hur du tillåter användare att skicka e-post för en grupp i Administrationscentret för Exchange (EAC) i Exchange Online.
  
1. Gå till **mottagargrupper**i \> **administrationscentret** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">för Exchange.</a>
    
2. Välj **Redigera** ![redigera gruppikon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i den grupp som du vill tillåta användare att skicka som. 
    
3. Välj **gruppdelegering**.
    
4. Markera tecknet **+** i avsnittet Skicka för räkning för att lägga till de användare som du vill skicka som gruppen. 
    
    ![Välj plustecknet om du vill lägga till de användare som du vill skicka som Office 365-grupp](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Sök efter eller välj en användare i listan. Välj **OK** och **Spara**.
    
    ![Skriv för att söka eller välja en användare från listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Relaterade artiklar

[Läs mer om Office 365-grupper](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Behörighet för lägg till mottagare](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
