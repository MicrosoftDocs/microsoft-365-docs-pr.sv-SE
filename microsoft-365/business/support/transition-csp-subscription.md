---
title: Överför en CSP-prenumeration på Microsoft 365 Business 
description: Ta reda på hur du kan överföra en Microsoft 365 Business CSP-prenumeration från förhandsgranskning till GA. 
author: jasongroce
f1.keywords:
- NOCSH
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, csp-prenumeration
ms.date: 11/01/2017
ms.openlocfilehash: 7d8e04a0136f86d3c4bb51208081fd1dcbecf59d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42057364"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Överför en CSP-prenumeration på Microsoft 365 Business

Om du har en CSP-prenumeration i Microsoft 365 Business Preview följer du den här guiden för att ta reda på hur du kan överföra din befintliga förhandsprenumeration till Microsoft 365 Business GA (allmän tillgänglighet).

**Så här överför du en förhandsprenumeration till GA**

1. Logga in på <a href="https://partnercenter.microsoft.com" target="_blank">PartnerCenter</a>.
2. Välj **Kunder**på instrumentpanelen och leta efter och välj sedan företagsnamnet.

    Abonnemangen för företaget kommer att listas.

    ![Kundens prenumerationer i PartnerCenter](../../media/pc_customer_subscriptions_1.png)
    
