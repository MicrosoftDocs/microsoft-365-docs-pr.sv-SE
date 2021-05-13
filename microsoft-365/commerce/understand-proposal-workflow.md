---
title: Förstå arbetsflödet för förslag
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: presharm, jmueller
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Läs mer om förslag som hjälper dig att köpa Produkter och tjänster från Microsoft.
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: 5dece5ccc0cc26b157ae0cc33ec9bb1fe44c44b3
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345088"
---
# <a name="understand-the-proposal-workflow"></a>Förstå arbetsflödet för förslag

Ett förslag är ett formellt erbjudande från Microsoft om att din organisation ska köpa Microsofts produkter och tjänster. Du arbetar direkt med en Microsoft-representant för att fastställa specifika produkter, tjänster och villkor för ditt förslag.

En Microsoft-representant utkast till ett förslag som innehåller de objekt som du och din representant diskuterat. Representanten skickar ett e-postmeddelande med en länk till förslagswebbplatsen. Webbplatsen innehåller förslag som förberetts specifikt för dig och din organisation.

När du får e-postmeddelandet följer du länken till förslagswebbplatsen. När du har loggat in på webbplatsen kan du påbörja granskningsprocessen för förslaget.

## <a name="prerequisites-for-buying-items-with-a-proposal"></a>Krav för att köpa produkter med ett förslag

Innan du kan köpa artiklar till ett förslag måste du ha ett faktureringskonto och ett avtal med Microsoft.

### <a name="billing-account"></a>Faktureringskonto

Du använder ett faktureringskonto för att hantera dina kontoinställningar, fakturor, faktureringsprofiler och produkter och tjänster. Om du inte redan har ett faktureringskonto skapar din Microsoft-representant ett åt dig.
Annars använder de ett befintligt faktureringskonto för din organisation, så länge du har behörighet att använda det faktureringskontot.

Faktureringskontobehörigheter hanteras av faktureringskontots ägare.
Globala administratörer kan tilldela sig själva rollen som faktureringskontoägare och sedan göra andra personer till ägare av faktureringskonto.

Mer information om faktureringskonton finns i [Hantera faktureringskonton.](manage-billing-accounts.md)

### <a name="microsoft-customer-agreement"></a>Microsofts kundavtal

