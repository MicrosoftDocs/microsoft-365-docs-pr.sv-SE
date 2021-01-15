---
title: Simulera nätfiske-attack med Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur man simulerar nät fiske attacker och tränar användarna att förhindra nätfiske genom att använda utbildning för attack simulering i Microsoft Defender för Office 365.
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870973"
---
# <a name="simulate-a-phishing-attack"></a>Simulera nätfiske-attack

Utbildning för angrepps simulering i Microsoft Defender för Office 365 kan du köra säkra cyberattack-simuleringar på din organisation för att testa din säkerhets policy och dina arbets rutiner, samt för att träna dina anställda att öka sin medvetenhet och minska deras känslighet för attacker. I den här artikeln får du lära dig hur du skapar en simulerad nätfiske-attack med utbildning för att simulera attacker.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Information om hur du kommer igång med utbildning för att förbereda attacker finns i [komma igång med att använda funktionen för simulering av attacker](attack-simulation-training-get-started.md).

För att starta en simulerad nätfiske-attack, öppna [Microsoft 365 Security Center](https://security.microsoft.com/), gå till **e-& samarbets** möjligheter för \> **simulering** och gå till fliken [**simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Välj **+ starta en simulering** under **simuleringar**.

![Starta en simulerings knapp i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> När som helst under simuleringen kan du spara och stänga för att fortsätta att konfigurera simuleringen senare.

## <a name="selecting-a-social-engineering-technique"></a>Välja en social teknik teknik

Välj bland fyra olika tekniker som kan granskas från [Mitre to&CK® Framework](https://attack.mitre.org/techniques/enterprise/). Olika nytto laster är tillgängliga för olika tekniker:

- När uppgifter **skördas** försöker insamling av autentiseringsuppgifter genom att användare till en välkänd webbplats med inmatnings rutor skickar ett användar namn och lösen ord.
- **Bifogad fil med skadlig kod** lägger till en skadlig bifogad fil i ett meddelande. När användaren öppnar den bifogade filen körs valfri kod som gör att angriparen kan kompromissa med mål enheten.
- **Länk i bilaga** är en typ av certifiering skörde hybrid. En angripare infogar en URL i en e-postbilaga. URL-adressen i den bifogade filen följer samma teknik som skörd för autentiseringsuppgifter.
- **Länk till malware kör skadlig** kod från en fil som finns på en välkänd fildelnings tjänst. Meddelandet som skickas till användaren innehåller en länk till den här skadliga filen. Att öppna filen och göra det lättare för angriparen att kompromissa med mål enheten.

> [!TIP]
> Om du klickar på **Visa information** inom beskrivningen av varje teknik visas ytterligare information och simulerings stegen för tekniken.
>
> ![Simulerings steg för certifiering skörd inom utbildning för simulering av attacker i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-sim-steps.png)

När du har valt en teknik och klickat på **Nästa** ska du ge simuleringen ett namn och eventuellt en beskrivning.

## <a name="selecting-a-payload"></a>Välja en nytto Last

Sedan måste du antingen välja en nytto Last från en befintlig nytto Last katalog.

Det finns många data punkter som du kan använda för att välja:

- **Klicka på Rate** räknas hur många personer som klickade på denna nytto Last.
- **Förväntad kompromiss frekvens** förväntar sig att procent andelen personer som kommer att bli utsatt för denna nytto Last baserat på historiska data för nytto lasten i Microsoft Defender för Office 365-kunder.
- **Simuleringar startas** antal gånger denna nytto Last användes i andra simuleringar.
- **Komplexitet**, tillgängliga genom **filter**, beräknas baserat på antalet indikatorer inom nytto lasten som led trådar till att det är en attack. Fler indikatorer kan leda till lägre komplexitet.
- **Källa**, som är tillgänglig via **filter**, anger om nytto lasten skapades på din klient organisation eller är en del av Microsofts förvalda nytto fil katalog (global).

![Vald nytto Last i utbildning för attack simulering i Microsoft 365 säkerhets Center](../../media/attack-sim-preview-select-payload.png)

Välj en nytto Last i listan för att se en förhands granskning av nytto lasten med ytterligare information om den.

Om du vill skapa en egen nytto Last läser du [skapa en nytto last för utbildning för utskrivning](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Mål grupps anpassning

Nu är det dags att välja simuleringens mål grupp. Du kan välja att **ta med alla användare i organisationen** eller **bara ta med specifika användare och grupper**.

Om du väljer att **bara inkludera specifika användare och grupper** kan du antingen:

- **Lägg till användare**, som gör att du kan använda Sök funktionen för din klient organisation, samt avancerade funktioner för sökning och filtrering, som mål för användare som inte har riktat mot en simulering under de senaste 3 månaderna.
  ![Användar filter i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)
- **Importera från CSV** låter dig importera en fördefinierad uppsättning användare för den här simuleringen.

## <a name="assigning-training"></a>Tilldela utbildning

Vi rekommenderar att du tilldelar utbildning för varje simulering, eftersom anställda som deltar i utbildningen är mindre utsatta för liknande attacker.

Du kan antingen välja att ha utbildning tilldelat åt dig eller välja kurser och moduler själv.

Välj **förfallo datum för utbildning** för att se till att anställda avslutar sin utbildning i god tid.

> [!NOTE]
> Om du väljer att välja kurser och moduler själv kan du fortfarande se det rekommenderade innehållet och alla tillgängliga kurser och moduler.
>
> ![Lägga till Rekommenderad utbildning i utbildning för attack simulering i Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

I nästa steg måste du **lägga till utbildningar** om du väljer det själv och anpassar din utbildning. Du kan förhandsgranska övnings sidan för utbildning och även ändra sidhuvud och brödtext.

## <a name="launch-details-and-review"></a>Starta detaljer och granska

Nu när allt är konfigurerat kan du starta simuleringen direkt eller schemalägga det för ett senare datum. Du måste också välja när simuleringen ska avslutas. Vi slutar samla in interaktionen med den här simuleringen tidigare den valda tiden.

**Aktivera region medveten leverans** för att leverera simulerade attack meddelanden till dina anställda under deras arbets tid baserat på deras region.

När du är klar klickar du på **Nästa** och läser informationen för simuleringen. Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra eventuell information som behövs. När du är klar klickar du på **Skicka**.
