---
title: Använda Microsoft Defender för slutpunkts-API:er
ms.reviewer: ''
description: Lär dig hur du utformar en Windows-app för att få programtisk åtkomst till Microsoft Defender för Endpoint utan en användare.
keywords: apis, graph api, apis som stöds, aktör, aviseringar, enhet, användare, domän, ip, fil, avancerad sökning, fråga
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8f23a0b269986f4caa199ad3744c563fcc6ff6b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769107"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Använda Microsoft Defender för slutpunkts-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

På den här sidan beskrivs hur du skapar ett program för att få programmässiga åtkomst till Defender för Endpoint för en användares räkning.

Om du behöver programmeringsåtkomst till Microsoft Defender för Slutpunkt utan en användare går du till [Access Microsoft Defender för Slutpunkt med programkontext](exposed-apis-create-app-webapp.md).

Om du inte är säker på vilken åtkomst du behöver kan du läsa [introduktionssidan.](apis-intro.md)

Microsoft Defender för slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De här API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Microsoft Defender för Slutpunkt-funktioner. API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

I allmänhet måste du vidta följande steg för att använda API:er:
- Skapa ett AAD-program
- Hämta en åtkomsttoken med det här programmet
- Använda token för att komma åt Defender för Endpoint API

På den här sidan förklaras hur du skapar ett AAD-program, hämtar en åtkomsttoken till Microsoft Defender för Endpoint och verifierar token.

>[!NOTE]
> När du öppnar Microsoft Defender för Endpoint API åt en användare behöver du rätt programbehörighet och användarbehörighet.
> Om du inte är bekant med användarbehörigheter i Microsoft Defender för Endpoint kan du läsa Hantera [portalåtkomst med hjälp av rollbaserad åtkomstkontroll](rbac.md).

>[!TIP]
> Om du har behörighet att utföra en åtgärd i portalen har du behörighet att utföra åtgärden i API:t.

## <a name="create-an-app"></a>Skapa en app

