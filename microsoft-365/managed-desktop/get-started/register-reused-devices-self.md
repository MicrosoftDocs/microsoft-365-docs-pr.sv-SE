---
title: Registrera befintliga enheter själv
description: Registrera återanvändda enheter du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
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
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445572"
---
# <a name="register-existing-devices-yourself"></a>Registrera befintliga enheter själv

>[!NOTE]
>I det här avsnittet beskrivs hur du återanvänder enheter du redan har och registrerar dem i Microsoft Managed Desktop. Om du arbetar med helt nya enheter följer du instruktionerna i Registrera [nya enheter i Microsoft Managed Desktop själv i](register-devices-self.md) stället.

Processen för partner beskrivs i Steg [för partner för att registrera enheter.](register-devices-partner.md)

Microsoft Managed Desktop kan arbeta med helt nya enheter eller återanvända enheter som du kanske redan har (vilket innebär att du måste animera dem igen). Du kan registrera enheter med Microsoft Managed Desktop i Microsoft Endpoint Manager-portalen.

## <a name="prepare-to-register-existing-devices"></a>Förbered dig för att registrera befintliga enheter


Så här registrerar du befintliga enheter:

1. [Hämta maskinvaruhash för varje enhet.](#obtain-the-hardware-hash)
2. [Slå samman hash-data](#merge-hash-data)
3. [Registrera enheterna i Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Kontrollera att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Hämta maskinvaruhash

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaru-hash. Du har fyra alternativ för att hämta den här informationen från enheter som du redan använder:

- Be din OEM-leverantör om AutoPilot-registreringsfilen, som innehåller maskinvaru-hashfilerna.
- Samla in information i [Konfigurationshanteraren för Microsoft Endpoint](#microsoft-endpoint-configuration-manager).
- Kör ett Windows PowerShell-skript – antingen med hjälp av [Active Directory](#active-directory-powershell-script-method) eller manuellt på varje enhet – och samla in resultaten i en fil. [](#manual-powershell-script-method)
- Starta varje enhet– men slutför inte Windows-installationen – och samla in hashtaggarna på ett [flyttbart flash-minne.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvarushashar från befintliga enheter som du vill registrera i Microsoft Managed Desktop.

> [!IMPORTANT]
> Alla enheter som du vill få den här informationen till måste köra Windows 10, version 1703 eller senare. 

Om du har uppfyllt alla krav är du redo att samla in informationen genom att göra följande:

1. Välj Övervakning i konfigurationshanterarens **konsol.** 
2. På arbetsytan Övervakning expanderar du **noden Rapportering,** **expanderar Rapporter** och väljer **noden Maskinvara –** Allmänt. 
3. Kör rapporten Windows **Autopilot-enhetsinformation** och visa resultatet.
4. I rapportvisaren väljer du **ikonen Exportera** och sedan **CSV-alternativet (kommaavgränsad).**
5. När du har sparat filen måste du filtrera resultaten till bara de enheter som du planerar att registrera dig på Microsoft Managed Desktop och ladda upp data till Microsoft Managed Desktop. Öppna Microsoft Endpoint Manager och gå till menyn **Enheter,** leta sedan efter avsnittet Microsoft Managed Desktop och välj **Enheter**. Välj **+ Registrera enheter** så öppnas en flygblads för att registrera nya enheter.


Mer information [finns i Registrera enheter med hjälp av](#register-devices-by-using-the-admin-portal) administrationsportalen.


#### <a name="active-directory-powershell-script-method"></a>PowerShell-skriptmetod för Active Directory

I en Active Directory-miljö kan du använda PowerShell-cmdleten för att fjärr samla in information från enheter i `Get-WindowsAutoPilotInfo` Active Directory-grupper med hjälp av WinRM. Du kan också använda `Get-AD Computer` cmdleten och få filtrerade resultat för ett specifikt namn på maskinvarumodellen som ingår i katalogen. Innan du fortsätter bekräftar du först dessa krav och fortsätter sedan med stegen:

- WinRM är aktiverat.
- De enheter du vill registrera är aktiva i nätverket (det vill säga att de inte är frånkopplade eller inaktiverade).
- Kontrollera att du har en parameter för domänbehörigheter för autentiseringsuppgifter som kan köras via fjärrstyrning på enheterna.
- Kontrollera att Windows-brandväggen tillåter åtkomst till WMI. Det gör du genom att följa de här stegen:

    1. Öppna Kontrollpanelen **för Windows Defender-brandväggen** och välj **Tillåt en app eller funktion i Windows Defender-brandväggen.**
    
    2. Leta **reda på Windows Management Instrumentation (WMI)** i listan, aktivera både privat och **offentlig** och välj sedan **OK.**

1.  Öppna en PowerShell-fråga med administrativa rättigheter.

2.  Kör *något av* följande skript:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Öppna alla kataloger där det kan finnas poster för enheterna. Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory. Observera att borttagningen kan ta några timmar att bearbeta helt.

4. Åtkomsthanteringstjänster där det kan finnas poster för enheterna. Ta bort poster för varje enhet från *alla* hanteringstjänster, inklusive Konfigurationshanteraren för Microsoft Slutpunkt, Microsoft Intune och Windows Autopilot. Observera att borttagningen kan ta några timmar att bearbeta helt.

Nu kan du fortsätta att [registrera enheter](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Manuell PowerShell-skriptmetod

1.  Öppna en PowerShell-fråga med administrativa rättigheter.
2.  Kör `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Kör `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Slå samman hash-data.](#merge-hash-data)

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
10. [Slå samman hash-data.](#merge-hash-data)

>[!IMPORTANT]
>Ström inte på enheten som du registrerar igen förrän du har slutfört registreringen för den. 



### <a name="merge-hash-data"></a>Slå samman hash-data

Om du har samlat in maskinvaruhashdata med de manuella PowerShell- eller flash-metoderna måste du nu ha data i CSV-filerna kombinerade i en enda fil för att slutföra registreringen. Här är ett PowerShell-exempelskript som gör det enkelt:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Med hash-data kopplade till en CSV-fil kan du nu fortsätta att [registrera enheterna](#register-devices-by-using-the-admin-portal).


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrera enheter med hjälp av administrationsportalen

I [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)väljer du **Enheter** i det vänstra navigeringsfönstret. Titta efter avsnittet Microsoft Managed Desktop på menyn och välj **Enheter**. På arbetsytan Microsoft Hanterade skrivbordsenheter väljer du **+ Registrera-enheter,** som gör att du kan registrera nya enheter.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gör så här:

1. Ange **en sökväg** till CSV-filen du skapade tidigare i Filuppladdning.

1. Välj **Registrera enheter**. Systemet lägger till enheterna i din lista med enheter i bladet **Enheter**, markerade som **Väntar på registrering.** Registrering tar vanligtvis mindre än 10 minuter och  när enheten lyckas visas den som Redo för användare. Det innebär att den är redo att börja använda och väntar på att användaren ska börja använda den.


Du kan övervaka förloppet för enhetsregistreringen på huvudsidan. Möjliga delstater som rapporterats där är:

| Delstat | Beskrivning |
|---------------|-------------|
| Registrering väntar | Registreringen är inte klar än. Kom tillbaka senare. |
| Registreringen misslyckades | Registreringen kunde inte slutföras. Mer information [finns i Felsökning av](#troubleshooting-device-registration) enhetsregistrering. |
| Redo för användare | Registreringen har lyckats och enheten är nu redo att levereras till användaren. Microsoft Managed Desktop vägleder dem genom första gången, så du behöver inte göra ytterligare förberedelser. |
| Aktiv | Enheten har levererats till användaren och de har registrerats i din klientorganisation. Det här betyder också att de regelbundet använder enheten. |
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

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar över enheten till användaren kontrollerar du att du har skaffat och [tillämpat lämpliga licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser används kan [](get-started-devices.md)du förbereda användarna för att använda enheter och sedan starta enheten och gå vidare via Windows-konfigurationen.









