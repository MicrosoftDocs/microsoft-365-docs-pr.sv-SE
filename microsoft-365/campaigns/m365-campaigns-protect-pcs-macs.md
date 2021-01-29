---
title: Skydda ohanterade Windows 10-PC- och Mac-datorer
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
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044390"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Skydda ohanterade Windows 10-PC- och Mac-datorer

Du kan hantera Pc- och Mac-datorer med Windows 10 genom att registrera dem i Microsoft Intune, så att du kan säkerställa att de är felfria och säkra innan du använder data i din miljö. Många kampanjer och småföretag inkluderar dock personal som tar med sina egna enheter (BYOD), som inte kommer att hanteras av organisationen. För de här ohanterade PC- och Mac-datorer använder du den här artikeln för att säkerställa att minsta möjliga säkerhetsfunktion är konfigurerad.

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

Enhetskryptering finns på en mängd olika Windows-enheter och skyddar dina data genom att kryptera dem. Om du aktiverar enhetskryptering kan endast behöriga personer komma åt din enhet och dina data. Anvisningar [finns i aktivera enhetskryptering.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)

 Om enhetskryptering inte är tillgängligt på din enhet kan du aktivera vanlig [BitLocker-kryptering i](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) stället. (BitLocker är inte tillgängligt i Windows 10 Home-versionen.) 

**Skydda din enhet med Windows-säkerhet**<p>
Om du har Windows 10 får du det senaste antivirusskyddet med Windows-säkerhet. När du startar Windows 10 för första gången är Windows-säkerhet på och hjälper aktivt till att skydda datorn genom att söka efter skadlig programvara (skadlig kod), virus och säkerhetshot. Windows-säkerhet använder realtidsskydd för att söka igenom allt du laddar ned eller kör på datorn.

Windows Update laddar automatiskt ned uppdateringar för Windows-säkerhet för att skydda datorn mot hot.

Om du har en tidigare version av Windows och använder Microsoft Security Essentials är det en bra idé att gå över till Windows-säkerhet. Mer information finns i skydda [enheten med Windows-säkerhet.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Aktivera Windows-brandväggen**<p>
Du bör alltid köra Windows-brandväggen även om du har en annan brandvägg aktiverad. Om du inaktiverar Windows-brandväggen kan enheten (och nätverket, om du har ett) bli mer sårbar för obehörig åtkomst. Anvisningar [finns i Aktivera eller inaktivera Windows-brandväggen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)

## <a name="mac"></a>[Mac](#tab/Mac)

**Använda FileVault för att kryptera Mac-hårddisken**<p>
Diskkryptering skyddar data om enheter försvinner eller blir stulna. FileVault fullständig diskkryptering hjälper till att förhindra obehörig åtkomst till informationen på startdisken. Instruktioner [finns i FileVault för att kryptera startdisken](https://support.apple.com/HT204837) på din Mac.

**Skydda mac-datorn mot skadlig programvara**<p>
Microsoft rekommenderar att du installerar och använder tillförlitlig antivirusprogramvara på din Mac. I följande artikel finns en lista med alternativ: [Bästa antivirusprogrammet för Mac 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

Du kan också minska risken för skadlig programvara genom att bara använda programvara från tillförlitliga källor. I inställningarna för & sekretess kan du ange källor för programvara som är installerad på din Mac. Mer information finns i skydda [din Mac mot skadlig programvara.](https://support.apple.com/kb/PH25087)

**Aktivera brandväggsskydd**<p>
Använd brandväggsinställningarna för att skydda din Mac från oönskad kontakt initierad av andra datorer när du är ansluten till Internet eller ett nätverk. Utan det här skyddet kan din Mac vara mer sårbar för obehörig åtkomst. Instruktioner [finns i programmets](https://support.apple.com/HT201642) brandvägg.
