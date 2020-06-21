---
title: Konfigurera Microsoft Threat Protection-pelare för testlabbets miljö
description: Konfigurera Microsoft Threat Protection-pelare, Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP för teststudiemiljön
keywords: konfigurera Testversionen av Microsoft Threat Protection, testkonfigurationen för Microsoft Threat Protection, konfigurera Microsoft Threat Protection-pelare, Microsoft Threat Protection-pelare
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
ms.openlocfilehash: ba603f3703a7d4b6df567f8299af9f1804e42b96
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702576"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a>Konfigurera Microsoft Threat Protection-pelare för testlabbeta

**Gäller:**
- Microsoft Hotskydd


Att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den är en trefasprocess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbered testlabbeta för Microsoft Threat Protection" />
      <br/>Fas 1: Förbered</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera testlabbmiljön för Microsoft Threat Protection" />
      <br/>Fas 2: Installation</a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera varje Microsoft Threat Protection-pelare för testlabbmiljön för Microsoft Threat Protection och slutpunkter ombord" />
      <br/>Fas 3: Konfigurera & ombord</a><br>
</td>


  </tr>
</table>

Du befinner dig för närvarande i konfigurationsfasen.


Förberedelse är nyckeln till en lyckad distribution. I den här artikeln får du vägledning om de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pelare för skydd av Microsofts hotskydd
Microsoft Threat Protection består av fyra pelare. Även om en pelare redan kan ge värde till nätverksorganisationens säkerhet, ger aktivering av de fyra Microsoft Threat Protection-pelarna din organisation mest värde.

![Image of_Microsoft Threat Protection-lösning för användare, Azure Advanced Threat Protection, för slutpunkter Microsoft Defender Advanced Threat Protection, för molnappar, Microsoft Cloud App Security och för data, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png) <br>

Det här avsnittet hjälper dig att konfigurera:
-   Office 365 Avancerat skydd
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Avancerat skydd


## <a name="configure-office-365-advanced-threat-protection"></a>Konfigurera avancerat hotskydd för Office 365
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat förhandsskydd för Office 365.Skip this step if you have already enabled Office 365 Advanced Threat Protection. 

Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper till att avgöra några av dessa inställningar. När du kör som administratör i din klientorganisation, get-ORCAReport kommer att bidra till att generera en bedömning av anti-spam, anti-phish och andra inställningar meddelandehygien. Du kan ladda ner denna modul från https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Policy**.
![Sidan Of_Office 365 Security & Compliance Center Threat management policy](../../media/mtp-eval-32.png) <br>
 
