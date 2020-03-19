---
title: Vanliga frågor om självbetjäning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Hitta svar på vanliga frågor om köp med självbetjäning.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: 4e4ec060a1d782b9c0ddd970906eabebe218ac4f
ms.sourcegitcommit: ab916c216053999c9c4ef4838217e82cd861f23f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42808274"
---
# <a name="self-service-purchase-faq"></a>Vanliga frågor om självbetjäning

> [!NOTE]
> Informationen i den här artikeln gäller endast Microsoft Power Platform -prenumerationer (Power BI, Power Apps och Power Automate).

Självbetjäningsköp är nu tillgängliga för Power Platform i flera länder och regioner.

## <a name="general"></a>Allmänt

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Vilka ändringar tillkännagav Microsoft köp med självbetjäning för Power Platform-produkterna?

Den 19 november gav vi IT-administratörer ett sätt att stänga av självbetjäningsköp per produkt via PowerShell. Mer information om hur du använder den finns i [Använda AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

För att ge mer tid att förbereda sig för den här ändringen uppdaterar vi lanseringen för självbetjäningsköpsfunktioner för Power Platform-produkter som börjar med Power BI den 14 januari för alla kommersiella molnkunder.  

Från och med den 14 januari 2020 kommer självbetjäningsköp, prenumeration och licenshanteringsfunktioner för Power Platform-produkter (Power BI, Power Apps och Power Automate) att vara tillgängliga för kommersiella molnkunder i USA. Självbetjäningsköp ger användarna en chans att prova ny teknik och låter dem utveckla lösningar som i slutändan kommer att gynna deras större organisationer. Den här funktionen kommer inte att vara tillgänglig för hyresgäster i USA som är statliga, ideella eller utbildning, just nu. Centrala upphandlings- och IT-team kommer att ha synlighet för alla användare som köper och distribuerar självbetjäningsköpslösningar via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-administrationscentret</a>och kommer att kunna stänga av självbetjäningsköp per produkt via PowerShell.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Varför lägger Microsoft till ett köpalternativ för självbetjäning för Power Platform-produkterna?

I dagens värld söker slutanvändare och avdelningar i allt högre grad upp och köper tekniklösningar på egen hand. Vi har fått många förfrågningar från dessa kunder om att möjliggöra självbetjäningsköp av Power Platform-produkter. Vi svarar på detta kundbehov samtidigt som vi balanserar behoven hos IT-administratörer, som ofta gånger förlorar synlighet och kontroll när individer inom organisationen antar tredjepartslösningar utan deras vetskap. Med den kommande självbetjäningsfunktionen för Power Platform-produkter kommer IT-administratörer att ha fullständig synlighet för alla självbetjäningsköp som äger rum inom organisationen, och datastyrningsprinciper som fastställts på organisationsnivå kommer att tillfalla abonnemang som köpts via självbetjäning. Administratörer kan också tilldela befintliga licenser, eller köpa ytterligare prenumerationer, av Power Platform-produkter genom befintliga avtal och priser för användare som tilldelats självbetjäningsköp. När administratörer har tilldelats dessa centralt inköpta licenser kan de begära att köparna avbryter sina befintliga prenumerationer. Microsoft undersöker olika sätt att förenkla och effektivisera den här processen för administratörer i framtiden.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>Vilka Power Platform-produkter är tillgängliga för självbetjäningsköp?

Microsoft har lanserat självbetjäningsköp för Power Platform (Power BI, Power Apps och Power Automate) till kunder i USA, med ytterligare marknader blir tillgängliga under de kommande månaderna. Den här funktionen kommer inte att vara tillgänglig för hyresgäster i USA som är statliga, ideella eller utbildning, just nu.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>Kommer köp med självbetjäning att aktiveras för tjänster utöver Power Platform-produkterna?

För närvarande erbjuds endast Power Platform-familjens produkter genom köp av självbetjäning.

## <a name="making-a-self-service-purchase"></a>Göra ett köp med självbetjäning

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Hur gör en kund ett självbetjäningsköp?

Kunderna kommer att kunna göra ett självbetjäningsköp online från webbplatserna Microsoft Power BI, Power Apps och Power Automate. Kunder uppmanas först att ange en e-postadress för att säkerställa att de är användare i en befintlig Azure Active Directory (AD) klient. Då dirigeras de att logga in med hjälp av sina Azure AD-autentiseringsuppgifter. När kunden har loggat in blir kunden ombedd att välja hur många prenumerationer de vill köpa och tillhandahålla kreditkortsbetalning. När köpet är klart kan de börja använda sin prenumeration. Köparen kommer också att kunna komma åt en begränsad vy av <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 administrationscenter</a> där de kan göra det möjligt för andra människor i organisationen att använda produkten.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Vilka är betalningsalternativen för köp med självbetjäning?

För närvarande är kreditkort den enda tillgängliga betalningsmetoden. Betalning via fakturering stöds inte.

### <a name="who-can-buy-through-self-service-purchase"></a>Vem kan köpa genom självbetjäningsköp?

Alla användare med ett användarkonto som inte är gästanvändare kan köpa. Den här funktionen kommer inte att vara tillgänglig för klienter som är statliga, ideella eller utbildning, just nu. Om detta gäller för din organisation krävs för närvarande ingen ytterligare åtgärd för att styra köp med självbetjäning.

Användare i organisationer eller marknader som inte är berättigade till köp med självbetjäning visas ett meddelande där de uppmanas att kontakta sin IT-administratör som de gör idag.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Kan gästanvändare köpa genom köp med självbetjäning?

Nej, gästanvändare kan inte slutföra ett självbetjäningsköp i en klient där de är gäst.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Kan användare synkroniseras från en lokal Active Directory köpa via självbetjäningsköp?

Om en användare har ett aktivt användarkonto i en kvalificerad Azure AD-klient kan de slutföra ett självbetjäningsköp.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Vem kan självbetjäningsköpare tilldela licenser till?

Självbetjäningsköpare kan bara tilldela licenser till användare i samma Azure AD-klient. Köparen kan komma åt en begränsad vy av <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365</a> för att tilldela licenser. De har bara synlighet och kan tilldela licenser till de produkter som de har köpt via självbetjäningsköp, och de kan bara tilldela dessa licenser till användare i samma Azure AD-klient.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Var ser självbetjäningsköparen och hanterar sina inköp?

Självbetjäningsköpare kan hantera sina inköp i den begränsade vyn av <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365</a>. Köpare kan alltid komma åt administrationscentret från **administratörspanelen** i Startprogrammet för Office 365 som är inbyggda i alla Office 365- och Dynamics-onlineappar. De kan visa de inköp de har gjort, köpa ytterligare prenumerationer på samma tjänst och tilldela licenser för dessa prenumerationer till andra användare i organisationen. Dessutom kan köparna visa och betala sin faktura, uppdatera sin betalningsmetod och avbryta sin prenumeration.

**Vy över det begränsade administrationscentret för Microsoft 365 för självbetjäningsköpare:**

![Microsoft 365 admin center skärmdump.](../../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Prissättning

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Vad är prissättningen för köp med självbetjäning?

Priser för var och en av Power Platform-produkterna för självbetjäningsköp kommer att finnas tillgängliga på Microsofts webbplats och visas också som en del av kassaupplevelsen samtidigt som du gör ett köp med självbetjäning. Dessa priser kan skilja sig från de priser en organisation betalar när du gör centrala inköp eller priser som erbjuds via en partner.

### <a name="who-is-responsible-for-payment"></a>Vem är ansvarig för betalningen?

Den person som köper prenumerationen genom köp med självbetjäning faktureras och ansvarar för betalning baserat på villkoren och prissättningen av köpet.

## <a name="admin-capabilities"></a>Administratörsfunktioner

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Vilka funktioner har en administratör för självbetjäningsköp?

Administratörer kan visa alla självbetjäningsköp som gjorts i organisationen i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365</a>. De kan se produkten, köparens namn, köpta prenumerationer, utgångsdatum, orderhistorik, inköpspris och tilldelade användare för varje självbetjäningsköp. I Administrationscentret för Power Platform kan administratörer också visa kapacitet för självbetjäningsköp. Om det behövs för sin organisation kan administratörer stänga av självbetjäningsköp per produkt via PowerShell. Administratörer har samma datahanterings- och åtkomstpolicyer över produkter som köpts via köp med självbetjäning eller centralt.

Administratörer kan också styra om användare i organisationen kan göra självbetjäningsköp. Mer information finns i [Använd AllowSelfServicePurchase för MSCommerce PowerShell-modulen](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Hur respekterar Microsoft datastyrning och efterlevnad genom att aktivera köp av självbetjäning?

Administratörer behåller kontrollen över vilka tjänster och produkter som är aktiverade inom sin klientorganisation baserat på deras datastyrning och efterlevnadskrav. Dessutom gäller alla datahanterings- och åtkomstprinciper, som din organisation har aktiverat, för självbetjäningsköpta aktiverade tjänster.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Vem äger produktdata som skapats från självbetjäningsköp?

Data som skapas från produkter som köpts genom köp av självbetjäning ägs och kontrolleras av organisationen.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Hur centraliserar jag inköpen genom köp med självbetjäning?

Administratörer kan tilldela befintliga licenser eller köpa ytterligare prenumerationer på Power Platform-produkter (Power BI, Power Apps och Power Automate) genom befintliga avtal och priser för användare som tilldelats självbetjäningsköp. När administratörer har tilldelats dessa centralt inköpta licenser kan de begära att köparna avbryter sina befintliga prenumerationer. Microsoft undersöker olika sätt att förenkla och effektivisera den här processen för administratörer i framtiden.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Var ser administratören köp med självbetjäning?

Globala administratörer och faktureringsadministratörer kan se prenumerationer som köps genom köp av självbetjäning i > **Faktureringsprodukter & tjänster** i **Billing** <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365</a> tillsammans med alla andra prenumerationer som köps via central upphandling. De kan filtrera listan till bara de prenumerationer som köps via central upphandling eller inkludera prenumerationer som köpts via självbetjäningsköp.

Administratörer kan se produkten, köparens namn, köpt prenumeration, utgångsdatum, orderhistorik, inköpspriset och tilldelade användare.

## <a name="support-and-training"></a>Stöd och utbildning

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Förväntas kundernas IT-avdelningar eller partners stödja produkter som köpts genom köp av självbetjäning?

IT-avdelningar och partners förväntas inte ge stöd för produkter som köpts genom köp av självbetjäning. Microsoft kommer att ge standardsupport för självbetjäningsköpare.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Om en självbetjäningsköpare anropar support, kommer de att använda kundens Premier-supportincidenter?

Självbetjäningsköpare kommer inte att använda en kunds Premier-supportincidenter för att få support för sina självbetjäningsköp.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Hur förväntas användarna få utbildning på de produkter de köper genom köp av självbetjäning?

Omfattande utbildning för användare finns på webbplatserna Microsoft Power BI, Power Apps och Power Automate. Produkterna har guidat lärande, dokumentation, exempel och starka grupper för att få svar och tips direkt från andra användare.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>Vad händer med ett självbetjäningsköp om en användare lämnar organisationen?

Giltiga användare kommer att fortsätta att ha full användning av självbetjäningsköpet under prenumerationens löptid. Prenumerationen förblir aktiv tills köparen avbryter den direkt eller en administratör begär att prenumerationen ska avbrytas via kundsupport. Administratörer kan också välja att tilldela en centralt köpt licens till användare av den avbrutna prenumerationen.

## <a name="partners"></a>Partner

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Vilken roll spelar Microsofts partner i köp med självbetjäning?

Partner som har delegerade administrationsprivilegier kan se självbetjäningsköp i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret för Microsoft 365</a>, precis som en administratör. Partner kan hjälpa till att stödja en organisation som vill centralisera produkter som köpts genom självbetjäningsköp. Dessutom kan partner erbjuda lösningar för att utöka funktionerna i ett självbetjäningsköp.

## <a name="country-and-region-availability"></a>Land- och regiontillgänglighet

### <a name="in-which-countries-and-regions-can-i-make-a-self-service-purchase"></a>I vilka länder och regioner kan jag göra ett självbetjäningsköp?

Självbetjäningsköp finns i följande länder och regioner: Afghanistan, Åland, Albanien, Algeriet, Amerikanska Samoa, Andorra, Angola, Anguilla, Antarktis, Antigua och Barbuda, Argentina, Armenien, Aruba, Australien, Österrike, Azerbajdzjan, Bahamas, Bahrain, Bangladesh, Barbados, Vitryssland, Belgien, Bulgarien, Belize, Benin, Bermuda, Bhutan, Bolivia, Bonaire, Sint Eustatius och Saba, Bosnien och Hercegovina, Botswana, Bouvet Island, Brasilien, Brittiska Indiska oceanen, Brittisk Jungfruöarna, Brunei, Burkina Faso, Burundi, Cabo Verde, Kambodja, Kamerun, Kanada, Caymanöarna, Centralafrikanska republiken, Tchad, Chile, Kina, Julön, Cocos (Keeling) Islands, Colombia, Komorerna, Kongo, Kongo, Kongo, Kongo, Cooköarna, Costa Rica, Elfenbenskusten, Kroatien, Cypern, Curaçao, Tjeckien, Danmark, Djibouti, Dominikanska republiken, Ecuador, Egypten, El Salvador, Ekvatorialguinea, Eritrea, Estland, Etiopien, Falklandsöarna, Färöarna, Fiji, Finland, Frankrike, Franska Guyana, Franska Polynesien, Franska sydterritorierna, Gabon, Gambia, Georgien, Tyskland, Ghana, Gibraltar, Grönland, Grekland, Grenada, Guadeloupe, Guam, Guatemala, Guernsey, Guinea, Guinea-Bissau, Guyana, Haiti, Heard Island och McDonald islands, Honduras, Hong Kong SAR, Ungern, Island, Indonesien, Irak, Irland, Isle of Man, Israel, Italien, Jamaica, Japan, Jersey, Jordanien, Kazakstan, Kenya, Kiribati, Korea, Kosovo, Kuwait, Kirgizistan, Laos, Lettland, Libanon, Lesotho, Liberia, Libyen, Liechtenstein, Litauen, Luxemburg, Macao SAR, Madagaskar, Malawi, Malaysia, Maldiverna, Mali, Malta, Marshallöarna, Martinique, Mauretanien, Mauritius, Mayotte, Mexiko, Mikronesien, Moldavien, Monaco, Mongoliet, Montenegro, Montserrat, Marocko, Moçambique, Myanmar, Namibia, Nauru, Nepal, Nederländerna, Nya Kaledonien, Nya Zeeland, Nicaragua, Niger, Nigeria, Niue, Norfolk Island, Nordmakedonien, Nordmarianerna, Norge, Oman, Pakistan, Palau, palestinska myndigheten, Panama, Papua Nya Guinea, Paraguay, Peru, Filippinerna, Pitcairnöarna, Polen, Portugal, Puerto Rico, Qatar, Réunion, Rumänien, Ryssland, Rwanda, Saint Barthélemy, Saint Kitts och Nevis, Saint Lucia, Saint Martin, Saint Pierre och Miquelon, Saint Vincent och Grenadinerna, Samoa, San Marino, São Tomé och Príncipe, Saudiarabien, Senegal, Serbien, Seychellerna, Sierra Leone, Singapore, Sint Maarten, Slovakien, Slovenien, Salomonöarna, Somalia, Sydafrika, Sydgeorgien och Sydsandwichöarna, Sydsudan, Spanien, Sri Lanka, St Helena, Uppstigning, Tristan da Cunha, Surinam, Svalbard och Jan Mayen, Swaziland, Sverige, Schweiz, Taiwan, Tadzjikistan, Tanzania, Thailand, Östtimor, Togo, Tokelau, Tonga, Trinidad och Tobago, Tunisien, Turkiet, Turkmenistan, Turks och Caicos öarna, Tuvalu, USA Outlying Islands, USA Outlying Islands, USA Jungfruöarna, Uganda, Ukraina, Förenade Arabemiraten, Storbritannien, USA, Uruguay, Uzbekistan, Vanuatu, Vatikanstaten, Venezuela, Vietnam, Wallis och Futuna, Jemen, Zambia och Zimbabwe.