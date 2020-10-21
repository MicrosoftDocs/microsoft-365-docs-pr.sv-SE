---
title: Förstå arbets flödet för förslag
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig mer om förslag som hjälper dig att köpa Microsoft-produkter och-tjänster.
ROBOTS: NOINDEX
ms.openlocfilehash: d0e8c6fd9973573d4e49f7512e4394f7534bd97c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646805"
---
# <a name="understand-the-proposal-workflow"></a>Förstå arbets flödet för förslag

Ett förslag är ett formellt anbud från Microsoft för organisationen för att köpa Microsofts produkter och tjänster. Du arbetar direkt med en Microsoft-representant för att fastställa specifika produkter, tjänster och villkor för ditt förslag.

Ett Microsoft-ombud utkast till ett förslag som innehåller de objekt som du och din representant har diskuterat. Representanten skickar ett e-postmeddelande med en länk till webbplatsen för förslag. Webbplatsen innehåller förslaget för dig och din organisation.

När du har fått e-postmeddelandet kan du följa länken till förslags webbplatsen. När du har loggat in på webbplatsen kan du starta gransknings processen för förslag.

## <a name="prerequisites-for-buying-items-with-a-proposal"></a>Förutsättningar för att köpa artiklar med ett förslag

Innan du kan köpa objekt för ett förslag måste du ha ett fakturerings konto och ett avtal med Microsoft.

### <a name="billing-account"></a>Fakturerings konto

Du använder ett fakturerings konto för att hantera dina konto inställningar, fakturor, fakturerings profiler och produkter och tjänster. Om du inte redan har ett fakturerings konto skapar din Microsoft-representant ett åt dig.
Annars använder de ett befintligt fakturerings konto för din organisation, så länge du har tillstånd att använda fakturerings kontot.

Konto behörigheter för fakturering hanteras av ägaren till fakturerings kontot.
Globala administratörer kan tilldela sig själva rollen som ägare av fakturerings konto och sedan göra andra fakturerings konto ägare.

Mer information om fakturerings konton finns i [hantera fakturerings konton](manage-billing-accounts.md).

### <a name="microsoft-customer-agreement"></a>Microsoft-kundavtal

