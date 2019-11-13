---
title: Övergång en Microsoft 365 Business CSP-prenumeration 
description: Ta reda på hur du kan övergå en Microsoft 365 Business CSP-prenumeration från förhandsversion till GA. 
author: jasongroce
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365, SMB, övergång CSP-prenumeration
ms.date: 11/01/2017
ms.openlocfilehash: b907c3a3bccc4179369890b7769dcb14ba2acbb7
ms.sourcegitcommit: e4f2f06daa264b8b476813a2dfe80cffb59f968f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311103"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Övergång en Microsoft 365 Business CSP-prenumeration

Om du har en Microsoft 365 Business Preview CSP-prenumeration följer du den här guiden för att ta reda på hur du kan gå över din befintliga förhandsversion till Microsoft 365 Business GA (allmän tillgänglighet).

**Hur man övergång en förhandsversion prenumeration på GA**

1. Logga in på <a href="https://partnercenter.microsoft.com" target="_blank">partner Center</a>.
2. Från instrumentpanelen väljer **kunder**, och sedan hitta och välj företagsnamn.

    Prenumerationerna för företaget kommer att listas.

    ![Kundens prenumerationer i Partner Center](images/pc_customer_subscriptions_1.png)
    
3. På företagets **prenumerations** sida väljer du **Lägg till prenumeration**.
4. På sidan **ny prenumeration** väljer du **Small Business** och väljer sedan **Microsoft 365 Business** i listan.
5. Lägg till antalet licenser och välj sedan **Nästa: granska** för att granska prenumerationen och välj sedan **Skicka**.

    ![Granska den nya prenumerationen på Microsoft 365 Business](images/pc_customer_reviewnewsubscription.png)

    De **licensbaserade prenumerationerna** visar **Microsoft 365 Business Preview** och **Microsoft 365 Business**. Du avbryter förhandsversionen av prenumerationen nästa.

6. Välj **Microsoft 365 Business Preview**.
7. På sidan **Microsoft 365 Business Preview** väljer du **avstängd** för att avbryta prenumerationen förhandsversion.

    ![Pausa prenumerationen på Microsoft 365 Business Preview](images/pc_customer_m365bpreview_suspend.png)

8. Välj **Skicka** för att bekräfta.

    På sidan **prenumerationer** bekräftar du att status för **Microsoft 365 Business Preview** visar **pausad**.

    ![Bekräfta att förhandsgranskningen prenumerationsstatus är avstängd](images/pc_customer_m365bpreview_suspend_confirm.png)

