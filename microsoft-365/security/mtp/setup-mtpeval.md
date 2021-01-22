---
title: Konfigurera din utvärderingslabb eller pilotmiljö i Microsoft 365 Defender
description: Access Microsoft 365 Säkerhetscenter konfigurera sedan utvärderingslabbmiljön i Microsoft 365 Defender
keywords: Utvärderingsversion av Microsoft Threat Protection, pilotkonfiguration för Microsoft Threat Protection, prova Microsoft Threat Protection, utvärderingslabbkonfiguration för Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932988"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Konfigurera utvärderingslabbmiljön i Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender 


Att skapa ett testlabb eller pilotmiljö i Microsoft 365 Defender och distribuera den är en process i tre steg:

|[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fas 1: Förbereda](prepare-mtpeval.md) |![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fas 3: Onboard](config-mtpeval.md) | [![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Tillbaka till pilotspelboken](mtp-pilot.md) |
|--|--|--|--|
||*Du är här!*  | | |


Du befinner dig för närvarande i den inledande fasen. Ta de första stegen för att komma åt Microsoft 365 Säkerhetscenter och konfigurera sedan utvärderingslabb eller pilotmiljö.

Registrera dig för en Office 365- eller Azure Active Directory-prenumeration om du vill generera en *.onmicrosoft.com-klientorganisation* som du kan använda för att registrera dig för din Microsoft 365 E5-licens. 

>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa klientorganisation i Office 365 E5.

I den här fasen vägleds du till:
- Skapa en utvärderingsklientorganisation för Office 365 E5
- Aktivera utvärderingsprenumeration på Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Skapa en utvärderingsklientorganisation för Office 365 E5
>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa utvärderingsversionen av Office 365 E5.

1. Gå till Office [365 E5-produktportalen och](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) välj **Kostnadsfri utvärderingsversion.**

   ![Bild of_Office utvärderingsversion av 365 E5](../../media/mtp-eval-9.png)
  
2. Slutför registreringen av utvärderingsversionen genom att ange din e-postadress (personlig eller företagsadress). Klicka **på Konfigurera konto.**

   ![Bild of_Office konfigurationssidan för registrering av utvärderingsversion av 365 E5](../../media/mtp-eval-10.png)

3. Fyll i ditt förnamn, efternamn, telefonnummer, företagsnamn, företagsstorlek och land eller region.  

   ![Bild of_Office 365 E5 sida för registrering av utvärderingsversion som frågar om namn, telefon och företagsinformation](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Det land eller den region som du anger här bestämmer vilken datacenterregion som Office 365 ska lagras i.
  
4. Välj verifieringsinställning: via ett sms eller samtal. Klicka **på Skicka verifieringskod.** 

   ![Bild of_Office 365 E5 sida för registrering av utvärderingsversion som frågar om verifieringsinställning](../../media/mtp-eval-12.png)

5. Ange det anpassade domännamnet för klientorganisationen och klicka sedan på **Nästa.**

   ![Bild of_Office registreringssida för utvärderingsversion av 365 E5 där du kan konfigurera ditt eget domännamn](../../media/mtp-eval-13.png)
 
6. Konfigurera den första identiteten, som blir global administratör för klientorganisationen. Fyll i **namn** och **lösenord.** Klicka **på Registrera dig.**

   ![Bild of_Office 365 E5 sida för registrering av utvärderingsversion där du kan ange din företagsidentitet](../../media/mtp-eval-14.png)

7. Klicka **på Gå till installation** för att slutföra klientorganisationsetablering för Office 365 E5.

   ![Bild på registreringssidan för utvärderingsversionen av Office 365 E5 där du uppmanas att klicka på knappen Kör installationsprogram](../../media/mtp-eval-15.png)

8. Anslut företagsdomänen till Office 365-innehavaren. [Valfritt] Välj **Anslut en domän som du redan äger** och ange ditt domännamn. Klicka på **Nästa**.

   ![Bild of_Office konfigurationssidan i 365 E5 där du bör anpassa din inloggning och e-post](../../media/mtp-eval-16.png)
 
9. Lägg till en TXT- eller MX-post för att verifiera domänägarskapet. När du har lagt till TXT- eller MX-posten i domänen väljer du **Verifiera.**

   ![Bild of_Office 365 E5-konfigurationssidan där du bör lägga till en TXT av MX-post för att verifiera din domän](../../media/mtp-eval-17.png)
 
10. [Valfritt] Skapa fler användarkonton för klientorganisationen. Du kan hoppa över det här steget genom att klicka på **Nästa.**

    ![Bild of_Office konfigurationssidan i 365 E5 där du kan lägga till fler användare](../../media/mtp-eval-18.png)
 
11. [Valfritt] Ladda ned Office-appar. Klicka **på Nästa** för att hoppa över det här steget. 

    ![Bild of_Office 365 E5 där du kan installera Office-programmen](../../media/mtp-eval-19.png)

12. [Valfritt] Migrera e-postmeddelanden. Du kan hoppa över det här steget.

    ![Bild of_Office 365 E5 där du kan ange om du vill migrera e-postmeddelanden eller inte](../../media/mtp-eval-20.png)
 
13. Välj onlinetjänster. Välj **Exchange** och klicka på **Nästa.** 

    ![Bild of_Office 365 E5 där du kan välja onlinetjänster](../../media/mtp-eval-21.png)

14. Lägg till MX-, CNAME- och TXT-poster i din domän. När det är klart väljer du **Verifiera.**

    ![Bild of_Office 365 E5 här kan du lägga till dina DNS-poster](../../media/mtp-eval-22.png)
 
15. Grattis! Du har slutfört etableringen av din Office 365-klientorganisation.

    ![Bild of_Office bekräftelsesidan för slutförande av konfigurationen i 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivera utvärderingsprenumeration på Microsoft 365

>[!NOTE]
>När du registrerar dig för en utvärderingsversion får du 25 användarlicenser att använda under en månad. Mer information finns i Prova [eller Köpa en M365-prenumeration.](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1)

1. Klicka [på Fakturering i administrationscentret för Microsoft 365](https://admin.microsoft.com/)och navigera sedan till Köp **tjänster.** 

2. Välj **Microsoft 365 E5 och** klicka på Starta kostnadsfri **utvärderingsversion.** 

   ![Bild of_Microsoft 365 E5 , sida för kostnadsfri utvärderingsversion](../../media/mtp-eval-24.png)

3. Välj verifieringsinställning: via ett sms eller samtal. När du har bestämt dig anger du telefonnumret och väljer **Sms:a mig** eller Ring **upp mig** beroende på vad du har valt.

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion och fråga efter kontaktuppgifter för att skicka kod för att bevisa att du inte är en robot](../../media/mtp-eval-25.png)
 
4. Ange verifieringskoden och klicka på **Starta den kostnadsfria utvärderingsversionen.**

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du kan fylla i verifieringskoden som systemet skickat till bevisa att du inte är en robot](../../media/mtp-eval-26.png)

5. Klicka **på Prova nu** för att bekräfta utvärderingsversionen av Microsoft 365 E5.

   ![Bild of_Microsoft 365 E5 Starta kostnadsfri utvärderingsversion där du ska trycka på knappen Prova nu för att starta](../../media/mtp-eval-27.png)
 
6. Gå till Microsoft **365 Admin Center –**  >  **Aktiva**  >  **användare.** Välj ditt användarkonto, välj **Hantera produktlicenser** och byt sedan licensen från Office 365 E5 till **Microsoft 365 E5.** Klicka på **Spara**.

   ![Bild of_Microsoft sidan administrationscenter för 365 där du kan välja Microsoft 365 E5-licens](../../media/mtp-eval-28.png)
 
7. Välj det globala administratörskontot igen och klicka sedan **på Hantera användarnamn.**

   ![Bild of_Microsoft 365 Admin Center där du kan välja Konto och sedan Hantera användarnamn](../../media/mtp-eval-29.png)

8. [Valfritt] Ändra domänen från *onmicrosoft.com* domän till en egen domän, beroende på vad du valde i föregående steg. Klicka på **Spara ändringar**.

   ![Bild of_Microsoft sidan i administrationscentret för 365 där du kan ändra domäninställningarna](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nästa steg
|[Fas 3: Konfigurera & registrering](config-mtpeval.md) | Konfigurera varje Microsoft 365 Defender-pilotversion av ditt provlabb eller pilotmiljö i Microsoft 365 Defender och registrera slutpunkterna.
|:-------|:-----|
