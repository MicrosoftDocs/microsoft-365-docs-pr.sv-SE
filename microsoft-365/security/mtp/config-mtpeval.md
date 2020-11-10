---
title: Konfigurera Microsoft 365 Defender-pelaren för utvärderings labbet eller pilot miljön
description: Konfigurera Microsoft 365 Defender-pelaren, till exempel Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App-säkerhet och Microsoft Defender för slut punkten, för utvärderings labbet eller pilot miljön.
keywords: Konfigurera utvärderings versionen av Microsoft Threat Protection, test version av Microsoft Threat Protection, konfigurera Microsoft Threat Protection Pilot-projekt, konfigurera Microsoft Threat Protection-spel, Microsoft Threat Protection-pelare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 5259c7b74446ad273ff9b1ae0baccd339e34baa3
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984956"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurera Microsoft 365 Defender-pelaren för utvärderings labbet eller pilot miljön

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
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Konfigurera utvärderings labb eller pilot miljö för Microsoft 365 Defender" />
      <br/>Fas 2: konfiguration </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera varje Microsoft 365 Defender-pelare för utvärderings labb och drift slut punkter för Microsoft 365 Defender" />
      <br/>Steg 3: Konfigurera & inbyggt </a><br>
</td>
  </tr>
</table>

Du är för närvarande i konfigurations fasen.


Förberedelsen är viktig för eventuell distribution. I den här artikeln vägleder vi dig på de Points du måste tänka på när du förbereder dig för att distribuera Microsoft Defender för slut punkten.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-pelare
Microsoft 365 Defender består av fyra pelare. Även om en pelare redan kan ge ett värde till din organisations säkerhet i ditt nätverk, ger de fyra hög365 Defender-stenarna det mest aktuella värdet.

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet för slut punkter Microsoft Defender för slut punkter, moln program, Microsoft Cloud App-säkerhet och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

I det här avsnittet får du hjälp att konfigurera:
-   Microsoft Defender för Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender för Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>Konfigurera Microsoft Defender för Office 365

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Defender för Office 365. 

Det finns en PowerShell-modul som heter *Office 365 Advanced Threat Protection (Orca)* som hjälper dig att avgöra vissa av de här inställningarna. När du kör som administratör i klient organisationen kan du med ORCAReport få en utvärdering av skräp post, anti-Phish och andra inställningar för meddelande hygien. Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  policy för **hantering** av villkor för efterlevnad  >  **Policy**.

   ![Bild of_Office 365 säkerhets & policy för Threat Management-hantering](../../media/mtp-eval-32.png)
 
2. Klicka på **nätfiske** , Välj **skapa** och fyll i princip namnet och beskrivningen. Klicka på **Nästa**.

   ![Bild of_Office 365 säkerhet & policy för skydd mot Office-nätfiske där du kan namnge policyn](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Redigera din avancerade policy för anti-nätfiske i Microsoft Defender för Office 365. Ändra den **avancerade nät fiske tröskeln** till **2-aggressivt**.

3. Klicka på den nedrullningsbara menyn **Lägg till en villkors** lista och välj din domän (er) som mottagar domän. Klicka på **Nästa**.

   ![Bild of_Office 365 säkerhet & policy för skydd mot server för uppringnings Center där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png)
 
4. Granska dina inställningar. Klicka på **skapa den här principen** för att bekräfta. 

   ![Bild of_Office 365 säkerhets & policy för skydd mot efterlevnad för nätfiske där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)
 
5. Välj **bifogade filer** och välj alternativet **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .

   ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)

6. Klicka på ikonen + för att skapa en ny princip för säker bifogad fil, tillämpa den som mottagar domän i domänerna. Klicka på **Spara**.

   ![Bild of_Office 365 säkerhets & sidan Compliance Center, där du kan skapa en ny princip för säker bifogad fil](../../media/mtp-eval-37.png)
 
