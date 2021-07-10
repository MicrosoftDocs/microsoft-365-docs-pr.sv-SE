---
title: Läs mer om Microsofts feedback för din organisation
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs mer om feedback som dina användare kan skicka till Microsoft om Microsoft-produkter.
ms.openlocfilehash: 7b8798847559e84a6ea10079aab010a08d8eaa42
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363937"
---
# <a name="learn-about-microsoft-feedback-for-your-organization"></a>Läs mer om Microsofts feedback för din organisation

Feedback från användare är en viktig signal för Microsoft att förstå användarupplevelsen med Microsoft-produkter. Microsoft värdesätter våra användares åsikter. Användarfeedbacken går direkt till våra tekniker och hjälper oss att forma framtiden för Microsofts produkter och tjänster för alla användare.  
I det här avsnittet hittar du information om vilka typer av feedback som finns, hur vi samlar in den, vad vi samlar in och hur vi hanterar data.

Som administratör kan du hantera feedbacksignalen för din organisation. Vi introducerar en ny uppsättning principinställningar som hjälper dig att hantera insamling av användarfeedback i Microsoft 365 för din organisation. De här principinställningarna hjälper dig att rikta Azure Active Directory grupper och konfigurera feedbackinsamling för din organisation. Användarfeedbacken går direkt till våra tekniker och hjälper oss att forma framtiden för Microsofts produkter och tjänster för alla användare. Du kan läsa mer om de här principinställningarna, vilka program de gäller för och metodtips i Hantera [Microsoft-feedback för din organisation.](../manage/manage-feedback-ms-org.md)

## <a name="feedback-types"></a>Feedbacktyper

### <a name="in-product-feedback"></a>Feedback i produkten

Om användarna använder någon av Microsofts appar och vill ge feedback kan de göra det i de appar de använder. Användarna kan använda de här olika sätten för att dela feedback om produkter och funktioner med oss. Ett av de vanligaste sätten att dela feedback via Microsoft-appar finns under Hjälp-menyn. Om **du väljer**  >  **Hjälpfeedback** i de flesta Microsoft-appar öppnas en feedbacksida där användarna kan skicka feedback till Microsoft.

#### <a name="in-product-feedback-examples"></a>Exempel på feedback i produkten

:::image type="content" source="../../media/In-appfeedbackbackstage.png" alt-text="Skärmbild: Exempel på feedback i produkten":::
:::image type="content" source="../../media/In-appfeedbackwindows.png" alt-text="Skärmbild: Windows exempel på feedback i produkten":::
:::image type="content" source="../../media/TeamsIn-appFeedback.png" alt-text="Skärmbild: Teams exempel på feedback i produkten":::

### <a name="in-product-surveys"></a>Undersökningar i produkten

Användarna kan även betygsätta sin upplevelse och ge ytterligare information om upplevelsen via systeminitierade undersökningsuppnstruktionerna. De här instruktionerna Microsoft 365 produkter då och då. När användarna uppmanas att göra det kan de välja om de vill ge feedback. Undersökningsanvisningarna visas vanligtvis längst ned till höger i programmet. Om användaren bestämmer sig för att ge feedback, avvisa frågan eller låta frågan försvinna på egen hand, kommer användaren inte att se undersökningen igen på ett tag. Microsoft använder även en styrningsprocess för att begränsa antalet systeminitierade undersökningar.  Syftet med styrning är att säkerställa att användarna inte överväldigas av antalet undersökningsuppmaningar.

:::image type="content" source="../../media/feedback-love.png" alt-text="Skärmbild: Exempel på feedbackbegäran i produkten":::

:::image type="content" source="../../media/feedback-excel.png" alt-text="Skärmbild: Exempel på feedbackbegäran i produkten":::

## <a name="what-kind-of-feedback-is-best"></a>Vilken typ av feedback är bäst?

Detaljerad och användbar feedback är viktigt för att göra ändringar och förbättringar i Microsoft-produkter. Om dina användare har problem eller förslag på hur vi kan förbättra dem vill vi gärna höra det. Nedan följer några tips och exempel på användbar feedback som skickas till Microsoft.

- **Kort och beskrivande rubrik**   Beskrivande och specifika rubriker hjälper oss att förstå problemet som rapporteras. Exempel: Excel **Senaste-filer innehåller** inte nyligen tillagda filer OneDrive filer.
- **Fokusera på ett problem i taget**   Ge feedback om ett problem eller rekommendation för ett objekt i taget. Detta säkerställer att rätt loggar och data tas emot vid varje inskickade data och kan tilldelas för uppföljning. Om du har fler än ett ärende kan du skicka en ny feedbackbegäran för varje ärende. Det hjälper oss att identifiera mängden feedback vi får om ett visst problem.
- **Skriv information i rutan Beskrivning**   Information om din enhet, operativsystem och appar tas automatiskt med i varje rapporterad feedback. Lägg till ytterligare information om ett problem som du tycker är viktigt. Ta till exempel med detaljerade steg för att återskapa problemet.