1. Logga in på [Azure](https://portal.azure.com) med ett användarkonto som har **rollen Global** administratör.

2. Gå till **Azure Active Directory**  >  **Appregistreringar**  >  **Ny registrering.** 

   ![Bild av Microsoft Azure navigering till registrering av program](images/atp-azure-new-app2.png)

3. När sidan **Registrera ett program** visas anger du registreringsinformationen för ditt program:

   - **Namn** – Ange ett beskrivande programnamn som ska visas för användare av programmet.
   - **Kontotyper som stöds** – Välj vilka konton du vill att programmet ska ha stöd för.

       | Kontotyper som stöds | Beskrivning |
       |-------------------------|-------------|
       | **Konton endast i den här organisationskatalogen** | Välj det här alternativet om du skapar ett LOB-program. Det här alternativet är inte tillgängligt om du inte registrerar programmet i en katalog.<br><br>Det här alternativet mappar endast till Azure AD med en klientorganisation.<br><br>Det här är standardalternativet såvida du inte registrerar programmet utanför en katalog. I fall där appen är registrerad utanför en katalog är standard azure AD-konton för flera innehavare och personliga Microsoft-konton. |
       | **Konton i valfri organisationskatalog** | Välj det här alternativet om du vill rikta alla företags- och utbildningskunder.<br><br>Det här alternativet mappar till en Azure AD endast för flera innehavare.<br><br>Om du har registrerat appen som Azure AD endast för en enskild klientorganisation kan du uppdatera den till Att vara Azure AD för flera innehavare och tillbaka till en klientorganisation via **autentiseringsbladet.** |
       | **Konton i valfri organisationskatalog och personliga Microsoft-konton** | Välj det här alternativet om du vill ha det i hela uppsättningen kunder.<br><br>Det här alternativet mappar till Azure AD-konton för flera innehavare och personliga Microsoft-konton.<br><br>Om du har registrerat appen som Azure AD-konton för flera innehavare och personliga Microsoft-konton kan du inte ändra detta i användargränssnittet. I stället måste du använda manifestredigeraren för att ändra kontotyperna som stöds. |

   - **Omdirigerings-URI (valfritt)** – Välj typ av app du **skapar,** Webb eller Offentlig klient **(mobil & skrivbord)** och ange sedan omdirigerings-URI (eller svars-URL) för programmet.
       - För webbprogram anger du programmets bas-URL. Kan till `http://localhost:31544` exempel vara URL-adressen för en webbapp som körs på din lokala dator. Användarna skulle använda URL-adressen för att logga in i ett webbklientprogram.
       - För offentliga klientprogram anger du den URI som används av Azure AD för att returnera tokensvar. Ange ett specifikt värde för programmet, till exempel `myapp://auth` .

     Om du vill se specifika exempel för webbprogram eller interna program kan du läsa [våra snabbstartsguider.](/azure/active-directory/develop/#quickstarts)

     När du är klar väljer du **Registrera**.

4. Tillåt att ditt program får åtkomst till Microsoft Defender för Endpoint och tilldela behörigheten Läsaviseringar:

    - Välj API-behörigheter Lägg till **behörighetS-API:er** som min organisation använder för  >    >   > **WindowsDefenderATP** och välj på **WindowsDefenderATP.**

    - **Obs!** *WindowsDefenderATP* visas inte i den ursprungliga listan. Börja skriva namnet i textrutan så att det visas.

      ![lägg till behörighet](images/add-permission.png)

    - Välj **Avisering om**  >  **delegerade behörigheter.Läs** > välj **Lägg till behörigheter**

      ![programbehörigheter](images/application-permissions-public-client.png)

    - **Viktigt meddelande:** Välj relevant behörighet. Läsaviseringar är bara ett exempel.

      Exempel:

      - Om [du vill köra avancerade](run-advanced-query-api.md)frågor väljer du behörigheten Kör avancerade frågor
      - Om [du vill isolera en enhet](isolate-machine.md)väljer du behörigheten Isolera dator
      - Ta reda på vilken behörighet du behöver i avsnittet **Behörigheter** i API:t som du vill anropa.

    - Välj **Bevilja medgivande**

      **Obs!** Varje gång du lägger till behörighet måste du välja **Bevilja medgivande** för att den nya behörigheten ska gälla.

      ![Bild av bevilja behörigheter](images/grant-consent.png)

6. Skriv ned ditt program-ID och ditt klient-ID:

   - Gå till Översikt på **programsidan och** kopiera följande information:

   ![Bild på skapad app-ID](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a>Hämta en åtkomsttoken

Mer information om AAD-tokens finns i [Självstudiekurs för Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="using-c"></a>Använda C #

- Kopiera/klistra in nedanstående klass i programmet.
- Använd **metoden AcquireUserTokenAsync** med ditt program-ID, klientorganisations-ID, användarnamn och lösenord för att hämta en token.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>Verifiera token

Kontrollera att du har fått rätt token:
- Kopiera/klistra in [i JWT](https://jwt.ms) den token du fick i föregående steg för att avkoda den
- Verifiera att du får ett SCP-anspråk med rätt appbehörighet
- På skärmbilden nedan kan du se en avkodad token som förvärvats från programmet i självstudiekursen:

![Bild på tokenverifiering](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Använda token för att komma åt Microsoft Defender för Endpoint API

- Välj det API du vill använda – Microsoft [Defender som stöds för slutpunkts-API:er](exposed-apis-list.md)
- Ange rubriken Auktorisering i HTTP-begäran som du skickar till "Bearer {token}" (Bearer är auktoriseringsschemat)
- Förfallodatum för token är 1 timme (du kan skicka mer än en begäran med samma token)

- Exempel på att skicka en begäran om att få en lista med aviseringar **med C#** 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Se även
- [Microsoft Defender för slutpunkts-API:er](exposed-apis-list.md)
- [Access Microsoft Defender för slutpunkt med programkontext](exposed-apis-create-app-webapp.md)
