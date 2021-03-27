---
title: Skydda ohanterade Windows 10 PC- och Mac-datorer
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Skydda ohanterade eller ta med dina egna enheter (BYOD) med Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398259"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Skydda ohanterade Windows 10 PC- och Mac-datorer

Du kan hantera Windows 10-datorer och Mac-datorer genom att registrera dem i Microsoft Intune, så att du kan säkerställa att de är skyddade och får åtkomst till data i din miljö. Många kampanjer och småföretag innefattar dock personal som tar med sig egna enheter (BYOD), som inte hanteras av organisationen. För de här ohanterade PC- och Mac-datorer använder du den här artikeln för att säkerställa att minsta möjliga säkerhetsfunktion är konfigurerad.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Skydda en dator med Windows 10 eller en Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Om din Windows 10-dator eller Mac inte hanteras av din organisation måste du konfigurera dessa säkerhetsfunktioner.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Aktivera enhetskryptering**<p>

Enhetskryptering finns på ett brett utbud av Windows-enheter och skyddar dina data genom att kryptera dem. Om du aktiverar enhetskryptering kan endast behöriga personer komma åt din enhet och dina data. Anvisningar [finns i Aktivera enhetskryptering.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)

 Om enhetskryptering inte är tillgängligt på din enhet kan du aktivera vanlig [BitLocker-kryptering i](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) stället. (BitLocker är inte tillgängligt i Windows 10 Home-versionen.) 

**Skydda din enhet med Windows-säkerhet**<p>
Om du har Windows 10 får du det senaste antivirusskyddet med Windows-säkerhet. När du startar Windows 10 för första gången är Windows-säkerhet på och hjälper aktivt till att skydda datorn genom att söka efter skadlig programvara (skadlig kod), virus och säkerhetshot. Windows Security använder realtidsskydd för att söka igenom allt du laddar ned eller kör på datorn.

Windows Update laddar automatiskt ned uppdateringar för Windows-säkerhet för att skydda datorn mot hot.

Om du har en tidigare version av Windows och använder Microsoft Security Essentials är det en bra idé att gå över till Windows-säkerhet. Mer information finns i Skydda [enheten med Windows-säkerhet.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Aktivera Windows-brandväggen**<p>
Du bör alltid köra Windows-brandväggen även om du har en annan brandvägg aktiverad. Om du inaktiverar Windows-brandväggen kan din enhet (och eventuella nätverk) bli mer sårbar för obehörig åtkomst. Anvisningar [finns i Aktivera eller inaktivera Windows-brandväggen.](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)

**Använda FileVault för att kryptera Mac-hårddisken**<p>
Diskkryptering skyddar data om enheter försvinner eller blir stulna. FileVault fullständig diskkryptering hjälper till att förhindra obehörig åtkomst till informationen på startdisken. Instruktioner [finns i Använda FileVault för att kryptera startdisken](https://support.apple.com/HT204837) på din Mac.

**Skydda mac-datorn mot skadlig programvara**<p>
Microsoft rekommenderar att du installerar och använder tillförlitlig antivirusprogramvara på din Mac. I följande artikel finns en lista med alternativ: [Bästa antivirusprogrammet för Mac 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

Du kan också minska risken för skadlig programvara genom att bara använda programvara från tillförlitliga källor. Med inställningarna i & sekretessinställningar kan du ange källor för programvara som är installerad på din Mac. Mer information finns i Skydda [mac-datorn mot skadlig programvara.](https://support.apple.com/kb/PH25087)

**Aktivera brandväggsskydd**<p>
Använd brandväggsinställningarna för att skydda datorn mot oönskad kontakt initierad av andra datorer när du är ansluten till Internet eller ett nätverk. Utan det här skyddet kan din Mac vara mer sårbar för obehörig åtkomst. Instruktioner [finns i om programbrandväggen.](https://support.apple.com/HT201642)
