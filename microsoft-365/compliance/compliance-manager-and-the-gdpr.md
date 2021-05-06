---
title: Microsoft Compliance Manager och GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager är ett kostnadsfritt arbetsflödesbaserat riskutvärderingsverktyg i Microsoft Service Trust Portal. Med Efterlevnadshanteraren kan du spåra, tilldela och verifiera aktiviteter för regelefterlevnad som är relaterade till Microsofts molntjänster.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "52161494"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager och GDPR

Den allmänna dataskyddsförordningen (GDPR) som tillämpas av EU kan påverka din efterlevnadsstrategi och specifika åtgärder för att hantera användar- och kundinformation som används i Efterlevnadshanteraren.

## <a name="user-privacy-settings"></a>Inställningar för användarsekretess

Vissa bestämmelser kräver att en organisation måste kunna ta bort användarhistorikdata. Efterlevnadshanteraren **ger funktioner för Inställningar** sekretess som administratörer kan:
  
- [Söka efter en användare](#search-for-a-user)
- [Exportera en rapport över kontodatahistorik](#export-a-report-of-account-data-history)
- [Ta bort användardatahistorik](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Söka efter en användare

Så här söker du efter ett användarkonto:
  
1. Ange ett användar-e-postalias (informationen till vänster om @-symbolen) och välj domännamnet i listan med domänsuffix till höger. För organisationer med flera registrerade domäner bör du kontrollera att domännamnssuffixet stämmer.

2. När du har angett användarnamnet korrekt väljer du **Sök**.

3. För användarkonton som inte returneras visas **Användaren hittades inte** på sidan. Kontrollera användarens e-postadressinformation och gör eventuella korrigeringar. Om du vill försöka igen väljer du **Sök**.

4. För användarkonton som returneras ändras texten på knappen från **Sök till** **Rensa**. Detta anger att det returnerade användarkontot är operativsystemskontexten för de ytterligare funktionerna och att dessa funktioner gäller för det här användarkontot.

5. Om du vill rensa sökresultat och söka efter en annan användare väljer du **Rensa**.

## <a name="export-a-report-of-account-data-history"></a>Exportera en rapport över kontodatahistorik

För varje användarkonto som identifieras kan du generera en rapport över beroenden som är kopplade till kontot. Med den här informationen kan du omtilldela öppna uppgifter eller säkerställa åtkomst till tidigare uppladdade bevis.
  
 Så här skapar och exporterar du en rapport:
  
1. Välj **Exportera** om du vill skapa och ladda ned en rapport med Kontrollen Åtgärdshanteraren (Compliance Manager) som för närvarande tilldelats det returnerade användarkontot samt listan med dokument som laddats upp av användaren. Om det inte finns några tilldelade åtgärder eller överladdade dokument visas felmeddelandet "Inga data för den här användaren".

2. Rapporten laddas ned i bakgrunden i det aktiva webbläsarfönstret – om du inte ser ett popup-fönster för nedladdning som du vill kontrollera webbläsarens nedladdningshistorik.

3. Öppna dokumentet för att granska rapportdata.

> [!IMPORTANT]
> Rapportdata är inte en historisk lista som behåller och visar tillståndsändringar i tilldelningshistorik för åtgärdsobjekt. Den genererade rapporten är en ögonblicksbild av kontrollen Åtgärdsobjekt som tilldelats vid den tidpunkt då rapporten körs (datum- och tidsstämpeln skrivs in i rapporten). Alla efterföljande omtilldelar av åtgärdsuppgifter leder till andra ögonblicksbilder av rapportdata om rapporten genereras igen för samma användare.
  
## <a name="delete-user-data-history"></a>Ta bort användardatahistorik

Anger alla kontrollobjekt som tilldelats den returnerade användaren till "inte tilldelat". Anger värdet **uppladdat efter** för dokument som laddats upp av den returnerade användaren till "användare borttagen".
  
Så här tar du bort användarkontots åtgärdsobjekt och dokumentets uppladdningshistorik:
  
1. Välj **Ta bort**.

    En bekräftelsedialogruta visas: " Detta tar bort alla uppgifter i *åtgärdsobjekt och dokumentuppladdningshistoriken för den valda användaren. Den här åtgärden är permanent. Vill du fortsätta?*"

2. Fortsätt genom att **välja OK**, annars välj **Avbryt.**
