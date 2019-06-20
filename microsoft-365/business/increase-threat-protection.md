---
title: Ökat skydd för Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Advanced Threat Protection och skydda känsliga data.
ms.openlocfilehash: b6e9941eee9de4f295b0f8056c1c91b7076e530c
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2019
ms.locfileid: "35086399"
---
# <a name="increase-threat-protection"></a>Ökat skydd

Den här artikeln hjälper dig att öka skyddet av din Microsoft 365 prenumeration skydd mot nätfiske, skadliga program och andra hot. Dessa rekommendationer är lämplig för organisationer med ett ökat behov av säkerhet som lag kontor och kliniker hälso-och sjukvård.

Innan du börjar, kontrollera dina Office 365 säkra poäng. Office 365 säkra poäng analyserar organisationen Office 365 säkerhet utifrån dina vanliga aktiviteter och säkerhetsinställningar och tilldelar en poäng. Börja genom att ta del av dina aktuella poäng. Vidta lämpliga åtgärder i den här artikeln ökar dina poäng. Målet är inte att uppnå högsta poäng, utan att vara medveten om möjligheter att skydda miljön som inte negativt påverkar produktivitet för användarna. 

Mer information finns i [Skydda Microsoft-poäng](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja skyddet mot skadlig kod i e-post

Din Office 365 eller Microsoft 365 miljö innehåller skydd mot skadlig kod, men du kan öka skyddet genom att blockera bilagor med filtyper som är vanliga för skadlig programvara. Att öka skydd mot skadlig kod i e-post:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med autentiseringsuppgifterna för kontot Administratör. 
    
2. I Office 365 säkerhet &amp; regelefterlevnadscentret, i den vänstra navigeringsrutan under **Threat management**väljer **principen** \> **Mot skadlig kod**.
    
3. Dubbelklicka på standardprincipen om du vill redigera den här principen för hela företaget.
    
4. Klicka på **Inställningar**.
    
5. Välj **på**under **Vanliga bifogade typer Filter**. Filtyper som blockeras visas i fönstret nedanför den här kontrollen.  Kontrollera att du lägger till dessa filetypes:
   - ADE, adp, ani, bas, bat, chm, cmd, com, Kontrollpanelen, crt, hlp, ht, hta, inf, moduler, isp, jobb, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> Du kan lägga till eller ta bort filtyper senare om det behövs.
    
6. Klicka på **Spara.**
    
Mer information finns i [skydd mot skadlig kod](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Skydda mot ransomware

Ransomware begränsar åtkomsten till data genom att kryptera filer eller låser datorskärmar. Sedan försöker extort pengar från offer som frågar efter ”ransom”, vanligtvis i form av cryptocurrencies som Bitcoin, i utbyte mot åtkomst till data. 
  
Du kan skydda mot ransomware genom att skapa en eller flera e-post flöde regler att blockera filnamnstillägg används ofta för ransomware (dessa har lagts till i steg [höja nivån på det skydd mot skadlig kod i e-post](#raise-the-level-of-protection-against-malware-in-mail) ) eller för att varna användare som tar emot dessa bifogade filer i e-post.

Förutom de filer som du har blockerat i föregående steg, är det också bra att skapa en regel för att varna användare innan du öppnar bifogade filer Office som innehåller makron. Ransomware kan döljas inuti makron, så vi ska varna användare att inte öppna dessa filer från personer som de inte vet.

Skapa en regel för transport av e-post:
  
1. Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> och välj **Admin Centrerar** \> **Exchange**.
    
2. Klicka på **regler**i kategorin **e-postflöde** .
    
3. Klicka på **+**, och klicka sedan på **Skapa en ny regel**.
    
4. Klicka på **fler alternativ** längst ned i dialogrutan om du vill se en fullständig uppsättning alternativ. 
    
5. Tillämpa inställningarna i följande tabell för regeln. Lämna resten av inställningarna på standard, om du inte vill ändra inställningarna.
    
6. Klicka på **Spara**.
    
|**Inställning**|**Varna användarna innan du öppnar bifogade filer med Office-filer**||
|:-----|:-----|:-----|
|Namn  <br/> |Anti-ransomware regel: Varna användare  <br/>  |
|Tillämpa den här regeln om. . .  <br/> |Inga bifogade filer. . . filtillägget överensstämmer. . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till följande filtyper:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Gör på följande sätt. . .  <br/> |Meddela mottagare med ett meddelande  <br/> |
|Ange meddelandetext  <br/> |Öppna inte dessa typ av filer från personer du inte känner, eftersom de kan innehålla makron med skadlig kod.  <br/> |
   
Mer information finns i:
  
- [Hantera ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Återställa din OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordring för e-post

Hackare som försöker komma åt en postlåda kan stjäla din e-post genom att ange postlådan att automatiskt vidarebefordra e-post. Detta kan inträffa även utan användarens medvetande. Du kan förhindra detta genom att konfigurera en regel för e-flöde. 
  
Titta på [det här korta videoklippet](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) eller gör så här om du vill skapa en regel för transport av e-post:
  
1. Klicka på **Admin Centrerar** i Microsoft 365 administratörscenter, \> **Exchange**.
    
2. Klicka på **regler**i kategorin **e-postflöde** .
    
3. Klicka på **+**, och klicka sedan på **Skapa en ny regel**.
    
4. Klicka på **fler alternativ** längst ned i dialogrutan om du vill se en fullständig uppsättning alternativ. 
    
5. Tillämpa inställningarna i följande tabell. Lämna resten av inställningarna på standard, om du inte vill ändra inställningarna.
    
6. Klicka på **Spara**.
    
|**Inställning**|**Varna användarna innan du öppnar bifogade filer med Office-filer**|
|:-----|:-----|
|Namn  <br/> |Förhindra automatisk vidarebefordring av e-post till externa domäner  <br/> |
|Tillämpa den här regeln om...  <br/> |Avsändaren. . . är externa internt. . . Inom organisationen  <br/> |
|Lägg till villkor  <br/> |Meddelandeegenskaper. . . Inkludera meddelandetypen. . . Automatisk vidarebefordring  <br/> |
|Gör följande...  <br/> |Spärra meddelandet. . . avvisa meddelandet och innefatta en förklaring.  <br/> |
|Ange meddelandetext  <br/> |Automatiskt vidarebefordra e-post utanför organisationen förhindras av säkerhetsskäl.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiskeattacker

Om du har konfigurerat en eller flera anpassade domäner i Office 365 eller Microsoft 365-miljö kan konfigurera du skydd riktad mot nätfiske. Skydd mot nätfiske ATP, en del av Office 365 Advanced Threat Protection, kan du skydda din organisation från skadliga personifiering-baserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en anpassad domän, behöver du inte göra detta.
  
Vi rekommenderar att du börjar med detta skydd genom att skapa en princip för att skydda din viktigaste användare och din egen domän. 

  
Titta på [den här korta videon utbildning](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)om du vill skapa en princip för anti-phishing ATP eller utför du följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com). 
    
2. I Office 365 säkerhet &amp; regelefterlevnadscentret, i den vänstra navigeringsrutan under **Threat management**väljer **principen**.
    
3. Välj på sidan **principen** **ATP anti-phishing**.
    
4. Välj **+ Skapa**på sidan **Anti-phishing** . Det startas en guide som vägleder dig genom att definiera anti-phishing-principen.
    
5. Ange namn, beskrivning och inställningar för principen som rekommenderas i diagrammet nedan. Mer information finns i [Lär dig mer om ATP anti-phishing principalternativ](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) . 
    
6. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**efter behov.
    

|**Inställningen eller alternativ**<br/>|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Domän och mest värdefulla kampanj personal  <br/> |
|Beskrivning  <br/> |Kontrollera de viktigaste personal och vår domän inte är att personifiera.  <br/> |
|Lägga till användare för att skydda  <br/> |Välj **Lägg till ett villkor mottagaren är +**. Skriv användarnamn eller ange e-postadressen kandidaten, chef för kampanjen och andra viktiga personalen. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.  <br/> |
|Lägga till domäner för att skydda  <br/> |Välj **Lägg till ett villkor, mottagarens domän är +**. Ange anpassade domäner som är associerade med ditt Microsoft 365 abonnemang om du har definierat en. Du kan ange mer än en domän.  <br/> |
|Välj åtgärder  <br/> |Om e-post skickas av en personifierad användare: Välj **omdirigera meddelandet till en annan e-postadress**och Skriv e-postadressen security administrator. till exempel *Alice<span><span>@contoso.com*.          Om e-post skickas av en personifierad domän: Välj **karantän meddelande**.  <br/> |
|Postlåda intelligence  <br/> |Postlåda intelligence väljs som standard när du skapar en ny princip för anti-phishing. Lämna den här inställningen **på** för bästa resultat.  <br/> |
|Lägga till betrodda avsändare och domäner  <br/> |Här kan du lägga till din egen domän eller i betrodda domäner.  <br/> |
|Tillämpas på  <br/> |Välj **mottagarens domän är**. Markera **Välj**under **någon av dessa**. Välj **+ Lägg till**. Markera kryssrutan bredvid namnet på domänen, till exempel *contoso.<span> <span>com*i listan och välj sedan **Lägg till**. Välj **klar**.  <br/> |
   
Mer information finns i [Konfigurera Office 365 ATP anti-phishing principer](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Skydda dig mot skadliga bifogade filer och filer med ATP säkra bifogade filer

Personer som regelbundet skicka ta emot och dela bifogade filer som dokument, presentationer, kalkylblad och mer. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig genom att bara titta på ett e-postmeddelande. Office 365 Advanced Threat Protection innehåller skydd för ATP säker bifogad fil, men detta skydd aktiveras inte som standard. Vi rekommenderar att du skapar en ny regel om du vill börja använda detta skydd. Detta skydd sträcker sig till filer i SharePoint, OneDrive och Microsoft-Teams.
  
Titta på [det här korta videoklippet](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)om du vill skapa en princip för säker bifogad fil ATP eller utför du följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto. 
    
2. I Office 365 säkerhet &amp; regelefterlevnadscentret, i den vänstra navigeringsrutan under **Threat management**väljer **principen**.
    
3. Välj på sidan principen **ATP säkra bifogade filer**.
    
4. På sidan säkra bifogade filer gäller detta skydd brett genom att markera kryssrutan **Aktivera ATP för SharePoint, OneDrive, och Microsoft team** . 
    
5. Välj **+** att skapa en ny princip. 
    
6. Tillämpa inställningarna i följande tabell. 
    
7. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**efter behov.
    

|**Inställningen eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Blockera aktuella och framtida e-postmeddelanden med identifierade skadlig programvara.  <br/> |
|Beskrivning  <br/> |Blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierade skadlig programvara.  <br/> |
|Spara bifogade filer malware okänt svar  <br/> |Välj **Block - Blockera aktuella och framtida meddelanden och bilagor med identifierade skadlig programvara**.  <br/> |
|Dirigera om bilagan på identifiering  <br/> |Aktivera omdirigering (markerar du denna ruta) Ange administratörskontot eller en inställning av postlåda för karantän.          Gäller ovanstående urval om malware scanning för bifogade filer på grund av timeout eller fel uppstår (markerar du den här rutan).  <br/> |
|Tillämpas på  <br/> |Den mottagande domänen är. . . Välj din domän.  <br/> |
   
Mer information finns i [Konfigurera Office 365 ATP anti-phishing principer](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Skydda dig mot nätfiskeattacker med säkra ATP-länkar

Hackare dölja ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365 ATP Safe länkar (ATP Safe länkar), en del av Office 365 Advanced Threat Protection, hjälper dig att skydda din organisation genom att ge tid Klicka på kontroll av webbadresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras genom ATP Safe länkar principer.
  
Vi rekommenderar att du gör följande:
  
- Ändra standardprincipen för att öka skyddet.
    
- Lägga till en ny princip som riktar sig till alla mottagare i din domän.
    
Titta på [den här korta videon utbildning](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)om du vill konfigurera ATP Safe länkar eller utför du följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto. 
    
2. I Office 365 säkerhet &amp; regelefterlevnadscentret, i den vänstra navigeringsrutan under **Threat management**väljer **principen**.
    
3. Välj **Säker ATP-länkar**på sidan principen.
    
Så här ändrar du standardprincipen:
  
1. Välj princip för **standard** på sidan säkra länkar under **principer som gäller för hela organisationen**. 
    
2. Markera **Office 365 ProPlus, Office för iOS och Android**under **inställningar som gäller för innehåll utom e-post**.
    
3. Klicka på **Spara**. 
    
Skapa en ny princip som riktar sig till alla mottagare i din domän:
  
1. På sidan säkra länkar under **principer som gäller för hela organisationen**, **+** att skapa en ny princip. 
    
2. Tillämpa inställningarna som visas i följande tabell.
    
3. Klicka på **Spara**. 

|**Inställningen eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Princip för säker länkar för alla mottagare i domänen  <br/> |
|Välj åtgärden för okända skadliga URL: er i meddelanden  <br/> |Välj **på - URL: er ska skrivas om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken**.  <br/> |
|Använd säkra bifogade filer ska sökas igenom nedladdningsbart innehåll  <br/> |Markera den här rutan.  <br/> |
|Tillämpas på  <br/> |Den mottagande domänen är. . . Välj din domän.  <br/> |
   
Mer information finns i [Office 365 ATP safe länkar](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Gå till Intune administratörscenter

1. Logga in på [Azure portal](https://portal.azure.com/).

2. Markera **alla tjänster** och Skriv i *Intune* i **Sökrutan**.

3. När resultatet visas klickar du på start nästa **Microsoft Intune** så att det blir en favorit och lätta att hitta senare.

Förutom administratörscenter, kan du använda Intune för att registrera och hantera enheter i din organisation. Mer information finns i [funktioner som metod för certifikatregistrering för Windows-enheter](https://docs.microsoft.com/intune/enrollment-method-capabs) och [registreringsalternativ för enheter som hanteras av Intune](https://docs.microsoft.com/intune/enrollment-options).
