---
title: Hur mappar skyddsfunktioner i Microsoft 365 Business Premium till Intune-inställningarna
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Lär dig hur skyddsfunktioner i Microsoft 365 Business Premium mappar till Intune-inställningar. Prenumerationen ger dig en licens för att ändra Intune-inställningarna.
ms.openlocfilehash: 5e8a7aa570b0f56324a483fb2cdb77c19f3b2379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913031"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Hur mappar skyddsfunktioner i Microsoft 365 Business Premium till Intune-inställningarna

## <a name="android-and-ios-application-protection-settings"></a>Skyddsinställningar för Android- och iOS-appar

Följande tabell visar hur principinställningar för Android- och iOS-appar mappas till Intune-inställningar.
  
Du hittar Intune-inställningen genom att logga in med dina autentiseringsuppgifter som administratör för Microsoft 365 Business Premium och gå till Administrationscenter och sedan **Intune**.
  
 > [!IMPORTANT]
 > 
 > En Microsoft 365 Business Premium-prenumeration ger dig en licens för att ändra alla Intune-inställningar. Se [Introduktion till Intune för att komma igång.](/intune/introduction-intune)
  
Välj det principnamn du vill &mdash; använda, till exempel Programprincip för &mdash; Android, och välj sedan **Principinställningar**.
  
Under **Skydda filer om enheter försvinner eller blir stulna**
  
|**Inställningen för Android- eller iOS-program**|**Intune-inställning(ar)**|
|:-----|:-----|
|Ta bort arbetsﬁler från en inaktiv enheten efter  <br/> |Offlineintervall (dagar) innan appdata rensas  <br/> |
|Tvinga användare att spara alla filer i OneDrive för företag  <br/> Observera att endast OneDrive för företag är tillåtet  <br/> |Välj med vilka lagringtjänster företagsdata ska sparas  <br/> |
|||
   
Under **Hantera hur användare kommer åt Office-filer på mobila enheter**
  
|**Inställningen för Android- eller iOS-program**|**Intune-inställning(ar)**|
|:-----|:-----|
|Ta bort arbetsﬁler från en inaktiv enheten efter  <br/> |Offlineintervall (dagar) innan appdata rensas  <br/> |
|Tvinga användare att spara alla filer i OneDrive för företag  <br/> Observera att endast OneDrive för företag är tillåtet  <br/> |Välj med vilka lagringtjänster företagsdata ska sparas  <br/> |
|Kryptera arbetsfiler  <br/> |Kryptera appdata  <br/> |
|Under **Hantera hur användare kommer åt Office-filer på mobila enheter** <br/> ||
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> | Kräv PIN för åtkomst  <br/>  Här anges även:  <br/> **Tillåt enkel PIN** till **Ja** <br/> **Längd på PIN-kod** till 4  <br/> **Tillåt fingeravtryck i stället för PIN** till **Ja** <br/> **Inaktivera appens PIN-kod när enhetens PIN-kod hanteras** till **Nej** <br/> |
|Återställ PIN-kod när inloggning misslyckas så här många gånger (det här är inaktiverat om PIN-kod inte krävs)  <br/> |Antal försök innan PIN-koden återställs  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva i (det här är inaktiverat om PIN-kod inte krävs)  <br/> | Kontrollera åtkomstkraven igen efter (minuter)  <br/>  Här anges även:  <br/> **Timeout** är inställt på minuter  <br/>  Det här är samma antal minuter som du angav i Microsoft 365 Business.  <br/> **Offline respitperiod** är inställt på 720 minuter som standard  <br/> |
|Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter  <br/> |Blockera hanterade appar från att köras på jailbrokade eller rotade enheter  <br/> |
|Tillåt användare att kopiera innehåll från Office-program till personliga program  <br/> | Begränsa klippa ut, kopiera och klistra in med andra appar  <br/>  Om alternativet Microsoft 365 Business Premium är inställt på **På** ställs de här tre alternativen även in på **Alla appar** i Intune:  <br/> **Tillåt att appen överför data till andra appar** <br/> **Tillåt att appen tar emot data från andra appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** <br/>  Om alternativet Microsoft 365 Business är **På** ställs alla Intune-alternativ in så här:  <br/> **Tillåt att appen överför data till andra appar** är inställt på **Principhanterade appar** <br/> **Tillåt att appen tar emot data från andra appar** är inställt på **Alla appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** är inställt på **Principhanterade appar med inklistring** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Skyddsinställningar för Windows 10-appar

Följande tabell visar hur principinställningar för Windows 10-appar mappas till Intune-inställningar.
  