## <a name="how-microsoft-uses-feedback"></a>Så här använder Microsoft feedback

Microsoft använder feedback för att förbättra Microsofts produkter. Vi får feedback från användare i form av frågor, problem, beröm och förslag. Vi ser till att denna feedback kommer tillbaka till rätt team, som använder feedback för att identifiera, prioritera och förbättra Microsofts produkter. Feedback är viktig för våra produktteam för att förstå våra användares upplevelser och påverkar direkt prioriteten för korrigeringar och förbättringar.

### <a name="what-do-we-collect"></a>Vad samlar vi in?

När en användare skickar feedback samlas appinformationen vanligtvis in tillsammans med appklassificeringar och feedbackbeskrivningar.  Om du har aktiverat principen kan vi tillåta att användare skickar skärmbilder och loggar som hjälper oss att felsöka och lösa problem som användaren kan ha på grund av problem. Här är de vanligaste objekten som samlas in eller beräknas.

- **Kommentarer**   Användaren skickade kommentarer på det ursprungliga språket.
- **App**   Microsoft-produkt vi fått feedback från.
- **Skickat den**   Datum och tid då vi fick feedback.
- **Användar-ID**   Azure Active Directory-ID eller e-postadressen för den autentiserade användare som skickar feedback. Anonym feedback tillåts men visas inte i den här vyn.
- **Användarens e-postadress**   Om användaren är ok med att ange sin e-postadress för uppföljning.
- **Språk eller kommentarsspråk**   Det ursprungliga språket som kommentaren skickades på.
- **Feedbacktyp**   Undersökningsfeedback eller feedback via app.
- **Undersökningsfrågor**   Frågor som vi ställde till användaren under undersökningen.
- **Undersökningssvar**   Användarsvar på undersökningsfrågor.
- **Kanal**   Kanal för Microsoft-produkt som är relaterad till feedback.
- **App build**   Versionsnummer för Microsoft-produkt som togs med vid inskicking.
- **Appspråk**   Språk för Microsoft-produkt som fördes in vid sändningen.
- **Bifogade filer**   Hade några bifogade filer (dvs. skärmbilder, filer) samlas in som en del av feedbacken? (Ja/Nej).
- **TenantId**   Om feedback skickas från ett Azure Active Directory konto, som TenantId har kopplats till.

## <a name="how-can-i-see-my-users-feedback"></a>Hur kan jag se min användares feedback?

För att uppfylla Microsofts juridiska åtaganden mot kunder arbetar vi på en ny upplevelse i Administrationscenter för Microsoft 365 som administratörer kan visa, ta bort och exportera feedbackdata för sina organisationer. Som en del av sitt ansvar för datakontroll kommer kunder att äga alla data för användarfeedback och den här funktionen kommer att hjälpa administratörer att ge direkt insyn i sina användares upplevelse av Microsoft 365-produkter och göra det möjligt för användare att ge feedback som en del av en dataämnesbegäran. Globala administratörer och efterlevnadsdataadministratörer kan visa, exportera och ta bort feedback från användare. Alla andra administratörer, liksom läsare, kan visa och exportera feedbackdata men kan inte utföra efterlevnadsrelaterade uppgifter eller se information om vem som publicerat feedbacken (t.ex. användarnamn, e-post eller enhetsnamn). För att få åtkomst till din organisations feedbackdata, loggar du in på Administrationscenter för Microsoft 365 och anpassa navigeringen för att visa hälsonoden. Du kommer åt den här upplevelsen **genom att välja Produktfeedback** under noden Hälsa.

## <a name="data-handling-and-privacy"></a>Datahantering och sekretess

Vi förstår att när du använder våra molntjänster anförtror du oss med en av dina mest värdefulla tillgångar: dina data. Vi ser till att den feedback vi får lagras och hanteras under Microsofts hanteringsregler och att den bara kan användas för godkända användningsområden. Vi använder inte din e-post, chatt, filer eller annat personligt innehåll för att rikta annonser till dig. När vi samlar in data använder vi dem för att förbättra dina upplevelser.

Om du vill veta mer om hur vi skyddar din datas integritet och sekretess och hur vi ser till att de endast används på ett sätt som stämmer överens med dina förväntningar kan du läsa igenom sekretessprinciperna i [Microsoft Säkerhetscenter.](https://www.microsoft.com/trust-center/privacy)
