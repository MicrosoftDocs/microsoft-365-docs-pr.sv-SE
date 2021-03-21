---
title: Appar på Microsoft Hanterat skrivbord
description: Förklarar hur appar hanteras, inklusive hur du paketerar, distribuerar och ger stöd för dem.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ea0990e5f30aa45ec48bb2e6a7c957c187c74ebb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922950"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Appar på Microsoft Hanterat skrivbord

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Appar i allmänhet

Microsoft inkluderar vissa viktiga appar tillsammans med licensen för Microsoft 365 E3 eller E5 som krävs för att delta i Microsoft Managed Desktop. Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder som måste slutföras.

Du kan också distribuera ytterligare appar som inte är Microsoft-appar till användarna för självbetjäning via företagsportalen eller en obligatorisk bakgrundsinstallation som använder Microsoft Intunes distributionsförlopp. Om du har de kunskaper du behöver kan du migrera de appar du behöver själv. Alternativt kan Microsoft Consulting Services (MCS) eller andra leverantörer än Microsoft hjälpa dig med ett paketerings- och migreringsprojekt. Mer information om hur du arbetar med MCS finns [i Arbeta med Microsoft Consulting Services.](apps-MCS.md)


## <a name="apps-provided-by-microsoft"></a>Appar som tillhandahålls av Microsoft

Som en del av din Microsoft Managed Desktop-licens ingår 64-bitarsversioner av apparna i Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote.) Klicka-och-kör-versioner av Microsoft Project och Visio *ingår* inte som standard, men du kan begära att de läggs till. Mer information om apparna finns i Installera [Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Vad Microsoft gör för att stödja de appar vi tillhandahåller

Microsoft kommer att tillhandahålla fullständiga tjänster för distribution, uppdatering och support för de Microsoft 365-appar för företag som ingår. Klicka-och-kör-versioner av Microsoft  Project och Visio ingår inte som standard, men Microsoft Managed Desktop tillhandahåller distributionsgrupper där IT-administratören kan hantera licenser och distribuera programmen på rätt sätt för din organisation. Microsoft ger support för användare av de här programmen via supportkanalerna för Microsoft Managed Desktop.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Vad du behöver göra för att stödja de appar vi tillhandahåller

Det finns fortfarande vissa saker du behöver göra med de här apparna:

- **Tilldela licenser** – Du är ansvarig för att skaffa och tilldela lämpliga licenser till användare för Microsoft 365 Apps för företag.
- **Lägga till användare i säkerhetsgrupper** – Om du använder Microsoft Project eller Visio måste IT-administratören lägga till de användarna i lämpliga distributionsgrupper. IT-administratörer är också ansvariga för att återta licenser från dessa användare om de lämnar företaget.
- **Distribuera Microsoft 365-tillägg** – Om du behöver tillägg för något av Microsoft 365-programmen för företag kan du distribuera dem centralt precis som andra Windows 32-program. 

## <a name="apps-you-provide"></a>Appar som du tillhandahåller

Du har förmodligen andra appar som du behöver för verksamheten. De här apparna kan endast distribueras till Microsoft Managed Desktop-enheter med hjälp av Microsoft Intune-distributionsförlopp. Om programmet behöver det kan de paketeras av en leverantör (som kan vara en leverantör som inte är en Microsoft-leverantör eller Microsoft Consulting Services (MCS)) eller, om du har möjlighet, kan du paketera dem själv. Sedan lägger du till paketen i Microsoft Managed Desktop-portalen och tilldelar dem till Azure Active Directory-grupper för att starta distributionen. 

Om du för närvarande distribuerar dina appar med hjälp av Microsoft Endpoint Configuration Manager, kan Microsoft Managed Desktop ge dig en fråga för att bedöma dina appar och identifiera vilka som är redo att migreras till Microsoft Intune och vilka som kan behöva justeras.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Förbereda egna program för inkludering i Microsoft Managed Desktop
Granska dina appar och kontrollera:

- Inga av apparna är förbjudna eller har begränsat beteende enligt beskrivningen i appkrav för [Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)
- Apparna måste vara klara för hantering av Microsoft Intune. Mer information om det här avsnittet finns i [Distribution av Windows 10-appar med Microsoft Intune och](/intune/apps-windows-10-app-deploy) Lägg till appar i Microsoft [Intune.](/intune/apps-add)
- Andra paketeringskrav som till exempel tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.

### <a name="decide-how-to-package-apps"></a>Bestäm hur du ska paketera appar

Vissa oberoende programvaruutgivare kan kräva att apparna paketeras innan de distribueras centralt. "Paketering" innebär att programmets installationsprogram är konfigurerat med inställningar som licensnycklar, fjärrserverplatser eller skrivbordsgenvägar så att programmet kan installeras i bakgrunden.

Det finns tre alternativ för att paketera dina appar: 


- Du kan paketera appar själv
- Du kan arbeta med en leverantör som inte är en Microsoft-leverantör
- Du kan kommunicera med MCS för att paketera dina appar. Arbeta med din Microsoft-kontorepresentant. Mer information finns i [Arbeta med Microsoft Consulting Services.](apps-MCS.md)



## <a name="deploying-apps"></a>Distribuera program

Oavsett vilken metod du använder för att paketera appar är du redo att följa stegen i Distribuera appar till [Microsoft Managed Desktop-enheter.](../get-started/deploy-apps.md)