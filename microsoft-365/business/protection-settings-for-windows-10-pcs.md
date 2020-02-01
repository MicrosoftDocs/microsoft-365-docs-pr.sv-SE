---
title: Ange inställningar för enhetsskydd för Windows 10
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Lär dig mer om standardinställningar och andra inställningar som är tillgängliga i Microsoft 365 Business för att skydda Windows 10-enheter.
ms.openlocfilehash: b286eb417a8e723b01838c16286ceb612d497c7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593525"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Ange inställningar för enhetsskydd för Windows 10

## <a name="secure-windows-10-devices"></a>Skydda Windows 10-enheter

Titta på en video om hur du skyddar Windows 10-enheter med Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Gå till admin <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>center på . 
    
2. Välj \> **Enhetsprinciper** \> Lägg **** **till**på den vänstra naven .
  
3. I fönstret **Lägg till princip** anger du ett unikt namn för principen. 
    
4. Under **Typ av princip** väljer du **Konfiguration av Windows 10-enhet**.
    
5. Expandera **Skydda Windows 10-enheter** \> konfigurera inställningar enligt eget önskemål. Mer information finns i [Tillgängliga inställningar](#available-settings). 
    
    Du kan alltid använda länken **Återställ standardinställningar** för att återgå till standardinställningarna. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. **Vem får de här inställningarna?** Om du inte vill använda säkerhetsgruppen **Alla användare** (standard) väljer du **Ändra** och anger vilka säkerhetsgrupper som får dessa inställningar \> **Välj**.
    
7. Välj **Klar** för att spara principen och tilldela den till enheter. 
    
## <a name="available-settings"></a>Tillgängliga inställningar

Som standard är alla inställningar **På**. Följande inställningar är tillgängliga.
  
Mer information finns i [Hur mappar skyddsfunktioner i Microsoft 365 Business till Intune-inställningarna](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.  <br/> |
|Använd regler som minskar enheternas attackytor  <br/> |När inställningen är aktiv bidrar minskningen av attackytan till att blockera åtgärder och program som vanligtvis används av skadlig programvara för att smitta enheter. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Minska attackytor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Skydda mappar från hot som utpressningstrojaner  <br/> |Den här inställningen använder kontrollerad mappåtkomst för att skydda företagsdata från att ändras av misstänkta eller skadliga program, till exempel utpressningstrojaner. Dessa typer av program blockeras från att göra ändringar i skyddade mappar. Inställningen är bara tillgänglig om Windows Defender Antivirus är aktiverad. Mer information finns i [Skydda mappar med kontrollerad mappåtkomst.](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)  <br/> |
|Förhindra nätverksåtkomst till potentiellt skadlig innehåll på Internet  <br/> |Använd den här inställningen om du vill blockera utgående användaranslutningar till internetplatser med låg anseende som kan vara värdar för nätfiskebedrägerier, exploateringar eller annat skadligt innehåll. Den här inställningen är endast tillgänglig om Windows Defender Antivirus är inställt på **På**. Mer information finns i [Skydda nätverket](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker  <br/> |BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen. Mer information finns i [Vanliga frågor och svar om Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Tillåt användare att hämta appar från Microsoft Store  <br/> |Låter användare ladda ned och installera appar från Microsoft Store. Appar inbegriper allt från spel till produktivitetsverktyg, så vi lämnar den här inställningen **På**, men du kan inaktivera den för extra säkerhet.  <br/> |
|Tillåt användare att använda Cortana  <br/> |Cortana kan vara mycket användbar! Cortana kan aktivera eller inaktivera inställningar åt dig, ge anvisningar och se till att du är i tid för avtalade tider, så vi behåller den här inställningen **På** som standard.  <br/> |
|Tillåt användare att ta emot Windows-tips och reklam från Microsoft  <br/> |Windows-tips kan vara praktiskt eftersom de informerar användare när nya funktioner blir tillgängliga.  <br/> |
|Håll Windows 10-enheter uppdaterade automatiskt  <br/> |Säkerställer att Windows 10-enheter automatiskt får de senaste uppdateringarna.  <br/> |
|Stäng av enhetens skärm efter en viss tids inaktivitet  <br/> |Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.  <br/> |
