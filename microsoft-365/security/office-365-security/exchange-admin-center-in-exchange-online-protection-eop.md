---
title: Exchange administrationscenter i Exchange Online Protection
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
description: Administrationscentret för Exchange (EAC) är den webbaserade hanteringskonsolen för Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 3b5fb014e56a9928d58abffd5e4c96e1eef463ad
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808613"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange administrationscenter i Exchange Online Protection

Administrationscentret för Exchange (EAC) är den webbaserade hanteringskonsolen för Microsoft Exchange Online Protection (EOP).

Letar du efter Exchange Server-versionen av det här avsnittet? Se [Administrationscenter för Exchange i Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).

Letar du efter Exchange Online-versionen av det här avsnittet? Se [Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="accessing-the-eac"></a>Tillgång till EAC

I de flesta fall kommer EOP-kunder åt EAC via administrationscentret för Microsoft 365. Du hittar en länk till EOP i den nedrullningsbara menyn i **panelen Admin,** som ligger bredvid panelen **Jag.** Klicka på panelen **Admin** och välj **Exchange Online Protection** på den nedrullningsbara menyn som ska tas till EAC.

Du kan också komma åt inloggningssidan för EAC direkt via följande webbadress: `https://admin.protection.outlook.com/ecp/<companydomain>`. Till exempel `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. När du har angett dina användaruppgifter kommer du att tas direkt in i EAC.

## <a name="common-user-interface-elements-in-the-eac"></a>Vanliga användargränssnittselement i EAC

I det här avsnittet beskrivs de element i användargränssnittet som finns i EAC.

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Funktionsfönstret

Detta är den första navigeringsnivån för de flesta av de uppgifter du utför i EAC. Funktionsfönstret är organiserat efter funktionsområden.

1. **Mottagare**: Här visar du interna användare och externa kontakter.

2. **Behörigheter**: Här hanterar du administratörsroller.

3. **Efterlevnadshantering**: Här hittar du granskningsloggar och rapporter, till exempel rollen administratörsgruppsrapport.

4. **Skydd**: Här hanterar du skydd mot skadlig kod och skräppost för din organisation samt hanterar meddelanden i karantän.

5. **E-postflöde:** Här hanterar du regler, accepterade domäner och kopplingar samt vart du ska gå för att utföra meddelandespårning.

### <a name="tabs"></a>Flikar

Flikarna är din andra navigeringsnivå. Vart och ett av funktionsområdena innehåller olika flikar, som var och en representerar en funktion.

### <a name="toolbar"></a>Verktygsfältet

När du klickar på de flesta flikar visas ett verktygsfält. Verktygsfältet har ikoner som utför en viss åtgärd. I följande tabell beskrivs ikonerna och deras handlingar.

|**Ikonen**|**Namn**|**Åtgärder**|
|:-----|:-----|:-----|
|![Lägg till ikon](../../media/ITPro-EAC-AddIcon.gif)|Lägg till, Ny|Använd den här ikonen om du vill skapa ett nytt objekt. Vissa av dessa ikoner har en associerad nedpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.|
|![Redigera ikon](../../media/ITPro-EAC-EditIcon.gif)|Redigera|Använd den här ikonen om du vill redigera ett objekt.|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|Ta bort|Använd den här ikonen om du vill ta bort ett objekt. Vissa borttagningsikoner har en nedpil som du kan klicka på för att visa ytterligare alternativ.|
|![Sökikon](../../media/ITPro-EAC-.gif)|Sök|Använd den här ikonen om du vill öppna en sökruta där du kan skriva sökfrasen efter ett objekt som du vill hitta.|
|![Ikon för uppdatering](../../media/ITPro-EAC-RefreshIcon.gif)|Uppdatera|Använd den här ikonen för att uppdatera listvyn.|
|![Ikon för fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Fler alternativ|Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för den flikens objekt. I ** \> Mottagare användare** klickar på den här ikonen visar alternativet att utföra en **avancerad sökning**.|
|![Ikon för upppil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikon för nedpil](../../media/ITPro-EAC-DownArrowIcon.gif)|Upppil och nedåtpil|Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|Ta bort|Använd den här ikonen om du vill ta bort objekt från en lista.|

### <a name="list-view"></a>Listvy

När du väljer en flik visas en listvy i de flesta fall. Den synliga gränsen med EAC-listvyn är cirka 10 000 objekt. Dessutom inkluderas växling så att du kan bläddra till resultat.

### <a name="details-pane"></a>Informationsfönstret

När du markerar ett objekt i listvyn visas information om objektet i informationsfönstret. I vissa fall innehåller informationsfönstret hanteringsuppgifter.

### <a name="me-tile-and-help"></a>Jag kakel och hjälp

Med panelen **Me** kan du logga ut eac och logga in som en annan användare. På **Help**den nedrullningsbara hjälpikonen](../../media/ITPro-EAC-HelpIcon.gif) kan du utföra följande åtgärder:![

1. **Hjälp**: ![Klicka](../../media/ITPro-EAC-HelpIcon.gif) på Hjälpikonen om du vill visa hjälpinnehållet online.

2. **Inaktivera hjälpbubbla:** Hjälpbubblan visar kontextuell hjälp för fält när du skapar eller redigerar ett objekt. Du kan stänga av hjälpbubblan eller aktivera den om den har inaktiverats.

3. **Upphovsrätt**: Klicka på denna länk för att läsa upphovsrättsmeddelandet för Exchange Online Protection.

4. **Sekretess:** Klicka för att läsa sekretesspolicyn för Exchange Online Protection.

## <a name="supported-browsers"></a>Webbläsare som stöds

För bästa upplevelse med EAC rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och apparna. Vi rekommenderar också att du installerar programuppdateringar när de blir tillgängliga. Mer information om webbläsare och systemkrav som stöds för tjänsten finns i [Systemkrav för Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages-in-eop"></a>Språk som stöds i EOP

Följande språk stöds och är tillgängliga för Exchange Online Protection.

- Amhariska

- Arabiska

- Baskiska (baskiska)

- Bengali (Indien)

- Bulgariska

- Katalanska

- Kinesiska (förenklad)

- Kinesiska (traditionell)

- Kroatiska

- Tjeckiska

- Danska

- Nederländska

- Nederländska

- Engelska

- Estniska

- Filippinska (Filippinerna)

- Finska

- Franska

- Galiciska

- Tyska

- Grekiska

- Gujarati

- Hebreiska

- Hindi

- Ungerska

- Isländska

- Indonesiska

- Italienska

- Japanska

- Kannada

- Kazakiska

- Kiswahili

- Koreanska

- Lettiska

- Litauiska

- Malajiska (Brunei Darussalam)

- Malajiska (Malaysia)

- Malayalam

- Marathi

- Norska (Bokmål)

- Norska (nynorsk)

- Oriya

- Persiska

- Polska

- Portugisiska (Brasilien)

- Portugisiska (Portugal)

- Rumänska

- Ryska

- Serbiska (kyrilliska, Serbien)

- Serbiska (latin)

- Slovakiska

- Slovenska

- Spanska

- Svenska

- Tamilska

- Telugu

- Thai

- Turkiska

- Ukrainska

- Urdu

- Vietnamesiska

- Walesiska


