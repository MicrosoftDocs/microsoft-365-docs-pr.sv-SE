---
title: Öka hotets skydd för Microsoft 365 för företag
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Konfigurera Office 365 Avancerat skydd mot nätfiske, skadlig program vara och andra hot.
ms.openlocfilehash: d56a5371bc5fc4da22f4625024769cc0325a25ca
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948597"
---
# <a name="increase-threat-protection"></a>Öka hotskyddet

Den här artikeln hjälper dig att öka skyddet i Microsoft 365-prenumerationen för att skydda mot nätfiske, skadlig program vara och andra hot. Dessa rekommendationer är lämpliga för organisationer med förbättrat behov av säkerhet, till exempel juridiska kontor och hälso vårds kliniker.

Innan du börjar bör du kontrol lera din Office 365 säkra poäng. Med säkra Poäng för Office 365 analyseras organisationens säkerhet utifrån dina vanliga aktiviteter och säkerhets inställningar och du får en poäng. Börja med att anteckna ditt aktuella Poäng värde. Om du vill öka poängen kan du slutföra åtgärderna som rekommenderas i den här artikeln. Målet är inte att uppnå maximal poäng, men det är medvetet om möjligheter att skydda din miljö som inte påverkar produktiviteten för dina användare negativt.

Mer information finns i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja nivån på skyddet mot skadlig program vara i e-post

Din Office 365 eller Microsoft 365-miljön skyddar mot skadlig program vara. Du kan öka skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig program vara. Öka skyddet mot skadlig program vara i e-post:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med dina inloggnings uppgifter för ditt administratörs konto.

2. I &amp; det vänstra navigerings fönstret i Center för säkerhets kontroll väljer du **princip** mot **Threat management** \> **skadlig program vara**under Threat Management.

3. Dubbelklicka på standard principen för att redigera företagets policy.

4. Välj **Inställningar**.

5. Välj **på**under **vanliga typer av bifogade filer**. De filtyper som blockeras visas i fönstret direkt under den här kontrollen. Se till att du lägger till dessa filtyper:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Vid behov kan du lägga till eller ta bort filtyper senare.

6. Välj **Spara.**

