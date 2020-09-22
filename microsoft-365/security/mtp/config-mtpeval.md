---
title: Konfigurera Microsoft Threat Protection-pelare för utvärderings labbet eller pilot miljön
description: Konfigurera skydd mot Microsoft Threat Protection, till exempel Office 365 ATP, Azure ATP, Microsoft Cloud App Security och Microsoft Defender ATP, för utvärderings labbet eller pilot miljön.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1778e8485e859d01e4eec40c7a0d404636e27e8d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199655"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurera skydd mot Microsoft Threat för utvärderings labbet eller pilot miljön

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd


Att skapa ett utvärderings labb för Microsoft Threat-eller pilot miljö och distribuera det är en process i tre steg:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö" />
      <br/>Fas 1: förbereda </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Ställ in ett utvärderings labb eller pilot miljö för Microsoft Threat Protection" />
      <br/>Fas 2: konfiguration </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurera var and rings skydd för ditt Microsoft Threat Protection test labb eller pilot miljö och inbyggda slut punkter" />
      <br/>Steg 3: Konfigurera & inbyggt </a><br>
</td>


  </tr>
</table>

Du är för närvarande i konfigurations fasen.


Förberedelsen är viktig för eventuell distribution. I den här artikeln ska du vägleda dig på de Points du måste tänka på när du förbereder dig för att distribuera Microsoft Defender ATP.


## <a name="microsoft-threat-protection-pillars"></a>Microsoft Threat Protection-pelare
Microsoft Threat Protection består av fyra pelare. Även om en pelare redan kan ge ett värde till din nätverks organisations säkerhet, ger det fyra till gång till din organisation flest värde.
<br>
![Of_Microsoft hot skydds lösning för användare, Azure Avancerat skydd för slut punkter Microsoft Defender Avancerat skydd, för Cloud-appar, Microsoft Cloud App-säkerhet och för data, Office 365 Avancerat skydd  ](../../media/mtp-eval-31.png) <br>

I det här avsnittet får du hjälp att konfigurera:
-   Office 365 Avancerat skydd
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App Security
-   Microsoft Defender Avancerat skydd


## <a name="configure-office-365-advanced-threat-protection"></a>Konfigurera Office 365 Avancerat skydd
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Office 365 Avancerat skydd. 

Det finns en PowerShell-modul som heter *Office 365 Advanced Threat Protection (Orca)* som hjälper dig att avgöra vissa av de här inställningarna. När du kör som administratör i klient organisationen kan du med ORCAReport få en utvärdering av skräp post, anti-Phish och andra inställningar för meddelande hygien. Du kan hämta den här modulen från https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  policy för**hantering**av villkor för efterlevnad  >  **Policy**.
![Bild of_Office 365 säkerhets & policy för Threat Management-hantering](../../media/mtp-eval-32.png) <br>
 
2. Klicka på **ATP-nätfiske**och välj **skapa** och fyll i Principens namn och beskrivning. Klicka på **Nästa**.
![Bild of_Office 365 säkerhet & policy för skydd mot Office-nätfiske där du kan namnge policyn](../../media/mtp-eval-33.png) <br>

>[!NOTE]
>Redigera din avancerade policy för ATP-anti-phishing. Ändra den **avancerade nät fiske tröskeln** till **2-aggressivt**.
<br>

3. Klicka på den nedrullningsbara menyn **Lägg till en villkors** lista och välj din domän (er) som mottagar domän. Klicka på **Nästa**.
![Bild of_Office 365 säkerhet & policy för skydd mot server för uppringnings Center där du kan lägga till ett villkor för dess program](../../media/mtp-eval-34.png) <br>
 
4. Granska dina inställningar. Klicka på **skapa den här principen** för att bekräfta. 
![Bild of_Office 365 säkerhets & policy för skydd mot efterlevnad för nätfiske där du kan granska dina inställningar och klicka på knappen Skapa den här principen](../../media/mtp-eval-35.png) <br>
 
5. Markera alternativet för **säker säkerhet för ATP** och välj alternativ **för att aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .  
![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera ATP för SharePoint, OneDrive och Microsoft Teams](../../media/mtp-eval-36.png) <br>

6. Klicka på ikonen + för att skapa en ny princip för säker bifogad fil, tillämpa den som mottagar domän i domänerna. Klicka på **Spara**.
![Bild of_Office 365 säkerhets & sidan Compliance Center, där du kan skapa en ny princip för säker bifogad fil](../../media/mtp-eval-37.png) <br>
 
