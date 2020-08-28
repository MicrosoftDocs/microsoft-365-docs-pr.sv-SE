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
ms.openlocfilehash: da5798b3412cb69580e5d9adc582f0ca4add1e3e
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289597"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Appar på Microsoft Hanterat skrivbord

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Vanligt vis appar

Microsoft inkluderar vissa viktiga appar tillsammans med Microsoft 365 E3-eller E5-licensen som behövs för att delta på Microsoft Managed Desktop. Men även om vi tillhandahåller dessa appar har du fortfarande vissa skyldigheter och åtgärder att slutföra.

Du kan också distribuera ytterligare icke-Microsoft-appar till dina användare själv-tjänst via företags portalen eller en nödvändig bakgrunds installation med hjälp av Microsoft Intunes drift sättning. Om du har expert isen kan du migrera de program du behöver själv; Du kan också använda MCS (Microsoft Consulting Services) eller icke-Microsoft-leverantörer för att hjälpa dig med ett paket för paketering och migrering. Mer information om hur du arbetar med MCS finns i [arbeta med Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Appar som tillhandahålls av Microsoft

Inkluderat med din Microsoft-hanterade Skriv bords licens är 64-bitars versioner av programmen i Microsoft 365-apparna för Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote). Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men du kan begära att de ska läggas till. Mer information om de här apparna finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Vad Microsoft gör för att stödja de program vi tillhandahåller

Microsoft tillhandahåller fullständig service för distribution, uppdatering och support för de medföljande Microsoft 365-apparna för företags program. Klicka-och-kör-versioner av Microsoft Project och Visio ingår *inte* som standard, men Microsoft Managed Desktop tillhandahåller distributions grupper som gör att IT-administratören kan hantera licenser och distribuera dessa program på lämpligt sätt för din organisation. Microsoft kommer att stödja användare av dessa program via stöd kanaler i Microsoft Managed Desktop support.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Det här behöver du för att stödja de program vi tillhandahåller

Det finns fortfarande vissa saker du måste göra med de här apparna:

- **Tilldela licenser** – du ansvarar för att erhålla och tilldela lämpliga licenser till användare för Microsoft 365-appar för företag.
- **Lägga till användare i säkerhets grupper** – om du använder Microsoft Project eller Visio måste din IT-administratör lägga till dessa användare i distributions grupperna. IT-administratörer ansvarar också för att återta licenser från dessa användare om de lämnar företaget.
- **Distribuera Microsoft 365-tillägg** – om du behöver några tillägg för någon av Microsoft 365-apparna för företags program kan du använda dem centralt som alla andra Windows 32-program. 

## <a name="apps-you-provide"></a>Program du tillhandahåller

Självklart är det troligt att du har ett antal andra program som du behöver för ditt företag. Dessa kan bara distribueras till Microsoft Managed Station ära datorer med hjälp av Microsoft Intunes drift sättning. Om appen behöver den kan du ha dem paketerade av en leverantör (som kan vara en leverantör eller Microsoft Consulting Services), eller om du har det kan du paketera dem själv. Sedan lägger du till dessa paket till Microsoft Managed Desktop Portal och tilldelar dem till Azure Active Directory-grupper för att utlösa distributionen. 

Om du för närvarande distribuerar dina program med hjälp av Microsoft Endpoint Configuration Manager kan Microsoft Managed Desktop förse dig med en fråga för att utvärdera dina appar och upptäcka vilka som är klara att migreras till Microsoft Intune och vilka som kan behöva justeras.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Förbereda dina egna appar för inkludering på Microsoft Managed Desktop
Granska dina appar, kontrol lera:

- Inga av programmen är förbjudna eller har begränsat beteende, enligt beskrivningen i [Microsofts hanterade program krav](https://aka.ms/app-req).
- Program måste vara klara för hantering av Microsoft Intune. Mer information om detta finns i [Windows 10-programdistribution med Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) och [Lägg till program i Microsoft Intune](https://docs.microsoft.com/intune/apps-add).
- Andra krav för förpackning som att tillhandahålla licens nycklar, avtal med licens villkor och för att konfigurera server anslutningar.

### <a name="decide-how-to-package-apps"></a>Bestämma hur du ska paketera appar

Vissa oberoende program varu leverantörer kan kräva att dina appar paketeras innan de distribueras centralt. "Paketera" betyder att appens installations program är konfigurerat med inställningar som licens nycklar, fjärrplatser eller Skriv bords gen vägar så att programmet kan installeras i bakgrunden.

Det finns tre sätt att få dina appar paketerade: 


- Du kan paketera appar själv
- Du kan arbeta med en leverantör som inte tillhör Microsoft
- Du kan samar beta med MCS för att paketera dina appar. Arbeta med ditt Microsoft-konto. Mer information finns i [arbeta med Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Distribuera appar

Oavsett vilken metod du använder för att få appar paketerade, när de är klara kan du följa stegen i [distribuera appar till Microsoft Managed Station ära datorer](../get-started/deploy-apps.md).


