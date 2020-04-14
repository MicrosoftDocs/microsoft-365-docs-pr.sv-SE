---
title: Överföra en Microsoft 365 Business CSP-prenumeration
description: Ta reda på hur du kan överföra en Microsoft 365 Business CSP-prenumeration från förhandsversion till allmän tillgänglighet (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, csp-prenumeration på övergång
ms.date: 11/01/2017
ms.openlocfilehash: 0a30d80ad5217868fec81866ab1dc41013917e99
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504116"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Överföra en Microsoft 365 Business CSP-prenumeration

Om du har en Microsoft 365 Business Preview CSP-prenumeration följer du den här guiden för att ta reda på hur du kan överföra din befintliga förhandsprenumeration till Microsoft 365 Business GA (allmän tillgänglighet).

**Så här överför du en förhandsprenumeration till GA**

1. Logga in <a href="https://partnercenter.microsoft.com" target="_blank">på Partner Center</a>.
2. Välj **Kunder**på instrumentpanelen och leta sedan reda på och välj företagsnamn.

    Teckningarna för bolaget kommer att listas.

    ![Kundens prenumerationer i Partner center](../../media/pc_customer_subscriptions_1.png)
    
3. På företagets sida **Prenumerationer** väljer du **Lägg till prenumeration**.
4. På sidan **Ny prenumeration** väljer du **Småföretag** och väljer sedan **Microsoft 365 Business** i listan.
5. Lägg till antalet licenser och välj sedan **Nästa: Granska** om du vill granska prenumerationen och välj sedan **Skicka**.

    ![Granska den nya prenumerationen på Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    **De licensbaserade prenumerationerna** visar **Microsoft 365 Business Preview** och Microsoft **365 Business**. Du stänger av förhandsprenumerationen nästa gång.

6. Välj **Förhandsversionen av Microsoft 365 Business**.
7. På sidan Förhandsgranska företag i **Microsoft 365** väljer du **Pausad** om du vill avbryta förhandsversionen av förhandsversionen.

    ![Stänga av Microsoft 365 Business Preview-prenumerationen](../../media/pc_customer_m365bpreview_suspend.png)

8. Välj **Skicka** för att bekräfta.

    På sidan **Prenumerationer** bekräftar du att statusen för förhandsversionen av **Microsoft 365 Business** visar **pausad**.

    ![Bekräfta att prenumerationsstatusen för förhandsversionen är avstängd](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Du kan också validera licensavtalet. Gör så här:
    1. Välj **Användare och licenser** på företagets sida **Prenumerationer.**
    2. Välj en användare på sidan **Användare och licenser.**
    3. På användarens sida kontrollerar du avsnittet **Tilldela licenser** och bekräftar att microsoft **365 Business**visas .

        ![Bekräfta att Microsoft 365 Business-licensen har tilldelats användaren](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Påverkan på kunder och användare under och efter övergången

Det finns ingen inverkan på kunder och användare under övergången och efter övergången.

## <a name="impact-to-customers-who-dont-transition"></a>Påverkan på kunder som inte övergår

I följande tabell sammanfattas effekten för kunder som inte övergår från en Microsoft 365 Business Preview-prenumeration till en Microsoft 365 Business-prenumeration.

|       | T-0 till T+30     | T+30 till T+60 | T+60 till T+120 | Bortom T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Statligt** | I respitperiod | Löpt ut      | Inaktiverad      | Avetablerade |
| **Tjänstens påverkan**                                                        |
| **Administratörsportal för Microsoft 365 Business** | Ingen påverkan på funktionaliteten | Ingen påverkan på funktionaliteten | Kan lägga till/ta bort användare, köpa prenumerationer.</br> Det går inte att tilldela/återkalla licenser. | Kundens prenumeration och alla data raderas. Admin kan hantera andra betalda prenumerationer. |
| **Office-program**                         | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Läget för nedsatt funktionalitet går in i läget Förminskad funktionalitet.</br> Användare kan bara visa filer. | Läget för nedsatt funktionalitet går in i läget Förminskad funktionalitet.</br> Användare kan bara visa filer. |
| **Molntjänster (SharePoint Online, Exchange Online, Skype, Teams med mera)** | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Slutanvändare och administratörer har ingen åtkomst till data i molnet. | Kundens prenumeration och alla data raderas. |
| **EM+S-komponenter** | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetseffekter vid prenumerationens utgång och](#mobile-device-impacts-upon-subscription-expiration) Windows [10-datorns effekter vid prenumerationens utgång](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetseffekter vid prenumerationens utgång och](#mobile-device-impacts-upon-subscription-expiration) Windows [10-datorns effekter vid prenumerationens utgång](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Windows 10 Företag** | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetseffekter vid prenumerationens utgång och](#mobile-device-impacts-upon-subscription-expiration) Windows [10-datorns effekter vid prenumerationens utgång](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetseffekter vid prenumerationens utgång och](#mobile-device-impacts-upon-subscription-expiration) Windows [10-datorns effekter vid prenumerationens utgång](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Azure AD-inloggning på en Windows 10-dator** | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin-påverkan</br> Ingen inverkan på slutanvändaren | När klienten har tagits bort kan en användare endast logga in med lokala autentiseringsuppgifter. Avbildning på nytt om det inte finns några lokala autentiseringsuppgifter. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Mobil enhet påverkar prenumerationens utgång

I följande tabell sammanfattas effekten på apphanteringsprinciperna på mobila enheter.

|                            | Fullt licensierad upplevelse                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ta bort arbetsfiler från en inaktiv enhet** | Arbetsfiler tas bort efter valda dagar | Arbetsfiler finns kvar på användarens personliga enheter |
| **Tvinga användare att spara alla filer i OneDrive för företag** | Arbetsfiler kan bara sparas i OneDrive för företag | Arbetsfiler kan sparas var som helst |
| **Kryptera arbetsfiler** | Arbetsfiler krypteras | Arbetsfiler är inte längre krypterade.</br> Säkerhetsprinciper tas bort och Office-data om appar tas bort. |
| **Kräv PIN-kod eller fingeravtryck för att komma åt Office-appar** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Återställ PIN-kod när inloggningen misslyckas** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Kräv att användare loggar in igen efter att Office-programmen har varit inaktiva** | Inloggning krävs | Ingen inloggning krävs |
| **Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter** | Arbetsfiler kan inte nås på jailbroken/rooted-enheter | Arbetsfiler kan nås på jailbroken/rooted-enheter |
| **Tillåt användare att kopiera innehåll från Office-appar till personliga appar** | Kopiera/klistra in begränsade till appar som är tillgängliga som en del av Microsoft 365 Business-prenumeration | Kopiera/klistra in tillgängligt för alla appar |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10-datorer påverkar prenumerationens utgång

I följande tabell sammanfattas effekten på konfigurationsprinciperna för Windows 10-enheter.

|                            | Fullt licensierad upplevelse                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Skydda datorer från hot med Windows Defender** | Aktivera/inaktiverad är utanför användarkontrollen | Användaren kan aktivera/inaktivera Windows Defender på Windows 10-datorn |
| **Skydda datorer från webbaserade hot i Microsoft Edge** | PC-skydd i Microsoft Edge | Användaren kan aktivera/inaktivera datorskydd i Microsoft Edge |
| **Stäng av enhetsskärmen när den är inaktiv** | Administratör definierar principen för tidsgränsen för skärmtidsintervall | Skärmtidsgränsen kan konfigureras av slutanvändaren |
| **Tillåt användare att hämta appar från Microsoft Store** | Administratör definierar om en användare kan hämta appar från Microsoft Store | Användaren kan ladda ned appar från Microsoft Store när som helst |
| **Tillåt användare att använda Cortana** | Administratör definierar princip för användaråtkomst till Cortana | Använda enheter för att aktivera/inaktivera Cortana |
| **Tillåt användare att ta emot tips och annonser från Microsoft** | Administratör definierar princip för användarmottagning tips och annonser från Microsoft | Användaren kan slå på /av tips och annonser från Microsoft |
| **Tillåt användare att kopiera innehåll från Office-program till personliga program** | Admin definierar principen för att hålla Windows 10-enheter uppdaterade | Användare kan bestämma när Windows ska uppdateras |
