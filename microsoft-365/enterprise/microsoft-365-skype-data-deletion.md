---
title: Office 365 Skype för Business Data borttagning
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln hittar du en förklaring till data borttagning i Skype för företag, inklusive vilka typer av innehåll som inte behålls.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf317f2ecd3d547ae8601553a34fb43fb4b5bd9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694749"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Data borttagning för Skype för företag i Office 365

Med Skype för företag kan du arkivera peer-to-peer-snabb meddelanden, direkt meddelanden och innehålls överförings aktiviteter i möten. Arkiverings funktionen kräver Exchange och styrs av användarens Exchange-post låda-attribut, som arkiverar både e-post och Skype för företag.

All arkivering i Skype för företag betraktas som "arkivering på användar nivå" eftersom du aktiverar eller inaktiverar den för en eller flera specifika användare eller grupper av användare genom att skapa, konfigurera och tillämpa en princip för arkivering av användar nivå för dessa användare. Det finns ingen direkt kontroll över inställningar för arkivering i administrations centret för Skype för företag.

Följande typer av innehåll arkiveras inte i Skype för företag:

- Fil överföringar mellan peer-to-peer
- Ljud/video för peer-to-peer snabb meddelanden och konferenser
- Program delning för peer-to-peer snabb meddelanden och konferenser
- Konferens anteckningar 

## <a name="meeting-content-retention"></a>Bevarande av mötes innehåll

Kunder som använder Skype för företag kan ladda upp innehåll till ett Skype för företag-möte som bilagor, till exempel PowerPoint-presentationer, OneNote-filer och andra filer. Bevarande perioden för innehåll som har laddats upp till ett möte ser ut så här:

- **Ett möte med en gång** – innehållet bevaras i 15 dagar från och med den sista personen som lämnar mötet.
- **Återkommande möte** – innehållet behålls i 15 dagar efter att den sista personen har lämnat den sista sessionen av mötet. Timern för kvarhållande återställer om någon ansluter till samma mötesinbjudan inom 15 dagar. Anta till exempel att ett Skype för företag-möte ska inträffa varje vecka i ett år och en fil laddas upp till mötet under den första instansen. Om minst en person ansluter till mötesinbjudan varje vecka bevaras filen i Skype för företag – Online-servrar för hela året plus 15 dagar efter att den sista personen har lämnat det sista mötet i serien.
- **Möte nu** – innehållet behålls i 8 timmar efter mötets slut tid.

> [!NOTE]
> Om en användare inte är licensierad eller inaktive rad (till exempel om **msRTCSIP-UserEnabled** är inställt på *false*) och sedan återkallas eller återaktiveras, kommer Mötes innehåll inte att bevaras.

## <a name="meeting-expiration"></a>Mötet upphör

Användare kan komma åt ett visst möte efter att mötet har avslut ATS, beroende på följande tids perioder:

- **Ett möte med en gång** -mötet upphör att gälla 14 dagar efter den schemalagda mötets slut tid.
- **Återkommande möte med slutdatum** -mötet upphör att gälla 14 dagar efter den schemalagda slut tiden för det senaste Mötes tillfället.
- Möte **nu slutar svara** efter 8 timmar.

## <a name="whiteboard-collaboration"></a>Whiteboard-samarbete

Anteckningar som gjorts på whiteboardtavlor visas av alla deltagare. När du sparar en whiteboard sparas whiteboard och alla anteckningar på en Skype för företag-Server, och den bevaras på servern enligt de principer för giltighets datum som anges av administratören.

## <a name="audio-test-service"></a>Ljud test tjänst

Ett kort (cirka 5 sekunder) exempel på din röst spelas in under samtalet. Röst provet används för att kontrol lera och/eller verifiera ljud kvaliteten på ditt Skype för företag-samtal baserat på inspelningens kvalitet. När ljud test tjänstens samtal är slut raderas röst provet.

## <a name="persistent-group-chat"></a>Beständig gruppchatt

I beständiga gruppchatt sparas innehållet i gruppchatt-konversationer. Om den är aktive rad kan administratören kontrol lera kvarhållningsperioden, den server där informationen lagras, om gruppchattens historik är arkiverad efter efterlevnad eller andra ändamål och hantera/ändra alla egenskaper i ett rum. Användare med olika roller har åtkomst till beständiga data på följande sätt:

- Administratörer kan ta bort gammalt innehåll (till exempel innehåll som har publicerats före ett visst datum) från ett chattrum för att hålla databasens storlek avsevärt. Eller så kan de ta bort eller ersätta meddelanden som är olämpliga för ett visst chattrum (eller som ansågs olämpliga).
- Slutanvändare, inklusive meddelande författare, kan inte ta bort innehåll från ett chattrum.
- Chattrum kan inaktivera rum men inte ta bort rum. Endast administratörer kan ta bort ett chattrum när det har skapats.