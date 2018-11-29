---
title: Överföra en Microsoft 365 Business CSP-prenumeration 
description: Ta reda på hur du kan överföra en Microsoft 365 Business CSP-prenumeration från Förhandsgranska GA. 
author: jasongroce
ms.author: jasgro
ms.topic: article 
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business 
keywords: Microsoft 365 Business, Microsoft 365 SMB övergång CSP-prenumeration
ms.date: 11/01/2017
ms.openlocfilehash: 8109c0b00f06a15c12bbccf89e7f49dc3fa4b34a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982489"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Överföra en Microsoft 365 Business CSP-prenumeration

Om du har en Microsoft 365 Business Förhandsgranska CSP-prenumeration följer du den här guiden för att ta reda på hur du kan överföra din befintliga Förhandsgranska prenumeration på Microsoft 365 Business GA (allmän tillgänglighet).

**Hur du uppgraderar en Förhandsgranska-prenumeration på GA**

1. Logga in på <a href="https://partnercenter.microsoft.com" target="_blank">Partner Center</a>.
2. Från instrumentpanelen, välja **kunder**och hitta och välj namnet på företaget.

    Abonnemang för företaget visas.

    ![Kundens abonnemang Partner Center](images/pc_customer_subscriptions_1.png)
    
3. Välj **Lägg till prenumeration**på sidan för företagets **prenumerationer** .
4. Välj **Small business** och välj **Microsoft 365 Business** i listan på sidan **ny prenumeration** .
5. Lägg till antalet licenser och välj sedan **Nästa: granska** granska prenumerationen och välj sedan **Skicka**.

    ![Granska ny prenumeration på Microsoft 365 Business](images/pc_customer_reviewnewsubscription.png)

    **Prenumerationer på licens** visas **Microsoft 365 Business förhandsgranskning** och **Microsoft 365 Business**. Du måste avbryta prenumerationen Förhandsgranska nästa.

6. Välj **Microsoft 365 Business förhandsgranskning**.
7. Välj **Suspended** att avbryta prenumerationen för förhandsgranskning i **Microsoft 365 Business** förhandsgranskningen.

    ![Avbryta prenumerationen Microsoft 365 Business förhandsgranskning](images/pc_customer_m365bpreview_suspend.png)

8. Välj **Skicka** för att bekräfta.

    Bekräfta att status för **Microsoft 365 Business förhandsgranskning** visar **Suspended**på sidan **prenumerationer** .

    ![Bekräfta att förhandsgranska prenumerationsstatus är pausad](images/pc_customer_m365bpreview_suspend_confirm.png)

