---
title: Konfigurera Microsoft Threat Protection-pelare för testlabbetamiljön
description: Konfigurera Microsoft Threat Protection-pelare, Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP för testlabbetamiljön
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049515"
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
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Förbereda testlabbeta för Microsoft Threat Protection" />
      <br/>Fas 1: Förbered</a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Konfigurera testlabbeta för Microsoft Threat Protection" />
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


Förberedelse är nyckeln till en lyckad distribution. I den här artikeln får du vägledning på de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Pelare för skydd av Microsofts hotskydd
Microsoft Threat Protection består av fyra pelare. Även om en pelare redan kan ge värde till nätverksorganisationens säkerhet, ger aktivering av de fyra Microsoft Threat Protection-pelarna din organisation mest värde.

![Bild of_page](../../media/mtp-eval-31.png) <br>

Det här avsnittet hjälper dig att konfigurera:
-   Office 365 Avancerat skydd
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Avancerat skydd


## <a name="configure-office-365-advanced-threat-protection"></a>Konfigurera avancerat hotskydd för Office 365
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat avancerat skydd mot Office 365-hot. 

Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper till att avgöra några av dessa inställningar. När du kör som administratör i din klientorganisation, get-ORCAReport kommer att bidra till att generera en bedömning av anti-spam, anti-phish och andra inställningar meddelandehygien. Du kan ladda https://www.powershellgallery.com/packages/ORCA/ner denna modul från . 

1. Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.
![Bild of_page](../../media/mtp-eval-32.png) <br>
 
