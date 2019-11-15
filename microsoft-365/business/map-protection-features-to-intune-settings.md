---
title: Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna
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
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Läs om hur skyddsfunktioner i Microsoft 365 Business Map till Intune-inställningar. Prenumerationen ger dig en licens för att ändra Intune-inställningar.
ms.openlocfilehash: b7d87e9a174e942a6533ae034b4f4a551ae2159f
ms.sourcegitcommit: 9a057e70637dcfe06d4f729a96c02be989cf9e25
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38633298"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna

## <a name="android-and-ios-application-protection-settings"></a>Skyddsinställningar för Android- och iOS-appar

Följande tabell visar hur principinställningar för Android- och iOS-appar mappas till Intune-inställningar.
  
Du hittar Intune-inställningen genom att logga in med dina autentiseringsuppgifter för Microsoft 365 Business Admin och gå till **Administrationscenter**och sedan **Intune**.
  
 > [!IMPORTANT]
 > 
 > En Microsoft 365 Business-prenumeration ger dig en licens för att ändra alla Intune-inställningar. Se [Introduktion till Intune för att komma igång.](https://docs.microsoft.com/intune/introduction-intune)
  
Välj det principnamn som du &mdash; vill ha till exempel användningsprincip för &mdash; Android och välj sedan **principinställningar**.
  
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
|Återställ PIN-kod när inloggningen misslyckas detta många gånger (detta är inaktiverat om PIN-koden inte krävs)  <br/> |Antal försök innan PIN-koden återställs  <br/> |
|Kräv att användare loggar in igen efter att Office-apparna har varit inaktiva (detta är inaktiverat om PIN-koden inte krävs)  <br/> | Kontrollera åtkomstkraven igen efter (minuter)  <br/>  Här anges även:  <br/> **Timeout** är inställt på minuter  <br/>  Det här är samma antal minuter som du angav i Microsoft 365 Business.  <br/> **Offline respitperiod** är inställt på 720 minuter som standard  <br/> |
|Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter  <br/> |Blockera hanterade appar från att köras på jailbrokade eller rotade enheter  <br/> |
|Tillåt användare att kopiera innehåll från Office-program till personliga program  <br/> | Begränsa klipp ut, kopiera och klistra in med andra appar  <br/>  Om alternativet Microsoft 365 Business är **På** ställs även dessa tre alternativ in på **Alla appar** i Intune:  <br/> **Tillåt att appen överför data till andra appar** <br/> **Tillåt att appen tar emot data från andra appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** <br/>  Om alternativet Microsoft 365 Business är **På** ställs alla Intune-alternativ in så här:  <br/> **Tillåt att appen överför data till andra appar** är inställt på **Principhanterade appar** <br/> **Tillåt att appen tar emot data från andra appar** är inställt på **Alla appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** är inställt på **Principhanterade appar med inklistring** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Skyddsinställningar för Windows 10-appar

Följande tabell visar hur principinställningar för Windows 10-appar mappas till Intune-inställningar.
  
Du hittar Intune-inställningen genom att logga in med dina autentiseringsuppgifter för Microsoft 365 Business Admin och gå till [Azure Portal](https://portal.azure.com). Välj **fler tjänster**och skriv Intune i **filtret**. Välj **Intune App Protection** \> **-appprincipen**.
  
 > [!IMPORTANT]
 >
 >En Microsoft 365 Business-prenumeration ger dig en licens för att ändra endast Intune-inställningar som mappas till inställningarna som är tillgängliga i Microsoft 365 Business. 
  
Om du vill utforska de tillgängliga inställningarna väljer du det Principnamn du vill ha och väljer **Allmänt, tilldelningar**, **tillåtna appar**, **undantagna appar**, **obligatoriska inställningar**eller **Avancerade inställningar** från det vänstra navigeringsfönstret. 
  
|**Principinställningen för Windows 10-program**|**Intune-inställning(ar)**|
|:-----|:-----|
|Kryptera arbetsfiler  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Återkalla krypteringsnycklar vid avregistrering** och **Återkalla åtkomst till skyddade data när enheten registreras i MDM** är båda **På**.  <br/> |
|Förhindra användare från att kopiera företagsdata till personliga filer.  <br/> |**Nödvändiga inställningar** \> **Läget för Windows informationsskydd**. **På** i Microsoft 365 Business Maps till: **Dölj åsidosättningar**, **av** i Microsoft 365 Business Maps till: **off**.  <br/> |
|Åtkomstkontroll för Office-dokument  <br/> | Om inställningen är **På** i Microsoft 365 Business så  <br/> **Avancerade inställningar** \> **Åtkomst**, **Använd Windows Hello för företag som inloggningsmetod för Windows** är **På**, med följande ytterligare inställningar:  <br/> **Ange lägsta antal tillåtna tecken för PIN-kod** är inställt på **4**.  <br/> **Ställ in användning av versaler i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av versaler för PIN-kod**.  <br/> **Ställ in användning av gemener i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av gemener för PIN-kod**.  <br/> **Ställ in användning av specialtecken i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av specialtecken för PIN-kod**.  <br/> **Ange den tidsperiod (i dagar) som en PIN-kod kan användas innan systemet kräver att användaren ändrar** anges till **0**.  <br/> **Ange antalet tidigare PIN-koder som kan kopplas till ett användarkonto och som inte kan återanvändas** är inställt på **0**.  <br/> **Antal autentiseringsförsök som tillåts innan enheten rensas** anges till samma som i Microsoft 365 Business (5 som standard).  <br/> **Maximal tid (i minuter) som får passera innan en aktiv enhet låses med PIN-kod eller lösenord** anges till samma som i Microsoft 365 Business.  <br/> |
|Aktivera återställning av skyddade data  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Visa symbol för företagsdataskydd** och **Använd Azure RMS för Windows informationsskydd** är **På**.  <br/> |
|Skydda ytterligare företagsmolnplatser  <br/> |**Avancerade inställningar** \> **Skyddade domäner** och **Molnresurser** visar domäner och SharePoint-webbplatser.  <br/> |
|Filer som används av de här apparna är skyddade  <br/> |Listan med skyddade appar finns i **Tillåtna appar**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Skyddsinställningar för Windows 10-enheter

Följande tabell visar hur konfigurationsinställningar för Windows 10-enheter mappas till Intune-inställningar.
  
För att hitta Intune-inställningen loggar du in med dina autentiseringsuppgifter för Microsoft 365 Business Admin och går till [Azure-portalen](https://portal.azure.com), väljer **fler tjänster**och skriver in Intune i **filtret**och väljer **Intune** \> - **enhetskonfigurationprofiler** \> ****. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Principinställning för Windows 10-enhet**|**Intune-inställning(ar)**|
|:-----|:-----|
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Tillåt övervakning i realtid = PÅ  <br/> Tillåt molnskydd = PÅ  <br/> Be användarna att skicka exempel = Skicka säkra exempel automatiskt (standard är automatiskt skickad information som är icke personligt identifierbar)  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |**SmartScreen** i **webbläsarinställningar för Edge** är inställt på **Krävs**.  <br/> |
|Stäng av enhetens skärm när datorn varit inaktiv i (minuter)  <br/> |Maximalt antal minuter av inaktivitet innan skärmen låses (minuter)  <br/> |
|Tillåt användare att hämta appar från Microsoft Store  <br/> |Anpassad URI-princip  <br/> |
|Tillåt användare att använda Cortana  <br/> |**Allmänt** \> **Cortana** är inställt på **blockera** i Intune när värdet är **Av** i Microsoft 365 Business.  <br/> |
|Tillåt användare att ta emot Windows-tips och reklam från Microsoft  <br/> |**Windows spotlight**, allt blockerat om detta är inställt på **av** i Microsoft 365 Business.  <br/> |
|Håll Windows 10-enheter uppdaterade automatiskt  <br/> | Den här inställningen är i **Microsoft Intune** \> **service updates-Windows 10 uppdatera ringar**, Välj **uppdateringsprincip för Windows 10 enheter**, och sedan **Egenskaper** \> **Inställningar**.  <br/>  När företags inställningen Microsoft 365 är inställd **på på**, ställs alla följande inställningar in:  <br/> **Tjänstgren** är inställt på **CB** (CBB när det är inaktiverat Microsoft 365 Business).  <br/> **Microsoft-produktuppdateringar** är inställt på **Tillåt**.  <br/> **Windows-drivrutiner** är inställt på **Tillåt**.  <br/> **Funktionssätt för automatisk uppdatering** är inställt på **Installera automatiskt vid underhåll** med:  <br/> **Starttid för aktiva timmar** är inställt på **06:00**.  <br/> **Sluttid för aktiva timmar** är inställt på **22:00**.  <br/> **Uppskjutningsperiod för kvalitetsuppdatering (dagar)** är inställt på **0**.  <br/> **Uppskjutningsperiod för funktionsuppdatering (dagar)** är inställt på **0**.  <br/> **Nedladdningsläge för leveransoptimering** är inställt på **HTTP blandat med peering bakom samma NAT**.  <br/> |
|||
   

