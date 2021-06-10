---
title: E-postsäkerhet med Threat Explorer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Visa och undersöka försök till nätfiske efter skadlig kod.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877902"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>E-postsäkerhet med Threat Explorer i Microsoft Defender för Office 365

I den här artikeln:

- [Visa skadlig programvara som upptäckts i e-post](#view-malware-detected-in-email)
- [Visa nätfiske-URL och klicka på bedömningsdata](#view-phishing-url-and-click-verdict-data)
- [Starta automatisk undersökning och svar](#start-automated-investigation-and-response)

> [!NOTE]
> Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem). De andra två artiklarna i den här serien [är Grunderna i Hotutforskaren](threat-hunting-in-threat-explorer.md) och Hotutforskaren och [Realtidsidentifiering.](real-time-detections.md) 

I den här artikeln förklarar vi hur du visar och undersöker skadlig kod och nätfiskeförsök som identifieras i e-Microsoft 365 säkerhetsfunktionerna. 

**Gäller för**

- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Visa skadlig programvara som upptäckts i e-post

Om du vill se skadlig programvara som upptäckts [](threat-explorer-views.md#email--malware) i e-Microsoft 365 efter teknik använder du vyn E> program för skadlig programvara i Utforskaren (eller identifieringar i realtid). Skadlig programvara är standardvyn, så den kan väljas så fort du öppnar Utforskaren.

1. I Säkerhets- & (), <https://protection.office.com> väljer du **Utforskaren för hantering** av hot \>  **(eller identifieringar i realtid).** (I det här exemplet används Utforskaren.)

   Om du är i den konvergerade Microsoft 365 Defender-portalen <https://security.microsoft.com> () bläddrar du till **E-& för samarbete**  >  **i Utforskaren.**

   Härifrån börjar du med visa, väljer en viss tidsperiod att undersöka (om det behövs) och fokuserar dina filter, enligt [Utforskarens genomgång.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)

2. Välj Skadlig **programvara för** e-post **i visa-menyn.** \> 

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicka **på Avsändare** och välj sedan **Enkel** \> **identifieringsteknik.**

   Dina identifieringstekniker är nu tillgängliga som filter för rapporten.

   > [!div class="mx-imgBorder"]
   > ![Teknik för identifiering av skadlig programvara](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Välj ett alternativ. Välj sedan knappen **Uppdatera** för att använda filtret.

   > [!div class="mx-imgBorder"]
   > ![Vald identifieringsteknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   Rapporten uppdateras för att visa resultat som skadlig programvara upptäckt i e-post med hjälp av det teknikalternativ som du valt. Härifrån kan du göra ytterligare analyser. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Visa nätfiske-URL och klicka på bedömningsdata

Du kan visa nätfiskeförsök via URL:er i e-postmeddelanden, inklusive en lista över URL:er som tillåts, blockerades och åsidosätts. Om du vill identifiera url:er som [klickades Valv måste](safe-links.md) länkarna konfigureras. Kontrollera att du har Valv [principer](set-up-safe-links-policies.md) för klickningsskydd och loggning av klickning genom att Valv Länkar.

Om du vill granska webbadresser i meddelanden och klicka på WEBBADRESSer i [   >  **phish-meddelanden**](threat-explorer-views.md#email--phish) använder du e-postvyn Phish i Utforskaren eller identifieringar i realtid.

1. I Säkerhets- & (), <https://protection.office.com> väljer du **Utforskaren för hantering** av hot \>  **(eller identifieringar i realtid).** (I det här exemplet används Utforskaren.)

2. Välj **E-post**  \> **phish på menyn Visa.**

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för Utforskaren i nätfiskekontext](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicka **på Avsändare** och välj sedan **URL:er Klicka** på \> **Bedömning**.

4. Välj ett eller flera  alternativ, som Blockerad och Blockera  **åsidosätts,** och välj sedan knappen Uppdatera på samma rad som alternativen för att använda filtret. (Uppdatera inte webbläsarfönstret.)

   > [!div class="mx-imgBorder"]
   > ![URL:er och klicka på bedömningar](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Rapporten uppdateras så att två olika URL-tabeller visas på fliken URL under rapporten:

   - **Url:er** är URL:er i de meddelanden som du filtrerat ned till och åtgärden för e-postleverans räknas för varje URL. I e-postvyn för phish innehåller den här listan vanligtvis legitima URL:er. Attacker kan innehålla en blandning av bra och dåliga URL-adresser i sina meddelanden för att försöka få dem levererade, men de gör skadliga länkar mer intressanta. Tabellen med URL:er sorteras efter totalt antal e-postmeddelanden, men den här kolumnen är dold för att förenkla vyn.

   - **De översta klicken** är Valv Länkar-radbrutna WEBBADRESSer som klickades, sorterade efter totalt antal klick. Den här kolumnen visas inte heller för att förenkla vyn. Totalt antal efter kolumn anger antalet Valv klickar på antal bedömningsvärden för varje klickad URL. I e-postvyn är det oftast misstänkta eller skadliga URL-adresser. Men vyn kan innehålla URL:er som inte är hot men som är i phish-meddelanden. URL-klick på olästa länkar visas inte här.

   De två URL-tabellerna visar de viktigaste webbadresserna i nätfiskemeddelanden genom leveransåtgärd och -plats. Tabellerna visar URL-klick som har blockerats eller besökts, trots en varning, så att du kan se vilka potentiella dåliga länkar som visades för användare och att användarna har klickat på dem. Härifrån kan du göra ytterligare analyser. Under diagrammet kan du till exempel se de översta webbadresserna i e-postmeddelanden som har blockerats i organisationens miljö.

   > [!div class="mx-imgBorder"]
   > ![Url-adresser som har blockerats i Utforskaren](../../media/ExplorerPhishClickVerdictURLs.png)

   Välj en URL för att visa mer detaljerad information.

   > [!NOTE]
   > I dialogrutan för utfällningsrutan för URL tas filtreringen av e-postmeddelanden bort för att visa den fullständiga visningen av exponering av URL:en i miljön. På så sätt kan du filtrera efter e-postmeddelanden som du är orolig för i Utforskaren, hitta specifika WEBBADRESSer som är potentiella hot och sedan utöka förståelsen av exponering av URL-adresser i din miljö (via dialogrutan URL-information) utan att behöva lägga till URL-filter i utforskarvyn.

### <a name="interpretation-of-click-verdicts"></a>Tolkning av klickningar

I de utfällliga e-post- eller URL-adresserna, de övre klicken och i våra filtreringsupplevelser visas olika värden för klickning:

- **Ingen:** Det går inte att registrera url-adressens bedömning. Användaren kan ha klickat via URL-adressen.
- **Tillåtet:** Användaren tillåts navigera till URL-adressen.
- **Blockerad:** Användaren blockerades från att navigera till URL-adressen.
- **Väntande bedömning:** Användaren visades en sida som väntar på att detonation.
- **Blockerad åsidosätts:** Användaren blockerades från att navigera direkt till URL-adressen. Men användaren överränder blocket för att navigera till URL-adressen.
- **Väntande bedömning kringgås:** Användaren visades med detonationssidan. Men användaren överränder meddelandet för att få åtkomst till URL-adressen.
- **Fel:** Användaren visades på felsidan eller så uppstod ett fel vid inspelning av bedömningsfelet.
- **Fel:** Ett okänt undantag uppstod vid inspelningen av bedömningsfelet. Användaren kan ha klickat via URL-adressen.

## <a name="start-automated-investigation-and-response"></a>Starta automatisk undersökning och svar

> [!NOTE]
> Funktioner för automatisk undersökning och svar finns i *Microsoft Defender för Office 365 abonnemang 2* och *e5 Office 365.*

[Med automatiserad undersökning och](automated-investigation-response-office.md) svar kan du spara tid och arbete som utförs i säkerhetsåtgärder mot cyberattacker. Förutom att konfigurera aviseringar som kan utlösa en säkerhetsspelbok kan du starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren. Mer information finns i [Exempel: En säkerhetsadministratör utlöser en undersökning från Utforskaren](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="other-articles"></a>Andra artiklar

[Undersöka e-postmeddelanden med sidan E-post entitet](mdo-email-entity-page.md)