3. På sidan **Prenumerationer** väljer du **Lägg till prenumeration**.
4. På sidan **Ny prenumeration** väljer du **Småföretag** och väljer sedan **Microsoft 365 Business** i listan.
5. Lägg till antalet licenser och välj sedan **Nästa: Granska** för att granska prenumerationen och välj sedan **Skicka**.

    ![Granska den nya prenumerationen på Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    De **licensbaserade prenumerationerna** visar **förhandsversionen av Microsoft 365 Business Preview** och Microsoft **365 Business**. Du pausar förhandsversionen nästa.

6. Välj **förhandsversion av Microsoft 365 Business**.
7. Välj **Avstängd** på sidan Förhandsversion av **Microsoft 365 Business.**

    ![Avbryta prenumerationen på förhandsversionen av Microsoft 365 Business Preview](../../media/pc_customer_m365bpreview_suspend.png)

8. Välj **Skicka** för att bekräfta.

    På sidan **Prenumerationer** bekräftar du att statusen för förhandsversionen av **Microsoft 365 Business Preview** visar **avstängd**.

    ![Bekräfta att förhandsprenumerationsstatusen är avstängd](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Du kan också validera licensavtalet. Gör så här:
    1. Välj **Användare och licenser** på företagets **prenumerationssida.**
    2. Välj en användare på sidan **Användare och licenser.**
    3. På användarens sida kontrollerar du avsnittet **Tilldela licenser** och bekräftar att det visar **Microsoft 365 Business**.

        ![Bekräfta att Microsoft 365 Business-licensen har tilldelats användaren](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Påverkan på kunder och användare under och efter övergången

Det finns ingen inverkan på kunder och användare under övergången och efter övergången.

## <a name="impact-to-customers-who-dont-transition"></a>Inverkan på kunder som inte övergår

I följande tabell sammanfattas effekten för kunder som inte övergår från en Microsoft 365 Business Preview-prenumeration till en Microsoft 365 Business-prenumeration.

|       | T-0 till T+30     | T+30 till T+60 | T+60 till T+120 | Bortom T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Statligt** | Under respitperioden | Löpt ut      | Inaktiverad      | Avetablerad |
| **Effekter av tjänsten**                                                        |
| **Administratörsportal för Microsoft 365 Business** | Ingen inverkan på funktionaliteten | Ingen inverkan på funktionaliteten | Kan lägga till/ta bort användare, köpa prenumerationer.</br> Det går inte att tilldela/återkalla licenser. | Kundens prenumeration och alla data raderas. Admin kan hantera andra betalda prenumerationer. |
| **Office-appar**                         | Ingen slutanvändare snedslag | Ingen slutanvändare snedslag | Office går in i läget nedsatt funktionalitet.</br> Användare kan bara visa filer. | Office går in i läget nedsatt funktionalitet.</br> Användare kan bara visa filer. |
| **Molntjänster (SharePoint Online, Exchange Online, Skype, Teams med mera)** | Ingen slutanvändare snedslag | Ingen slutanvändare snedslag | Slutanvändare och administratörer har ingen åtkomst till data i molnet. | Kundens prenumeration och alla data raderas. |
| **EM+S-komponenter** | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetspåverkan vid prenumerationens utgångsdatum](#mobile-device-impacts-upon-subscription-expiration) och Windows [10 PC påverkar prenumerationens upphörande](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetspåverkan vid prenumerationens utgångsdatum](#mobile-device-impacts-upon-subscription-expiration) och Windows [10 PC påverkar prenumerationens upphörande](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Windows 10 Företag** | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetspåverkan vid prenumerationens utgångsdatum](#mobile-device-impacts-upon-subscription-expiration) och Windows [10 PC påverkar prenumerationens upphörande](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Kapaciteten tillämpas inte längre.</br> Se [Mobil enhetspåverkan vid prenumerationens utgångsdatum](#mobile-device-impacts-upon-subscription-expiration) och Windows [10 PC påverkar prenumerationens upphörande](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Azure AD-inloggning till en Windows 10-dator** | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | Ingen inverkan på administratören</br> Ingen slutanvändare snedslag | När klienten har tagits bort kan en användare logga in med endast lokala autentiseringsuppgifter. Ombild av enheten om det inte finns några lokala autentiseringsuppgifter. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Mobil enhet påverkar vid abonnemangets utgång

I följande tabell sammanfattas effekten på apphanteringsprinciperna på mobila enheter.

|                            | Fullt licensierad upplevelse                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ta bort arbetsfiler från en inaktiv enhet** | Arbetsfiler tas bort efter valda dagar | Arbetsfiler finns kvar på användarens personliga enheter |
| **Tvinga användare att spara alla filer i OneDrive för företag** | Arbetsfiler kan bara sparas på OneDrive för företag | Arbetsfiler kan sparas var som helst |
| **Kryptera arbetsfiler** | Arbetsfiler krypteras | Arbetsfiler är inte längre krypterade.</br> Säkerhetsprinciper tas bort och Office-data för appar tas bort. |
| **Kräv PIN-kod eller fingeravtryck för att komma åt Office-appar** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Återställ PIN-kod när inloggningen misslyckas** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Kräv att användare loggar in igen efter att Office-appar har inaktiv** | Inloggning krävs | Ingen inloggning krävs |
| **Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter** | Arbetsfiler kan inte nås på jailbroken / rotade enheter | Arbetsfiler kan nås på jailbroken / rotade enheter |
| **Tillåt användare att kopiera innehåll från Office-appar till personliga appar** | Kopiera/klistra in begränsat till appar som är tillgängliga som en del av Microsoft 365 Business-prenumerationen | Kopiera/klistra in tillgängligt för alla appar |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC påverkar prenumerationens utgångsdatum

I följande tabell sammanfattas effekten på konfigurationsprinciperna för Windows 10-enheten.

|                            | Fullt licensierad upplevelse                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Skydda datorer från hot med Windows Defender** | Aktivera/inaktivera är utanför användarkontrollen | Användaren kan aktivera/inaktivera Windows Defender på Windows 10-datorn |
| **Skydda datorer från webbaserade hot i Microsoft Edge** | Datorskydd i Microsoft Edge | Användaren kan aktivera/inaktivera datorskydd i Microsoft Edge |
| **Stäng av enhetsskärmen när den är inaktiv** | Admin definierar principen för tidsintervall för skärmtidstimeout | Skärmtimeout kan konfigureras av slutanvändare |
| **Tillåt användare att hämta appar från Microsoft Store** | Admin definierar om en användare kan ladda ned appar från Microsoft Store | Användaren kan ladda ned appar från Microsoft Store när som helst |
| **Tillåt användare att använda Cortana** | Admin definierar principen om användaråtkomst till Cortana | Användarenheter för att aktivera/inaktivera Cortana |
| **Tillåt användare att få tips och annonser från Microsoft** | Admin definierar policy för användare får tips och annonser från Microsoft | Användaren kan aktivera/inaktivera tips och annonser från Microsoft |
| **Tillåt användare att kopiera innehåll från Office-program till personliga program** | Admin definierar principen för att hålla Windows 10-enheter uppdaterade | Användare kan bestämma när windows ska uppdateras |
