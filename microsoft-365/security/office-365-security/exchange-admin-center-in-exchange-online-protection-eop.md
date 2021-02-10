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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Läs mer om webbhanteringsgränssnittet i fristående Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81af6c64d2ec3204d0c9d46888bbfe21335955bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166225"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Administrationscenter för Exchange i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](https://go.microsoft.com/fwlink/?linkid=2148611)

Administrationscentret för Exchange (EAC) är en webbaserad hanteringskonsol för fristående Exchange Online Protection (EOP).

Letar du efter Exchange Online-versionen av det här avsnittet? Se [administrationscentret för Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)

## <a name="open-the-eac-in-eop"></a>Öppna EAC i EOP

Fristående EOP-kunder kan komma åt EAC på följande sätt:

- **Från administrationscentret för Microsoft 365:**

  1. Gå till <https://admin.microsoft.com> och klicka på Visa **alla.**

     ![Klicka på Visa alla i administrationscentret för Microsoft 365](../../media/m365-center-show-all.png)

  2. Klicka på **Alla administrationscenter** i avsnittet **Administrationscenter som visas.**

     ![Klicka på Alla administrationscenter i administrationscentret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. Klicka på Exchange Online **Protection** på sidan Alla **administrationscenter som visas.**

- Gå direkt `https://admin.protection.outlook.com/ecp/` till.

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Vanliga element i användargränssnittet i EAC i EOP

I det här avsnittet beskrivs de användargränssnittselement som finns i EAC.

![Administrationscentret för Exchange i Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Funktionsfönstret

Det här är den första navigeringsnivån för de flesta uppgifter som du utför i EAC. Funktionsfönstret är ordnat efter funktionsområden.

- **Mottagare:** Det är här du visar grupper och externa kontakter.

- **Behörigheter:** Här hanterar du administratörsroller.

- **Efterlevnadshantering:** Det är här du hittar rapporten över administratörsrollgrupper och granskningsloggrapporten för administratörer.

- **Skydd:** Det är här du kan hantera principer för skydd mot skadlig programvara, standardprincipen för anslutningsfilter och DKIM.

  > [!NOTE]
  > Du bör hantera principer för skadlig programvara och standardprincipen för anslutningsfilter i Säkerhets- & Efterlevnadscenter. Mer information finns i Konfigurera [principer för skadlig programvara i EOP och](configure-anti-malware-policies.md) Konfigurera [anslutningsfiltrering i EOP.](configure-the-connection-filter-policy.md)

- E-postflöde: Det är här du hanterar e-postflödesregler (kallas även transportregler), godkända domäner och kopplingar samt var du kan köra meddelandespårning.

- **Hybrid:** Det är här du kan köra [hybridkonfigurationsguiden](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)och där kan du installera [Exchange Online PowerShell-modulen.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)

### <a name="tabs"></a>Flikar

Flikarna är den andra nivån av navigering. Var och en av funktionsområdena innehåller olika flikar, som var och en representerar en funktion.

### <a name="toolbar"></a>Verktygsfält

När du klickar på de flesta flikar visas ett verktygsfält. Verktygsfältet innehåller ikoner som utför en viss åtgärd. I följande tabell beskrivs ikonerna och deras åtgärder.

****

|Ikon|Namn|Åtgärd|
|---|---|---|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|Lägg till, Ny|Använd den här ikonen för att skapa ett nytt objekt. Vissa av dessa ikoner har en associerad nedpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.|
|![Redigeringsikon](../../media/ITPro-EAC-EditIcon.gif)|Redigera|Använd den här ikonen för att redigera ett objekt.|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|Ta bort|Använd den här ikonen för att ta bort ett objekt. Vissa borttagningsikoner har en nedåtpil som du kan klicka på för att visa ytterligare alternativ.|
|![Sökikon](../../media/ITPro-EAC-.gif)|Sök|Använd den här ikonen för att öppna en sökruta där du kan skriva sökfrasen för ett objekt som du vill hitta.|
|![Uppdatera-ikon](../../media/ITPro-EAC-RefreshIcon.gif)|Återställning|Använd den här ikonen för att uppdatera listvyn.|
|![Ikonen Fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Fler alternativ|Använd den här ikonen för att visa fler åtgärder som du kan utföra för objekten på den fliken. Om du till exempel **klickar \> på ikonen Mottagare** visas ett alternativ för avancerad **sökning.**|
|![Ikon med uppil](../../media/ITPro-EAC-UpArrowIcon.gif)![Nedåtpilikon](../../media/ITPro-EAC-DownArrowIcon.gif)|Uppil och nedpil|Använd de här ikonerna för att flytta ett objekts prioritet uppåt eller nedåt.|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|Ta bort|Använd den här ikonen för att ta bort objekt från en lista.|
|

### <a name="list-view"></a>Listvy

När du väljer en flik visas i de flesta fall en listvy. Visningsgränsen med EAC-listvyn är cirka 10 000 objekt. Dessutom ingår sidindening så att du kan visa sidresultat.

### <a name="details-pane"></a>Informationsfönstret

När du väljer ett objekt i listvyn visas information om objektet i informationsfönstret. I vissa fall innehåller informationsfönstret hanteringsuppgifter.

### <a name="me-tile-and-help"></a>Panelen Jag och Hjälp

På **panelen** Jag kan du logga ut från EAC och logga in som en annan användare. Gör **följande** ![ på den ](../../media/ITPro-EAC-HelpIcon.gif) nedrullningsmenyn i hjälpikonen:

- **Hjälp:** Klicka ![ på ikonen Hjälp om du vill visa ](../../media/ITPro-EAC-HelpIcon.gif) onlinehjälpens innehåll.
- **Feedback:** Lämna feedback.
- **Community:** Ställa en fråga för att få svar i community-forumen.
- **Inaktivera hjälpbubblan:** Hjälpbubblan visar sammanhangsberoende hjälp för fält när du skapar eller redigerar ett objekt. Du kan stänga av hjälpbubblan eller aktivera den om den har inaktiverats.
- **Visa kommandologgning:** Ett nytt fönster öppnas som visar motsvarande PowerShell-kommandon baserat på vad du har konfigurerat i EAC.

## <a name="supported-browsers"></a>Webbläsare som stöds

För att EAC ska bli så bra som möjligt rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och programmen. Vi rekommenderar även att du installerar programuppdateringar när de blir tillgängliga. Mer information om vilka webbläsare och systemkrav som stöds för tjänsten finns [i Systemkrav för Office.](https://products.office.com/office-system-requirements)

## <a name="supported-languages"></a>Språk som stöds

Följande språk stöds och är tillgängliga för EAC i fristående EOP.

- Amhariska
- Arabiska
- Baskiska (Baskien)
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
- Kiswahili
- Korean
- Latvian
- Lithuanian
- Malajiska (Brunei)
- Malajiska (Malaysia)
- Malayalam
- Marathi
- Norska (bokmål)
- Norska (nynorsk)
- Oriya
- Persiska
- Polish
- Portugisiska (Brasilien)
- Portugisiska (Portugal)
- Romanian
- Russian
- Serbiska (kyrillisk språk, Serbien)
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
