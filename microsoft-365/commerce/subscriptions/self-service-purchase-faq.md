---
title: Vanliga frågor och svar om självbetjäning för köp
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Hitta svar på vanliga frågor om självbetjäning.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333200"
---
# <a name="self-service-purchase-faq"></a>Vanliga frågor och svar om självbetjäning för köp

Köp av självbetjäning ger användarna möjlighet att prova på ny teknik och utveckla lösningar som i slutänden kan vara till förmån för större organisationer. Central inköp och IT-team har tillgång till alla användare som köper och distribuerar självbetjäningslösningar via administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Administratörer kan inaktivera självbetjäning för köp per produkt via PowerShell. Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

Köp via självbetjäning är tillgängligt för Power Platform (Power BI, Power Apps och Power Automate), Project och Visio.

> [!NOTE]
> Självbetjäning är inte tillgängligt i Indien eller för myndighets- eller utbildningskunder. Project och Visio är inte tillgängliga för köp via självbetjäning i Brasilien och Kongo.

## <a name="making-a-self-service-purchase"></a>Köpa självbetjäning

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hur gör en kund ett självbetjäningsköp?

Kunder kan göra ett självbetjäningsköp online från produktwebbplatserna eller från uppmaningar om köp via app. Kunderna ombeds först att ange en e-postadress för att säkerställa att de är en användare i en befintlig Azure Active Directory-klientorganisation (AD). Därefter dirigeras de till att logga in med sina Azure AD-autentiseringsuppgifter. När du har loggat in uppmanas kunden att välja hur många prenumerationer de vill köpa och att tillhandahålla kreditkortsbetalning. När köpet är klart kan de börja använda sin prenumeration. Den som gör inköparen har åtkomst till en begränsad vy av administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> där de kan tilldela licenser till produkten till andra personer i organisationen.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Vilka betalningsalternativ finns för köp via självbetjäning?

Kreditkort är för närvarande det enda tillgängliga betalningssättet. Betalning via invoicing stöds inte.

### <a name="who-can-buy-through-self-service-purchase"></a>Vem kan köpa via självbetjäning?

Alla användare med ett användarkonto som inte är gäst i en hanterad Azure AD-klientorganisation kan göra ett självbetjäningsköp. Självbetjäning för köp är inte tillgängligt för klientorganisationer som är myndigheter eller utbildningsorganisationer. Om det här gäller för din organisation krävs ingen ytterligare åtgärd för att styra självbetjäning för köp av självbetjäning.

Användare i organisationer eller marknader som inte är berättigade till självbetjäning för köp via självbetjäning ser ett meddelande där de uppmanas att kontakta sin IT-administratör.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kan gästanvändare köpa via självbetjäning?

Nej, gästanvändare kan inte genomföra ett självbetjäningköp i en klientorganisation där de är gäst.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kan användare synkroniseras från en lokal Active Directory-köp via självbetjäning köp?

Om en användare har ett aktivt användarkonto i en berättigad Azure AD-klient kan de genomföra ett självbetjäningsköp.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Vem kan självbetjäning som inköpare tilldelar licenser till?

Självbetjäning som gör inköpare kan bara tilldela licenser till användare i samma Azure AD-klientorganisation. Den som gör inköparen har åtkomst till en begränsad vy av administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 för</a> att tilldela licenser. Inköpare kan tilldela licenser till de produkter som de har köpt genom självbetjäning köp, och kan bara tilldela dessa licenser till användare i samma Azure AD-klientorganisation.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Var kan den som gör självbetjäning se och hantera sina köp?

Självbetjäning som inköpare kan hantera sina köp i den begränsade vyn i administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Inköpare kan alltid komma till  administrationscentret från administratörspanelen i startprogrammet som är inbyggt i alla onlineappar för Microsoft 365 och Dynamics. Inköpare kan visa de köp de har gjort, köpa ytterligare prenumerationer på samma tjänst och tilldela licenser för dessa prenumerationer till andra användare i organisationen. Dessutom kan inköpare visa och betala sin faktura, uppdatera sin betalningsmetod och avbryta sin prenumeration.

## <a name="pricing"></a>Priser

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Vad är prissättningen för självbetjäning?

