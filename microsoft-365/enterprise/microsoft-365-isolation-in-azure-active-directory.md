---
title: Microsoft 365-isolering och åtkomst kontroll i Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig hur isolering och åtkomst kontroll fungerar för att hålla data för flera klient organisationer isolerade från varandra i Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332418"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365-isolering och åtkomst kontroll i Azure Active Directory

Azure Active Directory (Azure AD) har utformats för att hantera flera klient organisationer på ett mycket säkert sätt via logisk data isolering. Åtkomst till Azure AD är gated av ett Authorization-lager. Azure AD isolerar kunder som använder klient organisationer som säkerhets gränser för att skydda en kunds innehåll, så att det inte går att komma åt eller göra intrång i en medarbetare. Tre kontroller utförs av Azure ADs Authorization-lager:

- Är huvud gruppen för åtkomst till Azure AD-klient organisationen?
- Är huvud delen aktive rad för åtkomst till data i denna klient organisation?
- Är huvud rollen för den här innehavaren godkänd för den typ av data åtkomst som begärs?

Inget program, användare, server eller tjänst kan komma åt Azure AD utan korrekt verifikation och token eller certifikat. Förfrågningar avvisas om de inte åtföljs av korrekta uppgifter.

Azure AD är effektivt och är värd för varje klient organisation i sin egen skyddade behållare, med principer och behörigheter till och inom behållaren som bara ägs och hanteras av innehavaren.
 
![Azure-behållare](../media/office-365-isolation-azure-container.png)

Konceptet med klient organisationer är djupt i katalog tjänsten på alla lager, från portaler till beständig lagring. Även när flera Azure AD Tenant-metadata lagras på samma fysiska disk finns det ingen relation mellan andra behållare än vad som definieras av katalog tjänsten, vilket i sin tur styrs av klient organisationens administratör. Det kan inte finnas några direkta anslutningar till Azure AD Storage från ett program eller en tjänst som begär det utan att först gå igenom auktoriseringsarkivet.

I det här exemplet nedan har contoso och Fabrikam båda separata, dedikerade behållare och även om dessa behållare kan dela en del av samma underliggande infrastruktur, till exempel servrar och lagrings enheter, är de åtskilda och isolerade från varandra, och gated genom åtkomst kontroll.
 
![Azure-dedikerade behållare](../media/office-365-isolation-azure-dedicated-containers.png)

Dessutom finns det inga program komponenter som kan köras i Azure AD och det är inte möjligt för en klient organisation att tvinga fram överträdelse av en annan klient organisations integritet, åtkomst krypterings nycklar för en annan klient organisation eller läsa rå data från servern.

Som standard tillåter Azure AD alla åtgärder som utfärdas av identiteter i andra klient organisationer. Varje klient organisation isoleras logiskt i Azure AD via anspråksmedvetna åtkomst kontroller. Läsning och skrivning av katalog data bevaras till klient behållare och gated med ett internt abstraktions skikt och ett lagerbaserat-lager (rollbaserad åtkomst kontroll) som sammantvingar innehavaren som säkerhets gräns. Varje begäran om åtkomst till katalog data behandlas av dessa lager och varje åtkomstbegäran i Microsoft 365 bevaras av ovanstående logik.

Azure AD har Nord Amerika, amerikanska myndigheter, Europeiska unionen, Tyskland och världs omfattande partitioner. Det finns en klient organisation i en enda partition och partitioner kan innehålla flera klient organisationer. Partitionsinformationen sammanfattas från användare. En given partition (inklusive alla klient organisationer) replikeras till flera data Center. Partitionen för en klient organisation väljs utifrån egenskaperna hos innehavaren (till exempel lands koden). Hemligheter och annan känslig information i alla partitioner är krypterade med en särskild. Nycklarna skapas automatiskt när en ny partition skapas.

Azure AD system-funktioner är en unik instans för varje användarsession. Dessutom använder Azure AD krypterings teknik för att isolera delade system resurser på nätverks nivå för att förhindra obehörig och oavsiktlig överföring av information.
