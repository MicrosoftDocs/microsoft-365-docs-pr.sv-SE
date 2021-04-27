---
title: Appar i Microsoft Hanterat skrivbord
description: Förklarar hur appar hanteras, inklusive hur du paketerar, distribuerar och ger stöd för dem.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028950"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Appar i Microsoft Hanterat skrivbord

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Appar i allmänhet

Microsoft inkluderar vissa viktiga appar tillsammans med licensen för Microsoft 365 E3 eller E5 som krävs för att delta i Microsoft Managed Desktop. Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder som måste slutföras.

Du kan också distribuera ytterligare appar som inte är Microsoft-appar till användarna för självbetjäning via företagsportalen eller en obligatorisk bakgrundsinstallation som använder Microsoft Intunes distributionsförlopp. 

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

Du har förmodligen andra appar som du behöver för verksamheten. De här apparna kan endast distribueras till Microsoft Managed Desktop-enheter med hjälp av Microsoft Intune-distributionsförlopp. Mer information om programdistribution finns i Distribuera program [till Microsoft Managed Desktop-enheter.](../get-started/deploy-apps.md)

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Förbereda egna program för inkludering i Microsoft Managed Desktop
Granska dina appar och kontrollera:

- Inga av apparna är förbjudna eller har begränsat beteende enligt beskrivningen i appkrav för [Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)
- Apparna måste vara klara för hantering av Microsoft Intune. Mer information om det här avsnittet finns i [Distribution av Windows 10-appar med Microsoft Intune och](/intune/apps-windows-10-app-deploy) Lägg till appar i Microsoft [Intune.](/intune/apps-add)
- Andra paketeringskrav som till exempel tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Managed Desktop](prerequisites.md).
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Managed Desktop](apps.md) (den här artikeln)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md)
