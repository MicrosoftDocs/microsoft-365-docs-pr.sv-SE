---
title: Öka hotskyddet
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
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
description: Få hjälp med att öka skyddsnivån i Microsoft 365
ms.openlocfilehash: a1f4714d5b7dcd8d6a22a07c118055e13b27e069
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398283"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a>Öka skydd mot hot för Microsoft 365 prenumeration

Den här artikeln hjälper dig att öka skyddet för Microsoft 365-prenumerationen för att skydda mot nätfiske, skadlig programvara och andra hot. De här rekommendationerna är lämpliga för organisationer med ett ökat behov av säkerhet, t.ex. politiska kampanjer, juristkontor och hälsovårdskontoret.

Innan du börjar kontrollerar du Microsoft Secure Score. Microsoft Secure Score analyserar organisationens säkerhet utifrån aktiviteter och säkerhetsinställningar samt tilldelar ett poängresultat. Börja med att anteckna det aktuella resultatet. Om du vidtar de åtgärder som rekommenderas i den här artikeln ökar poängen. Målet är inte att uppnå maxresultatet, utan att vara medveten om möjligheter att skydda din miljö som inte negativt påverkar användarnas produktivitet.

Mer information finns i [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a>Höja skyddsnivån för skadlig programvara i e-post

Din Office 365- eller Microsoft 365-miljö innehåller skydd mot skadlig programvara, men du kan öka skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig programvara. Så här stöter du på skydd mot skadlig programvara i e-post:

1. Gå till <https://protection.office.com> och logga in med autentiseringsuppgifterna för ditt administratörskonto.

2. Välj Policy Anti-Malware & i det vänstra navigeringsfönstret, under **Hothantering,** i säkerhets- och **efterlevnadscentret.** \> 

3. Dubbelklicka på standardprincipen om du vill redigera den här företagsövergripande principen.

4. Klicka på **Inställningar**.

5. Under **Vanliga typer av bifogade filer väljer** du **På**. De filtyper som är blockerade visas i fönstret direkt nedanför den här kontrollen. Se till att du lägger till de här filtyperna:

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   Du kan lägga till eller ta bort filtyper senare om det behövs.

6. Klicka **på Spara.**

Mer information finns i Skydd [mot skadlig programvara i EOP.](../security/office-365-security/anti-malware-protection.md)

## <a name="protect-against-ransomware"></a>Skydda mot utpressningstrojaner

Utpressningstrojaner begränsar åtkomsten till data genom att kryptera filer eller låsa datorskärmar. Sedan försöker den utträlja pengar från en leverantör genom att begära "utpressningstrojan", vanligtvis i form av cryptocurrencies som Bitcoin, i utbyte mot åtkomst till data.

Du kan skydda dig mot utpressningstrojaner genom att skapa en eller flera e-postflödesregler för att blockera filnamnstillägg som ofta används för utpressningstrojaner (dessa har lagts till för att höja skyddsnivån mot skadlig programvara i e-poststeg) eller för att varna användare som får dessa bifogade filer i e-post. [](#raise-the-level-of-protection-against-malware-in-mail)

Utöver de filer som du blockerade i föregående steg är det också bra att skapa en regel som varnar användare innan de Office bifogade filer som innehåller makron. Utpressningstrojaner kan vara dolda i makron, så varna användare att inte öppna dessa filer från personer de inte känner.

Så här skapar du en regel för e-posttransport:

1. Gå till administrationscentret och <https://admin.microsoft.com> välj **Administrationscenter** \> **Exchange**.

2. Klicka på **regler i** kategorin **E-postflöde.**

3. Klicka **+** på och sedan på Skapa en ny **regel.**

4. Klicka **på Fler** alternativ längst ned i dialogrutan om du vill se alla alternativ.

5. Tillämpa inställningarna i följande tabell för regeln. Låt resten av inställningarna vara som standard, såvida du inte vill ändra dem.

6. Klicka på **Spara**.

|Inställning|Varna användare innan de öppnar bifogade filer Office filer|
|---|---|
|Namn|Regel för utpressningstrojaner: varna användare|
|Tillämpa den här regeln om . . .|En bifogad fil . . . filtillägg matchar . . .|
|Ange ord eller fraser|Lägg till följande filtyper: <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|Gör följande. . .|Meddela mottagaren med ett meddelande|
|Ange meddelandetext|Öppna inte den här typen av filer från personer som du inte känner eftersom de kan innehålla makron med skadlig kod.|

Mer information finns i:

- [Utpressningstrojaner: minska riskerna](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [Återställa OneDrive](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a>Stoppa automatisk vidarebefordran av e-post

Hackare som får åtkomst till en användares postlåda kan stjäla din e-post genom att ställa in så att postlådan automatiskt vidarebefordrar e-post. Det här kan inträffa även utan användarens uppmärksamhet. Du kan förhindra detta genom att konfigurera en e-postflödesregel.

Om du vill skapa en e-posttransportregel kan du antingen [titta på den här](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) korta videon eller följa de här stegen:

1. I administrationscentret Microsoft 365 du på **Administrationscenter för** \> **Exchange**.

2. Klicka på **regler i** kategorin **E-postflöde.**

3. Klicka **+** på och sedan på Skapa en ny **regel.**

4. Klicka **på Fler** alternativ längst ned i dialogrutan om du vill se alla alternativ.

5. Använd inställningarna i följande tabell. Låt resten av inställningarna vara som standard, såvida du inte vill ändra dem.

6. Klicka på **Spara**.

|Inställning|Varna användare innan de öppnar bifogade filer Office filer|
|---|---|
|Namn|Förhindra automatisk vidarebefordran av e-post till externa domäner|
|Tillämpa den här regeln om ...|Avsändaren . . . är extern/intern . . . Inom organisationen|
|Lägg till villkor|Meddelandeegenskaperna . . . ange meddelandetypen . . . Vidarebefordra automatiskt|
|Gör följande ...|Blockera meddelandet . . . avvisa meddelandet och ge en förklaring.|
|Ange meddelandetext|Automatisk vidarebefordran av e-post utanför organisationen förhindras av säkerhetsskäl.|

## <a name="protect-your-email-from-phishing-attacks"></a>Skydda din e-post från nätfiskeattacker

Om du har konfigurerat en eller flera egna domäner i din Office 365- Microsoft 365-miljö kan du konfigurera riktade skydd mot nätfiske. Skydd mot nätfiske, en del av Microsoft Defender för Office 365, kan skydda organisationen från skadliga personifieringsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en egen domän behöver du inte göra det.

Vi rekommenderar att du kommer igång med det här skyddet genom att skapa en princip för att skydda dina viktigaste användare och din anpassade domän.

Om du vill skapa en policy mot nätfiske i Defender för Office 365 tittar du [på den](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)här korta utbildningsvideon eller följer anvisningarna nedan:

1. Gå till <https://protection.office.com>.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i **det vänstra navigeringsfönstret** väljer du **Princip.**

3. Välj **Nätfiskeskydd** **på sidan Princip.**

4. På sidan **mot nätfiske** väljer du **+ Skapa.** En guide startar stegen för att definiera din policy mot nätfiske.

5. Ange namn, beskrivning och inställningar för principen enligt rekommenderade inställningar i diagrammet nedan. Mer information finns i Läs [mer om nätfiskeprincip i Microsoft Defender för Office 365 nätfiskealternativ.](../security/office-365-security/set-up-anti-phishing-policies.md)

6. När du har granskat inställningarna väljer du Skapa **den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Domän och mest värdefull personal|
|Beskrivning|Se till att den viktigaste personalen och vår domän inte utger sig för att vara.|
|Lägga till användare att skydda|Välj **+ Lägg till ett villkor, mottagaren är**. Skriv användarnamn eller ange e-postadressen till företagsägare, partner eller kandidat, chefer och andra viktiga personalmedlemmar. Du kan lägga till upp till 20 interna och externa adresser som du vill skydda från personifiering.|
|Lägga till domäner att skydda|Välj **+ Lägg till ett villkor, mottagarens domän är**. Ange den anpassade domän som är kopplad till Microsoft 365-prenumerationen, om du har definierat en sådan. Du kan ange mer än en domän.|
|Välja åtgärder|Om e-post skickas av en imiterad användare: Välj Omdirigera meddelande till en annan e-postadress och skriv sedan säkerhetsadministratörens e-postadress. Till exempel Så här ser det ut, Det kan vara *<span> <span> @ contoso.com.* <br/> Om e-post skickas av en imiterad domän: Välj **Sätt meddelande i karantän**.|
|Postlådeintelligens|Postlådeintelligens är valt som standard när du skapar en ny princip mot nätfiske. Lämna den här inställningen **På** för bästa resultat.|
|Lägga till betrodda avsändare och domäner|Här kan du lägga till din egen domän eller andra betrodda domäner.|
|Tillämpas på|Välj **Mottagarens domän är**. Under **Valfri av dessa** väljer du **Välj**. Välj **+ Lägg till.** Markera kryssrutan bredvid namnet på domänen, till exempel *contoso. <span> <span> com*, i listan och välj sedan Lägg **till**. Välj **Klar**.|

Mer information finns i [Konfigurera principer för skydd mot nätfiske i Defender för Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a>Skydda mot skadliga bilagor, filer och länkar med Defender för Office 365

![Banderoll som pekar på https://aka.ms/aboutM365preview .](../media/m365admincenterchanging.png)

Kontrollera först att förhandsgranskningen av det nya administrationscentret är aktiverad i <https://admin.microsoft.com> administrationscentret. Aktivera växlingsknappen bredvid texten **I det nya administrationscentret**.

   ![Den nya förhandsversionen av administrationscentret är på.](../media/previewon.png)

Om du inte ser  sidan Konfigurera med kort i din klientorganisation ännu, se hur du slutför de här stegen i Säkerhets- & efterlevnadscenter. Se Konfigurera Valv och bilagor i Säkerhets- och [& säkerhets- och](#set-up-safe-attachments-in-the-security--compliance-center) efterlevnadscenter och Konfigurera Valv i Säkerhets- & [Efterlevnadscenter.](#set-up-safe-links-in-the-security--compliance-center)

1. Välj Konfigurera i **navigeringsfältet till vänster.**
2. På sidan **Konfigurera** väljer du **Visa** på **kortet Öka skyddet mot avancerade** hot.

   ![Välj Visa på fliken Öka skyddet mot avancerade hot.](../media/startatp.png)

3. På sidan **Öka skyddet mot avancerade hot** väljer du Komma **igång.**
4. I fönstret som öppnas markerar du kryssrutorna bredvid Länkar och bifogade filer i e-post **,** Skanna filer i **SharePoint, OneDrive och Teams** och sök igenom länkar i Office skrivbord och Office **Online-appar** under Sök efter skadligt **innehåll.**

   Under **Länkar och bifogade filer i e-postmeddelanden** skriver du in Alla användare eller de användare vars e-post du vill skanna.

   ![Markera alla kryssrutor i Öka skyddet mot avancerade hot.](../media/setatp.png)

5. Välj **Skapa principer** för att aktivera Valv bifogade filer Valv länkar.

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a>Konfigurera e Valv och bifogade filer i Säkerhets- & Säkerhets- och efterlevnadscenter

Personer skickar, tar emot och delar regelbundet bifogade filer, till exempel dokument, presentationer, kalkylblad med mera. Det är inte alltid lätt att avgöra om en bifogad fil är säker eller skadlig bara genom att titta på ett e-postmeddelande. Microsoft Defender för Office 365 innehåller Valv skydd för bifogade filer, men det här skyddet är inte aktiverat som standard. Vi rekommenderar att du skapar en ny regel för att börja använda det här skyddet. Skyddet omfattar filer i SharePoint, OneDrive och Microsoft Teams.

Om du vill Valv en princip för bifogade filer kan du [antingen titta på](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)den här korta videon eller utföra följande steg:

1. Gå till <https://protection.office.com> och logga in med ditt administratörskonto.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i **det vänstra navigeringsfönstret** väljer du **Princip.**

3. På sidan Princip väljer du Välj **Valv Bifogade filer**.

4. På sidan Valv bifogade filer tillämpar du det här skyddet brett genom att markera kryssrutan Aktivera ATP för **SharePoint, OneDrive** och Microsoft Teams.

5. Välj **+** för att skapa en ny princip.

6. Använd inställningarna i följande tabell.

7. När du har granskat inställningarna väljer du **Skapa den här principen** eller **Spara** efter behov.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Blockera aktuella och framtida e-postmeddelanden med upptäckt skadlig programvara.|
|Beskrivning|Blockera aktuella och framtida e-postmeddelanden och bifogade filer med identifierade skadlig programvara.|
|Spara bifogade filer – okänd skadlig kod|Välj **Blockera – blockera aktuella och framtida e-postmeddelanden och bifogade filer med upptäckt skadlig kod.**|
|Omdirigera bifogad fil vid identifiering|Aktivera omdirigering (markera den här rutan) <br/> Ange administratörskontot eller en postlådekonfiguration för karantän. <br/> Använd alternativet ovan om genomsökning efter bifogade filer på tider eller fel inträffar (markera den här rutan).|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|

Mer information finns i [Konfigurera principer för skydd mot nätfiske i Defender för Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).

### <a name="set-up-safe-links-in-the-security--compliance-center"></a>Konfigurera Valv i Säkerhets- & Säkerhets- och efterlevnadscenter

Hackare döljer ibland skadliga webbplatser i länkar i e-postmeddelanden och andra filer. Valv Länkar, som är en del av Microsoft Defender för Office 365, kan skydda organisationen genom att tillhandahålla snabb verifiering av webbadresser (URL:er) i e-postmeddelanden och Office dokument. Skydd definieras via Valv principer för länkar.

Vi rekommenderar att du gör följande:

- Ändra standardprincipen för att öka skyddet.

- Lägg till en ny princip som är riktad för alla mottagare i din domän.

Om du vill Valv konfigurera länkar kan du [titta på den här](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)korta utbildningsvideon eller följa stegen nedan:

1. Gå till <https://protection.office.com> och logga in med ditt administratörskonto.

2. I det vänstra & säkerhets- och efterlevnadscentret under Hothantering i **det vänstra navigeringsfönstret** väljer du **Princip.**

3. På sidan Princip väljer du **Valv Länkar**.

Så här ändrar du standardprincipen:

1. På Valv under Principer som **gäller för hela** organisationen väljer du **Standardprincip.**

2. Under Inställningar som gäller för innehåll utom **e-post** väljer **du Microsoft 365-appar för företag, Office för iOS och Android.**

3. Klicka på **Spara**.

Så här skapar du en ny princip som är riktad till alla mottagare i din domän:

1. På sidan Valv, under Principer som gäller för hela **organisationen, klickar** du på för **+** att skapa en ny princip.

2. Använd inställningarna i följande tabell.

3. Klicka på **Spara**.

|Inställning eller alternativ|Rekommenderad inställning|
|---|---|
|Namn|Valv länkar för alla mottagare i domänen|
|Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden|Välj **På – URL:er skrivs om och kontrolleras mot en lista med kända skadliga länkar när användaren klickar på länken.**|
|Använda bifogade Valv för att söka igenom nedladdningsbart innehåll|Markera den här rutan.|
|Tillämpas på|Mottagarens domän är . . . väljer du din domän.|

Mer information finns i [Valv i Defender för Office 365](../security/office-365-security/safe-links.md).

## <a name="turn-on-the-unified-audit-log"></a>Aktivera den enhetliga granskningsloggen

När du har aktivera granskningsloggsökningen i Säkerhets- och & efterlevnadscenter kan du behålla administratör och annan användaraktivitet i loggen och söka i den.

Du måste ha tilldelats rollen Granskningsloggar i Exchange Online aktivera eller inaktivera granskningsloggsökning i din Microsoft 365 prenumeration. Som standard är den här rollen tilldelad rollgrupperna Efterlevnadshantering och Organisationshantering på sidan Behörigheter Exchange administrationscentret. Globala administratörer i Microsoft 365 är medlemmar i den här gruppen som standard.

1. Om du vill aktivera granskningsloggsökningen går du till administrationscentret och <https://admin.microsoft.com> väljer sedan **Säkerhet** under **Administrationscenter** i det vänstra navigeringsfältet.
2. På sidan Microsoft 365 **säkerhet** väljer du **Fler**  resurser och sedan Öppna på Office 365 **för & säkerhets- och efterlevnadscenter.**

    ![Välj Öppna på säkerhets- & kompatibilitetsbilar.](../media/gotosecandcomp.png)
3. På sidan säkerhet och efterlevnad väljer du **Sök och** sedan **Granskningsloggsökning**.
4. Välj Aktivera granskning **högst upp på sidan** **Granskningsloggsökning.**

När funktionen är aktiverad kan du söka efter filer, mappar och många aktiviteter. Mer information finns i söka [i granskningsloggen](../compliance/search-the-audit-log-in-security-and-compliance.md).

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders&quot;></a>Finjustera inställningar för anonym delning av SharePoint och OneDrive filer och mappar

(ändra standardinställningen för anonym länk till 14 dagar, ändra standarddelningstypen till &quot;Vissa personer") Så här ändrar du delningsinställningarna för OneDrive och SharePoint:

1. Gå till administrationscentret och välj <https://admin.microsoft.com> SharePoint administrationscentret **i** det vänstra  navigeringsfältet.
2. Gå till SharePoint principerdelning i  \> **administrationscentret.**
3. Under  Fil- och mapplänkar på sidan Delning väljer du Specifika personer och  **under** Avancerade inställningar för **"Alla"-länkar** markerar du Dessa länkar måste upphöra att gälla inom så här många dagar och skriv in 14 (eller ett annat antal dagar som du vill begränsa länkens livslängd till).

   ![Välj Specifika personer och ange att länken ska gå ut 14 dagar.](../media/anyonelinks.png)

## <a name="activity-alerts"></a>Aktivitetsaviseringar

Du kan använda aktivitetsaviseringar för att spåra administratörs- och användaraktiviteter och identifiera incidenter mot skadlig programvara och dataförlust i organisationen. Din prenumeration innehåller en uppsättning standardprinciper, men du kan också skapa egna. Mer information finns i [aviseringsprinciper.](../compliance/alert-policies.md) Om du till exempel lagrar en viktig fil i SharePoint som du inte vill att någon ska dela externt kan du skapa ett meddelande som meddelar dig om någon delar den.

På följande bild visas de standardprinciper som ingår i Microsoft 365.

![Standardprinciper för avisering ingår i Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a>Inaktivera eller hantera kalenderdelning

Du kan förhindra att personer i organisationen delar sina kalendrar eller så kan du hantera vad de kan dela. Du kan till exempel begränsa delningen till endast ledig/upptagen tid.

1. Gå till administrationscentret på <https://admin.microsoft.com> och välj Inställningar Organisation  \> **Inställningar**.
2. På sidan **Tjänster** väljer du **Kalender** och väljer om personer i organisationen ska kunna dela sina kalendrar med personer utanför organisationen som har Office 365 eller Exchange eller med någon.

   Om du väljer alternativet Dela med alla kan du välja att även bara dela ledig/upptagen-information.

3. Välj **Spara ändringar** längst ned på sidan.

   Följande bild visar kalenderdelning som inte är tillåten.

   ![Skärmbild som visar extern kalenderdelning som ej tillåten.](../media/nocalendarsharing.png)

   På följande bild visas inställningarna när kalenderdelning tillåts med en e-postlänk med endast ledig/upptagen-information.

   ![Skärmbild av ledig/upptagen-delning i kalendern med vem som helst.](../media/sharefreebusy.png)

Om användarna tillåts dela sina kalendrar kan du läsa [de här](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) anvisningarna för hur du delar Outlook på webben.
