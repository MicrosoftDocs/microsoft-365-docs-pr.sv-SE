---
title: Öka skyddet mot hot för Microsoft 365 Business
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Avancerat skydd mot hot och skydda känsliga data.
ms.openlocfilehash: 00a40ceb6d51add2ebe8cc7ca4c299fe07a10b89
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320117"
---
# <a name="increase-threat-protection"></a>Öka skyddet mot hot

Den här artikeln hjälper dig att öka skyddet i din Microsoft 365-prenumeration för att skydda mot nätfiske, skadlig kod och andra hot. Dessa rekommendationer är lämpliga för organisationer med ett ökat behov av säkerhet, som advokatbyråer och vårdcentraler.

Kontrollera din Office 365 Secure score innan du börjar. Office 365 Secure score analyserar din Office 365-organisations säkerhet baserat på dina vanliga aktiviteter och säkerhetsinställningar och tilldelar en poäng. Börja med att notera din nuvarande poäng. Slutför åtgärderna som rekommenderas i den här artikeln om du vill öka poängen. Målet är inte att uppnå maximal poäng, men att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar produktiviteten för dina användare. 

Mer information finns i [Microsoft Secure score](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höj skyddsnivån mot skadlig kod i Mail

Din Office 365 eller Microsoft 365-miljö innehåller skydd mot skadlig kod. Du kan öka skyddet genom att blockera bilagor med filtyper som ofta används för skadlig kod. För att öka Malware Protection i e-post:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med autentiseringsuppgifterna för administratörskontot. 
    
2. I &amp; Office 365 Security Compliance Center, i det vänstra navigeringsfönstret, under **Threat Management**, väljer du **policy** \> **anti-malware**.
    
3. Dubbelklicka på standardprincipen om du vill redigera policyn för hela företaget.
    
4. Välj **Inställningar**.
    
5. Under **vanliga bilage typer filter**väljer du **på**. De filtyper som blockeras visas i fönstret direkt under den här kontrollen. Se till att du lägger till följande filtyper:
   - ade, ADP, Ani, bas, bat, chm, cmd, com, cpl, CRT, HLP, HT, HTA, inf, ins, ISP, Job, js, jse, lnk, MDA, MDB, MDE, MDZ, MSC, MSI, msp, MST, PCD, REG, SCR, Sct, SHS, URL, VB, VBE, vbs, WSC, WSF, WSH, exe, PIF  <br/> 
   
   Om det behövs kan du lägga till eller ta bort filtyper senare.
    
6. Välj **Spara.**
    
Mer information finns i [skydd mot skadlig kod](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Skydda mot Ransomware

Ransomware begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Det försöker sedan pressa pengar från offren genom att be om "lösen", vanligtvis i form av kryptovalutor som Bitcoin, i utbyte mot tillgång till data. 
  
Om du vill skydda mot Ransomware skapar du en eller flera e-postflödesregler för att blockera filtillägg som ofta används för ransomware. (Du har lagt till dessa regler i [höja nivån av skydd mot skadlig kod i Mail](#raise-the-level-of-protection-against-malware-in-mail) steg.) Du kan också varna användare som får dessa bilagor i e-post.

Förutom de filer som du blockerade i föregående steg, är det en bra vana att skapa en regel för att varna användare innan du öppnar bilagor för Office-filer som innehåller makron. Ransomware kan döljas inuti makron, så varna användare att inte öppna dessa filer från personer som de inte känner.

Så här skapar du en regel för e-transport:
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>Gå till administratörscenter på och välj **admin Centers** \> **Exchange**.
    
2. Välj **regler**i kategorin **e-postflöde** .
    
3. Välj **+** och välj sedan **skapa en ny regel**.
    
4. Välj **fler alternativ** längst ned i dialogrutan om du vill se en fullständig uppsättning alternativ. 
    
5. Tillämpa inställningarna i följande tabell för regeln. Använd standardvärdena för resten av inställningarna om du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användare innan bilagor till Office-filer öppnas**||
|:-----|:-----|:-----|
|Namn  <br/> |Anti-Ransomware-regel: varna användare  <br/>  |
|Tillämpa den här regeln om. . .  <br/> |Någon bifogad fil. . . filändelsen matchningar. . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till följande filtyper:  <br/> dotm, DOCM, xlsm, sltm, xla, XLAM, XLL, PPTM, POTM, PPAM, PPSM, sldm  <br/>|
|Gör följande. . .  <br/> |Meddela mottagaren med ett meddelande  <br/> |
|Ange meddelandetext  <br/> |Öppna inte de här typerna av filer från personer som du inte känner till eftersom de kan innehålla makron med skadlig kod.  <br/> |
   
Mer information finns i:
  
- [Hur man handskas med Ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Återskapa din OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordran för e-post

Hackare som får åtkomst till en användares postlåda kan stjäla e-post genom att ställa in brevlådan så att e-post automatiskt vidarebefordras. Detta kan inträffa även utan användarens medvetenhet. Konfigurera en regel för e-postflöde för att förhindra att detta händer. 
  
Om du vill skapa en regel för transport av e-post kan du titta på [den korta videon](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) eller följa dessa steg:
  
1. I den Microsoft 365 administratörscenter, Välj **admin Centers** \> **Exchange**.
    
2. Välj **regler**i kategorin **e-postflöde** .
    
3. Välj **+** och välj sedan **skapa en ny regel**.
    
4. Om du vill visa alla alternativ väljer du **fler alternativ** längst ned i dialogrutan. 
    
5. Använd inställningarna i följande tabell. Använd standardvärdena för resten av inställningarna om du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användare innan bilagor till Office-filer öppnas**|
|:-----|:-----|
|Namn  <br/> |Förhindra automatisk vidarebefordran av e-post till externa domäner  <br/> |
|Använd den här regeln om...  <br/> |Avsändaren. . . är extern/intern. . . Inom organisationen  <br/> |
|Lägg till villkor  <br/> |Meddelandeegenskaperna. . . inkludera meddelandetypen. . . Auto-Forward  <br/> |
|Gör följande...  <br/> |Blockera meddelandet. . . avvisa meddelandet och inkludera en förklaring.  <br/> |
|Ange meddelandetext  <br/> |Automatisk vidarebefordran av e-post utanför den här organisationen förhindras av säkerhetsskäl.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post mot phishing-attacker

Om du har konfigurerat en eller flera anpassade domäner för din Office 365-eller Microsoft 365-miljö kan du konfigurera riktat skydd mot nätfiske. ATP anti-phishing Protection, en del av Office 365 Advanced Threat Protection, kan hjälpa till att skydda din organisation från skadliga personifiering-baserade phishing-attacker och andra phishing-attacker. Om du inte har konfigurerat en anpassad domän behöver du inte göra detta.
  
Vi rekommenderar att du börjar med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän. 

Om du vill skapa en anti-phishing-policy för ATP, titta på [den här korta utbildningsvideon](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)eller utför följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com). 
    
2. I Office 365 Security &amp; regelefterlevnadscenter, i det vänstra navigeringsfönstret under **Threat Management**, Välj **princip**.
    
3. På sidan **princip** väljer du **ATP anti-phishing**.
    
4. På sidan **mot nätfiske** väljer du **+ skapa**. En guide startas som steg dig genom att definiera din anti-phishing-policy.
    
5. Ange namn, beskrivning och inställningar för principen som rekommenderas i följande tabell. Mer information finns i [Lär dig mer om ATP anti-phishing principalternativ](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options). 
    
6. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**, efter behov.
    

|**Inställning eller alternativ**<br/>|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Domän och mest värdefulla kampanj personal  <br/> |
|Beskrivning  <br/> |Se till att den viktigaste personalen och vår domän inte personieras.  <br/> |
|Lägg till användare för att skydda  <br/> |Välj **+ Lägg till ett villkor, mottagaren är**. Skriv användarnamn eller ange e-postadressen till kandidaten, kampanj hanteraren och andra viktiga personal medlemmar. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda mot personifiering.  <br/> |
|Lägg till domäner för att skydda  <br/> |Välj **+ Lägg till ett villkor, mottagar domänen är**. Ange den anpassade domänen som är associerad med din Microsoft 365-prenumeration, om du har definierat en. Du kan ange fler än en domän.  <br/> |
|Välj åtgärder  <br/> |Om e-post skickas av en personiserad användare: Välj **omdirigera meddelande till en annan e-postadress**och skriv sedan e-postadressen till säkerhetsadministratören. till exempel *Alice<span><span>@contoso. com*. Om e-post skickas av en personiserad domän: Välj **karantän meddelande**.  <br/> |
|Postlåda intelligens  <br/> |Som standard väljs postlådeinformation när du skapar en ny policy mot nätfiske. Låt den här inställningen vara **på** för bästa resultat.  <br/> |
|Lägga till betrodda avsändare och domäner  <br/> |Här kan du lägga till din egen domän eller andra betrodda domäner.  <br/> |
|Tillämpas på  <br/> |Välj **mottagar domänen**. Välj **Välj**under **något av dessa**. Välj **+ Lägg till**. Markera kryssrutan bredvid namnet på domänen, till exempel *contoso.<span> com <span>*, i listan och välj sedan **Lägg till**. Välj **klar**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Skydda mot skadliga bilagor och filer med ATP Safe bilagor

Personer skickar, tar emot och delar regelbundet bilagor, till exempel dokument, presentationer, kalkylark med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Office 365 Advanced Threat Protection innehåller skydd för ATP säker bifogad fil, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Det här skyddet omfattar filer i SharePoint, OneDrive och Microsoft Teams.
  
Om du vill skapa en säker bifogad princip för ATP, antingen titta på [den här korta videon](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller utför följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com)och logga in med ditt administratörskonto. 
    
2. I Office 365 Security &amp; regelefterlevnadscenter, i det vänstra navigeringsfönstret under **Threat Management**, Välj **princip**.
    
3. På sidan princip väljer du **ATP säkra bilagor**.
    
4. På den säkra bilagor sidan, tillämpa det här skyddet i stort sett genom att markera kryssrutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** . 
    
5. Välj **+** om du vill skapa en ny princip. 
    
6. Använd inställningarna i följande tabell. 
    
7. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**, efter behov.
    

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Blockera aktuella och framtida e-postmeddelanden med identifierad skadlig kod.  <br/> |
|Beskrivning  <br/> |Blockera aktuella och framtida e-postmeddelanden och bilagor med identifierad skadlig kod.  <br/> |
|Spara bilagor okänt malware svar  <br/> |Välj **blockera-blockera aktuella och framtida e-postmeddelanden och bilagor med identifierad skadlig kod**.  <br/> |
|Omdirigera bifogad fil vid identifiering  <br/> |Aktivera omdirigering (Markera den här rutan) ange administratörskontot eller en postlådeinställning för karantän.          Tillämpa ovanstående val om malware skanning för bilagor timeout eller fel uppstår (Markera den här rutan).  <br/> |
|Tillämpas på  <br/> |Mottagar domänen är. . . Välj din domän.  <br/> |
   
Mer information finns [i ställa in Office 365 ATP anti-phishing principer](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Skydda mot phishing-attacker med ATP Safe Links

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365 ATP Safe länkar (ATP Safe Links), en del av Office 365 Advanced Threat Protection, kan hjälpa till att skydda din organisation genom att tillhandahålla tid-för-klick-verifiering av webbadresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras via ATP Safe Links-principer.
  
Vi rekommenderar att du gör följande:
  
- Ändra standardprincipen för att öka skyddet.
    
- Lägg till en ny princip riktad till alla mottagare i domänen.
    
För att ställa in ATP Safe Links, titta på [denna korta utbildning video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), eller utföra följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com)och logga in med ditt administratörskonto. 
    
2. I Office 365 Security &amp; regelefterlevnadscenter, i det vänstra navigeringsfönstret under **Threat Management**, Välj **princip**.
    
3. På sidan princip väljer du **ATP Safe Links**.
    
Så här ändrar du standardprincipen:
  
1. Välj **standard** principen under **principer som gäller för hela organisationen**på sidan säkra länkar. 
    
2. Under **inställningar som gäller innehåll utom e-post**väljer du **Office 365 ProPlus, Office för iOS och Android**.
    
3. Välj **Spara**. 
    
Så här skapar du en ny princip riktad till alla mottagare i domänen:
  
1. På sidan säkra länkar, under **principer som gäller för hela organisationen**, väljer **+** du för att skapa en ny princip. 
    
2. Använd inställningarna som visas i följande tabell.
    
3. Välj **Spara**. 

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Princip för säkra Länkar för alla mottagare i domänen  <br/> |
|Välj åtgärden för okända potentiellt skadliga webbadresser i meddelanden  <br/> |Välj **on-URLs kommer att skrivas om och kontrolleras mot en lista över kända skadliga länkar när användaren klickar på länken**.  <br/> |
|Använd säkra bilagor för att skanna nedladdningsbart innehåll  <br/> |Markera den här rutan.  <br/> |
|Tillämpas på  <br/> |Mottagar domänen är. . . Välj din domän.  <br/> |
   
Mer information finns i [Office 365 ATP Safe Links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Gå till Intune administratörscenter

1. Logga in på [Azure Portal](https://portal.azure.com/).

2. Välj **alla tjänster** och skriv i *Intune* i **sökrutan**.

3. När resultatet visas väljer du Start bredvid **Microsoft Intune** för att göra det till en favorit och lätt att hitta senare.

Förutom administratörscenter kan du använda Intune för att registrera och hantera organisationens enheter. Mer information finns i [funktioner efter registreringsmetod för Windows-enheter](https://docs.microsoft.com/intune/enrollment-method-capabs) och [registreringsalternativ för enheter som hanteras av Intune](https://docs.microsoft.com/intune/enrollment-options).
