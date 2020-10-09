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
description: 'Sammanfattning: hur contoso använde ett team med säkerhets isolering för ett Top Secret för att utveckla en ny serie produkter och tjänster.'
ms.openlocfilehash: 16d10f5d6e5b5939172c02746c9324eb20b6987e
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399495"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isolerat team för ett hemligt projekt av Contoso Corporation

Efter en företags ledning beställde Contosos VD utvecklingen för en ny serie produkter och tjänster som kunde dubbelt så lite som Contosos vinst under de kommande fem åren. Det översta och hemliga projektet för att utveckla företags-, teknik-och marknads plan har bearbetats till **Project 2x** och viktiga anställda i företaget har rekryterats. 

Tids linjerna för forskning och utveckling var tätt avsedda att samarbetet måste vara effektivt och möjliggöra säkra möten, pågående konversationer och fil lagring.

De slutliga slut produkterna för Project 2X var företags abonnemang, produkt-och teknik specifikationer och marknadsförings material och schemalägger i form av Word-, Excel-och PowerPoint-filer. 

Till följd av känsligheten var följande:

- Begränsat till projekt som är dubbelt så grupp medlemmar och ledarskaps chef.
- Krypterat och skyddat med behörigheter att endast tillåta åtkomst till grupp medlemmar i Project 2X och chefs ledarskap, även om filerna distribuerades utanför deras skyddade mappar.

Contoso IT-personal använde ett [team med säkerhets isolering](secure-teams-security-isolation.md) för Project 2x och de här stegen.

## <a name="step-1-created-a-private-team"></a>Steg 1: skapa ett privat team

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen är det bara att contoso IT-administratörer konfigurerade de [rekommenderade åtkomst principerna för SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).

Sedan skapar en Contoso-administratör en ny privat grupp med Project 2X och La till användar kontona i Project 2X-personal som medlemmar. De har även konfigurerat gruppen så att bara Project 2X team-ägarna kan skapa privata kanaler.

Mer information finns i [skapa ett privat team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Steg 2: skapa en känslighets etikett för Project 2X-teamet

Contoso-administratörer har skapat en ny känslighets etikett med namnet **Project 2x** som:

- Aktive rad kryptering.
- Tillåtna Co-Author behörigheter för Project 2X Microsoft 365-gruppen.
- Tillåtna visnings behörigheter för gruppen chef.
- Blockerad åtkomst till ohanterade enheter.

Filer i avsnittet **dokument** på den underliggande Project 2x SharePoint-webbplatsen skyddas av:

- Webbplats behörigheterna, som endast tillåter fullständig behörighet till medlemmar i projektet 2X Microsoft 365-gruppen och Läs behörigheter till chefens ledarskaps grupp.
- Etiketten Project 2X känslighet med kryptering och behörigheter som följer med filen om den flyttas eller kopieras från webbplatsen.

Information om konfiguration finns i [skapa en känslighets etikett](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Steg 3: Konfigurera den underliggande SharePoint-webbplatsen

För att skydda åtkomsten till den underliggande SharePoint-webbplatsen för gruppen är det bara att contoso IT-administratörer konfigurerade de [rekommenderade åtkomst principerna för SharePoint](../security/office-365-security/sharepoint-file-access-policies.md).

Sedan har de konfigurerat ytterligare behörighets inställningar för webbplatsen:

- Om du inte vill att grupp medlemmar i Project 2X ska kunna dela åtkomst till webbplatsen. Information om konfiguration finns i [SharePoint-inställningar för en grupp med säkerhets isolering](secure-teams-security-isolation.md#sharepoint-settings).
- För Läs behörighet för gruppen chef.

Sedan har de konfigurerat ytterligare behörighets inställningar för webbplatsen för att förhindra att medlemmar i Project 2X kan dela åtkomsten till webbplatsen. 

Eftersom privata kanaler för Project 2X skapades inaktiverades gäst delningen av grupp ägaren och ange den som standard delnings länk till det **specifika** värdet.

Här är den resulterande konfigurationen för Project 2X-teamet med säkerhets isolering.

![Den resulterande konfigurationen för Project 2X-teamet](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Steg 4: utbildad Project 2X-grupp medlemmar

Contoso säkerhet bemannade projektets grupp medlemmar i en obligatorisk kurs som har passerat dem genom:

- Hur du får till gång till det nya projektet 2X, använda möten och chattar och hur du samarbetar med gruppfiler.
- Så här skapar du nya filer i teamet och laddar upp nya filer som skapats lokalt.
- Så här etiketterar du filer med etiketten dubbel känslighet för Project.
- En demonstration av hur Project-dubbel etikett skyddar en fil även när den lämnar gruppen.

Slut resultatet var en säker miljö där grupp medlemmarna i Project 2X samarbetar i en säker miljö för chattar, möten och filer.

Här är ett exempel på en fil som är lagrad i den underliggande Project 2X-webbplatsen med etiketten dubbel känslighet för Project.

![Ett exempel på en fil som lagras i den underliggande projektets dubbel webbplats](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

I ett par fall har Project 2X team medlemmar laddat ned filer som skyddas av Project 2X till en lokal enhet för offlinearbete. 

Men efter att ha uppmanats att ange autentiseringsuppgifter när du öppnade dem konstaterade de misstaget och tagit bort dem.

På grund av samarbets miljön i Teams och säkerhetsfunktionerna i Microsoft 365 var informationen i Project 2X den hemliga under projektets giltighets tid. Contoso meddelade sina abonnemang och är i färd med att lansera nya produkter och tjänster till passar av sina kunder och investerare och Chagrin.

## <a name="next-step"></a>Nästa steg

[Distribuera en grupp med säkerhets isolering](secure-teams-security-isolation.md) i din organisation.

