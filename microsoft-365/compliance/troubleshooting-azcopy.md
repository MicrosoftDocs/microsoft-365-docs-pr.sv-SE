---
title: Felsöka AzCopy i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Felsöka fel för Azure AzCopy vid inläsning av icke-Office 365-data för felåtgärder i Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162030"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Felsöka AzCopy i Advanced eDiscovery

När du läser in data eller dokument som inte är Microsoft 365 eller dokument för felreparation i Advanced eDiscovery tillhandahåller användargränssnittet ett Azure AzCopy-kommando som innehåller parametrarna för platsen där de filer du vill ladda upp lagras och azure-lagringsplatsen som filerna ska laddas upp till. Om du vill ladda upp dina dokument kopierar du det här kommandot och kör det sedan i en kommandotolk på den lokala datorn.  På följande skärmbild visas ett exempel på ett AzCopy-kommando:

![Upload filer som inte är Microsoft 365 filer](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Vanligtvis fungerar det kommando som tillhandahålls när du kör det. Det kan dock finnas tillfällen när kommandot som visas inte körs. Här är några möjliga orsaker.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>Den version av AzCopy som stöds är inte installerad på den lokala datorn

För stunden måste du använda AzCopy v8.1 för att läsa in icke-Microsoft 365-data i Advanced eDiscovery. Kommandot AzCopy som visas på **filsidan för Upload** som visas på föregående skärmbild returnerar ett fel om du inte använder AzCopy v8.1. Information om hur du installerar den [här versionen finns i Överföra data med AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy är inte installerat på den lokala datorn eller är inte installerat på standardplatsen

Om AzCopy inte är installerat eller om det är installerat på en annan plats än standardplatsen för installation (d.v.s. ) kan följande felmeddelande visas när du kör `%ProgramFiles(x86)%` kommandot AzCopy:

> Det går inte att hitta den angivna sökvägen.

Om AzCopy inte är installerat på den lokala datorn hittar du installationsinformationen under Överför data med [AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy). Se till att installera den på standardplatsen.

Om AzCopy är installerat, men det installeras på en annan plats än standardplatsen, kan du kopiera kommandot, klistra in det i en textfil och sedan ändra sökvägen till den plats där AzCopy är installerad. Om Azcopy till exempel finns i kan du ändra den `%ProgramFiles%` första delen av kommandot från till `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . När du har gör den här ändringen kopierar du den från textfilen och kör den i kommandotolken.

> [!TIP]
> Om AzCopy är installerat på en annan plats än standardplatsen för installation bör du överväga att avinstallera det och sedan installera om det på standardplatsen. Det här hjälper till att förhindra det här problemet i framtiden.