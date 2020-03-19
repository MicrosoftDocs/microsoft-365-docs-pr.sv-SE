---
title: Appar på Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: adb6423d5c014b5f02fc272f9653abebc14cf543
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42808589"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Appar på Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Appar i allmänhet

Microsoft innehåller vissa nyckelappar tillsammans med microsoft 365 E3- eller E5-licensen som krävs för att delta i Microsoft Managed Desktop. Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder att slutföra.

Du kan också distribuera ytterligare appar som inte kommer från Microsoft till slutanvändarna för självbetjäning via företagsportalen eller en nödvändig bakgrundsinstallation, alla med Hjälp av Microsoft Intunes distributionspipeline. Om du har den expertis en kan du migrera de appar du behöver själv. Alternativt hjälper Microsoft Consulting Services (MCS) eller leverantörer som inte kommer från Microsoft gärna dig med ett paketerings- och migreringsprojekt. Mer information om hur du arbetar med MCS finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Appar från Microsoft

Med licensen för Microsoft Managed Desktop finns 64-bitarsversioner av apparna i Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote.) Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men du kan begära att de läggs till. Mer information om dessa appar finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Vad Microsoft gör för att stödja de appar vi tillhandahåller

Microsoft tillhandahåller full service för distribution, uppdatering och support för de inkluderade Office 365 ProPlus-apparna. Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men Microsoft Managed Desktop tillhandahåller distributionsgrupper som gör det möjligt för IT-administratören att hantera licenser och distribuera dessa program på rätt sätt för din organisation. Microsoft kommer att stödja slutanvändare av dessa program via microsoft managed desktop-supportkanalerna.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Vad du behöver göra för att stödja de appar vi tillhandahåller

Det finns fortfarande vissa saker du behöver göra med dessa appar:

- **Tilldela licenser** – Du är ansvarig för att hämta och tilldela lämpliga licenser till slutanvändare för Office 365 ProPlus.
- **Lägg till användare i säkerhetsgrupper** – Om du använder Microsoft Project eller Visio måste IT-administratören lägga till dessa användare i lämpliga distributionsgrupper. IT-administratörer ansvarar också för att återkräva licenser från dessa användare om de lämnar företaget.
- **Distribuera Office 365-tillägg** – Om du behöver några tillägg för någon av Office 365 ProPlus-programmen distribuerar du dem centralt som alla andra Windows 32-appar. 

## <a name="apps-you-provide"></a>Appar som du tillhandahåller

Naturligtvis har du förmodligen ett antal andra appar du behöver för din verksamhet. Dessa kan bara distribueras till Microsoft Managed Desktop-enheter med hjälp av Microsoft Intunes distributionspipeline. Om appen behöver den kan du få dem paketerade av en leverantör (som kan vara en icke-Microsoft-leverantör eller Microsoft Consulting Services (MCS)) eller om du har medel, kan du paketera dem själv. Du lägger sedan till dessa paket i Microsoft Managed Desktop-portalen och tilldelar dem till Azure Active Directory-grupper för att utlösa distributionen. 

Om du för närvarande distribuerar dina appar med Hjälp av Microsoft Endpoint Configuration Manager kan Microsoft Managed Desktop ge dig en fråga för att bedöma dina appar och upptäcka vilka som är redo att migrera till Microsoft Intune och vilka som kan kräva vissa Justering.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Förbereda dina egna appar för att inkluderas i Microsoft Managed Desktop
Granska dina appar och kontrollera:

- Ingen av apparna är förbjuden eller har begränsat beteende, enligt beskrivningen i [Appkraven](https://aka.ms/app-req)för Microsoft Managed Desktop .
- Appar måste vara klara för hantering av Microsoft Intune. Mer information om detta finns i [Distributionav Windows 10-appar med Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) och [Lägg till appar i Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Andra krav för förpaketering, till exempel att tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.

### <a name="decide-how-to-package-apps"></a>Bestäm hur appar ska paketeras

Vissa oberoende programvaruleverantörer kan kräva att dina appar paketeras innan de distribueras centralt. "Förpackning" innebär att appens installationsprogram är konfigurerat med inställningar som licensnycklar, fjärrserverplatser eller skrivbordsgenvägar så att appen kan installeras i bakgrunden.

Det finns tre alternativ för att paketera dina appar: 


- Du kan paketera appar själv
- Du kan arbeta med en leverantör som inte kommer från Microsoft
- Du kan interagera med MCS för att paketera dina appar. Arbeta med din Microsoft-kontorepresentant. Mer information finns i [Arbeta med Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Distribuera appar

Oavsett vilken metod du använder för att få appar paketerade, när det är klart, är du redo att följa stegen i [Distribuera appar till Microsoft Managed Desktop-enheter](../get-started/deploy-apps.md).


