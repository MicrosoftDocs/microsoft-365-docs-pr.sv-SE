---
title: Köra en rapport om administratörsrollgrupp i EOP
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
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du kör en rapport över en administratörsrollgrupp i Exchange Online Protection (EOP).
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034462"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Köra en rapport om administratörsrollgrupp i EOP

 När en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper loggar EOP (Exchange Online Protection) varje förekomst. När du kör en administratörsrollgruppsrapport i Administrationscenter för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, vem som har ändrat rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes. Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid att slutföra: 2 minuter

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Information om vilka behörigheter du behöver finns i avsnittet "Rapporter" [i funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Använda EAC för att köra en administratörsrollgruppsrapport

Kör rapporten administratörsrollgrupp för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.

1. I EAC navigerar du till **granskning av** **efterlevnadshantering** \> och väljer Kör en **administratörsrollgruppsrapport**.

2. Välj **startdatum** och **slutdatum**. Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.

3. Om du vill visa ändringarna för en viss rollgrupp klickar du på **Välj rollgrupper**. Markera rollgruppen (eller grupperna) i den efterföljande dialogrutan och klicka på **OK**. Du kan också lämna fältet tomt för att hitta alla ändrade rollgrupper.

4. Klicka på **Sök**.

Om några ändringar hittas med hjälp av de angivna villkoren visas de i resultatfönstret. Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du har kört en rapport över administratörsrollgrupper visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret. Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet. Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör rapporten igen.

## <a name="monitor-changes-to-role-group-membership"></a>Övervaka ändringar i rollgruppsmedlemskap

När medlemmar läggs till eller tas bort från en rollgrupp anger sökresultaten i informationsfönstret att rollgruppens medlemskap har uppdaterats och de aktuella medlemmarna visas. Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.

För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten. Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**

> 2018-01-27 16:43 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb,florencef;pilarp <br> 2018-06-06 10:09 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip <br> 2018-02-19 14:12 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;tonip

I det här exemplet har administratörsanvändarkontot gjort följande ändringar:

- Den 2018-02-06 lade de till användarens tonip.

- Den 2018-02-19 tog de bort användarens pilarp.