Med Microsoft Customer Agreement (MCA) kan en organisation köpa Microsofts produkter och tjänster. Mer information finns i [Microsoft Customer Agreement](https://www.microsoft.com/en-us/Licensing/how-to-buy/microsoft-customer-agreement).

## <a name="permissions-needed-to-sign-an-agreement-or-pay-for-items"></a>Behörigheter som krävs för att underteckna ett avtal eller betala för artiklar

Om du inte har en tilldelad roll i fakturerings kontot har du tilldelats rollen grundläggande läsare när du visar förslaget. Med den här rollen kan du Visa, men inte vidta någon åtgärd, för förslaget. Du måste vara tilldelad rollen fakturerings-eller fakturerings konto deltagare innan du kan signera ett avtal eller köpa produkter och tjänster. Du kan tilldela den här rollen till ditt fakturerings konto.

Mer information om fakturerings konto roller finns i [förstå åtkomst till fakturerings konton](manage-billing-accounts.md#understand-access-to-billing-accounts).

Om det är ett nytt fakturerings konto och ingen har godkänt ett avtal blir du automatiskt fakturerings kontots ägare, förutsatt att du:

- Är personen som heter i förslaget \
    ELLER
- Är redan en [Global Azure Active Directory-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) för din organisation

## <a name="what-is-the-overall-workflow"></a>Vad är det övergripande arbets flödet?

Det övergripande förslags arbets flödet ser ut så här:

- Din Microsoft-representant skapar ett förslag och skickar en länk till dig i ett e-postmeddelande.

- Du använder länken för att gå till inloggnings sidan för förslag.

- Du granskar organisationens information.

- Du granskar förslaget, godkänner MCA om det behövs och slutför utcheckningen.

    > [!IMPORTANT]
    > Du måste ha behörighet att signera en MCA åt din organisation. Om du inte har den här myndigheten måste någon som gör det här steget.

- När utcheckningen är klar får du ytterligare länkar för att konfigurera produkter och tjänster.

## <a name="proposal-terms"></a>Villkor för förslag

Följande tabell innehåller termer och definitioner som visas i ditt förslag och på webbplatsen för förslag.

| **Term** | **Definition** |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fakturerings konto | Ett konto som används för att hantera dina konto inställningar, fakturor, betalnings metoder och produkter. |
| Fakturerings profil | Information om din organisation där du kan anpassa vilka objekt som ska ingå i din faktura och hur du betalar för dina fakturor. Fakturerings profilen inkluderar namnet på fakturerings kontot, betalnings metoderna som används för den specifika fakturerings profilen, kontakt information, faktura inställningar och behörigheter som gör att du kan ändra fakturerings profil, betala räkningar och köpa produkter och tjänster. |
| Befintliga avtal | Alla avtal som din organisation redan har på plats med Microsoft. Detta kan inkludera, men är inte begränsat till, ett företags avtal, Microsoft Product & Services-avtal eller Microsoft-kundavtal. |
| Microsoft Customer Agreement (MCA) | Ett avtal som beskriver villkoren för kontot som innehas av din organisation hos Microsoft. |
| Microsoft-representant | En godkänd Microsoft-representant som förbereder ett förslag för dig och din organisation. |
| Organisation | En juridisk person som använder Microsofts produkter, teknologier eller tjänster. |
| För beredd av | E-postadressen till Microsoft-representanten som har bearbetat förslaget. |
| Kompletterande villkor | Ändringar av MCA som innehåller termer som är specifika för din organisation. Om du vill acceptera kompletterande villkor måste du använda in för att spela in en elektronisk signatur. |

## <a name="step-1-review-organization-information"></a>Steg 1: granska organisationsinformation

När du har loggat in är det första du ska granska organisationens information.

### <a name="your-organization"></a>Din organisation

I avsnittet **organisation** visas det konto som är kopplat till det. Fakturerings konto informationen hämtas antingen från ett befintligt fakturerings konto eller skapas för dig av Microsoft-representanten. Om organisationen är ett dotter bolag till en annan organisation kan du också se ett avsnitt om **organisationens** namn och adress.

Om det är första gången din organisation etablerar en kommersiell relation med Microsoft och du ännu **inte har** signerat en MCA kan du kontakta den som **skapade den för** att göra ändringar. När du har godkänt en MCA kan du granska och ändra organisationens adress och kontakt information på sidan [fakturerings konton](https://go.microsoft.com/fwlink/p/?linkid=2084771) i administrations centret för Microsoft 365. Om ditt organisations namn ändras öppnar du en tjänst förfrågan för att uppdatera den. [Lär dig hur du öppnar en tjänst förfrågan](../admin/contact-support-for-business-products.md)

### <a name="your-information"></a>Din information

Om du är en ny kund anger du ditt namn, din e-postadress och ditt telefonnummer under **informationen**och väljer sedan **Spara**. Om du redan är en kund kontrollerar du att informationen är korrekt. Om du vill göra ändringar väljer du **Redigera**, gör nödvändiga ändringar och väljer sedan **Spara**.

När du är klar väljer du **Fortsätt** för att gå vidare till nästa steg.

## <a name="step-2-review-proposal"></a>Steg 2: granska förslag

Förslaget innehåller information om de objekt som du har diskuterat med Microsoft-representanten. Du kan vidarebefordra e-postmeddelandet med förslags länken för att dela den med andra intressenter i organisationen. Alla andra som använder länken har en skrivskyddad vy av förslaget.

Om du vill göra ändringar i förslaget efter granskning, kontaktar du din Microsoft-representant.

### <a name="proposal-contents"></a>Förslags innehåll

Förslaget innehåller följande information:

| Del | Beskrivning |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Organisations namn | Namnet på den organisation som förslaget var bearbetat för. |
| Giltigt till datum | Det datum då förslags erbjudandet upphör att gälla. Om du missar det här utgångs datumet kontaktar du din Microsoft-representant för att tala om att du fortfarande är intresse rad av förslaget. |
| Valuta | Den valuta som används för att beräkna kostnaden för artiklar i förslaget. |
| För beredd för | Fakturerings konto namn, adress, kontaktens e-postadress och telefonnummer för den person som begärde förslaget. |
| För beredd av | E-postadressen till Microsoft-representanten som har bearbetat förslaget. |
| Sammanfattning | Visar delsumma som är associerad med förslaget. Vid behov visas även valuta priset (FX) som används för att beräkna kostnaderna. |
| Förslags poster | Det här avsnittet innehåller kvantitet, enhets pris och delsumma för alla artiklar som ingår i förslaget. |
| Nästa steg | I det här avsnittet visas nödvändig åtgärd. |

Om du vill signera en MCA väljer du knappen under **Nästa steg**. Om du måste signera tilläggs villkor kommer en länk till in webbplats där du följer anvisningarna för att signera dokumentet.

När du har loggat alla nödvändiga avtal eller kompletterande villkor väljer **du gå till kassan**.

## <a name="step-3-checkout"></a>Steg 3: utcheckning

Sidan utcheckning innehåller följande avsnitt:

### <a name="sold-to"></a>Såld till

I det här avsnittet visas det fakturerings konto som används för förslaget. Om du behöver ändra någon information väljer du länken **Redigera** . Du kan också använda länken **Redigera** för att lägga till företagets moms-ID. Moms-ID: t måste vara relaterat till det land som anges i avsnittet **såld till** . Om du har en skatte befrielse måste du öppna ett support ärende för att begära skattebefriad status.

Om du vill veta mer om moms-ID: n och hur du ansöker om skattebefriad-status, se [skatte information](billing-and-payments/tax-information.md).

### <a name="billed-to"></a>Fakturerat till

I det här avsnittet visas den betalnings profil som används för att bestämma vilka artiklar som ska ingå i din faktura och hur du betalar dina fakturor. Varje betalnings cykel får du en separat faktura för varje fakturerings profil. Du betalar för fakturor genom att använda antingen check-eller tråd överföring eller Azure-förskotts betalning. Om du inte redan har en fakturerings profil skapar din Microsoft-representant en åt dig. Vid utcheckning kan du välja en annan fakturerings profil om du har en, ändra namnet på fakturerings profilen eller lägga till en P.O. numeriska. Du kan också skapa en ny fakturerings profil.

Information om fakturerings profiler finns i [hantera fakturerings profiler](billing-and-payments/manage-billing-profiles.md).

### <a name="proposal-items-in-this-order"></a>Förslags poster i den här ordningen

I det här avsnittet visas en lista över alla objekt som ingår i förslaget. Listan kan innehålla en eller flera av följande kategorier:

- **Kompletterande villkor** En lista över eventuella ändringar i MCA som innehåller termer för organisationen. Listan kan till exempel innehålla HIPAA eller GDPR villkor.

- **Köp nu** En lista över artiklar som du betalar för under utcheckningen i slutet av arbets flödet för godkännande av förslag.

- **Rabatter (kopplade till framtida avgifter)** En lista med rabatter som du får som en del av förslaget.

- **Ingår** En lista med objekt som ingår i förslags paketet utan extra avgift. Vissa av dessa objekt kan ha en kostnad som är kopplad till dem i framtiden.

### <a name="summary"></a>Sammanfattning

I det här avsnittet visas antalet artiklar som du betalar för, Delsumma, uppskattad moms och total beloppet för beställningen.

Om du vill placera beställningen väljer du **Lägg** till eller **acceptera avtal & order**.

När du har placerat beställningen får du en bekräftelse med nästa steg. Om du har köpt en Azure-plan är nästa steg att konfigurera ditt fakturerings konto i Azure-portalen.

## <a name="step-4-set-up-your-new-billing-account-azure-customers-only"></a>Steg 4: Konfigurera ditt nya fakturerings konto (endast för Azure-kunder)

Om du är en ny kund och har köpt Azure-produkter som en del av förslaget är nästa steg att skapa ett nytt fakturerings konto. Mer information finns i [Konfigurera ett fakturerings konto för ett Microsoft-kundavtal](https://docs.microsoft.com/azure/cost-management-billing/manage/mca-setup-account).

Om du är en befintlig Azure-kund med ett företags avtal och du loggar en MCA för första gången är nästa steg att lära sig mer om ändringarna mellan avtalen och hur du slutför uppgifter med ditt nya fakturerings konto. Mer information finns i [slutföra uppgifter om ett Microsoft-kundavtal i ditt fakturerings konto](https://docs.microsoft.com/azure/cost-management-billing/manage/mca-enterprise-operations).

## <a name="understand-invoicing"></a>Förstå fakturering

När du har checkat ut och slutfört beställningen skickas en ursprunglig faktura inom 24-48 timmar. Efter det tar du emot fakturor dygnet runt varje månad. Månads fakturan innehåller avgifter från den föregående månaden. Om du har pengar på ditt konto dras de av från din fakturerings profils monetära kredit och läggs till i faktura balansen. Resterande saldo efter betalning är förfallet. Du har 30 dagar på dig från fakturerings datumet för att betala fakturan.

Betalnings anvisningar för var du ska skicka kontroll-eller tråd överföring ingår i PDF-kopian av fakturan. Information om hur du visar eller laddar ned fakturan finns i [Visa din](billing-and-payments/view-your-bill-or-invoice.md)faktura.