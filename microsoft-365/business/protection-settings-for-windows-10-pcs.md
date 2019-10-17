---
title: Ange inställningar för enhetsskydd för Windows 10
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Lär dig mer om standardinställningar och andra inställningar som är tillgängliga i Microsoft 365 Business för att säkra Windows 10-enheter.
ms.openlocfilehash: ab306e3d5a6011a0e7d537c98ecca6ef49ff82d9
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575767"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Ange inställningar för enhetsskydd för Windows 10

## <a name="secure-windows-10-devices"></a>Skydda Windows 10-enheter

Titta på en video om hur du skyddar Windows 10-enheter med Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. I det vänstra navigeringsfältet väljer **du Lägg till** **enhets** \> **principer** \> .
  
3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Under **Typ av princip** väljer du **Konfiguration av Windows 10-enhet**.
    
5. Expandera **Skydda Windows 10-enheter** \> konfigurera inställningar enligt eget önskemål. Se [Tillgängliga inställningar](#available-settings) för mer information. 
    
    Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningar. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. **Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla användare** (standard) väljer du **Ändra** och anger vilka säkerhetsgrupper som får dessa inställningar \> **Välj**.
    
7. Välj **Klar** för att spara principen och tilldela den till enheter. 
    
## <a name="available-settings"></a>Tillgängliga inställningar

Som standard är alla inställningar **På**. Följande inställningar är tillgängliga.
  
Mer information finns i artikeln om [hur skyddsfunktioner i Microsoft 365 Business mappas till Intune-inställningarna](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.  <br/> |
|Använd regler som minskar enheternas attackytor  <br/> |När inställningen är aktiv bidrar minskningen av attackytan till att blockera åtgärder och program som vanligtvis används av skadlig programvara för att smitta enheter. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Minska attackytor](https://go.microsoft.com/fwlink/?linkid=870417).  <br/> |
|Skydda mappar från hot som utpressningstrojaner  <br/> |Den här inställningen använder kontrollerad mappåtkomst för att skydda företagsdata från att ändras av misstänkta eller skadliga program, till exempel utpressningstrojaner. Dessa typer av program blockeras från att göra ändringar i skyddade mappar. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Skydda filer med kontrollerad mappåtkomst](https://go.microsoft.com/fwlink/?linkid=870418).  <br/> |
|Förhindra nätverksåtkomst till potentiellt skadlig innehåll på Internet  <br/> |Använda den här inställningen för att blockera utgående användaranslutningar till beryktade Internetplatser som kan vara värdar för nätfiske, trojaner eller annat skadligt innehåll. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Skydda ditt nätverk](https://go.microsoft.com/fwlink/?linkid=870419).  <br/> |
|Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker  <br/> |BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen. Mer information finns i [Vanliga frågor och svar om Bitlocker ](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Tillåt användare att hämta appar från Microsoft Store  <br/> |Låter användare ladda ned och installera appar från Microsoft Store. Appar inbegriper allt från spel till produktivitetsverktyg, så vi lämnar den här inställningen **På**, men du kan inaktivera den för extra säkerhet.  <br/> |
|Tillåt användare att använda Cortana  <br/> |Cortana kan vara mycket användbar! Hon kan aktivera eller inaktivera inställningar åt dig, ge vägbeskrivningar och kontrollera att du håller avtalade tider, så vi lämnar inställningen **På** som standard.  <br/> |
|Tillåt användare att ta emot Windows-tips och reklam från Microsoft  <br/> |Windows-tips kan vara praktiskt eftersom de informerar användare när nya funktioner blir tillgängliga.  <br/> |
|Håll Windows 10-enheter uppdaterade automatiskt  <br/> |Säkerställer att Windows 10-enheter automatiskt får de senaste uppdateringarna.  <br/> |
|Stäng av enhetens skärm efter en viss tids inaktivitet  <br/> |Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.  <br/> |
   
  