7. Välj sedan policyn för **Safet ATP-länkar** och klicka sedan på Penn ikonen för att redigera standard principen.

8. Kontrol lera att alternativet **Spåra inte när användare klickar på säkra länkar** inte är markerat, medan resten av alternativen är markerade. Se [Inställningar för Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) . Klicka på **Spara**. 
![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att alternativet spåra inte när användare klickar på säker är inte markerat](../../media/mtp-eval-38.png) <br>

9. Välj sedan standard principen för att förhindra **mot skadlig program vara** och välj sedan Penn ikonen.

10. Klicka på **Inställningar** och välj **Ja och Använd standard meddelande texten** för att aktivera **identifiering av skadlig program vara**. Aktivera **filtret vanliga typer av bifogade filer** . Klicka på **Spara**.
<br>![Bild of_Office 365 säkerhets & sidan Compliance Center som visar att svaret om skadlig program vara är aktiverat med standard meddelande och att filtret vanliga bilage typer är aktiverat](../../media/mtp-eval-39.png) <br>
  
11. Navigera till [Office 365-säkerhets & Compliance Center](https://protection.office.com/homepage)  >  **Sök**efter  >  **gransknings loggs ökning** och aktivera granskning.  
![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera gransknings loggs ökningen](../../media/mtp-eval-40.png) <br>

12. Integrera Office 365 ATP med Microsoft Defender ATP. Navigera till [Office 365-säkerhets &](https://protection.office.com/homepage)  >  **hanterings**Center för regelefterlevnad  >  **Explorer** och välj **WDATP inställningar** i det övre högra hörnet av skärmen. I dialog rutan Microsoft Defender ATP-anslutning aktiverar **du Anslut till Windows ATP**.
![Bild of_Office 365 säkerhets & sidan Compliance Center där du kan aktivera Windows Defender ATP-anslutning på](../../media/mtp-eval-41.png) <br>

## <a name="configure-azure-advanced-threat-protection"></a>Konfigurera Avancerat skydd för Azure
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Azure Avancerat skydd


1. Gå till [Microsoft 365-säkerhets Center](https://security.microsoft.com/info) > Välj **fler resurser**  >  **Azure Avancerat skydd**.
![Bild of_Microsoft 365 säkerhets Center sida där det finns ett alternativ för att öppna Azure Avancerat skydd](../../media/mtp-eval-42.png) <br>

2. Klicka på **skapa** för att starta guiden Avancerat skydd för Azure. 
<br>![Bild of_Azure sidan för avancerat skydd på guiden där du bör Klicka på knappen Skapa](../../media/mtp-eval-43.png) <br>

3. Välj **ge ett användar namn och lösen ord för att ansluta till Active Directory-skogen**.  
![Bild på Välkomst sidan för of_Azure avancerad skydd](../../media/mtp-eval-44.png) <br>

4. Ange lokala inloggnings uppgifter för Active Directory. Det kan vara vilket användar konto som helst som har Läs åtkomst till Active Directory.
![Bild of_Azure sidan för tjänsten för avancerat skydds katalog där du ska ange dina uppgifter](../../media/mtp-eval-45.png) <br>

5. Välj sedan **Ladda ned sensor konfiguration** och överföra fil till domänkontrollanten. 
![Bild of_Azure sidan för avancerat skydd där du kan välja nedladdnings sensor inställning](../../media/mtp-eval-46.png) <br>

6. Kör installations programmet för Azure ATP och börja följa guiden.
<br>![Bild of_Azure sidan för avancerat skydd där du bör Klicka på Nästa för att följa Azure ATP-sensor guiden](../../media/mtp-eval-47.png) <br>
 
7. Klicka på **Nästa** på sensor distributions typen.
<br>![Bild of_Azure sidan för avancerat skydd för hotet där du bör Klicka på Nästa för att gå till nästa sida](../../media/mtp-eval-48.png) <br>
 
8. Kopiera snabb tangenten eftersom du måste ange den intill i guiden.
![Bild of_the sensorer-sida där du vill kopiera den snabb åtkomst du behöver ange på nästa sida med guiden för Azure ATP-sensor](../../media/mtp-eval-49.png) <br>
 
9. Kopiera till guiden och klicka på **Installera**. 
<br>![Bild of_Azure sidan för avancerat skydd för Azure ATP-guiden där du bör tillhandahålla snabb tangenten och klicka sedan på knappen Installera.](../../media/mtp-eval-50.png) <br>

10. Grattis! du har konfigurerat Azure Avancerat skydd för din domänkontrollant.
![Bild of_Azure Avancerat skydd för Azure ATP-sensor för installation av Office.](../../media/mtp-eval-51.png) <br>
 
11. Under Inställningar för [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) väljer du **Windows Defender ATP**och aktiverar sedan växlings knappen. Klicka på **Spara**. 
![Bild of_the sidan för Azure Azure ATP-inställningar där du bör aktivera Windows Defender ATP.](../../media/mtp-eval-52.png) <br>

>[!NOTE]
>Windows Defender ATP har ändrats som Microsoft Defender ATP. Att ändra dina ändringar i alla portaler blir då mer konsekvens.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurera säkerhet för Microsoft Cloud App
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat säkerhet för Microsoft Cloud App. 

1. Navigera till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Cloud App-säkerhet**.
![Bild of_Microsoft 365 säkerhets Center sida där du kan se Microsoft Cloud App Card och ska klicka på knappen Öppna](../../media/mtp-eval-53.png) <br>

2. Välj **Aktivera Azure ATP-data integrering**i informations meddelandet om du vill integrera Azure ATP. 
<br>![Bild of_the meddelande om att integrera Azure ATP där du bör välja länken Aktivera Azure ATP-data integrering](../../media/mtp-eval-54.png) <br>

>[!NOTE]
>Om du inte ser den här uppmaningen kan det betyda att din Azure ATP-data integrering redan har Aktiver ATS. Om du är osäker kontaktar du IT-administratören för att bekräfta. 

3. Gå till **Inställningar**, aktivera **integreringen av Azure ATP** och klicka sedan på **Spara**. 
![Sidan image of_the inställningar där du bör aktivera och inaktivera integreringen med Azure ATP klickar du på Spara](../../media/mtp-eval-55.png) <br>
>[!NOTE]
>För nya Azure ATP-instanser är denna växel växling automatiskt aktive rad. Kontrol lera att din Azure ATP-integrering har Aktiver ATS innan du går vidare till nästa steg.
 
4. Under Inställningar för moln identifiering väljer du **Microsoft Defender ATP-integrering**och aktiverar integrationen. Klicka på **Spara**.
![Bild of_the Microsoft Defender ATP-sida där kryss rutan blockera program som inte används under Microsoft Defender ATP-integrering är markerad. Klicka på Spara.](../../media/mtp-eval-56.png) <br>

5. Under Inställningar för moln identifiering väljer du **användar upplevelse**och aktiverar integrationen med Azure Active Directory.
![Bild av avsnittet användar berikning där kryss rutan utökad identifiering av användar identifierare med Azure Active Directory-username är markerad](../../media/mtp-eval-57.png) <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Konfigurera Microsoft Defender Avancerat skydd
>[!NOTE]
>Hoppa över det här steget om du redan har aktiverat Microsoft Defender Avancerat skydd.

1. Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/info)  >  **fler resurser**  >  **Microsoft Defender säkerhets Center**. Klicka på **Öppna**.
<br>![Bild of_Microsoft Defender säkerhets Center på sidan Microsoft 365 Security Center](../../media/mtp-eval-58.png) <br>
 
2. Följ guiden för avancerat skydd mot Microsoft Defender. Klicka på **Nästa**. 
<br>![Bild of_the sidan Välkommen till Microsoft Defender säkerhets Center](../../media/mtp-eval-59.png) <br>

3. Välj baserat på din önskade lagrings plats för data, bevarande princip för data, organisations storlek och val för förhands gransknings funktioner. 
<br>![Bild of_the sida för att välja data lagrings land, bevarande princip och organisations storlek. Klicka på Nästa när du är klar med valet.](../../media/mtp-eval-60.png) <br>
>[!NOTE]
>Du kan inte ändra vissa inställningar, till exempel data lagrings plats, efteråt. 
<br>

Klicka på **Nästa**. 

4. Klicka på **Fortsätt** så etableras din Microsoft Defender ATP-klient.
<br>![Bild of_the sida där du uppmanas att klicka på knappen Fortsätt för att skapa din moln instans](../../media/mtp-eval-61.png) <br>

5. Ta fram dina slut punkter via grup principer, Microsoft slut punkts hanteraren eller genom att köra ett lokalt skript till Microsoft Defender ATP. För enkelhetens skull använder den här guiden det lokala skriptet.

6. Klicka på **Ladda ned paket** och kopiera registrerings skriptet till din slut punkt (er).  
<br>![Bild of_page du uppmanas att klicka på knappen Ladda ned paket för att kopiera det inbyggda skriptet till slut punkten eller slut punkterna](../../media/mtp-eval-62.png) <br>

7. Kör skriptet som administratör på slut punkten och välj Y.
<br>![Bild of_the kommando rad där du kör det inbyggda skriptet och väljer sedan Y för att fortsätta](../../media/mtp-eval-63.png) <br>

8. Grattis! du har öppnat din första slut punkt.  
<br>![Bild of_the kommando rad där du får bekräftelse på att du har öppnat din första slut punkt. Tryck på en tangent för att fortsätta](../../media/mtp-eval-64.png) <br>

9. Kopiera – klistra in identifierings testet från guiden Microsoft Defender ATP.
<br>![Bild of_the kör ett identifierings test steg där du bör Klicka på Kopiera för att kopiera det identifierings test som du vill klistra in i kommando tolken](../../media/mtp-eval-65.png) <br>

10. Kopiera PowerShell-skriptet till en upphöjd kommando tolk och kör det. 
<br>![Bild of_command fråga var du bör kopiera PowerShell-skriptet till en upphöjd kommando tolk och köra det](../../media/mtp-eval-66.png) <br>

11. Välj **börja använda Microsoft Defender ATP** från guiden.
<br>![Bild of_the bekräfta meddelande i guiden där du bör Klicka på börja använda Microsoft Defender ATP](../../media/mtp-eval-67.png) <br>
 
12. Gå till [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/). Gå till **Inställningar** och välj sedan **avancerade funktioner**. 
<br>![Bild of_Microsoft Defender säkerhets Center-menyn inställningar där du bör välja avancerade funktioner](../../media/mtp-eval-68.png) <br>

13. Aktivera integrationen med **Avancerat Azure-skyddat skydd**.  
<br>![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativet för Azure Avancerat skydds alternativ växling som du måste aktivera](../../media/mtp-eval-69.png) <br>

14. Aktivera integrationen med **Office 365 Threat Intelligence**.
<br>![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, alternativ för Office 365 Threat Intelligence växla till att aktivera](../../media/mtp-eval-70.png) <br>

15. Aktivera integrering med **säkerhet för Microsoft Cloud App**.
<br>![Bild of_Microsoft Defender säkerhets Center avancerade funktioner, säkerhets alternativ för Microsoft Cloud App](../../media/mtp-eval-71.png) <br>

16. Rulla nedåt och klicka på **Spara inställningar** för att bekräfta de nya integreringarna.
<br>![Knappen bild of_Save inställningar som du måste klicka på](../../media/mtp-eval-72.png) <br>

## <a name="start-the-microsoft-threat-protection-service"></a>Starta tjänsten Microsoft Threat Protection
>[!NOTE]
>Från och med den 1 juni 2020 aktive ras Microsoft automatiskt skydds funktioner för alla kvalificerade klient organisationer. Mer information finns i den här [artikeln i Microsoft Tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) . 
<br>

Gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/homepage). Navigera till **Inställningar** och välj sedan **Microsoft Threat Protection**.
<br>![Skärm bild av alternativ för of_Microsoft skydd från säkerhets Center för Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Mer omfattande vägledning finns i [Aktivera skydd mot Microsoft Threat](mtp-enable.md). 

Grattis! Du har just skapat ett utvärderings labb för Microsoft Threat Protection eller pilot miljö! Nu kan du bekanta dig med användar gränssnittet för Microsoft Threat Protection! Se vad du kan lära dig från och hur du använder varje instrument panel för din dagliga säkerhets åtgärd: [Microsoft Threat Protection interaktiv guide](https://aka.ms/MTP-Interactive-Guide).

Sedan kan du simulera en attack och se hur funktionerna för kors produkten identifieras, skapa aviseringar och automatiskt svara på en fillös attack på en slut punkt.

## <a name="next-step"></a>Nästa steg
|![Fasen för attack simulering](../../media/mtp/run-sim.png) <br>[Fasen för attack simulering](mtp-pilot-simulate.md) | Kör angrepps simuleringen för din pilot miljö för Microsoft Threat Protection.
|:-------|:-----|
