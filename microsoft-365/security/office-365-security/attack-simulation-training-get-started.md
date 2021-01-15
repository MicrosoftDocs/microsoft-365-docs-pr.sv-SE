---
title: Komma igång med att använda utbildning för attack simulering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda angrepps simulerings utbildning för att köra simulerade nätfiske och lösen ords attacker i sina Microsoft 365 E5-eller Microsoft Defender för Office 365 plan 2-organisationer.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871254"
---
# <a name="get-started-using-attack-simulation-training"></a>Komma igång med att använda utbildning för attack simulering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Om din organisation har Microsoft 365 E5 eller Microsoft Defender för Office 365 abonnemang 2, som innehåller [hot undersöknings-och svars funktioner](office-365-ti.md), kan du använda funktionen för simulering av attacker i Microsoft säkerhets Center för att köra realistiska angrepp i din organisation. Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din botten linje. Läs den här artikeln om du vill veta mer.

> [!NOTE]
> Utbildning för utskrivning av attacker ersätter den gamla attack Simulator v1-upplevelsen som beskrivs i [angrepps simulatorn i Microsoft Defender för Office 365](attack-simulator.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets Center genom att gå till <https://security.microsoft.com/> . Utbildning för att simulering av attacker är tillgängligt på utbildning om **e-post och samarbete** \> . Gå direkt till utbildning för angrepps simulering genom att öppna <https://security.microsoft.com/attacksimulator> .

- Mer information om hur du får till gång till utbildning för utskrivning i olika Microsoft 365-abonnemang finns i [Beskrivning av Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Du måste tilldelas behörigheter i säkerhets & efterföljandekrav eller i Azure Active Directory innan du kan göra det i den här artikeln. Specifikt måste du vara medlem i **organisations hantering**, **säkerhets administratör** eller någon av följande roller:
  - **Administratörer för angrepps Simulator**: skapa och hantera alla aspekter av kampanjer för utsättning av attacker.
  - **Nytto lastare för angrepps Simulator**: skapa nytto laster som en administratör kan initiera senare.

  Mer information finns i [behörigheter i avsnittet säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md) eller [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Det finns inga motsvarande PowerShell-cmdlets för utbildning för att simulera attacker.

- Information om attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster. Mer information finns i [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations). Simulering av attacker är för närvarande inte tillgängligt i följande regioner: SGP, Förenade Arabemiraten, ZAF, ty, BRA och CHE.

## <a name="simulations"></a>Simuleringar

*Nätfiske* är en generisk term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare. *Nätfiske* är en del av en delmängd teknik som vi klassificerar som _social teknik_.

I utbildning för att simulera attacker är flera typer av social teknik teknik tillgängliga:

- **Skörd för autentiseringsuppgifter**: en angripare skickar mottagaren ett meddelande som innehåller en URL. När mottagaren klickar på URL-adressen tas de till en webbplats som normalt visar en dialog ruta där användaren uppmanas att uppge användar namn och lösen ord. Vanligt vis är målsidan ett tema som representerar en välkänd webbplats för att bygga förtroende för användaren.

- **Bifogad fil med skadlig kod**: en angripare skickar mottagaren ett meddelande som innehåller en bifogad fil. När mottagaren öppnar den bifogade filen körs valfri kod (till exempel ett makro) på användarens enhet så att angriparen kan installera ytterligare kod eller entrench sig själva.

- **Länk i bilaga**: det här är en hybrid av en skörd för uppgifter. En angripare skickar mottagaren ett meddelande som innehåller en URL-adress i en bifogad fil. När mottagaren öppnar den bifogade filen och klickar på URL-adressen, tas de till en webbplats som visar en dialog ruta där användaren uppmanas att uppge användar namn och lösen ord. Vanligt vis är målsidan ett tema som representerar en välkänd webbplats för att bygga förtroende för användaren.

- **Länk till skadlig program vara**: angriparen skickar ett meddelande till mottagaren med en länk till en bifogad fil på en välkänd fildelnings webbplats (till exempel SharePoint Online eller Dropbox). När mottagaren klickar på URL-adressen öppnas den bifogade filen och valfri kod (till exempel ett makro) körs på användarens enhet så att angriparen kan installera ytterligare kod eller entrench sig själva.

- **Drive-by-URL**: en angripare skickar ett meddelande med en URL till mottagaren. När mottagaren klickar på URL-adressen tas de till en webbplats där bakgrunds koden körs. Den här bakgrunds koden försöker samla in information om mottagaren eller distribuera valfri kod på sina enheter. Vanligt vis är mål webbplatsen en välkänd webbplats som har komprometterats eller en klon av en välkänd webbplats. Bekant med webbplatsen gör det möjligt för användaren att klicka på länken. Den här tekniken kallas också ett hål för att _attackera_ ett problem.

> [!NOTE]
> Kontrol lera tillgängligheten för den simulerade nät fiske URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj. Medan vi arbetar med många URL-ryktes leverantörer för att alltid tillåta dessa simulerings-URL: er har vi inte alltid full täckning (till exempel Google Safe Internet). De flesta leverantörer tillhandahåller vägledning som gör att du alltid kan tillåta specifika webb adresser (till exempel <https://support.google.com/chrome/a/answer/7532419> ).

URL-adresserna som används för utbildning av angrepps simulering beskrivs i följande lista:

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

Steg för steg-instruktioner om hur du skapar och skickar en ny simulering finns i [simulera en nätfiske-attack](attack-simulation-training.md).

### <a name="create-a-payload"></a>Skapa en nytto Last

Mer information om hur du skapar en nytto last för användning i en simulering finns i [skapa en anpassad nytto last för utbildning för attack simulering](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Få insikter

Steg för steg-instruktioner om hur du får insikter med rapportering finns i [få insikter genom att öva på att simulera attacker](attack-simulation-training-insights.md).