9. Du kan eventuellt också verifiera licensavtalet. Gör så här:
    1. Välj **användare och licenser** från företagets sida för **abonnemang** .
    2. Välj en användare på sidan **användare och licenser** .
    3. Kontrollera avsnittet **tilldela licenser** och bekräfta att den visar **Microsoft 365 Business**i användarens sida.

        ![Bekräfta att Microsoft 365 Business licens tilldelas användaren](images/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Påverkan på kunder och användare under och efter övergången

Det finns ingen påverkan till kunder och användare under övergången och bokför övergång.

## <a name="impact-to-customers-who-dont-transition"></a>Påverkan på kunder som inte övergång

I följande tabell sammanfattas konsekvenserna för kunder som inte övergår från en förhandsgranskning av Microsoft 365 Business-prenumeration till en Microsoft 365 Business-prenumeration.

|       | T-0 T + 30     | T + 30-T + 60 | T + 60 T + 120 | Utöver T + 120  |
|-------|-----------------|--------------|---------------|---------------|
| **Region** | I grace-perioden | Upphört att gälla      | Inaktiverad      | Deprovisioned |
| **Tjänsten påverkar**                                                        |
| **Administrationsportalen för Microsoft 365 Business** | Ingen påverkan på funktionen | Ingen påverkan på funktionen | Lägg till/ta bort användare kan köpa prenumerationer.</br> Det går inte att tilldela/återkalla licenser. | Kundens prenumeration och alla data raderas. Admin kan hantera andra betalda prenumerationer. |
| **Office-appar**                         | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Office övergår i läget Nedsatt funktionalitet.</br> Användare kan visa endast filer. | Office övergår i läget Nedsatt funktionalitet.</br> Användare kan visa endast filer. |
| **Cloud services (SharePoint Online, Exchange Online, Skype, team och mer)** | Ingen inverkan på slutanvändaren | Ingen inverkan på slutanvändaren | Användare och administratörer har ingen åtkomst till data i molnet. | Kundens prenumeration och alla data raderas. |
| **EM + S komponenter** | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Kapacitet kommer att upphöra att tillämpas.</br> Mer info finns i [mobila enhet påverkar när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC påverkan när prenumerationen upphör att gälla](#windows-10-pc-impacts-upon-subscription-expiration) . | Kapacitet kommer att upphöra att tillämpas.</br> Mer info finns i [mobila enhet påverkar när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC påverkan när prenumerationen upphör att gälla](#windows-10-pc-impacts-upon-subscription-expiration) . |
| **Windows 10 Business** | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Kapacitet kommer att upphöra att tillämpas.</br> Mer info finns i [mobila enhet påverkar när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC påverkan när prenumerationen upphör att gälla](#windows-10-pc-impacts-upon-subscription-expiration) . | Kapacitet kommer att upphöra att tillämpas.</br> Mer info finns i [mobila enhet påverkar när prenumerationen upphör att gälla](#mobile-device-impacts-upon-subscription-expiration) och [Windows 10 PC påverkan när prenumerationen upphör att gälla](#windows-10-pc-impacts-upon-subscription-expiration) . |
| **Azure AD-inloggning till en Windows 10 PC** | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | Ingen admin påverkan</br> Ingen inverkan på slutanvändaren | En användare kan logga in med lokala autentiseringsuppgifter när arrendatorn tas bort. Image enheten igen om det inte finns några lokala autentiseringsuppgifter. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Påverkan av mobil enhet när prenumerationen upphör att gälla

Followint tabell sammanfattar påverkan på hanteringsprinciper app på mobila enheter.

|                            | Fullständig licenserad erfarenhet                      | T + 60 dagar efter förfallodatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ta bort filer för arbete från en inaktiv enhet** | Arbete-filer tas bort efter valda dagar | Arbete-filer finns kvar på användarens personliga enheter |
| **Tvinga användare att spara alla filer i OneDrive för företag** | Arbetsfält kan endast sparas på OneDrive för företag | Arbete-filer kan sparas var som helst |
| **Kryptera arbetsfiler** | Arbetsfält är krypterade | Arbete-filer är inte längre krypterade.</br> IPSec-principer tas bort och Office-data i appar tas bort. |
| **Kräv PIN-kod eller fingeravtryck för att komma åt Office apps** | Begränsad åtkomst till appar | Ingen begränsning för app-behörighet |
| **Återställ PIN-kod när inloggningen misslyckas** | Begränsad åtkomst till appar | Ingen begränsning för app-behörighet |
| **Användare måste logga in igen när Office apps har varit inaktiv** | -Inloggning krävs | Ingen inloggning krävs för åtkomst till appar |
| **Neka åtkomst till arbetsfiler på jailbrokade eller rotade enheter** | Arbete-filer kan inte användas på jailbroken/rotade enheter | Arbetsfält kan nås på jailbroken/rotade enheter |
| **Tillåt användare att kopiera innehåll från Office apps till personliga appar** | Kopiera/Klistra in begränsat till appar som är tillgängliga som en del av Microsoft 365 Business-prenumeration | Kopiera/Klistra in tillgängliga för alla program |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Windows 10 PC påverkan när prenumerationen upphör att gälla

I följande tabell sammanfattas påverkan på principer för Windows 10 enhetens konfiguration.

|                            | Fullständig licenserad erfarenhet                      | T + 60 dagar efter förfallodatum          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Skydda datorer mot hot med hjälp av Windows Defender** | Aktivera/inaktivera ligger utanför användarkontroll | Användaren kan aktivera/inaktivera Windows Defender i Windows 10 PC |
| **Skydda datorer från webbaserade hot i Microsoft Edge** | PC-skydd i Microsoft Edge | Användaren kan aktivera/inaktivera PC protection i Microsoft Edge |
| **Stänga av enhetens skärm vid inaktivitet** | Admin definierar principen för skärmen timeout-intervall | Timeout för skärmen kan konfigureras av användaren |
| **Tillåt användare att hämta appar från Microsoft Store** | Admin-anger om en användare kan hämta appar från Microsoft Store | Användaren kan ladda ned appar från Microsoft Store när som helst |
| **Tillåt användare att använda Cortana** | Admin definierar principer på användarnas åtkomst till Cortana | Enheter för användaren att aktivera/inaktivera Cortana |
| **Tillåt användare att få tips och annonser från Microsoft** | Admin definierar principen för användaren att få tips och annonser från Microsoft | Användaren kan aktivera/inaktivera tips och annonser från Microsoft |
| **Tillåt användare att kopiera innehåll från Office-program till personliga program** | Admin definierar en princip för att hålla det uppdaterat Windows 10 enheter | Användare kan bestämma när du vill uppdatera Windows |




