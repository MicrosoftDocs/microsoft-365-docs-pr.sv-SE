---
title: Dekryptering i eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer Microsoft 365 hur eDiscovery-verktyg hanterar krypterade dokument som bifogas i e-postmeddelanden och lagras i SharePoint Online och OneDrive för företag.
ms.openlocfilehash: b87d87b7b0e870d6f396d87dc693fb8f41d5826b
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "52162652"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Dekryptering i Microsoft 365 eDiscovery-verktyg

Kryptering är en viktig del av din strategi för filskydd och informationsskydd. Organisationer av alla typer använder krypteringsteknik för att skydda känsligt innehåll inom organisationen och säkerställa att bara rätt personer har åtkomst till innehållet.

För att utföra vanliga eDiscovery-uppgifter på krypterat innehåll måste eDiscovery-hanterare dekryptera innehåll i e-postmeddelanden när det exporterades från innehållssökningar, Core eDiscovery-fall och Advanced eDiscovery fall. Innehåll som krypterades med Microsoft-krypteringstekniker var inte tillgängligt för granskning förrän efter att det exporterades.

För att göra det enklare att hantera krypterat innehåll i eDiscovery-arbetsflödet använder Microsoft 365 eDiscovery-verktygen nu dekryptering av krypterade filer som bifogas i e-postmeddelanden och som skickas i Exchange Online. <sup>1</sup> Dessutom kan krypterade dokument som lagras SharePoint Online och OneDrive för företag dekrypteras i Advanced eDiscovery.

Före den här nya funktionen dekrypterades endast innehållet i ett e-postmeddelande som skyddas av rättighetshantering (och inte bifogade filer). Krypterade dokument i SharePoint och OneDrive kunde inte dekrypteras under eDiscovery-arbetsflödet. Nu finns filer som är krypterade med en Microsoft-krypteringsteknik på ett SharePoint- eller OneDrive-konto sökbara och dekrypterade när sökresultaten förbereds för förhandsgranskning, läggs till i en granskning i Advanced eDiscovery och exporteras. Dessutom är krypterade dokument i SharePoint och OneDrive som bifogas i ett e-postmeddelande sökbara. Med den här dekrypteringsfunktionerna kan eDiscovery-hanterare visa innehållet i krypterade e-postbilagor och webbplatsdokument när de förhandsgranskar sökresultat och granska dem när de har lagts till i en granskningsuppsättning Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>Krypteringsteknik som stöds

Microsofts eDiscovery-verktyg stöder objekt som krypteras med Microsoft-krypteringsteknik. Dessa tekniker är Azure Rights Management och Microsoft Information Protection (specifikt känslighetsetiketter). Mer information om Microsofts krypteringstekniker finns i [Kryptering](encryption.md). Innehåll som krypteras med krypteringsteknik från tredje part stöds inte. Det går till exempel inte att förhandsgranska eller exportera innehåll som krypterats med tekniker som inte är från Microsoft.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>eDiscovery-aktiviteter som stöder krypterade objekt

I följande tabell identifieras de uppgifter som stöds som kan utföras i Microsoft 365 eDiscovery-verktyg på krypterade filer som bifogats i e-postmeddelanden och krypterade dokument i SharePoint och OneDrive. De här uppgifterna som stöds kan utföras på krypterade filer som uppfyller villkoren för en sökning. Värdet för `N/A` anger att funktionen inte är tillgänglig i motsvarande eDiscovery-verktyg.

|eDiscovery-uppgift  |Innehållssökning  |Core eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|Söka efter innehåll i krypterade filer i e-post och webbplatser<sup>1</sup>     |Ja      |Ja      |Ja      |
|Förhandsgranska krypterade filer som bifogats till e-post     |Ja      |Ja     |Ja       |
|Förhandsgranska krypterade dokument i SharePoint och OneDrive|Nej      |Nej    |Ja       |
|Granska krypterade filer i en granskningsuppsättning    |EJ TILLÄMPLIGT      |EJ TILLÄMPLIGT        | Ja        |
|Exportera krypterade filer som bifogats till e-post    |Ja       |Ja  |Ja    |
|Exportera krypterade dokument i SharePoint och OneDrive    |Nej       |Nej  |Ja    |
|||||

> [!NOTE]
> <sup>1</sup> Krypterade filer som finns på en lokal dator (och inte lagras på en SharePoint eller OneDrive-webbplats) indexeras inte för eDiscovery. Det innebär att om en krypterad lokal fil bifogas i ett e-postmeddelande returneras filen inte med en nyckelordssökningsfråga, även om filen innehåller nyckelord som matchar sökfrågan. Men e-postmeddelanden med lokal krypterad fil kan returneras med en eDiscovery-sökning om en e-postegenskap (till exempel skickat, avsändare, mottagare eller ämne) matchar sökfrågan.

### <a name="decryption-limitations-with-sensitivity-labels"></a>Dekrypteringsbegränsningar med känslighetsetiketter

eDiscovery stöder inte krypterade filer i SharePoint och OneDrive när en känslighetsetikett som tillämpat krypteringen konfigureras med någon av följande inställningar:

- Användare kan tilldela behörigheter när de tillämpar etiketten manuellt på ett dokument. Det här kallas ibland för *användardefinierade behörigheter.*

- Användaråtkomst till dokumentet har en utgångsinställning som är inställd på ett annat värde än **Aldrig.**

Mer information om de här inställningarna finns i avsnittet "Konfigurera krypteringsinställningar" i Begränsa åtkomst till innehåll genom att använda känslighetsetiketter [för att tillämpa kryptering.](encryption-sensitivity-labels.md#configure-encryption-settings)

Dokument som krypterats med tidigare inställningar kan fortfarande returneras med en eDiscovery-sökning. Det här kan inträffa när en dokumentegenskap (t.ex. titel, författare eller ändringsdatum) matchar sökvillkoren. Även om dessa dokument kan ingå i sökresultat kan de inte förhandsgranskas eller granskas. De här dokumenten förblir också krypterade när de exporteras i Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>Krav för dekryptering i eDiscovery

Du måste ha tilldelats rollen RMS-dekryptering för att kunna förhandsgranska, granska och exportera filer som är krypterade med Microsoft-krypteringsteknik. Du måste också tilldelas den här rollen för att granska och fråga krypterade filer som läggs till i en granskningsuppsättning Advanced eDiscovery.

Den här rollen är tilldelad som standard till  rollgruppen för eDiscovery Manager på sidan Behörigheter i Office 365 säkerhets- & efterlevnadscenter. Mer information om RMS-dekrypteringens roll finns i [Tilldela eDiscovery-behörigheter.](assign-ediscovery-permissions.md#rms-decrypt)