Priser för var och en av produkterna för självbetjäning finns på Microsofts webbplats. Priserna visas också som en del av utcheckningen när användarna gör ett köp via självbetjäning. Dessa priser kan skilja sig från de priser som en organisation betalar när centrala köp eller priser erbjuds via en partner.

### <a name="who-is-responsible-for-payment"></a>Vem är ansvarig för betalningen?

Den person som köper prenumerationen via självbetjäning är den person som faktureras och som ansvarar för betalningen baserat på villkoren och prissättningen för köpet.

## <a name="admin-capabilities"></a>Administratörsfunktioner

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Vilka funktioner har en administratör för köp via självbetjäning?

Administratörer kan visa alla köp som gjorts via självbetjäning i organisationen i administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> De kan se produkten, inköparens namn, prenumerationer som köpts, utgångsdatum, orderhistorik, inköpspris och tilldelade användare för varje självbetjäning köp. I administrationscentret för Power Platform kan administratörer även se inköpskapaciteten för självbetjäning. Om det krävs för organisationen kan administratörer inaktivera självbetjäning för köp per produkt via PowerShell. Administratörer har samma datahanterings- och åtkomstprinciper över produkter som köpts via självbetjäning eller centralt.

Administratörer kan också styra om användarna i organisationen ska kunna göra självbetjäning. Mer information finns i [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hur respekterar Microsoft datastyrning och efterlevnad genom att aktivera självbetjäning för köp?

Administratörer har kontroll över vilka tjänster och produkter som är tillgängliga i deras klientorganisation baserat på deras krav på datastyrning och efterlevnad. Alla datahanterings- och åtkomstprinciper som organisationen har aktiverat gäller för köpta självbetjäningstjänster.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Vem äger produktdata som skapats från köp via självbetjäning?

Data som skapas från produkter som köpts via självbetjäning ägs och kontrolleras av organisationen.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hur kan jag centralisera köp som gjorts genom självbetjäning?

Administratörer kan tilldela befintliga licenser eller köpa ytterligare prenumerationer på självbetjäningsprodukter genom befintliga avtal och priser för användare som tilldelats självbetjäning. När de här centralt köpta licenserna har tilldelats kan administratörer sedan begära att inköparna avbryter sina befintliga prenumerationer.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Var ser administratören köp av självbetjäning?

Globala administratörer och faktureringsadministratörer kan se prenumerationer som köpts via självbetjäning i Fakturering Dina produkter i administrationscentret  >   för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> De kan filtrera produktlistan för att bara visa de prenumerationer som köpts genom central inköp, eller för att inkludera prenumerationer som köpts via självbetjäning.

Administratörer kan se produkten, inköpares namn, prenumeration köpt, utgångsdatum, orderhistorik, inköpspris och tilldelade användare.

## <a name="support-and-training"></a>Support och utbildning

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Förväntas kundernas IT-avdelningar eller partners kunna erbjuda support för produkter som köpts via självbetjäning?

IT-avdelningar och partner förväntas inte erbjuda support för produkter som köpts via självbetjäning. Microsoft tillhandahåller standardsupport för självbetjäning som inköpare.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Använder det kundens Premier-supportärenden om en självbetjäningsinköpare ringer supporten?

Självbetjäningsinköpare använder inte Premier-supportärenden för att få support för sin självbetjäning.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hur förväntas användarna få utbildning om produkter som de köper via självbetjäning?

Omfattande utbildning för användare finns på produktwebbplatserna. Produkterna har guidad utbildning, dokumentation, exempel och starka grupper för att få svar och tips direkt från andra användare.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Vad händer med självbetjäning om en användare lämnar organisationen?

Om personen som ursprungligen köpte självköpsprodukten lämnar organisationen fortsätter giltiga användare att ha full användning av produkten under hela prenumerationen. Prenumerationen förblir aktiv tills den som gör inköparen säger upp den direkt eller en administratör begär att prenumerationen avbryts via kundsupport. Administratörer kan också välja att tilldela en centralt köpt licens för användare av den av inställda prenumerationen.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Vilken är Microsofts partners roll vid självbetjäning?

Partner som har behörigheten delegerad administration kan se köp via självbetjäning i administrationscentret för <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365,</a>precis som en administratör. Partner kan hjälpa en organisation som vill centralisera produkter som köpts via självbetjäning. Partner kan dessutom erbjuda lösningar för att utöka funktionerna för köp av självbetjäning.