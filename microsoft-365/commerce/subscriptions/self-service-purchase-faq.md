---
title: Frågor om självbetjänings köp
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Hitta svar på vanliga frågor om självbetjänings köp.
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816931"
---
# <a name="self-service-purchase-faq"></a>Frågor om självbetjänings köp

Självbetjänings köp ger användarna en chans att pröva nya tekniker och utveckla lösningar som slutligen drar nytta av sina större organisationer. Central upphandling och IT-grupper har insyn för alla användare som köper och distribuerar självbetjänings köp lösningar via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret för Microsoft 365</a>. Administratörer kan stänga av självbetjänings köp per produkt med hjälp av PowerShell. Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

Självbetjänings köp är tillgängligt för Power Platform (Power BI, Power app och Power autoautomatisera), Project och Visio.

> [!NOTE]
> Självbetjänings köp är inte tillgängligt i Indien eller för andra institutioner. Project och Visio är inte tillgängliga för självbetjänings köp i Brasilien och demokratiska republiken Kongo.

## <a name="making-a-self-service-purchase"></a>Skapa ett självbetjänings köp

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hur gör en kund ett självbetjänings köp?

Kunderna kan ringa ett självbetjänings Köp online från produkt webbplatserna eller från-program-köp-uppmaningar. Kunderna ombeds att ange en e-postadress för att säkerställa att de är en användare i en befintlig Azure Active Directory-klient. Därefter dirigeras de till att logga in med sina Azure AD-autentiseringsuppgifter. Efter att du har loggat in uppmanas kunden att välja hur många abonnemang de vill köpa och för att tillhandahålla kredit korts betalning. När köpet är klart kan de börja använda sitt abonnemang. Köparen har till gång till en begränsad vy av <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret för Microsoft 365</a> där de kan tilldela licenser till andra personer i organisationen.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Vilka är betalnings alternativen för självbetjänings köp?

För närvarande är kredit kort det enda tillgängliga betalnings sättet. Betalning via fakturering stöds inte.

### <a name="who-can-buy-through-self-service-purchase"></a>Vem kan köpa via eget service köp?

Alla användare med ett användar konto som inte är gäst i en hanterad Azure AD-klient organisation kan göra ett självbetjänings köp. Självbetjänings köp är inte tillgängligt för innehavare som är statliga eller utbildnings organisationer. Om det gäller din organisation måste ingen ytterligare åtgärd vidtas för att kontrol lera självbetjänings köpet.

Användare i organisationer och marknader som inte är berättigade till själv service köp kan se ett meddelande som ber dem kontakta sin IT-administratör.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kan gäst användare köpa via självbetjänings köp?

Nej, gäst användarna kan inte slutföra ett självbetjänings köp i en klient organisation där de är gäst.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kan användare synkroniseras från en lokal Active Directory-köp via självbetjänings köp?

Om en användare har ett aktivt användar konto i en giltig Azure AD-klient organisation kan de slutföra ett självbetjänings köp.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Vem kan självbetjänings köparna tilldela licenser?

Självbetjänings inköpare kan bara tilldela licenser till användare i samma Azure AD-klient organisation. Köparen har till gång till en begränsad vy av <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> för att tilldela licenser. Köparna kan tilldela licenser till de produkter som de har köpt via självbetjänings köp och kan bara koppla dessa licenser till användare i samma Azure AD-klient organisation.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Var är självbetjänings köparen att se och hantera deras inköp?

Självbetjänings inköpare kan hantera deras inköp i begränsad vy i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. Det går alltid att få till gång till administrations centret från **administrations** panelen i program Start programmet i alla Microsoft 365-och Dynamics Online-appar. Köparna kan visa de inköp de har gjort, köpa fler abonnemang till samma tjänst och tilldela licenser för dessa abonnemang till andra användare i organisationen. Dessutom kan köparna Visa och betala sin faktura, uppdatera sin betalnings metod och annullera deras abonnemang.

## <a name="pricing"></a>Priser

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Vad är priset för självbetjänings köp?

Priser för varje produkt för självbetjänings köp finns på Microsofts webbplats. Priser visas också som en del av utcheckningen när användare gör ett självbetjänings köp. Dessa priser kan skilja sig från priserna som en organisation betalar när de köper köp eller priser som erbjuds genom en partner.

