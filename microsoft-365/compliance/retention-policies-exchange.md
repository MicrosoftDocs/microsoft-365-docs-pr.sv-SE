---
title: Mer information om kvarhållning för Exchange
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Mer information om hur kvarhållning för Exchange fungerar.
ms.openlocfilehash: 29a07ca9c819939c32f9ec13205a821a45e03883
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985438"
---
# <a name="learn-about-retention-for-exchange"></a>Mer information om kvarhållning för Exchange

Informationen i den här artikeln kompletterar [Mer information om kvarhållning](retention.md) eftersom den innehåller specifik information för Exchange.  För övriga arbetsbelastningar finns information i:

- [Mer information om kvarhållning för SharePoint och OneDrive](retention-policies-sharepoint.md)
- [Mer information om kvarhållning för Microsoft Teams](retention-policies-teams.md)
- [Mer information om kvarhållning för Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>Vad ingår för kvarhållning och borttagning

Följande Exchange-objekt från användarpostlådor samt delade postlådor kan behållas och tas bort med hjälp av kvarhållningsprinciper och kvarhållningsetiketter: e-postmeddelanden (inklusive mottagna meddelanden, utkast och skickade meddelanden) med bifogade filer, uppgifter när de har ett slutdatum och anteckningar. 

Kalenderobjekt som har ett slutdatum stöds för kvarhållningsprinciper, men stöds inte för kvarhållningsetiketter.

Kontakter och alla uppgifter och kalenderobjekt som inte har ett slutdatum stöds inte.

Andra objekt som lagras i en postlåda, till exempel Skype- och Teams-meddelanden, ingår inte i kvarhållningsprinciper eller -etiketter för Exchange. Dessa objekt har sina egna kvarhållningsprinciper.

## <a name="how-retention-works-for-exchange"></a>Så fungerar kvarhållning för Exchange

Både en postlåda och en offentlig mapp använder [mappen Återställningsbara objekt](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) för att behålla objekt. Bara personer som har tilldelats eDiscovery-behörigheter kan visa objekt i en annan användares mapp för Återställningsbara objekt.
  
När en person tar bort ett meddelande i en annan mapp än mappen Borttaget flyttas meddelandet som standard till mappen Borttaget. När en person tar bort ett objekt i mappen Borttaget flyttas meddelandet till mappen Återställningsbara objekt. En användare kan dock ta bort ett objekt temporärt (Skift+Delete) i en mapp, vilket kringgår mappen Borttaget och flyttar objektet direkt till mappen Återställningsbara objekt.
  
När du tillämpar inställningarna för kvarhållning på Exchange-data utvärderar ett tidsinställt jobb regelbundet objekt i mappen Återställningsbara objekt. Om ett objekt inte stämmer överens med reglerna för minst en kvarhållningsprincip eller kvarhållningsetikett för att kvarhålla objektet, tas objektet bort permanent från mappen Återställningsbara objekt.

> [!NOTE]
> På grund av [första principen om kvarhållning](retention.md#the-principles-of-retention-or-what-takes-precedence)inaktiveras permanent borttagning alltid om samma objekt måste behållas på grund av en annan kvarhållningsprincip eller kvarhållningstagg, eller om det finns eDiscovery som gäller för juridiska skäl eller av juridiska skäl.

Det kan ta upp till sju dagar att köra det tidsinställda jobbet och Exchange-platsen måste innehålla minst 10 MB.
  
När en användare försöker ändra egenskaper för ett postlådeobjekt, t.ex. ämne, brödtext, bifogade filer, avsändare och mottagare, eller datumet då ett meddelande skickades eller togs emot – sparas en kopia av det ursprungliga objektet i mappen Återställningsbara objekt innan ändringen görs. Den här åtgärden inträffar för varje efterföljande ändring. I slutet av kvarhållningsperioden tas kopior i mappen Återställningsbara objekt bort permanent.

När inställningarna för kvarhållning har tillämpats på Exchange-innehåll beror sökvägarna som innehållet tar på om kvarhållningsinställningarna ska behålla och ta bort, endast behålla eller endast ta bort.

När kvarhållningsinställningarna ska behålla och ta bort:

![Diagram över kvarhållningsflödet i e-post och gemensamma mappar](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Om objektet ändras eller tas bort permanent** av användaren (antingen SKIFT+DELETE eller borttaget från Borttagna objekt) under kvarhållningsperioden: Objektet flyttas (eller kopieras vid redigering) till mappen Återställningsbara objekt. Där körs ett tidsinställt jobb regelbundet och identifierar objekt vars kvarhållningsperiod har upphört att gälla och dessa objekt tas bort permanent inom 14 dagar från det att kvarhållningsperioden upphört. Observera att 14 dagar är standardinställningen, men det kan konfigureras upp till 30 dagar.

2. **Om objektet inte ändras eller tas bort** under kvarhållningsperioden: Samma process körs regelbundet på alla mappar i postlådan och identifierar objekt vars kvarhållningsperiod har gått ut och de objekten tas bort permanent inom 14 dagar efter att kvarhållningsperioden har gått ut. Observera att 14 dagar är standardinställningen, men det kan konfigureras upp till 30 dagar. 

När inställningarna för kvarhållning endast ska behålla eller endast ta bort, är innehållssökvägarna varianter av kvarhålla eller ta bort:

### <a name="content-paths-for-retain-only-retention-settings"></a>Innehållssökvägar för kvarhållningsinställningar för endast kvarhållning

1. **Om objektet ändras eller tas bort** under kvarhållningsperioden: En kopia av det ursprungliga objektet skapas i mappen Återställningsbara objekt och bevaras till slutet av kvarhållningsperioden, när kopian i mappen Återställningsbara objekt tas bort permanent inom 14 dagar efter att objektet upphört. 

2. **Om objektet inte ändras eller tas bort** under kvarhållningsperioden: Ingenting händer före och efter kvarhållningsperioden, objektet förblir på sin ursprungliga plats.

### <a name="content-paths-for-delete-only-retention-settings"></a>Innehållssökvägar för kvarhållningsinställningar för endast borttagning

1. **Om objektet inte tas** under den konfigurerade perioden: I slutet av den konfigurerade perioden i kvarhållningsprincipen flyttas objektet till mappen Återställningsbara objekt. 

2. **Om objektet tas bort** under den konfigurerade perioden: Objektet flyttas direkt till mappen Återställningsbara objekt. Om en användare tar bort objektet därifrån eller tömmer mappen Återställningsbara objekt tas objektet bort permanent. Annars tas objektet bort permanent efter att det legat i mappen Återställningsbara objekt i 14 dagar. 

## <a name="when-a-user-leaves-the-organization"></a>När en användare lämnar organisationen 

Om en användare lämnar organisationen och användarens postlåda ingår i en kvarhållningsprincip blir postlådan en inaktiv postlåda när användarens Microsoft 365-konto tas bort. Innehållet i en inaktiv postlåda omfattas fortfarande av en kvarhållningsprincip som placerades på postlådan innan den inaktiverades, och innehållet är tillgängligt för eDiscovery-sökningar. Mer information finns under [Inaktiva postlådor i Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Konfigurationsvägledning

Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).

Om du är redo att konfigurera en kvarhållningsprincip eller kvarhållningsetikett för Exchange följer du anvisningarna nedan:
- [Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md)
- [Skapa kvarhållningsetiketter och använda dem i appar](create-apply-retention-labels.md)
- [Använda en kvarhållningsetikett för innehåll automatiskt](apply-retention-labels-automatically.md)