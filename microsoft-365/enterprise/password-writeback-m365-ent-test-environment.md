---
title: Tillbakaskrivning av lösenord i testmiljön för Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera tillbakaskrivning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: cc71b581730001d8dc021b5074e300fed636e3d9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632881"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Tillbakaskrivning av lösenord i testmiljön för Microsoft 365

*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

Med tillbakaskrivning av lösenord kan användare uppdatera sina lösenord via Azure Active Directory (Azure AD), som sedan replikeras till din lokala Active Directory Domain Services (AD DS). Med funktionen för tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala AD DS där de ursprungliga användarkontona lagras. Det här underlättar vid nätverksväxling och för fjärranvändare som inte har en fjärråtkomstanslutning till det lokala nätverket.

I den här artikeln beskrivs hur du kan konfigurera Microsoft 365-testmiljön för tillbakaskrivning av lösenord.

Det finns två faser för att konfigurera detta:

1.    Skapa Microsoft 365-testmiljön för det simulerade företaget med synkronisering av lösenordshash.
2.    Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen.
    
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). Här är konfigurationsresultatet.
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av: 
  
- Utvärderingsversioner av eller betalda prenumerationer för Microsoft 365 E5 eller Office 365 E5.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen

Börja med att konfigurera kontot för användare 1 med rollen global administratör.

1. Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).

2. Klicka på **Aktiva användare**.
 
3. På sidan **Aktiva användare** klickar du på kontot **user1**.

4. I fönstret **user1** klickar du på **Redigera** bredvid **Roller**.

5. Gå till fönstret **Redigera användarroller** för user1 och klicka på **Global administrator**. Klicka på **Spara** och sedan på **Stäng**.

Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2.  Klicka på **Start** på skrivbordet för APP1. Skriv **active**och klicka sedan på **Active Directory – användare och datorer**.

3. Klicka på **Visa** i menyraden. Om **Avancerade funktioner** inte har aktiverats, aktiverar du det genom att klicka på det.

4. Högerklicka på din domän i trädfönstret, klicka på **Egenskaper** och klicka sedan på fliken **Säkerhet**.

5. Klicka på **Avancerat**.

6. På fliken **Behörigheter** klickar du på **Lägg till**.

7. Klicka på **Välj ett huvudkonto**, skriv **User1** och klicka sedan på **OK**.

8. I **Gäller för** väljer du **Underordnade användarobjekt**.

9. Under **Behörigheter** väljer du följande:

    - Ändra lösenord
    - Återställa lösenord

10. Under **Egenskaper** väljer du följande:
    - Skriv lockoutTime
    - Skriv pwdLastSet

11. Klicka på **OK** tre gånger för att spara ändringarna.

12. Stäng **Active Directory – användare och datorer**.

Konfigurera därefter Azure AD Connect på APP1 för tillbakaskrivning av lösenord.

1. Om det behövs kan du ansluta till APP1 med TESTLAB\User1-kontot.

2. Dubbelklicka på **Azure AD Connect** på APP1-skrivbordet.

3. På **välkomstsidan** klickar du på **Konfigurera**.

4. På sidan **Ytterligare uppgifter** klickar du på **Anpassa synkroniseringsalternativ** och sedan på **Nästa**.

5. På sidan **Anslut till Azure AD** skriver du dina globala administratörsautentiseringsuppgifter. Klicka sedan på **Nästa**.

6. På sidorna **Anslut kataloger** och **Domän-/OU-filtrering** klickar du på **Nästa**.

7. På sidan **Valfria funktioner** väljer du **Tillbakaskrivning av lösenord** och klickar på **Nästa**. 

8. På sidan **Redo att konfigurera** klickar du på **Konfigurera** och väntar tills processen har slutförts.

9. När konfigurationen är klar klickar du på **Avsluta**.

Du är nu redo att testa tillbakaskrivning av lösenord för användare på datorer som inte är anslutna till det virtuella nätverket i det simulerade intranätet.

Här är konfigurationsresultatet:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Konfigurationen består av:

- Utvärderingsversioner av eller betalda prenumerationer på Microsoft 365 E5 eller Office 365 E5 med DNS-domänen TESTLAB.\<ditt domännamn> registrerad.
- Ett förenklat företagsintranät anslutet till Internet som består av de virtuella datorerna DC1, APP1 och CLIENT1 i ett undernät i ett virtuellt Azure-nätverk. 
- Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen. 
- Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.

I steget [Enklare uppdatering av lösenord](identity-add-user-accounts.md#identity-pw-writeback) i Identitet-fasen finns mer information om och länkar till hur du konfigurerar tillbakaskrivning av lösenord i produktion.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)


