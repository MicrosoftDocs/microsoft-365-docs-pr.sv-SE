---
title: Inaktuellt visningsprogram för meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Appen Meddelandekryptering i Office 365 visningsprogram (OME) togs bort från Android- och Apple-butiker under 2018.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "52161810"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Inaktuellt visningsprogram för meddelandekryptering

Den 15 augusti 2018 tog vi bort mobilappen Meddelandekryptering i Office 365 (OME) Viewer från Android- och Apple-butiker. Mobilappen Visningsprogram för meddelandekryptering i Office 365 för att läsa e-postmeddelanden och bifogade filer som krypterades med den tidigare versionen av OME på Apple- och Android-telefoner. Förutom att ta bort OME-visningsappen gör vi inga andra ändringar i den tidigare versionen av OME.
  
## <a name="changes-from-august-2018"></a>Ändringar från augusti 2018

Som vi meddelade september 2017 har vi släppt en ny version av [Meddelandekryptering i Office 365](https://aka.ms/ome2017) så att användare kan skicka krypterade och skyddade meddelanden till alla inom eller utanför organisationen utan krav på mobilappen. Sedan dess har vi lagt till fler funktioner:
  
- [Mall för endast kryptering](https://aka.ms/encryptonly)

- [Kontroll för att dekryptera bifogade filer](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Med den här ändringen kan användarna inte längre ladda ned mobilappen från Visningsprogram för meddelandekryptering i Office 365 den 1 augusti. Därför kan e-postmottagare inte läsa meddelanden som krypterats med den tidigare versionen av OME på vissa mobila Android- och Apple-enheter. De kommer dock fortfarande att kunna läsa dessa meddelanden på persondatorer (via webbläsare på datorn). Användare som redan har laddat ned programmet fortsätter att kunna använda det.
  
## <a name="why-this-change-was-made"></a>Varför den här ändringen gjordes

Den nya versionen av OME kräver inte längre en mobilapp för att läsa skyddade e-postmeddelanden och bifogade filer. Kunder som använder de nya OME-funktionerna kan visa det skyddade meddelandet i Outlook mobila och icke-kunder kan visa skyddade meddelanden i en webbläsare.
  
Att kräva att användare laddar ned en mobilapp är ett annat hinder för kunderna att visa skyddade meddelanden. De nya Meddelandekryptering i Office 365 funktionerna ger en bättre mobil upplevelse.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Kan jag fortfarande använda den tidigare versionen av Meddelandekryptering i Office 365

Den tidigare versionen av Meddelandekryptering i Office 365 är för nuvarande version inte föråldrad, men vi har gjort betydande förbättringar av den nya versionen av Meddelandekryptering i Office 365, som gör det enklare att kryptera och rättighetsskydda känsliga data för alla och på alla enheter – inklusive möjligheten för användare att läsa skyddade meddelanden direkt i Outlook (stationär, mobil och webb). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Vad behöver jag göra för att förbereda mig inför ändringen

Om din organisation skickar krypterade bifogade filer till mottagare som kräver OME-visningsappen bör du uppdatera din dokumentation och utbildningsresurser.
  
Vi rekommenderar att du Exchange befintliga e-postflödesregler för att använda den aktuella versionen av OME så att din organisation kan dra nytta av de nya och förbättrade funktionerna. När du har ställt in de nya OME-funktionerna behöver inte mottagarna omE-visningsappen för att läsa krypterade meddelanden på mobila enheter.
  
Microsoft rekommenderar att du gör en plan för att flytta över till de nya OME-funktionerna så snart det är lämpligt för din organisation. Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md) Om du vill veta mer om hur de nya funktionerna fungerar först kan du läsa mer [i Meddelandekryptering i Office 365](ome.md).
  

