---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Validera Microsoft 365 Business-appskyddsinställningar på Windows 10-enheter och verifiera att användarna inte kan kopiera företagsdata till personliga filer eller appar som inte hanteras.
ms.openlocfilehash: 4d3d7e950311ac32606e700ebb35bf026ae091cc
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550006"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Bekräfta programskyddsinställningar på PC-datorer med Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Kontrollera att användarna inte kan kopiera företagsdata till personliga filer på företagets enheter

När du [ställt in principer för programskydd](protection-settings-for-windows-10-devices.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter. Om du har **aktiverat Förhindra** att **användare kopierar företagsdata till personliga filer och tvingar dem att spara arbetsfiler till OneDrive för företag** för företagsägda enheter kan du kontrollera detta på användarens enhet när de har anslutit till Azure AD och loggat in. 
  
 **Kontrollera anslutningsinställningar**
  
1. När du har loggat in med Microsoft 365 Business-autentiseringsuppgifter och anslutit till Azure AD enligt beskrivningen i [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) går du till **Windows-inställningar** \> **Konton** \> **Åtkomst till arbete eller skola**. Välj **Ansluten till \<innehavarnamn\> Azure AD** och välj sedan **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. På sidan **Hanterat efter** \<\> klientnamn kan du se **anslutningsinformationen** som innehåller en **hanteringsserveradress** som den som visas i följande bild. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Kontrollera att du inte kan klistra in företagsdata i en icke-hanterad app**
  
1. Öppna Outlook 2016 som installerades av Microsoft 365 Business.
    
2. Öppna ett e-postmeddelande och kopiera visst innehåll från det.
    
    Öppna Anteckningar och försök att klistra in innehållet där.
    
    Du får ett felmeddelande om att appen inte kan komma åt innehåll.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Du kan dock klistra in samma innehåll i Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Kontrollera att användarna inte kan kopiera företagsdata till personliga filer på personliga enheter

 **Kontrollera anslutningsinställningar**
  
1. På din personliga Windows 10-enhet där du är inloggad som lokal användare går du till **Windows-inställningar**och trycker på eller trycker på **Konton** \> **Åtkomst arbete eller skola**.
    
2. Välj **Anslut** under **Åtkomst till arbete eller skola**.
    
3. Ange dina Microsoft 365 Business-autentiseringsuppgifter i dialogrutan **Konfigurera ett arbets- eller skolkonto** \> **Logga in**.
    
4. På sidan **Åtkomst till arbetet eller skolan** väljer du **Arbets- eller skolkonto** och väljer sedan **Info**.
    
    ![Klicka eller tryck på Info i dialogrutan Arbete eller skolkonto.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. På sidan **Access-arbete eller skola** kan du se **anslutningsinformationen** som innehåller en **hanteringsserveradress** som den som visas i följande bild och innehåller orden *som raderar* och *mam* inuti. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Kontrollera att du inte kan klistra in företagsdata i en icke-hanterad app**
  
1. Öppna Outlook 2016 och lägg till ditt Microsoft 365 Business-konto om det behövs, och logga in med dina Microsoft 365 Business-autentiseringsuppgifter.
    
2. Öppna ett e-postmeddelande och kopiera visst innehåll från det.
    
    Öppna Anteckningar och försök att klistra in innehållet där.
    
    Du får ett felmeddelande om att Appen inte kan komma åt innehåll.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Du kan dock klistra in samma innehåll i Word 2016.
    

