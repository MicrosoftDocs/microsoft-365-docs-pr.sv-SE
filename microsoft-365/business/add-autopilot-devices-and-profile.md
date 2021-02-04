---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag så att de är redo att användas av de anställda.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099759"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler

Du kan använda Windows AutoPilot för att konfigurera nya **Windows** 10-enheter för företaget så att de är redo att användas när du ger dem till dina anställda.
  
## <a name="device-requirements"></a>Enhetskrav

Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare
    
- Nya enheter som inte har använts direkt i Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Använda installationsguiden för att skapa enheter och profiler

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Om du inte har skapat enhetsgrupper eller profiler ännu är det bästa sättet att komma igång genom att använda steg-för-steg-guiden. Du kan också [lägga till enheter](create-and-edit-autopilot-devices.md) och tilldela [profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden. 
  
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Välj Devices AutoPilot i det **vänstra** \> **navigeringsfönstret.**

    ![I administrationscentret väljer du enheter och sedan AutoPilot.](../media/AutoPilot.png)
  
2. Klicka eller tryck på Start-guiden på **sidan** **AutoPilot.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. På sidan **Ladda upp CSV-fil med lista över** enheter bläddrar du till en plats där du har förberett den. CSV-fil och **sedan Öppna** \> **nästa.** Filen måste ha tre rubriker:
    
    - Kolumn A: Enhetsserienummer
    
    - Kolumn B: Produkt-ID för Windows
    
    - Kolumn C: Maskinvaruhash
    
    Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo för](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) att generera en CSV-fil. 
    
    Mer information finns i [CSV-filen med enhetslistan](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**. 
    
> [!NOTE]
> Det här skriptet använder WMI för att hämta egenskaper som krävs för att en kund ska registrera en enhet med Windows Autopilot. Observera att det är normalt att den resulterande CSV-filen inte samlar in ett PKID-värde (Windows Product ID), eftersom det inte krävs för att registrera en enhet och PKID som är NULL i CSV-utdata är helt okej. Endast serienumret och maskinvaruhashen fylls i.
    
4. På sidan **Tilldela en profil** kan du antingen välja en befintlig profil eller skapa en ny. Om du inte redan har en uppmanas du att skapa en. 
    
    En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.
    
    Standardfunktionerna är obligatoriska och ställs in automatiskt. Standardfunktionerna är följande:
    
    - Hoppa över Cortana, OneDrive och OEM-registrering.
    
    - Skapa inloggning med företagets varumärke.
    
    - Anslut dina enheter till Azure Active Directory-konton och registrera dem automatiskt så att de hanteras av Microsoft 365 Business Premium.
    
    Mer information finns i Om [AutoPilot-profilinställningar.](autopilot-profile-settings.md) 
    
5. Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard. 
    
    Välj **Nästa**.
    
6. **Du är klar anger** att profilen du skapade (eller valde) kommer att tillämpas på enhetsgruppen som du skapade genom att ladda upp listan med enheter. Inställningarna börjar gälla nästa gång enhetens användare loggar in. Välj **Stäng**.
    
