---
title: Konfigurera Micro Focus ArcSight för att hämta Microsoft Defender för identifiering av slutpunkter
description: Konfigurera Micro Focus ArcSight för att ta emot och dra identifieringar från Microsoft Defender Säkerhetscenter
keywords: konfigurera Micro Focus ArcSight, säkerhetsinformation och händelsehanteringsverktyg, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166191"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>Konfigurera Micro Focus ArcSight för att hämta Defender för slutpunktsidentifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

Du måste installera och konfigurera vissa filer och verktyg för att använda Micro Focus ArcSight så att Defender kan användas för identifiering av slutpunkter.

>[!Note]
>- [Defender för slutpunktsavisering](alerts.md) består av en eller flera identifieringar
>- [Defender för identifiering av](api-portal-mapping.md) slutpunkt består av den misstänkta händelsen som inträffade på enheten och tillhörande aviseringsinformation.

## <a name="before-you-begin"></a>Innan du börjar

Konfigurering av verktyget Micro Focus ArcSight Connector kräver flera konfigurationsfiler för att hämta och tolka identifieringar från Azure Active Directory-programmet (AAD).

I det här avsnittet får du hjälp med att ställa in och använda de konfigurationsfiler som krävs.

- Kontrollera att du har aktiverat funktionen SIEM-integrering på **menyn** Inställningar. Mer information finns i Aktivera [SIEM-integrering i Defender för slutpunkt.](enable-siem-integration.md)

- Se till att filen du sparade från att aktivera SIEM-integreringsfunktionen är klar. Du måste få följande värden:
  - OAuth 2.0 Token refresh URL
  - OAuth 2.0 Klient-ID
  - OAuth 2.0 Client secret

- Ha följande konfigurationsfiler redo:
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    Du skulle ha sparat en ZIP-fil som innehåller de här två filerna när du valde Micro Focus ArcSight som den SIEM-typ du använder i organisationen.

- Se till att du genererar följande token och har dem redo:
  - Åtkomsttoken
  - Uppdatera token

  Du kan generera de här tokenen från avsnittet konfiguration av **SIEM-integrering** i portalen.

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Installera och konfigurera Micro Focus ArcSight FlexConnector

