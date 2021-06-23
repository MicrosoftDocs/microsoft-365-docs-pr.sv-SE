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
description: Administratörer kan lära sig hur de använder utbildning av attack simulering för att köra simulerad nätfiske- och lösenordsattacker i sina Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2 organisationer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082906"
---
# <a name="get-started-using-attack-simulation-training"></a>Kom igång med Attack simuleringsträning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för** [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

Om din organisation har Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2, som innehåller funktioner för undersökning av hot och [svar,](office-365-ti.md)kan du använda utbildning av attackspel i Microsoft 365 Defender-portalen för att köra realistiska attackscenarier i organisationen. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nedersta linje. Läs den här artikeln om du vill veta mer.

> [!NOTE]
> Utbildning av attack simulering ersätter den gamla attackberäkning v1-upplevelsen som beskrivs i [Attack Defender i Microsoft Defender för Office 365](attack-simulator.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Utbildning av attack simulering är tillgänglig på **E-post och** \> **samarbete Attack simulering utbildning**. Om du vill gå direkt till simuleringsutbildningen för attack öppnar du <https://security.microsoft.com/attacksimulator> .

- Mer information om tillgängligheten för simulering av attack i olika abonnemang Microsoft 365 finns i [Microsoft Defender Office 365 beskrivning av tjänsten](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Du måste ha tilldelats behörigheter i portalen Microsoft 365 Defender eller i Azure Active Directory innan du kan utföra procedurerna i den här artikeln. Du måste vara medlem i Organisationshantering, **Säkerhetsadministratör** eller någon av följande roller: 
  - **Attack attackadministratörer:** Skapa och hantera alla aspekter av attack simuleringskampanjer.
  - **Författare av attack av nyttolast**: Skapa attack payloads som en administratör kan initiera senare.

  Mer information finns i [Behörigheter i Microsoft 365 Defender eller](permissions-microsoft-365-security-center.md) Om [administratörsroller.](../../admin/add-users/about-admin-roles.md)

- Det finns inga Motsvarande PowerShell-cmdlets för simulering av attackattacker.

- Attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365 tjänster. Mer information finns [Microsoft 365 dataplatser](../../enterprise/o365-data-locations.md). Attack simulering är tillgänglig i följande regioner: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN och KOR.

- Från och med 15 juni 2021 finns simuleringsutbildning för attack i GCC. Om din organisation har Office 365 G5 GCC eller Microsoft Defender för Office 365 (abonnemang 2) för myndigheter kan du använda utbildning av attackspel i Microsoft 365 Defender-portalen för att köra realistiska attackscenarier i organisationen enligt beskrivningen i den här artikeln. Utbildning av attack simulering är ännu inte tillgängligt GCC hög- eller dod-miljöer.

> [!NOTE]
> Utbildning av attack simulering ger en del av funktionerna för E3-kunder som en utvärderingsversion. Utvärderingserbjudandet innehåller möjligheten att använda en nyttolast för autentiseringsuppgifter och möjligheten att välja utbildningsupplevelser om ISA-nätfiske eller massutfiske. Inga andra funktioner ingår i utvärderingsversionen av E3.

## <a name="simulations"></a>Simuleringar

*Nätfiske* är en allmän term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. *Nätfiske* är en del av en del av en uppsättning tekniker som vi klassificerar som _social engineering_.

I utbildning av attack simulering finns det flera typer av social engineering-tekniker:

- **Credential credential harvest**: An attacker sends the recipient a message that contains a URL. När mottagaren klickar på URL-adressen kommer de till en webbplats som vanligtvis visar en dialogruta där användaren uppmanas att ange sitt användarnamn och lösenord. Målsidan brukar motsvara en känd webbplats för att skapa förtroende för användaren.

- **Bifogad fil från** skadlig programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en bifogad fil. När mottagaren öppnar den bifogade filen körs godtycklig kod (till exempel ett makro) på användarens enhet för att hjälpa attackerare att installera ytterligare kod eller ytterligare entrencha sig själva.

- **Länk i bifogad** fil: Det här är en hybrid av en credential-skörd. En attackerare skickar ett meddelande till mottagaren som innehåller en URL-adress i en bifogad fil. När mottagaren öppnar den bifogade filen och klickar på URL-adressen kommer de till en webbplats som vanligtvis visar en dialogruta där användaren ombeds ange sitt användarnamn och lösenord. Målsidan brukar motsvara en känd webbplats för att skapa förtroende för användaren.

- **Länk till skadlig** programvara: En attackerare skickar ett meddelande till mottagaren som innehåller en länk till en bifogad fil på en känd webbplats för fildelning (till exempel SharePoint Online eller Dropbox). När mottagaren klickar på URL-adressen öppnas den bifogade filen och godtycklig kod (till exempel ett makro) körs på användarens enhet för att hjälpa attackeret att installera ytterligare kod eller ytterligare entrencha sig själva.

- **Drive-by-url**: En attack skickar ett meddelande till mottagaren som innehåller en URL. När mottagaren klickar på URL-adressen tas den till en webbplats som försöker köra bakgrundskod. Den här bakgrundskoden försöker samla in information om mottagaren eller distribuera godtycklig kod på enheten. Vanligtvis är målwebbplatsen en känd webbplats som har komprometterats eller en klona av en känd webbplats. Webbplatsens bekanta med webbplatsen övertygar användaren om att länken är säker att klicka på. Den här tekniken kallas även för en _watering hole-attack_.

> [!NOTE]
> Kontrollera om den simulerade nätfiske-URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj. Medan vi arbetar med många url-ryktesleverantörer för att alltid tillåta dessa simulerings-URL:er har vi inte alltid fullständig täckning (till exempel Google Valv Browsing). De flesta leverantörer ger vägledning som gör att du alltid kan tillåta specifika URL:er (till <https://support.google.com/chrome/a/answer/7532419> exempel).

Url:erna som används av simuleringsutbildning för attack beskrivs i följande lista:

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

Stegvisa instruktioner om hur du skapar och skickar en ny simulering finns i [Simulera en nätfiskeattack](attack-simulation-training.md).

### <a name="create-a-payload"></a>Skapa en nyttolast

Stegvisa instruktioner för hur du skapar en nyttolast för användning i en simulering finns i Skapa en anpassad [nyttolast för utbildning av attackattacker.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Få insikter

Stegvisa instruktioner om hur du får insikter med rapporter finns i Få insikter [genom utbildning av attack simulering](attack-simulation-training-insights.md).

> [!NOTE]
> Attack Defender använder Valv-länkar i Defender för Office 365 för att säkert spåra klickdata för URL-adressen i nyttolastmeddelandet som skickas till riktade mottagare av en nätfiskekampanj, även om inställningen Spåra inte **användarens** klickningar i Valv-länkar är aktiverad.
