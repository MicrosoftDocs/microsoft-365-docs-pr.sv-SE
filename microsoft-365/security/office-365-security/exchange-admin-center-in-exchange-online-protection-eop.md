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
description: Lär dig mer om webbhanteringsgränssnittet i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 378754f2565604236f7ac33e471d1f991238d304
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209742"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Administrationscenter för Exchange i fristående EOP

Exchange admin center (EAC) är en webbaserad hanteringskonsol för fristående Exchange Online Protection (EOP).

Letar du efter Exchange Online-versionen av det här avsnittet? Se [Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Öppna EAC i EOP

Fristående EOP-kunder kan komma åt EAC med hjälp av följande metoder:

- **Från Microsoft 365 admin center:**

  1. Gå till <https://admin.microsoft.com> och klicka på Visa **alla**.

     ![Klicka på Visa alla i administrationscentret för Microsoft 365](../../media/m365-center-show-all.png)

  2. Klicka på Alla **administrationscenter i** avsnittet **Administrationscenter**som visas.

     ![Klicka på Alla administrationscenter i administrationscentret för Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. Klicka på **Exchange Online Protection**på sidan Alla **administrationscenter** som visas .

- Gå direkt till `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Gemensamma element för användargränssnitt i EAC i EOP

I det här avsnittet beskrivs de användargränssnittselement som finns i EAC.

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Funktionsfönstret

Detta är den första navigeringsnivån för de flesta av de uppgifter som du utför i EAC. Funktionsfönstret är ordnat efter funktionsområden.

- **Mottagare**: Här ska du visa grupper och externa kontakter.

- **Behörigheter**: Här hanterar du administratörsroller.

- **Efterlevnadshantering**: Här hittar du rapporten administratörsrollgrupp och rapporten administratörsgranskningslogg.

- **Skydd**: Här kan du hantera principer mot skadlig kod, standardprincipen för anslutningsfilter och DKIM.

  > [!NOTE]
  > Du bör hantera principer mot skadlig kod och standardprincipen för anslutningsfilter i Security & Compliance Center. Mer information finns [i Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md) och Konfigurera [anslutningsfiltrering i EOP](configure-the-connection-filter-policy.md).

- **E-postflöde:** Här hanterar du regler för e-postflöde (kallas även transportregler), accepterade domäner och kopplingar samt var du kan gå för att köra meddelandespårning.

- **Hybrid:** Här kan du köra [hybridkonfigurationsguiden](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)och där du kan installera [Exchange Online PowerShell-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell).

### <a name="tabs"></a>Flikar

Flikarna är din andra navigeringsnivå. Vart och ett av funktionsområdena innehåller olika flikar, som var och en representerar en funktion.

### <a name="toolbar"></a>Verktygsfältet

När du klickar på de flesta flikar visas ett verktygsfält. Verktygsfältet har ikoner som utför en viss åtgärd. I följande tabell beskrivs ikonerna och deras åtgärder.

||||
|---|---|---|
|**Ikonen**|**Namn**|**Åtgärder**|
|![Ikonen Lägg till](../../media/ITPro-EAC-AddIcon.gif)|Lägg till, Nytt|Använd den här ikonen om du vill skapa ett nytt objekt. Vissa av dessa ikoner har en associerad nedpil som du kan klicka på för att visa ytterligare objekt som du kan skapa.|
|![Ikonen Redigera](../../media/ITPro-EAC-EditIcon.gif)|Redigera|Använd den här ikonen för att redigera ett objekt.|
|![ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.gif)|Ta bort|Använd den här ikonen om du vill ta bort ett objekt. Vissa borttagningsikoner har en nedpil som du kan klicka på för att visa ytterligare alternativ.|
|![Sökikon](../../media/ITPro-EAC-.gif)|Sök|Använd den här ikonen för att öppna en sökruta där du kan skriva sökfrasen för ett objekt som du vill söka efter.|
|![Ikonen Uppdatera](../../media/ITPro-EAC-RefreshIcon.gif)|Återställning|Använd den här ikonen för att uppdatera listvyn.|
|![Ikonen Fler alternativ](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Fler alternativ|Använd den här ikonen om du vill visa fler åtgärder som du kan utföra för flikens objekt. I Mottagare **visar \> användare** som klickar på den här ikonen alternativet för att utföra en **avancerad sökning**.|
|![Ikon för uppåtpil](../../media/ITPro-EAC-UpArrowIcon.gif)![Ikon för nedpil](../../media/ITPro-EAC-DownArrowIcon.gif)|Uppil och nedpil|Använd dessa ikoner för att flytta ett objekts prioritet uppåt eller nedåt.|
|![Ikon för borttagning](../../media/ITPro-EAC-RemoveIcon.gif)|Ta bort|Använd den här ikonen om du vill ta bort objekt från en lista.|
|

### <a name="list-view"></a>Listvy

När du väljer en flik visas i de flesta fall en listvy. Den synliga gränsen med EAC-listvyn är cirka 10 000 objekt. Dessutom ingår personsökning så att du kan bläddra till resultat.

### <a name="details-pane"></a>Informationsfönstret

När du markerar ett objekt i listvyn visas information om objektet i informationsfönstret. I vissa fall innehåller informationsfönstret hanteringsuppgifter.

### <a name="me-tile-and-help"></a>Jag kakel och hjälp

Med panelen **Jag** kan du logga ut EAC:en och logga in som en annan användare. På **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) den nedrullningssvänliga menyn Hjälpikon kan du utföra följande åtgärder:

- **Hjälp:** Klicka på ![ ](../../media/ITPro-EAC-HelpIcon.gif) Hjälpikonen för att visa hjälpinnehållet online.

- **Feedback**: Lämna feedback.

- **Community**: Post en fråga för att hitta svar i community forum.

- **Inaktivera hjälpbubbla:** Hjälpbubblan visar sammanhangsberoende hjälp för fält när du skapar eller redigerar ett objekt. Du kan stänga av hjälpbubblan eller slå på den om den har inaktiverats.

- **Visa kommandologgning:** Ett nytt fönster öppnas som visar motsvarande PowerShell-kommandon baserat på vad du har konfigurerat i EAC.

## <a name="supported-browsers"></a>Webbläsare som stöds

För bästa möjliga upplevelse av EAC rekommenderar vi att du alltid använder de senaste webbläsarna, Office-klienterna och apparna. Vi rekommenderar också att du installerar programuppdateringar när de blir tillgängliga. Mer information om de webbläsare och systemkrav som stöds för tjänsten finns i [Systemkrav för Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Språk som stöds

Följande språk stöds och är tillgängliga för EAC i fristående EOP.

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