I följande anvisningar förutsätts att du har slutfört alla steg som krävs [i Innan du börjar](#before-you-begin).

1. Installera det senaste 32-bitars Windows FlexConnector-installationsprogrammet. Du hittar detta i HPE Software Center. Verktyget installeras vanligtvis på följande standardplats: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</br></br>Du kan välja var verktyget ska sparas, till exempel C: \\ *folder_location*\current\bin där *folder_location* representerar installationsplats.

2. Följ installationsguiden genom följande uppgifter:
   - Introduktion
   - Välj Installera mapp
   - Välj Installera uppsättning
   - Välj Genvägsmapp
   - Sammanfattning före installationen
   - Installerar...

   Du kan behålla standardvärdena för var och en av dessa uppgifter eller ändra valet så att det passar dina behov.

3. Öppna Utforskaren och leta reda på de två konfigurationsfiler som du sparade när du aktiverade SIEM-integreringsfunktionen. Placera de två filerna på FlexConnector-installationsplatsen, till exempel:

   - WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   - WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent\

   > [!NOTE]
   > 
   > Du måste placera konfigurationsfilerna på den här *platsen, folder_location* representerar den plats där du installerade verktyget.

4. När installationen av kärnkopplingen är klar öppnas fönstret Kopplingskonfiguration. Välj Lägg till en koppling i **fönstret Konfiguration av koppling.**

5. Välj Typ: **ArcSight FlexConnector REST** och klicka på **Nästa**.

6. Ange följande information i formuläret för parameterinformation. Alla andra värden i formuläret är valfria och kan lämnas tomma.

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>Fält</th>
    <th>Value</th>
    </tr>
    <tr>
    <td>Konfigurationsfil</td>
    <td>Skriv namnet på egenskapsfilen för klienten. Namnet måste matcha filen som angavs i ZIP-filen som du hämtade.
Om konfigurationsfilen i flexagent-katalogen till exempel heter &quot; &quot;WDATP-Connector.js&quot; onparser.properties måste du skriva &quot; &quot; WDATP-Connector &quot; som namn på egenskapsfilen för klienten.</td>
    </tr>
    <td>URL för händelser</td>
    <td>Beroende på platsen för ditt datacenter väljer du antingen EU eller URL:en för USA: </br></br> <b>För EU:</b>https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>För USA:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>I Storbritannien</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>Autentiseringstyp</td>
    <td>OAuth 2</td>
    </tr>
    <td>OAuth 2 Client Properties-fil</td>
    <td>Bläddra till platsen för <em>wdatp-connector.properties-filen.</em> Namnet måste matcha filen som angavs i ZIP-filen som du hämtade.</td>
    <tr>
    <td>Uppdatera token</td>
    <td>Du kan hämta en uppdateringstoken på två sätt: genom att generera en uppdateringstoken från sidan <b>SIEM-inställningar</b> eller använda restutil-verktyget. <br><br> Mer information om att generera en uppdateringstoken från <b>inställningarna</b> finns i <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Aktivera SIEM-integrering i Defender för slutpunkt.</a> </br> </br><b>Hämta uppdateringstoken med verktyget restutil:</b> </br> a. Öppna en kommandotolk. Gå till C:\<em>folder_location</em>\current\bin <em>där folder_location</em> representerar den plats där du installerade verktyget. </br></br> b. Skriv: <code>arcsight restutil token -config</code> från fackkatalogen. Till exempel: <b>arcsight restutil boxtoken -proxy.location.hp.com:8080</b> ett webbläsarfönster öppnas. </br> </br>c. Skriv in dina autentiseringsuppgifter och klicka sedan på lösenordsfältet för att låta sidan omdirigera. I inloggningsupp frågan anger du dina autentiseringsuppgifter. </br> </br>d. En uppdateringstoken visas i kommandotolken. </br></br> e. Kopiera och klistra in den i <b>fältet Uppdatera</b> token.
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. Ett webbläsarfönster öppnas av kopplingen. Logga in med dina inloggningsuppgifter för programmet. När du har loggat in uppmanas du att ge behörighet till din OAuth2-klient. Du måste ge behörighet till din OAuth 2-klient så att anslutningskonfigurationen kan autentiseras.

   Om det <code>redirect_uri</code> är en https-URL omdirigeras du till en URL på den lokala värden. En sida visas där du uppmanas att lita på det certifikat som tillhandahålls av anslutningen som körs på den lokala värden. Du måste lita på certifikatet om det redirect_uri ett https.
   
   Om du däremot anger en http-URL för redirect_uri-adress, behöver du inte ge ditt medgivande för att lita på certifikatet.

8. Fortsätt med anslutningskonfigurationen genom att gå tillbaka till installationsfönstret för Micro Focus ArcSight Connector.

9. Välj **Hanteraren för ArcSight (krypterad)** som destination och klicka på **Nästa.**

10. Skriv in mål-IP/hostname i **Manager Hostname** och dina autentiseringsuppgifter i formuläret för parametrar. Alla andra värden i formuläret bör behållas med standardvärdena. Klicka på **Nästa**.

11. Skriv ett namn på kopplingen i formuläret för kopplingsinformation. Alla andra värden i formuläret är valfria och kan lämnas tomma. Klicka på **Nästa**.

12. Fönstret för importcertifikat för ESM-hanteraren visas. Välj **Importera certifikatet till anslutningen från destinationen och** klicka på **Nästa.** Fönstret **Lägg till** kopplingssammanfattning visas och certifikatet importeras.

13. Kontrollera att informationen i fönstret Sammanfattning **av lägg till koppling** är korrekt och klicka sedan på **Nästa.**

14. Välj **Installera som tjänst och** klicka på **Nästa.**

15. Skriv ett namn i fältet **Internt namn för** tjänsten. Alla andra värden i formuläret kan behållas med standardvärdena eller lämnas tomma. Klicka på **Nästa**.

16. Skriv in tjänstparametrarna och klicka på **Nästa.** Ett fönster med **sammanfattningen av installationen** av tjänsten visas. Klicka på **Nästa**.

17. Avsluta installationen genom att välja **Avsluta** och **Nästa.**

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Installera och konfigurera Konsolen Micro Focus ArcSight

1. Följ installationsguiden genom följande uppgifter:
   - Introduktion
   - Licensavtal
   - Specialmeddelande
   - Välj installationskatalogen ArcSight
   - Välj Genvägsmapp
   - Sammanfattning före installationen

2. Klicka på **Installera**. När installationen har slutförts öppnas konfigurationsguiden för ArcSight Console.

3. Skriv localhost i **Manager Host Name och** 8443 i Manager Port **och** klicka sedan på **Nästa.**

4. Välj **Använd direktanslutning** och klicka sedan på **Nästa.**

5. Välj **Lösenordsbaserad autentisering** och klicka sedan på **Nästa.**

6. Välj **Det här är en installation för en enskild användare. (Rekommenderas)** och klicka sedan på **Nästa.**

7. Avsluta **installationsprogrammet** genom att klicka på Klar.

8. Logga in på konsolen Micro Focus ArcSight.

9. Gå till **Aktiv kanal ange Ny** villkor  >    >    >  **enhetens enhet produkt**.

10. Ange **enhetsprodukt = Microsoft Defender ATP**. När du har kontrollerat att händelser flödar till verktyget stoppar du processen igen och går till Windows Services och startar ArcSight FlexConnector REST.

Nu kan du köra frågor i konsolen Micro Focus ArcSight.

Defender för slutpunktsidentifiering visas som fristående händelser, med "Microsoft" som leverantör och "Windows Defender ATP" som enhetsnamn.


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Felsöka anslutning för Micro Focus ArcSight

**Problem:** Det gick inte att uppdatera token. Loggen finns på C: folder_location \\ \current\logs där *folder_location* representerar den plats där du installerade verktyget. Öppna _agent.log_ och leta efter `ERROR/FATAL/WARN` .

**Symptom:** Du får följande felmeddelande:

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**Lösning:**

1. Stoppa processen genom att klicka på Ctrl + C i fönstret Koppling. Klicka **på Y** när du tillfrågas om "Avbryt batchjobb Y/N?".

2. Gå till mappen där du sparade FILEN WDATP-connector.properties och redigera den för att lägga till följande värde: `reauthenticate=true` .

3. Starta om kopplingen genom att köra följande kommando: `arcsight.bat connectors` .

   Ett webbläsarfönster visas. Tillåt att den körs, den ska försvinna och kopplingen ska nu vara igång.

> [!NOTE]
> Kontrollera att kopplingen körs genom att stoppa processen igen. Starta sedan kopplingen igen så visas inget webbläsarfönster.

## <a name="related-topics"></a>Relaterade ämnen
- [Aktivera SIEM-integrering i Defender för Slutpunkt](enable-siem-integration.md)
- [Dra identifieringar till dina SIEM-verktyg](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [Hämta Defender för slutpunktsidentifiering med REST API](pull-alerts-using-rest-api.md)
- [Felsöka problem med SIEM-verktygsintegrering](troubleshoot-siem.md)
