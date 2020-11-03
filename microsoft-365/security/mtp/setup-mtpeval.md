---
title: Konfigurera utvärderings labb eller pilot miljö för Microsoft 365 Defender
description: Gå till Microsoft 365 säkerhets Center och konfigurera utvärderings laboratorie miljön för Microsoft 365 Defender
keywords: Utvärderings version av Microsoft Threat Protection – Microsoft Threat Protection pilot-konfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844830"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Konfigurera utvärderings labb miljön för Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender 


Att skapa en test labb-eller pilot miljö för Microsoft 365 Defender och distribuera det är en process i tre steg:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender" />
      <br/>Fas 1: förbereda </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Konfigurera utvärderings labb eller pilot miljö för Microsoft 365 Defender" />
      <br/>Fas 2: konfiguration </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Konfigurera varje Microsoft 365 Defender-pelare för utvärderings labb eller pilot miljön Microsoft 365 Defender" />
      <br/>Steg 3: Konfigurera & inbyggt </a><br>
</td>


  </tr>
</table>

Du befinner dig i fasen inställning. Vidta de första stegen för att komma åt Microsoft 365 Security Center och konfigurera sedan utvärderings labbet eller pilot miljön.

Registrera dig för en Office 365-eller Azure Active Directory-prenumeration och generera en *. onmicrosoft.com* -klient organisation som du kan använda för att registrera dig för din Microsoft 365 E5-licens. 

>[!NOTE]
>Om du redan har en prenumeration på Office 365 eller Azure Active Directory kan du hoppa över Office 365 E5-utvärderings-och pilot klient skapande anvisningar.

I den här fasen vägleds du:
- Skapa en Office 365 E5-prov klient
- Aktivera utvärderings prenumeration för Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Skapa en Office 365 E5-prov klient
>[!NOTE]
>Om du redan har en prenumeration på Office 365 eller Azure Active Directory kan du hoppa över stegen för att skapa ett Office 365 E5-prov.

1. Gå till [produkt portalen för Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) och välj **gratis prov**.

   ![Bild of_Office 365 E5 gratis prov sida](../../media/mtp-eval-9.png)
  
2. Slutför utvärderings registreringen genom att ange din e-postadress (privat eller företag). Klicka på **Konfigurera konto**.

   ![Bild of_Office 365 E5 prov registrerings sida för utvärderings version](../../media/mtp-eval-10.png)

