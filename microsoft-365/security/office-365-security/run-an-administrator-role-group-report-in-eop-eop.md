---
title: 'Köra en administratörsrollgruppsrapport i EOP '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Administratörer kan lära sig hur du kör en administratörsrollgrupprapport i Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper, Loggar EOP (Microsoft Exchange Online Protection) varje förekomst.
ms.openlocfilehash: d9e7db8accae259b3eb332ce17c52c6749c2bec2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808116"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Köra en administratörsrollgruppsrapport i EOP

 När en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper loggar EOP -loggningar (Exchange Online Protection) varje förekomst. När du kör en administratörsrollgrupprapport i Administrationscentret för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, som ändrade rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes. Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid att slutföra: 2 minuter

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill se vilka behörigheter du behöver läser du avsnittet "Rapporter" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Använda EAC för att köra en administratörsrollgrupprapport

Kör rapport för administratörsrollgruppen för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.

1. I EAC navigerar du till **Granskning** **av efterlevnadshantering** \> och väljer Kör en rapport över **en administratörsrollgrupp**.

2. Välj **startdatum** och **slutdatum**. Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.

3. Om du vill visa ändringarna för en viss rollgrupp klickar du på **Välj rollgrupper**. Markera rollgruppen (eller grupperna) i den efterföljande dialogrutan och klicka på **OK**. Du kan också lämna fältet tomt för att hitta alla ändrade rollgrupper.

4. Klicka på **Sök**.

Om några ändringar hittas med de villkor som du har angett visas de i resultatfönstret. Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du har kört en rapport över en administratörsrollgrupp visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret. Om det inte finns några resultat har inga ändringar av rollgrupper ägt rum inom det angivna datumintervallet. Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör sedan rapporten igen.

## <a name="monitor-changes-to-role-group-membership"></a>Övervaka ändringar i rollgruppsmedlemskap

När medlemmar läggs till eller tas bort från en rollgrupp visar sökresultaten i informationsfönstret att rollgruppsmedlemskapet har uppdaterats och visar de aktuella medlemmarna. Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.

För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata transaktioner i rapporten. Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**

> 1/27/2018 16:43 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb,florencef;pilarp <br> 2/06/2018 10:09 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip <br> 2/19/2018 14:12 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;tonip

I det här exemplet gjorde administratörsanvändarkontot följande ändringar:

- Den 2/06/2018 lade de till användaren tonip.

- Den 2/19/2018 tog de bort användaren.
