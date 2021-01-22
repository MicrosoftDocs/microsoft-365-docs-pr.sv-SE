---
title: Simulera en nätfiskeattack med Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur de kan simulera nätfiskeattacker och träna sina användare mot nätfiskeskydd med hjälp av utbildning för attackbedrägerier i Microsoft Defender för Office 365.
ms.technology: mdo
ms.openlocfilehash: f22fe8633d8ffa8856f851369739a0f12364342b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929208"
---
# <a name="simulate-a-phishing-attack"></a>Simulera en nätfiskeattack

Med hjälp av attacksimuleringsutbildning i Microsoft Defender för Office 365 kan du köra simuleringar av cyberattacker på din organisation för att testa säkerhetsprinciper och säkerhetsmetoder, samt utbilda de anställda att öka medvetenheten och minska deras känslighet för attacker. I den här artikeln får du hjälp med att skapa en simulerad nätfiskeattack med hjälp av utbildning om attacksimulering.

Information om att simulera attacker finns i Komma igång med att [använda attackerssimuleringsutbildning.](attack-simulation-training-get-started.md)

Om du vill starta en simulerad nätfiskeattack öppnar du Säkerhetscenter för [Microsoft 365,](https://security.microsoft.com/)går till E-post&-utbildning för samarbetsattack och växlar till  \>  [**fliken Simuleringar.**](https://security.microsoft.com/attacksimulator?viewid=simulations)

Under **Simuleringar** väljer du **+ Starta en simulering.**

![Starta en simuleringsknapp i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> När som helst under simuleringen kan du spara och stänga för att fortsätta konfigurera simuleringen vid ett senare tillfälle.

## <a name="selecting-a-social-engineering-technique"></a>Välja en social engineering-teknik

Välj bland fyra olika tekniker, utvalda från [MITRE ATT&CK® framework.](https://attack.mitre.org/techniques/enterprise/) Olika nyttolaster är tillgängliga för olika tekniker:

- **Autentiseringsuppgifter försöker samla** in autentiseringsuppgifter genom att ta användare till en känd webbplats med inmatningsrutor för att skicka ett användarnamn och lösenord.
- **Bifogad fil i** skadlig programvara lägger till en skadlig bilaga i ett meddelande. När användaren öppnar den bifogade filen körs godtycklig kod som hjälper attackeraren att kompromettera målets enhet.
- **Länk i bifogad** fil är en typ av hybrid för autentiseringsuppgifter för att samla information. En attack infogar en URL i en e-postbilaga. URL:en i den bifogade filen följer samma teknik som för den autentiseringsuppgifter.
- **Länk till skadlig** programvara kör skadlig kod från en fil som finns på en känd fildelningstjänst. Meddelandet som skickas till användaren innehåller en länk till filen. Öppna filen och hjälp attackeraren att kompromettera målets enhet.

> [!TIP]
> Om du **klickar på** Visa information i beskrivningen av varje teknik visas ytterligare information och simuleringsstegen för tekniken.
>
> ![Simuleringssteg för att samla autentiseringsuppgifter i attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-sim-steps.png)

När du har valt metoden och klickat på **Nästa ger du** din simulering ett namn och en beskrivning om du vill.

## <a name="selecting-a-payload"></a>Välja ett nyttolast

Därefter måste du antingen välja en nyttolast från den befintliga nyttolastkatalogen.

Nyttolaster har ett antal datapunkter som hjälper dig att välja:

- **Click rate counts** how many people clicked this payload.
- **Förutsagd** komprometterad ränta förutsäger den procentandel av personer som kommer att bli komprometterad av den här nyttolasten baserat på historiska data för nyttolasten i Microsoft Defender för Office 365-kunder.
- **Vid simuleringar** som startas räknas antalet gånger som den här nyttolasten har använts i andra simuleringar.
- **Komplexiteten,** som är tillgänglig **via** filter, beräknas utifrån antalet indikatorer i nyttolasten som tyder på att den är en attack. Fler indikatorer leder till lägre komplexitet.
- **Källa,** som är tillgänglig **via** filter, anger om nyttolasten skapades i klientorganisationen eller är en del av Microsofts befintliga nyttolastkatalog (global).

![Vald nyttolast inom attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-select-payload.png)

Välj en nyttolast i listan om du vill se en förhandsgranskning av nyttolasten med ytterligare information om den.

Om du vill skapa en egen nyttolast kan du läsa om att [skapa en nyttolast för att simulera attacker.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Målgruppsanpassning

Nu är det dags att välja den här simuleringens målgrupp. Du kan välja att **inkludera alla användare i organisationen eller** att endast inkludera vissa användare och **grupper.**

När du väljer att **endast inkludera vissa användare och grupper kan** du antingen:

- **Lägg till** användare, så att du kan utnyttja sökning för klientorganisationen, samt avancerade sök- och filtreringsfunktioner, till exempel rikta användare som inte har riktats av en simulering under de senaste 3 månaderna.
  ![Användarfiltrering i utbildning om attacksimulering i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-user-targeting.png)
- **Med import från CSV** kan du importera en fördefinierad uppsättning användare för den här simuleringen.

## <a name="assigning-training"></a>Tilldela utbildning

Vi rekommenderar att du tilldelar utbildning för varje simulering eftersom anställda som går på utbildning är mindre känsliga för liknande attacker.

Du kan antingen välja att själv tilldela utbildning till dig eller välja själv kurser och moduler.

Välj förfallodatum **för utbildningen för** att se till att de anställda slutför sin utbildning i tid.

> [!NOTE]
> Om du väljer att själv välja kurser och moduler kan du fortfarande se det rekommenderade innehållet samt alla tillgängliga kurser och moduler.
>
> ![Lägga till rekommenderad utbildning inom attacksimuleringsutbildning i Microsoft 365 säkerhetscenter](../../media/attack-sim-preview-add-training.png)

I nästa steg måste du  lägga till utbildningar om du valt att själv välja det och anpassa startsidan för utbildningen. Du kommer att kunna förhandsgranska startsidan för utbildningen samt ändra sidhuvudet och brödtexten.

## <a name="launch-details-and-review"></a>Starta information och granska

Nu när allt är konfigurerat kan du starta den här simuleringen direkt eller schemalägga den till ett senare datum. Du måste också välja när du vill avsluta den här simuleringen. Vi slutar fånga interaktionen med den här simuleringen efter den valda tiden.

**Aktivera regionmedveten tidszonsleverans** för att leverera simulerade attackmeddelanden till dina anställda under deras arbetstider baserat på deras region.

När du är klar klickar du på **Nästa och** granskar detaljerna i din simulering. Klicka på **Redigera** på någon av delarna för att gå tillbaka och ändra information som behöver ändras. Klicka på Skicka när du **är klar.**