Mer information finns i [skydda mot skadlig program vara i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Skydda mot utpressningstrojaner

Utpressnings tro Jan attack begränsar åtkomsten till data genom att kryptera filer eller låsa dator skärmar. Sedan försöker extort pengar från offer genom att be om "utpressnings gilla", vanligt vis i form av cryptocurrencies som Bitcoin, i Exchange för åtkomst till data.

För att skydda mot utpressnings tro Jan kan du skapa en eller flera regler för e-postflöde för att blockera fil namns tillägg som ofta används för utpressning (Du har lagt till dessa regler i [höja nivån på skyddet mot skadlig program vara i e-](#raise-the-level-of-protection-against-malware-in-mail) poststeget.) Du kan också varna användare som tar emot dessa bilagor via e-post.

Utöver de filer som du har blockerat i föregående steg är det lämpligt att skapa en regel för att varna användarna innan de öppnar filer för Office-filer som innehåller makron. Utpressnings tro Jan kan vara dolda inuti makron, så varna användarna för att inte öppna de här filerna från personer de inte känner.

Så här skapar du en e-posttransport regel:

1. Gå till administrations centret på <https://admin.microsoft.com> och välj Exchange **Center** - \> **utbyte**.

2. Välj **regler**i kategorin **e-postflöde** .

3. Välj **+** och välj sedan **skapa en ny regel**.

4. Välj **fler alternativ** längst ned i dialog rutan för att visa alla alternativ.

5. Använd inställningarna i tabellen nedan för regeln. Använd standardinställningarna för resten av inställningarna om du inte vill ändra dem.

6. Välj **Spara**.

|Inställning|Varna användare innan du öppnar bifogade filer av Office-filer||
|---|---|---|
|Namn|Policy för antipressnings tro Jan: varna användare|
|Använd den här regeln om. . .|Bifogade filer. . . fil namns tillägg matchar. . .|
|Ange ord eller fraser|Lägg till följande filtyper:  <br/> dotm, DOCM, xlsm, sltm, xla, XLAM, XLL, PPTM, POTM, PPAM, PPSM, sldm|
|Gör följande. . .|Meddela mottagaren med ett meddelande|
|Ange meddelande text|Öppna inte dessa typer av filer från personer som du inte känner eftersom de kan innehålla makron med skadlig kod.|

Mer information finns i:

- [Utpressnings tro Jan: minska riskerna](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Återställa OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordring för e-post

Hackare som får till gång till en användares post låda kan stjäla e-post genom att ställa in post lådan så att e-post skickas Detta kan inträffa även om användarens kännedom inte är medvetenhet. För att förhindra att detta händer kan du konfigurera en regel för e-postflöde.

Om du vill skapa en regel för e-posttransport, titta på [den här korta videon](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) eller följ de här stegen:

1. I administrations centret för Microsoft 365 väljer du **Admin Center** \> **Exchange**.

2. Välj **regler**i kategorin **e-postflöde** .

3. Välj **+** och välj sedan **skapa en ny regel**.

4. Om du vill se alla alternativ väljer du **fler alternativ** längst ned i dialog rutan.

5. Använd inställningarna i följande tabell. Använd standardinställningarna för resten av inställningarna om du inte vill ändra dem.

6. Välj **Spara**.

|Inställning|Varna användare innan du öppnar bifogade filer av Office-filer|
|---|---|
|Namn|Förhindra automatisk vidarebefordran av e-post till externa domäner|
|Använd den här regeln om...|Avsändaren. . . är externt/internt. . . Inom organisationen|
|Lägg till villkor|Meddelande egenskaper. . . inkludera meddelande typen. . . Automatisk vidarebefordran|
|Gör följande:|Blockera meddelandet. . . avvisa meddelandet och ta med en förklaring.|
|Ange meddelande text|E-post utanför organisationen förhindras automatiskt av säkerhets skäl.|


## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiske-attacker

Om du har konfigurerat en eller flera egna domäner för Office 365 eller Microsoft 365-miljön kan du konfigurera riktat mot nätfiske-skydd. ATP-skydd mot nätfiske, en del av Office 365 Avancerat skydd mot obehöriga attacker och andra nät fiske attacker. Om du inte har konfigurerat en egen domän behöver du inte göra detta.

Vi rekommenderar att du kommer igång med detta skydd genom att skapa en princip för att skydda de viktigaste användarna och din egen domän.

Om du vill skapa en Antivirus policy för ATP kan du titta på  [den här korta utbildnings videon](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)eller göra följande:

1. Gå till [https://protection.office.com](https://protection.office.com).

2. &amp;Välj **policy**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**

3. Välj **ATP-nätfiske**på sidan **policy** .

4. På sidan för **nätfiske** väljer du **+ skapa**. En guide öppnas med instruktioner för hur du definierar din skydds policy för nätfiske.

5. Ange namn, beskrivning och inställningar för principen enligt rekommendationer i följande tabell. Mer information finns i [Läs mer om alternativ för skydd mot ATP-nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**på lämpligt sätt.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Domän och mest värdefulla kampanj personal|
|Beskrivning|Se till att du har den viktigaste personalen och att domänen inte personifieras.|
|Lägga till användare att skydda|Välj **+ Add a Condition, mottagaren är**. Skriv användar namn eller ange e-postadress för kandidat-, kampanj ansvarig och andra viktiga medlemmar i personalen. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.|
|Lägga till domäner att skydda|Välj **+ Add a Condition, mottagar domänen är**. Ange den anpassade domän som är kopplad till Microsoft 365-prenumerationen om du har definierat en. Du kan ange fler än en domän.|
|Välj åtgärder|Om e-post skickas av en personifierad användare: Välj **omdirigera meddelande till en annan e-postadress**och skriv sedan e-postadressen för säkerhets administratören. till exempel *Alice <span> <span> @contoso. com*. Om e-post skickas av en domänkontrollant: Välj **karantän meddelande**.|
|Post lådans intelligens|Som standard väljs post lådans intelligens när du skapar en ny skydds policy. Lämna den här **inställningen för** bästa resultat.|
|Lägga till betrodda avsändare och domäner|Här kan du lägga till en egen domän eller någon annan betrodd domän.|
|Tillämpas på|Välj **mottagar domänen**. Välj **Välj**under **något av dessa**. Välj **+ Lägg till**. Markera kryss rutan bredvid domän namnet, till exempel *contoso. <span> <span> com*, i listan och välj sedan **Lägg till**. Välj **klar**.|

## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a>Skydda mot skadlig bifogad fil och filer med säkra filer för ATP

Personer skickar, tar emot och delar ut bifogade filer regelbundet, till exempel dokument, presentationer, kalkyl blad och annat. Det är inte alltid enkelt att berätta om en bifogad fil är säker eller skadlig genom att titta i ett e-postmeddelande. Office 365 Avancerat skydd för säkert bilagor, men detta skydd är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda detta skydd. Det här tillägget gäller för filer i SharePoint, OneDrive och Microsoft Teams.

Om du vill skapa en policy för säker bilaga med ATP kan du titta på [den här korta videon](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller göra följande:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörs konto.

2. &amp;Välj **policy**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**

3. På princip sidan väljer du säkerhets anslags **säkra bifogade filer**.

4. På sidan betrodda bifogade filer tillämpar du det här skyddet brett genom att markera kryss rutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .

5. Välj **+** för att skapa en ny princip.

6. Använd inställningarna i följande tabell.

7. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara**på lämpligt sätt.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig kod.|
|Beskrivning|Blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.|
|Spara bifogade filer, svar på skadlig program vara|Välj **blockera-blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierad skadlig kod**.|
|Omdirigera bilaga vid identifiering|Aktivera omdirigering (Välj den här rutan) ange administratörs kontot eller en post låda inställning för karantän.          Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar (Välj den här rutan).|
|Tillämpas på|Mottagar domänen är. . . Välj din domän.|

Mer information finns i [Konfigurera Office 365 ATP-Antivirus principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a>Skydda mot nätfiske-attacker med säkra ATP-länkar

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Office 365-säkra länkar (ATP), en del av det avancerade hotets skyddet för Office 365, kan skydda din organisation genom att ange inloggnings kontroll för webb adresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras genom principer för säkra Länkar för ATP.

Vi rekommenderar att du gör följande:

- Ändra standard principen för att öka skyddet.

- Lägg till en ny princip riktade till alla mottagare i domänen.

Om du vill ställa in säkerhets Länkar för ATP kan du titta på [den här korta utbildnings videon](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)eller göra följande:

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt administratörs konto.

2. &amp;Välj **policy**i det vänstra navigerings fönstret under säkerhets kontroll. **Threat management**

3. På sidan policy väljer du **säkerhets Länkar för ATP**.

Så här ändrar du standard principen:

1. På sidan Safe Links, under **principer som gäller för hela organisationen**, väljer du **standard** policy.

2. Välj **Microsoft 365-appar för företag, Office för iOS och Android**under **inställningar som gäller för innehåll förutom e-post**.

3. Välj **Spara**.

Så här skapar du en ny princip för alla mottagare i domänen:

1. På sidan Safe Links, under **principer som gäller för hela organisationen**, väljer **+** du för att skapa en ny princip.

2. Använd inställningarna i följande tabell.

3. Välj **Spara**.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Principer för säkra Länkar för alla mottagare i domänen|
|Välj åtgärd för okända URL-adresser i meddelanden|Välj **URL-adresser skrivs igen och kontrol leras mot en lista över kända illasinnade länkar när användaren klickar på länken**.|
|Använda säkra bifogade filer för att skanna nedladdnings Bart innehåll|Markera den här rutan.|
|Tillämpas på|Mottagar domänen är. . . Välj din domän.|

Mer information finns i [Office 365 säkerhets Länkar för ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="go-to-intune-admin-center"></a>Gå till administrations centret för Intune

1. Logga in på [Azure-portalen](https://portal.azure.com/).

2. Markera **alla tjänster** och skriv in *Intune* i **sökrutan**.

3. När resultatet visas väljer du påbörja inledningen bredvid **Microsoft Intune** så att den blir favorit och lätt att hitta senare.

Utöver Admin Center kan du använda Intune för att registrera och hantera organisationens enheter. Mer information finns i avsnittet [funktioner för registrerings metod för Windows-enheter](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) och [registrerings alternativ för enheter som hanteras av Intune](https://docs.microsoft.com/intune/enrollment-options).
