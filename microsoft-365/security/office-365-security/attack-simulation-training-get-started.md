---
title: Kom igång med Attack simuleringsträning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de kan använda utbildning i attacksimulering för att köra simulerad nätfiske- och lösenordsattacker i sina organisationer med Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a33c212f7d0fd6b0617a8059b03ac90de03fba16
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407486"
---
# <a name="get-started-using-attack-simulation-training"></a>Kom igång med Attack simuleringsträning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Om din organisation har Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2, som omfattar funktioner för hotundersökning och [svar,](office-365-ti.md)kan du använda utbildning i attackattack i Microsofts säkerhetscenter för att köra realistiska attackscenarier i organisationen. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nederkant. Läs den här artikeln om du vill veta mer.

> [!NOTE]
> Utbildning av attacksimulering ersätter den gamla attackberäkning v1-upplevelsen som beskrivs i Attack Defender i [Microsoft Defender för Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar Microsofts säkerhetscenter genom att gå till <https://security.microsoft.com/> . Utbildning av attacksimulering finns tillgänglig på **e-post- och** \> **samarbetsattacksimuleringsutbildning.** Om du vill gå direkt till attacksimuleringsutbildningen öppnar du <https://security.microsoft.com/attacksimulator> .

- Mer information om tillgängligheten för attackprenumerationer för olika Microsoft 365-prenumerationer finns i tjänstbeskrivningen för Microsoft Defender för [Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Du måste ha tilldelats behörigheter i Säkerhets- & Efterlevnadscenter eller i Azure Active Directory innan du kan utföra procedurerna i den här artikeln. Du måste vara medlem i **organisationshantering,** **säkerhetsadministratör** eller någon av följande roller:
  - **Administratörer för attackgrupper:** Skapa och hantera alla aspekter av attackspelingskampanjer.
  - **Författare av attack av nyttolast:** Skapa attack payloads som en administratör kan initiera senare.

  Mer information finns i Behörigheter [i Säkerhets- & Efterlevnadscenter](permissions-in-the-security-and-compliance-center.md) eller [Om administratörsroller.](../../admin/add-users/about-admin-roles.md)

- Det finns inga Motsvarande PowerShell-cmdlets för attacksimuleringsutbildning.

- Attackattack och utbildningsrelaterade data lagras med andra kunddata för Microsoft 365-tjänster. Mer information finns i [Microsoft 365-dataplatser.](../../enterprise/o365-data-locations.md) Attack simulering är tillgänglig i följande regioner: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN och KOR.

## <a name="simulations"></a>Simuleringar

*Nätfiske* är en vanlig term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar komma från legitima eller betrodda avsändare. *Nätfiske* är en del av några tekniker som vi klassificerar som _social engineering._

I utbildning för attacksimulering finns det flera typer av social engineering-tekniker:

- **Credential harvest**: An attacker sends the recipient a message that contains a URL. När mottagaren klickar på URL:en kommer de till en webbplats som vanligtvis visar en dialogruta där användaren uppmanas att ange sitt användarnamn och lösenord. Målsidan är vanligtvis tema som representerar en känd webbplats för att skapa förtroende för användaren.

- **Bifogad fil i** skadlig programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en bifogad fil. När mottagaren öppnar den bifogade filen körs godtycklig kod (till exempel ett makro) på användarens enhet för att hjälpa attackeraren att installera ytterligare kod eller ytterligare entrenchning själva.

- **Länk i bifogad** fil: Det här är en hybrid av en autentiseringsfördring. En attack skickar mottagaren ett meddelande som innehåller en URL i en bifogad fil. När mottagaren öppnar den bifogade filen och klickar på URL-adressen kommer de till en webbplats som vanligtvis visar en dialogruta där användaren ombeds ange sitt användarnamn och lösenord. Målsidan är vanligtvis tema som representerar en känd webbplats för att skapa förtroende för användaren.

- **Länk till skadlig** programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en länk till en bifogad fil på en känd fildelningswebbplats (till exempel SharePoint Online eller Dropbox). När mottagaren klickar på URL:en öppnas den bifogade filen och valfri kod (till exempel ett makro) körs på användarens enhet för att hjälpa attackerare att installera ytterligare kod eller ytterligare entrencha sig själva.

- **Drive-by-url:** En attacker skickar ett meddelande som innehåller en URL till mottagaren. När mottagaren klickar på URL:en kommer de till en webbplats som försöker köra bakgrundskod. Den här bakgrundskoden försöker samla in information om mottagaren eller distribuera godtycklig kod på enheten. Vanligtvis är målwebbplatsen en känd webbplats som har komprometterats eller klonats av en känd webbplats. Om du är bekant med webbplatsen övertygar du användaren om att länken är säker att klicka på. Den här tekniken kallas även för en _vattenstämpel som hålattack._

> [!NOTE]
> Kontrollera om den simulerade nätfiske-URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj. Medan vi arbetar med många url-ryktesleverantörer för att alltid tillåta dessa url:er för simulering har vi inte alltid fullständig täckning (till exempel Google Säker surfning). De flesta leverantörerna ger vägledning som gör att du alltid kan tillåta specifika URL:er (till <https://support.google.com/chrome/a/answer/7532419> exempel).

URL:erna som används av attacksimuleringsutbildningen beskrivs i följande lista:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Skapa en simulering

Stegvisa instruktioner om hur du skapar och skickar en ny simulering finns i [Simulera en nätfiskeattack.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Skapa en nyttolast

Stegvisa instruktioner för hur du skapar en nyttolast för användning i en simulering finns i Skapa en anpassad [nyttolast för attacksimuleringsutbildning.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Få insikter

Stegvisa instruktioner om hur du får insikter med rapporter finns i Utbildnings om [attacksimulering.](attack-simulation-training-insights.md)
