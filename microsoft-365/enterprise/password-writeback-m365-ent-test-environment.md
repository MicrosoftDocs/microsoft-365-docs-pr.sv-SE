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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Sammanfattning: Konfigurera tillbakaskrivning av lösenord i testmiljön för Microsoft 365.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921486"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Tillbakaskrivning av lösenord i testmiljön för Microsoft 365

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

Användare kan använda tillbakaskrivning av lösenord för att uppdatera sina lösenord via Azure Active Directory (Azure AD), som sedan replikeras till AD DS (Local Active Directory Domain Services). Med tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala AD DS där deras ursprungliga användarkonton lagras. Detta hjälper roaming- eller fjärranvändare som inte har en fjärranslutning till sina lokala nätverk.

I den här artikeln beskrivs hur du konfigurerar Microsoft 365 testmiljö för tillbakaskrivning av lösenord.

Konfigurering av testmiljön för återställning av lösenord omfattar två faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.
- Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen

Börja med att konfigurera kontot för användare 1 med rollen global administratör.

1. Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).

2. Välj **Aktiva användare.**
 
3. På sidan **Aktiva** användare väljer du **användarkontot,**

4. I fönstret **användare1** väljer du **Redigera** bredvid **Roller.**

5. I fönstret **Redigera användarroller** för användare1 väljer **du Global administratör**, väljer **Spara** och sedan **Stäng.**

Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2. På skrivbordet i APP1 väljer du **Start**, anger **aktiv** och väljer sedan **Active Directory - användare och datorer.**

3. På menyraden väljer du **Visa**. Om **Avancerade funktioner** inte är aktiverade aktiverar du den genom att markera den.

4. I trädfönstret väljer du och håller ned (eller högerklickar på) domänen, väljer **Egenskaper** och väljer sedan **fliken** Säkerhet.

5. Välj **Avancerat**.

6. På fliken **Behörigheter** väljer du Lägg **till**.

7. Välj **Välj ett huvudnamn**, ange **Användare1** och välj sedan **OK.**

8. I **Gäller för** väljer du **Underordnade användarobjekt**.

9. Under **Behörigheter** väljer du följande:

    - **Ändra lösenord**
    - **Återställa lösenord**

10. Under **Egenskaper** väljer du följande:
    - **Skriv lockoutTime**
    - **Skriv pwdLastSet**

11. Spara ändringarna genom att välja **OK** tre gånger.

12. Stäng **Active Directory – användare och datorer**.

Konfigurera därefter Azure AD Connect på APP1 för tillbakaskrivning av lösenord.

1. Om det behövs kan du ansluta till APP1 med TESTLAB\User1-kontot.

2. Dubbelklicka på **Azure AD Connect** på APP1-skrivbordet.

3. På **välkomstsidan väljer** du **Konfigurera**.

4. På sidan **Ytterligare uppgifter** väljer du **Anpassa synkroniseringsalternativ** och sedan **Nästa**.

5. På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för ditt globala administratörskonto och väljer sedan **Nästa.**

6. På Anslut **kataloger och filtreringssidor** **för Domän/OU** väljer du **Nästa.**

7. På sidan **Valfria** funktioner väljer du **Tillbakaskrivning av lösenord** och väljer sedan **Nästa**.

8. På sidan **Är redo att** konfigurera väljer du **Konfigurera** och väntar till processen är klar.

9. När konfigurationen är klar väljer du **Avsluta**.

Nu kan du testa tillbakaskrivning av lösenord för användare på datorer som inte är anslutna till det virtuella nätverket i ditt simulerade intranät.

Den resulterande konfigurationen ser ut så här:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Konfigurationen består av:

- En Microsoft 365 E5 utvärderingsversion eller betalda prenumerationer med DNS-domänen TESTLAB.\<*your domain name*> registrerat.
- Ett förenklat organisationsintranät som är anslutet till internet och består av virtuella DC1-, APP1- och CLIENT1-datorer på ett undernät i ett virtuellt Azure-nätverk.
- Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.
- Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)