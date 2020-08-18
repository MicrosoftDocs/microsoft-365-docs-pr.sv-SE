---
title: De 10 bästa sätten att skydda Microsoft 365 för företag-abonnemang
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: 'Skydda dina företags meddelanden och data från cyberterrorism hot, inklusive utpressnings tro Jan, nätfiske och illvilliga filer. '
ms.openlocfilehash: c5ae75bea68f56cb1ba028500a1f206603332717
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778308"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>De 10 bästa sätten att skydda Microsoft 365 för företag-abonnemang

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du är en liten eller medels Tor organisation med en av Microsofts affärs abonnemang och din organisations typ är riktad mot cyberterrorism kriminella och hackare kan du använda vägledningen i den här artikeln för att öka säkerheten i organisationen. Den här vägledningen hjälper organisationen att nå de mål som beskrivs i Harvard Kennedy School [Cybersecurity kampanj hand bok](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409).
  
Microsoft rekommenderar att du utför de uppgifter som visas i följande tabell som gäller för din service plan. 
  
||**Uppgift**|**Microsoft 365 Business Standard**|**Microsoft 365 Business Premium**|
|:-----|:-----|:-----|:-----|
|9.1  <br/> |[Konfigurera multifaktorautentisering](secure-your-business-data.md#setup) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|två  <br/> |[Utbilda dina användare](secure-your-business-data.md#train) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|amp;3D  <br/> |[Använda dedikerade administratörs konton](secure-your-business-data.md#admin) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9.4  <br/> |[Höja nivån på skyddet mot skadlig program vara i e-post](secure-your-business-data.md#malware) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|T5  <br/> |[Skydda mot utpressningstrojaner](secure-your-business-data.md#ransomware) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|18.6  <br/> |[Stoppa automatisk vidarebefordring för e-post](secure-your-business-data.md#forwarding) <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|borttagning  <br/> |[Använda Office meddelande kryptering](secure-your-business-data.md#encryption) <br/> ||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8.2  <br/> |[Skydda din e-post från nätfiske-attacker](secure-your-business-data.md#phishing) <br/> ||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9  <br/> |[Skydda mot skadlig bifogad fil och filer med säkra filer för ATP](secure-your-business-data.md#atp) <br/> ||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10.3  <br/> |[Skydda mot nätfiske-attacker med säkra ATP-länkar](secure-your-business-data.md#phishingatp) <br/> ||![Förts](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
Innan du börjar bör du kontrol lera din [microsoft 365 säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) i Microsoft 365 säkerhets Center. Från en central instrument panel kan du övervaka och förbättra säkerheten för dina Microsoft 365-identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (som att visa rapporter) eller adress rekommendationer med en tredje parts program eller program vara. Med ytterligare insikter och mer insyn i en bredare uppsättning Microsoft-produkter och-tjänster kan du känna dig säker på hur din organisations säkerhets tillstånd fungerar.
  
![Skärm bild av Microsofts säkra Poäng](../../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1: Konfigurera multifaktorautentisering
<a name="setup"> </a>

Att använda multifaktorautentisering är ett av de enklaste och mest effektiva sätten att öka säkerheten i organisationen. Det är enklare än att det låter: när du loggar in innebär multifaktorautentisering att du skriver en kod från telefonen för att få till gång till Microsoft 365. Detta kan förhindra att hackare tar över om de känner till ditt lösen ord. Multifaktorautentisering kallas också för tvåstegsverifiering. Enskilda personer kan lägga till tvåstegsverifiering till de flesta konton, till exempel till sina Google-eller Microsoft-konton. Så här lägger du [till tvåstegsverifiering för ditt personliga Microsoft-konto](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409).
  
För företag som använder Microsoft 365 lägger du till en inställning som kräver att användarna loggar in med multifaktorautentisering. När du gör den här ändringen uppmanas användarna att konfigurera sin telefon för tvåfaktorautentisering nästa gång de loggar in.
Om du vill se en utbildnings video om hur du konfigurerar MFA och hur användarna ska konfigureras kan du läsa [Konfigurera MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) och konfigurera [användare](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225).
  
För att konfigurera multifaktorautentisering kan du aktivera säkerhets standarder:

För de flesta organisationer tillhandahåller standardinställningar för säkerhet en god nivå av ytterligare inloggningssäkerhet. Mer information finns i [Vad är standardinställningar för säkerhet?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Om prenumerationen är ny kan standardinställningar för säkerhet redan vara aktiverat för dig automatiskt.

Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.

1.  Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
2.  I det vänstra navigeringsfältet väljer du **Visa alla** och under **Administratörscenter**väljer du **Azure Active Directory**.
3. I **Azure Active Directory administratörscenter** väljer du **Azure Active Directory** > **Egenskaper**.
3.  Längst ner på sidan väljer du **Hantera standardinställningar för säkerhet**.
4.  Välj **Ja** för att aktivera standardinställningar för säkerhet eller **Nej** för att inaktivera dem och välj sedan **Spara**.


När du har konfigurerat multifaktorautentisering för din organisation måste dina användare konfigurera tvåstegsverifiering på sina enheter. Mer information finns i [Konfigurera tvåstegsverifiering för Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).
  
Fullständiga uppgifter och fullständiga rekommendationer finns i [Konfigurera multifaktorautentisering för användare](set-up-multi-factor-authentication.md).
  
## <a name="2-train-your-users"></a>2: träna dina användare
<a name="train"> </a>

Det här är en utmärkt vägledning i Harvard Kennedy School [Cybersecurity-kampanjen](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) med att skapa en starkt kultur av säkerhets medvetenhet inom din organisation, inklusive utbildnings användare för att identifiera nätfiske-attacker. 
  
Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar åtgärderna som beskrivs i den här artikeln: [skydda ditt konto och dina enheter från hackare och skadlig program vara](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Dessa åtgärder inkluderar:
  
- Använda starka lösen ord
    
- Skydda enheter
    
- Aktivera säkerhetsfunktioner på datorer med Windows 10 och Mac
    
Microsoft rekommenderar också att användare skyddar sina privata e-postkonton genom att vidta åtgärder som rekommenderas i följande artiklar:
  
- [Skydda ditt Outlook.com-e-postkonto](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3: använda dedikerade administratörs konton
<a name="admin"> </a>

De administrativa konton du använder för att administrera Microsoft 365-miljön inkluderar förhöjda behörigheter. Dessa är värdefulla mål för hackare och cyberterrorism kriminella. Använd endast administratörs konton för administration. Administratörer ska ha ett separat användar konto för regelbunden, icke-administrativ användning och bara använda sitt administratörs konto när det behövs för att slutföra en uppgift som är kopplad till deras jobb funktion. Ytterligare rekommendationer:
  
- Se till att administratörs konton också är inställda för multifaktorautentisering. 
    
- Innan du använder administratörs konton kan du stänga alla icke relaterade webbläsar-och appar, inklusive personliga e-postkonton.
    
- När du har slutfört administratörs uppgifterna måste du logga ut från webbläsarsessionen.
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Höj skyddet mot skadlig program vara i e-post
<a name="malware"> </a>

Din Microsoft 365-miljö har skydd mot skadlig program vara, men du kan öka skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig program vara. Om du vill öka skyddet mot skadlig program vara i e-post kan du titta på en [kort utbildnings video](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)eller göra följande:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med dina inloggnings uppgifter för ditt administratörs konto. 
    
2. I &amp; det vänstra navigerings fönstret i Center för säkerhets kontroll väljer du **princip** mot **Threat management** \> **skadlig program vara**under Threat Management.
    
3. Dubbelklicka på standard principen för att redigera företagets policy.
    
4. Välj **Inställningar**.
    
5. Välj **på**under **vanliga typer av bifogade filer**. De filtyper som blockeras visas i fönstret direkt under den här kontrollen. Du kan lägga till och ta bort filtyper senare om det behövs.
    
6. Välj **Spara.**
    
Mer information finns i [skydda mot skadlig program vara](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="5-protect-against-ransomware"></a>5: skydda mot utpressnings tro Jan
<a name="ransomware"> </a>

Utpressnings tro Jan attack begränsar åtkomsten till data genom att kryptera filer eller låsa dator skärmar. Sedan försöker extort pengar från offer genom att be om "utpressning", vanligt vis i form av cryptocurrencies som Bitcoin, i Exchange för åtkomst till data. 
  
Du kan skydda mot utpressnings tro Jan genom att skapa en eller flera e-postflödes regler för att blockera fil namns tillägg som ofta används för utpressnings Jan program vara, eller för att varna användare som tar emot dessa bilagor En bra start punkt är att skapa två regler:
  
- Varna användare innan du öppnar bifogade filer i Office med makron. Utpressnings tro Jan kan vara dolda inuti makron, så vi meddelar användare att inte öppna de här filerna från personer som de inte känner. 
    
- Blockera filtyper som kan innehålla utpressnings tro Jan eller annan skadlig kod. Vi börjar med en gemensam lista med körbara filer (visas i tabellen nedan). Om din organisation använder någon av de här körbara typerna och du förväntar dig att få skicka meddelanden via e-post lägger du till dessa i föregående regel (varna användare).
    
Om du vill skapa en regel för e-posttransport kan du titta på en [kort utbildnings video](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)eller göra följande:
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **regler**i kategorin **e-postflöde** .
    
3. Välj **+** och skapa sedan **en ny regel**.
    
4. Välj * * * * längst ned i dialog rutan för att se alla alternativ. 
    
5. Använd inställningarna i tabellen nedan för varje regel. Låt resten av inställningarna vara standard, såvida du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användare innan du öppnar bifogade filer av Office-filer**|**Blockera filtyper som kan innehålla utpressnings tro Jan eller annan skadlig kod**|
|:-----|:-----|:-----|
|Namn  <br/> |Policy för antipressnings tro Jan: varna användare  <br/> |Regel för antipressnings skydd: blockera filtyper  <br/> |
|Använd den här regeln om. . .  <br/> |Bifogade filer. . . fil namns tillägg matchar. . .  <br/> |Bifogade filer. . . fil namns tillägg matchar. . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till följande filtyper:  <br/> dotm, DOCM, xlsm, sltm, xla, XLAM, XLL, PPTM, POTM, PPAM, PPSM, sldm  <br/> |Lägg till följande filtyper:  <br/> ade, ADP, Ani, bas, bat, chm, cmd, com, cpl, CRT, HLP, HT, HTA, inf, ins, Internet leverantör, jobb, js, jse, lnk, MDA, MDB, MDE, MDZ, MSC, MSI, msp, MST, PCD, REG, SCR, Sct, SHS, URL, VB, VBE, vbs, WSC, WSF, WSH  <br/> |
|Gör följande. . .  <br/> |Meddela mottagaren med ett meddelande  <br/> |Blockera meddelandet. . . avvisa meddelandet och ta med en förklaring  <br/> |
|Ange meddelande text  <br/> |Öppna inte dessa typer av filer – såvida du inte förväntar dem – eftersom filerna kan innehålla skadlig kod och veta att avsändaren inte är garanti för säkerheten.  <br/> ||
   
> [!TIP]
> Du kan också lägga till de filer som du vill blockera i listan med skadlig program vara i [steg 4](#4-raise-the-level-of-protection-against-malware-in-mail).

Mer information finns i:
  
- [Så hanterar du utpressnings tro Jan](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Återställa OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6: stoppa automatisk vidarebefordran för e-post
<a name="forwarding"> </a>

Hackare som får till gång till en användares post låda kan exfiltrate e-post genom att konfigurera post lådan så att e-post skickas automatiskt Detta kan inträffa även om användarens kännedom inte är medvetenhet. Du kan förhindra detta genom att konfigurera en regel för e-postflöde. 
  
Så här skapar du en e-posttransport regel:
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **regler**i kategorin **e-postflöde** .
    
3. Välj **+** och skapa sedan **en ny regel**.
    
4. Välj **fler alternativ** längst ned i dialog rutan för att visa alla alternativ. 
    
5. Använd inställningarna i följande tabell. Låt resten av inställningarna vara standard, såvida du inte vill ändra dem.
    
6. Välj **Spara**.
    
|**Inställning**|**Avvisa e-postmeddelanden som skickas automatiskt till externa domäner**|
|:-----|:-----|
|Namn  <br/> |Förhindra automatisk vidarebefordran av e-post till externa domäner  <br/> |
|Använd den här regeln om...  <br/> |Avsändaren. . . är externt/internt. . . Inom organisationen  <br/> |
|Lägg till villkor  <br/> |Mottagaren. . . är externt/internt. . . Utanför organisationen  <br/> |
|Lägg till villkor  <br/> |Meddelande egenskaper. . . inkludera meddelande typen. . . Automatisk vidarebefordran  <br/> |
|Gör följande:  <br/> |Blockera meddelandet. . . avvisa meddelandet och ta med en förklaring.  <br/> |
|Ange meddelande text  <br/> |E-post utanför organisationen förhindras automatiskt av säkerhets skäl.  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7: använda Office Message Encryption
<a name="encryption"> </a>

Office meddelande kryptering ingår i Microsoft 365. Den är redan konfigurerad. Med Office Message Encryption kan organisationen skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. Office 365 meddelande kryptering fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. Kryptering via e-post säkerställer att endast avsedda mottagare kan visa meddelande innehåll.
  
Office meddelande kryptering ger två skydds alternativ när du skickar e-post:
  
- Vidarekoppla inte
    
- Inträffade
    
Din organisation kan ha konfigurerat ytterligare alternativ som använder en etikett i e-postmeddelandet, till exempel konfidentiellt.
  
### <a name="to-send-protected-email"></a>Skicka skyddad e-post

I Outlook för PC väljer du **alternativ** i e-postmeddelandet och väljer sedan **behörigheter**. 
  
![Kryptering av e-postmeddelanden i Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
I Outlook.com väljer du **skydda** i e-postmeddelandet. Standard skyddet **vidarebefordras inte**. Om du vill ändra detta för kryptering väljer du **ändra behörigheter** för \> **kryptera**. 
  
![E-postkryptering i Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>Ta emot krypterad e-post

Om mottagaren har Outlook 2013 eller Outlook 2016 och ett Microsoft-e-postkonto visas en avisering om objektets begränsade behörigheter i Läs fönstret. När du har öppnat meddelandet kan mottagaren Visa meddelandet på samma sätt som andra.
  
Om mottagaren använder en annan e-postklient eller ett e-postkonto, till exempel Gmail eller Yahoo, visas en länk som gör att de kan logga in för att läsa e-postmeddelandet eller begära att ett lösen ord i en webbläsare visas. Om användarna inte får e-postmeddelandet kan de kontrol lera mappen skräp post eller skräppostmappen. 
  
Mer information finns i [skicka, Visa och svara på krypterade meddelanden i Outlook för PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. skydda din e-post från nätfiske-attacker
<a name="phishing"> </a>

Om du har konfigurerat en eller flera egna domäner för Microsoft 365-miljön kan du konfigurera riktat mot nätfiske-skydd. ATP-skydd mot nätfiske, en del av Office 365 Avancerat skydd mot obehöriga attacker och andra nät fiske attacker. Om du inte har konfigurerat en egen domän behöver du inte göra detta.
  
Vi rekommenderar att du kommer igång med detta skydd genom att skapa en princip för att skydda de viktigaste användarna och din egen domän. 
  
![Skapa en policy för Stöldskydd mot nätfiske](../../media/security-and-compliance-center.png)
  
Om du vill skapa en Antivirus policy för ATP kan du titta på en [kort utbildnings video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)eller göra följande:
  
1. Gå till [https://protection.office.com](https://protection.office.com). 
    
2. &amp;Välj **princip**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**
    
3. Välj **ATP-nätfiske**på sidan policy.
    
4. På sidan för nätfiske väljer du **+ skapa**. En guide öppnas med instruktioner för hur du definierar din skydds policy för nätfiske.
    
5. Ange namn, beskrivning och inställningar för principen enligt rekommendationer i diagrammet nedan. Läs mer om att få mer information om alternativ för att läsa mer [om ATP-alternativen](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) . 
    
6. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**på lämpligt sätt.


|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Domän och mest värdefulla kampanj personal  <br/> |
|Beskrivning  <br/> |Se till att du har den viktigaste personalen och att domänen inte personifieras.  <br/> |
|Lägga till användare att skydda  <br/> |Välj **+ Add a Condition, mottagaren är**. Skriv användar namn eller ange e-postadress för kandidat-, kampanj ansvarig och andra viktiga medlemmar i personalen. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.  <br/> |
|Lägga till domäner att skydda  <br/> |Välj **+ Add a Condition, mottagar domänen är**. Ange den anpassade domän som är kopplad till Microsoft 365-prenumerationen om du har definierat en. Du kan ange fler än en domän.  <br/> |
|Välj åtgärder  <br/> |Om e-post skickas av en personifierad användare: Välj **omdirigera meddelande till en annan e-postadress**och ange sedan e-postadressen för säkerhets administratören. till exempel securityadmin@contoso.com.          Om e-post skickas av en domänkontrollant: Välj **karantän meddelande**.  <br/> |
|Post lådans intelligens  <br/> |Som standard väljs post lådans intelligens när du skapar en ny skydds policy. Lämna den här **inställningen för** bästa resultat.  <br/> |
|Lägga till betrodda avsändare och domäner  <br/> |I det här exemplet definierar du inte några åsidosättningar.  <br/> |
|Tillämpas på  <br/> |Välj **mottagar domänen**. Välj **Välj**under **något av dessa**. Välj **+ Lägg till**. Markera kryss rutan bredvid domän namnet, till exempel contoso.com, i listan och välj sedan **Lägg till**. Välj **klar**.  <br/> |
|
   
Mer information finns i [Konfigurera Office 365 ATP-Antivirus principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: skydda mot skadliga bifogade filer och filer med säkra filer för ATP
<a name="atp"> </a>

Personer skickar, tar emot och delar ut bifogade filer regelbundet, till exempel dokument, presentationer, kalkyl blad och annat. Det är inte alltid enkelt att berätta om en bifogad fil är säker eller skadlig genom att titta i ett e-postmeddelande. Office 365 Avancerat skydd för säkert bilagor, men detta skydd är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda detta skydd. Det här tillägget gäller för filer i SharePoint, OneDrive och Microsoft Teams.
  
Om du vill skapa en policy för säker bilaga med ATP kan du titta på en [kort utbildnings video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller göra följande:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörs konto. 
    
2. &amp;Välj **princip**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**
    
3. Markera **säkra bifogade filer för ATP**på sidan policy.
    
4. På sidan betrodda bifogade filer tillämpar du det här skyddet brett genom att markera kryss rutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** . 
    
5. Välj **+** för att skapa en ny princip. 
    
6. Använd inställningarna i följande tabell. 
    
7. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**på lämpligt sätt.
    

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig kod.  <br/> |
|Beskrivning  <br/> |Blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.  <br/> |
|Spara bifogade filer, svar på skadlig program vara  <br/> |Välj **blockera-blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierad skadlig kod**.  <br/> |
|Omdirigera bilaga vid identifiering  <br/> |Aktivera omdirigering (Välj den här rutan) ange administratörs kontot eller en post låda inställning för karantän.          Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar (Välj den här rutan).  <br/> |
|Tillämpas på  <br/> |Mottagar domänen är. . . Välj din domän.  <br/> |
|
   
Mer information finns i [Konfigurera Office 365 ATP-Antivirus principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: skydda mot nätfiske-attacker med säkra ATP-länkar
<a name="phishingatp"> </a>

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365-säkra länkar (ATP), en del av det avancerade hotets skyddet för Office 365, kan skydda din organisation genom att ange inloggnings kontroll för webb adresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras genom principer för säkra Länkar för ATP.
  
Vi rekommenderar att du gör följande:
  
- Ändra standard principen för att öka skyddet.
    
- Lägg till en ny princip riktade till alla mottagare i domänen.
    
För att komma åt säkra anslutningar via ATP kan du titta på en [kort utbildnings video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)eller göra följande:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörs konto. 
    
2. &amp;Välj **princip**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**
    
3. På sidan policy väljer du **säkerhets Länkar för ATP**.
    
Så här ändrar du standard principen:
  
1. Dubbelklicka på **standard** principen på sidan Safe Links under **principer som gäller för hela organisationen**. 
    
2. Ange en URL som ska blockeras, till exempel _example.com_, under **inställningar som gäller för innehåll i Office 365**och välj **+** .

3. Välj **Office 365-program**under **inställningar som gäller för innehåll utom e-post**, **Spåra inte när användare klickar på säkra länkar**och låter **inte användare klicka genom säkra länkar till original-URL: en**.
    
4. Välj **Spara**. 
    
Så här skapar du en ny princip för alla mottagare i domänen:
  
1. På sidan Safe Links, under **principer som gäller för specifika mottagare**, väljer **+** du för att skapa en ny princip. 
    
2. Använd inställningarna i följande tabell.
    
3. Välj **Spara**. 
    
|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Principer för säkra Länkar för alla mottagare i domänen  <br/> |
|Välj åtgärd för okända URL-adresser i meddelanden  <br/> |Välj **URL-adresser skrivs igen och kontrol leras mot en lista över kända illasinnade länkar när användaren klickar på länken**.  <br/> |
|Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer  <br/> |Markera den här rutan.  <br/> |
|Tillämpas på  <br/> |Mottagar domänen är. . . Välj din domän.  <br/> |
|
   
Mer information finns i [Office 365 säkerhets Länkar för ATP](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).
