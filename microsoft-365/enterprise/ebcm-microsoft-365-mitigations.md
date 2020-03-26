---
title: Begränsningar för hantering av affärskontinuitet i Microsoft 365
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Några exempel på begränsningar för händelsescenarier i Microsoft 365-tjänsten.
ms.openlocfilehash: ea9804d4f22a11ea9ffcda9d9939d70574c2e87e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806484"
---
# <a name="service-incident-mitigation-strategies"></a>Strategier för att begränsa händelser i tjänsten

Här är några strategier och scenarier som visar hur du kan minska effekten på din affärsprocess av en händelse i Microsoft 365-tjänsten.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>Scenarier med tjänstehändelser och potentiella begränsningar

|Microsoft 365-beroende|potentiella begränsningar|
|---------|---------|
|Ärendehanteringssystem är beroende av Exchange Online för att engagera jourtekniker och händelsehanterare.|Kontrollera att ditt händelsehanteringssystem har stöd för kommunikation via flera kanaler, t. ex. parallell e-post, telefonsamtal och SMS-meddelande, och anropa trädhierarkier om den primära jourenheten inte aktiveras så att systemet automatiskt aktiverar reservkanalen. Se också till att varje meddelande innehåller reservmetoder för kontakt, så att det går enkelt att hitta andra kommunikationsmetoder. Alternativa kommunikationsmetoder, t. ex. Yammer, kan användas för att samarbeta i nödfall om tjänsten för händelsehantering inte är tillgänglig.|
|Microsoft Teams används för att lagra filer som används via klienten.|Teams lagrar filer som laddats upp till klienten i ett SharePoint Online-dokumentbibliotek. Filerna är fortfarande tillgängliga via SharePoint Online. Utbilda användarna om var filerna finns i SharePoint Online.|
|Konferenssamtal med Microsoft Teams bygger på allmän kommunikation och sortering av posthantering.|Upprätta en reservlösning för konferenser med en extern leverantör.|
|VoIP-telefoner används som sekundär kommunikationsmetod.|Implementera ej VoIP-telefoner som kan användas för PSTN-samtal, framför allt för nätverks- och tjänståtgärder under händelser. Lägg till en anställds mobiltelefonnummer i företagets katalog för att tillåta att kritisk personal kontaktas via det mobila nätverket.|
|OneDrive för företag används för fillagring och användarproduktivitet. [Filer på begäran](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234) konfigureras för att frigöra utrymme på lokala användarenheter.|Med grupprinciper för OneDrive-synkronisering kan administratörer begära att visst innehåll ska synkroniseras lokalt eller frigöra utrymme vid behov. Om du vill minska risken för att dokument blir otillgängliga kan du konfigurera den här principen för lokal synkronisering av viktiga dokument. Träna användarna att manuellt använda inställningen ”Behåll alltid på den här enheten” för viktiga dokument.|
|För kommunikation av störningar i verksamheten till kunder och leverantörer används Exchange Online.|Offentliga sociala nätverk från tredje part kan användas som ett alternativt sätt att masskommunicera.

## <a name="leveraging-mobile-app-access"></a>Utnyttja tillgång till mobilappar

Den ökade mobilanvändningen har genererat nya sätt att hålla kontakten, och Microsoft 365-mobilappar kan bli en viktig del av din återhämtningsstrategi. Eftersom de ansluter till molntjänster via nätverket för mobilleverantörer är de inte beroende av organisationens nätverksinfrastruktur.

Vi använder Outlook som exempel. Användare kan ansluta till Exchange Online-postlådor via olika nätverksprotokoll (https eller MAPI) beroende på vilket e-postprogram som används. Om det finns en tjänsthändelse som innefattar något av protokollen, till exempel MAPI som datorklienten använder, kan användarna fortfarande komma åt sina postlådor via Outlook-mobilappen eller Outlook på webben.
  
Om du bestämmer dig för låta användarna ansluta till Microsoft 365-tjänster via sina mobila enheter kan du använda Microsoft Intune för att konfigurera och hantera enheterna på ett säkert sätt. När användarkontona och -enheterna har registrerats i din mobilhanteringslösning ser du till att apparna har laddats ned och konfigurerats.
