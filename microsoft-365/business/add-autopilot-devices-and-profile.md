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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag.
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323104"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler

Du kan använda Windows AutoPilot för att konfigurera **nya** Windows 10-enheter för ditt företag så att de är klara att användas när du ger dem till dina anställda.
  
## <a name="device-requirements"></a>Enhetskrav

Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare
    
- Nya enheter som inte har gått igenom Windows out-of-Box-upplevelse
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Använda installationsguiden för att skapa enheter och profiler

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Om du inte har skapat enhetsgrupper eller profiler ännu, är det bästa sättet att komma igång med hjälp av steg-för-steg-guide. Du kan också [lägga till enheter](create-and-edit-autopilot-devices.md) och [tilldela profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden. 
  
1. Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. I det vänstra navigeringsfönstret väljer du **enheter** \> **autopilot**.

    ![I administratörscenter väljer du enheter och sedan AutoPilot.](media/AutoPilot.png)
  
2. På **Autopilotsidan** klickar eller knackar du på **Start Guide**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. På sidan **överför. csv-fil med listan över enheter** bläddrar du till en plats där du har den förberedd. CSV-fil och sedan **Öppna** \> **Nästa**. Filen måste ha tre rubriker:
    
    - Kolumn A: Enhetsserienummer
    
    - Kolumn B: Produkt-ID för Windows
    
    - Kolumn C: Maskinvaruhash
    
    Du kan hämta den här informationen från maskinvaruleverantören, eller så kan du använda [PowerShell-skriptet get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil. 
    
    Mer information finns i [CSV-filen med enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**. 
    
4. På sidan **tilldela en profil** kan du antingen välja en befintlig profil eller skapa en ny. Om du inte har en ännu, uppmanas du att skapa en. 
    
    En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.
    
    Standardfunktionerna är obligatoriska och ställs in automatiskt. Standardfunktionerna är följande:
    
    - Hoppa över Cortana, OneDrive och OEM-registrering.
    
    - Skapa inloggning med företagets varumärke.
    
    - Anslut dina enheter till Azure Active Directory-konton och registrera dem automatiskt för att hanteras av Microsoft 365 Business.
    
    Mer information finns i [om inställningar för autopilot-profil](autopilot-profile-settings.md). 
    
5. Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard. 
    
    Välj **Nästa**.
    
6. **Du är klar** anger att profilen som du skapade (eller valde) kommer att tillämpas på enhetsgruppen som du skapade genom att ladda upp listan över enheter. Inställningarna träder i kraft när enhetsanvändarna loggar in härnäst. Välj **Stäng**.
    