### <a name="who-is-responsible-for-payment"></a>Vem är ansvarig för betalning?

Den person som köper abonnemanget via självbetjänings köp är den person som debiteras och vem som ansvarar för betalning baserat på villkoren och priset på inköpet.

## <a name="admin-capabilities"></a>Administratörs funktioner

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Vilka funktioner har en administratör för självbetjänings köp?

Administratörer kan visa alla självbetjänings köp i sin organisation i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. De kan se produkt, köpar namn, inköpta abonnemang, utgångs datum, order historik, inköps pris och tilldelade användare för varje själv service-inköp. I administratörs centret för Power Platform kan administratörer också Visa självbetjäningens inköps kapacitet. Om det behövs för sin organisation kan administratörerna inaktivera självbetjänings köp per produkt med hjälp av PowerShell. Administratörer har samma data hanterings-och åtkomst principer som de produkter som köpts via eget köp eller centralt.

Administratörer kan även kontrol lera om användare i organisationen kan göra självbetjänings köp. Mer information finns i [använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hur använder Microsoft respekt för data styrning och efterlevnad genom att aktivera självbetjänings köp?

Administratörer behåller kontroll över vilka tjänster och produkter som är tillgängliga inom sin klient organisation baserat på deras data styrning och efterföljandekrav. Alla data hanterings-och åtkomst principer som din organisation har aktiverat gäller för tillgängliga självbetjänings tjänster.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Vem äger produkt data från självbetjänings köp?

Data som skapats från produkter som köpts via självbetjänings köp ägs och kontrol leras av organisationen.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hur centraliserar jag inköp via Self-Service-inköp?

Administratörer kan tilldela befintliga licenser eller köpa ytterligare abonnemang för självbetjänings köp produkter genom befintliga avtal och priser för användare tilldelade till självbetjänings köp. När du har tilldelat dessa centralt köpta licenser kan administratörer begära att köparen annullerar sina befintliga abonnemang.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Var kan administratören se själv tjänstens inköp?

Globala och fakturerings administratörer kan se abonnemang som har köpts via självbetjänings köp i **fakturering**av  >  **dina produkter** i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>. De kan filtrera produkt listan för att endast visa vilka abonnemang som har köpts via Central inköp, eller för att inkludera abonnemang som har köpts via eget service-inköp.

Administratörer kan se produkt, köpar namn, inköpt abonnemang, utgångs datum, order historik, inköps pris och tilldelade användare.

## <a name="support-and-training"></a>Support och utbildning

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Förväntar sig kundernas IT-avdelningar eller partners för att stödja produkter som köpts via självbetjänings köp?

IT-avdelningar och-partners förväntas inte tillhandahålla support för produkter som köpts via självbetjänings köp. Microsoft tillhandahåller Standard Support för självbetjänings-och inköpare.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Om ett självbetjänings köp samtal ger support, används kundens Premier Support-händelser?

Självbetjänings inköpare använder inte kundens Premier Support-händelser för att få support för sina självbetjänings köp.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hur förväntar vi användarna att få öva på de produkter de köper via självbetjänings köp?

Omfattande utbildning för användare finns på produkt webbplatserna. Produkterna har guidad inlärning, dokumentation, exempel och starka communities att få svar och tips direkt från andra användare.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Vad händer med självbetjänings köpet om en användare lämnar organisationen?

Om den person som ursprungligen köpte självbetjänings köpet lämnar organisationen, fortsätter giltiga användare att ha full användning av produkten under prenumerationens varaktighet. Abonnemanget är aktivt tills köparen direkt annullerar det eller en administratör begär att prenumerationen ska annulleras via kund support. Administratörer kan även välja att tilldela en centralt avtalad licens till användare av den inställda prenumerationen.

## <a name="partners"></a>Parterna

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Vad är Microsoft-partnerns roll i självbetjänings köp?

Partner som har delegerade administratörs privilegier kan se självbetjänings köp i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a>, precis som en administratör. Partners kan hjälpa till med stöd för en organisation som vill centralisera produkter som köpts via självbetjänings köp. Dessutom kan partners ge lösningar för att utöka funktionerna i ett självbetjänings köp.