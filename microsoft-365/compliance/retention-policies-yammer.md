---
title: Mer information om kvarhållning för Yammer
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
description: Mer information om de kvarhållningsprinciper som gäller för Yammer.
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362300"
---
# <a name="learn-about-retention-for-yammer"></a>Mer information om kvarhållning för Yammer

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Den här funktionen är i förhandsversion och kan komma att ändras.

Informationen i den här artikeln kompletterar [Mer information om kvarhållning](retention.md) eftersom den innehåller specifik information för Yammer.

För andra arbetsbelastningar, se:

- [Mer information om kvarhållning för SharePoint och OneDrive](retention-policies-sharepoint.md)
- [Mer information om kvarhållning för Microsoft Teams](retention-policies-teams.md)
- [Lär dig mer om kvarhållning för Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Vad omfattas för kvarhållning och borttagning

Följande Yammer-objekt kan behållas och tas bort med kvarhållningsprinciper för Yammer: Communitymeddelanden och användarmeddelanden.

Reaktioner från andra i form av uttryckssymboler tas inte med i dessa meddelanden.

## <a name="how-retention-works-with-yammer"></a>Så fungerar kvarhållning för Yammer

I det här avsnittet beskrivs hur lagringen och processerna på serverdelen uppfyller dina efterlevnadskrav, och varför de bör verifieras med eDiscovery-verktyg i stället för med de meddelanden som för närvarande visas i Yammer-appen.

Du kan använda en kvarhållningsprincip för att behålla data från community-meddelanden och användarmeddelanden i Yammer samt ta bort dessa meddelanden. Bakom kulisserna används Exchange-postlådor för att lagra data som kopieras från dessa meddelanden. Data från Yammer-användarmeddelanden lagras i en dold mapp i postlådan för varje användare som ingår i användarmeddelandet, och en liknande dold mapp i en gruppostlåda används för community-meddelanden.

Kopior av community-meddelanden kan också lagras i den dolda mappen med användarpostlådor när de @omnämner användare eller meddelar användaren om ett svar. Även om dessa meddelanden kommer från ett community-meddelande innehåller en kvarhållningsprincip för Yammer-användarmeddelanden ofta kopior av community-meddelanden.

De dolda mapparna är inte avsedda att vara direkt tillgängliga för användare eller administratörer, utan för att lagra data som efterlevnadsadministratörer kan söka i med eDiscovery-verktyg.

> [!IMPORTANT]
> Eftersom kopior av community-meddelanden också kan lagras i användarpostlådor kan en kvarhållningsprincip med en borttagningsåtgärd för Yammer-användarmeddelanden resultera i att det ursprungliga communitymeddelandet inte längre visas för användare i Yammer-appen.
> 
> En kopia av det ursprungliga meddelandet är dock fortfarande tillgänglig i den dolda mappen i gruppostlådan för communityn och är tillgänglig med eDiscovery-sökningar i efterlevnadssyfte.

Yammer-meddelanden påverkas inte av kvarhållningsprinciper som har konfigurerats för Exchange-postlådor. Även om Yammer-meddelanden lagras i Exchange omfattas dessa Yammer-data endast av en kvarhållningsprincip som är konfigurerad för platserna **Community-meddelanden i Yammer** och **Användarmeddelanden i Yammer**.

> [!NOTE]
> Om en användare ingår i en aktiv kvarhållningsprincip som behåller Yammer-data och du tar bort postlådan för en användare som ingår i den principen, konverteras postlådan till en [inaktiv postlåda](inactive-mailboxes-in-office-365.md) för att Yammer-datan ska behållas. Om du inte behöver behålla Yammer-datan för användaren exkluderar du användarkontot från kvarhållningsprincipen innan du tar bort postlådan.

När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden, utvärderar ett tidsinställt jobb från Exchange-tjänsten regelbundet objekt i den dolda mappen där dessa Yammer-meddelanden lagras. Det tidsinställda jobbet tar upp till sju dagar att köra. När kvarhållningsperioden för objekten har upphört flyttas de till mappen SubstrateHolds. Det är en dold mapp som finns i varje användar- eller gruppostlåda där ej permanent borttagna objekt lagras innan de tas bort permanent.

> [!NOTE]
> På grund av [första principen om kvarhållning](retention.md#the-principles-of-retention-or-what-takes-precedence)inaktiveras permanent borttagning alltid om samma objekt måste behållas på grund av en annan kvarhållningsprincip, eller om det finns eDiscovery som gäller för juridiska skäl eller av juridiska skäl.

När en kvarhållningsprincip har konfigurerats för Yammer-meddelanden beror sökvägarna till innehållet på om kvarhållningsprincipen ska behålla och sedan ta bort, endast behålla eller endast ta bort.

När kvarhållningsprincipen ska behålla och sedan ta bort:

![Diagram med kvarhållningsflöde för Yammer-meddelanden](../media/yammerretentionlifecycle.png)

För de två sökvägarna i diagrammet:

1. **Om ett Yammer-meddelande redigeras eller tas bort** av användaren under kvarhållningsperioden, kopieras det ursprungliga meddelandet omedelbart (om det redigeras) eller flyttas (om det tas bort) till mappen SubstrateHolds. Meddelandet lagras där tills kvarhållningsperioden upphör och meddelandet tas bort permanent.

2. **Om ett Yammer-meddelande inte tas bort** och för aktuella meddelanden efter redigering, flyttas meddelandet till mappen SubstrateHolds efter att kvarhållningsperioden har upphört. Den här åtgärden tar upp till sju dagar från utgångsdatumet. När meddelandet finns i mappen SubstrateHolds tas det omedelbart bort permanent. 

> [!NOTE]
> Meddelanden i mappen SubstrateHolds är sökbara med eDiscovery-verktyg. Tills meddelandena tas bort permanent (i mappen SubstrateHolds) förblir de sökbara med eDiscovery-verktyg.

När kvarhållningsprincipen endast ska behålla eller endast ta bort, är innehållssökvägarna varianter av att behålla eller ta bort.

### <a name="content-paths-for-retain-only-retention-policy"></a>Innehållssökvägar för kvarhållningsprincip som endast behåller

1. **Om ett Yammer-meddelande redigeras eller tas bort**: En kopia av det ursprungliga meddelandet skapas omedelbart i mappen SubstrateHolds och behålls där tills kvarhållningsperioden upphör. Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.

2. **Om Yammer-meddelandet inte ändras eller tas bort** och för aktuella meddelanden efter redigering under kvarhållningsperioden: Ingenting händer före och efter kvarhållningsperioden, meddelandet finns kvar på sin ursprungliga plats.

### <a name="content-paths-for-delete-only-retention-policy"></a>Innehållssökvägar för kvarhållningsprincip som endast tar bort

1. **Om Yammer-meddelandet inte tas bort** under kvarhållningsperioden: Meddelandet flyttas till mappen SubstrateHolds efter kvarhållningsperioden. Den här åtgärden tar upp till sju dagar från utgångsdatumet. Meddelandet tas sedan bort permanent från mappen SubstrateHolds omedelbart.

2. **Om Yammer-meddelandet tas bort av användaren** under perioden flyttas objektet omedelbart till mappen SubstrateHolds där det tas bort omedelbart och permanent.


## <a name="messages-and-external-users"></a>Meddelanden och externa användare

Som standard gäller en kvarhållningsprincip för användarmeddelanden i Yammer alla användare i organisationen, men inte för externa användare. Du kan använda en kvarhållningsprincip för externa användare om du använder alternativet **Redigera** för användare som ingår och ange deras konto.

För närvarande stöds inte Azure B2B-gästanvändare.

## <a name="when-a-user-leaves-the-organization"></a>När en användare lämnar organisationen 

Om användare lämnar organisationen och deras Microsoft 365-konto tas bort, lagras deras Yammer-användarmeddelanden som ska behållas i en inaktiv postlåda. Meddelandena finns kvar enligt kvarhållningsprincipen för användaren innan postlådan inaktiverades och innehållet är tillgängligt för eDiscovery-sökningar. Mer information finns i [Inaktiva postlådor i Exchange Online](inactive-mailboxes-in-office-365.md). 

Om användaren har lagrat några filer i Yammer kan du se [motsvarande avsnitt](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) för SharePoint och OneDrive.

## <a name="limitations"></a>Begränsningar

För närvarande finns det en förhandsversion av Yammers kvarhållningsprinciper och vi arbetar kontinuerligt med att optimera kvarhållningsfunktionen. Under tiden bör du vara medveten om följande begränsning när du använder kvarhållning för Yammer community-meddelanden och användarmeddelanden:

- När du väljer **Redigera** för platsen **Användarmeddelanden i Yammer** kan du se gäster och användare utan postlåda. Kvarhållningsprinciperna är inte avsedda för de här användarna, så välj dem inte.

## <a name="configuration-guidance"></a>Konfigurationsvägledning

Om du inte är bekant med att konfigurera kvarhållning i Microsoft 365 kan du läsa mer i [Komma igång med kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md).

Om du är redo att konfigurera en kvarhållningsprincip för Yammer kan du läsa [Skapa och konfigurera kvarhållningsprinciper](create-retention-policies.md).