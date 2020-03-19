---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42806794"
---
# <a name="register-new-devices-yourself"></a>Registrera nya enheter själv

Microsoft Managed Desktop kan arbeta med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen). Du kan registrera enheter med Hjälp av Microsoft Managed Desktop på Azure Portal.

> [!NOTE]
> Arbetar du med en partner för att hämta enheter? Om så är fallet behöver du inte oroa dig för att få hårdvarahashes; De tar hand om det åt dig. Kontrollera att din partner upprättar en relation med dig i [Partnercenter](https://partner.microsoft.com/dashboard) och att de innehåller delegerade administrationsprivilegier för Azure Active Directory och Office 365. Din partner kan läsa mer på [Hjälp i PartnerCenter.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) När denna relation har upprättats registrerar din partner helt enkelt enheter för din räkning – inga ytterligare åtgärder krävs från dig. Om du vill se informationen, eller om din partner har frågor, se [Steg för partners för att registrera enheter](register-devices-partner.md). När enheterna har registrerats kan du fortsätta [med att kontrollera avbildningen](#check-the-image) och [leverera enheterna](#deliver-the-device) till användarna.

## <a name="prepare-to-register-brand-new-devices"></a>Förbered dig på att registrera helt nya enheter


När du har de nya enheterna i handen följer du följande steg:

1. [Skaffa maskinvaruhash för varje enhet.](#obtain-the-hardware-hash)
2. [Sammanfoga hash-data](#merge-hash-data)
3. [Registrera enheterna i Microsoft Managed Desktop](#register-devices).
4. [Dubbelkolla att bilden är korrekt.](#check-the-image)
5. [Leverera enheten](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Skaffa maskinvaruhash

Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhash. Du har tre alternativ för att få den här informationen:

- Fråga oem-leverantören om AutoPilot-registreringsfilen, som inkluderar maskinvaruhashar.
- Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla in resultaten i en fil.
- Starta varje enhet – men slutför inte Windows-installationsupplevelsen – och [samla in hasharna på ett flyttbart flashminne](#flash-drive-method).

#### <a name="powershell-script-method"></a>PowerShell-skriptmetod

1.  Öppna en PowerShell-prompt med administrativa rättigheter.
2.  Köra`Install-Script -Name Get-MMDRegistrationInfo`
3.  Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>Flash-enhet metod

1. Sätt i en USB-enhet på en annan enhet än den du registrerar.
2. Öppna en PowerShell-prompt med administrativa rättigheter.
3. Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Slå på enheten som du registrerar, men *starta inte installationsupplevelsen*. Om du av misstag startar installationsupplevelsen måste du återställa eller avbilda enheten igen.
5. Sätt i USB-enheten och tryck sedan på SKIFT + F10.
6. Öppna en PowerShell-prompt med administrativa `cd <pathToUsb>`rättigheter och kör sedan .
7. Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`

>[!IMPORTANT]
>Slå inte på enheten som du registrerar igen förrän du har slutfört registreringen för den. 


### <a name="merge-hash-data"></a>Sammanfoga hash-data

Du måste ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen. Här är ett exempel powershell-skript för att göra detta enkelt:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>Registrera enheter

CSV-filen måste vara i ett visst format för registrering. Om du har samlat in data själv i föregående steg ska filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.

>[!NOTE]
>För din bekvämlighet kan du ladda ner ett [exempel CSV-fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).

Filen måste innehålla **exakt samma kolumnrubriker** som exempelrubriken (tillverkare, modell osv.), men dina egna data för de andra raderna. Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data på rad 1 ensam, och ange bara data i rad 2 och nedan. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Om du glömmer att ändra någon av exempeldata misslyckas registreringen.

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrera enheter med hjälp av Azure Portal

Välj **Enheter** i den vänstra navigeringsfönstret i Microsoft Managed Desktop [Azure Portal.](https://aka.ms/mmdportal) Välj **+ Registrera enheter**; inflygningen öppnas:

[![Inflygning efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar den nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Följ anvisningarna nedan:

1. Ange en sökväg till den CSV-fil som du skapade tidigare i **Filuppladdning.**
2. Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål. Det finns inga formatkrav för dessa värden.
3. Välj **Registrera enheter**. Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerat som **Registreringsväntande**. Registreringen tar vanligtvis mindre än 10 minuter, och när enheten lyckas visas som **klar för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.


Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop – Enheter.** Möjliga tillstånd som rapporteras där inkluderar:

| Statligt | Beskrivning |
|---------------|-------------|
| Väntande registrering | Registreringen är inte klar än. Kom tillbaka senare. |
| Registreringen misslyckades | Det gick inte att slutföra registreringen. Mer information finns i [Felsöka enhetsregistrering.](#troubleshooting-device-registration) |
| Redo för användare | Registreringen lyckades och enheten är nu redo att levereras till slutanvändaren. Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser. |
| Aktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation. Detta indikerar också att de regelbundet använder enheten. |
| Inaktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation. De har dock inte använt enheten nyligen (under de senaste 7 dagarna).  | 

#### <a name="troubleshooting-device-registration"></a>Felsöka enhetsregistrering

| Felmeddelande | Information |
|---------------|-------------|
| Enheten hittades inte | Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den medföljande tillverkaren, modellen eller serienumret. Bekräfta dessa värden med din enhetsleverantör. |
| Maskinvaruhash är ogiltigt | Maskinvaruhash som du angav för den här enheten har inte formaterats korrekt. Dubbelkolla maskinvaruhash och skicka sedan in igen. |
| Enheten har redan registrerats | Den här enheten är redan registrerad i din organisation. Inga ytterligare åtgärder krävs. |
| Enhet som en annan organisation har gjort anspråk på | Den här enheten har redan hävdats av en annan organisation. Kontrollera med din enhetsleverantör. |
| Oväntat fel | Det gick inte att behandla din begäran automatiskt. Kontakta supporten och ange begärande-ID:<requestId> |

### <a name="check-the-image"></a>Kontrollera bilden

Om enheten har hämtats från en Microsoft Managed Desktop-partnerleverantör bör avbildningen vara korrekt.

Du är också välkommen att använda bilden på egen hand om du vill. För att komma igång kontaktar du den Microsoft-representant som du arbetar med och de ger dig plats och steg för att använda avbildningen.

### <a name="deliver-the-device"></a>Leverera enheten

> [!IMPORTANT]
> Innan du lämnar ut enheten till användaren kontrollerar du att du har fått och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.

Om alla licenser tillämpas kan du [förbereda användarna för att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå igenom installationsprogrammet för Windows.






