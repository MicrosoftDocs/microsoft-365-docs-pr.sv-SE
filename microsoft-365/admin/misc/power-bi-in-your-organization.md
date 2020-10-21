---
title: Power BI i organisationen
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
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Lär dig mer om Power BI och hur användare i organisationen kan använda Business Analytics-tjänsten.
ms.openlocfilehash: 633052889a2ca5c5c4db4c3b3c9334b396148e2a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644933"
---
# <a name="power-bi-in-your-organization"></a>Power BI i organisationen

På den här sidan beskrivs hur användare i organisationen kan använda Power BI, och hur du kan styra hur din organisation tar del av den här tjänsten.
    
## <a name="what-is-power-bi"></a>Vad är Power BI?

Med Microsoft Power BI kan användarna visualisera data, dela upptäckter med varandra och samarbeta på nya och intuitiva sätt. Mer information finns på [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Uppfyller Power BI nationella, regionala och företagsspecifika efterföljandekrav?

Mer information om kompatibilitet med Power BI finns i [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Hur registrerar sig användarna för Power BI?

Som administratör kan du registrera dig för Power BI via [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/). Du kan också registrera dig via sidan Köp tjänster i administrations centret för Microsoft 365. När administratörer registrerar sig för Power BI kan de tilldela prenumerationslicenser till användare som bör ha åtkomst.
  
Dessutom kan enskilda användare i organisationen registrera sig för Power BI via [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/). När en användare i organisationen registrerar sig för Power BI tilldelas den användaren en Power BI-licens automatiskt.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hur registrerar sig enskilda användare inom organisationen?

Det finns tre situationer som kan gälla för användare i organisationen:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-an-microsoft-365-account"></a>Scenario 1: organisationen har redan en befintlig Microsoft 365-miljö och användaren som registrerar sig för Power BI har redan ett Microsoft 365-konto.

I den här situationen, där användaren redan har ett konto för arbetet eller skolan hos klientorganisationen (t.ex. contoso.com) men ännu inte har Power BI, aktiverar Microsoft helt enkelt abonnemanget för kontot, och användaren får automatiskt ett meddelande om hur man använder Power BI-tjänsten.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-an-microsoft-365-account"></a>Scenario 2: organisationen har en befintlig Microsoft 365-miljö och användaren som registrerar sig för Power BI har inget Microsoft 365-konto.

I det här scenariot har användaren en e-postadress i organisationens domän (till exempel contoso.com) men inte ett Microsoft 365-konto. I det här fallet kan användaren registrera sig för Power BI och tilldelas automatiskt ett konto. Då kan användaren komma åt Power BI-tjänsten. Om en anställd till exempel använder sin arbets-e-postadress (till exempel Nancy@contoso.com) för att registrera dig, lägger Microsoft automatiskt till Nancy som en användare i den contoso Microsoft 365-miljön och aktiverar Power BI för det kontot.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Scenario 3: din organisation har ingen Microsoft 365-miljö ansluten till e-postdomänen.

Organisationen behöver inte vidta några administrativa åtgärder för att kunna dra nytta av Power BI.
  
> [!IMPORTANT]
> Om organisationen har flera e-postdomäner och du vill att alla e-posttillägg ska finnas i samma klient organisation, måste du lägga till alla e-postadresser till klient organisationen innan användarna skapar din primära klient organisation. Det finns ingen automatisk mekanism för att flytta användare mellan klient organisationer när de har skapats. Mer information om den här processen finns i [om jag har flera domäner, kan jag styra klient organisationen som användare läggs till i?](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) längre ned i den här artikeln och [lägga till en domän i Office 365](../setup/add-domain.md) online. 
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hur ändrar det här mitt nuvarande sätt att hantera identiteter för organisationens användare?

Om din organisation redan har en befintlig Microsoft 365-miljö och alla användare i organisationen har Microsoft 365-konton ändras inte identitets hanteringen.
  
Om din organisation redan har en befintlig Microsoft 365-miljö men inte alla användare i organisationen har Microsoft 365-konton skapar vi en användare i klient organisationen och tilldelar licenser baserat på användarens e-postadress för arbete eller skola. Det innebär att antalet användare som du hanterar växer efter hand som användare inom organisationen registrerar sig för tjänsten.
  
Om du hanterar katalogen lokalt och använder AD FS (Active Directory Federation Services), så kommer Microsoft inte att lägga till några användare i klientorganisationen, och användare som försöker gå med i klientorganisationen får ett meddelande om att de ska kontakta organisationens administratör.
  
Om organisationen inte har en Microsoft 365-miljö ansluten till e-postdomänen, kommer du inte att ändra hur du hanterar identiteten. Användarna läggs till i en ny, molnbaserad användarkatalog, och du har möjlighet att välja att ta över som administratör för klientorganisationen och hantera dem.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Vilken är processen för att hantera en klientorganisation som skapats av Microsoft för mina användare?

Om en klientorganisation har skapats av Microsoft kan du begära och hantera klientorganisationen genom att följa stegen nedan:
  
1. Anslut till klientorganisationen genom att [registrera dig för Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) med en e-postadressdomän som överensstämmer med den klientorganisationsdomän som du vill hantera. Om Microsoft t.ex. skapade klientorganisationen contoso.edu, så måste du ansluta till klientorganisationen med en e-postadress som slutar med @contoso.edu. 
    
2. Begära administratörskontroll genom att verifiera att du äger domänen: du kan ge dig själv administratörsrollen genom att verifiera att du äger domänen. Gör så här:
 
::: moniker range="o365-worldwide"
   
3. Gå till [https://admin.microsoft.com](https://admin.microsoft.com).
 

::: moniker-end

::: moniker range="o365-germany"

3. Gå till [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Gå till [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

    
4. Välj ikonen för startprogrammet i det övre vänstra hörnet, och välj sedan **Admin**.
    
    ![Start ikon för appen med administratörs programmet markerat](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Läs instruktionerna på sidan **bli administratör** och välj sedan **Ja, jag vill vara administratör**.
    
    > [!NOTE]
    >  Om det här alternativet inte visas finns det redan en administratör. 
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Om jag har flera domäner kan jag styra klient organisation som användare läggs till i?

Om du inte gör någonting skapas en klientorganisation för varje e-postdomän och e-postunderdomän för användare.
  
Om du vill att alla användare ska finnas i samma klientorganisation, oavsett e-postadresstillägg, gör du följande:
  
- Skapa en målklientorganisation i förväg eller använd en befintlig klientorganisation, och lägg till alla befintliga domäner och underdomäner som du vill samla i den klientorganisationen. Då kommer alla användare med e-postadresser som slutar med de domänerna och underdomänerna automatiskt att gå med i målklientorganisationen när de registrerar sig.
    
> [!IMPORTANT]
> Det finns ingen automatiserad mekanism för att flytta användare mellan klientorganisationer när de har skapats. Information om hur du lägger till domäner till en enda Microsoft 365-klient organisation finns i [lägga till en domän i Office 365](../setup/add-domain.md). 
  
> [!IMPORTANT]
> Mer information och vägledning om hur du hanterar klient organisationer finns i [Vad är Power BI-administration?](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization). 
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>Hur kan jag hindra användare från att ansluta till min befintliga klient organisation?

Det finns åtgärder du kan vidta som administratör för att hindra användare från att ansluta till din befintliga klient organisation. Om du blockerar detta Miss lyckas användarens inloggnings problem och de kommer att kontakta sin organisations administratör. Du behöver inte upprepa den här proceduren om du redan har inaktiverat automatisk licens distribution före (t. ex. Office 365 Education för studenter, lärare och personal).
  
För de här stegen måste du använda Windows PowerShell. Om du vill få hjälp med att komma igång med Windows PowerShell kan du läsa [PowerShell Komma igång](https://go.microsoft.com/fwlink/p/?LinkID=286814).
  
För att utföra följande steg måste du installera den senaste 64-bitars versionen av [Azure Active Directory v2 PowerShell-modulen](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).
  
När du har markerat länken väljer du **Kör** för att köra installations paketet. 
  
 **Inaktivera automatisk anslutning till klientorganisation**: Använd det här Windows PowerShell-kommandot för att hindra nya användare från att ansluta till en hanterad klientorganisation:
  
Så här inaktiverar du automatisk anslutning till klientorganisation för nya användare:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Så här aktiverar du automatisk anslutning till klientorganisation för nya användare:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Detta förhindrar att nya användare i organisationen kan registrera sig för Power BI. Användare som registrerar sig för Power BI innan de kan inaktivera nya registreringar för din organisation behåller sina licenser. Se [hur du tar bort Power BI för användare som redan har registrerat sig?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) för anvisningar om hur du kan ta bort åtkomst till Power BI för användare som tidigare registrerat sig för tjänsten. 
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>Hur kan jag tillåta användare att gå med i min nuvarande klient organisation?

Om du vill tillåta att användarna ansluter till klientorganisationen inverterar du kommandot som anges i frågan ovan:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Hur verifierar jag om jag har blockering aktiverad i klientorganisationen?

Använd följande PowerShell-skript:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hur kan jag förhindra att min befintliga användare börjar använda Power BI?

 **Inaktivera automatisk licens distribution:** Använd detta Windows PowerShell-skript för att inaktivera automatiska licens distributioner för befintliga användare. Du behöver inte upprepa den här proceduren om du redan har inaktiverat automatisk licens distribution före (t. ex. Office 365 Education för studenter, lärare och personal). 
  
Så här inaktiverar du automatisk licensdistribution för befintliga användare:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Så här aktiverar du automatisk licensdistribution för befintliga användare:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> *AllowAdHocSubscriptions* -flaggan används för att styra flera användar funktioner i organisationen, inklusive möjligheten för användare att registrera sig för Azure Rights Management-tjänsten. Om den här flaggan ändras, påverkas alla de här funktionerna. 
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hur tillåter jag att de befintliga användarna registrerar sig för Power BI?

Om du vill tillåta att användarna registrerar sig för Power BI inverterar du kommandot som anges i frågan ovan:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hur tar jag bort Power BI för användare som redan registrerat sig?

Om en användare har registrerat sig för Power BI-men du inte längre vill att de ska ha åtkomst till Power BI, kan du ta bort Power BI-licensen för den användaren.

::: moniker range="o365-worldwide"
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Leta reda på den användare som du vill ta bort licensen för och välj sedan personens namn.
    
3. På fliken **licenser och appar** avmarkerar du kryss rutan **Microsoft Power BI** .
    
4. Välj **Spara ändringar**.

::: moniker-end

  
::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Leta reda på den användare som du vill ta bort licensen för och välj sedan personens namn.
    
3. Bredvid **produkt licenser**väljer du **Redigera**. 
    
4. Inaktivera **Microsoft Power BI** -alternativet.
    
5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Leta reda på den användare som du vill ta bort licensen för och välj sedan personens namn.
    
3. Bredvid **produkt licenser**väljer du **Redigera**. 
    
4. Inaktivera **Microsoft Power BI** -alternativet.
    
5. Välj **Spara**.

::: moniker-end 


## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hur vet jag när nya användare har anslutit till min klientorganisation?

Användare som har anslutit till din klientorganisation som en del av det här programmet tilldelas en unik licens som du kan filtrera efter i det aktiva användarfönstret på instrumentpanelen för administratörer.
  
Om du vill skapa den nya vyn går du till administrations centret och följer stegen för att [skapa en anpassad vy](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view). Under **tilldelad produkt licens**väljer du **Microsoft Power BI**. När du har skapat den nya vyn kan du se alla användare i klient organisationen som har registrerat sig i det här programmet.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Finns det något annat som jag ska vara förberedd på?

Du får eventuellt fler förfrågningar om återställning av lösenord. Mer information om den här processen finns i [Återställa en användares lösenord](../add-users/reset-passwords.md).
  
Du kan ta bort en användare från klient organisationen via standard processen i administrations centret. Men om användaren fortfarande har en aktiv e-postadress från organisationen kan de ansluta igen såvida du inte blockerar alla användare från att ansluta.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>Varför visas 1 000 000-licenser för Microsoft Power BI i min klient organisation?

Eftersom din organisation är kvalificerad, är användare inom organisationen behöriga att använda Microsoft Power BI-tjänsten, och de här licenserna representerar den tillgängliga kapaciteten för nya Power BI-användare inom klientorganisationen. Ingen avgift utgår för de här licenserna. Om du har valt att tillåta att användare registrerar sig för Power BI kan de få en av dessa gratis licenser när de slutför registrerings processen. Du kan också välja att tilldela dessa licenser till användare själv via administrations centret.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Kostar det någonting? Debiteras jag för licenserna?

Licenserna gäller för den kostnadsfria versionen av Power BI. Om du vill ha fler funktioner kan du ta en titt på Power BI Pro.
  
## <a name="why-1-million-licenses"></a>Varför 1 miljon licenser?

Vi valde ett nummer som var tillräckligt stort för att majoriteten av de flesta organisationer skulle kunna ge denna fördel utan dröjsmål till sina användare.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Vad händer om jag behöver mer än 1 miljon licenser?

Kontakta din Microsoft-kontorepresentant för mer information om du behöver skaffa ytterligare licenser.
