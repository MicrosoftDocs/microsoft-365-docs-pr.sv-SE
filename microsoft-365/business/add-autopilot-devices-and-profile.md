---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag.
ms.openlocfilehash: ee4b4a9b06c08b8f9456822b680542665c27baf3
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37121207"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler

Du kan använda Windows AutoPilot för att konfigurera **nya** Windows 10-enheter för ditt företag så att de är klara för produktiv användning så snart du ger dem till dina anställda.
  
## <a name="device-requirements"></a>Enhetskrav

Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare.
    
- Nya enheter som inte har genomgått Windows välkomstprogram.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Använda installationsguiden för att skapa enheter och profiler

[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Om du inte redan har skapat enhetsgrupper eller profiler kommer du enklast igång genom att använda dig av en guide med stegvisa anvisningar, men du kan även [lägga till enheter](create-and-edit-autopilot-devices.md) och [tilldela profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden. 
  
1. Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. På vänster nav väljer du **enheter** \> **autopilot**.

    ![I administratörscenter väljer du enheter och sedan AutoPilot.](media/AutoPilot.png)
  
2. På **Autopilotsidan** klickar eller knackar du på **Start Guide**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. På sidan för **uppladdning av CSV-fil med lista över enheter** bläddrar du till en plats där du har den förberedda CSV-filen. Klicka sedan på **Öppna** \> **Nästa**. Filen bör ha tre rubriker:
    
  - Kolumn A: Enhetsserienummer
    
  - Kolumn B: Produkt-ID för Windows
    
  - Kolumn C: Maskinvaruhash
    
    Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil. 
    
    Mer information finns i [CSV-filen med enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**. 
    
4. På sidan **Tilldela en profil** kan du välja en befintlig profil eller skapa en ny. Om du inte redan har en uppmanas du att skapa en ny. 
    
    En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.
    
    Standardfunktionerna är obligatoriska och ställs in automatiskt. Standardfunktionerna är följande:
    
  - Cortana-, OneDrive- och OEM-registrering hoppas över.
    
  - Skapa inloggning med företagets varumärke.
    
  - Enheterna ansluts till Azure Active Directory-konton och registreras automatiskt för att hanteras av Microsoft 365 Business.
    
    Mer information finns i
    
    [Om AutoPilot-profilinställningar](autopilot-profile-settings.md) . 
    
5. Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard. 
    
    Välj **Nästa**.
    
6. Sidan **Du är klar** visar att profilen du skapade (eller valde) kommer att användas för enhetsgruppen du skapade genom att ladda upp listan med enheter. De här inställningarna börjar gälla nästa gång enhetsanvändarna loggar in. Välj **Stäng**.
    