3. Fyll i ditt förnamn, efter namn, företags telefonnummer, företags namn, företags storlek och land eller region.  

   ![Bild of_Office 365 E5 utvärderings versionen av prov registrerings sidan som frågar efter namn, telefon och företagets uppgifter](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Det land eller den region som du anger här bestämmer vilket område i data centret som Office 365 hanteras på.
  
4. Välj verifierings inställningar: via SMS eller ett samtal. Klicka på **Skicka verifierings kod**. 

   ![Bild of_Office 365 E5 prov registrerings sida för utvärderings version](../../media/mtp-eval-12.png)

5. Ange det anpassade domän namnet för din klient organisation och klicka sedan på **Nästa**.

   ![Bild of_Office 365 E5 prov registrerings sidan där du kan konfigurera ditt eget domän namn](../../media/mtp-eval-13.png)
 
6. Konfigurera den första identiteten, som är global administratör för klient organisationen. Fyll i **namn** och **lösen ord**. Klicka på **Registrera dig**.

   ![Bild of_Office 365 E5 prov registrerings sidan där du kan ställa in din företags identitet](../../media/mtp-eval-14.png)

7. Klicka på **gå till installations programmet** för att slutföra Office 365 E5-etableringen för utvärderings version.

   ![Bild av Office 365 E5 prov registrerings sidan uppmana dig att klicka på knappen Kör inställningar](../../media/mtp-eval-15.png)

8. Anslut företags domänen till Office 365-klient organisationen. Skriver Välj **Anslut en domän som du redan äger** och skriv in ditt domän namn. Klicka på **Nästa**.

   ![Bild of_Office 365 E5 – installations sida där du bör anpassa inloggnings-och e-post](../../media/mtp-eval-16.png)
 
9. Lägga till en TXT-eller MX-post för att verifiera domänens ägarskap. När du har lagt till TXT-eller MX-posten i domänen väljer du **Verifiera**.

   ![Bild of_Office 365 E5-installationsfilen där du bör lägga till en TXT-post för att verifiera din domän](../../media/mtp-eval-17.png)
 
10. Skriver Skapa fler användar konton för din klient organisation. Du kan hoppa över det här steget genom att klicka på **Nästa**.

    ![Bild of_Office 365 E5-installationsfilen där du kan lägga till fler användare](../../media/mtp-eval-18.png)
 
11. Skriver Ladda ner Office-appar. Hoppa över det här steget genom att klicka på **Nästa** . 

    ![Bild of_Office 365 E5-sida där du kan installera Office-programmen](../../media/mtp-eval-19.png)

12. Skriver Migrera e-postmeddelanden. Du kan hoppa över det här steget.

    ![Bild of_Office 365 E5 där du kan ange om du vill migrera e-postmeddelanden eller inte](../../media/mtp-eval-20.png)
 
13. Välj online tjänster. Välj **Exchange** och klicka på **Nästa**. 

    ![Bild of_Office 365 E5 där du kan välja online tjänster](../../media/mtp-eval-21.png)

14. Lägga till MX-, CNAME-och TXT-poster i din domän. När du är klar väljer du **Verifiera**.

    ![Bild of_Office 365 E5 här kan du lägga till dina DNS-poster](../../media/mtp-eval-22.png)
 
15. Grattis, du har slutfört etableringen av din Office 365-klient.

    ![Bild of_Office 365 E5-sidan för avslutning av installations programmet](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivera utvärderings prenumeration för Microsoft 365

>[!NOTE]
>Om du registrerar dig för en utvärderings version får du 25 användar licenser att använda i en månad. Mer information finns i [prova eller köpa en M365-prenumeration](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .

1. Från [Microsoft 365 administrations Center](https://admin.microsoft.com/)klickar du på **fakturering** och navigerar sedan till **inköps tjänster**.

2. Välj **Microsoft 365 E5** och klicka på **Starta gratis prov period**. 

   ![Bild of_Microsoft 365 E5 gratis prov sida](../../media/mtp-eval-24.png)

3. Välj verifierings inställningar: via SMS eller ett samtal. När du har bestämt dig anger du telefonnumret, väljer **SMS** eller **Ring mig** beroende på ditt val.

   ![Bild of_Microsoft 365 E5 gratis prov sida med förfrågan om kontakt information för att skicka kod som visar att du inte är en robot](../../media/mtp-eval-25.png)
 
4. Ange verifierings koden och klicka på **starta din gratis prov period**.

   ![Bild of_Microsoft 365 E5 gratis prov sida där du kan fylla i verifierings kod systemet skickade för att bevisa att du inte är en robot](../../media/mtp-eval-26.png)

5. Klicka på **prova nu** för att bekräfta utvärderings versionen av Microsoft 365 E5.

   ![Bild of_Microsoft 365 E5 gratis prov sida där du bör stänga knappen prova nu för att starta](../../media/mtp-eval-27.png)
 
6. Gå till **administrations centret för Microsoft 365** -  >  **användare**  >  **Active users**. Välj ditt användar konto, Välj **Hantera produkt licenser** och byt sedan licensen från Office 365 E5 till **Microsoft 365 E5**. Klicka på **Spara**.

   ![Bild of_Microsoft 365 administrations Center sida där du kan välja Microsoft 365 E5-licens](../../media/mtp-eval-28.png)
 
7. Välj det globala administratörs kontot igen och klicka sedan på **hantera användar namn**.

   ![Bild of_Microsoft 365 administrations Center sida där du kan välja konto och sedan hantera användar namn](../../media/mtp-eval-29.png)

8. Skriver Ändra domänen från *onmicrosoft.com* till din egen domän, beroende på vad du valde i föregående steg. Klicka på **Spara ändringar**.

   ![Bild of_Microsoft 365 administrations Center sida där du kan ändra din domäns preferens](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nästa steg
|![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png) <br>[Steg 3: Konfigurera & inbyggt](config-mtpeval.md) | Konfigurera varje Microsoft 365 Defender-pelare för utvärderings labb eller pilot miljö för Microsoft 365 Defender och få slut punkter.
|:-------|:-----|
