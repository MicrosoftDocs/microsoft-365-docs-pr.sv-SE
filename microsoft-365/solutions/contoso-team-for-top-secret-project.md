---
title: Isolerat team för ett hemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Sammanfattning: Hur Contoso använde en grupp med säkerhetsisolering för ett hemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029022"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isolerat team för ett hemligt projekt av Contoso Corporation

Efter en chef på plats beställde Contosos VD utvecklingen av en ny uppsättning produkter och tjänster som skulle kunna dubbla Contosos resultat under de kommande fem åren. Det topphemliga projektet att utveckla företagets, teknik- och marknadsplan kallades **Project 2X** och viktig personal i hela företaget har rekryteringts. 

Tidslinjerna för forskning och utveckling var knappa, vilket gjorde att samarbetet kunde vara effektivt och ge säkra möten, pågående konversationer och fillagring.

De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och tekniska specifikationer samt marknadsföringsmaterial och scheman i form av Word, Excel och PowerPoint filer. 

På grund av sin känsliga natur var åtkomsten till dessa filer:

- Begränsas till Project 2X-teammedlemmar och ledningsgruppen.
- Krypterad och skyddad med behörigheter att bara ge åtkomst till Project 2X-teammedlemmar och ledningsgruppen, även om filerna distribuerades utanför sina skyddade mappar.

Contosos IT-personal använde [ett team med säkerhetsisolering](secure-teams-security-isolation.md) för att Project 2X och de här stegen.

## <a name="step-1-created-a-private-team"></a>Steg 1: Skapat ett privat team

För att skydda åtkomsten till teamets underliggande SharePoint-webbplats konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint för åtkomstprinciper.](../security/office-365-security/sharepoint-file-access-policies.md)

En Contoso IT-administratör skapade sedan ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar. De har även konfigurerat teamet så att endast Project 2X-teamägare kan skapa privata kanaler.

Konfigurationsinformationen finns i Skapa [ett privat team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Steg 2: Skapat en känslighetsetikett för Project 2X-teamet

Contoso-administratörer har skapat en ny känslighetsetikett **med namnet Project 2X som:**

- Aktiverad kryptering.
- Tillåten Co-Author behörigheter för gruppen Project 2X Microsoft 365 användare.
- Tillåtna visningsbehörigheter för ledningsgruppsgruppen.
- Blockerad åtkomst till ohanterade enheter.

Filer i avsnittet **Dokument** på den underliggande webbplatsen Project 2X SharePoint skyddade av:

- Webbplatsbehörigheter, som endast tillåter fullständiga behörigheter för medlemmar i gruppen Project 2X Microsoft 365, och läsa behörigheter till ledningsgruppsgruppen.
- Den Project känslighetsetikett för 2X, med kryptering och behörigheter som tillsammans med filen flyttas eller kopieras från webbplatsen.

Mer information om konfiguration finns i [Skapa en känslighetsetikett](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Steg 3: Konfigurerade den underliggande SharePoint webbplatsen

För att skydda åtkomsten till teamets underliggande SharePoint-webbplats konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint för åtkomstprinciper.](../security/office-365-security/sharepoint-file-access-policies.md)

Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen:

- För att Project 2X-gruppmedlemmar från att dela åtkomst till webbplatsen. Information om konfiguration finns i SharePoint [för ett team med säkerhetsisolering](secure-teams-security-isolation.md#sharepoint-settings).
- För läsbehörigheter för ledningsgruppsgruppen.

Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen för att förhindra Project 2X-gruppmedlemmar från att dela åtkomst till webbplatsen. 

När privata kanaler för Project 2X har skapats inaktiverade gruppägaren gästdelningen och ställer in standardlänken för delning till värdet **Specifika** personer.

Här är den resulterande konfigurationen av en Project 2X-grupp med säkerhetsisolering.

![Den resulterande konfigurationen av 2X-Project 2X-gruppen](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: Utbildat Project 2X-teammedlemmar

Contoso-säkerhetspersonalen har utbildat Project 2X-teammedlemmar i en obligatorisk kurs som gått igenom dem:

- Hur du får tillgång till det Project 2X-teamet, använder möten och chattar och hur du samarbetar i teamfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- Så här etiketterar du filer Project med en känslighetsetikett som är 2X.
- En demonstration av hur en Project med 2X-etikett skyddar en fil även när den lämnar teamet.

Resultatet var en säker miljö där 2X-Project samarbetade i en säker miljö för chattar, möten och filer.

Här är ett exempel på en fil som lagras på den underliggande 2X Project-webbplatsen med känslighetsetiketten Project 2X tilldelat.

![Ett exempel på en fil som lagras på den underliggande Project 2X-webbplatsen](../media/contoso-team-for-top-secret-project-example.png)

I några fall laddade Project 2X-gruppmedlemmar ned filer skyddade av Project 2X-etiketten till en lokal enhet för offlinearbete. 

När de efter en uppmaning om att ange autentiseringsuppgifter när de öppnade dem insåg de sitt misstag och raderade dem.

På grund av samarbetsmiljön i Teams och säkerhetsfunktionerna i Microsoft 365 har informationen i Project 2X varit hemlig under hela projektet. Contoso meddelade sina planer och är i processen med att lansera nya produkter och tjänster till glädjen från sina kunder och investerare och chagrin av sina konkurrenter.

## <a name="next-step"></a>Nästa steg

[Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md) i din organisation.

