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
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Lär dig hur funktioner i Microsoft 365 Business mappas till Intune-inställningar. Prenumerationen får du en licens för att ändra inställningarna för Intune.
ms.openlocfilehash: a6aaf6cc06c31b870eb85582f5aa47699919d75d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074269"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna

## <a name="android-and-ios-application-protection-settings"></a>Skyddsinställningar för Android- och iOS-appar

Följande tabell visar hur principinställningar för Android- och iOS-appar mappas till Intune-inställningar.
  
Om du vill hitta Intune-inställningen loggar du in med ditt Microsoft 365 Business-administratörskonto och går till **administratörscenter** och sedan **Intune**.
  
 **Viktigt:** En Microsoft 365 Business-prenumeration får du en licens för att ändra inställningarna för Intune. Se [Introduktion till Intune för att komma igång.](https://docs.microsoft.com/intune/introduction-intune)
  
Klicka på det principnamn du vill markera, till exempel Programprincip för Android, och välj sedan **Principinställningar**.
  
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
|Återställ PIN-kod när inloggning misslyckas så här många gånger (alternativet är inaktiverat om PIN-kod inte krävs)  <br/> |Antal försök innan PIN-koden återställs  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva i (alternativet är inaktiverat om PIN-kod inte krävs)  <br/> | Kontrollera åtkomstkraven igen efter (minuter)  <br/>  Här anges även:  <br/> **Timeout** är inställt på minuter  <br/>  Det här är samma antal minuter som du angav i Microsoft 365 Business.  <br/> **Offline respitperiod** är inställt på 720 minuter som standard  <br/> |
|Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter  <br/> |Blockera hanterade appar från att köras på jailbrokade eller rotade enheter  <br/> |
|Tillåt användare att kopiera innehåll från Office-program till personliga program  <br/> | Begränsa klipp ut, kopiera och klistra in med andra appar  <br/>  Om alternativet Microsoft 365 Business är **På** ställs även dessa tre alternativ in på **Alla appar** i Intune:  <br/> **Tillåt att appen överför data till andra appar** <br/> **Tillåt att appen tar emot data från andra appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** <br/>  Om alternativet Microsoft 365 Business är **På** ställs alla Intune-alternativ in så här:  <br/> **Tillåt att appen överför data till andra appar** är inställt på **Principhanterade appar** <br/> **Tillåt att appen tar emot data från andra appar** är inställt på **Alla appar** <br/> **Begränsa klippa ut, kopiera och klistra in med andra appar** är inställt på **Principhanterade appar med inklistring** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Skyddsinställningar för Windows 10-appar

Följande tabell visar hur principinställningar för Windows 10-appar mappas till Intune-inställningar.
  
För att hitta Intune inställningen loggat in med dina autentiseringsuppgifter för Microsoft 365 Business admin, gå till [Azure portal](https://portal.azure.com)och sedan markera **flera tjänster**och typ i Intune till **Filter**väljer du **Intune App skydd** \> ** App för**.
  
 **Viktigt!** En Microsoft 365 Business-prenumeration ger dig en licens för att ändra endast de Intune-inställningar som mappas till inställningarna i Microsoft 365 Business. 
  
Klicka på det principnamn du vill markera och välj sedan **Allmänt, Tilldelningar**, **Tillåtna appar**, **Undanta appar**, **Nödvändiga inställningar** eller **Avancerade inställningar** från navigeringsfältet till vänster för att utforska de tillgängliga inställningarna. 
  
|**Principinställningen för Windows 10-program**|**Intune-inställning(ar)**|
|:-----|:-----|
|Kryptera arbetsfiler  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Återkalla krypteringsnycklar vid avregistrering** och **Återkalla åtkomst till skyddade data när enheten registreras i MDM** är båda **På**.  <br/> |
|Förhindra användare från att kopiera företagsdata till personliga filer.  <br/> |**Nödvändiga inställningar** \> **Läget för Windows informationsskydd**. **På** i Microsoft 365 Business mappas till: **Dölj åsidosättningar**, **Av** i Microsoft 365 Business mappas till: **Av**.  <br/> |
|Åtkomstkontroll för Office-dokument  <br/> | Om inställningen är **På** i Microsoft 365 Business så  <br/> **Avancerade inställningar** \> **Åtkomst**, **Använd Windows Hello för företag som inloggningsmetod för Windows** är **På**, med följande ytterligare inställningar:  <br/> **Ange lägsta antal tillåtna tecken för PIN-kod** är inställt på **4**.  <br/> **Ställ in användning av versaler i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av versaler för PIN-kod**.  <br/> **Ställ in användning av gemener i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av gemener för PIN-kod**.  <br/> **Ställ in användning av specialtecken i PIN-koden för Windows Hello för företag** är inställt på **Tillåt inte användning av specialtecken för PIN-kod**.  <br/> **Ange tidsperiod (i dagar) som en PIN-kod får användas innan användaren måste ändra den** är inställt på **0**.  <br/> **Ange antalet tidigare PIN-koder som kan kopplas till ett användarkonto och som inte kan återanvändas** är inställt på **0**.  <br/> **Antal autentiseringsförsök som tillåts innan enheten rensas** anges till samma som i Microsoft 365 Business (5 som standard).  <br/> **Maximal tid (i minuter) som får passera innan en aktiv enhet låses med PIN-kod eller lösenord** anges till samma som i Microsoft 365 Business.  <br/> |
|Aktivera återställning av skyddade data  <br/> |**Avancerade inställningar** \> **Dataskydd**: **Visa symbol för företagsdataskydd** och **Använd Azure RMS för Windows informationsskydd** är **På**.  <br/> |
|Skydda ytterligare företagsmolnplatser  <br/> |**Avancerade inställningar** \> **Skyddade domäner** och **Molnresurser** visar domäner och SharePoint-webbplatser.  <br/> |
|Filer som används av de här apparna är skyddade  <br/> |Listan med skyddade appar finns i **Tillåtna appar**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Skyddsinställningar för Windows 10-enheter

Följande tabell visar hur konfigurationsinställningar för Windows 10-enheter mappas till Intune-inställningar.
  
För att hitta Intune inställningen loggat in med dina autentiseringsuppgifter för Microsoft 365 Business admin, gå till [Azure portal](https://portal.azure.com)och sedan markera **flera tjänster**och typ i Intune till **Filter**väljer du **Intune** \> **enhet konfiguration av** \> **profiler**. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Principinställning för Windows 10-enhet**|**Intune-inställning(ar)**|
|:-----|:-----|
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Tillåt övervakning i realtid = PÅ  <br/> Tillåt molnskydd = PÅ  <br/> Be användarna att skicka exempel = Skicka säkra exempel automatiskt (standard är automatiskt skickad information som är icke personligt identifierbar)  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |**SmartScreen** i **webbläsarinställningar för Edge** är inställt på **Krävs**.  <br/> |
|Stäng av enhetens skärm när datorn varit inaktiv i (minuter)  <br/> |Maximalt antal minuter av inaktivitet innan skärmen låses (minuter)  <br/> |
|Tillåt användare att hämta appar från Microsoft Store  <br/> |Anpassad URI-princip  <br/> |
|Tillåt användare att använda Cortana  <br/> |**Allmänt** \> **Cortana** är inställt på **blockera** i Intune när värdet är **Av** i Microsoft 365 Business.  <br/> |
|Tillåt användare att ta emot Windows-tips och reklam från Microsoft  <br/> |**Windows spotlight**, allt blockerat om detta är inställt på **av** i Microsoft 365 Business.  <br/> |
|Håll Windows 10-enheter uppdaterade automatiskt  <br/> | This setting is in **Microsoft Intune** \> **Service updates - Windows 10 Update Rings**, choose U **pdate policy for Windows 10 devices**, and then **Properties** \> **Settings**.  <br/>  När Microsoft 365 Business-inställningen är **På** ställs följande inställningar in så här:  <br/> **Tjänstgren** är inställt på **CB** (CBB när det är inaktiverat Microsoft 365 Business).  <br/> **Microsoft-produktuppdateringar** är inställt på **Tillåt**.  <br/> **Windows-drivrutiner** är inställt på **Tillåt**.  <br/> **Funktionssätt för automatisk uppdatering** är inställt på **Installera automatiskt vid underhåll** med:  <br/> **Starttid för aktiva timmar** är inställt på **06:00**.  <br/> **Sluttid för aktiva timmar** är inställt på **22:00**.  <br/> **Uppskjutningsperiod för kvalitetsuppdatering (dagar)** är inställt på **0**.  <br/> **Uppskjutningsperiod för funktionsuppdatering (dagar)** är inställt på **0**.  <br/> **Nedladdningsläge för leveransoptimering** är inställt på **HTTP blandat med peering bakom samma NAT**.  <br/> |
|||
   

