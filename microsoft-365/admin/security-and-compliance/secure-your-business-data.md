---
title: Topp 10 sätt att skydda Microsoft 365 för affärsplaner
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
description: 'Skydda företagets e-post och data från cyberhot, inklusive utpressningsartiklar, nätfiske och skadliga bilagor. '
ms.openlocfilehash: cffc922aec3ca46543b5b1608fa37e6fa0acfa23
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138296"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>Topp 10 sätt att skydda Microsoft 365 för affärsplaner

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du är en liten eller medelstor organisation som använder en av Microsofts affärsplaner och din typ av organisation är måltavla för cyberbrottslingar och hackare använder du vägledningen i den här artikeln för att öka säkerheten för din organisation. Den här vägledningen hjälper din organisation att uppnå de mål som beskrivs i Handboken för Harvard Kennedy School [Cybersecurity Campaign](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409).
  
Microsoft rekommenderar att du slutför uppgifterna i följande tabell som gäller för serviceplanen. 
  
||**Uppgift**|**Microsoft 365 Business Standard**|**Microsoft 365 Business Premium**|
|:-----|:-----|:-----|:-----|
|1  <br/> |[Konfigurera multifaktorautentisering](secure-your-business-data.md#setup) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|2  <br/> |[Utbilda dina användare](secure-your-business-data.md#train) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|3  <br/> |[Använda dedikerade administratörskonton](secure-your-business-data.md#admin) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|4  <br/> |[Höj skyddsnivån mot skadlig kod i post](secure-your-business-data.md#malware) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|5  <br/> |[Skydda mot utpressningstrojaner](secure-your-business-data.md#ransomware) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|6  <br/> |[Stoppa automatisk vidarebefordran för e-post](secure-your-business-data.md#forwarding) <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|7  <br/> |[Använda Office-meddelandekryptering](secure-your-business-data.md#encryption) <br/> ||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|8  <br/> |[Skydda din e-post från nätfiskeattacker](secure-your-business-data.md#phishing) <br/> ||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|9  <br/> |[Skydda mot skadliga bilagor och filer med ATP-säkra bilagor](secure-your-business-data.md#atp) <br/> ||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
|10  <br/> |[Skydda mot nätfiskeattacker med ATP Safe Links](secure-your-business-data.md#phishingatp) <br/> ||![Ingår](../../media/d238e041-6854-4a78-9141-049224df0795.png)           <br/> |
   
Innan du börjar kontrollerar du ditt [Microsoft 365 Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) i microsoft 365-säkerhetscentret. Från en centraliserad instrumentpanel kan du övervaka och förbättra säkerheten för dina Microsoft 365-identiteter, data, appar, enheter och infrastruktur. Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter (till exempel visa rapporter) eller hantera rekommendationer med ett program eller en programvara från tredje part. Med ytterligare insikter och mer insyn i en bredare uppsättning Microsoft-produkter och -tjänster kan du känna dig säker på att rapportera om organisationens säkerhetshälsa.
  
![Skärmbild av Microsoft Secure Score](../../media/secure-score.png)
  
## <a name="1-set-up-multi-factor-authentication"></a>1: Ställa in multifaktorautentisering
<a name="setup"> </a>

Att använda multifaktorautentisering är ett av de enklaste och mest effektiva sätten att öka säkerheten för din organisation. Det är enklare än det låter - när du loggar in innebär multifaktorautentisering att du skriver en kod från telefonen för att få tillgång till Microsoft 365. Detta kan hindra hackare från att ta över om de känner till ditt lösenord. Multifaktorautentisering kallas också tvåstegsverifiering. Enskilda personer kan enkelt lägga till tvåstegsverifiering i de flesta konton, till exempel i sina Google- eller Microsoft-konton. Så här lägger du till [tvåstegsverifiering i ditt personliga Microsoft-konto](https://go.microsoft.com/fwlink/?linkid=2016403&amp;clcid=0x409).
  
För företag som använder Microsoft 365 lägger du till en inställning som kräver att användarna loggar in med multifaktorautentisering. När du gör den här ändringen uppmanas användarna att konfigurera sin telefon för tvåfaktorsautentisering nästa gång de loggar in.
Information om hur du visar en utbildningsvideo för hur du konfigurerar MFA och hur användarna slutför konfigurera den finns [i konfigurera MFA](https://support.microsoft.com/office/e12187b8-216a-4490-9e3b-df34a06fb787) och [användarskapare](https://support.microsoft.com/office/a32541df-079c-420d-9395-9d59354f7225).
  
Så här ställer du in multifaktorautentisering:

1. Välj Aktiva användare i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) **Users**  >  **Active Users**.

2. Välj **Multifaktorautentisering**i avsnittet **Aktiva användare** .

3. På sidan **Multifaktorautentisering** väljer du **Användare** om du aktiverar detta för en användare eller så kan du utföra en **massuppdatering**.

4. Välj **Aktivera** under **Snabbsteg**.

5. Välj **Aktivera multifaktorautentisering**i popup-fönstret .


När du har konfigurerat multifaktorautentisering för din organisation måste dina användare konfigurera tvåstegsverifiering på sina enheter. Mer information finns i [Konfigurera tvåstegsverifiering för Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14).
  
Fullständig information och fullständiga rekommendationer finns i [Konfigurera multifaktorautentisering för användare](set-up-multi-factor-authentication.md).
  
## <a name="2-train-your-users"></a>2: Träna dina användare
<a name="train"> </a>

Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ger utmärkt vägledning om hur du skapar en stark kultur av säkerhetsmedvetenhet inom din organisation, inklusive utbildning användare att identifiera phishing-attacker. 
  
Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar de åtgärder som beskrivs i den här artikeln: [Skydda ditt konto och dina enheter från hackare och skadlig kod](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Dessa åtgärder omfattar:
  
- Använda starka lösenord
    
- Skydda enheter
    
- Aktivera säkerhetsfunktioner på Windows 10- och Mac-datorer
    
Microsoft rekommenderar också att användarna skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:
  
- [Skydda ditt Outlook.com e-postkonto](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
    
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
    
## <a name="3-use-dedicated-admin-accounts"></a>3: Använd dedikerade administratörskonton
<a name="admin"> </a>

De administrativa konton som du använder för att administrera din Microsoft 365-miljö innehåller förhöjda privilegier. Dessa är värdefulla mål för hackare och cyberbrottslingar. Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för regelbunden, icke-administrativ användning och endast använda sitt administrativa konto när det behövs för att slutföra en uppgift som är associerad med deras jobbfunktion. Ytterligare rekommendationer:
  
- Se till att administratörskonton också är konfigurerade för multifaktorautentisering. 
    
- Innan du använder administratörskonton stänger du alla orelaterade webbläsarsessioner och appar, inklusive personliga e-postkonton.
    
- När du har slutfört administratörsuppgifter, se till att logga ut från webbläsarsessionen.
    
## <a name="4-raise-the-level-of-protection-against-malware-in-mail"></a>4: Höj skyddsnivån mot skadlig kod i post
<a name="malware"> </a>

Din Microsoft 365-miljö innehåller skydd mot skadlig kod, men du kan öka det här skyddet genom att blockera bilagor med filtyper som ofta används för skadlig kod. Om du vill stöta upp skyddet för skadlig programvara i e-post kan du visa en [kort träningsvideo](https://support.microsoft.com/office/02b5783a-eea0-42e8-8856-62440718c3f0)eller utföra följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med dina administratörskontouppgifter. 
    
2. Välj &amp; **Policy** **Threat management** \> **Anti-Malware**i det vänstra navigeringsfönstret i det vänstra navigeringsfönstret.
    
3. Dubbelklicka på standardprincipen om du vill redigera den här företagsövergripande principen.
    
4. Välj **Inställningar**.
    
5. Under **Filter för vanliga typer av bifogade filer**väljer du **På**. De filtyper som är blockerade visas i fönstret direkt under den här kontrollen. Du kan lägga till eller ta bort filtyper senare om det behövs.
    
6. Välj **Spara.**
    
Mer information finns i [Skydd mot skadlig kod](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).
  
## <a name="5-protect-against-ransomware"></a>5: Skydda mot ransomware
<a name="ransomware"> </a>

Ransomware begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Det försöker sedan att pressa pengar från offer genom att be om "lösen", vanligtvis i form av kryptokurner som Bitcoin, i utbyte mot tillgång till data. 
  
Du kan skydda mot ransomware genom att skapa en eller flera regler för e-postflöde för att blockera filnamnstillägg som ofta används för ransomware, eller för att varna användare som tar emot dessa bilagor via e-post. En bra utgångspunkt är att skapa två regler:
  
- Varna användare innan du öppnar Office-bifogade filer som innehåller makron. Ransomware kan döljas inuti makron, så vi varnar användarna att inte öppna dessa filer från människor som de inte känner. 
    
- Blockera filtyper som kan innehålla ransomware eller annan skadlig kod. Vi börjar med en gemensam lista över körbara filer (listade i tabellen nedan). Om din organisation använder någon av dessa körbara typer och du förväntar dig att dessa ska skickas i e-post lägger du till dessa i föregående regel (varna användare).
    
Om du vill skapa en regel för e-posttransport kan du visa en [kort träningsvideo](https://support.microsoft.com/office/a9ecca03-42a6-4867-b9fd-38e3f6bb06ad)eller utföra följande steg:
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **regler**i kategorin **e-postflöde** .
    
3. Markera **+** och **skapa sedan en ny regel**.
    
4. Välj **** längst ned i dialogrutan om du vill se hela uppsättningen alternativ. 
    
5. Använd inställningarna i följande tabell för varje regel. Lämna resten av inställningarna som standard, om du inte vill ändra dessa.
    
6. Välj **Spara**.
    
|**Inställning**|**Varna användare innan du öppnar bifogade filer i Office-filer**|**Blockera filtyper som kan innehålla ransomware eller annan skadlig kod**|
|:-----|:-----|:-----|
|Namn  <br/> |Anti-ransomware regel: varna användare  <br/> |Anti-ransomware regel: blockera filtyper  <br/> |
|Använd den här regeln om . . .  <br/> |Alla bifogade filer . . . filändelsen matchar . . .  <br/> |Alla bifogade filer . . . filändelsen matchar . . .  <br/> |
|Ange ord eller fraser  <br/> |Lägg till följande filtyper:  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |Lägg till följande filtyper:  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|Gör följande . . .  <br/> |Meddela mottagaren med ett meddelande  <br/> |Blockera meddelandet . . . avvisa meddelandet och inkludera en förklaring  <br/> |
|Ange meddelandetext  <br/> |Öppna inte dessa typer av filer , om du inte förväntade dig dem, eftersom filerna kan innehålla skadlig kod och veta avsändaren är inte en garanti för säkerhet.  <br/> ||
   
> [!TIP]
> Du kan också lägga till de filer du vill blockera i listan Mot skadlig kod i [steg 4](#4-raise-the-level-of-protection-against-malware-in-mail).

Mer information finns i:
  
- [Hur man hanterar ransomware](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [Återställa din OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)
    
## <a name="6-stop-auto-forwarding-for-email"></a>6: Sluta vidarebefordra automatiskt för e-post
<a name="forwarding"> </a>

Hackare som får åtkomst till en användares postlåda kan exfiltrate e-post genom att konfigurera brevlådan för att automatiskt vidarebefordra e-post. Detta kan hända även utan användarens medvetenhet. Du kan förhindra att detta händer genom att konfigurera en regel för e-postflöde. 
  
Så här skapar du en regel för e-posttransport:
  
1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Välj **regler**i kategorin **e-postflöde** .
    
3. Markera **+** och **skapa sedan en ny regel**.
    
4. Välj **Fler alternativ** längst ned i dialogrutan om du vill se hela uppsättningen alternativ. 
    
5. Använd inställningarna i följande tabell. Lämna resten av inställningarna som standard, om du inte vill ändra dessa.
    
6. Välj **Spara**.
    
|**Inställning**|**Avvisa e-postmeddelanden framåt automatiskt till externa domäner**|
|:-----|:-----|
|Namn  <br/> |Förhindra automatisk vidarebefordran av e-post till externa domäner  <br/> |
|Tillämpa den här regeln om ...  <br/> |Avsändaren . . . är extern/intern . . . Inne i organisationen  <br/> |
|Lägg till villkor  <br/> |Mottagaren . . . är extern/intern . . . Utanför organisationen  <br/> |
|Lägg till villkor  <br/> |Meddelandeegenskaperna . . . inkludera meddelandetypen . . . Auto-framåt  <br/> |
|Gör följande ...  <br/> |Blockera meddelandet . . . avvisa meddelandet och inkludera en förklaring.  <br/> |
|Ange meddelandetext  <br/> |E-post som vidarebefordras automatiskt utanför den här organisationen förhindras av säkerhetsskäl.  <br/> |
   
## <a name="7-use-office-message-encryption"></a>7: Använda Office-meddelandekryptering
<a name="encryption"> </a>

Office Message Encryption ingår i Microsoft 365. Den är redan klar. Med Kryptering av Office-meddelanden kan din organisation skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. Office 365 Message Encryption fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. Kryptering av e-postmeddelanden säkerställer att endast avsedda mottagare kan visa meddelandeinnehåll.
  
Kryptering av Office Message-meddelanden ger två skyddsalternativ när du skickar e-post:
  
- Vidarebefordra inte
    
- Kryptera
    
Din organisation kan ha konfigurerat ytterligare alternativ som använder en etikett på e-post, till exempel Konfidentiellt.
  
### <a name="to-send-protected-email"></a>Så här skickar du skyddad e-post

I Outlook för PC väljer du **Alternativ** i e-postmeddelandet och väljer sedan **Behörigheter**. 
  
![Kryptering av e-postmeddelanden i Outlook](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)
  
I Outlook.com väljer du **Skydda** i e-postmeddelandet. Standardskyddet är **Vidarebefordra inte**. Om du vill ändra detta till kryptera väljer du **Ändra behörigheter** \> **Kryptera**. 
  
![Kryptering av e-postmeddelanden i Outlook.com](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)
  
### <a name="to-receive-encrypted-email"></a>Så här får du krypterad e-post

Om mottagaren har Outlook 2013 eller Outlook 2016 och ett Microsoft-e-postkonto visas en avisering om objektets begränsade behörigheter i läsfönstret. När du har öppnat meddelandet kan mottagaren visa meddelandet precis som alla andra.
  
Om mottagaren använder en annan e-postklient eller e-postkonto, till exempel Gmail eller Yahoo, visas en länk där de antingen kan logga in för att läsa e-postmeddelandet eller begära en engångslösenkod för att visa meddelandet i en webbläsare. Om användarna inte får e-postmeddelandet låter du dem kontrollera mappen Skräppost eller Skräppost. 
  
Mer information finns i [Skicka, visa och svara på krypterade meddelanden i Outlook för PC](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980).
  
## <a name="8-protect-your-email-from-phishing-attacks"></a>8. Skydda din e-post från nätfiskeattacker
<a name="phishing"> </a>

Om du har konfigurerat en eller flera anpassade domäner för din Microsoft 365-miljö kan du konfigurera riktat skydd mot nätfiske. ATP:s skydd mot nätfiske, som är en del av det avancerade skydd mot office 365, kan skydda din organisation från skadliga identitetsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en anpassad domän behöver du inte göra detta.
  
Vi rekommenderar att du kommer igång med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän. 
  
![Skapa en ATP-policy för phishing](../../media/security-and-compliance-center.png)
  
Om du vill skapa en ATP-policy mot nätfiske kan du visa en [kort träningsvideo](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)eller utföra följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com). 
    
2. Välj &amp; **Princip**i det vänstra navigeringsfönstret i det vänstra navigeringsfönstret i **det**vänstra navigeringsfönstret .
    
3. På sidan Princip väljer du **ATP-anti-nätfiske**.
    
4. På sidan Anti-phishing väljer du **+ Skapa**. En guide startar som vägleder dig genom att definiera din anti-phishing-policy.
    
5. Ange namn, beskrivning och inställningar för principen enligt rekommendationen i diagrammet nedan. Mer information [finns i Läs mer om atp-policyalternativ för nätfiske.](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies) 
    
6. När du har granskat inställningarna väljer du **Skapa den här principen** eller **Spara**, beroende på vad som är lämpligt.


|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Domän och mest värdefull kampanjpersonal  <br/> |
|Beskrivning  <br/> |Se till att den viktigaste personalen och vår domän inte personifieras.  <br/> |
|Lägga till användare för att skydda  <br/> |Välj **+ Lägg till ett villkor, Mottagaren är**. Skriv användarnamn eller ange kandidatens, kampanjchefens och andra viktiga medarbetares e-postadress. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda mot personifiering.  <br/> |
|Lägga till domäner som ska skyddas  <br/> |Välj **+ Lägg till ett villkor, Mottagarens domän är**. Ange den anpassade domän som är kopplad till din Microsoft 365-prenumeration, om du har definierat en sådan. Du kan ange mer än en domän.  <br/> |
|Välj åtgärder  <br/> |Om e-post skickas av en personifierad användare: välj **Omdirigera meddelande till en annan e-postadress**och skriv sedan säkerhetsadministratörens e-postadress. till exempel securityadmin@contoso.com.          Om e-post skickas av en personifierad domän väljer du **Karantänmeddelande**.  <br/> |
|Information om brevlåda  <br/> |Som standard väljs postlådeinformation när du skapar en ny anti-phishing-policy. Lämna den här inställningen **På** för bästa resultat.  <br/> |
|Lägga till betrodda avsändare och domäner  <br/> |I det här exemplet definierar du inte några åsidosättningar.  <br/> |
|Tillämpas på  <br/> |Välj **Mottagardomänen är**. Under **Något av dessa**väljer du **Välj**. Välj **+ Lägg till**. Markera kryssrutan bredvid namnet på domänen, till exempel contoso.com i listan och välj sedan **Lägg till**. Välj **Klar**.  <br/> |
|
   
Mer information finns i [Konfigurera Office 365 ATP:s principer mot nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).
  
## <a name="9-protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>9: Skydda mot skadliga bilagor och filer med ATP Säkra bilagor
<a name="atp"> </a>

Personer skickar, ta emot och delar regelbundet bifogade filer, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Office 365 Advanced Threat Protection innehåller ATP-skydd för säkra bilagor, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Det här skyddet omfattar filer i SharePoint, OneDrive och Microsoft Teams.
  
Om du vill skapa en ATP-princip för säker bifogad fil kan du visa en [kort träningsvideo](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller utföra följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto. 
    
2. Välj &amp; **Princip**i det vänstra navigeringsfönstret i det vänstra navigeringsfönstret i **det**vänstra navigeringsfönstret .
    
3. På sidan Princip väljer du **BETRODDa ATP-bilagor**.
    
4. På sidan Säkra bifogade filer använder du det här skyddet brett genom att markera kryssrutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.** 
    
5. Välj **+** det här om du vill skapa en ny princip. 
    
6. Använd inställningarna i följande tabell. 
    
7. När du har granskat inställningarna väljer du **Skapa den här principen** eller **Spara**, beroende på vad som är lämpligt.
    

|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Blockera nuvarande och framtida e-postmeddelanden med upptäckt skadlig kod.  <br/> |
|Beskrivning  <br/> |Blockera aktuella och framtida e-postmeddelanden och bilagor med upptäckt skadlig kod.  <br/> |
|Spara okända skadliga filer för okänd skadlig kod  <br/> |Välj **Blockera - Blockera aktuella och framtida e-postmeddelanden och bilagor med upptäckt skadlig kod**.  <br/> |
|Omdirigera bifogad fil vid identifiering  <br/> |Aktivera omdirigering (välj den här rutan) Ange administratörskontot eller en postlådeinställning för karantän.          Använd markeringen ovan om skadlig kod söker efter bilagor time out eller fel inträffar (välj den här rutan).  <br/> |
|Tillämpas på  <br/> |Mottagardomänen är . . . välj domän.  <br/> |
|
   
Mer information finns i [Konfigurera Office 365 ATP:s principer mot nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-atp-anti-phishing-policies).
  
## <a name="10-protect-against-phishing-attacks-with-atp-safe-links"></a>10: Skydda mot nätfiskeattacker med ATP Safe Links
<a name="phishingatp"> </a>

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365 ATP Safe Links (ATP Safe Links), en del av Office 365 Advanced Threat Protection, kan skydda din organisation genom att tillhandahålla snabbverifiering av webbadresser i e-postmeddelanden och Office-dokument. Skydd definieras via ATP Safe Links-principer.
  
Vi rekommenderar att du gör följande:
  
- Ändra standardprincipen för att öka skyddet.
    
- Lägg till en ny princip som riktar sig till alla mottagare på domänen.
    
Om du vill komma åt ATP Safe Links kan du visa en [kort träningsvideo](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)eller utföra följande steg:
  
1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörskonto. 
    
2. Välj &amp; **Princip**i det vänstra navigeringsfönstret i det vänstra navigeringsfönstret i **det**vänstra navigeringsfönstret .
    
3. På sidan Princip väljer du **BETRODDA ATP-länkar**.
    
Så här ändrar du standardprincipen:
  
1. Dubbelklicka på **standardprincipen** under Principer som gäller för hela organisationen under **Principer som gäller för hela organisationen.** 
    
2. Under **Inställningar som gäller för innehåll i Office 365**anger du en URL som ska blockeras, till exempel _example.com_och väljer **+** .

3. Under **Inställningar som gäller för innehåll utom e-post**väljer du Office **365-program**, **Spåra inte när användare klickar på säkra länkar**och Låt inte användare klicka på säkra länkar till den ursprungliga **webbadressen**.
    
4. Välj **Spara**. 
    
Så här skapar du en ny princip som riktar sig till alla mottagare på domänen:
  
1. På sidan Säkra länkar under **Principer som gäller för specifika mottagare**väljer du att skapa en ny **+** princip. 
    
2. Använd inställningarna i följande tabell.
    
3. Välj **Spara**. 
    
|**Inställning eller alternativ**|**Rekommenderad inställning** <br/>|
|:-----|:-----|
|Namn  <br/> |Princip för säkra länkar för alla mottagare i domänen  <br/> |
|Välj åtgärden för okända potentiellt skadliga url:er i meddelanden  <br/> |Välj **På - webbadresser skrivs om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken**.  <br/> |
|Använda URL-skanning i realtid efter misstänkta länkar och länkar som pekar på filer  <br/> |Markera den här rutan.  <br/> |
|Tillämpas på  <br/> |Mottagardomänen är . . . välj domän.  <br/> |
|
   
Mer information finns i [säkra länkar till Office 365 ATP](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).
