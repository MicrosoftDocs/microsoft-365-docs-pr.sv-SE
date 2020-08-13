---
title: Administrationscenter för Exchange i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Lär dig mer om webb hanterings gränssnittet i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652915"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Administrationscenter för Exchange i fristående EOP

Administrations centret för Exchange (UK) är en webbaserad hanterings konsol för fristående Exchange Online Protection (EOP).

Letar du efter Exchange Online-versionen av det här avsnittet? Se [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Öppna EOP i UK

Fristående EOP-kunder kan komma åt UK på följande sätt:

- **Från administrations centret för Microsoft 365**:

  1. Gå till <https://admin.microsoft.com> och klicka på **Visa alla**.

     ![Klicka på Visa alla i administrations centret för Microsoft 365](../../media/m365-center-show-all.png)

  2. I avsnittet **Administratörer** som visas klickar du på **alla administratörs Center**.

     ![Klicka på alla administratörs Center i administrations centret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. På sidan **alla administratörs Center** som visas klickar du på **Exchange Online Protection**.

- Gå direkt till `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Vanliga gränssnitts element i EOP

I det här avsnittet beskrivs de användar gränssnitts element som finns i UK.

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Fönstret funktion

Det här är den första navigerings nivån för de flesta uppgifter som du utför i UK. Fönstret funktion är ordnad efter funktions områden.

- **Mottagare**: här visas grupper och externa kontakter.

- **Behörigheter**: här hanterar du administratörs roller.

- **Hantering av efterlevnad**: här hittar du rapporten administratörs roll grupp och rapporten administratörs granskning.

- **Skydd**: här kan du hantera principer mot skadlig program vara, standard princip för anslutnings filter och DKIM.

  > [!NOTE]
  > Du bör hantera principer mot skadlig program vara och standard princip för anslutnings filter i säkerhets & efterlevnad. Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md) och [Konfigurera ANSLUTNINGS filtrering i EOP](configure-the-connection-filter-policy.md).

- **E-postflöde**: här hanterar du regler för e-postflöde (kallas även transport regler), godkända domäner och kopplingar, samt var du kan gå till spåra meddelanden.

- **Hybrid**: här kan du köra [hybrid konfigurations guiden](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)och där du kan installera [Exchange Online PowerShell-modulen](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).

### <a name="tabs"></a>TABB

Flikarna är den andra navigerings nivån. Varje funktions område innehåller olika flikar, som representerar en funktion.

### <a name="toolbar"></a>Raden

När du klickar på de flesta flikar ser du ett verktygsfält. Verktygsfältet innehåller ikoner som utför en viss åtgärd. I följande tabell beskrivs ikonerna och deras åtgärder.

****

|Ikonen|Namn|Fattning|
|---|---|---|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|Lägga till, ny|Använd den här ikonen för att skapa ett nytt objekt. Vissa av de här ikonerna har en associerad nedpilen som du kan klicka på för att visa ytterligare objekt som du kan skapa.|
|![Redigera-ikon](../../media/ITPro-EAC-EditIcon.gif)|Redigera|Använd den här ikonen om du vill redigera ett objekt.|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|Ta bort|Använd den här ikonen om du vill ta bort ett objekt. Vissa borttagnings ikoner är nedpilen som du kan klicka på för att visa fler alternativ.|
|![Sökikon](../../media/ITPro-EAC-.gif)|Sökmotor|Använd den här ikonen för att öppna en sökruta där du kan skriva Sök frasen för ett objekt som du vill hitta.|
|![Ikonen uppdatera](../../media/ITPro-EAC-RefreshIcon.gif)|Återställning|Använd den här ikonen för att uppdatera listvyn.|
|![Ikonen fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Fler alternativ|Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för den flikens objekt. I **mottagarna \> användare** klickar du till exempel på den här ikonen för att utföra en **Avancerad sökning**.|
|![Ikonen uppåtpil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikonen nedåtpil](../../media/ITPro-EAC-DownArrowIcon.gif)|UPPIL och NEDPIL|Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|Bort|Använd den här ikonen för att ta bort objekt från en lista.|
|

### <a name="list-view"></a>Listvy

När du väljer en flik visas en listvy. Den synliga gränsen för vyn UK visar ungefär 10 000 objekt. Dessutom är växling inkluderat för att du ska kunna göra en sida till resultatet.

### <a name="details-pane"></a>Informations fönstret

När du väljer ett objekt från listvyn visas information om objektet i informations fönstret. I vissa fall innehåller informations fönstret hanterings uppgifter.

### <a name="me-tile-and-help"></a>Panel och hjälp med mig

Med panelen **min** kan du logga ut från UK och logga in som en annan användare. I den **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) nedrullningsbara menyn hjälp hjälp ikon kan du göra följande:

- **Hjälp**: Klicka på ![ ikonen hjälp ](../../media/ITPro-EAC-HelpIcon.gif) för att visa onlinehjälpen.

- **Feedback**: lämna feedback.

- **Community**: Ställ en fråga för att hitta svar i Community-forumen.

- **Inaktivera hjälp bubbla**: hjälp bubblan visar kontextuell hjälp för fält när du skapar eller redigerar ett objekt. Du kan stänga av hjälp bubblan eller aktivera den om den har inaktiverats.

- **Visa kommando loggning**: ett nytt fönster öppnas med motsvarande PowerShell-kommandon baserat på vad du konfigurerade i UK.

## <a name="supported-browsers"></a>Webbläsare som stöds

Vi rekommenderar att du alltid använder de senaste webbläsarna, Office-klienterna och apparna för att få den bästa upplevelsen. Vi rekommenderar även att du installerar program varu uppdateringar när de blir tillgängliga. Mer information om webbläsare och system krav för tjänsten finns i [system krav för Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Språk som stöds

Följande språk stöds och är tillgängliga för UK i fristående EOP.

- Amhariska
- Arabiska
- Baskiska (baskiska)
- Bengali (Indien)
- Bulgarian
- Catalan
- Kinesiska (förenklad)
- Kinesiska (traditionell)
- Croatian
- Czech
- Danish
- Dutch
- English
- Estonian
- Filippinska (Filippinerna)
- Finnish
- French
- Galician
- German
- Greek
- Gujarati
- Hebrew
- Hindi
- Hungarian
- Isländska
- Indonesian
- Italian
- Japanese
- Kannada
- Kazakh
- Swahili
- Korean
- Latvian
- Lithuanian
- Malajiska (Brunei Darussalam)
- Malajiska (Malaysia)
- Malayalam
- Marathi
- Norska (bokmål)
- Norska (nynorsk)
- Odia
- Persiska
- Polish
- Portugisiska (Brasilien)
- Portugisiska (Portugal)
- Romanian
- Russian
- Serbiska (kyrillisk skrift, Serbien)
- Serbiska (latinsk)
- Slovak
- Slovenian
- Spanish
- Swedish
- Tamilska
- Telugu
- Thai
- Turkish
- Ukrainian
- Urdu
- Vietnamese
- Walesiska
