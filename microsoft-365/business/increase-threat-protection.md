---
title: Öka hotskyddet för Microsoft 365 Business
f1.keywords:
- NOCSH
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Advanced Threat Protection och skydda känsliga data mot nätfiske, skadlig kod och andra hot.
ms.openlocfilehash: 9d7bae60091c87fa0246a697f2a49e1cbc6e2f06
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550366"
---
# <a name="increase-threat-protection"></a>Öka hotskyddet

Den här artikeln hjälper dig att öka skyddet i din Microsoft 365-prenumeration för att skydda mot nätfiske, skadlig kod och andra hot. Dessa rekommendationer är lämpliga för organisationer med ett ökat behov av säkerhet, som advokatbyråer och vårdcentraler.

Innan du börjar kontrollerar du ditt säkra Office 365-resultat. Office 365 Secure Score analyserar din Office 365-organisations säkerhet baserat på dina vanliga aktiviteter och säkerhetsinställningar och tilldelar en poäng. Börja med att notera din nuvarande poäng. Om du vill öka poängen fyller du i de åtgärder som rekommenderas i den här artikeln. Målet är inte att uppnå maximal poäng, utan att vara medveten om möjligheter att skydda din miljö som inte påverkar produktiviteten negativt för användarna. 

Mer information finns i [Microsoft Secure Score](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja skyddsnivån mot skadlig kod med e-post

Din Office 365- eller Microsoft 365-miljö innehåller skydd mot skadlig kod. Du kan öka det här skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig kod. Så här ökar du skyddet för skadlig kod i e-post:
  
1. Gå [https://protection.office.com](https://protection.office.com) till och logga in med dina administratörskontouppgifter. 
    
2. Välj **Princip** \> **anti-malware**i det vänstra navigeringsfönstret **** i Office 365 Security &amp; Compliance Center.
    
3. Dubbelklicka på standardprincipen för att redigera den här företagsomfattande principen.
    
4. Välj **Inställningar**.
    
5. Välj På under **Filtret Vanliga bifogade filer**väljer du **På**. De filtyper som är blockerade visas i fönstret direkt under den här kontrollen. Se till att du lägger till de här filtyperna:
   - ade, adp, ani, bas, fladdermus, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, jobb, js, js, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> 
   
   Om det behövs kan du lägga till eller ta bort filtyper senare.
    
6. Välj **Spara.**
    
Mer information finns i [Skydd mot skadlig kod](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="protect-against-ransomware"></a>Skydda mot ransomware

Ransomware begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Det försöker sedan pressa pengar från offren genom att be om "lösen", vanligtvis i form av kryptokurvor som Bitcoin, i utbyte mot tillgång till data. 
  
Om du vill skydda mot ransomware skapar du en eller flera regler för e-postflöde för att blockera filtillägg som ofta används för ransomware. (Du har lagt till dessa regler i [höjningen av skyddsnivån mot skadlig kod i e-poststeg.)](#raise-the-level-of-protection-against-malware-in-mail) Du kan också varna användare som får dessa bilagor i e-post.

Förutom de filer som du blockerade i föregående steg är det en bra idé att skapa en regel för att varna användarna innan du öppnar bifogade filer i Office som innehåller makron. Ransomware kan döljas inuti makron, så varna användarna att inte öppna dessa filer från människor som de inte känner.

Så här skapar du en regel för e-posttransport:
  
1. Gå <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>till administrationscentret på och välj Admin **centers** \> **Exchange**.
    
2. Välj **regler**i kategorin **e-postflöde** .
    
3. Markera **+** och välj sedan **Skapa en ny regel**.
    
4. Välj **Fler alternativ** längst ned i dialogrutan om du vill se hela uppsättningen alternativ. 
    
5. Använd inställningarna i följande tabell för regeln. Använd standardvärdena för resten av inställningarna, såvida du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användarna innan du öppnar bifogade filer för Office-filer**||
|:-----|:-----|:-----|
|Namn  <br/> |Anti-ransomware regel: varna användare  <br/>  |
|Använd den här regeln om . . .  <br/> |Alla bifogade filer . . . filändelsen matchar . . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till dessa filtyper:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/>|
|Gör följande . . .  <br/> |Meddela mottagaren med ett meddelande  <br/> |
|Ange meddelandetext  <br/> |Öppna inte dessa typer av filer från personer som du inte känner eftersom de kan innehålla makron med skadlig kod.  <br/> |
   
Mer information finns i:
  
- [Hur man handskas med ransomware](https://go.microsoft.com/fwlink/?linkid=2016501)
    
- [Återställa din OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordran för e-post

Hackare som får åtkomst till en användares postlåda kan stjäla e-post genom att ange postlådan för att automatiskt vidarebefordra e-post. Detta kan ske även utan användarens medvetenhet. Om du vill förhindra att detta händer konfigurerar du en regel för e-postflöde. 
  
Om du vill skapa en e-posttransportregel kan du antingen titta på [den här korta videon](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) eller följa följande steg:
  
1. Välj **Administrationscenter** \> **Exchange**i administrationscentret för Microsoft 365.
    
2. Välj **regler**i kategorin **e-postflöde** .
    
3. Markera **+** och välj sedan **Skapa en ny regel**.
    
4. Om du vill visa alla alternativ väljer du **Fler alternativ** längst ned i dialogrutan. 
    
5. Använd inställningarna i följande tabell. Använd standardvärdena för resten av inställningarna, såvida du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användarna innan du öppnar bifogade filer för Office-filer**|
|:-----|:-----|
|Namn  <br/> |Förhindra automatisk vidarebefordran av e-post till externa domäner  <br/> |
|Tillämpa den här regeln om ...  <br/> |Avsändaren . . . är extern/intern . . . Inuti organisationen  <br/> |
|Lägg till villkor  <br/> |Meddelandeegenskaperna . . . inkludera meddelandetypen . . . Framåt automatiskt  <br/> |
|Gör följande ...  <br/> |Blockera meddelandet . . . avvisa meddelandet och inkludera en förklaring.  <br/> |
|Ange meddelandetext  <br/> |Skicka e-post automatiskt utanför den här organisationen förhindras av säkerhetsskäl.  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiskeattacker

Om du har konfigurerat en eller flera anpassade domäner för din Office 365- eller Microsoft 365-miljö kan du konfigurera riktat skydd mot nätfiske. ATP-skydd mot nätfiske, en del av Office 365 Advanced Threat Protection, kan skydda din organisation från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en anpassad domän behöver du inte göra det.
  
Vi rekommenderar att du kommer igång med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän. 

Om du vill skapa en ATP-policy för nätfiske kan du titta på [den här korta träningsvideon](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)eller slutför följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com). 
    
2. Välj **Princip**i det &amp; vänstra navigeringsfönstret i Office **** 365 Security Compliance Center.
    
3. På sidan **Policy** väljer du **ATP-antinätfiske**.
    
4. På **sidan Motnätsfiske** väljer du **+ Skapa**. En guide startar som leder dig genom att definiera din anti-phishing-policy.
    
5. Ange namn, beskrivning och inställningar för principen enligt beskrivningen i följande tabell. Mer information finns i [Lär dig mer om atp-alternativ för antinätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#learn-about-atp-anti-phishing-policy-options). 
    
6. När du har granskat dina inställningar väljer du **Skapa den här principen** eller **Spara**, beroende på vad som är lämpligt.
    

|**Inställning eller alternativ**<br/>|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Domän och mest värdefulla kampanjpersonal  <br/> |
|Beskrivning  <br/> |Se till att de viktigaste personalen och vår domän inte personifieras.  <br/> |
|Lägga till användare att skydda  <br/> |Välj **+ Lägg till ett villkor, mottagaren är**. Skriv användarnamn eller ange e-postadressen för kandidaten, kampanjchefen och andra viktiga medarbetare. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda mot personifiering.  <br/> |
|Lägga till domäner för att skydda  <br/> |Välj **+ Lägg till ett villkor, mottagardomänen är**. Ange den anpassade domän som är associerad med din Microsoft 365-prenumeration om du har definierat en sådan. Du kan ange mer än en domän.  <br/> |
|Välj åtgärder  <br/> |Om e-post skickas av en personifierat användare: Välj **Omdirigera meddelande till en annan e-postadress**och skriv sedan säkerhetsadministratörens e-postadress. Till exempel *<span><span>Alice @contoso.com*. Om e-post skickas av en personifierat domän: Välj **Karantänmeddelande**.  <br/> |
|Information om brevlådan  <br/> |Som standard väljs postlådeinformation när du skapar en ny anti-phishing-princip. Lämna den här inställningen **På** för bästa resultat.  <br/> |
|Lägga till betrodda avsändare och domäner  <br/> |Här kan du lägga till din egen domän eller andra betrodda domäner.  <br/> |
|Tillämpad på  <br/> |Välj **Mottagardomänen är**. Under **något av dessa**väljer du **Välj**. Välj **+ Lägg till**. Markera kryssrutan bredvid namnet på domänen, till exempel *contoso.<span> com <span>*, i listan, och välj sedan **Lägg till**. Välj **Klar**.  <br/> |
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Skydda mot skadliga bilagor och filer med ATP-säkra bilagor

Personer skickar, tar emot och delar regelbundet bilagor, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Office 365 Advanced Threat Protection innehåller SKYDD FÖR BETRODD akvarstad i ATP, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Det här skyddet sträcker sig till filer i SharePoint, OneDrive och Microsoft Teams.
  
Om du vill skapa en atp-princip för säker bifogad fil kan du antingen titta på [den här korta videon](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller slutföra följande steg:
  
1. Gå [https://protection.office.com](https://protection.office.com)till och logga in med ditt administratörskonto. 
    
2. Välj **Princip**i det &amp; vänstra navigeringsfönstret i Office **** 365 Security Compliance Center.
    
3. På sidan Policy väljer du **AP-säkra bilagor**.
    
4. På sidan Betrodda bilagor använder du det här skyddet i stort sett genom att markera kryssrutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.** 
    
5. Välj **+** om du vill skapa en ny princip. 
    
6. Använd inställningarna i följande tabell. 
    
7. När du har granskat dina inställningar väljer du **Skapa den här principen** eller **Spara**, beroende på vad som är lämpligt.
    

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig kod.  <br/> |
|Beskrivning  <br/> |Blockera aktuella och framtida e-postmeddelanden och bilagor med upptäckt skadlig kod.  <br/> |
|Spara bifogade filer okänt svar om skadlig kod  <br/> |Välj **Block - Blockera aktuella och framtida e-postmeddelanden och bilagor med upptäckt skadlig kod**.  <br/> |
|Omdirigera bifogad fil vid identifiering  <br/> |Aktivera omdirigering (välj den här rutan) Ange administratörskontot eller en postlådeinställning för karantän.          Använd ovanstående val om malware skanning för bilagor timeout eller fel inträffar (välj den här rutan).  <br/> |
|Tillämpad på  <br/> |Mottagardomänen är . . . välj din domän.  <br/> |
   
Mer information finns i [Konfigurera Office 365 ATP-policyer för nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Skydda mot nätfiskeattacker med ATP-säkra länkar

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365 ATP Safe Links (ATP Safe Links), en del av Office 365 Advanced Threat Protection, kan skydda din organisation genom att tillhandahålla tidsklicka verifiering av webbadresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras genom ATP Safe Links-principer.
  
Vi rekommenderar att du gör följande:
  
- Ändra standardprincipen för att öka skyddet.
    
- Lägg till en ny princip riktad till alla mottagare i domänen.
    
Så här konfigurerar du ATP Safe Links genom att titta på [den här korta träningsvideon](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)eller slutför följande steg:
  
1. Gå [https://protection.office.com](https://protection.office.com)till och logga in med ditt administratörskonto. 
    
2. Välj **Princip**i det &amp; vänstra navigeringsfönstret i Office **** 365 Security Compliance Center.
    
3. På sidan Policy väljer du **ATP-säkra länkar**.
    
Så här ändrar du standardprincipen:
  
1. Välj **standardprincipen** under **Principer som gäller för hela organisationen**på sidan Säkra länkar. 
    
2. Under **Inställningar som gäller för innehåll utom e-post**väljer du Office **365 ProPlus, Office för iOS och Android**.
    
3. Välj **Spara**. 
    
Så här skapar du en ny princip riktad till alla mottagare i domänen:
  
1. På sidan Säkra länkar väljer du **+** för att skapa en ny princip under Principer som gäller för hela **organisationen.** 
    
2. Använd inställningarna i följande tabell.
    
3. Välj **Spara**. 

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Princip för säkra länkar för alla mottagare i domänen  <br/> |
|Välj åtgärd för okända potentiellt skadliga webbadresser i meddelanden  <br/> |Välj **På - Webbadresser skrivs om och kontrolleras mot en lista över kända skadliga länkar när användaren klickar på länken**.  <br/> |
|Använd säkra bifogade filer för att skanna nedladdningsbart innehåll  <br/> |Markera den här rutan.  <br/> |
|Tillämpad på  <br/> |Mottagardomänen är . . . välj din domän.  <br/> |
   
Mer information finns i [Office 365 ATP-säkra länkar](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).

## <a name="go-to-intune-admin-center"></a>Gå till Administrationscentret för Intune

1. Logga in på [Azure-portalen](https://portal.azure.com/).

2. Välj **Alla tjänster** och skriv in *Intune* i **sökrutan**.

3. När resultaten visas väljer du början **bredvid Microsoft Intune** för att göra det till en favorit och lätt att hitta senare.

Förutom administrationscentret kan du använda Intune för att registrera och hantera organisationens enheter. Mer information finns i [Funktioner genom att registrera metod för Windows-enheter](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) och [registreringsalternativ för enheter som hanteras av Intune](https://docs.microsoft.com/intune/enrollment-options).
