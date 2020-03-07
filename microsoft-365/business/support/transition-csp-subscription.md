---
title: Överför en CSP-prenumeration för Microsoft 365 Business CSP 
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
keywords: Microsoft 365 Business, Microsoft 365, SMB, övergång CSP-prenumeration
ms.date: 11/01/2017
ms.openlocfilehash: 77b7b474a5ad17db58e283ea61b074c959905d1b
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560789"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Överför en CSP-prenumeration för Microsoft 365 Business CSP

Om du har en CSP-prenumeration för Microsoft 365 Business Preview följer du den här guiden och tar reda på hur du kan överföra din befintliga förhandsgranskningsprenumeration till Microsoft 365 Business GA (allmän tillgänglighet).

**Så här övergår du en förhandsgranskningsprenumeration till GA**

1. Logga in på <a href="https://partnercenter.microsoft.com" target="_blank">Partner Center</a>.
2. Välj **Kunder**på instrumentpanelen och leta sedan efter och välj företagsnamnet.

    Abonnemangen för bolaget kommer att listas.

    ![Kundens prenumerationer i Partner Center](../../media/pc_customer_subscriptions_1.png)
    
3. På företagets **prenumerationssida** väljer du **Lägg till prenumeration**.
4. På sidan **Ny prenumeration** väljer du **Small business** och väljer sedan **Microsoft 365 Business** i listan.
5. Lägg till antalet licenser och välj sedan **Nästa: Granska** för att granska prenumerationen och välj sedan **Skicka**.

    ![Granska den nya prenumerationen på Microsoft 365 Business](../../media/pc_customer_reviewnewsubscription.png)

    De **licensbaserade prenumerationerna** visar **Microsoft 365 Business Preview** och Microsoft **365 Business**. Du kommer att avbryta förhandsgranskningsprenumerationen nästa gång.

6. Välj **Microsoft 365 Business Preview**.
7. På sidan Förhandsgranskning av **Microsoft 365 Business** väljer du **Pausad** för att avbryta förhandsgranskningsprenumerationen.

    ![Pausa Microsoft 365 Business Preview-prenumerationen](../../media/pc_customer_m365bpreview_suspend.png)