2. Klicka på **ATP-anti-nätfiske,** välj **Skapa** och fyll i principnamnet och beskrivningen. Klicka på **Nästa**.
![Bild of_page](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Redigera din avancerade ATP-policy mot nätfiske. Ändra **avancerad tröskel för nätfiske** till **2 - Aggressiv**.
<br>

3. Klicka på den nedrullningsbara menyn **Lägg till ett villkor** och välj domänen/domänerna som mottagardomän. Klicka på **Nästa**.
![Bild of_page](../../media/mtp-eval-34.png) <br>
 
4. Granska dina inställningar. Klicka på **Skapa den här principen** för att bekräfta. 
![Bild of_page](../../media/mtp-eval-35.png) <br>
 
5. Välj **ATP Säkra bilagor** och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**  
![Bild of_page](../../media/mtp-eval-36.png) <br>

6. Klicka på ikonen + om du vill skapa en ny princip för säker bifogad fil och tillämpa den som mottagaredomän på dina domäner. Klicka på **Spara**.
![Bild of_page](../../media/mtp-eval-37.png) <br>
 
7. Välj sedan **atp-principen för säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.

8. Kontrollera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade. Mer information finns i inställningar för [säkra länkar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) Klicka på **Spara**. 
![Bild of_page](../../media/mtp-eval-38.png) <br>

9. Välj sedan policyn **mot skadlig kod,** välj standard och välj pennikonen.

10. Klicka på **Inställningar** och välj **Ja och använd standardmeddelandetexten** för att aktivera **svar på identifiering av skadlig kod**. Aktivera **filtret Vanliga typer av bifogade filer.** Klicka på **Spara**.
<br>![Bild of_page](../../media/mtp-eval-39.png) <br>
  
11. Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** och aktivera Granskning.  
![Bild of_page](../../media/mtp-eval-40.png) <br>

12. Integrera Office 365 ATP med Microsoft Defender ATP. Navigera till [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** och välj **WDATP-inställningar** längst upp till höger på skärmen. Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning.
![Bild of_page](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Konfigurera Avancerat hotskydd för Azure
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Azure Advanced Threat Protection


1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > välja Fler **resurser** > **Azure Advanced Threat Protection**.
![Bild of_page](../../media/mtp-eval-42.png) <br>

2. Klicka på Skapa om du vill starta guiden Avancerat skydd mot Azure.Click **Create** to start the Azure Advanced Threat Protection wizard. 
<br>![Bild of_page](../../media/mtp-eval-43.png) <br>

3. Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.  
![Bild of_page](../../media/mtp-eval-44.png) <br>

4. Ange lokala autentiseringsuppgifter för Active Directory. Detta kan vara alla användarkonton som har läsbehörighet till Active Directory.
![Bild of_page](../../media/mtp-eval-45.png) <br>

5. Välj sedan **Hämta sensorinstallation och** överför filen till domänkontrollanten. 
![Bild of_page](../../media/mtp-eval-46.png) <br>

6. Kör installationen av Azure ATP-sensor och börja följa guiden.
<br>![Bild of_page](../../media/mtp-eval-47.png) <br>
 
7. Klicka på **Nästa** vid sensordistributionstypen.
<br>![Bild of_page](../../media/mtp-eval-48.png) <br>
 
8. Kopiera åtkomstnyckeln som du behöver för att ange den nästa i guiden.
![Bild of_page](../../media/mtp-eval-49.png) <br>
 
9. Kopiera åtkomstnyckeln till guiden och klicka på **Installera**. 
<br>![Bild of_page](../../media/mtp-eval-50.png) <br>

10. Grattis, du har konfigurerat Azure Advanced Threat Protection på domänkontrollanten.
![Bild of_page](../../media/mtp-eval-51.png) <br>
 
11. Under avsnittet [Azure Azure ATP-inställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlingsknappen. Klicka på **Spara**. 
![Bild of_page](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP har bytt namn till Microsoft Defender ATP. Omprofilering förändringar över alla våra portaler håller på att rullas ut för konsekvens.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurera Säkerhet för Microsoft Cloud-appar
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security. 

1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Mer resurser** > **Microsoft Cloud App Security**.
![Bild of_page](../../media/mtp-eval-53.png) <br>

2. Vid informationsfrågan om att integrera Azure ATP väljer du **Aktivera Azure ATP-dataintegration**. 
<br>![Bild of_page](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Om du inte ser den här prompten kan det innebära att din Azure ATP-dataintegrering redan har aktiverats. Om du är osäker kontaktar du dock IT-administratören för att bekräfta. 

3. Gå till **Inställningar**, aktivera växlingsknappen för **Azure ATP-integrering** och klicka sedan på **Spara**. 
![Bild of_page](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>För nya Azure ATP-instanser aktiveras den här integrationsväxlingen automatiskt. Bekräfta att din Azure ATP-integrering har aktiverats innan du går vidare till nästa steg.
 
4. Under inställningarna för molnidentifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integreringen. Klicka på **Spara**.
![Bild of_page](../../media/mtp-eval-56.png) <br>

5. Under Molnidentifieringsinställningar väljer du **Användarberikande**och aktiverar sedan integreringen med Azure Active Directory.
![Bild of_page](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Konfigurera avancerat hotskydd för Microsoft Defender
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender Advanced Threat Protection.

1. Navigera till [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Mer resurser** > **Microsoft Defender Security Center**. Klicka på **Öppna**.
<br>![Bild of_page](../../media/mtp-eval-58.png) <br>
 
2. Följ guiden Avancerat skydd mot microsoft defender. Klicka på **Nästa**. 
<br>![Bild of_page](../../media/mtp-eval-59.png) <br>

3. Välj baserat på önskad plats för datalagring, datalagringsprincip, organisationsstorlek och opt-in för förhandsversionsfunktioner. 
<br>![Bild of_page](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>Du kan inte ändra vissa inställningar, till exempel lagringsplats för data, efteråt. 
<br>

Klicka på **Nästa**. 

4. Klicka på **Fortsätt** så etablerar microsoft defender ATP-klienten.
<br>![Bild of_page](../../media/mtp-eval-61.png) <br>

5. Ombord på dina slutpunkter via grupprinciper, Microsoft Slutpunktshanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP. För enkelhetens skull använder den här guiden det lokala skriptet.

6. Klicka på **Hämta paket** och kopiera introduktionsskriptet till slutpunkterna.  
<br>![Bild of_page](../../media/mtp-eval-62.png) <br>

7. Kör introduktionsskriptet som administratör på slutpunkten och välj Y.
<br>![Bild of_page](../../media/mtp-eval-63.png) <br>

8. Grattis, du har onboarded din första slutpunkt.  
<br>![Bild of_page](../../media/mtp-eval-64.png) <br>

9. Kopiera in identifieringstestet från ATP-guiden Microsoft Defender.
<br>![Bild of_page](../../media/mtp-eval-65.png) <br>

10. Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör det. 
<br>![Bild of_page](../../media/mtp-eval-66.png) <br>

11. Välj **Börja använda Microsoft Defender ATP** i guiden.
<br>![Bild of_page](../../media/mtp-eval-67.png) <br>
 
12. Besök [Microsoft Defender Security Center](https://securitycenter.windows.com/). Gå till **Inställningar** och välj sedan **Avancerade funktioner**. 
<br>![Bild of_page](../../media/mtp-eval-68.png) <br>

13. Aktivera integreringen med **Azure Advanced Threat Protection**.  
<br>![Bild of_page](../../media/mtp-eval-69.png) <br>

14. Aktivera integreringen med **Office 365 Threat Intelligence**.
<br>![Bild of_page](../../media/mtp-eval-70.png) <br>

15. Aktivera integrering med **Microsoft Cloud App Security**.
<br>![Bild of_page](../../media/mtp-eval-71.png) <br>

16. Bläddra nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.
<br>![Bild of_page](../../media/mtp-eval-72.png) <br>

## <a name="next-steps"></a>Nästa steg
[Aktivera Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) och generera sedan [en testvarning](generate-test-alert.md).
