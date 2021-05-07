---
title: Konfigurera en koppling för att arkivera information om Bloomberg-meddelanden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratörer kan konfigurera en dataanslutning för att importera och arkivera data från e-postverktyget Bloomberg Message i Microsoft 365. På så sätt kan du arkivera data från datakällor från tredje part i Microsoft 365 så att du kan använda efterlevnadsfunktioner som bevarande av juridiska principer, innehållssökning och bevarandeprinciper för att hantera data från tredje part i organisationen.
ms.openlocfilehash: 7029b95e4b9ceb91859e2a4b38afb5205e3307b2
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162470"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Konfigurera en koppling för att arkivera information om Bloomberg-meddelanden

Använd en dataanslutning i kompatibilitetscentret för Microsoft 365 för att importera och arkivera e-postdata för finansiella tjänster från [samarbetsverktyget Bloomberg Message.](https://www.bloomberg.com/professional/product/collaboration/) När du har konfigurerat och konfigurerat en anslutning ansluts den till din organisations Ftp-säkra FTP-webbplats (SFTP) en gång om dagen och importerar e-postobjekt till postlådor i Microsoft 365.

När Bloomberg Message-data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, innehållssökning, arkivering på plats, granskning, kommunikationsefterlevnad och Microsoft 365-bevarandeprinciper för Bloomberg Message-data. Du kan till exempel söka i Bloomberg Message-e-postmeddelanden med hjälp av verktyget för innehållssökning eller associera postlådan som innehåller Information om Bloomberg-meddelandet med en medarbetare i ett Advanced eDiscovery fall. Genom att använda en Koppling för Bloomberg Message till att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Översikt över arkivering av information om Bloomberg-meddelanden

Följande översikt förklarar processen med att använda en koppling för att arkivera data i Bloomberg Message i Microsoft 365.

![Processen för import och arkiv av meddelanden i Bloomberg](../media/BloombergMessageArchiving.png)

1. Din organisation arbetar med Bloomberg för att skapa en Bloomberg SFTP-webbplats. Du arbetar också med Bloomberg för att konfigurera Bloomberg Message så att det kopierar e-postmeddelanden till BloombergS SFTP-webbplats.

2. En gång per dygn kopieras e-postmeddelanden från Bloomberg Message till BloombergS SFTP-webbplats.

3. Kopplingen Bloomberg Message som du skapar i efterlevnadscentret för Microsoft 365 ansluter till Bloombergs SFTP-webbplats varje dag och överför e-postmeddelanden från de föregående 24 timmarna till ett säkert Azure Storage område i Microsoft Cloud.

4. Kopplingen importerar e-postobjekten till en viss användares postlåda. En ny mapp med namnet BloombergMessage skapas i den specifika användarens postlåda och objekten importeras till den.

   Kopplingen gör detta med hjälp av värdet för egenskapen CorporateEmailAddress. Alla e-postmeddelanden innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare i e-postmeddelandet. Förutom automatisk användarmappning med värdet för egenskapen *CorporateEmailAddress* kan du också definiera en anpassad mappning genom att ladda upp en CSV-mappningsfil. Den här mappningsfilen innehåller Bloomberg UUID och motsvarande e Microsoft 365 postlådeadress för varje användare i organisationen. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på den anpassade mappningsfilen för varje e-postobjekt. Om kopplingen inte hittar en giltig Microsoft 365-användare som motsvarar en användares Bloomberg UUID använder kopplingen egenskapen *CorporateEmailAddress* för e-postobjektet. Om kopplingen inte hittar en giltig Microsoft 365-användare i antingen custom-mapping-filen eller *egenskapen CorporateEmailAddress* för e-postobjektet, importeras inte objektet.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

Några av de implementeringssteg som krävs för att arkivera data i Bloomberg Message är Microsoft 365 och måste slutföras innan du kan skapa anslutningen i efterlevnadscentret.

- Om du vill konfigurera en Koppling för Bloomberg Message måste du använda tangenter och tangentpassphraser för PGP (Pretty Good Privacy) och Secure Shell (SSH). Dessa nycklar används för att konfigurera Bloomberg SFTP-webbplatsen och används av kopplingen för att ansluta till BloombergS SFTP-webbplatsen för att importera data till Microsoft 365. PGP-nyckeln används för att konfigurera krypteringen av data som överförs från BloombergS SFTP-webbplatsen till Microsoft 365. SSH-nyckeln används för att konfigurera säkert gränssnitt för att aktivera en säker fjärrinloggning när kopplingen ansluter till BloombergS SFTP-webbplatsen.

  När du inställningar för en koppling kan du välja att använda offentliga tangenter och lösenordsfraser som tillhandahålls av Microsoft, eller så kan du använda dina egna privata nycklar och lösenord. Vi rekommenderar att du använder de offentliga nycklar som tillhandahålls av Microsoft. Men om din organisation redan har konfigurerat en Bloomberg SFTP-webbplats med privata nycklar kan du skapa en koppling med samma privata nycklar.

- Prenumerera på [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Detta krävs för att du ska kunna logga in på Bloomberg Anywhere för att komma åt BloombergS SFTP-webbplatsen som du måste konfigurera.

- Konfigurera en Bloomberg SFTP-webbplats (Secure File Transfer Protocol). När du har arbetat med Bloomberg med att konfigurera SFTP-webbplatsen laddas data från Bloomberg Message upp till SFTP-webbplatsen varje dag. Kopplingen som du skapar i steg 2 ansluter till den här SFTP-webbplatsen och överför e-postdata till Microsoft 365 postlådor. SFTP krypterar även information om Bloomberg-meddelandet som skickas till postlådor under överföringsprocessen.

  Mer information om Bloomberg SFTP (kallas *även BB-SFTP*):

  - Se dokumentet "SFTP Connectivity Standards" på [Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Kontakta [Bloombergs kundsupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

- När du har samarbetat med Bloomberg med att konfigurera en SFTP-webbplats kommer Bloomberg att ge dig viss information när du svarar på e-postmeddelandet från Bloomberg-implementeringen. Spara en kopia av följande information. Du använder den för att konfigurera en koppling i steg 3.

  - Fast kod, som är ett ID för din organisation och används för att logga in på Bloomberg SFTP-webbplatsen.

  - Lösenord för din Bloomberg SFTP-webbplats

  - URL för Bloomberg SFTP-webbplats (till exempel sftp.bloomberg.com). Dessutom kan Bloomberg tillhandahålla en motsvarande IP-adress till Bloomberg SFTP-webbplatsen, som också kan användas för att konfigurera kopplingen.

  - Portnummer för Bloomberg SFTP-webbplats

- Kopplingen Bloomberg Message kan importera totalt 200 000 objekt på en enda dag. Om det finns fler än 200 000 objekt på SFTP-webbplatsen importeras inga av dessa objekt till Microsoft 365.

- Den användare som skapar en Koppling för Bloomberg Message i steg 3 (och som laddar ned de offentliga nycklarna och IP-adressen i steg 1) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Detta krävs för att lägga till kopplingar på **sidan Datakopplingar** i Microsoft 365 kompatibilitetscenter. Som standard är den här rollen inte tilldelad någon rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="set-up-a-connector-using-public-keys"></a>Konfigurera en koppling med hjälp av offentliga tangenter

Anvisningarna i det här avsnittet visar hur du ställer in en koppling för Bloomberg Message med hjälp av de offentliga tangenterna för PGP (Pretty Good Privacy) och Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Steg 1: Hämta offentliga nycklar för PGP och SSH

Det första steget är att skaffa en kopia av de offentliga nycklarna PGP och SSH. Du använder de här nycklarna i steg 2 för att konfigurera Bloombergs SFTP-webbplats så att kopplingen (som du skapar i steg 3) ansluter till SFTP-webbplatsen och överför e-postdata för Bloomberg-meddelandet till Microsoft 365 postlådor. Du får också en IP-adress i det här steget, som du använder när du konfigurerar BloombergS SFTP-webbplatsen.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. På sidan **Datakopplingar** under **Bloomberg-meddelande klickar** du på **Visa**.

3. På sidan **Produktbeskrivning för Bloomberg Message** klickar du på **Lägg till koppling**

4. Klicka på **Acceptera på** sidan **Användningsvillkor.**

5. På sidan **Lägg till autentiseringsuppgifter för innehållskälla** klickar du på **Jag vill använda offentliga PGP- och SSH-nycklar från Microsoft.**

   ![Välj alternativet för att använda offentliga nycklar](../media/BloombergMessagePublicKeysOption.png)

6. Under steg 1 klickar du på Länkarna Ladda ned **SSH**, Ladda ned **PGP-tangenten** och Ladda ned **IP-adresslänkar** för att spara en kopia av varje fil på din lokala dator.

   ![Länkar för att ladda ned offentliga nycklar och IP-adress](../media/BloombergMessagePublicKeyDownloadLinks.png)

   Dessa filer innehåller följande objekt som används för att konfigurera Bloomberg SFTP-webbplatsen i steg 2:

   - Offentlig PGP-nyckel: Den här nyckeln används för att konfigurera kryptering av data som överförs från BloombergS SFTP-webbplatsen till Microsoft 365.

   - Offentlig SSH-nyckel: Den här nyckeln används för att konfigurera säkert gränssnitt för att aktivera en säker fjärrinloggning när kopplingen ansluter till Bloomberg SFTP-webbplatsen.

   - IP-adress: BloombergS SFTP-webbplatsen är konfigurerad att acceptera anslutningsförfrågningar från den här IP-adressen. Samma IP-adress används av Bloomberg Message-kopplingen för att ansluta till SFTP-webbplatsen och överföra Bloomberg Message-data till Microsoft 365.

7. Stäng **guiden genom** att klicka på Avbryt. Du kommer tillbaka till den här guiden i Steg 3 för att skapa kopplingen.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Steg 2: Konfigurera Bloomberg SFTP-webbplatsen

> [!NOTE]
> Om din organisation tidigare har ställt in en Bloomberg SFTP-webbplats för att arkivera Instant Bloomberg-data med hjälp av offentliga PGP- och SSH-nycklar behöver du inte konfigurera ytterligare en. Du kan ange samma SFTP-webbplats när du skapar kopplingen i steg 3.

Nästa steg är att använda de offentliga tangenterna PGP och SSH och IP-adressen som du fick i steg 1 för att konfigurera PGP-kryptering och SSH-autentisering för Bloomberg SFTP-webbplatsen. Då kan kopplingen Bloomberg Message som du skapar i steg 3 ansluta till Bloomberg SFTP-webbplatsen och överföra Bloomberg Message-data till Microsoft 365. Du måste arbeta med Bloombergs kundsupport för att konfigurera din Sftp-webbplats för Bloomberg. Kontakta [Bloombergs kundsupport om](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) du behöver hjälp.

> [!IMPORTANT]
> Bloomberg rekommenderar att du bifogar de tre filer som du hämtade i steg 1 i ett e-postmeddelande och skickar det till kundsupportteamet när de arbetar med dem för att konfigurera din Sftp-webbplats för Bloomberg.

### <a name="step-3-create-a-bloomberg-message-connector"></a>Steg 3: Skapa en koppling för Bloomberg-meddelande

Det sista steget är att skapa en Bloomberg Message-koppling i Microsoft 365 för efterlevnadscenter. Kopplingen använder den information du anger för att ansluta till Bloombergs SFTP-webbplats och överföra e-postmeddelanden till motsvarande rutor för användarpostlådor i Microsoft 365.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. På sidan **Datakopplingar** under **Bloomberg-meddelande klickar** du på **Visa**.

3. På sidan **Produktbeskrivning för Bloomberg Message** klickar du på **Lägg till koppling**

4. Klicka på **Acceptera på** sidan **Användningsvillkor.**

5. På sidan **Lägg till autentiseringsuppgifter för innehållskälla** klickar du på **Jag vill använda offentliga PGP- och SSH-nycklar från Microsoft.**

6. Under Steg 3 anger du den information som krävs i följande rutor och klickar sedan på **Verifiera anslutning.**

      - **Namn:** Namnet på kopplingen. Den måste vara unik i din organisation.

      - **Företagskod:** ID för din organisation som används som användarnamn på Bloomberg SFTP-webbplatsen.

      - **Lösenord:** Lösenordet för din organisations Bloomberg SFTP-webbplats.

      - **SFTP-URL:** URL-adressen för Bloomberg SFTP-webbplatsen (till exempel `sftp.bloomberg.com` ). Du kan också använda en IP-adress för det här värdet.

      - **SFTP-port:** Portnumret för Bloomberg SFTP-webbplatsen. Kopplingen använder den här porten för att ansluta till SFTP-webbplatsen.

7. När anslutningen har verifierats klickar du på **Nästa.**

8. På sidan **Karta Bloomberg Message till användare Microsoft 365 aktivera** automatisk användarmappning och ange anpassad användarmappning efter behov.

   > [!NOTE]
   > Kopplingen importerar meddelandeobjekt till en viss användares postlåda. En ny mapp **med namnet BloombergMessage** skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör det med värdet för egenskapen *CorporateEmailAddress.* Varje chattmeddelande innehåller den här egenskapen och egenskapen fylls i med e-postadressen för alla deltagare i chattmeddelandet. Förutom automatisk användarmappning med värdet för egenskapen *CorporateEmailAddress* kan du också definiera anpassad mappning genom att ladda upp en CSV-mappningsfil. Mappningsfilen ska innehålla Bloomberg UUID och motsvarande Microsoft 365 postlådeadress för varje användare. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på anpassad mappningsfil för varje meddelandeobjekt. Om kopplingen inte hittar en giltig Microsoft 365-användare som motsvarar en användares Bloomberg UUID använder kopplingen egenskapen *CorporateEmailAddress* för chattobjektet. Om kopplingen inte hittar en giltig Microsoft 365 användare i den anpassade mappningsfilen eller *egenskapen CorporateEmailAddress* för meddelandeobjektet, importeras inte objektet.

9. Klicka **på** Nästa, granska dina inställningar och klicka sedan **på Slutför** för att skapa kopplingen.

10. Gå till **sidan Datakopplingar** för att se förloppet för importen för den nya anslutningen. Klicka på kopplingen för att visa den utfällade sidan som innehåller information om kopplingen.

## <a name="set-up-a-connector-using-private-keys"></a>Konfigurera en koppling med privata nycklar

Stegen i det här avsnittet visar hur du ställer in en kontakt för Bloomberg Message med privata PGP- och SSH-nycklar. Det här alternativet för kopplingskonfiguration är avsett för organisationer som redan har konfigurerat en Bloomberg SFTP-webbplats med privata nycklar.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Steg 1: Hämta en IP-adress för att konfigurera Bloomberg SFTP-webbplatsen

> [!NOTE]
> Om din organisation tidigare har konfigurerat en Bloomberg SFTP-webbplats för att arkivera Instant Bloomberg-data med privata PGP- och SSH-nycklar behöver du inte konfigurera en annan. Du kan ange samma SFTP-webbplats när du skapar kopplingen i steg 2.

Om din organisation har använt privata PGP- och SSH-nycklar för att konfigurera en Bloomberg SFTP-webbplats måste du ha en IP-adress och ge den till Bloombergs kundsupport. Bloombergs SFTP-webbplats måste vara konfigurerad för att acceptera anslutningsförfrågningar från denna IP-adress. Samma IP-adress används av Bloomberg Message-kopplingen för att ansluta till SFTP-webbplatsen och överföra Bloomberg Message-data till Microsoft 365.

Så här hämtar du IP-adressen:

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. På sidan **Datakopplingar** under **Bloomberg-meddelande klickar** du på **Visa**.

3. På sidan **Produktbeskrivning för Bloomberg Message** klickar du på **Lägg till koppling**

4. Klicka på **Acceptera på** sidan **Användningsvillkor.**

5. På sidan **Lägg till autentiseringsuppgifter för innehållskälla** klickar du **på Jag vill använda privata PGP- och SSH-nycklar.**

6. Under steg 1 klickar du på **Ladda ned IP-adress** för att spara en kopia av IP-adressfilen på den lokala datorn.

   ![Ladda ned IP-adressen](../media/BloombergMessageConnectorIPAddress.png)

7. Stäng **guiden genom** att klicka på Avbryt. Du kommer tillbaka till den här guiden i steg 2 för att skapa kopplingen.

Du måste arbeta med Bloombergs kundsupport för att konfigurera din SFTP-webbplats för Bloomberg att acceptera anslutningsförfrågningar från den här IP-adressen. Kontakta [Bloombergs kundsupport om](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) du behöver hjälp.

### <a name="step-2-create-a-bloomberg-message-connector"></a>Steg 2: Skapa en koppling för Bloomberg-meddelande

När du har konfigurerat BloombergS SFTP-webbplats är nästa steg att skapa en Koppling för Bloomberg Message i Microsoft 365 för efterlevnadscenter. Kopplingen använder den information du anger för att ansluta till Bloombergs SFTP-webbplats och överföra e-postmeddelanden till motsvarande rutor för användarpostlådor i Microsoft 365. För att slutföra det här steget ska du se till att ha kopior av samma privata nycklar och lösenordslösenord som du använde för att konfigurera din Bloomberg SFTP-webbplats.

1. Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.

2. På sidan **Datakopplingar** under **Bloomberg-meddelande klickar** du på **Visa**.

3. På sidan **Produktbeskrivning för Bloomberg Message** klickar du på **Lägg till koppling**

4. Klicka på **Acceptera på** sidan **Användningsvillkor.**

5. På sidan **Lägg till autentiseringsuppgifter för innehållskälla** klickar du **på Jag vill använda privata PGP- och SSH-nycklar.**

   ![Markera alternativet för att använda privata nycklar](../media/BloombergMessagePrivateKeysOption.png)

6. Under Steg 3 anger du den information som krävs i följande rutor och klickar sedan på **Verifiera anslutning.**

      - **Namn:** Namnet på kopplingen. Den måste vara unik i din organisation.

      - **Företagskod:** ID för din organisation som används som användarnamn på Bloomberg SFTP-webbplatsen.

      - **Lösenord:** Lösenordet för din organisations Bloomberg SFTP-webbplats.

      - **SFTP-URL:** URL-adressen för Bloomberg SFTP-webbplatsen (till exempel `sftp.bloomberg.com` ). Du kan också använda en IP-adress för det här värdet.

      - **SFTP-port:** Portnumret för Bloomberg SFTP-webbplatsen. Kopplingen använder den här porten för att ansluta till SFTP-webbplatsen.

      - **Privat PGP-nyckel:** Den privata PGP-nyckeln för Bloomberg SFTP-webbplatsen. Se till att ta med hela det privata nyckelvärdet, inklusive de första och sista raderna i nyckelblocket.

      - **PGP-nyckelfras:** Lösenordsfrasen för den privata PGP-nyckeln.

      - **Privat SSH-nyckel:** Den privata SSH-nyckeln för Bloomberg SFTP-webbplatsen. Se till att ta med hela det privata nyckelvärdet, inklusive de första och sista raderna i nyckelblocket.

      - **Lösenord för SSH-tangenten:** Lösenordsfrasen för den privata SSH-nyckeln.

7. När anslutningen har verifierats klickar du på **Nästa.**

8. På sidan **Karta Bloomberg Message till användare Microsoft 365 aktivera** automatisk användarmappning och ange anpassad användarmappning efter behov.

   > [!NOTE]
   > Kopplingen importerar meddelandeobjekt till en viss användares postlåda. En ny mapp **med namnet BloombergMessage** skapas i den specifika användarens postlåda och objekten importeras till den. Kopplingen gör det med värdet för egenskapen *CorporateEmailAddress.* Varje chattmeddelande innehåller den här egenskapen och egenskapen fylls i med e-postadressen för alla deltagare i chattmeddelandet. Förutom automatisk användarmappning med värdet för egenskapen *CorporateEmailAddress* kan du också definiera anpassad mappning genom att ladda upp en CSV-mappningsfil. Mappningsfilen ska innehålla Bloomberg UUID och motsvarande Microsoft 365 postlådeadress för varje användare. Om du aktiverar automatisk användarmappning och tillhandahåller en anpassad mappning kommer kopplingen först att titta på anpassad mappningsfil för varje meddelandeobjekt. Om kopplingen inte hittar en giltig Microsoft 365-användare som motsvarar en användares Bloomberg UUID använder kopplingen egenskapen *CorporateEmailAddress* för chattobjektet. Om kopplingen inte hittar en giltig Microsoft 365 användare i den anpassade mappningsfilen eller *egenskapen CorporateEmailAddress* för meddelandeobjektet, importeras inte objektet.

9. Klicka **på** Nästa, granska dina inställningar och klicka sedan **på Slutför** för att skapa kopplingen.

10. Gå till **sidan Datakopplingar** för att se förloppet för importen för den nya anslutningen. Klicka på kopplingen för att visa den utfällade sidan som innehåller information om kopplingen.

## <a name="known-issues"></a>Kända problem

- Trådning av e-postmeddelande i Bloomberg som importerats Microsoft 365 meddelanden stöds inte. Enskilda meddelanden som skickas till en person importeras, men de visas inte i en trådad konversation. Microsoft arbetar för att det ska gå att tråda i senare versioner av datakopplingen Bloomberg Message.