7. Välj sedan principen för **säkra länkar** och klicka sedan på Penn ikonen för att redigera standard principen.

8. Kontrol lera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade. Se [Inställningar för Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) . Klicka på **Spara**. 

   ![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att alternativet spåra inte när användare klickar på säker är inte markerat](../../media/mtp-eval-38.png)

9. Välj sedan standard principen för att förhindra **mot skadlig program vara** och välj sedan Penn ikonen.

10. Klicka på **Inställningar** och välj **Ja och Använd standard meddelande texten** för att aktivera **identifiering av skadlig program vara**. Aktivera **filtret vanliga typer av bifogade filer** . Klicka på **Spara**.

    ![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att svaret om skadlig program vara är aktiverat med standard meddelande och att filtret vanliga bilage typer är aktiverat](../../media/mtp-eval-39.png)
  
11. Navigera till [Office 365-säkerhets & Compliance Center](https://protection.office.com/homepage)  >  **Sök** efter  >  **gransknings loggs ökning** och aktivera granskning.

    ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera gransknings loggs ökningen](../../media/mtp-eval-40.png)

12. Integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten. Navigera till [Office 365-säkerhets & efterlevnad för Compliance Center](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** och välj **Microsoft Defender för slut punkts inställningar** i det övre högra hörnet av skärmen. I dialog rutan Defender för slut punkts anslutning aktiverar **du Anslut till Microsoft Defender för slut punkt**.

    ![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera Microsoft Defender för slut punkts anslutning på](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Konfigurera Microsoft Defender för identitet

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender för identitet

1. Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info) > Välj **fler resurser**  >  **Microsoft Defender för identitet**.

   ![Bild of_Microsoft 365 säkerhets Center sida där det finns ett alternativ för att öppna Microsoft Defender för identitet](../../media/mtp-eval-42.png)

2. Klicka på **skapa** för att starta Microsoft Defender för identitets guiden. 

   ![Bild of_Microsoft Defender för guiden för identitet där du bör Klicka på knappen Skapa](../../media/mtp-eval-43.png)

3. Välj **ge ett användar namn och lösen ord för att ansluta till Active Directory-skogen**.  

   ![Bild of_Microsoft Defender för välkomst sida](../../media/mtp-eval-44.png)

4. Ange lokala inloggnings uppgifter för Active Directory. Det kan vara vilket användar konto som helst som har Läs åtkomst till Active Directory.

   ![Bild of_Microsoft Defender för identitets katalog tjänster där du ska ange dina uppgifter](../../media/mtp-eval-45.png)

5. Välj sedan **Ladda ned sensor konfiguration** och överföra fil till domänkontrollanten.

   ![Bild of_Microsoft Defender för identitets sida där du kan välja nedladdnings sensor inställning](../../media/mtp-eval-46.png)

6. Kör installations programmet för Microsoft Defender för identitets sensor och börja följa guiden.

   ![Bild of_Microsoft Defender för identitets sida där du bör Klicka på Nästa för att följa Microsoft Defender-guiden för identitets sensor](../../media/mtp-eval-47.png)
 
7. Klicka på **Nästa** på sensor distributions typen.

   ![Bild of_Microsoft Defender för identitets sida där du bör klicka bredvid gå till nästa sida](../../media/mtp-eval-48.png)
 
8. Kopiera snabb tangenten eftersom du måste ange den intill i guiden.

   ![Bild of_the sensorer-sida där du vill kopiera den snabb åtkomst-knapp som du måste ange på nästa sida i guiden Konfigurera Microsoft Defender för identitets sensor](../../media/mtp-eval-49.png)
 
9. Kopiera till guiden och klicka på **Installera**. 

   ![Bild of_Microsoft Defender för guiden för identitets sensor där du bör tillhandahålla åtkomst-tangenten och sedan klicka på knappen Installera](../../media/mtp-eval-50.png)

10. Grattis! du har konfigurerat Microsoft Defender för din domänkontrollant.

    ![Bild of_Microsoft Defender för guiden för identitets sensor installation, där du bör Klicka på knappen Slutför](../../media/mtp-eval-51.png)
 
11. Under [Microsoft Defender för identitets](https://go.microsoft.com/fwlink/?linkid=2040449) inställningar väljer du * * Microsoft Defender för slut punkt * * och aktiverar sedan växlingen. Klicka på **Spara**. 

    ![Bild of_the inställningar för inloggnings sidan för Microsoft Defender för att du ska aktivera växla mellan Microsoft Defender för slut punkt](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP har ändrats som Microsoft Defender för slut punkt. Att ändra dina ändringar i alla portaler blir då mer konsekvens.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurera säkerhet för Microsoft Cloud App

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat säkerhet för Microsoft Cloud App. 

1. Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Cloud App-säkerhet**.

   ![Bild of_Microsoft 365 säkerhets Center sida där du kan se Microsoft Cloud App Card och ska klicka på knappen Öppna](../../media/mtp-eval-53.png)

2. I rutan information om hur du integrerar Microsoft Defender för identiteter väljer du **aktivera Microsoft Defender för identitets data integrering**.
  
   ![Of_the om du vill integrera Microsoft Defender för en identitet där du bör välja länken Aktivera Microsoft Defender för identitets data integrering](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Om du inte ser den här uppmaningen kan det betyda att din Microsoft Defender för identitets data integrering redan har Aktiver ATS. Om du är osäker kontaktar du IT-administratören för att bekräfta. 

3. Gå till **Inställningar** , aktivera växla mellan **Microsoft Defender för identitets integrering** och klicka sedan på **Spara**. 

   ![Sidan image of_the inställningar där du bör aktivera växla mellan Microsoft Defender för identitets integrering och klicka på Spara.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > För nya Microsoft Defender för identitets instanser är denna växel växling automatiskt aktive rad. Kontrol lera att din Microsoft Defender för identitets integrering har Aktiver ATS innan du fortsätter till nästa steg.
 
4. Under Inställningar för moln identifiering väljer du **Microsoft Defender för slut punkts integrering** och aktiverar integrationen. Klicka på **Spara**.

   ![Bild of_the Microsoft Defender för slut punkts sida där kryss rutan blockera program utan sanktioner under Microsoft Defender för slut punkts integrering är markerad. Klicka på Spara.](../../media/mtp-eval-56.png)

5. Under Inställningar för moln identifiering väljer du **användar upplevelse** och aktiverar integrationen med Azure Active Directory.

   ![Bild av avsnittet användar berikning där kryss rutan utökad identifiering av användar identifierare med Azure Active Directory-username är markerad](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Defender för slut punkten

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender för slut punkter.

1. Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Defender säkerhets Center**. Klicka på **Öppna**.

   ![Bild of_Microsoft Defender säkerhets Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png)
 
2. Följ instruktionerna i Microsoft Defender för slut punkter. Klicka på **Nästa**. 

   ![Bild of_the sidan Välkommen till Microsoft Defender säkerhets Center](../../media/mtp-eval-59.png)

3. Välj baserat på din önskade lagrings plats för data, bevarande princip för data, organisations storlek och val för förhands gransknings funktioner.

   ![Bild of_the sida för att välja data lagrings land, bevarande princip och organisations storlek. Klicka på Nästa när du är klar med valet.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Du kan inte ändra vissa inställningar, till exempel data lagrings plats, efteråt. 

   Klicka på **Nästa**. 

4. Klicka på **Fortsätt** så tillhandahåller Microsoft Defender för slut punkts klient organisation.

   ![Bild of_the sida där du uppmanas att klicka på knappen Fortsätt för att skapa din moln instans](../../media/mtp-eval-61.png)

5. Ta fram dina slut punkter via grup principer, Microsoft slut punkts hanteraren eller genom att köra ett lokalt skript till Microsoft Defender för slut punkt. För enkelhetens skull använder den här guiden det lokala skriptet.

6. Klicka på **Ladda ned paket** och kopiera registrerings skriptet till din slut punkt (er).

   ![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera det inbyggda skriptet till slut punkten eller slut punkterna](../../media/mtp-eval-62.png)

7. Kör skriptet som administratör på slut punkten och välj Y. 

   ![Bild of_the kommando rad där du kör det inbyggda skriptet och väljer sedan Y för att fortsätta](../../media/mtp-eval-63.png)

8. Grattis! du har öppnat din första slut punkt.

   ![Bild of_the kommando rad där du får bekräftelse på att du har öppnat din första slut punkt. Tryck på en tangent för att fortsätta](../../media/mtp-eval-64.png)

9. Kopiera – klistra in identifierings testet från Microsoft Defender för slut punkts guiden.

   ![Bild of_the kör ett identifierings test steg där du bör Klicka på Kopiera för att kopiera det identifierings test som du vill klistra in i kommando tolken](../../media/mtp-eval-65.png)

10. Kopiera PowerShell-skriptet till en upphöjd kommando tolk och kör det. 

    ![Bild of_command fråga var du bör kopiera PowerShell-skriptet till en upphöjd kommando tolk och köra det](../../media/mtp-eval-66.png)

11. Välj **börja använda Microsoft Defender för slut punkt** från guiden.

    ![Bild of_the bekräfta uppmaning i guiden där du bör Klicka på börja använda Microsoft Defender för slut punkt](../../media/mtp-eval-67.png)
 
12. Gå till [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/). Gå till **Inställningar** och välj sedan **avancerade funktioner**. 

    ![Bild of_Microsoft Defender säkerhets Center-menyn inställningar där du bör välja avancerade funktioner](../../media/mtp-eval-68.png)

13. Aktivera integrationen med **Microsoft Defender för identiteten**.  

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Microsoft Defender för identitet som du måste aktivera](../../media/mtp-eval-69.png)

14. Aktivera integrationen med **Office 365 Threat Intelligence**.

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Office 365 Threat Intelligence växla till att aktivera](../../media/mtp-eval-70.png)

15. Aktivera integrering med **säkerhet för Microsoft Cloud App**.

    ![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, säkerhets alternativ för Microsoft Cloud App](../../media/mtp-eval-71.png)

16. Rulla nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.

    ![Knappen bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Starta tjänsten Microsoft 365 Defender

>[!NOTE]
>Från och med den 1 juni 2020, aktiverar Microsoft automatiskt Microsoft 365 Defender-funktioner för alla kvalificerade klient organisationer. Mer information finns i den här [artikeln i Microsoft Tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) . 


Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage). Navigera till **Inställningar** och välj sedan **Microsoft 365 Defender**.

![Bild of_Microsoft 365 Defender alternativ skärm bild från sidan Inställningar för säkerhets Center för Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

En mer omfattande vägledning finns i [aktivera Microsoft 365 Defender](mtp-enable.md). 

Grattis! Du har just skapat en utvärderings version av Microsoft 365 Defender eller pilot miljö! Nu kan du bekanta dig med Microsoft 365 Defender-användargränssnittet! Se vad du kan lära dig från följande Microsoft 365 Defender interaktiva guide och hur du använder varje instrument panel för dina dagliga säkerhets åtgärder.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Sedan kan du simulera en attack och se hur funktionerna för kors produkten identifieras, skapa aviseringar och automatiskt svara på en fillös attack på en slut punkt.

## <a name="next-step"></a>Nästa steg
|![Fasen för attack simulering](../../media/mtp/run-sim.png) <br>[Fasen för attack simulering](mtp-pilot-simulate.md) | Kör angrepps simuleringen för din Microsoft 365 Defender pilot miljö.
|:-------|:-----|