2. Klicka på **ATP-anti-nätfiske,** välj **Skapa** och fyll i principnamnet och beskrivningen. Klicka på **Nästa**.
![Bild of_Office 365 Security & Compliance Center anti-phishing-policysida där du kan namnge din policy](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Redigera din avancerade ATP-policy mot nätfiske. Ändra **avancerad nätfisketröskel** till **2 - Aggressiv**.
<br>

3. Klicka på den nedrullningsbara menyn **Lägg till ett villkor** och välj domänen/domänerna som mottagardomän. Klicka på **Nästa**.
![Bild of_Office 365 Security & Compliance Center anti-phishing policy sida där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png) <br>
 
4. Granska dina inställningar. Klicka på **Skapa den här principen** för att bekräfta. 
![Bild of_Office 365 Security & Compliance Center anti-phishing policy sida där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png) <br>
 
5. Välj **ATP Säkra bilagor** och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**  
![Bild of_Office sidan 365 Security & Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png) <br>

6. Klicka på ikonen + om du vill skapa en ny princip för säker bifogade filer och tillämpa den som mottagaredomän på dina domäner. Klicka på **Spara**.
![Bild of_Office 365 Security & Compliance Center sida där du kan skapa en ny skapa en ny säker bilaga princip](../../media/mtp-eval-37.png) <br>
 
7. Välj sedan **atp-principen för säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.

8. Kontrollera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade. Mer information finns i inställningar för [säkra länkar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) Klicka på **Spara**. 
![Bild of_Office 365 Sidan Security & Compliance Center som visar att alternativet Spåra inte när användarna klickar säkert inte är markerat](../../media/mtp-eval-38.png) <br>

9. Välj sedan policyn **mot skadlig kod,** välj standardikonen och välj pennikonen.

10. Klicka på **Inställningar** och välj **Ja och använd standardmeddelandetexten** för att aktivera **svar på identifiering av skadlig kod**. Aktivera **filtret Vanliga typer av bifogade filer.** Klicka på **Spara**.
<br>![Bild of_Office sidan 365 Security & Compliance Center som visar att svar på identifiering av skadlig kod är aktiverat med standardmeddelande och filtret för vanliga typer av bifogade filer är aktiverat](../../media/mtp-eval-39.png) <br>
  
11. Navigera till [Office 365 Security &](https://protection.office.com/homepage)  >  **Search**  >  **Audit-loggsökning för** efterlevnadscenter och aktivera granskning.  
![Bild of_Office 365 Säkerhets- & compliance center-sidan där du kan aktivera granskningsloggsökningen](../../media/mtp-eval-40.png) <br>

12. Integrera Office 365 ATP med Microsoft Defender ATP. Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **management**  >  **Explorer** och välj **WDATP-inställningar** längst upp till höger på skärmen. Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning .
![Bild of_Office 365 Security & Compliance Center sida där du kan aktivera Windows Defender ATP-anslutning](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Konfigurera Avancerat hotskydd för Azure
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Azure Advanced Threat Protection


1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > välja Fler **resurser**Azure Advanced  >  **Threat Protection**.
![Bild of_Microsoft 365 Security Center-sida där det finns ett alternativ för att öppna Azure Advanced Threat Protection](../../media/mtp-eval-42.png) <br>

2. Klicka på Skapa om du vill starta guiden Avancerat skydd mot Azure.Click **Create** to start the Azure Advanced Threat Protection wizard. 
<br>![Bild of_Azure guidesida för avancerat skydd mot hot där du ska klicka på Knappen Skapa](../../media/mtp-eval-43.png) <br>

3. Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.  
![Välkommen sida för of_Azure avancerat skydd mot skydd](../../media/mtp-eval-44.png) <br>

4. Ange lokala autentiseringsuppgifter för Active Directory. Detta kan vara alla användarkonton som har läsbehörighet till Active Directory.
![Bild of_Azure sidan Advanced Threat Protection Directory services där du bör placera dina autentiseringsuppgifter](../../media/mtp-eval-45.png) <br>

5. Välj sedan **Hämta sensorinstallation och** överför filen till domänkontrollanten. 
![Bild of_Azure sidan Avancerat skydd mot hot där du kan välja Inställningar för hämtningssensor](../../media/mtp-eval-46.png) <br>

6. Kör installationen av Azure ATP-sensor och börja följa guiden.
<br>![Bild of_Azure sidan Avancerat skydd mot hot där du ska klicka bredvid för att följa guiden Azure ATP-sensor](../../media/mtp-eval-47.png) <br>
 
7. Klicka på **Nästa** vid sensordistributionstypen.
<br>![Bild of_Azure sidan Avancerat skydd mot hot där du ska klicka bredvid för att följa guiden Azure ATP-sensor](../../media/mtp-eval-48.png) <br>
 
8. Kopiera åtkomstnyckeln som du behöver för att ange den nästa i guiden.
![Bild of_the sensorsida där du ska kopiera åtkomstnyckeln som du behöver ange på nästa guidesida för Azure ATP-sensorinstallation](../../media/mtp-eval-49.png) <br>
 
9. Kopiera åtkomstnyckeln till guiden och klicka på **Installera**. 
<br>![Bild of_Azure Avancerad hotskydd Azure ATP sensor guide sida där du bör ange åtkomstnyckeln och klicka sedan på installationsknappen](../../media/mtp-eval-50.png) <br>

10. Grattis, du har konfigurerat Azure Advanced Threat Protection på domänkontrollanten.
![Avbildning of_Azure Avancerat skydd Mot Azure ATP-sensorguiden installationsavslutning där du ska klicka på knappen Slutför](../../media/mtp-eval-51.png) <br>
 
11. Under avsnittet [Azure Azure ATP-inställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlingsknappen. Klicka på **Spara**. 
![Avbildning of_the azure azure-atp-inställningssida där du ska aktivera Windows Defender ATP-växlingsknappen](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP har bytt namn till Microsoft Defender ATP. Omprofilering förändringar över alla våra portaler håller på att rullas ut för konsekvens.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurera Säkerhet för Microsoft Cloud-appar
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security. 

1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info)Fler  >  **resurser**Microsoft Cloud  >  **App Security**.
![Bild of_Microsoft 365 Security Center-sida där du kan se Microsoft Cloud App-kort och klicka på knappen Öppna](../../media/mtp-eval-53.png) <br>

2. Vid informationsfrågan om att integrera Azure ATP väljer du **Aktivera Azure ATP-dataintegration**. 
<br>![Avbildning of_the informationsfråga för att integrera Azure ATP där du bör välja länken Aktivera Azure ATP-dataintegration](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Om du inte ser den här prompten kan det innebära att din Azure ATP-dataintegrering redan har aktiverats. Om du är osäker kontaktar du dock IT-administratören för att bekräfta. 

3. Gå till **Inställningar**, aktivera växlingsknappen för **Azure ATP-integrering** och klicka sedan på **Spara**. 
![Bild of_the inställningssida där du ska aktivera växlingsknappen för Azure ATP-integrering och klicka sedan på spara](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>För nya Azure ATP-instanser aktiveras den här integrationsväxlingen automatiskt. Bekräfta att din Azure ATP-integrering har aktiverats innan du går vidare till nästa steg.
 
4. Under inställningarna för molnidentifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integreringen. Klicka på **Spara**.
![Bild of_the Microsoft Defender ATP-sida där kryssrutan blockera oregistrerade appar under Microsoft Defender ATP-integrering är markerad. Klicka på Spara.](../../media/mtp-eval-56.png) <br>

5. Under Molnidentifieringsinställningar väljer du **Användarberikande**och aktiverar sedan integreringen med Azure Active Directory.
![Avbildning av avsnittet Användares anrikning där kryssrutan berikade identifierade användaridentifierare med Azure Active Directory-användarnamn är markerat](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Konfigurera avancerat hotskydd för Microsoft Defender
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender Advanced Threat Protection.

1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info)Mer  >  **resurser**Microsoft Defender  >  **Security Center**. Klicka på **Öppna**.
<br>![Bild of_Microsoft alternativet Defender Security Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png) <br>
 
2. Följ guiden Avancerat skydd mot microsoft defender.Follow the Microsoft Defender Advanced Threat Protection wizard. Klicka på **Nästa**. 
<br>![Sidan Välkommen of_the Microsoft Defender Security Center](../../media/mtp-eval-59.png) <br>

3. Välj baserat på önskad plats för datalagring, datalagringsprincip, organisationsstorlek och opt-in för förhandsversionsfunktioner. 
<br>![Bild of_the sida för att välja datalagringsland, lagringsprincip och organisationsstorlek. Klicka på nästa när du är klar med markeringen.](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>Du kan inte ändra vissa inställningar, till exempel datalagringsplats, efteråt. 
<br>

Klicka på **Nästa**. 

4. Klicka på **Fortsätt** så etablerar microsoft defender ATP-klienten.
<br>![Bild of_the sida som uppmanar dig att klicka på knappen Fortsätt för att skapa din molninstans](../../media/mtp-eval-61.png) <br>

5. Ombord på dina slutpunkter via grupprinciper, Microsoft Slutpunktshanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP. För enkelhetens skull använder den här guiden det lokala skriptet.

6. Klicka på **Hämta paket** och kopiera introduktionsskriptet till slutpunkterna.  
<br>![Bild of_page du uppmanas att klicka på knappen Hämta paket för att kopiera introduktionsskriptet till slutpunkten eller slutpunkterna](../../media/mtp-eval-62.png) <br>

7. På slutpunkten kör du introduktionsskriptet som administratör och väljer Y.
<br>![Bild of_the kommandorad där du kör introduktionsskriptet och väljer Y att fortsätta](../../media/mtp-eval-63.png) <br>

8. Grattis, du har onboarded din första slutpunkt.  
<br>![Bild of_the kommandorad där du får en bekräftelse på att du har lagt till din första slutpunkt. Tryck på valfri tangent för att fortsätta](../../media/mtp-eval-64.png) <br>

9. Kopiera in identifieringstestet från Atp-guiden Microsoft Defender.
<br>![Bild of_the köra ett teststeg där du bör klicka på Kopiera för att kopiera det identifieringstestskript som du bör klistra in i kommandotolken](../../media/mtp-eval-65.png) <br>

10. Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör det. 
<br>![Bild of_command fråga om var du ska kopiera PowerShell-skriptet till en upphöjd kommandotolk och köra den](../../media/mtp-eval-66.png) <br>

11. Välj **Börja använda Microsoft Defender ATP** i guiden.
<br>![Bild of_the bekräftelsefråga från guiden där du bör klicka på Börja använda Microsoft Defender ATP](../../media/mtp-eval-67.png) <br>
 
12. Besök [Microsoft Defender Security Center](https://securitycenter.windows.com/). Gå till **Inställningar** och välj sedan **Avancerade funktioner**. 
<br>![Bild of_Microsoft menyn Inställningar för Defender Security Center där du bör välja Avancerade funktioner](../../media/mtp-eval-68.png) <br>

13. Aktivera integreringen med **Azure Advanced Threat Protection**.  
<br>![Avbildning of_Microsoft Defender Security Center Avancerade funktioner, Azure Advanced Threat Protection alternativ växla som du behöver för att aktivera](../../media/mtp-eval-69.png) <br>

14. Aktivera integreringen med **Office 365 Threat Intelligence**.
<br>![Bild of_Microsoft Defender Security Center Avancerade funktioner, Office 365 Threat Intelligence-alternativet växla som du behöver aktivera](../../media/mtp-eval-70.png) <br>

15. Aktivera integrering med **Microsoft Cloud App Security**.
<br>![Bild of_Microsoft Defender Security Center Avancerade funktioner, Microsoft Cloud App Security-alternativet växla som du behöver aktivera](../../media/mtp-eval-71.png) <br>

16. Bläddra nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.
<br>![Knappen Bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png) <br>

## <a name="turn-on-microsoft-threat-protection"></a>Aktivera Microsoft Hotskydd
>[!NOTE]
>Från och med den 1 juni 2020 aktiverar Microsoft automatiskt Microsoft Threat Protection-funktioner för alla berättigade klienter. Mer information finns i den här [artikeln i Microsoft Tech Community om licensberättigande.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 
<br>

Gå till [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Navigera till **Inställningar** och välj sedan **Microsoft Threat Protection**.
<br>![Bild of_Microsoft alternativ för skydd av hot från sidan Inställningar för Microsoft 365 Security Center](../../media/mtp-eval-72b.png) <br>

Grattis! Du har precis skapat testlabbmiljön för Microsoft Threat Protection! Du kan nu simulera en attack och se hur cross-produktfunktionerna identifierar, skapar aviseringar och automatiskt svarar på en fillös attack på en slutpunkt.

## <a name="next-steps"></a>Nästa steg
[Generera en testavisering](generate-test-alert.md).
