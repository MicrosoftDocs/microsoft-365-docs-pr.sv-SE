---
title: Öka hotskyddet
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: Få hjälp med att öka skydds nivån i Microsoft 365
ms.openlocfilehash: 99b9bfac7867d6f6b29571940f717667fd05a697
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843262"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Öka skydds prenumerationen för Microsoft 365

Den här artikeln hjälper dig att öka skyddet i Microsoft 365-prenumerationen för att skydda mot nätfiske, skadlig program vara och andra hot. Dessa rekommendationer är lämpliga för organisationer med förbättrat behov av säkerhet, som politiska kampanjer, juridik kontor och sjukvårds tjänst.

Innan du börjar bör du kontrol lera dina säkra poäng i Microsoft. Med Microsofts säkra Poäng analyseras organisationens säkerhet utifrån dina vanliga aktiviteter och säkerhets inställningar och du får en poäng. Börja med att anteckna ditt aktuella Poäng värde. Om du vidtar åtgärderna i den här artikeln ökar poängen. Målet är inte att uppnå det högsta antalet poäng, men att vara medveten om möjligheter att skydda din miljö som inte påverkar produktiviteten för användarna negativt.

Mer information finns i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja nivån på skyddet mot skadlig program vara i e-post

Din Office 365-eller Microsoft 365-miljö inkluderar skydd mot skadlig program vara, men du kan öka detta genom att blockera bifogade filer med filtyper som ofta används för skadlig program vara. Så här stöter du på skadlig program vara i e-post:

1. Gå till <https://protection.office.com> och logga in med dina inloggnings uppgifter för ditt administratörs konto.

2. Välj **policy** **Threat management** \> **anti-malware** under Threat Management i navigerings fönstret för säkerhets &.

3. Dubbelklicka på standard principen för att redigera företagets policy.

4. Klicka på **Inställningar**.

5. Välj **på** under **vanliga typer av bifogade filer**. De filtyper som blockeras visas i fönstret direkt under den här kontrollen. Se till att du lägger till de här filtypna:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Du kan lägga till och ta bort filtyper senare om det behövs.

6. Klicka på **Spara.**

Mer information finns i [skydda mot skadlig program vara i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).

## <a name="protect-against-ransomware"></a>Skydda mot utpressningstrojaner

Utpressnings tro Jan attack begränsar åtkomsten till data genom att kryptera filer eller låsa dator skärmar. Sedan försöker extort pengar från offer genom att be om "utpressnings gilla", vanligt vis i form av cryptocurrencies som Bitcoin, i Exchange för åtkomst till data.

