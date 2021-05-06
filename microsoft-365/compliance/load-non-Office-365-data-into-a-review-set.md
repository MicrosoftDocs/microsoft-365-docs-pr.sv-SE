---
title: Läsa in data som Microsoft 365 i en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du importerar icke-Microsoft 365 data till en granskningsuppsättning för analys i Advanced eDiscovery fall.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161849"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Läsa in data som Microsoft 365 i en granskningsuppsättning

Alla dokument som du behöver analysera i Advanced eDiscovery finns inte i Microsoft 365. Med funktionen för Microsoft 365 dataimport i Advanced eDiscovery kan du ladda upp dokument som inte finns i Microsoft 365 till en granskningsuppsättning. Den här artikeln visar hur du för in icke-Microsoft 365 dokument till Advanced eDiscovery för analys.

## <a name="requirements-to-upload-non-office-365-content"></a>Krav för att överföra innehåll som inte Office 365 innehåll

Om du använder funktionen för uppladdning Microsoft 365 som beskrivs i den här artikeln krävs att du har följande:

- Alla medarbetare som du vill associera icke-Microsoft 365 måste tilldelas rätt licens. Mer information finns i [Komma igång med Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Ett befintligt Advanced eDiscovery ärende.

- Dokumentföretag måste läggas till i ärendet innan du kan överföra och associera icke-Microsoft 365 data med dem.

- Icke-Microsoft 365-data måste vara en filtyp som stöds av Advanced eDiscovery. Mer information finns i [Filtyper som stöds i Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Alla filer som laddas upp till en granskningsuppsättning måste finnas i mappar, där varje mapp är associerad med en särskild person. Namnen för de här mapparna måste ha följande namnformat: *alias@domainname*. Den alias@domainname måste vara användarens alias Microsoft 365 och domän. Du kan samla alla alias@domainname i en rotmapp. Rotmappen kan endast innehålla alias@domainname mappar. Lösa filer i rotmappen stöds inte.

   Mappstrukturen för de icke-Microsoft 365 data som du vill ladda upp liknar följande exempel:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Där abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, och staci.gonzalez@contoso.com är i det fallet SMTP-adresserna till biblioteksadresserna.

   ![Mappstruktur för Microsoft 365 datauppladdning](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Ett konto som har tilldelats rollgruppen för eDiscovery-hanteraren (och lagts till som eDiscovery-administratör).

- Verktyget AzCopy v8.1 är installerat på en dator som har tillgång till den Microsoft 365 andra innehållsmappstrukturen. Information om hur du installerar AzCopy finns i [Överföra data med AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy). Installera AzCopy på standardplatsen, d.v.s. **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**. Du måste använda AzCopy v8.1. Andra versioner av AzCopy kanske inte fungerar vid inläsning av Microsoft 365-data i Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Upload icke-Microsoft 365 innehåll i Advanced eDiscovery

1. Som eDiscovery Manager eller eDiscovery-administratör öppnar du Advanced eDiscovery och går till den händelse som icke-Microsoft 365-data laddas upp till.  

2. Klicka **på Granska uppsättningar** och välj sedan granskningsuppsättningen för att ladda upp de Microsoft 365 data till.  Om du inte har någon granskningsuppsättning kan du skapa en. 
 
3. I granskningsuppsättningen klickar du på Hantera **granskningsuppsättning** och sedan på Visa uppladdningar på **panelen Microsoft 365 data.** 

4. Klicka **Upload filer för** att starta dataimportguiden.

   ![Upload filer](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   Det första steget i guiden förbereder en säker plats från Microsoft som Azure Storage att ladda upp filerna till.  När förberedelsen är klar **blir knappen Upload filer** aktiv.

   ![Import för Microsoft 365: Förbereda](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Klicka **på Nästa: Upload filer**.

6. På **Upload filer** gör du följande:

   ![Icke-Microsoft 365: Upload filer](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. I rutan **Sökväg till platsen för** filer verifierar du eller anger platsen för rotmappen där du har lagrat de Microsoft 365 data du vill ladda upp. Exempel: För platsen för de exempelfiler som visas i avsnittet Innan du börjar skriver du **%USERPROFILE\Nedladdningar\nonO365**. När du har rätt plats ser du till att AzCopy-kommandot som visas i rutan under sökvägen uppdateras korrekt.

   b. Klicka **på Kopiera till Urklipp** för att kopiera kommandot som visas i rutan.

7. Starta en Windows kommandotolk, klistra in kommandot som du kopierade  i föregående steg och tryck sedan på Retur för att starta kommandot AzCopy.  När du startar kommandot laddas filerna som Microsoft 365 upp till den plats Azure Storage förbereddes i steg 4.

   ![Import utan Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Som tidigare nämnts måste du använda AzCopy v8.1 för att kunna använda kommandot som finns på **sidan Upload filer.** Om det angivna AzCopy-kommandot misslyckas kan du [gå till Felsöka AzCopy i Advanced eDiscovery.](troubleshooting-azcopy.md)

8. Gå tillbaka till säkerhets- & säkerhets- och efterlevnadscentret och **klicka på Nästa: Bearbeta** filer i guiden.  Detta initierar bearbetning, text extrahering och indexering av de Microsoft 365 filer som laddats upp till Azure Storage platsen.  

9. Spåra förloppet för bearbetningen av filerna på  sidan **Processfiler** eller på fliken Jobb genom att visa ett jobb med namnet Lägga till **Microsoft 365-data i en uppsättning med granskare.**  När jobbet är klart blir de nya filerna tillgängliga i granskningsuppsättningen.

   ![Import utan Microsoft 365: Bearbeta filer](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. När bearbetningen är klar kan du stänga guiden.