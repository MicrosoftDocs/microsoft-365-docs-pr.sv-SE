---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 4de1d173a26005d32fb07117d93ee78582b77d54
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689215"
---
# <a name="register-new-devices-yourself"></a>Registrera nya enheter själv

Microsoft Managed Desktop kan arbeta med helt nya enheter eller återanvända enheter som du kanske redan har (vilket innebär att du måste animera dem igen). Du kan registrera enheter med Microsoft Managed Desktop i Microsoft Endpoint Manager-portalen.

> [!NOTE]
> Arbetar du med en partner för att skaffa enheter? I så fall behöver du inte oroa dig för att få maskinvaru-hashtaggarna. tar de hand om det åt dig. Kontrollera att din partner upprättar en relation med dig på [Partnercenter.](https://partner.microsoft.com/dashboard) Din partner kan läsa mer på [Hjälp om Partnercenter.](/partner-center/request-a-relationship-with-a-customer) När den här relationen har upprättats registrerar din partner enheter åt dig – inga ytterligare åtgärder krävs från dig. Om du vill se informationen eller om din partner har frågor kan du gå till [Steg för partner för att registrera enheter.](register-devices-partner.md) När enheterna har registrerats kan du fortsätta med [att kontrollera bilden](#check-the-image) och leverera [enheterna](#deliver-the-device) till användarna.

## <a name="prepare-to-register-brand-new-devices"></a>Förbered dig för att registrera helt nya enheter


När du har de nya enheterna i handen följer du de här stegen:

1. [Hämta maskinvaruhash för varje enhet.](#obtain-the-hardware-hash)
2. [Slå samman hash-data](#merge-hash-data)
3. [Registrera enheterna i Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Kontrollera att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Hämta maskinvaruhash

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash. Du har tre alternativ för att hämta den här informationen:

- Be din OEM-leverantör om AutoPilot-registreringsfilen, som innehåller maskinvaru-hashfilerna.
- Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla in resultaten i en fil.
- Starta varje enhet– men slutför inte Windows-installationen – och samla in hashtaggarna på ett [flyttbart flash-minne.](#flash-drive-method)

#### <a name="powershell-script-method"></a>PowerShell-skriptmetod

Du kan använda [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell-skript på webbplatsen för PowerShell-galleriet. Mer information om enhetsidentifiering och maskinvaruhash finns i [Lägga till enheter i Windows Autopilot.](/mem/autopilot/add-devices#device-identification)

1.  Öppna en PowerShell-fråga med administrativa rättigheter.
2.  Kör `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Kör `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Kör `powershell -ExecutionPolicy restricted` för att förhindra att efterföljande ändrings unrestricted skript körs.


#### <a name="flash-drive-method"></a>Flash-enhetsmetod

1. Sätt i en USB-enhet på en annan enhet än den som du registrerar.
2. Öppna en PowerShell-fråga med administrativa rättigheter.
3. Kör `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Slå på enheten som du registrerar, *men starta inte konfigurationen.* Om du startar konfigurationen av misstag måste du återställa eller animera enheten.
5. Sätt i USB-enheten och tryck sedan på SKIFT + F10.
6. Öppna en PowerShell-fråga med administrativa rättigheter och kör sedan `cd <pathToUsb>` .
7. Kör `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Kör `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Ta bort USB-enheten och stäng sedan av enheten genom att köra `shutdown -s -t 0`

>[!IMPORTANT]
>Ström inte på enheten som du registrerar igen förrän du har slutfört registreringen för den. 


### <a name="merge-hash-data"></a>Slå samman hash-data

Du måste ha data i CSV-filerna kombinerade i en enda fil för att slutföra registreringen. Här är ett PowerShell-exempelskript som gör det enkelt:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrera enheter med hjälp av administrationsportalen

I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)väljer du **Enheter** i det vänstra navigeringsfönstret. Titta efter avsnittet Microsoft Managed Desktop på menyn och välj **Enheter**. På arbetsytan Microsoft Hanterade skrivbordsenheter väljer du **+ Registrera-enheter,** som gör att du kan registrera nya enheter.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gör så här:

1. Ange **en sökväg** till CSV-filen du skapade tidigare i Filuppladdning.
2. Välj en [enhetsprofil](../service-description/profiles.md) i listrutan.
3. Välj **Registrera enheter**. Systemet lägger till enheterna i din lista med enheter på enheter , **markerade som** **Väntande registrering.** Registrering tar vanligtvis mindre än 10 minuter och  när enheten lyckas visas den som Redo för användare. Det innebär att den är redo att börja använda och väntar på att användaren ska börja använda den.

> [!NOTE]
> Om du manuellt ändrar azure Active Directory-gruppmedlemskap för en enhet omtilldekas den automatiskt till gruppen för dess enhetsprofil och tas bort från grupper med konflikter.

Du kan övervaka förloppet för enhetsregistreringen på huvudsidan. Möjliga delstater som rapporterats där är:

| Delstat | Beskrivning |
|---------------|-------------|
| Registrering väntar | Registreringen är inte klar än. Kom tillbaka senare. |
| Registreringen misslyckades | Registreringen kunde inte slutföras. Mer information [finns i Felsökning av](#troubleshooting-device-registration) enhetsregistrering. |
| Redo för användare | Registreringen har lyckats och enheten är nu redo att levereras till användaren. Microsoft Managed Desktop vägleder dem genom första gången, så du behöver inte göra ytterligare förberedelser. |
| Aktiv | Enheten har levererats till användaren och de har registrerats i din klientorganisation. Den här statusen anger också att de regelbundet använder enheten. |
| Inaktiv | Enheten har levererats till användaren och de har registrerats i din klientorganisation. Men de har inte använt enheten nyligen (under de senaste 7 dagarna).  | 

#### <a name="troubleshooting-device-registration"></a>Felsökning av enhetsregistrering

| Felmeddelande | Information |
|---------------|-------------|
| Enheten hittades inte | Det gick inte att registrera den här enheten eftersom det inte gick att hitta en matchning för den angivna tillverkaren, modellen eller serienumret. Bekräfta dessa värden med din enhetsleverantör. |
| Maskinvaruhash inte giltig | Den maskinvaru-hash du angav för den här enheten är inte korrekt formaterad. Dubbelkolla maskinvaruhashen och skicka in igen. |
| Enheten är redan registrerad | Den här enheten är redan registrerad i din organisation. Inga ytterligare åtgärder krävs. |
| Enhet som påstås av en annan organisation | Den här enheten har redan blivit anspråksad av en annan organisation. Kontrollera med din enhetsleverantör. |
| Oväntat fel | Det gick inte att behandla din begäran automatiskt. Kontakta supporten och ange ditt begärande-ID: <requestId> |

### <a name="check-the-image"></a>Kontrollera bilden

Om enheten kommer från en Microsoft Managed Desktop-partnerleverantör ska bilden vara korrekt.

Du får också gärna använda bilden på egen hand om du föredrar det. Kontakta microsofts representant som du arbetar med för att komma igång och informera dig om var och hur du använder bilden.

### <a name="autopilot-group-tag"></a>Autopilot-grupptagg

När du använder administratörsportalen för att registrera enheter tilldelar vi automatiskt **Microsoft365Managed_Autopilot** på Autopilot-grupptaggen.
Tjänsten övervakar alla Microsoft Managed Desktop-enheter dagligen och tilldelar grupptaggen till alla som inte redan har den.

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar över enheten till användaren kontrollerar du att du har skaffat och [tillämpat lämpliga licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser används kan [](get-started-devices.md)du förbereda användarna för att använda enheter och sedan starta enheten och gå vidare via Windows-konfigurationen.
