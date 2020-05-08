---
title: Isolerat team för ett topphemligt projekt av Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: 'Sammanfattning: Hur Contoso använde ett team med säkerhetsisolering för ett topphemligt projekt för att utveckla en ny uppsättning produkter och tjänster.'
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159461"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isolerat team för ett topphemligt projekt av Contoso Corporation

Efter en verkställande offsite, Contoso VD beställde utvecklingen av en ny svit av produkter och tjänster som kan fördubbla Contoso vinst under de kommande fem åren. Det topphemliga projektet för att utveckla affärs-, ingenjörs- och marknadsplanen fick namnet **Project 2X** och nyckelpersonal i hela företaget rekryterades. 

Tidslinjerna för forskning och utveckling var snäva, vilket innebar att samarbetet måste vara effektivt och ge säkra möten, pågående samtal och fillagring.

De resulterande slutprodukterna för Project 2X var affärsplaner, produkt- och teknikspecifikationer samt marknadsföringsmaterial och scheman i form av Word-, Excel- och PowerPoint-filer. 

På grund av deras känsliga karaktär, tillgång till dessa filer var:

- Begränsad till Project 2X-gruppmedlemmar.
- Krypterad och skyddad med behörighet att endast tillåta åtkomst till Project 2X-gruppmedlemmar, även om filerna distribuerades utanför sina säkra mappar.

Contoso IT-personal använde ett [team med säkerhetsisolering](secure-teams-security-isolation.md) för Project 2X och dessa steg.

## <a name="step-1-created-a-private-team"></a>Steg 1: Skapade ett privat team

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](../enterprise/sharepoint-file-access-policies.md).

Därefter skapade en Contoso IT-administratör ett nytt privat team med namnet Project 2X och lade till användarkontona för Project 2X-personal som medlemmar.

Konfigurationsinformation finns i [Skapa ett privat team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Steg 2: Skapade en känslighetsetikett för Project 2X-teamet

Contoso-administratörer skapade en ny känslighetsetikett med namnet **Project 2X** som:

- Kräver kryptering.
- Tillåter samtidiga redigeringsbehörigheter för gruppen Project 2X Microsoft 365.

Filerna i avsnittet **Dokument** på den underliggande Project 2X SharePoint-webbplatsen skyddades av:

- Webbplatsbehörigheterna, som endast ger åtkomst till medlemmar i Gruppen Project 2X Microsoft 365.
- Känslighetsetiketten För Project 2X, med kryptering och behörigheter som färdas med filen om den flyttas eller kopieras från webbplatsen.

Konfigurationsinformation finns i [Skapa en känslighetsetikett](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Steg 3: Konfigurerade den underliggande SharePoint-webbplatsen

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för teamet konfigurerade Contoso IT-administratörer de [rekommenderade SharePoint-åtkomstprinciperna](../enterprise/sharepoint-file-access-policies.md).

Därefter konfigurerade de ytterligare behörighetsinställningar för webbplatsen för att förhindra att Project 2X delar åtkomst till webbplatsen. Konfigurationsinformation finns i [SharePoint-inställningar för ett team med säkerhetsisolering](secure-teams-security-isolation.md#sharepoint-settings).

Här är den resulterande konfigurationen av Project 2X-teamet.

![Den resulterande konfigurationen av Project 2X-teamet](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: Utbildade Project 2X-gruppmedlemmar

Contoso säkerhetspersonal utbildade Project 2X-teammedlemmarna i en obligatorisk kurs som klev igenom dem:

- Så här kommer du åt det nya Project 2X-teamet, använder möten och chattar och hur du samarbetar i gruppfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- En demonstration av hur DLP-principen blockerar filer från att delas externt.
- Så här märker du filer med känslighetsetiketten För Project 2X.
- En demonstration av hur Project 2X-etiketten skyddar en fil även när den lämnar teamet.

Slutresultatet blev en säker miljö där Project 2X-gruppmedlemmar samarbetade i en säker miljö för chattar, möten och filer.

Här är ett exempel på en fil som lagras i den underliggande Project 2X-platsen med känslighetsetiketten Project 2X tilldelad.

![Ett exempel på en fil som lagras på den underliggande Project 2X-platsen](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

I ett par fall hämtade Project 2X-gruppmedlemmar filer som skyddas av Project 2X-etiketten till en lokal enhet för offlinearbete. Men efter att ha uppmanats om autentiseringsuppgifter när de öppnades, insåg de sitt misstag och tog bort dem.

På grund av teamens samarbetsmiljö och säkerhetsfunktionerna i Microsoft 365 hölls detaljerna i Project 2X hemliga under hela projektet. Contoso tillkännagav sina planer och håller på att rulla ut de nya produkterna och tjänsterna till glädje för sina kunder och investerare och förtret för sina konkurrenter.

## <a name="next-step"></a>Nästa steg

[Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md) i organisationen.

