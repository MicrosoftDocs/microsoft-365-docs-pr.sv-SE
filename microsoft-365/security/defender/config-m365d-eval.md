---
title: Konfigurera Microsoft 365 Defender-pelarna för testlabb eller pilotmiljö
description: Konfigurera Microsoft 365 Defender-pelare, till exempel Microsoft Defender för Office 365, Microsoft Defender för identitet, Microsoft Cloud App Security och Microsoft Defender för Slutpunkt, för din testlabb- eller pilotmiljö.
keywords: konfigurera utvärderingsversion av Microsoft Threat Protection, utvärderingsversion av Microsoft Threat Protection, konfigurera Microsoft Threat Protection-pilotprojekt, konfigurera Microsoft Threat Protection-pelarna, Microsoft Threat Protection-pelarna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 8bb80e032fd2eb4c618b60f4ab46829d5cf11b6d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199235"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurera Microsoft 365 Defender-pelarna för din testlabb- eller pilotmiljö

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Det är en process i tre steg att skapa en provlabb eller pilotmiljö med Microsoft 365 Defender:

|[![Fas 1: Förbereda](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Fas 1: Förbereda](prepare-m365d-eval.md) |[![Fas 2: Konfigurera](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fas 2: Konfigurera](setup-m365deval.md) |![Fas 3: Introduktion](../../media/phase-diagrams/onboard.png)<br/>Fas 3: Introduktion | [![Tillbaka till pilottestning](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Tillbaka till pilotspelboken](m365d-pilot.md) |
|--|--|--|--|
|| |*Du är här!* | |

Du befinner dig för närvarande i konfigurationsfasen.

Förberedelse är avgörande för en lyckad distribution. I den här artikeln får du vägledning i de punkter du behöver tänka på när du förbereder distributionen av Microsoft Defender för Slutpunkt.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-pelarpelare
Microsoft 365 Defender består av fyra pelar. Även om en av de här pelarna redan kan ge värde åt nätverksorganisationens säkerhet ger det din organisation störst värde genom att aktivera de fyra Microsoft 365 Defender-pelarna.

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

I det här avsnittet får du veta hur du konfigurerar:
-   Microsoft Defender för Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender för Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>Konfigurera Microsoft Defender för Office 365

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Defender för Office 365. 

Det finns en PowerShell-modul som kallas *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* som hjälper dig att avgöra vissa av de här inställningarna. När du kör som administratör i klientorganisationen får du en utvärdering av anti-spam, anti-phish och andra inställningar för att bli kontaktad av ett meddelande. Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ . 

1. Gå till [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.

   ![Image of_Office 365 Security & Compliance Center Threat Management Policy page](../../media/mtp-eval-32.png)
 
2. Klicka **på Skydd mot nätfiske** och **välj** Skapa och fyll i principens namn och beskrivning. Klicka på **Nästa**.

   ![Bild of_Office 365 Security & Compliance Center – skydd mot nätfiske-policy där du kan namnge principen](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Redigera principen för avancerad skydd mot nätfiske i Microsoft Defender för Office 365. Ändra **avancerat tröskelvärde för nätfiske** **till 2 – Aggressivt.**

3. Klicka på **listrutan Lägg** till ett villkor och välj dina domäner som mottagardomän. Klicka på **Nästa**.

   ![Bild of_Office 365 Säkerhetscenter & policysida mot nätfiske där du kan lägga till ett villkor för programmet](../../media/mtp-eval-34.png)
 
4. Granska inställningarna. Klicka **på Skapa den här principen för** att bekräfta. 

   ![Bild of_Office 365 Säkerhet & sidan Skydd mot nätfiskeprincip i Säkerhetscenter där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png)
 
5. Välj **Säkra bifogade** filer och välj alternativet Aktivera **ATP för SharePoint, OneDrive och Microsoft Teams.**

   ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png)

6. Klicka på +-ikonen för att skapa en ny princip för säkra bifogade filer, använd den som mottagardomän för domänerna. Klicka på **Spara**.

   ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan skapa en ny princip för säkra bifogade filer](../../media/mtp-eval-37.png)
 
7. Välj sedan principen För **säkra länkar** och klicka sedan på pennikonen för att redigera standardprincipen.

8. Kontrollera att alternativet **Spåra inte när användare klickar** på säkra länkar inte är markerat, medan resten av alternativen är markerade. Mer [information finns i Inställningarna](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) för säkra länkar. Klicka på **Spara**. 

   ![Bild of_Office 365 Säkerhets- & Säkerhetscenter som visar att alternativet Spåra inte när användare klickar på Kassaskåp inte är markerat](../../media/mtp-eval-38.png)

9. Välj sedan **standardprincipen** för skadlig programvara och pennikonen.

10. Klicka **på Inställningar** och välj Ja och använd **standardmeddelandetexten för** att aktivera svar för identifiering av skadlig **programvara.** Aktivera filtret **Vanliga typer av bifogade filer.** Klicka på **Spara**.

    ![Bild of_Office 365 Säkerhet och efterlevnadscenter & som visar att svaret för identifiering av skadlig programvara är aktiverat med standardmeddelande och att filtret för vanliga bifogade filer är aktiverat](../../media/mtp-eval-39.png)
  
11. Gå till [Office 365-& granskningsloggsökning](https://protection.office.com/homepage)för efterlevnadscenter  >    >   och aktivera granskning.

    ![Bild of_Office 365 säkerhets- & efterlevnadscenter där du kan aktivera granskningsloggsökning](../../media/mtp-eval-40.png)

12. Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt. Gå till [Office 365 Security & Compliance Center Threat](https://protection.office.com/homepage)Management Explorer och välj Microsoft Defender för Slutpunktsinställningar i det övre  >    >   högra hörnet av skärmen.  I dialogrutan Defender för slutpunktsanslutning aktiverar du **Anslut till Microsoft Defender för Slutpunkt.**

    ![Bild of_Office 365 Säkerhets- & Efterlevnadscenter där du kan aktivera Microsoft Defender för slutpunktsanslutning](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Konfigurera Microsoft Defender för identitet

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender för identitet

1. Gå till [Säkerhetscenter för Microsoft 365 >](https://security.microsoft.com/info) **välja Fler resurser** Microsoft Defender för  >  **identitet.**

   ![Bild of_Microsoft 365 Säkerhetscenter där det finns ett alternativ för att öppna Microsoft Defender för identitet](../../media/mtp-eval-42.png)

2. Klicka **på Skapa** för att starta guiden Microsoft Defender för identitet. 

   ![Bild of_Microsoft sida i guiden Defender för identitet där du ska klicka på knappen Skapa](../../media/mtp-eval-43.png)

3. Välj **Ange ett användarnamn och lösenord för att ansluta till Active Directory-skogen**.  

   ![Bild of_Microsoft välkomstsidan för Defender för identitet](../../media/mtp-eval-44.png)

4. Ange lokala autentiseringsuppgifter för Active Directory. Det kan vara alla användarkonton som har läsbehörighet till Active Directory.

   ![Bild of_Microsoft för sidan Tjänster i Identitetskatalogen där du bör lägga till dina autentiseringsuppgifter](../../media/mtp-eval-45.png)

5. Välj sedan Ladda **ned sensorinstallation och** överför filen till domänkontrollanten.

   ![Bild of_Microsoft Defender för identitetssida där du kan välja Hämtnings sensorinställning](../../media/mtp-eval-46.png)

6. Kör Microsoft Defender för konfiguration av identitets sensor och börja följa guiden.

   ![Bild of_Microsoft Defender för identitetssida där du ska klicka på nästa för att följa guiden Microsoft Defender för identitets sensor](../../media/mtp-eval-47.png)
 
7. Klicka **på** Nästa vid sensordistributionstypen.

   ![Bild of_Microsoft Defender för identitetssida där du ska klicka på Nästa för att gå till nästa sida](../../media/mtp-eval-48.png)
 
8. Kopiera snabbtangenten eftersom du måste ange den nästa i guiden.

   ![Bild of_the sensorsidan där du bör kopiera snabbtangenten som du behöver ange på nästa sida i Microsoft Defender för installationsguiden för identitetssensorer](../../media/mtp-eval-49.png)
 
9. Kopiera in snabbtangenten i guiden och klicka på **Installera**. 

   ![Bild of_Microsoft sidan för guiden Defender för identitets sensor, där du bör ange snabbtangenten och klicka sedan på installationsknappen](../../media/mtp-eval-50.png)

10. Grattis! Du har konfigurerat Microsoft Defender för identitet på domänkontrollanten.

    ![Bild of_Microsoft defender för komplettering av identitets sensorguiden, där du ska klicka på knappen Slutför](../../media/mtp-eval-51.png)
 
11. Under avsnittet [Microsoft Defender för identitetsinställningar](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Microsoft Defender för slutpunkt **. Aktivera sedan växlingsknappen. Klicka på **Spara**. 

    ![Bild of_the microsoft Defender för identitetsinställningar, där du ska aktivera växlingsknappen Microsoft Defender för slutpunkt](../../media/mtp-eval-52.png)

> [!NOTE]
> Windows Defender ATP har rebranderats som Microsoft Defender för Endpoint. Ändringar som rebranderas i alla våra portaler distribueras för att skapa konsekvens.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurera Microsoft Cloud App-säkerhet

> [!NOTE]
> Hoppa över det här steget om du redan har aktiverat Microsoft Cloud App Security. 

1. Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser Microsoft** Cloud App  >  **Security**.

   ![Bild of_Microsoft 365 Säkerhetscenter där du kan se kortet Microsoft Cloud App och ska klicka på öppna-knappen](../../media/mtp-eval-53.png)

2. När du uppmanas att integrera Microsoft Defender för identitet markerar du **Aktivera Microsoft Defender för identitetsdataintegrering.**
  
   ![Bild of_the informationsfråga om att integrera Microsoft Defender för identitet, där du bör välja länken Aktivera Microsoft Defender för identitetsdataintegrering](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Om du inte ser det här alternativet kan det innebära att microsoft Defender för identitetsdataintegrering redan har aktiverats. Om du är osäker kan du kontakta IT-administratören för att bekräfta. 

3. Gå till **Inställningar**, aktivera växlingsknappen **Microsoft Defender för** identitetsintegrering och klicka sedan på **Spara**. 

   ![Bild of_the inställningar där du ska aktivera växlingsknappen För identitetsintegrering i Microsoft Defender och sedan klicka på Spara](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > För nya microsoft Defender för identitetsinstanser är växlingsknappen för den här integreringen aktiverad automatiskt. Bekräfta att Microsoft Defender för identitetsintegrering har aktiverats innan du går vidare till nästa steg.
 
4. Under inställningarna för molnidentifiering väljer du **Microsoft Defender för Slutpunktsintegrering** och aktiverar sedan integreringen. Klicka på **Spara**.

   ![Bild of_the på sidan Microsoft Defender för slutpunkt där kryssrutan blockera osanerade appar under Microsoft Defender för slutpunktsintegrering är markerad. Klicka på Spara.](../../media/mtp-eval-56.png)

5. Under Inställningar för molnidentifiering **väljer du Användarberikning** och aktiverar sedan integreringen med Azure Active Directory.

   ![Bild av avsnittet användarberikning där kryssrutan identifierad användaridentifierare med Azure Active Directory-användarnamn är markerad](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Defender för slutpunkt

>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender för Slutpunkt.

1. Gå till [Microsoft 365 Säkerhetscenter](https://security.microsoft.com/info)  >  **Fler resurser** Microsoft Defender  >  **Säkerhetscenter**. Klicka **på Öppna**.

   ![Bild of_Microsoft alternativ i Defender Säkerhetscenter på sidan Säkerhetscenter för Microsoft 365](../../media/mtp-eval-58.png)
 
2. Följ guiden Microsoft Defender för slutpunkt. Klicka på **Nästa**. 

   ![Bild of_the sida i välkomstguiden för Microsoft Defender Säkerhetscenter](../../media/mtp-eval-59.png)

3. Välj baserat på önskad datalagringsplats, databevarandeprincip, organisationsstorlek och möjlighet att registrera dig för förhandsgranskningsfunktioner.

   ![Bild of_the väljer du land för datalagring, bevarandeprincip och organisationsstorlek. Klicka på Nästa när du är klar med att välja.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Du kan inte ändra vissa inställningar, till exempel datalagringsplats efteråt. 

   Klicka på **Nästa**. 

4. Klicka **på Fortsätt** så etableras microsoft Defender för slutpunktsklientorganisationen.

   ![Bild of_the sida som uppmanar dig att klicka på knappen Fortsätt för att skapa din molninstans](../../media/mtp-eval-61.png)

5. Få igång slutpunkterna genom grupprinciper, Microsoft Endpoint Manager eller genom att köra ett lokalt skript i Microsoft Defender för Slutpunkt. För enkelhetens skull använder den här guiden det lokala skriptet.

6. Klicka **på Ladda ned** paket och kopiera introduktionsskriptet till slutpunkterna.

   ![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera onboarding-skriptet till slutpunkten eller slutpunkterna](../../media/mtp-eval-62.png)

7. Kör onboarding-skriptet som administratör på slutpunkten och välj Y. 

   ![Bild of_the här du kör onboarding-skriptet och väljer Y för att fortsätta](../../media/mtp-eval-63.png)

8. Grattis! Du har introducerat din första slutpunkt.

   ![Bild of_the här kommandotolken där du får bekräftelse på att du har introducerat din första slutpunkt. Tryck på en tangent för att fortsätta](../../media/mtp-eval-64.png)

9. Kopiera och klistra in identifieringstestet från guiden Microsoft Defender för slutpunkt.

   ![Bild of_the köra ett teststeg för identifiering där du ska klicka på Kopiera för att kopiera det identifieringstestskript som du ska klistra in i kommandotolken](../../media/mtp-eval-65.png)

10. Kopiera PowerShell-skriptet till en upphöjd kommandotolk och kör den. 

    ![Bild of_command fråga var du ska kopiera PowerShell-skriptet till en upphöjd kommandotolk och köra den](../../media/mtp-eval-66.png)

11. Välj **Börja använda Microsoft Defender för slutpunkt** i guiden.

    ![Bild of_the i guiden där du ska klicka på Börja använda Microsoft Defender för slutpunkt](../../media/mtp-eval-67.png)
 
12. Besök [Microsoft Defender Säkerhetscenter.](https://securitycenter.windows.com/) Gå till **Inställningar** och välj sedan **Avancerade funktioner**. 

    ![Bild of_Microsoft inställningsmenyn i Defender Säkerhetscenter där du bör välja Avancerade funktioner](../../media/mtp-eval-68.png)

13. Aktivera integrering med **Microsoft Defender för identitet.**  

    ![Bild of_Microsoft av avancerade funktioner i Defender Säkerhetscenter, alternativet Microsoft Defender för identitet, omkopplare som du behöver aktivera](../../media/mtp-eval-69.png)

14. Aktivera integrering med **Office 365 Threat Intelligence.**

    ![Bild of_Microsoft av avancerade funktioner i Defender Säkerhetscenter, alternativ för Office 365 Threat Intelligence som du behöver aktivera](../../media/mtp-eval-70.png)

15. Aktivera integrering med **Microsoft Cloud App Security.**

    ![Bild of_Microsoft Av/på avancerade funktioner i Defender Säkerhetscenter, med alternativet Säkerhet i Microsoft Cloud App](../../media/mtp-eval-71.png)

16. Rulla nedåt och klicka **på Spara inställningar** för att bekräfta de nya integrationerna.

    ![Bild of_Save inställningar som du behöver klicka på](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Starta tjänsten Microsoft 365 Defender

>[!NOTE]
>Från och med den 1 juni 2020 aktiverar Microsoft automatiskt Microsoft 365 Defender-funktioner för alla berättigade klienter. Mer information finns [i den här Microsoft Tech Community-artikeln om licensberättigande.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 


Gå till [Microsoft 365 Säkerhetscenter.](https://security.microsoft.com/homepage) Gå till **Inställningar** och välj sedan **Microsoft 365 Defender.**

![Bild of_Microsoft skärmbild med alternativ för 365 Defender från sidan Inställningar för Säkerhetscenter i Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Mer omfattande vägledning finns i Aktivera [Microsoft 365 Defender.](m365d-enable.md) 

Grattis! Du har just skapat din utvärderingsversionsmiljö i Microsoft 365 Defender! Nu kan du bekanta dig med Användargränssnittet i Microsoft 365 Defender! Se vad du kan lära dig av följande interaktiva guide i Microsoft 365 Defender och hur du använder varje instrumentpanel för dina dagliga säkerhetsåtgärdsuppgifter.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Sedan kan du simulera en attack och se hur funktionerna i olika produkter identifierar, skapar aviseringar och automatiskt svarar på fillösa angrepp mot en slutpunkt.

## <a name="next-step"></a>Nästa steg

- [Generera en testavisering](generate-test-alert.md) – Kör en attack simulering i ditt provlabb i Microsoft 365 Defender.