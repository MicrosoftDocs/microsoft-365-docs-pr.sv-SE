---
title: Hantera Relevanskonfigurationen i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Läs rekommendationerna för hur du konfigurerar Relevansträning i Advanced eDiscovery, så att du kan betygsätta filer efter relevans och ta fram analysresultat.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161722"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a>Hantera Relevanskonfigurationen i Advanced eDiscovery (klassisk version)

> [!NOTE]
> För Advanced eDiscovery krävs Office 365 E3 med tillägget Advanced Compliance eller en E5-prenumeration för din organisation. Om du inte har detta abonnemang men vill prova Advanced eDiscovery kan du [registrera dig för en utvärderingsversion av Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 Tekniken bakom Advanced eDiscovery Relevans använder expertledd programvara till att betygsätta filer efter relevans. Advanced eDiscovery Relevans kan användas till tidig aktutvärdering (Early Case Assessment – ECA), gallring och granskning av exempelfiler. 
  
 Advanced eDiscovery innehåller komponenter för Relevansträning och märkning av filer som hör till en akt. Med hjälp av träningsexempel på relevanta och ej relevanta filer lär sig Advanced eDiscovery att sätta relevanspoäng på olika filer och att skapa analysresultat som kan användas under och efter filgranskningsprocessen. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Riktlinjer för att konfigurera Relevansträning

 I Advanced eDiscovery går du till fönstret **Akter**, väljer en akt och klickar på **Gå till akten**. Klicka på **Relevans** \> **Relevanskonfiguration**. Följ riktlinjerna för att konfigurera Relevans. 
  
- **Märkning:** Effektiviteten hos den iterativa processen för Relevansträning beror på expertens förmåga att märka filexemplen med precision och konsekvens.

- **Problem med akter**:
  
  - För varje problem ska samma expert användas under hela Relevansträningsprocessen. Det är inte tillåtet att använda flera experter för att markera ett och samma problem flera gånger.
  
  - Avgör om varje grupp av filer är relevant endast för ett visst problem.

  - Om ett problem är för brett definierat kan Advanced eDiscovery returnera för många irrelevanta filer. Om ett problem är för smalt definierat kan Relevansträningsprocessen ta längre tid. 

  - Under varje Relevansträningscykel fokuserar Advanced eDiscovery på ett enskilt aktivt problem och interimsresultat från exemplen visas i enlighet med detta.

  - I ett scenario med flera problem går det att välja vilka problem som ska ingå i bearbetningen med hjälp av Urvalsläge. Problem som definieras som ”av” bearbetas inte förrän deras urvalsläge ändras. Ett problem kan endast vara ”inaktivt” eller ”på” för en expert.

  - Advanced eDiscovery kan användas till att skapa kandidatprivilegiefiler. Konfigurera ett separat problem för privilegier. Om möjligt bör du träna och gallra för relevans innan du använder endast den gallrade uppsättningen till privilegieträning (läs in den gallrade uppsättningen på nytt som en separat akt). 

  - Batchberäkningar kan endast utföras om det inte finns några öppna exempel (när du klickar på Batchberäkning visas en lista över användare med öppna exempel). För att ”stänga” exempel åt andra användare (detta bör endast utföras om användarna inte håller på att markera dessa exempel) kan administratören använda funktionen ”Ändra relevans” med alternativet ”Alla användares exempel”.

- **Metadata**: Advanced eDiscovery fokuserar på innehållet. Metadata tas inte i beaktning för relevanskriteriet.

- **Relevansgrad**: Om relevansgraden för ett problem är lägre än 3 % efter värdering, bör du överväga att använda seeding med kända relevanta och ej relevanta filer på Relevansträningen.

- **Filstorlek**: Stora filer (över 5 242 880 tecken i extraherad text) ignoreras i Relevans. Filerna ingår inte i Relevansträningsprocessen och får inga relevanspoäng efter Batchberäkning. Filer som är större än 5 MB kan inkluderas i värderingsuppsättningen.

## <a name="setting-up-case-issues"></a>Konfigurera aktproblem

De parametrar som beskrivs i det här avsnittet finns tillgängliga i Advanced eDiscovery, via **Relevans** \> **Relevanskonfiguration**.
  
- Problemen måste tilldelas till en användare som ska träna filerna.

- Därefter måste importerade filer läggas till i den dossier som ska behandlas.

- Var noggrann när du definierar och organiserar problem, eftersom detta påverkar resultaten från Relevansträningen.

När alla parametrar har angivits kan granskaren/experten börja träna filerna under fliken **Relevans**.
