---
title: Konfigurera testlabbeta för Microsoft Threat Protection
description: Öppna Microsoft 365 Security Center och konfigurera sedan testlabbeta Microsoft Threat Protection
keywords: Testinställning för Microsoft Threat Protection, prova microsoft threat protection, microsoft threat protection utvärdering lab setup
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049621"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Konfigurera testlabbeta för Microsoft Threat Protection 

**Gäller:**
- Microsoft Hotskydd 


Att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den är en trefasprocess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbered utvärderingslabbet för Microsoft Threat Protection" />
      <br/>Fas 1: Förbered</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera microsofts utvärderingslabb för hotskydd" />
      <br/>Fas 2: Installation</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och dina slutpunkter" />
      <br/>Fas 3: Konfigurera & ombord</a><br>
</td>


  </tr>
</table>

Du befinner dig för närvarande i ställningsfasen. Gör de första stegen för att komma åt Microsoft 365 Security Center och konfigurera sedan testlabbets miljö.

Registrera dig för en Office 365- eller Azure Active Directory-prenumeration för att generera en *.onmicrosoft.com-klient* som du kan använda för att registrera dig för din Microsoft 365 E5-licens. 

>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa utvärderingsversionen av Office 365 E5-utvärderingsversionen av klientversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av

I den här fasen guidas du till:
- Skapa en office 365 E5-utvärderingsklient
- Aktivera testprenumeration för Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Skapa en office 365 E5-utvärderingsklient
>[!NOTE]
>Om du redan har en befintlig Office 365- eller Azure Active Directory-prenumeration kan du hoppa över stegen för att skapa utvärderingsversionen av Office 365 E5-utvärderingsversionen av klientversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av utvärderingsversionen av

1. Gå till [produktportalen för Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) och välj **Kostnadsfri utvärderingsversion**.
![Bild of_page](../../media/mtp-eval-9.png) <br>
  
2. Slutför provregistreringen genom att ange din e-postadress (personlig eller företagsadress). Klicka på **Konfigurera konto**.
![Bild of_page](../../media/mtp-eval-10.png) <br> 

3. Fyll i förnamn, efternamn, företagstelefonnummer, företagsnamn, företagsstorlek och land eller region.  
<br>![Bild of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Det land eller den region som du anger här avgör vilken datacenterregion ditt Office 365 ska vara värd för.
  
4. Välj din verifieringsinställning: via ett sms eller samtal. Klicka på **Skicka verifieringskod**. 
![Bild of_page](../../media/mtp-eval-12.png) <br>

5. Ange det anpassade domännamnet för din klient organisation och klicka sedan på **Nästa**.
<br>![Bild of_page](../../media/mtp-eval-13.png) <br>
 
6. Ställ in den första identiteten som kommer att vara en global administratör för klienten. Fyll i **namn** och **lösenord**. Klicka på **Registrera dig**.
![Bild of_page](../../media/mtp-eval-14.png) <br>
C
7. Klicka på **Gå till installationsprogrammet** för att slutföra utvärderingsversionen av Office 365 E5 E5-utvärderingsversionen av klientversionen.
<br>![Bild of_page](../../media/mtp-eval-15.png) <br>

8. Anslut företagsdomänen till Office 365-klienten. [Valfritt] Välj **Anslut en domän som du redan äger** och skriv in ditt domännamn. Klicka på **Nästa**.
<br>![Bild of_page](../../media/mtp-eval-16.png) <br>
 
9. Du måste lägga till en TXT- eller MX-post för att validera domänägarskapet. När du har lagt till TXT- eller MX-posten i domänen väljer du **Verifiera**.
<br>![Bild of_page](../../media/mtp-eval-17.png) <br>
 
10. [Valfritt] Skapa fler användarkonton för din klient. Du kan hoppa över det här steget genom att klicka på **Nästa**.
![Bild of_page](../../media/mtp-eval-18.png) <br>
 
11. [Valfritt] Ladda ned Office-appar. Klicka på **Nästa** om du vill hoppa över det här steget. 
<br>![Bild of_page](../../media/mtp-eval-19.png) <br>

12. [Valfritt] Migrera e-postmeddelanden. Återigen kan du hoppa över det här steget.
<br>![Bild of_page](../../media/mtp-eval-20.png) <br>
 
13. Välj onlinetjänster. Välj **Exchange** och klicka på **Nästa**. 
<br>![Bild of_page](../../media/mtp-eval-21.png) <br>

14. Lägg till MX-, CNAME- och TXT-poster i domänen. När du är klar väljer du **Verifiera**.
<br>![Bild of_page](../../media/mtp-eval-22.png) <br>
 
15. Grattis, du har slutfört etableringen av din Office 365-klientorganisation.
<br>![Bild of_page](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivera testprenumeration för Microsoft 365

>[!NOTE]
>När du registrerar dig för en utvärderingsversion får du 25 användarlicenser att använda under en månad. Mer information finns i [Prova eller köp en M365-prenumeration.](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1)

1. I [Administrationscenter för Microsoft 365](https://admin.microsoft.com/)klickar du på **Fakturering** och navigerar sedan till **Köptjänster**.

2. Välj **Microsoft 365 E5** och klicka på **Starta kostnadsfri utvärderingsversion**. 
![Bild of_page](../../media/mtp-eval-24.png) <br>

3. Välj din verifieringsinställning: via ett sms eller samtal. När du har bestämt dig anger du telefonnumret, väljer **Sms:a mig** eller **Ring mig** beroende på ditt val.
![Bild of_page](../../media/mtp-eval-25.png) <br>
 
4. Ange verifieringskoden och klicka på **Starta din kostnadsfria utvärderingsversion**. 
<br>![Bild of_page](../../media/mtp-eval-26.png) <br>

5. Klicka på **Försök nu** om du vill bekräfta testversionen av Microsoft 365 E5.
<br>![Bild of_page](../../media/mtp-eval-27.png) <br>
 
6. Gå till **Microsoft 365 Admin Center** > **Användare** > Aktiva**användare**. Välj ditt användarkonto, välj **Hantera produktlicenser**och byt sedan licensen från Office 365 E5 till **Microsoft 365 E5**. Klicka på **Spara**.
![Bild of_page](../../media/mtp-eval-28.png) <br>
 
7. Välj det globala administratörskontot igen och klicka sedan på **Hantera användarnamn**.
<br>![Bild of_page](../../media/mtp-eval-29.png) <br>

8. [Valfritt] Ändra domänen från *onmicrosoft.com* till din egen domän – beroende på vad du valde i föregående steg. Klicka på **Spara ändringar**.
<br>![Bild of_page](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Nästa steg
||| |:-------|:-----|config-onboard.png) <br>[Fas 3: Konfigurera & ombord](config-mtpeval.md) | Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och dina slutpunkter.
