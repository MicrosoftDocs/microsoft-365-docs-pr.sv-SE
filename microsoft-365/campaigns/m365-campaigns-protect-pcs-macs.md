---
title: Skydda ohanterade Windows 10-datorer och Mac-datorer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Skydda mot nätfiske och andra attacker med Microsoft 365 för kampanjer.
ms.openlocfilehash: 7cb09d0cadcc70b96c5f1404defa5d0387947ca8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811838"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Skydda ohanterade Windows 10-datorer och Mac-datorer

Du kan hantera Windows 10-datorer och Mac-datorer genom att registrera dem i Microsoft Intune, vilket gör att du kan se till att de är friska och säkra innan du använder data i din miljö. Men många kampanjer och småföretag inkluderar personal som tar med egna enheter (byod), som inte kommer att hanteras av organisationen. För dessa ohanterade datorer och Mac-datorer använder du den här artikeln för att säkerställa att minimisäkerhetsfunktionerna är konfigurerade. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Skydda en dator med Windows 10 eller en Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Om din Windows 10 PC eller Mac inte hanteras av din organisation måste du konfigurera dessa säkerhetsfunktioner.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)
**Aktivera enhetskryptering**<p>

Enhetskryptering är tillgänglig på en mängd olika Windows-enheter och skyddar dina data genom att kryptera dem. Om du aktiverar enhetskryptering kan endast behöriga personer komma åt enheten och data. Se [aktivera enhetskryptering](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) för instruktioner.

 Om enhetskryptering inte är tillgänglig på enheten kan du aktivera [standardbitlocker-kryptering](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) i stället. (BitLocker är inte tillgängligt i Windows 10 Home edition.) 


**Skydda enheten med Windows Security**<p>
Om du har Windows 10 får du det senaste antivirusskyddet med Windows Security. När du startar Windows 10 för första gången är Windows Security aktiverat och hjälper aktivt till att skydda datorn genom att söka efter skadlig kod (skadlig programvara), virus och säkerhetshot. Windows Security använder realtidsskydd för att skanna allt du laddar ned eller kör på datorn.

Windows Update hämtar uppdateringar för Windows Security automatiskt för att skydda datorn och skydda den från hot.

Om du har en tidigare version av Windows och använder Microsoft Security Essentials är det en bra idé att flytta till Windows Security. Mer information finns i [skydda enheten med Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Aktivera Windows-brandväggen**<p>
Du bör alltid köra Windows-brandväggen även om du har en annan brandvägg påslagen. Om du inaktiverar Windows-brandväggen kan enheten (och nätverket, om du har en) mer sårbar för obehörig åtkomst. Se [Aktivera eller inaktivera Windows-brandväggen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) för instruktioner

## <a name="mac"></a>[Mac](#tab/Mac)
**Använda FileVault för att kryptera din Mac-disk**<p>
Diskkryptering skyddar data när enheter försvinner eller stjäls. FileVault-kryptering med full disk hjälper till att förhindra obehörig åtkomst till informationen på startdisken. Se [Använda FileVault för att kryptera startdisken på din Mac](https://support.apple.com/HT204837) för instruktioner.

**Skydda din mac från skadlig kod**<p>
Microsoft rekommenderar att du installerar och använder tillförlitligt antivirusprogram på din Mac. Se följande artikel för en lista med alternativ: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Du kan också minska risken för skadlig kod genom att endast använda programvara från tillförlitliga källor. Med inställningarna i inställningar för säkerhet & sekretess kan du ange de programkällor som är installerade på din Mac. Mer information finns i [skydda din Mac från skadlig kod](https://support.apple.com/kb/PH25087).

**Aktivera brandväggsskydd**<p>
Använd brandväggsinställningarna för att skydda din Mac från oönskad kontakt som initierats av andra datorer när du är ansluten till Internet eller ett nätverk. Utan det här skyddet kan din Mac vara mer sårbar för obehörig åtkomst. Se [om programbrandväggen](https://support.apple.com/HT201642) för instruktioner.
