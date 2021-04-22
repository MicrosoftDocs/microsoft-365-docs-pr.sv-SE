---
title: Konfigurera utvärderingslabb eller pilotmiljö med Microsoft 365 Defender
description: Gå till Microsoft 365 Säkerhetscenter och konfigurera sedan testlabbmiljön i Microsoft 365 Defender
keywords: Utvärderingsversionskonfiguration för Microsoft 365 Defender, pilotinstallation av Microsoft 365 Defender, Microsoft 365 Defender utvärderingslabbkonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935431"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Konfigurera utvärderingslabbmiljön i Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender 


Det är en process i tre steg att skapa en provlabb eller pilotmiljö med Microsoft 365 Defender:

|[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fas 1: Förbereda](prepare-m365d-eval.md) |![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Introduktion](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fas 3: Introduktion](config-m365d-eval.md) | [![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Tillbaka till pilotspelboken](m365d-pilot.md) |
|--|--|--|--|
||*Du är här!*  | | |


Du befinner dig för närvarande i ställ in fas. Gör de första stegen för att komma åt Microsoft 365 Säkerhetscenter och konfigurera sedan testlabb eller pilotmiljö.

Registrera dig för en Office 365- eller Azure Active Directory-prenumeration om du vill generera en *.onmicrosoft.com-klientorganisation* som du kan använda för att registrera dig för din Microsoft 365 E5-licens. 

>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa klientorganisation eller utvärderingsversionen av Office 365 E5.

I den här fasen får du vägledning genom att:
- Skapa en utvärderingsversion av Office 365 E5
- Aktivera utvärderingsprenumeration på Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Skapa en utvärderingsversion av Office 365 E5
>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa klientorganisationens klientorganisation i Office 365 E5.

1. Gå till Office [365 E5-produktportalen och](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) välj **Kostnadsfri utvärderingsversion**.

   ![Bild of_Office utvärderingsversion av 365 E5 kostnadsfritt](../../media/mtp-eval-9.png)
  
2. Slutför utvärderingsversionen genom att ange din e-postadress (personlig eller företagsadress). Klicka **på Konfigurera konto.**

   ![Bild of_Office registreringsinställningar för utvärderingsversionen av 365 E5](../../media/mtp-eval-10.png)

3. Fyll i ditt förnamn, efternamn, telefonnummer, företagsnamn, företagsstorlek och land eller region.  

   ![Bild of_Office 365 E5 sida för registrering av utvärderingsversion där du uppmanas att ange namn, telefonnummer och företagsinformation](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Landet eller regionen du anger här bestämmer vilken datacenterregion som Office 365 kommer att vara värd för.
  
4. Välj verifieringsinställning: via ett sms eller samtal. Klicka **på Skicka verifieringskod**. 

   ![Bild of_Office 365 E5 utvärderingsversion av registreringskonfiguration som frågar om verifieringsinställning](../../media/mtp-eval-12.png)

5. Ange eget domännamn för klientorganisationen och klicka sedan på **Nästa.**

   ![Bild of_Office registreringskonfigurationssidan för utvärderingsversionen av 365 E5 där du kan konfigurera ditt domännamn](../../media/mtp-eval-13.png)
 
6. Konfigurera den första identiteten, som blir global administratör för klientorganisationen. Fyll i **Namn** och **Lösenord.** Klicka **på Registrera dig.**

   ![Bild of_Office 365 E5 utvärderingsversionsinstallationssida där du kan ange din företagsidentitet](../../media/mtp-eval-14.png)

7. Klicka **på Gå till installationsprogrammet** för att slutföra klientorganisationsetablering för Office 365 E5.

   ![Bild av registreringsinstallationssidan för Office 365 E5 med uppmaning om att klicka på knappen Gå till installation](../../media/mtp-eval-15.png)

8. Anslut företagsdomänen till Office 365-klientorganisationen. [Valfritt] Välj **Anslut en domän som du redan äger** och skriv in domännamnet. Klicka på **Nästa**.

   ![Bild of_Office konfigurationssidan i 365 E5 där du bör anpassa din inloggning och e-post](../../media/mtp-eval-16.png)
 
9. Lägg till en TXT- eller MX-post för att verifiera domänägarskapet. När du har lagt till TXT- eller MX-posten i din domän väljer du **Verifiera**.

   ![Bild of_Office 365 E5-konfigurationssidan där du bör lägga till en TXT av MX-post för att verifiera din domän](../../media/mtp-eval-17.png)
 
10. [Valfritt] Skapa fler användarkonton för klientorganisationen. Du kan hoppa över det här steget genom att klicka **på Nästa.**

    ![Bild of_Office 365 E5-konfigurationssidan där du kan lägga till fler användare](../../media/mtp-eval-18.png)
 
11. [Valfritt] Ladda ned Office-appar. Hoppa **över det här** steget genom att klicka på Nästa. 

    ![Bild of_Office 365 E5 där du kan installera Office-programmen](../../media/mtp-eval-19.png)

12. [Valfritt] Migrera e-postmeddelanden. Du kan hoppa över det här steget.

    ![Bild of_Office 365 E5 där du kan ange om du vill migrera e-postmeddelanden eller inte](../../media/mtp-eval-20.png)
 
13. Välj onlinetjänster. Välj **Exchange** och klicka på **Nästa.** 

    ![Bild of_Office 365 E5 där du kan välja onlinetjänster](../../media/mtp-eval-21.png)

14. Lägg till MX-, CNAME- och TXT-poster i din domän. När det är klart väljer **du Verifiera**.

    ![Bild of_Office 365 E5 här kan du lägga till dina DNS-poster](../../media/mtp-eval-22.png)
 
15. Grattis! Du har slutfört etableringen av din Office 365-klientorganisation.

    ![Bild of_Office konfigurationsbekräftelse för E5 i 365](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivera utvärderingsprenumeration på Microsoft 365

>[!NOTE]
>När du registrerar dig för en utvärderingsversion får du 25 användarlicenser att använda under en månad. Mer [information finns i Prova eller köpa en M365-prenumeration.](../../commerce/try-or-buy-microsoft-365.md)

1. I [administrationscentret för Microsoft 365 klickar](https://admin.microsoft.com/)du **på Fakturering** och går sedan till **Köp tjänster.**

2. Välj **Microsoft 365 E5 och** klicka på Starta kostnadsfri **utvärderingsversion**. 

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion](../../media/mtp-eval-24.png)

3. Välj verifieringsinställning: via ett sms eller samtal. När du har bestämt dig anger du telefonnumret och väljer **Skicka sms eller** Ring **mig** beroende på ditt val.

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion och fråga efter kontaktuppgifter för att skicka kod för att bevisa att du inte är en robot](../../media/mtp-eval-25.png)
 
4. Ange verifieringskoden och klicka på **Starta den kostnadsfria utvärderingsversionen**.

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du kan fylla i verifieringskoden som systemet har skickat för att bevisa att du inte är en robot](../../media/mtp-eval-26.png)

5. Klicka **på Prova nu** för att bekräfta utvärderingsversionen av Microsoft 365 E5.

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du ska klocka knappen Prova nu för att starta](../../media/mtp-eval-27.png)
 
6. Gå till Microsoft **365 Admin Center Användare**  >    >  **aktiva användare.** Välj ditt användarkonto, välj **Hantera produktlicenser och** byt sedan licensen från Office 365 E5 till **Microsoft 365 E5.** Klicka på **Spara**.

   ![Bild of_Microsoft 365 Admin Center-sida där du kan välja Microsoft 365 E5-licens](../../media/mtp-eval-28.png)
 
7. Välj det globala administratörskontot igen och klicka sedan **på Hantera användarnamn**.

   ![Bild of_Microsoft 365 Admin Center-sida där du kan välja Konto och sedan Hantera användarnamn](../../media/mtp-eval-29.png)

8. [Valfritt] Ändra domänen från *onmicrosoft.com* till din egen domän, beroende på vad du valde i föregående steg. Klicka på **Spara ändringar**.

   ![Bild of_Microsoft 365 Administrationscenter där du kan ändra domäninställningarna](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nästa steg
|[Fas 3: Konfigurera & onboard](config-m365d-eval.md) | Konfigurera varje Microsoft 365 Defender-pilotversion för provlabb eller pilotmiljö med Microsoft 365 Defender och registrera slutpunkterna.
|:-------|:-----|