Med Microsofts kundavtal (MCA) kan en organisation köpa Microsofts produkter och tjänster. Mer information finns i [Microsofts kundavtal.](https://www.microsoft.com/en-us/Licensing/how-to-buy/microsoft-customer-agreement)

## <a name="permissions-needed-to-sign-an-agreement-or-pay-for-items"></a>Behörigheter som krävs för att signera ett avtal eller betala för artiklar

Om du inte har en tilldelad roll i faktureringskontot får du den grundläggande läsrollen när du visar förslaget. Med den här rollen kan du visa, men inte vidta någon åtgärd för, förslaget. Du måste ha tilldelats rollen som faktureringskontoägare eller faktureringskontodeltagare innan du kan signera ett avtal eller köpa produkter och tjänster. Din faktureringskontoägare kan tilldela den här rollen till dig.

Mer information om faktureringskontoroller finns i [Förstå åtkomst till faktureringskonton.](manage-billing-accounts.md#understand-access-to-billing-accounts)

Om det här är ett nytt faktureringskonto, och ingen har accepterat ett avtal, blir du automatiskt ägare till faktureringskontot, förutsatt att du:

- Är den person som namnges i förslaget\
    ELLER
- Är redan [Azure Active Directory global administratör](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) för organisationen

## <a name="what-is-the-overall-workflow"></a>Vad är det övergripande arbetsflödet?

Det övergripande arbetsflödet för förslag ser ut så här:

- Din Microsoft-representant skapar ett förslag och skickar en länk till dig i ett e-postmeddelande.
- Du använder länken för att gå till inloggningssidan för förslag.
- Du granskar informationen om din organisation.
- Du granskar förslaget, accepterar MCA:en om det behövs och slutför kassaprocessen.
    > [!IMPORTANT]
    > Du måste ha behörighet att signera en MCA för din organisations räkning. Om du inte har den behörigheten måste någon som måste göra det här steget.
- När utcheckningen är klar får du ytterligare länkar för att konfigurera dina produkter och tjänster.

## <a name="proposal-terms"></a>Förslagsvillkor

Följande tabell innehåller termer och definitioner som visas i ditt förslag och på förslagswebbplatsen.

| **Term** | **Definition** |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Faktureringskonto | Ett konto som används för att hantera dina kontoinställningar, fakturor, betalningsmetoder och produkter. |
| Faktureringsprofil | Information om din organisation som låter dig anpassa vilka artiklar som ingår på fakturan och hur du betalar för fakturor. Faktureringsprofilen innehåller namnet på faktureringskontot, betalningsmetoderna som används för den specifika faktureringsprofilen, kontaktinformation, fakturainställningar och behörigheter som gör att du kan ändra faktureringsprofilen, betala räkningar samt köpa produkter och tjänster. |
| Befintliga avtal | Alla avtal som din organisation redan har på plats med Microsoft. Detta kan innefatta, men är inte begränsat till, företagsavtal, Microsofts & för produkter och tjänster eller Microsofts kundavtal. |
| Microsofts kundavtal (MCA) | Ett avtal som beskriver de allmänna villkoren för kontot som din organisation kan ha med Microsoft. |
| Microsoft-representant | En auktoriserad Microsoft-representant som förbereder ett förslag åt dig och din organisation. |
| Organisation | En juridisk person som använder Microsofts produkter, tekniker eller tjänster. |
| Förbereds av | E-postadressen till den Microsoft-representant som förberett förslaget. |
| Kompletterande villkor | Gäller för den MCA som innehåller termer som är specifika för din organisation. Om du vill acceptera kompletterande villkor, måste du använda DocuSign för att spela in en elektronisk signatur. |

## <a name="step-1-review-organization-information"></a>Steg 1: Granska organisationsinformation

När du har loggat in bör du först granska informationen om din organisation.

### <a name="your-organization"></a>Din organisation

I **avsnittet Din** organisation visas det faktureringskonto som är kopplat till det. Faktureringskontoinformationen hämtas antingen från ett befintligt faktureringskonto eller skapas åt dig av Microsoft-representanten. Om din organisation är anknutna till en annan organisation kan du även se avsnittet **Lead organization** med namn och adress till den organisationen.

Om det är första gången din organisation upprättar en kommersiell relation med Microsoft, och du ännu  inte har signerat en MCA, kontaktar du representanten för att göra ändringar åt dig om informationen **under** din organisation eller leadorganisation är felaktig. När du har accepterat en MCA kan du granska och ändra organisationens adress och kontaktinformation på sidan Faktureringskonton i Microsoft 365 administrationscenter. [](https://go.microsoft.com/fwlink/p/?linkid=2084771) Om organisationens namn ändras öppnar du en tjänstförfrågan för att få den uppdaterad. [Lär dig hur du öppnar en tjänstbegäran](../business-video/get-help-support.md)

### <a name="your-information"></a>Din information

Om du är ny kund anger du namn, e-postadress och telefonnummer under **Din information** och väljer sedan **Spara**. Om du är kund verifierar du att informationen är korrekt. Om du vill göra eventuella korrigeringar väljer **du Redigera**, gör de nödvändiga ändringarna och väljer sedan **Spara**.

När du är klar väljer du **Fortsätt för** att gå vidare till nästa steg.

## <a name="step-2-review-proposal"></a>Steg 2: Granska förslag

Förslaget innehåller information om de punkter som du har diskuterat med din Microsoft-representant. Du kan vidarebefordra e-postmeddelandet med länken till förslaget för att dela det med andra intressenter i organisationen. Alla andra som använder länken har en skrivskyddsvy av förslaget.

Om du vill göra ändringar i förslaget efter granskning kontaktar du din Microsoft-representant.

### <a name="proposal-contents"></a>Förslagsinnehåll

Förslaget innehåller följande information:

| Avsnitt | Beskrivning |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Organisationsnamn | Namnet på den organisation som förslaget förberetts för. |
| Giltigt till-datum | Datumet då erbjudandet förfaller. Om du missar det här utgångsdatumet kontaktar du din Microsoft-representant för att meddela dem att du fortfarande är intresserad av förslaget. |
| Valuta | Den valuta som används för att beräkna kostnaden för artiklar i förslaget. |
| Förbered dig för | Namn, adress, kontakt-e-postadress och telefonnummer för faktureringskontot till den person som begärde förslaget. |
| Förbereds av | E-postadressen till den Microsoft-representant som förberett förslaget. |
| Sammanfattning | Visar delsumma som är kopplad till förslaget. Vid behov visas även den kurs för utländsk valuta (FX) som används för att beräkna kostnader. |
| Förslag på radobjekt | Det här avsnittet innehåller antal, enhetspris och delsumma för alla artiklar som ingår i förslaget. |
| Nästa steg | I det här avsnittet anges vilken åtgärd du måste vidta. |

Om du vill signera en MCA väljer du knappen under **Nästa steg.** Om du måste signera kompletterande villkor tar en länk dig till DocuSign-webbplatsen, där du följer anvisningarna för att signera dokumentet.

När du har signerat alla nödvändiga avtal eller kompletterande villkor väljer du **Gå till kassan.**

## <a name="step-3-checkout"></a>Steg 3: Gå till kassan

Utcheckningssidan innehåller följande avsnitt:

### <a name="sold-to"></a>Såld till

I det här avsnittet visas det faktureringskonto som användes för förslaget. Om du behöver ändra någon information väljer du **länken** Redigera. Du kan också använda länken **Redigera** för att lägga till din organisations skatte-ID. Skatte-ID måste vara relaterat till det land som anges i **avsnittet Såld till.** Om du har ett skatteundantag måste du öppna ett supportbegäran om du vill begära undantag från beskattning.

Mer information om skatte-ID och hur du ansökar om undantag från beskattning finns [i Skatteinformation.](billing-and-payments/tax-information.md)

### <a name="billed-to"></a>Faktureras till

I det här avsnittet visas faktureringsprofilen som används för att fastställa vilka artiklar som ingår på fakturan och hur du betalar dina fakturor. Varje faktureringsperiod får du en separat faktura för varje faktureringsprofil. Du betalar för fakturor med check eller banköverföring eller Azure-förskottsbetalning. Om du inte redan har en faktureringsprofil skapar din Microsoft-representant en åt dig. I kassan kan du välja en annan faktureringsprofil, om du har en, ändra namnet på faktureringsprofilen eller lägga till en P.O. tal. Du kan också skapa en ny faktureringsprofil.

Mer information om faktureringsprofiler finns i [Hantera faktureringsprofiler.](billing-and-payments/manage-billing-profiles.md)

### <a name="proposal-items-in-this-order"></a>Förslag på artiklar i denna order

I det här avsnittet visas en lista över alla objekt som ingår i förslaget. Listan kan innehålla en eller flera av följande kategorier:

- **Kompletterande villkor** En lista över alla som är med i den mca som innehåller villkor för din organisation. Den här listan kan till exempel innehålla HIPAA eller GDPR-villkor.
- **Köp nu** En lista över objekt som du betalar för i kassan i slutet av arbetsflödet för accepterande av förslag.
- **Rabatter (gäller för framtida debiteringar)** En lista med rabatter som du får som en del av förslaget.
- **Ingår** En lista över objekt som ingår som en del av förslagspaketet utan extra kostnad. Vissa av dessa artiklar kan ha en kostnad kopplad till dem i framtiden.

### <a name="summary"></a>Sammanfattning

I det här avsnittet visas antalet artiklar som ska betalas, delsumman, den uppskattade momsen och det totala beloppet för ordern.

Om du vill lägga ordern väljer **du Lägg order** eller Acceptera **&amp; avtals lägg order**.

När du har beställt får du en bekräftelse på att du ska göra nästa steg. Om du har köpt ett Azure-abonnemang är nästa steg att konfigurera ditt faktureringskonto i Azure Portal.

## <a name="step-4-set-up-your-new-billing-account-azure-customers-only"></a>Steg 4: Konfigurera ditt nya faktureringskonto (endast Azure-kunder)

Om du är ny kund och har köpt Azure-produkter som en del av förslaget är nästa steg att skapa ett nytt faktureringskonto. Mer information finns i Konfigurera [ditt faktureringskonto för ett Microsoft-kundavtal.](/azure/cost-management-billing/manage/mca-setup-account)

Om du är en befintlig Azure-kund med en företagsavtal och du loggar in på en MCA för första gången är nästa steg att lära dig mer om ändringarna mellan avtal och hur du utför uppgifter med ditt nya faktureringskonto. Mer information finns i Slutföra [företagsavtal uppgifter i ditt faktureringskonto för ett Microsoft-kundavtal.](/azure/cost-management-billing/manage/mca-enterprise-operations)

## <a name="understand-invoicing"></a>Förstå invoicing

När du checkar ut och slutför din beställning skickas en faktura inom 24–48 timmar. Därefter får du fakturor runt den 5:e i varje månad. Månadsfakturan innehåller avgifter från den föregående månaden. Om du har några krediter för ditt konto dras de av från faktureringsprofilens monetära krediter och tillämpas på fakturasaldot. Det återstående saldot efter att krediter har tillämpats är det förfallna saldot. Du har 30 dagar på dig att betala fakturan från faktureringsdatumet.

Betalningsinstruktioner för vart check- eller banköverföringar ska skickas ingår i PDF-kopian av fakturan. Information om hur du visar eller laddar ned fakturan finns [i Visa din faktura.](billing-and-payments/view-your-bill-or-invoice.md)
