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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487134"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Tillbakaskrivning av lösenord i testmiljön för Microsoft 365

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Användare kan använda Lösenordssynkronisering för att uppdatera sina lösen ord via Azure Active Directory (Azure AD), som sedan replikeras till din lokala Active Directory Domain Services (AD DS). Med lösen ords tillbakaskrivning behöver användarna inte uppdatera sina lösen ord via den lokala AD DS där deras ursprungliga användar konton lagras. Det gör att roaming-eller fjärran vändare som inte har en fjärråtkomstanslutning kan ansluta till deras lokala nätverk.

I den här artikeln beskrivs hur du konfigurerar din Microsoft 365 test miljö för tillbakaskrivning av lösen ord.

När du konfigurerar test miljön för lösen ords ändring görs två faser:
- [Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fas 1: Konfigurera synkronisering av lösenordshash för Microsoft 365-testmiljön

Följ först anvisningarna i [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md). Den resulterande konfigurationen ser ut så här:
  
![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Konfigurationen består av:
  
- En utvärderingsprenumeration eller betald prenumeration på Microsoft 365 E5.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.
- Azure AD Connect körs på APP1 för att synkronisera TESTLAB AD DS-domänen med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fas 2: Aktivera tillbakaskrivning av lösenord för TESTLAB AD DS-domänen

Börja med att konfigurera kontot för användare 1 med rollen global administratör.

1. Logga in med ditt globala administratörskonto från [administrationscentret för Microsoft 365](https://portal.microsoft.com).

2. Välj **aktiva användare**.
 
3. På sidan **aktiva användare** väljer du **Användare1** -kontot

4. I fönstret **Användare1** väljer du **Redigera** bredvid **roller**.

5. I fönstret **Redigera användar roller** för Användare1 väljer du **Global administratör**, väljer **Spara**och sedan **Stäng**.

Konfigurera därefter kontot User 1 med säkerhetsinställningarna som gör det möjligt att ändra lösenord för andra användares räkning i TESTLAB AD DS-domänen.

1. Logga in på [Azure-portalen](https://portal.azure.com) med ditt globala administratörskonto och anslut sedan till APP1 med kontot TESTLAB\User1.

2. I Skriv bords versionen av APP1 väljer du **Start**, anger **Active**och sedan **Active Directory-användare och datorer**.

3. På Meny raden väljer du **Visa**. Om **avancerade funktioner** inte är aktiverade väljer du det för att aktivera det.

4. Markera och håll ned (eller högerklicka) på din domän i träd fönstret, Välj **Egenskaper**och välj sedan fliken **säkerhet** .

5. Välj **Avancerat**.

6. Välj **Lägg till**på fliken **behörigheter** .

7. Välj **Markera ett huvud konto**, ange **user1**och välj sedan **OK**.

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

3. På **Välkomst sidan**väljer du **Konfigurera**.

4. På sidan **Ytterligare aktiviteter** väljer du **Anpassa synkroniseringsalternativ**och sedan **Nästa**.

5. På sidan **Anslut till Azure AD** anger du dina globala administratörs konto uppgifter och väljer sedan **Nästa**.

6. På sidorna **Anslut kataloger** och **domän/ou-filtrering** väljer du **Nästa**.

7. Välj **tillbakaskrivning för lösen ordet**på sidan **valfria funktioner** och välj sedan **Nästa**.

8. På sidan **redo att konfigurera** väljer du **Konfigurera** och vänta för att slutföra processen.

9. När konfigurationen är klar väljer du **Avsluta**.

Du är nu redo att testa tillbakaskrivning för lösen ord för användare på datorer som inte är anslutna till det virtuella nätverket i det simulerade intranätet.

Den resulterande konfigurationen ser ut så här:

![Det simulerade företaget med en testmiljö med direktautentisering](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Konfigurationen består av:

- En utvärderings version av Microsoft 365 E5 eller betalda abonnemang med DNS-TESTLAB.\<*your domain name*> registrerat.
- En förenklad organisations intranät som är ansluten till Internet, bestående av de virtuella datorerna DC1, APP1 och KLIENT1 i ett undernät för ett Azure Virtual Network.
- Azure AD Connect körs på APP1 för att synkronisera listan med konton och grupper från Azure AD-klientorganisationen för din Microsoft 365-prenumeration till TESTLAB AD DS-domänen.
- Tillbakaskrivning av lösenord är aktiverat så att användare kan ändra sina lösenord i Azure AD utan att behöva ansluta till det förenklade intranätet.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)