8. Välj **Skicka** för att bekräfta.

    På sidan **Prenumerationer** bekräftar du att **statusen för microsoft 365 Business Preview** visar **Suspenderad**.

    ![Bekräfta att förhandsgranskningsprenumerationsstatusen är avstängd](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Du kan också validera licensavtalet. Gör så här:
    1. Välj **Användare och licenser** på sidan **Prenumerationer.**
    2. Välj en användare på sidan **Användare och licenser.**
    3. På användarens sida kontrollerar du avsnittet **Tilldela licenser** och bekräftar att det visar **Microsoft 365 Business**.

        ![Bekräfta att Microsoft 365 Business-licensen har tilldelats användaren](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Inverkan på kunder och användare under och efter övergången

Det finns ingen inverkan på kunder och användare under övergången och efter övergången.

## <a name="impact-to-customers-who-dont-transition"></a>Effekt för kunder som inte övergår

I följande tabell sammanfattas effekten för kunder som inte övergår från en Microsoft 365 Business Preview-prenumeration till en Microsoft 365 Business-prenumeration.

|       | T-0 till T+30     | T+30 till T+60 | T+60 till T+120 | Bortom T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Statligt** | I respitperiod | Löpt ut      | Inaktiverad      | Avetablerad |
| **Tjänstens påverkan**                                                        |
| **Administrationsportal för Microsoft 365 Business** | Ingen påverkan på funktionaliteten | Ingen påverkan på funktionaliteten | Kan lägga till/ta bort användare, köpa prenumerationer.</br> Det går inte att tilldela/återkalla licenser. | kundens prenumeration och alla data tas bort. Admin kan hantera andra betalda prenumerationer. |
| **Office-appar**                         | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Office går in i läget nedsatt funktionalitet.</br> Användare kan bara visa filer. | Office går in i läget nedsatt funktionalitet.</br> Användare kan bara visa filer. |
| **Molntjänster (SharePoint Online, Exchange Online, Skype, Team med mera)** | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Slutanvändare och administratörer har ingen åtkomst till data i molnet. | Kundens prenumeration och alla data tas bort. |
| **EM+S-komponenter** | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Funktionen tillämpas inte längre.</br> Se [Mobile enhetspåverkan vid prenumerationens förfallodatum](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC-effekter vid prenumerationens förfallodag](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Funktionen tillämpas inte längre.</br> Se [Mobile enhetspåverkan vid prenumerationens förfallodatum](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC-effekter vid prenumerationens förfallodag](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Windows 10 Företag** | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Funktionen tillämpas inte längre.</br> Se [Mobile enhetspåverkan vid prenumerationens förfallodatum](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC-effekter vid prenumerationens förfallodag](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Funktionen tillämpas inte längre.</br> Se [Mobile enhetspåverkan vid prenumerationens förfallodatum](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC-effekter vid prenumerationens förfallodag](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Azure AD-inloggning på en Windows 10-dator** | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | Ingen administratörseffekt</br> Ingen inverkan på slutanvändaren | När klienten har tagits bort kan en användare bara logga in med lokala autentiseringsuppgifter. Avbilda enheten igen om det inte finns några lokala autentiseringsuppgifter. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Mobil enhet påverkar vid utgångsdatum för abonnemang

I följande tabell sammanfattas effekten av apphanteringsprinciperna på mobila enheter.

|                            | Fullt licensierad erfarenhet                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ta bort arbetsfiler från en inaktiv enhet** | Arbetsfiler tas bort efter valda dagar | Arbetsfiler finns kvar på användarens personliga enheter |
| **Tvinga användare att spara alla filer i OneDrive för företag** | Arbetsfiler kan bara sparas på OneDrive för företag | Arbetsfiler kan sparas var som helst |
| **Kryptera arbetsfiler** | Arbetsfiler krypteras | Arbetsfiler är inte längre krypterade.</br> Säkerhetsprinciper tas bort och Office-data om appar tas bort. |
| **Kräv PIN-kod eller fingeravtryck för att komma åt Office-appar** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Återställ PIN-koden när inloggningen misslyckas** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Kräv att användarna loggar in igen efter att Office-appar har varit inaktiva** | Inloggning krävs | Ingen inloggning krävs |
| **Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter** | Arbetsfiler kan inte nås på jailbroken / rotade enheter | Arbetsfiler kan nås på jailbroken / rotade enheter |
| **Tillåt användare att kopiera innehåll från Office-appar till personliga appar** | Kopiera/klistra in filer som är begränsade till appar som är tillgängliga som en del av Microsoft 365 Business-prenumeration | Kopiera/klistra in tillgängligt för alla appar |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC påverkar vid förfallodagen för prenumeration

I följande tabell sammanfattas effekten på konfigurationsprinciperna för Windows 10-enheter.

|                            | Fullt licensierad erfarenhet                      | T+60 dagar efter utgångsdatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Skydda datorer från hot med Windows Defender** | Aktivera/inaktivera är utanför användarkontrollen | Användaren kan aktivera/inaktivera Windows Defender på Windows 10-datorn |
| **Skydda datorer från webbaserade hot i Microsoft Edge** | Datorskydd i Microsoft Edge | Användaren kan aktivera/inaktivera datorskydd i Microsoft Edge |
| **Inaktivera enhetsskärmen när den är inaktiv** | Administratör definierar tidsintervallför skärmen | Tidsout för skärm kan konfigureras av slutanvändaren |
| **Tillåt användare att hämta appar från Microsoft Store** | Admin definierar om en användare kan hämta appar från Microsoft Store | Användaren kan ladda ned appar från Microsoft Store när som helst |
| **Tillåt användare att använda Cortana** | Admin definierar principen om användaråtkomst till Cortana | Användarenheter för att aktivera/inaktivera Cortana |
| **Tillåt användare att få tips och annonser från Microsoft** | Admin definierar policy för användaren får tips och annonser från Microsoft | Användaren kan aktivera/inaktivera tips och annonser från Microsoft |
| **Tillåt användare att kopiera innehåll från Office-program till personliga program** | Administratör definierar principen för att hålla Windows 10-enheter uppdaterade | Användare kan bestämma när de ska uppdatera Windows |
