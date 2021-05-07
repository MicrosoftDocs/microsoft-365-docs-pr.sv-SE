---
title: Felsöka eDiscovery-undantag
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Felsöka fel relaterade till juridiska fel som tillämpas på systemer och icke-godtyckliga datakällor i Core eDiscovery.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162668"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>Felsöka eDiscovery-undantag

I den här artikeln beskrivs vanliga problem som kan uppstå med eDiscovery-kvarhåller och hur du löser dem. Artikeln innehåller även rekommenderade metoder för att hjälpa dig att minimera eller undvika dessa problem.

## <a name="recommended-practices"></a>Rekommenderade metoder

För att minska antalet fel som rör eDiscovery-rymmer rekommenderar vi följande tillvägagångssätt:

- Om det fortfarande finns en väntande distribution, med statusen eller , väntar du tills kvarstående fördelning är klar `On (Pending)` innan du gör ytterligare `Off (Pending)` uppdateringar.

- Sammanfoga dina uppdateringar till ett eDiscovery-lager i en enda massbegäran i stället för att uppdatera principen för att behålla flera gånger för varje transaktion. Om du till exempel vill lägga till flera användarpostlådor i en befintlig blockeringsprincip med hjälp av cmdleten [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) kör du kommandot (eller lägger till som ett kodblock i ett skript) så att det bara körs en gång för att lägga till flera användare.

  **Rätt**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Felaktigt**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   I det föregående felaktiga exemplet kör cmdleten fem separata gånger för att slutföra aktiviteten. Mer information om rekommenderade metoder för att lägga till användare i en princip för att lagra finns i [avsnittet Mer information.](#more-information)

- Innan du kontaktar Microsoft Support om problem med eDiscovery-spärrade eDiscovery följer du stegen i avsnittet [Fel/problem:](#errorissue-holds-dont-sync) Innehåller inte synkroniseras för att försöka att spärra distributionen igen. Den här processen löser ofta tillfälliga problem, inklusive interna serverfel.

## <a name="errorissue-holds-dont-sync"></a>Fel/problem: Det går inte att synkronisera spärrar

Om du ser något av följande felmeddelanden när du försätter källinformation och datakällor i förvaring kan du använda lösningsstegen för att felsöka problemet.

> Resurser: Det tar längre tid än förväntat att distribuera principen. Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så kom tillbaka om några timmar.

> Principen kan inte distribueras till innehållskällan på grund av ett tillfälligt problem Office 365 datacentret. Den aktuella principen tillämpas inte på något innehåll i källan, så det påverkar inte den blockerade distributionen. Prova att distribuera principen på nytt för att lösa problemet.

> Det gick tyvärr inte att utföra de begärda ändringarna av principen på grund av ett tillfälligt internt serverfel. Försök igen om 30 minuter.

### <a name="resolution"></a>Lösning

1. Anslut [säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör följande kommando för ett eDiscovery-skal:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Undersök värdet i *parametern Fördelningsdetaljer.* Leta efter fel som följande:

   > Fel: Resurser: Det tar längre tid än förväntat att distribuera principen. Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så kom tillbaka om några timmar.

3. Prova att köra **kommandot Set-CaseHoldPolicy -RetryDistribution** för principen för väntande trafik. till exempel:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>Mer information

- I avsnittet Rekommenderade metoder (Rekommenderade metoder) för flera användare får du information om att systemet blockerar samtidiga uppdateringar av en princip för spärrade konton. Det innebär att när en uppdaterad princip för innehåll är tillämpad på nya innehållsplatser och principen för kvarstående innehåll är väntande, kan inte ytterligare innehållsplatser läggas till i principen för kvarstående innehåll. Här är några saker att tänka på för att hjälpa dig att minimera problemet:
  
  - Varje gång ett väntande tillstånd uppdateras hamnar det omedelbart i ett väntande tillstånd. Status för väntande tillstånd innebär att vänteläget tillämpas på innehållsplatser.
  
  - Om du har ett skript som kör en slinga och lägger till platser för principen en och en (liknande det felaktiga exemplet som visas i avsnittet Rekommenderade metoder) initierar den första innehållsplatsen (till exempel en användarpostlåda) synkroniseringsprocessen som utlöser den väntande statusen. Det innebär att andra användare som läggs till i principen i efterföljande loopar resulterar i ett fel.
  
  - Om organisationen använder ett skript som kör en slinga för att uppdatera innehållsplatser för en princip för körning måste du uppdatera skriptet så att det uppdaterar platser i en enda massåtgärd (som i rätt exempel i avsnittet Rekommenderade metoder).
