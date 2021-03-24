---
title: Isolerat team för ett hemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051012"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isolerat team för ett hemligt projekt av Contoso Corporation

Efter en chef på plats beställde Contosos VD utvecklingen av en ny uppsättning produkter och tjänster som skulle kunna dubbla Contosos resultat under de kommande fem åren. Det topphemliga projektet att utveckla affärs-, teknik- och marknadsplanen hette **Project 2X** och nyckelpersonal i hela företaget har rekryterings. 

Tidslinjerna för forskning och utveckling var knappa, vilket gjorde att samarbetet kunde vara effektivt och ge säkra möten, pågående konversationer och fillagring.

De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och tekniska specifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer. 

På grund av sin känsliga natur var åtkomsten till dessa filer:

- Begränsad till Project 2X-gruppmedlemmar och ledningsgruppen.
- Krypterat och skyddat med behörigheter att endast ge åtkomst till Project 2X-gruppmedlemmar och ledningsgruppen, även om filerna distribuerades utanför sina skyddade mappar.

Contosos IT-personal använde en [grupp med säkerhetsisolering](secure-teams-security-isolation.md) för Project 2X och de här stegen.

## <a name="step-1-created-a-private-team"></a>Steg 1: Skapat ett privat team

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint-åtkomstprincipen.](../security/defender-365-security/sharepoint-file-access-policies.md)

En Contoso IT-administratör skapade sedan ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar. De har även konfigurerat teamet så att endast Project 2X-teamägare kan skapa privata kanaler.

Konfigurationsinformationen finns i Skapa [ett privat team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Steg 2: Skapat en känslighetsetikett för Project 2X-teamet

Contoso-administratörer har skapat en ny känslighetsetikett med **namnet Project 2X som:**

- Aktiverad kryptering.
- Tillåten Co-Author för Microsoft 265-gruppen Project 2X.
- Tillåtna visningsbehörigheter för ledningsgruppsgruppen.
- Blockerad åtkomst till ohanterade enheter.

Filer i avsnittet **Dokument** på den underliggande SharePoint-webbplatsen för Project 2X skyddades av:

- Webbplatsbehörigheter, som endast tillåter fullständiga behörigheter för medlemmar i Microsoft 2X Microsoft 365-gruppen och läsbehörigheter för ledningsgruppsgruppen.
- Känslighetsetiketten för Project 2X med kryptering och behörigheter som förs med filen om den flyttas eller kopieras från webbplatsen.

Mer information om konfiguration finns i [Skapa en känslighetsetikett](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Steg 3: Konfigurerade den underliggande SharePoint-webbplatsen

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen konfigurerade Contoso IT-administratörer den [rekommenderade SharePoint-åtkomstprincipen.](../security/defender-365-security/sharepoint-file-access-policies.md)

Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen:

- Förhindra att medlemmar i Project 2X-grupper delar åtkomst till webbplatsen. Mer information om konfiguration finns i [SharePoint-inställningar för ett team med säkerhetsisolering](secure-teams-security-isolation.md#sharepoint-settings).
- För läsbehörigheter för ledningsgruppsgruppen.

Därefter har de konfigurerat ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X-gruppmedlemmar delar åtkomst till webbplatsen. 

När privata kanaler för Project 2X skapades inaktiverade gruppägaren gästdelningen och ställer in standardlänken för delning till **värdet Specifika** personer.

Här är den resulterande konfigurationen av Project 2X-teamet med säkerhetsisolering.

![Den resulterande konfigurationen av Project 2X-gruppen](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: Utbildning i Project 2X-gruppmedlemmar

Contoso-säkerhetspersonalen fick utbildning i Project 2X-gruppmedlemmarna i en obligatorisk kurs som tog dem genom:

- Hur du får tillgång till det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- Så här etiketterar du filer med känslighetsetiketten för Project 2X.
- En demonstration av hur project 2X-etiketten skyddar en fil även när den lämnar gruppen.

Resultatet var en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.

Här är ett exempel på en fil som lagrats på den underliggande Project 2X-webbplatsen med känslighetsetiketten för Project 2X tilldelad.

![Ett exempel på en fil som lagrats på den underliggande Project 2X-webbplatsen](../media/contoso-team-for-top-secret-project-example.png)

I några fall laddade Project 2X-gruppmedlemmar ned filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete. 

När de efter en uppmaning om att ange autentiseringsuppgifter när de öppnade dem insåg de sitt misstag och raderade dem.

På grund av samarbetsmiljön i Teams och säkerhetsfunktionerna i Microsoft 365 var informationen i Project 2X hemlig under hela projektet. Contoso meddelade sina planer och är i processen med att lansera nya produkter och tjänster till glädjen från sina kunder och investerare och chagrin av sina konkurrenter.

## <a name="next-step"></a>Nästa steg

[Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md) i din organisation.

