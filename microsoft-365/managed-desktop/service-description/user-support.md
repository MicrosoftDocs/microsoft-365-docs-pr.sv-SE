---
title: Användarsupport
description: Förklarar alternativen för kundledd och partnerledd support.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8063e1b0e76241df946a29ef2c5115bc0dc39aad
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363773"
---
# <a name="user-support"></a>Användarsupport

Dina Microsoft Hanterat skrivbord-användare kan få support från din organisation (vi kallar den här "kundledd" support) eller från en vald partner ("partnerledd"-support). Vi strävar efter att ge användarna en enhetlig upplevelse, samtidigt som vi skyddar enheterna med båda supportalternativen. Oavsett vilket alternativ du väljer gäller samma principer: 

- Flexibel integrering av Microsoft Hanterat skrivbord enheter med dina befintliga supportprocesser. 
- Tydliga roller och ansvarsområden mellan supportleverantören, IT-administratörer och Microsoft Hanterat skrivbord 
- [Definierad eskaleringsväg](#workflow-for-support-providers)
- Dokumentation från Microsoft Hanterat skrivbord, tillsammans med en portal där du vid behov kan begära utökad enhetsåtkomst och eskalering till vår supportpersonal.
- Övervakning av hot och åtgärder som tillhandahålls Microsoft Hanterat skrivbord hela dagen varje dag

## <a name="roles-and-responsibilities"></a>Roller och ansvar

För att säkerställa kvaliteten på tjänsten utan att komprometterande säkerhet måste supportleverantören, IT-administratörer och Microsoft Hanterat skrivbord ha olika roller och ansvarsområden.

### <a name="support-provider"></a>Supportleverantör

Vem som tillhandahåller support (antingen du för kundsupport eller en partner för partnerledd) ansvarar för följande:

- Tillhandahålla all användarsupport och teknisk support från första kontakten till lösningen för användaren
- Det här gäller alla serviceavtal för användarsupport som fastställts av din organisation eller i samarbete med den valda supportleverantören
- Utföra specifika felsökningsåtgärder, till exempel begära utökad enhetsbehörighet enligt beskrivningen i [Få hjälp för användare](../working-with-managed-desktop/end-user-support.md)
- Felsöka och åtgärda användarproblem, inklusive:
    - Operativsystem (Windows)
    - Microsoft Apps för företag
    - Webbläsarfunktioner
    - Enhetsproblem
    - Problem med infrastrukturen, till exempel skrivare, drivrutiner och VPN
    - Verksamhetsbaserade program

### <a name="it-admin"></a>IT-administratör

IT-administratören ansvarar för följande objekt:

- Arbeta med supportleverantören för att ange och hantera serviceavtal för användarsupport
- Hantera behörigheter med förhöjd åtkomst för godkänd supportpersonal. Mer information finns i [Aktivera användarsupportfunktioner](../get-started/enable-support.md)
- Om det finns enhetsproblem som påverkar flera användare kan du eskalera dem Microsoft Hanterat skrivbord administratörssupportprocessen. Mer information finns i [administratörssupport för Microsoft Hanterat skrivbord](../working-with-managed-desktop/admin-support.md).
- Dirigera maskinvarurelaterade problem till lämplig leverantör
- Underhålla och skydda inställningar för säkerhetsprincip på Microsoft Hanterat skrivbord enheter genom att förhindra att principerna vi anger ändras.

### <a name="microsoft-managed-desktop"></a>Microsoft Hanterat skrivbord

Som tjänsteleverantör ansvarar vi för följande artiklar:

- Förser med hjälpmedel för utökad enhetsåtkomst och eskalering av problem, inklusive dokumentation
- Hålla den här informationen om rollerna och ansvarsområdena aktuella
- Svara på administratörssupportförfrågningar i enlighet med definitionerna för allvarlighetsgrad
- Övervaka och minska hot för alla registrerade enheter hela dagen varje dag

## <a name="workflow-for-support-providers"></a>Arbetsflöde för supportleverantörer

Oavsett om supporten är kundledd eller partnerledd följer flödet av aktivitet för en användarsupportbegäran den här vägen:

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="När en användare kontaktar supporten fungerar de genom ditt system för nivåpersonal, så som du har utformat. Det är viktigt att utse en grupp supportpersonal som ska ges möjlighet till ökning och eskalering, även kallat supporteskaleringsteamet. För specifika Microsoft Hanterat skrivbord problem kan de eskalera till vårt team. För andra microsoft-problem kan de även dirigeras till din befintliga supportkanal, Unified eller Premier. Maskinvaruproblem bör alltid dirigeras till din etablerade leverantör eller leverantör":::

Att integrera befintliga processer med det här arbetsflödet för Microsoft Hanterat skrivbord är flexibelt, så informationen kan se annorlunda ut. Supportleverantören följer vanligtvis en befintlig nivåbaserad metod eller handoff-metod, och utser då specifika användare som har möjlighet att höja behörigheten eller eskalera problem till Microsoft Hanterat skrivbord Åtgärder. Det är bäst att hålla den här gruppen mindre än det bredare supportteamet.

Om ett användarproblem behöver eskaleras till Microsoft Hanterat skrivbord kan det vara bra att identifiera vilken grupp problemet bör dirigeras till. Vi kan överföra ärenden på rätt sätt, men det sparar tid att dirigera dem till rätt plats från början.

- Problem specifika för Microsoft Hanterat skrivbord (till exempel en princip eller inställning som används av själva tjänsten): eskalera direkt till operationsteamet. Mer information finns i [Få hjälp för användare.](../working-with-managed-desktop/end-user-support.md)
- Maskinvaruproblem: direkt till din maskinvaruleverantör eller leverantör
- Andra problem: eskalera genom befintliga supportkanaler, oavsett om det är en Unified- eller Premier-prenumeration.

## <a name="provided-support-framework"></a>Tillhandahållet supportramverk


### <a name="elevation-portal"></a>Höjdportal 

Eftersom Microsoft Hanterat skrivbord-enheter körs på standardanvändare som standard, kräver vissa uppgifter höjd på behörigheter. Mer information om användarkontokontroll finns i [Användarkontokontroll](/windows/security/identity-protection/user-account-control/user-account-control-overview). För att supportpersonalen ska [](../working-with-managed-desktop/end-user-support.md#elevation-requests) kunna utföra uppgifter medan problem felsökas för användarna ger vi "bara-i-tid" åtkomst till ett administratörskonto. Lösenordet kommer bara åt de du anger och roterar varannan timme.  

Anvisningar om hur du anger åtkomst för användare till den här portalen finns i [Aktivera användarstödfunktioner.](../get-started/enable-support.md)

Information om steg för att skicka en begäran om höjd finns i [Höjdbegäranden](../working-with-managed-desktop/end-user-support.md#elevation-requests).

### <a name="escalation-portal"></a>Eskaleringsportal 

Om ett problem kräver eskalering till Microsoft Hanterat skrivbord operationsteam kan den utsedda supportpersonalen ha liknande supportbegäran som it-administratörer.  

> [!NOTE]
> Endast Sev C-supportbegäranden kan arkiveras på det här sättet. Om du vill ha ett problem som matchar beskrivningen av andra allvarlighetsfall rekommenderar vi att du kontaktar rätt IT-administratör som ska filen. Mer information finns i Definitioner [av allvarlighetsgrad för supportbegäran.](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)

Anvisningar om hur du anger åtkomst för användare till den här portalen finns i [Aktivera användarstödfunktioner.](../get-started/enable-support.md)

Information om hur du skickar en eskaleringsbegäran finns [i Eskaleringsförfrågningar](../working-with-managed-desktop/end-user-support.md#escalation-requests).