Du hittar Intune-inställningen genom att logga in med dina autentiseringsuppgifter som administratör för Microsoft 365 Business Premium och gå till [Azure Portal.](https://portal.azure.com) Välj **Fler tjänster** och skriv Intune i **Filter.** Välj **Appprincip för Intune-appskydd.** \> 
  
 > [!IMPORTANT]
 >
 >En Microsoft 365 Business Premium-prenumeration ger dig en licens för att ändra endast de Intune-inställningar som mappas till inställningarna i Microsoft 365 Business Premium. 
  
Om du vill utforska de tillgängliga inställningarna väljer du det principnamn du vill använda och  väljer sedan **Allmänt, Tilldelningar,** Tillåtna **appar,** Undantagna **appar,** Nödvändiga inställningar eller Avancerade inställningar i det vänstra navigeringsfönstret. 
  
|**Principinställningen för Windows 10-program**|**Intune-inställning(ar)**|
|:-----|:-----|
|Kryptera arbetsfiler  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Återkalla krypteringsnycklar vid avregistrering** och **Återkalla åtkomst till skyddade data när enheten registreras i MDM** är båda **På**.  <br/> |
|Förhindra användare från att kopiera företagsdata till personliga filer.  <br/> |**Nödvändiga inställningar** \> **Läget för Windows informationsskydd**. **På** i Microsoft 365 Business Premium mappar du till: **Dölj** åsidosättningar **,** Av i Microsoft 365 Business Premium kartor till: **Av**.  <br/> |
|Åtkomstkontroll för Office-dokument  <br/> | Om detta är inställt **på På** i Microsoft 365 Business Premium  <br/> **Avancerade inställningar** \> **Åtkomst**, **Använd Windows Hello för företag som inloggningsmetod för Windows** är **På**, med följande ytterligare inställningar:  <br/> **Ange lägsta antal tillåtna tecken för PIN-kod** är inställt på **4**.  <br/> **Ställ in användning av versaler i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av versaler för PIN-kod**.  <br/> **Ställ in användning av gemener i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av gemener för PIN-kod**.  <br/> **Ställ in användning av specialtecken i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av specialtecken för PIN-kod**.  <br/> **Ange tidsperiod (i dagar) som** en PIN-kod kan användas innan användaren måste ändras är inställd på **0.**  <br/> **Ange antalet tidigare PIN-koder som kan kopplas till ett användarkonto och som inte kan återanvändas** är inställt på **0**.  <br/> **Antal autentiseringsförsök som tillåts innan enheten rensas** anges till samma som i Microsoft 365 Business (5 som standard).  <br/> **Maximal tid (i minuter) som får passera innan en aktiv enhet låses med PIN-kod eller lösenord** anges till samma som i Microsoft 365 Business.  <br/> |
|Aktivera återställning av skyddade data  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Visa symbol för företagsdataskydd** och **Använd Azure RMS för Windows informationsskydd** är **På**.  <br/> |
|Skydda ytterligare företagsmolnplatser  <br/> |**Avancerade inställningar** \> **Skyddade domäner** och **Molnresurser** visar domäner och SharePoint-webbplatser.  <br/> |
|Filer som används av de här apparna är skyddade  <br/> |Listan med skyddade appar finns i **Tillåtna appar**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Skyddsinställningar för Windows 10-enheter

Följande tabell visar hur konfigurationsinställningar för Windows 10-enheter mappas till Intune-inställningar.
  
Du hittar Intune-inställningen genom att logga in med dina administratörsautentiseringsuppgifter för Microsoft 365 Business Premium och gå till [Azure-portalen,](https://portal.azure.com)välja Fler tjänster och skriva in Intune i **Filter**, välja Intune-enhetskonfigurationsprofiler.  \>  \>  Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Principinställning för Windows 10-enhet**|**Intune-inställning(ar)**|
|:-----|:-----|
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Tillåt övervakning i realtid = PÅ  <br/> Tillåt molnskydd = PÅ  <br/> Be användarna att skicka exempel = Skicka säkra exempel automatiskt (standard är automatiskt skickad information som är icke personligt identifierbar)  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |**SmartScreen** i **webbläsarinställningar för Edge** är inställt på **Krävs**.  <br/> |
|Stäng av enhetens skärm när datorn varit inaktiv i (minuter)  <br/> |Maximalt antal minuter av inaktivitet innan skärmen låses (minuter)  <br/> |
|Tillåt användare att hämta appar från Microsoft Store  <br/> |Anpassad URI-princip  <br/> |
|Tillåt användare att använda Cortana  <br/> |**Allmänt** \> **Cortana** är inställd på **blockering** i Intune när **inaktiverat** i Microsoft 365 Business Premium.  <br/> |
|Tillåt användare att ta emot Windows-tips och reklam från Microsoft  <br/> |**Windows spotlight**, allt blockerat om detta är inställt **på av** i Microsoft 365 Business Premium.  <br/> |
|Håll Windows 10-enheter uppdaterade automatiskt  <br/> | Den här inställningen finns i Uppdateringar för **Microsoft Intune-tjänsten** \> **– Windows 10-uppdateringsringar,** välj **Uppdateringsprincip för Windows 10-enheter** och sedan **Egenskaper** \> **Inställningar.**  <br/>  När Inställningen Microsoft 365 Business Premium är inställd på **På** ställs alla följande inställningar in:  <br/> **Tjänstgren** är inställt **på CB** (CBB när det är inaktiverat i Microsoft 365 Business Premium).  <br/> **Microsoft-produktuppdateringar** är inställt på **Tillåt**.  <br/> **Windows-drivrutiner** är inställt på **Tillåt**.  <br/> **Funktionssätt för automatisk uppdatering** är inställt på **Installera automatiskt vid underhåll** med:  <br/> **Starttid för aktiva timmar** är inställt på **06:00**.  <br/> **Sluttid för aktiva timmar** är inställt på **22:00**.  <br/> **Uppskjutningsperiod för kvalitetsuppdatering (dagar)** är inställt på **0**.  <br/> **Uppskjutningsperiod för funktionsuppdatering (dagar)** är inställt på **0**.  <br/> **Nedladdningsläge för leveransoptimering** är inställt på **HTTP blandat med peering bakom samma NAT**.  <br/> |
|||
