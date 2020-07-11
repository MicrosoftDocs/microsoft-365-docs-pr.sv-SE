---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101665"
---
# <a name="register-new-devices-yourself"></a>Registrera nya enheter själv

Microsoft Managed Desktop kan fungera med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen). Du kan registrera enheter med hjälp av Microsoft Managed Desktop Admin Portal.

> [!NOTE]
> Arbeta med en partner för att få enheter? Om så är fallet behöver du inte oroa dig för att få hårdvaran hashar; De tar hand om det åt dig. Se till att din partner upprättar en relation med dig i [Partner center](https://partner.microsoft.com/dashboard). Din partner kan läsa mer på [Partner Center hjälp](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). När denna relation har upprättats registrerar din partner helt enkelt enheter för din räkning – inga ytterligare åtgärder krävs från dig. Om du vill se informationen eller om din partner har frågor läser du [Steg för partner för att registrera enheter](register-devices-partner.md). När enheterna har registrerats kan du fortsätta [med att kontrollera bilden](#check-the-image) och leverera [enheterna](#deliver-the-device) till användarna.

## <a name="prepare-to-register-brand-new-devices"></a>Förbered att registrera helt nya enheter


När du har de nya enheterna i handen följer du dessa steg:

1. [Hämta maskinvaruhhhen för varje enhet.](#obtain-the-hardware-hash)
2. [Slå samman hash-data](#merge-hash-data)
3. [Registrera enheterna i Microsoft Managed Desktop](#register-devices).
4. [Dubbelkolla att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Skaffa maskinvaruhhh

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhhh. Du har tre alternativ för att få den här informationen:

- Fråga oem-leverantören om registreringsfilen för Autopilot, som innehåller maskinvaruhännaren.
- Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla in resultaten i en fil.
- Starta varje enhet – men slutför inte installationsupplevelsen för Windows – och [samla in hasharen på ett flyttbart flashminne](#flash-drive-method).

#### <a name="powershell-script-method"></a>PowerShell-skriptmetod

1.  Öppna en PowerShell-prompt med administrativa rättigheter.
2.  Köra`Install-Script -Name Get-MMDRegistrationInfo`
3.  Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>Flash-enhet metod

1. På en annan enhet än den du registrerar sätter du i en USB-enhet.
2. Öppna en PowerShell-prompt med administrativa rättigheter.
3. Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Slå på enheten du registrerar, men *starta inte installationsupplevelsen*. Om du av misstag startar installationen måste du återställa eller konfigurera om enheten.
5. Sätt i USB-enheten och tryck sedan på SKIFT + F10.
6. Öppna en PowerShell-prompt med administrativa rättigheter och kör sedan `cd <pathToUsb>` .
7. Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`

>[!IMPORTANT]
>Slå inte på enheten du registrerar igen förrän du har registrerat dig för den. 


### <a name="merge-hash-data"></a>Sammanfoga hash-data

Du måste ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen. Här är ett exempel på PowerShell-skript för att göra det enkelt:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>Registrera enheter

CSV-filen måste vara i ett särskilt format för registrering. Om du själv har samlat in data i föregående steg bör filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.

>[!NOTE]
>För din bekvämlighet kan du ladda ner ett [exempel CSV fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).

Filen måste innehålla **exakt samma kolumnrubriker** som exemplet en (tillverkare, modell, etc.), men dina egna data för de andra raderna. Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data enbart på rad 1, och ange bara data i raderna 2 och lägre. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Om du glömmer att ändra någon av exempeldata, kommer registreringen misslyckas.

#### <a name="register-devices-by-using-the-admin-portal"></a>Registrera enheter med hjälp av adminportalen

Välj **Enheter** i det vänstra navigeringsfönstret i Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal) Välj **+ Registrera enheter;** fly-in öppnar:

[![Fly-in efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar det nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Gör så här:

1. I **Filöverföring**anger du en sökväg till CSV-filen som du skapade tidigare.
2. Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål. Det finns inga formatkrav för dessa värden.
3. Välj **Registrera enheter**. Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerade som **Registrering väntar**. Registreringen tar vanligtvis mindre än 10 minuter, och när den lyckas visas enheten som **redo för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.


Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop - Devices.** Möjliga tillstånd som rapporteras där inkluderar:

| Statligt | Beskrivning |
|---------------|-------------|
| Registrering väntar | Registreringen är inte klar ännu. Kom tillbaka senare. |
| Registreringen misslyckades | Det gick inte att slutföra registreringen. Mer information finns i [Registrering av felsökning av enheten.](#troubleshooting-device-registration) |
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

Du är också välkommen att använda bilden på egen hand om du föredrar. För att komma igång kontaktar du den Microsoft-representant du arbetar med och de ger dig plats och steg för att tillämpa avbildningen.

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar över enheten till användaren ska du se till att du har skaffat och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser tillämpas kan du [göra användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå vidare genom installationen av Windows.






