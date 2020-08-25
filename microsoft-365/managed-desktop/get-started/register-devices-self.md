---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 470047da0a1902a6076add27a6e7ac516edd3150
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46869013"
---
# <a name="register-new-devices-yourself"></a>Registrera nya enheter själv

Microsoft Managed Desktop kan fungera med helt nya enheter eller kan du återanvända enheter som du kanske redan har (som kräver att du skriver ut dem igen). Du kan registrera enheter på Microsoft Managed Desktop admin-portalen.

> [!NOTE]
> Arbetar du med en partner för att få fram enheter? Om så är fallet behöver du inte oroa dig för att få maskinvaru-hashar; de tar hand om det åt dig. Se till att din partner etablerar en relation med dig i [partner Center](https://partner.microsoft.com/dashboard). Din partner kan läsa mer i [Hjälp för partner Center](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). När den här relationen är etablerad registrerar din partner bara enheter åt dig – ingen ytterligare åtgärd krävs. Om du vill se informationen, eller om din partner har frågor, kan du läsa [anvisningarna för partner att registrera enheter](register-devices-partner.md). När du har registrerat enheterna kan du gå vidare med att [kontrol lera bilden](#check-the-image) och [leverera enheterna](#deliver-the-device) till användarna.

## <a name="prepare-to-register-brand-new-devices"></a>Förbereda för att registrera varumärket-nya enheter


När du har de nya produkterna i handen följer du de här stegen:

1. [Skaffa maskinvaru-hashvärdet för varje enhet.](#obtain-the-hardware-hash)
2. [Slå samman hash-data](#merge-hash-data)
3. [Registrera enheterna på Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Kontrol lera att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Skaffa maskinvaru-hashvärdet

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash. Du har tre alternativ för att få den här informationen:

- Be din OEM-leverantör om den autopilot registrerings filen som kommer att innehålla maskinvaru-hashar.
- Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla resultaten i en fil.
- Starta varje enhet, men Slutför inte installations upplevelsen för Windows--och [samla in hash-värden på ett löstagbart minne](#flash-drive-method).

#### <a name="powershell-script-method"></a>Metod för PowerShell-skript

Du kan använda [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-skriptet på PowerShell-galleriet. Mer information om enhets identifiering och maskinvaru-hash finns i [lägga till enheter i Windows autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).

1.  Öppna en PowerShell-kommandotolk med administrativa rättigheter.
2.  Använda `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Använda `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>Flash-enhet, metod

1. På en annan enhet än den du registrerar kan du sätta in en USB-enhet.
2. Öppna en PowerShell-kommandotolk med administrativa rättigheter.
3. Använda `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Slå på den enhet du registrerar, men *Starta inte installations upplevelsen*. Om du råkar starta installations upplevelsen måste du återställa eller återanvända enheten.
5. Sätt in USB-enheten och tryck sedan på SKIFT + F10.
6. Öppna en PowerShell-kommandotolk med administrativa rättigheter och kör den sedan `cd <pathToUsb>` .
7. Använda `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Använda `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Ta bort USB-enheten och stäng sedan av enheten genom att köra `shutdown -s -t 0`

>[!IMPORTANT]
>Koppla inte på den enhet du registrerar igen förrän du har registrerat dig. 


### <a name="merge-hash-data"></a>Slå samman hash-data

Du måste ha data i CSV-filerna sammankopplade till en enda fil för att slutföra registreringen. Här är ett exempel på PowerShell-skript som gör det enkelt:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrera enheter med hjälp av administrations portalen

Välj **enheter** i det vänstra navigerings fönstret på portalen Microsoft Managed Desktop [admin](https://aka.ms/mmdportal). Välj **+ registrera enheter**; infarten öppnas:

[![Flyg in när du har valt registrera enheter, visar enheter med kolumner för tilldelade användare, serie nummer, status, senaste datum och ålder](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gör så här:

1. Ange en sökväg till CSV-filen som du skapade tidigare i **fil överföring**.
3. Välj **registrera enheter**. Systemet lägger till enheter i listan med enheter i **bladet enheter**, markerade som **AutopilotRegistrationRequested**. Registreringen tar vanligt vis mindre än 10 minuter och när enheten lyckas visas den som **klar för användarna** , vilket betyder att det är klart och väntar på att en användare ska börja använda.


Du kan övervaka förloppet av enhets registreringen på huvud sidan för **hanterade skriv bord i Microsoft** . Möjliga tillstånd rapporterade att inkludera:

| Sessionsläget | Beskrivning |
|---------------|-------------|
| AutopilotRegistrationRequested | Registreringen är inte klar ännu. Kom tillbaka senare. |
| Registreringen misslyckades | Det gick inte att genomföra registreringen. Mer information finns i [fel sökning av enhets registrering](#troubleshooting-device-registration) . |
| Redo för användare | Registreringen lyckades och enheten är nu klar att levereras till slutanvändaren. Microsoft Managed Desktop vägleder dem genom första gången, vilket innebär att du inte behöver göra några fler förberedelser. |
| Aktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient organisation. Detta indikerar också att de ofta använder enheten. |
| Inaktiv | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient organisation. De har emellertid inte använt enheten nyligen (under de senaste 7 dagarna).  | 

#### <a name="troubleshooting-device-registration"></a>Felsöka registrering av enheter

| Fel meddelande | Information |
|---------------|-------------|
| Enheten hittades inte | Det gick inte att registrera den här enheten eftersom vi inte kunde hitta en träff för den medföljande tillverkaren, modellen eller serie numret. Bekräfta dessa värden med din enhets leverantör. |
| Maskinvaru-hashvärdet är inte giltigt | Den maskinvaru-hash som du har angett för enheten är inte korrekt formaterad. Dubbel kontrol lera maskinvaru-hashvärdet och skicka sedan igen. |
| Enheten är redan registrerad | Enheten är redan registrerad i din organisation. Ingen ytterligare åtgärd krävs. |
| Enhet som ägs av en annan organisation | Den här enheten har redan hävdats av en annan organisation. Hör med din enhets leverantör. |
| Oväntat fel | Begäran kunde inte behandlas automatiskt. Kontakta supporten och ange begäran-ID: <requestId> |

### <a name="check-the-image"></a>Kontrol lera bilden

Om din enhet kommer från en Microsoft Managed Desktop partner-leverantör ska bilden vara korrekt.

Du är också välkommen att lägga till din egen image om du vill. För att komma igång kontaktar du den Microsoft-representant du arbetar med och ger dig en plats och anvisningar för hur du kan använda bilden.

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar in enheten till din användare bör du kontrol lera att du har skaffat [rätt licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser tillämpas kan du [få användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå igenom installations upplevelsen i Windows.