9. Alternativt kan du också validera licensavtalet. Gör så här:
    1. Välj **användare och licenser** från företagets **prenumerations** sida.
    2. Välj en användare på sidan **användare och licenser** .
    3. På användarens sida, kontrollera den **tilldela licenser** avsnittet och bekräfta att den visar **Microsoft 365 Business**.

        ![Bekräfta att Microsoft 365 Business License har tilldelats användaren](images/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Påverkan på kunder och användare under och efter övergången

Det finns ingen inverkan på kunder och användare under övergången och efter övergången.

## <a name="impact-to-customers-who-dont-transition"></a>Påverkan på kunder som inte övergår

I följande tabell sammanfattas effekten för kunder som inte övergår från en Microsoft 365 Business Preview-prenumeration till en Microsoft 365 Business-prenumeration.

|       | T-0 till T + 30     | T + 30 till T + 60 | T + 60 till T + 120 | Bortom T + 120  |
|-------|-----------------|--------------|---------------|---------------|
| **Statligt** | I respittid | Löpt ut      | Inaktiverad      | Avetableras |
| **Påverkan på tjänsten**                                                        |
| **Microsoft 365 Business Admin Portal** | Ingen påverkan på funktionaliteten | Ingen påverkan på funktionaliteten | Kan lägga till/ta bort användare, köpa prenumerationer.</br> Det går inte att tilldela/återkalla licenser. | Kundens prenumeration och alla data raderas. Admin kan hantera andra betalda prenumerationer. |
| **Office-appar**                         | Ingen användar påverkan | Ingen användar påverkan | Office försätts i läget Nedsatt funktionalitet.</br> Användare kan bara visa filer. | Office försätts i läget Nedsatt funktionalitet.</br> Användare kan bara visa filer. |
| **Molntjänster (SharePoint Online, Exchange Online, Skype, team med mera)** | Ingen användar påverkan | Ingen användar påverkan | Slutanvändare och administratörer har ingen åtkomst till data i molnet. | Kundens prenumeration och alla data raderas. |
| **EM + S-komponenter** | Ingen admin påverkan</br> Ingen användar påverkan | Ingen admin påverkan</br> Ingen användar påverkan | Funktionen är inte längre tvingande.</br> Se den [mobila enhetens inverkan när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10-datorn påverkar prenumerationens förfallodatum](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Funktionen är inte längre tvingande.</br> Se den [mobila enhetens inverkan när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10-datorn påverkar prenumerationens förfallodatum](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Windows 10 Business** | Ingen admin påverkan</br> Ingen användar påverkan | Ingen admin påverkan</br> Ingen användar påverkan | Funktionen är inte längre tvingande.</br> Se den [mobila enhetens inverkan när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10-datorn påverkar prenumerationens förfallodatum](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. | Funktionen är inte längre tvingande.</br> Se den [mobila enhetens inverkan när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10-datorn påverkar prenumerationens förfallodatum](#windows-10-pc-impacts-upon-subscription-expiration) för mer information. |
| **Azure AD-inloggning till en Windows 10-dator** | Ingen admin påverkan</br> Ingen användar påverkan | Ingen admin påverkan</br> Ingen användar påverkan | Ingen admin påverkan</br> Ingen användar påverkan | När klienten har tagits bort kan en användare logga in med endast lokala autentiseringsuppgifter. Avbilda enheten igen om det inte finns några lokala autentiseringsuppgifter. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Mobil enhet påverkar när prenumerationen upphör att gälla

I följande tabell sammanfattas effekten på Apphanteringsprinciper på mobila enheter.

|                            | Fullständigt licensierad upplevelse                      | T + 60 dagar efter förfallodatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ta bort arbetsfiler från en inaktiv enhet** | Arbetsfiler tas bort efter valda dagar | Arbetsfiler finns kvar på användarens personliga enheter |
| **Tvinga användare att spara alla filer i OneDrive för företag** | Arbetsfiler kan bara sparas i OneDrive för företag | Arbetsfiler kan sparas var som helst |
| **Kryptera arbetsfiler** | Arbetsfiler krypteras | Arbetsfiler krypteras inte längre.</br> Säkerhetsprinciper tas bort och Office-data på appar tas bort. |
| **Kräv PIN-kod eller fingeravtryck för att komma åt Office-appar** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Återställ PIN-koden när inloggningen misslyckas** | Begränsad åtkomst till appar | Ingen åtkomstbegränsning på appnivå |
| **Kräv att användare loggar in igen efter att Office-apparna har varit inaktiva** | Inloggning krävs | Ingen inloggning krävs |
| **Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter** | Arbetsfiler kan inte nås på jailbroken/rotade enheter | Arbetsfiler kan nås på jailbroken/rotade enheter |
| **Tillåt användare att kopiera innehåll från Office-appar till personliga appar** | Kopiera/klistra in begränsad till appar som är tillgängliga som en del av Microsoft 365 Business-prenumeration | Kopiera/klistra in tillgängligt för alla appar |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC påverkar när prenumerationen upphör att gälla

I följande tabell sammanfattas effekten på konfigurationsprinciperna för Windows 10-enheter.

|                            | Fullständigt licensierad upplevelse                      | T + 60 dagar efter förfallodatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Skydda datorer mot hot med hjälp av Windows Defender** | Slå på/av är utanför användarkontroll | Förbrukaren kanna vända på/bort Fönstren Försvara på det Fönstren 10 PC |
| **Skydda datorer från webbaserade hot i Microsoft Edge** | PC-skydd i Microsoft Edge | Förbrukaren kanna vända på/bort PC säkringen i Mikroskop Egg |
| **Stäng av enhetens skärm vid inaktivitet** | Admin definierar skärmen timeout intervall princip | Skärmtimeout kan konfigureras av slutanvändaren |
| **Tillåt användare att hämta appar från Microsoft Store** | Admin definierar om en användare kan ladda ner appar från Microsoft Store | Användaren kan hämta appar från Microsoft Store när som helst |
| **Tillåt användare att använda Cortana** | Admin definierar policy för användaråtkomst till Cortana | Användarenheter för att slå på/av Cortana |
| **Tillåt användare att få tips och annonser från Microsoft** | Admin definierar policy för användare får tips och annonser från Microsoft | Användaren kan slå på/av tips och annonser från Microsoft |
| **Tillåt användare att kopiera innehåll från Office-program till personliga program** | Admin definierar policy för att hålla Windows 10-enheter uppdaterade | Användare kan bestämma när Windows ska uppdateras |
