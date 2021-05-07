---
title: Ta bort en tidigare anställd – översikt
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ stegen i den här lösningen för att ta bort en tidigare anställd Microsoft 365 och skydda organisationens data.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241742"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Översikt: Ta bort en tidigare anställd och säkra data

En fråga vi ofta får är "Vad ska jag göra för att skydda data och skydda åtkomsten när en anställd lämnar organisationen?" I den här artikeln förklarar vi hur du blockerar åtkomst till Microsoft 365, åtgärder du bör vidta för att skydda dina data och hur du ger andra anställda åtkomst till data.

Titta på en kort video om att ta bort en anställd. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).

Så här hindrar du en anställd från att logga in:

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera rutan bredvid användarens namn och välj sedan **Återställ lösenord**.
3. Ange ett nytt lösenord och välj sedan **Återställ**. (Skicka det inte till dem.)
4. Välj användarens namn för att gå till egenskapsfönstret och välj Initiera ut logga **ut på fliken Konto.** 

> [!NOTE]
> Du måste vara global administratör för att kunna starta ut logga ut.

Inom en timme – eller efter att han eller hon lämnar den Microsoft 365 aktuella sidan de befinner sig på – uppmanas de att logga in igen. En åtkomsttoken är bra i en timme, så tidslinjen beror på hur mycket tid som återstår för den tokenen och om de navigerar från den aktuella webbsidan.

> [!IMPORTANT]
> Vi har numrerat stegen i den här lösningen och du inte behöver slutföra lösningen i exakt ordning, men vi rekommenderar att du utför stegen så här.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör för att slutföra stegen i den här lösningen.

|||
|:-----|:-----|
|**Steg** <br/> |**Varför** <br/> |
|[Steg 1 – Förhindra en tidigare anställd från att logga in och blockera åtkomst Microsoft 365 tjänster](remove-former-employee-step-1.md) <br/> |Då blockeras den tidigare anställda från att logga in Microsoft 365 och hindrar personen från att komma Microsoft 365 tjänster. <br/> |
|[Steg 2 - Spara innehållet i en tidigare anställds postlåda](remove-former-employee-step-2.md) <br/> |Det är användbart för den person som ska ta över den anställdas arbete, eller om det finns tvister. <br/> |
|[Steg 3 - Vidarebefordra en tidigare anställds e-post till en annan anställd eller konvertera till en delad postlåda](remove-former-employee-step-3.md) <br/> |Då kan du hålla den före detta anställdas e-postadress aktiv. Om du har kunder eller partners som fortfarande skickar e-post till den före detta anställdas e-postadress hamnar den hos den person som har tagit över arbetet. <br/> |
|[Steg 4 – Ge en annan anställd tillgång OneDrive och Outlook data](remove-former-employee-step-6.md) <br/> |Om du bara tar bort en användares licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar. <br/><br/> Innan du tar bort kontot bör du ge en annan användare åtkomst OneDrive Outlook användare. Efter att du tagit bort en anställds konto sparas innehållet i OneDrive och Outlook i **30** dagar. Under de 30 dagarna kan du dock återställa användarens konto och få åtkomst till deras innehåll. Om du återställer användarens konto förblir OneDrive och Outlook tillgängligt för dig även efter 30 dagar. <br/> |
|[Steg 5 – Rensa och blockera en tidigare anställds mobila enhet](remove-former-employee-step-4.md) <br/> |Tar bort affärsdata från telefonen eller surfplattan.  <br/> |
|[Steg 6 - Ta bort och radera Microsoft 365 från en tidigare anställd](remove-former-employee-step-7.md) <br/> |När du tar bort en licens kan du tilldela någon annan den. Du kan också radera licensen så att du inte behöver betala för den förrän du anställer någon ny.  <br/><br/> När du tar bort eller raderar en licens sparas användarens gamla e-post, kontakter och kalender i **30 dagar**, och tas sedan bort permanent. Om du tar bort eller raderar en licens, men inte tar bort kontot, kommer innehållet på användarens OneDrive att finnas tillgängligt för dig även efter 30 dagar.  <br/> |
|[Steg 7 – Ta bort en tidigare anställds användarkonto](remove-former-employee-step-7.md) <br/> |Det här tar bort kontot från administrationscentret. Hjälper dig att hålla ordning och reda. <br/> |

## <a name="related-articles"></a>Relaterade artiklar

[Återställa en användare](restore-user.md)