Du kan skydda mot utpressnings tro Jan program vara genom att skapa en eller flera regler för e-postflöden för att blockera fil namns tillägg som ofta används för utpressnings tro Jan (dessa har lagts till i [höja nivån på skyddet mot skadlig kod i e](#raise-the-level-of-protection-against-malware-in-mail) -poststeg) eller för att varna användare som får bifogade filer

Utöver de filer som du har blockerat i föregående steg är det också bra att skapa en regel för att varna användarna innan de öppnar filer som innehåller makron i Office. Utpressnings tro Jan kan vara dolda inuti makron, så det är bara att varna användarna från personer de inte känner till.

Så här skapar du en e-posttransport regel:

1. Gå till administrations centret på <https://admin.microsoft.com> och välj Exchange **Center** - \> **utbyte**.

2. Klicka på **regler** i kategorin **e-postflöde** .

3. Klicka på **+** och sedan på **skapa en ny regel**.

4. Klicka på **fler alternativ** längst ned i dialog rutan för att visa alla alternativ.

5. Använd inställningarna i tabellen nedan för regeln. Lämna övriga inställningar som standard, såvida du inte vill ändra dem.

6. Klicka på **Spara**.

|Inställning|Varna användare innan du öppnar bifogade filer av Office-filer|
|---|---|
|Namn|Policy för antipressnings tro Jan: varna användare|
|Använd den här regeln om. . .|Bifogade filer. . . fil namns tillägg matchar. . .|
|Ange ord eller fraser|Lägg till följande filtyper: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Gör följande. . .|Meddela mottagaren med ett meddelande|
|Ange meddelande text|Öppna inte dessa typer av filer från personer som du inte känner eftersom de kan innehålla makron med skadlig kod.|

Mer information finns i:

- [Utpressnings tro Jan: minska riskerna](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Återställa OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordring för e-post

Hackare som får åtkomst till en användares post låda kan stjäla din e-post genom att ange brev lådan för automatisk vidarebefordran av e-post. Detta kan inträffa även om användarens kännedom inte är medvetenhet. Du kan förhindra detta genom att konfigurera en regel för e-postflöde.

Om du vill skapa en regel för e-posttransport, titta på [den här korta videon](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) eller följ de här stegen:

1. I administrations centret för Microsoft 365 klickar du på Exchange **Center** -tjänsten \> **Exchange**.

2. Klicka på **regler** i kategorin **e-postflöde** .

3. Klicka på **+** och sedan på **skapa en ny regel**.

4. Klicka på **fler alternativ** längst ned i dialog rutan för att visa alla alternativ.

5. Använd inställningarna i följande tabell. Lämna övriga inställningar som standard, såvida du inte vill ändra dem.

6. Klicka på **Spara**.

|Inställning|Varna användare innan du öppnar bifogade filer av Office-filer|
|---|---|
|Namn|Förhindra automatisk vidarebefordran av e-post till externa domäner|
|Använd den här regeln om...|Avsändaren. . . är externt/internt. . . Inom organisationen|
|Lägg till villkor|Meddelande egenskaper. . . inkludera meddelande typen. . . Automatisk vidarebefordran|
|Gör följande:|Blockera meddelandet. . . avvisa meddelandet och ta med en förklaring.|
|Ange meddelande text|E-post utanför organisationen förhindras automatiskt av säkerhets skäl.|

## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiske-attacker

Om du har konfigurerat en eller flera egna domäner för Office 365 eller Microsoft 365-miljön kan du konfigurera riktat mot nätfiske-skydd. Skydd mot nätfiske, en del av Microsoft Defender för Office 365, hjälper till att skydda din organisation från illasinnade nätfiske-attacker och andra nät fiske attacker. Om du inte har konfigurerat en egen domän behöver du inte göra detta.

Vi rekommenderar att du kommer igång med detta skydd genom att skapa en princip för att skydda de viktigaste användarna och din egen domän.

Om du vill skapa en AntiPhishing-princip i Defender för Office 365, titta på [den här korta utbildnings videon](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)eller gör så här:

1. Gå till <https://protection.office.com>.

2. Välj **policy** i det vänstra navigerings fönstret under säkerhets & efterlevnad under **Threat Management**.

3. Välj **anti-nätfiske** på sidan **policy** .

4. På sidan för **nätfiske** väljer du **+ skapa**. En guide öppnas med instruktioner för hur du definierar din skydds policy för nätfiske.

5. Ange namn, beskrivning och inställningar för principen enligt rekommendationer i diagrammet nedan. Mer information finns i [Läs mer om Antinätfiske-principer i alternativ för Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

6. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara** på lämpligt sätt.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Domän och mest värdefulla kampanj personal|
|Beskrivning|Se till att du har den viktigaste personalen och att domänen inte personifieras.|
|Lägga till användare att skydda|Välj **+ Add a Condition, mottagaren är**. Skriv användar namn eller ange e-postadress för kandidat-, kampanj ansvarig och andra viktiga medlemmar i personalen. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.|
|Lägga till domäner att skydda|Välj **+ Add a Condition, mottagar domänen är**. Ange den anpassade domän som är kopplad till Microsoft 365-prenumerationen om du har definierat en. Du kan ange fler än en domän.|
|Välj åtgärder|Om e-post skickas av en personifierad användare: Välj **omdirigera meddelande till en annan e-postadress** och skriv sedan e-postadressen för säkerhets administratören. till exempel *Alice <span> <span> @contoso. com*. <br/> Om e-post skickas av en domänkontrollant: Välj **karantän meddelande**.|
|Post lådans intelligens|Som standard väljs post lådans intelligens när du skapar en ny skydds policy. Lämna den här **inställningen för** bästa resultat.|
|Lägga till betrodda avsändare och domäner|Här kan du lägga till en egen domän eller någon annan betrodd domän.|
|Tillämpas på|Välj **mottagar domänen**. Välj **Välj** under **något av dessa**. Välj **+ Lägg till**. Markera kryss rutan bredvid domän namnet, till exempel *contoso. <span> <span> com* , i listan och välj sedan **Lägg till**. Välj **Klar**.|

Mer information finns i [Konfigurera anti-nätfiske-principer i Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Skydda mot skadliga bifogade filer, filer och länkar med Defender för Office 365

![Banderoll som pekar på https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Kontrol lera först att du i administrations centret <https://admin.microsoft.com> har aktiverat för hands versionen av administrations centret. Aktivera växlings knappen bredvid det **nya administrations centret**.

   ![Den nya för hands versionen av administrations centret.](../media/previewon.png)

Om du inte ser **inställnings** sidan med kort i klient organisationen ännu kan du läsa om hur du utför de här stegen i säkerhets & Compliance Center. Se [Konfigurera säkra bifogade filer i säkerhets & regelefterlevnad](#set-up-safe-attachments-in-the-security--compliance-center) och [skapa säkra länkar i säkerhets & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).

1. I det vänstra navigerings fältet väljer du **Inställningar**.
2. På sidan **Inställningar** väljer du **Visa** på kortet **öka skydd mot avancerade hot** .

   ![Välj Visa på ökat skydd mot avancerade hot.](../media/startatp.png)

3. På sidan **öka skyddet mot avancerade hot** väljer du **Kom igång**.
4. I fönstret som öppnas markerar du kryss rutorna bredvid **länkar och bifogade filer i e-post** , **skannar filer i SharePoint, OneDrive och Teams** och **söknings länkar i Office-skrivbordet och Office Online-program** under **Sök efter objekt efter skadligt innehåll**.

   Under **länkar och bifogade filer i e-post** skriver du in alla användare eller de specifika användare vars e-post du vill skanna.

   ![Markera alla kryss rutor för att öka skyddet mot avancerade hot.](../media/setatp.png)

5. Välj **skapa principer** för att aktivera säkra bifogade filer och säkra länkar.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Konfigurera säkra bifogade filer i säkerhets & efterlevnad

Personer skickar, tar emot och delar ut bifogade filer regelbundet, till exempel dokument, presentationer, kalkyl blad och annat. Det är inte alltid enkelt att berätta om en bifogad fil är säker eller skadlig genom att titta i ett e-postmeddelande. Microsoft Defender för Office 365 innehåller skyddad bilagor, men detta skydd är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda detta skydd. Det här tillägget gäller för filer i SharePoint, OneDrive och Microsoft Teams.

Om du vill skapa en policy för säker bifogad fil kan du titta på [den här korta videon](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)eller göra följande:

1. Gå till <https://protection.office.com> och logga in med ditt administratörs konto.

2. Välj **policy** i det vänstra navigerings fönstret under säkerhets & efterlevnad under **Threat Management**.

3. Välj **Safe Attachments** på sidan policy.

4. På sidan betrodda bifogade filer tillämpar du det här skyddet brett genom att markera kryss rutan **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** .

5. Välj **+** för att skapa en ny princip.

6. Använd inställningarna i följande tabell.

7. När du har granskat dina inställningar väljer du **skapa den här principen** eller **Spara** på lämpligt sätt.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig kod.|
|Beskrivning|Blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.|
|Spara bifogade filer, svar på skadlig program vara|Välj **blockera-blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierad skadlig kod**.|
|Omdirigera bilaga vid identifiering|Aktivera omdirigering (Välj den här rutan) <br/> Ange administratörs kontot eller en installations program vara för karantän. <br/> Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar (Välj den här rutan).|
|Tillämpas på|Mottagar domänen är. . . Välj din domän.|

Mer information finns i [Konfigurera anti-nätfiske-principer i Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Skapa säkra länkar i säkerhets & efterlevnad

Hackare döljer ibland skadliga webbplatser i länkar i e-post eller andra filer. Säkra länkar, en del av Microsoft Defender för Office 365, kan skydda din organisation genom att ange inloggnings kontroll för webb adresser (URL: er) i e-postmeddelanden och Office-dokument. Skydd definieras genom principer för säkra länkar.

Vi rekommenderar att du gör följande:

- Ändra standard principen för att öka skyddet.

- Lägg till en ny princip riktade till alla mottagare i domänen.

Om du vill skapa säkra länkar kan du titta på [den här korta utbildnings videon](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)eller göra följande:

1. Gå till <https://protection.office.com> och logga in med ditt administratörs konto.

2. Välj **policy** i det vänstra navigerings fönstret under säkerhets & efterlevnad under **Threat Management**.

3. Välj **Safe Links** på princip sidan.

Så här ändrar du standard principen:

1. På sidan Safe Links, under **principer som gäller för hela organisationen** , väljer du **standard** policy.

2. Välj **Microsoft 365-appar för företag, Office för iOS och Android** under **inställningar som gäller för innehåll förutom e-post**.

3. Klicka på **Spara**.

Så här skapar du en ny princip för alla mottagare i domänen:

1. På sidan Safe Links, under **principer som gäller för hela organisationen** , klickar **+** du på för att skapa en ny princip.

2. Använd inställningarna i följande tabell.

3. Klicka på **Spara**.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Principer för säkra Länkar för alla mottagare i domänen|
|Välj åtgärd för okända URL-adresser i meddelanden|Välj **URL-adresser skrivs igen och kontrol leras mot en lista över kända illasinnade länkar när användaren klickar på länken**.|
|Använda säkra bifogade filer för att skanna nedladdnings Bart innehåll|Markera den här rutan.|
|Tillämpas på|Mottagar domänen är. . . Välj din domän.|

Mer information finns i [fel säkert länkar i Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).

## <a name="turn-on-the-unified-audit-log"></a>Aktivera den enhetliga gransknings loggen

När du har aktiverat gransknings loggs ökningen i säkerhets & Compliance Center kan du behålla administratörs-och annan användar aktivitet i loggen och söka i den.

Du måste ha rollen gransknings loggar i Exchange Online för att aktivera eller inaktivera gransknings loggs ökningen i Microsoft 365-prenumerationen. Den här rollen är som standard kopplad till roll grupperna efterlevnad Management och organisations hantering på sidan behörigheter i administrations centret för Exchange. Globala administratörer i Microsoft 365 är medlemmar i den här gruppen som standard.

1. Aktivera gransknings loggs ökningen genom att gå till administrations centret på <https://admin.microsoft.com> och välja **efterföljande** under **Administratörs Center** i det vänstra navigerings fältet.
2. Välj **fler resurser** på sidan **Microsoft 365-efterlevnad** och **Öppna** sedan kortet **Office 365 Security & Center** .

    ![Välj Öppna på fliken säkerhet & bilar.](../media/gotosecandcomp.png)
3. På sidan säkerhet och efterlevnad väljer du **Sök** och sedan **Granska loggnings sökning**.
4. Välj **aktivera granskning** längst upp på sidan för **gransknings loggs ökning** .

När funktionen är aktive rad kan du söka efter filer, mappar och många aktiviteter. Mer information finns i [söka i gransknings loggen](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a>Finjustera inställningar för anonym delning för SharePoint-och OneDrive-filer och-mappar

(ändra den anonyma standard länken till 14 dagar, ändra standard typ för delning till "specifika personer") Så här ändrar du delnings inställningar för OneDrive och SharePoint:

1. Gå till administrations centret på <https://admin.microsoft.com> och välj sedan **SharePoint** under **administrations Center** i det vänstra navigerings fältet.
2. Gå till **princip** delning i administrations centret för SharePoint \> **Sharing**.
3. På sidan **delning** under fil- **och mappaktiviteter** väljer du **specifika personer** , och under **Avancerade inställningar för "alla"-länkar** kan du välja **att dessa länkar ska upphöra att gälla inom det här antalet dagar** och skriva i 14 (eller ett annat antal dagar som du vill begränsa länk livs längden till).

   ![Välj specifika personer och ange förfallo tid till 14 dagar.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Aktivitets aviseringar

Du kan använda aktivitets aviseringar för att spåra administratörs-och användar aktiviteter och för att upptäcka problem med skadlig program vara och data förlust vid din organisation. Ditt-abonnemang innehåller en uppsättning standard principer, men du kan också skapa egna. Mer information finns i [aviserings principer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies). Om du till exempel lagrar en viktig fil i SharePoint som du inte vill att någon ska dela externt kan du skapa ett meddelande som meddelar dig om någon gör det.

I följande bild visas de standard principer som ingår i Microsoft 365.

![Standard policy för aviseringar ingår i Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Inaktivera eller hantera kalender delning

Du kan förhindra att personer i organisationen delar sina kalendrar, eller också kan du även hantera vad de kan dela. Du kan till exempel begränsa delningen till endast ledig/upptagen tid.

1. Gå till administrations centret på <https://admin.microsoft.com> och välj **Inställningar** \> **tjänst & tillägg**.
2. På sidan **tjänster & tillägg** väljer du **kalender** och väljer om personer i din organisation kan dela sina kalendrar med personer utanför Office 365 eller Exchange eller med vem som helst.

   Om du väljer dela med någon kan du välja att bara dela med dig av ledig/upptagen-information.

3. Välj **Spara ändringar** längst ned på sidan.

   Följande bild visar att kalender delning inte är tillåtet.

   ![Skärm bild som visar extern kalender delning som inte tillåten.](../media/nocalendarsharing.png)

   I följande bild visas inställningarna när kalender delning tillåts med en e-postlänk med endast ledig/upptagen-information.

   ![Skärm bild av ledig/upptagen-delning med vem som helst.](../media/sharefreebusy.png)

Om användarna kan dela sina kalendrar kan du läsa [anvisningarna](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) för att dela från Outlook på webben.
