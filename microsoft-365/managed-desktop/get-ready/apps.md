---
title: Appar på Microsoft Hanterat skrivbord
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bc7192cf82c825a13780567663695d96a760b3ef
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530109"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Appar på Microsoft Hanterat skrivbord

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Appar i allmänhet

Microsoft innehåller vissa viktiga appar tillsammans med microsoft 365 E3- eller E5-licensen som behövs för att delta i Microsoft Managed Desktop. Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder att slutföra.

Du kan också distribuera ytterligare appar som inte kommer från Microsoft till slutanvändarna för självbetjäning via företagsportalen eller en nödvändig bakgrundsinstallation, som alla använder Microsoft Intunes distributionspipeline. Om du har den expertis som du har den expertis du behöver själv. Alternativt hjälper Microsoft Consulting Services (MCS) eller leverantörer utanför Microsoft dig gärna med ett paketerings- och migreringsprojekt. Mer information om hur du arbetar med MCS finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Appar från Microsoft

Med din Microsoft Managed Desktop-licens ingår 64-bitarsversioner av apparna i Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote.) Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men du kan begära att de läggs till. Mer information om dessa appar finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Vad Microsoft gör för att stödja de appar vi tillhandahåller

Microsoft tillhandahåller full service för distribution, uppdatering och support för de inkluderade Microsoft 365 Apps för företagsappar. Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men Microsoft Managed Desktop tillhandahåller distributionsgrupper som gör det möjligt för IT-administratören att hantera licenser och distribuera dessa program på rätt sätt för din organisation. Microsoft stöder slutanvändare av dessa program via Microsoft Managed Desktop-supportkanalerna.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Vad du behöver göra för att stödja de appar vi tillhandahåller

Det finns fortfarande vissa saker du behöver göra med dessa appar:

- **Tilldela licenser** – Du ansvarar för att skaffa och tilldela lämpliga licenser till slutanvändare för Microsoft 365 Apps för företag.
- **Lägg till användare i säkerhetsgrupper** – Om du använder Microsoft Project eller Visio måste IT-administratören lägga till dessa användare i lämpliga distributionsgrupper. IT-administratörer är också ansvariga för att återkräva licenser från dessa användare om de lämnar företaget.
- **Distribuera Microsoft 365-tillägg** – Om du behöver tillägg för någon av Microsoft 365 Apps för företagsappar kan du distribuera dem centralt som alla andra Windows 32-appar. 

## <a name="apps-you-provide"></a>Appar som du tillhandahåller

Naturligtvis har du förmodligen ett antal andra appar som du behöver för din verksamhet. Dessa kan endast distribueras till Microsoft Hanterade stationära enheter med hjälp av Microsoft Intunes distributionspipeline. Om appen behöver det kan du få dem paketerade av en leverantör (som kan vara en icke-Microsoft-leverantör eller Microsoft Consulting Services (MCS)) eller om du har möjlighet, kan du paketera dem själv. Du lägger sedan till dessa paket i Microsoft Managed Desktop-portalen och tilldelar dem till Azure Active Directory-grupper för att utlösa distributionen. 

Om du för närvarande distribuerar dina appar med Hjälp av Microsoft Endpoint Configuration Manager kan Microsoft Managed Desktop ge dig en fråga för att bedöma dina appar och ta reda på vilka som är redo att migrera till Microsoft Intune och vilka som kan behöva justeras.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Förbereda egna appar för inkludering i Microsoft Managed Desktop
Granska dina appar och kontrollera:

- Ingen av apparna är förbjudna eller har begränsat beteende, enligt beskrivningen i [Microsoft Managed Desktop-appkrav](https://aka.ms/app-req).
- Appar måste vara klara för hantering av Microsoft Intune. Mer information om detta finns i [distributionen av Windows 10-appar med Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) och [Lägg till appar i Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Andra förpaketeringskrav, till exempel tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.

### <a name="decide-how-to-package-apps"></a>Bestäm hur du ska paketera appar

Vissa oberoende programvaruleverantörer kan kräva att dina appar är paketerade innan de distribueras centralt. "Förpackning" innebär att appens installationsprogram är konfigurerat med inställningar som licensnycklar, fjärrserverplatser eller genvägar till skrivbordet så att appen kan installeras i bakgrunden.

Det finns tre alternativ för att få dina appar paketerade: 


- Du kan paketera appar själv
- Du kan arbeta med en leverantör som inte kommer från Microsoft
- Du kan samarbeta med MCS för att paketera dina appar. Arbeta med din Microsoft-kontorepresentant. Mer information finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Distribuera appar

Oavsett vilken metod du använder för att paketera appar är du redo att följa stegen i [Distribuera appar till Microsoft Hanterade skrivbordsenheter](../get-started/deploy-apps.md)när du är klar.


