---
title: Registrera befintliga enheter själv
description: Registrera återanvända enheter som du kanske redan har själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810044"
---
# <a name="register-existing-devices-yourself"></a>Registrera befintliga enheter själv

>[!NOTE]
>I det här avsnittet beskrivs stegen för att återanvända enheter som du redan har och registrera dem på Microsoft Managed Desktop. Om du arbetar med helt nya enheter följer du stegen i [Registrera nya enheter på Microsoft Managed Desktop själv](register-devices-self.md) i stället.

Processen för partners dokumenteras i [Steg för partner för att registrera enheter](register-devices-partner.md).

Microsoft Managed Desktop kan fungera med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen). Du kan registrera enheter med hjälp av Microsoft Managed Desktop på Azure Portal.

## <a name="prepare-to-register-existing-devices"></a>Förbereda för att registrera befintliga enheter


Så här registrerar du befintliga enheter:

1. [Hämta maskinvaruhhh för varje enhet.](#obtain-the-hardware-hash)
2. [Slå samman hash-data](#merge-hash-data)
3. [Registrera enheterna i Microsoft Managed Desktop](#register-devices).
4. [Dubbelkolla att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Skaffa maskinvaruhhh

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhh. Du har fyra alternativ för att hämta den här informationen från enheter som du redan använder:

- Fråga oem-leverantören om registreringsfilen för Autopilot, som innehåller maskinvaruhännarna.
- Skapa en anpassad rapport i [Configuration Manager](#configuration-manager).
- Kör ett Windows PowerShell-skript – antingen med Hjälp av [Active Directory](#active-directory-powershell-script-method) eller [manuellt](#manual-powershell-script-method) på varje enhet – och samla in resultaten i en fil.
- Starta varje enhet – men slutför inte installationsupplevelsen för Windows – och [samla in hasharen på ett flyttbart flashminne](#flash-drive-method).

#### <a name="configuration-manager"></a>Konfigurationshanteraren

Du kan använda Microsoft Endpoint Configuration Manager för att samla in maskinvaruhcens från befintliga enheter som du vill registrera dig på Microsoft Managed Desktop.

> [!IMPORTANT]
> Alla enheter som du vill hämta den här informationen för måste köra Windows 10, version 1703 eller senare. Du behöver också en enhet som är en Configuration Manager-klient som är ansluten till Configuration Manager-platsen (Current Branch). Du behöver också rollen Reporting Point Site System som konfigurerats i din miljö med SQL Server Reporting Services aktiverat. 

Om du har uppfyllt alla dessa förutsättningar är du redo att samla in informationen genom att följa dessa steg:

1. Välj **Övervakning**i Configuration Manager-konsolen . 
2. Expandera **Rapportering**på arbetsytan Övervakning och välj sedan **Rapporter**. 
3. Öppna guiden Skapa rapport i avsnittet **Skapa** **rapport** på fliken **Start.** 
4. På sidan **Information** ställer du in följande inställningar: 
    - **Namn:** Ange ett namn på rapporten. 
    - **Beskrivning:** Ange en beskrivning av rapporten. 
    - **Server:** Visar namnet på den rapportserver som du skapar rapporten på. 
    - **Sökväg:** Välj **Bläddra** om du vill ange en mapp där du vill lagra rapporten. 
5. Välj **Nästa**. 
6. Granska inställningarna på sidan **Sammanfattning.** Välj **Föregående** om du vill ändra inställningarna eller välj **Nästa** om du vill skapa rapporten i Configuration Manager. 
7. På sidan **Slutförd** väljer du **Stäng** för att avsluta guiden och öppna **Report Builder** för att ange rapportinställningarna. Ange ditt användarkonto och lösenord om du uppmanas att göra det och välj sedan **OK.** Om Report Builder inte är installerat på enheten uppmanas du att installera den. Välj **Kör för att installera Report Builder**, som krävs för att ändra och skapa rapporter. 


**I Microsoft Report Builder**anger du SQL-uttrycket för rapporten och gör så här:

1. Välj **Datauppsättningar**i den vänstra rutan och högerklicka sedan på Lägg till **datauppsättning**.
2. Gå till fliken **Fråga** och ange sedan namnet som *DataSet0*. 
3. Välj **Använd en datauppsättning som är inbäddad i rapporten.** Report Builder öppnas.
4. Välj **Datakälla**i **Report Builder:**. Välj standarddatakällan, som ska börja med "AutoGen". 
5. Välj **Frågetyp som text**och ange sedan den här frågan:




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. Navigera till fliken **Fält,** wehre-värden för **Fältnamn** och **Fältkälla** bör redan fyllas i. Om de inte är det väljer du **Lägg till**och väljer sedan **Frågefält**. Ange **fältnamn** och **fältkälla**.
6. Upprepa för vart och ett av dessa värden: 
    - Tillverkare 
    - Modell 
    - Tal 
    - HårdvaraHash
7. Välj **OK**.

**Definiera sedan rapportens visning och skapa rapporten** genom att följa dessa steg:

1. Välj **Tabell eller Matris**; en ny guide öppnas.
2. Välj **en befintlig datauppsättning i den här rapporten eller en delad datauppsättning i**Välj en **datauppsättning**.  
3. Välj **DataSet0** (standard) och välj sedan **Nästa**.
4. Dra **tillverkare,** **modell**och **serienummer** till rutan **Radgrupper.** Dra **HardwareHash** till rutan **Värden** och välj sedan **Nästa**.
5. Avmarkera kryssrutorna för **Visa delsummor och totalsummor** och **Expandera/komprimera grupper**. Välj **Nästa**.
6. Välj **Slutför**.
7. Välj **Kör** för att köra rapporten. Kontrollera att rapporten innehåller den information du förväntar dig. Om det behövs väljer du **Design** för att återgå till designvyn för att ändra rapporten.
8. Välj **Spara** om du vill spara rapporten på rapportservern. Du kan köra den nya rapporten i noden Rapporter på arbetsytan Övervakning. 

**Slutligen exportera rapporten och använda den för att registrera enheter** genom att följa dessa steg. (Du bör bara behöva följa steg 1 och 2 i det här avsnittet om du har navigerat bort efter föregående steg.):

1. Välj **Övervakning**i Configuration Manager-konsolen .
2. Expandera Rapportering **i** **Övervakning**och välj sedan **Rapporter**.
3. Leta reda på rapporten med det namn du skapade tidigare.
4. Högerklicka på den här rapporten och välj **Kör**.
5. I dialogrutan som öppnas väljer du **Exportera** och väljer sedan **Spara som CSV**.
6. Den här versionen av rapportextraher från alla Windows 10-enheter som Configuration Manager kommunicerar med. Du måste filtrera resultaten till just de enheter som du planerar att registrera dig hos Microsoft Managed Desktop.


> [!IMPORTANT]
> Frågan i Configuration Manager tillåter inte blanksteg i exporterade kolumnnamn. Det är därför stegen hade du ange "Serial_Number" och "HardwareHash." Nu när du har den exporterade CSV-filen måste du redigera rapportrubrikerna för att läsa *Serienummer* och *Maskinvaruh hash* som visas här innan du fortsätter med enhetsregistrering.

Nu kan du fortsätta att [registrera enheter med hjälp av Azure Portal](#register-devices-by-using-the-azure-portal).


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell-skriptmetod

I en Active Directory-miljö `Get-MMDRegistrationInfo` kan du använda PowerShell-cmdlet för att fjärrsamla information från enheter i Active Directory-grupper med winrm. Du kan också `Get-AD Computer` använda cmdlet och få filtrerade resultat för en viss maskinvarumodell namn som ingår i katalogen. För att göra detta, först bekräfta dessa förutsättningar och sedan gå vidare med stegen:

- WinRM är aktiverat.
- De enheter som du vill registrera är aktiva i nätverket (det vill säga de är inte frånkopplade eller avstängda).
- Kontrollera att du har en domänautentiseringsparameter som har behörighet att köras på distans på enheterna.
- Kontrollera att Windows-brandväggen ger åtkomst till WMI. Gör så här:
    1. Öppna kontrollpanelen **för Windows Defender-brandväggen** och välj **Tillåt en app eller funktion via Windows Defender-brandväggen**.
    2. Leta reda på **WMI (Windows Management Instrumentation)** i listan, aktivera både **privat och offentligt**och välj sedan **OK**.

1.  Öppna en PowerShell-prompt med administrativa rättigheter.
2.  Kör *något* av följande skript:
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. Få tillgång till alla kataloger där det kan finnas poster för enheterna. Ta bort poster för varje enhet från *alla* kataloger, inklusive Windows Server Active Directory Domain Services och Azure Active Directory. Tänk på att denna borttagning kan ta några timmar att helt bearbeta.
4. Åtkomsthanteringstjänster där det kan finnas poster för enheterna. Ta bort poster för varje enhet från *alla* hanteringstjänster, inklusive Microsoft Endpoint Configuration Manager, Microsoft Intune och Windows Autopilot. Tänk på att denna borttagning kan ta några timmar att helt bearbeta.

Nu kan du fortsätta att [registrera enheter](#register-devices).

#### <a name="manual-powershell-script-method"></a>Manuell PowerShell-skriptmetod

1.  Öppna en PowerShell-prompt med administrativa rättigheter.
2.  Köra`Install-Script -Name Get-MMDRegistrationInfo`
3.  Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Slå samman hash-data.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Flash-enhet metod

1. På en annan enhet än den du registrerar sätter du i en USB-enhet.
2. Öppna en PowerShell-prompt med administrativa rättigheter.
3. Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Slå på enheten du registrerar, men *starta inte installationsupplevelsen*. Om du av misstag startar installationen måste du återställa eller konfigurera om enheten.
5. Sätt i USB-enheten och tryck sedan på SKIFT + F10.
6. Öppna en PowerShell-prompt med administrativa `cd <pathToUsb>`rättigheter och kör sedan .
7. Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`
10. [Slå samman hash-data.](#merge-hash-data)

>[!IMPORTANT]
>Slå inte på enheten du registrerar igen förrän du har registrerat dig för den. 



### <a name="merge-hash-data"></a>Sammanfoga hash-data

Om du samlade in maskinvaruhhh-data med de manuella PowerShell- eller flash-enhetsmetoderna måste du nu ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen. Här är ett exempel på PowerShell-skript för att göra det enkelt:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

Med hash-data samman till en CSV-fil kan du nu fortsätta att [registrera enheterna](#register-devices).

### <a name="register-devices"></a>Registrera enheter

CSV-filen måste vara i ett särskilt format för registrering. Om du själv har samlat in data i föregående steg bör filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.

>[!NOTE]
>För din bekvämlighet kan du ladda ner en [mall](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) för den här CSV-filen.

Filen måste innehålla **exakt samma kolumnrubriker** som exemplet en (tillverkare, modell, etc.), men dina egna data för de andra raderna. Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data enbart i rad 1, och ange bara data i raderna 2 och lägre. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Om du glömmer att ändra någon av exempeldata, kommer registreringen misslyckas.

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrera enheter med hjälp av Azure Portal

Välj **Enheter** i det vänstra navigeringsfönstret i Microsoft Managed Desktop [Azure Portal.](https://aka.ms/mmdportal) Välj **+ Registrera enheter;** fly-in öppnar:

[![Fly-in efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar det nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Följ anvisningarna nedan:

1. I **Filöverföring**anger du en sökväg till CSV-filen som du skapade tidigare.
2. Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål. Det finns inga formatkrav för dessa värden.
3. Välj **Registrera enheter**. Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerade som **Registrering väntar**. Registreringen tar vanligtvis mindre än 10 minuter, och när den lyckas visas enheten som **redo för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.


Du kan övervaka hur enhetsregistreringen fortskrider på sidan **Microsoft Managed Desktop - Devices.** Möjliga tillstånd som rapporteras där inkluderar:

| Statligt | Beskrivning |
|---------------|-------------|
| Registrering väntar | Registreringen är inte klar ännu. Kom tillbaka senare. |
| Registreringen misslyckades | Registreringen kunde inte slutföras. Mer information finns i [Registrering av felsökning av enheten.](#troubleshooting-device-registration) |
| Redo för användare | Registreringen lyckades och enheten är nu klar att levereras till slutanvändaren. Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser. |
| Aktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient. Detta indikerar också att de regelbundet använder enheten. |
| Inaktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient. De har dock inte använt enheten nyligen (under de senaste 7 dagarna).  | 

#### <a name="troubleshooting-device-registration"></a>Felsöka enhetsregistrering

| Felmeddelande | Information |
|---------------|-------------|
| Enheten hittades inte | Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den angivna tillverkaren, modellen eller serienumret. Bekräfta dessa värden med din enhetsleverantör. |
| Maskinvaruh hash är ogiltigt | Maskinvaruhhingen som du angav för den här enheten har inte formaterats korrekt. Dubbelkolla maskinvaruhhhen och skicka sedan in den igen. |
| Enheten har redan registrerats | Den här enheten är redan registrerad i din organisation. Inga ytterligare åtgärder krävs. |
| Enhet som påstås av en annan organisation | Den här enheten har redan hävdats av en annan organisation. Kontrollera med din enhetsleverantör. |
| Oväntat fel | Det gick inte att bearbeta din begäran automatiskt. Kontakta supporten och ange ID:et för begäran:<requestId> |

### <a name="check-the-image"></a>Kontrollera bilden

Om enheten kommer från en Microsoft Managed Desktop-partnerleverantör ska avbildningen vara korrekt.

Du är också välkommen att använda bilden på egen hand om du vill. För att komma igång kontaktar du den Microsoft-representant du arbetar med och ger dig plats och steg för att tillämpa avbildningen.

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar över enheten till användaren ska du se till att du har skaffat och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser tillämpas kan du [göra användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå vidare genom installationen av Windows.









