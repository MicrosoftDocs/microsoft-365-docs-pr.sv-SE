---
title: Granska händelser och fel med hjälp av Loggboken
description: Få beskrivningar och ytterligare felsökningssteg (om det behövs) för alla händelser som rapporterats av Microsoft Defender för slutpunktstjänsten.
keywords: felsökning, händelsevisningsprogram, loggsammanfattning, felkod, misslyckades, Microsoft Defender för slutpunktstjänsten, kan inte starta, brytas, kan inte starta
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933847"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Granska händelser och fel med hjälp av Loggboken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- Loggboken
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Du kan granska händelse-IDt i [Loggboken](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) på enskilda enheter.

Om enheter inte visas i listan Enheter kan du till exempel behöva leta efter händelse-ID på enheterna. Du kan sedan använda tabellen för att fastställa ytterligare felsökningssteg.

**Öppna Loggboken och hitta Microsoft Defender för slutpunktens händelselogg för tjänsten:**

1. Klicka **på Start** på Windows-menyn, skriv **Loggboken** och tryck på **Retur.**

2. Bläddra i logglistan under **Loggsammanfattning** tills du ser **Microsoft-Windows-SENSE/Operational**. Dubbelklicka på objektet för att öppna loggen.

   a.  Du kan också öppna loggen genom att expandera **Program och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **SENSE och** klicka på **Drift.**

   > [!NOTE]
   > SENSE är det interna namn som används för att referera till den beteende sensor som driver Microsoft Defender för Endpoint.

3. Händelser som registreras av tjänsten visas i loggen. I följande tabell finns en lista över händelser som registrerats av tjänsten.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>Händelse-ID</th>
<th>Meddelande</th>
<th>Beskrivning</th>
<th>Åtgärd</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender för slutpunktstjänsten startades (version <code>variable</code> ).</td>
<td>Inträffar vid start av system, stängs av och under registrering.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>2</td>
<td>Microsoft Defender för Endpoint-tjänsten stängs av.</td>
<td>Inträffar när enheten stängs av eller stängs av.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft Defender för Slutpunkt-tjänsten kunde inte startas. Felkod: <code>variable</code> .</td>
<td>Tjänsten har inte startar.</td>
<td>Granska andra meddelanden för att fastställa möjliga orsaker och felsökningssteg.</td>
</tr>
<tr>
<td>4</td>
<td>Microsoft Defender för Slutpunkt-tjänsten kontaktade servern på <code>variable</code> .</td>
<td>Variabel = URL för Defender för slutpunktsbearbetningsservrar.<br>
Den här URL:en matchar den som visas i brandväggen eller nätverksaktiviteten.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>5</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte ansluta till servern hos <code>variable</code> .</td>
<td>Variabel = URL för Defender för slutpunktsbearbetningsservrar.<br>
Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</td>
<td>Kontrollera anslutningen till URL:en. Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></td>
</tr>
<tr>
<td>6</td>
<td>Microsoft Defender för Slutpunkt-tjänsten är inte onboarded och inga onboarding-parametrar hittades.</td>
<td>Enheten fungerade inte korrekt och rapporterar inte till portalen.</td>
<td>Onboarding måste köras innan tjänsten startas.<br>
Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>7</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte läsa onboarding-parametrarna. Fel: <code>variable</code> .</td>
<td>Variabel = detaljerad felbeskrivning. Enheten fungerade inte korrekt och rapporterar inte till portalen.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>8</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte rensa konfigurationen. Felkod: <code>variable</code> .</td>
<td><b>Under introduktionen:</b> Det gick inte att rensa konfigurationen av tjänsten under onboarding. Onboarding-processen fortsätter. <br><br> <b>Under offboarding:</b> Tjänsten kunde inte rensa konfigurationen under offboarding. Offboarding-processen har slutförts men tjänsten fortsätter att köras.
 </td>
<td><b>Introduktion:</b> Ingen åtgärd krävs. <br><br> <b>Offboarding:</b> Starta om systemet.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>9</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte ändra starttypen. Felkod: <code>variable</code> .</td>
<td><b>Under introduktionen:</b> Enheten fungerade inte korrekt och rapporterar inte till portalen. <br><br><b>Under offboarding:</b> Det gick inte att ändra tjänstens starttyp. Offboarding-processen fortsätter. </td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>10</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte spara informationen om introduktionen. Felkod: <code>variable</code> .</td>
<td>Enheten fungerade inte korrekt och rapporterar inte till portalen.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>11</td>
<td>Registrering eller om onboarding av Defender för slutpunktstjänsten har slutförts.</td>
<td>Enheten var korrekt igång.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.<br>
Det kan ta flera timmar innan enheten visas i portalen.</td>
</tr>
<tr>
<td>12</td>
<td>Standardkonfigurationen kunde inte användas i Microsoft Defender för Endpoint.</td>
<td>Det gick inte att använda standardkonfigurationen för tjänsten.</td>
<td>Det här felet bör åtgärdas efter en kort tidsperiod.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender för slutpunktens enhets-ID beräknat: <code>variable</code> .</td>
<td>Normal driftprocess.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>15</td>
<td>Microsoft Defender för Slutpunkt kan inte starta kommandokanalen med URL: <code>variable</code> .</td>
<td>Variabel = URL för Defender för slutpunktsbearbetningsservrar.<br>
Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</td>
<td>Kontrollera anslutningen till URL:en. Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></td>
</tr>
<tr>
<td>17</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte ändra plats för anslutna användarupplevelser och telemetritjänster. Felkod: <code>variable</code> .</td>
<td>Ett fel uppstod med Windows-telemetritjänsten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a><br>
Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>18</td>
<td>OOBE (Välkommen i Windows) har slutförts.</td>
<td>Tjänsten startar först när Windows-uppdateringarna har installerats.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Välkommen i Windows) har ännu inte slutförts.</td>
<td>Tjänsten startar först när Windows-uppdateringarna har installerats.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.<br>
Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</td>
</tr>
<tr>
<td>20</td>
<td>Det går inte att vänta på att OOBE (Välkommen i Windows) ska slutföras. Felkod: <code>variable</code> .</td>
<td>Internt fel.</td>
<td>Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender för Slutpunkt-tjänsten kunde inte återställa hälsostatus i registret. Felkod: <code>variable</code> .</td>
<td>Enheten fungerade inte korrekt.
Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte ange registreringsstatus i registret. Felkod: <code>variable</code> .</td>
<td>Enheten fungerade inte korrekt.<br>
Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte aktivera SENSE-läge i Microsoft Defender Antivirus. Onboarding-processen misslyckades. Felkod: <code>variable</code> .</td>
<td>Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a><br>
Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</td>
</tr>
<tr>
<td>28</td>
<td>Microsoft Defender för slutpunktsanslutna användarupplevelser och registrering av telemetritjänster misslyckades. Felkod: <code>variable</code> .</td>
<td>Ett fel uppstod med Windows-telemetritjänsten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a><br>
Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>29</td>
<td>Det gick inte att läsa parametrarna för offboarding. Feltyp: %1, Felkod: %2, Beskrivning: %3 </td>
<td>Händelsen inträffar när systemet inte&#39;av parametrarna för offboarding.</td>
<td>Kontrollera att enheten har internetanslutning och kör sedan hela offboardingprocessen igen. Kontrollera att offboarding-paketet inte har gått ut.</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte inaktivera SENSE-läge i Microsoft Defender Antivirus. Felkod: <code>variable</code> .</td>
<td>Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</td>
<td>Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter</a><br>
Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</td>
</tr>
<tr>
<td>31</td>
<td>Microsoft Defender för slutpunktsanslutna användarupplevelser och avregistrering av telemetritjänsten misslyckades. Felkod: <code>variable</code> .</td>
<td>Ett fel uppstod med Windows-telemetritjänsten under onboarding. Offboarding-processen fortsätter.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Sök efter fel med Windows-telemetritjänsten</a>.</td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte begära att stoppa sig själv efter offboardingprocessen. Felkod: %1</td>
<td>Ett fel uppstod vid offboarding.</td>
<td>Starta om enheten.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte spara SENSE GUID. Felkod: <code>variable</code> .</td>
<td>En unik identifierare används för att representera varje enhet som rapporterar till portalen.<br>
Om identifieraren inte finns kvar kan samma enhet visas två gånger i portalen.</td>
<td>Kontrollera registerbehörigheter på enheten för att säkerställa att tjänsten kan uppdatera registret.</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender för Slutpunkt-tjänsten kunde inte lägga till sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten, vilket ledde till att onboarding-processen misslyckades. Felkod: <code>variable</code> .</td>
<td>Ett fel uppstod med Windows-telemetritjänsten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a><br>
Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt. Försök distribuera konfigurationspaketen igen.<br>
Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender för slutpunktstjänsten kunde inte ta bort sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten. Felkod: <code>variable</code> .</td>
<td>Ett fel uppstod med Windows-telemetritjänsten under offboarding. Offboarding-processen fortsätter.
</td>
<td>Sök efter fel med Windows-diagnostikdatatjänsten.</td>
</tr>
<tr>
<td>36</td>
<td>Microsoft Defender för slutpunktsanslutna användarupplevelser och telemetritjänstregistrering lyckades. Slutförandekod: <code>variable</code> .</td>
<td>Registrering av Defender för slutpunkt med den anslutna användarupplevelsen och telemetritjänsten har slutförts.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender för slutpunkt En modul kommer att överskrida sin kvot. Modul: %1, Kvot: {%2} {%3}, Procentandel av kvotens användning: %4.</td>
<td>Enheten har nästan använt sin tilldelade kvot under det aktuella 24-timmarsfönstret. Den kommer att begränsas.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>38</td>
<td>Nätverksanslutningen identifieras som låg. Microsoft Defender för Endpoint kontaktar servern var %1:e minut. Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</td>
<td>Enheten använder ett nätverk med datatrafik/betalt nätverk och kontaktar servern mer sällan.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>39</td>
<td>Nätverksanslutningen identifieras som normal. Microsoft Defender för Endpoint kontaktar servern var %1:e minut. Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</td>
<td>Enheten använder inte en anslutning med databetalda data och kontaktar servern som vanligt.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>40</td>
<td>Batteritillståndet identifieras som låg. Microsoft Defender för Endpoint kontaktar servern var %1:e minut. Batteritillstånd: %2.</td>
<td>Enheten har låg batterinivå och kontaktar servern mindre ofta.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>41</td>
<td>Batteritillståndet identifieras som normalt. Microsoft Defender för Endpoint kontaktar servern var %1:e minut. Batteritillstånd: %2.</td>
<td>Enheten har inte låg batterinivå och kontaktar servern som vanligt.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender för slutpunktskomponenten kunde inte utföra någon åtgärd. Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsmeddelande: %4</td>
<td>Internt fel. Det gick inte att starta tjänsten.</td>
<td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender för slutpunktskomponenten kunde inte utföra någon åtgärd. Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsfel: %4, Undantagsmeddelande: %5</td>
<td>Internt fel. Det gick inte att starta tjänsten.</td>
<td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding av Defender för slutpunktstjänsten har slutförts.</td>
<td>Tjänsten var offboarded.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>45</td>
<td>Det gick inte att registrera och starta händelsespårningssessionen [%1]. Felkod: %2</td>
<td>Ett fel uppstod vid start av tjänsten vid skapandet av ETW-session. Detta orsakade startfel för tjänsten.</td>
<td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
<td>46</td>
<td>Det gick inte att registrera och starta händelsespårningssessionen [%1] på grund av brist på resurser. Felkod: %2. Det beror troligen på att det finns för många sessioner med aktiva händelsespårningar. Tjänsten kommer att försöka igen om 1 minut.</td>
<td>Ett fel uppstod vid start av tjänsten när ETW-sessionen skulle skapas på grund av brist på resurser. Tjänsten startades och körs, men rapporterar inte en sensorhändelse förrän ETW-sessionen startas.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs. Tjänsten försöker starta sessionen varje minut.</td>
</tr>
<tr>
<td>47</td>
<td>Registrerad och startade händelsespårningssessionen – återställdes efter tidigare misslyckade försök.</td>
<td>Händelsen följer den föregående händelsen efter att ETW-sessionen har startar.</td>
<td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
<td>48</td>
<td>Det gick inte att lägga till en provider [%1] i händelsespårningssession [%2]. Felkod: %3. Det innebär att händelser från den här leverantören inte rapporteras.</td>
<td>Det gick inte att lägga till en leverantör i ETW-sessionen. Därför rapporteras inte leverantörshändelserna.</td>
<td>Kontrollera felkoden. Kontakta support om felet kvarstår.</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>Kommandot ogiltig molnkonfiguration har tagits emot och ignorerats. Version: %1, status: %2, felkod: %3, meddelande: %4</td>
   <td>Fick en ogiltig konfigurationsfil från molntjänsten som ignorerades.</td>
   <td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>50</td>
   <td>Den nya molnkonfigurationen har använts. Version: %1.</td>
   <td>En ny konfiguration från molntjänsten har tillämpats.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>51</td>
   <td>Ny molnkonfiguration kunde inte användas, version: %1. Den senaste kända konfigurationen, version %2, har tillämpats.</td>
   <td>Fick en felaktig konfigurationsfil från molntjänsten. Den senaste kända konfigurationen har använts.</td>
   <td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>52</td>
   <td>Ny molnkonfiguration kunde inte användas, version: %1. Det gick inte heller att använda den senaste kända konfigurationen, version %2. Standardkonfigurationen har tillämpats.</td>
   <td>Fick en felaktig konfigurationsfil från molntjänsten. Det gick inte att använda den senaste kända konfigurationen – och standardkonfigurationen tillämpades.</td>
   <td>Tjänsten försöker ladda ned en ny konfigurationsfil inom 5 minuter. Om du inte ser händelsen #50 kontakta support.</td>
</tr>
<tr>
   <td>53</td>
   <td>Molnkonfiguration som lästs in från beständig lagring, version: %1.</td>
   <td>Konfigurationen startades från beständig lagring vid start av tjänsten.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>55</td>
   <td>Det gick inte att skapa automatisk ETW-loggare för säker ETW. Felkod: %1</td>
   <td>Det gick inte att skapa den säkra ETW-loggern.</td>
   <td>Starta om enheten. Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>56</td>
   <td>Det gick inte att ta bort automatisk loggare för Secure ETW. Felkod: %1</td>
   <td>Det gick inte att ta bort den säkra ETW-sessionen på offboarding.</td>
   <td>Kontakta support.</td>
</tr>
<tr>
   <td>57</td>
   <td>Fånga en ögonblicksbild av datorn i felsökningssyfte.</td>
   <td>Ett undersökningspaket, även kallat en forensisk paket, samlas in.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>59</td>
   <td>Startkommando: %1</td>
   <td>Kommandot Startar svarskörning.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>60</td>
   <td>Det gick inte att köra kommandot %1, fel: %2.</td>
   <td>Det gick inte att köra svarskommandot.</td>
   <td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>61</td>
   <td>Parametrar för datainsamlingskommandon är ogiltiga: SasUri: %1, compressionLevel: %2.</td>
   <td>Det gick inte att läsa eller tolka kommandoargumenten för datainsamling (ogiltiga argument).</td>
   <td>Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>62</td>
   <td>Det gick inte att starta den anslutna användarupplevelsen och telemetritjänsten. Felkod: %1</td>
   <td>Anslutna användarupplevelser och den telemetriska tjänsten (diagtrack) kunde inte startas. Telemetri med andra än Microsoft Defender för Slutpunkt-telemetri skickas inte från den här datorn.</td>
   <td>Leta efter fler felsökningstips i händelseloggen: Microsoft-Windows-UniversalTelemetryClient/Operational.</td>
</tr>
<tr>
   <td>63</td>
   <td>Uppdatera starttypen för extern tjänst. Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</td>
   <td>Den externa tjänstens starttyp har uppdaterats.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>64</td>
   <td>Starta den externa tjänsten som stoppas. Namn: %1, utgångskod: %2</td>
   <td>Starta en extern tjänst.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>65</td>
   <td>Det gick inte att läsa in minifilterdrivrutinen Microsoft Security Events Component. Felkod: %1</td>
   <td>Det gick inte att MsSecFlt.sys av filsystems minifilter.</td>
   <td>Starta om enheten. Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>66</td>
   <td>Principuppdatering: Svarstidsläge – %1</td>
   <td>Principen för&C-anslutningsfrekvensen uppdaterades.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>68</td>
   <td>Tjänstens starttyp är oväntad. Tjänstnamn: %1, verklig starttyp: %2, förväntad starttyp: %3</td>
   <td>Oväntad extern tjänststartstyp.</td>
   <td>Åtgärda den externa tjänstens starttyp.</td>
</tr>
<tr>
   <td>69</td>
   <td>Tjänsten stoppas. Tjänstnamn: %1</td>
   <td>Den externa tjänsten stoppas.</td>
   <td>Starta den externa tjänsten.</td>
</tr>
<tr>
   <td>70</td>
   <td>Principuppdatering: Tillåt exempelsamling – %1</td>
   <td>Exempelprincipen för samling har uppdaterats.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>71</td>
   <td>Kommandot Lyckades köra: %1</td>
   <td>Kommandot kördes korrekt.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>72</td>
   <td>Försökte skicka den första fullständiga datorprofilrapporten. Resultatkod: %1</td>
   <td>Endast information.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>73</td>
   <td>Start för plattform: %1</td>
   <td>Endast information.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>74</td>
   <td>Enhetstaggen i registret överskrider längdgränsen. Taggnamn: %2. Längdbegränsning: %1.</td>
   <td>Enhetstaggen överskrider längdgränsen.</td>
   <td>Använd en kortare enhetstagg.</td>
</tr>
<tr>
   <td>81</td>
   <td>Det gick inte att skapa Microsoft Defender för slutpunkt ETW – automatisklogg. Felkod: %1</td>
   <td>Det gick inte att skapa ETW-sessionen.</td>
   <td>Starta om enheten. Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>82</td>
   <td>Det gick inte att ta bort Microsoft Defender för endpoint ETW autologger. Felkod: %1</td>
   <td>Det gick inte att ta bort ETW-sessionen.</td>
   <td>Kontakta support.</td>
</tr>
<tr>
   <td>84</td>
   <td>Ange att Windows Defender Antivirus körs. Tvinga passivt läge: %1, resultatkod: %2.</td>
   <td>Ställa in defender running mode (aktivt eller passivt).</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>85</td>
   <td>Det gick inte att utlösa Microsoft Defender för körbar slutpunkt. Felkod: %1</td>
   <td>Körbar Stjärn senseIR misslyckades.</td>
   <td>Starta om enheten. Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>86</td>
   <td>Starta igen, stoppad extern tjänst som ska vara upp. Namn: %1, utgångskod: %2</td>
   <td>Starta den externa tjänsten igen.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>87</td>
   <td>Det går inte att starta den externa tjänsten. Namn: %1</td>
   <td>Det gick inte att starta den externa tjänsten.</td>
   <td>Kontakta support.</td>
</tr>
<tr>
   <td>88</td>
   <td>Uppdatera starttypen för den externa tjänsten igen. Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</td>
   <td>Uppdaterade starttypen för den externa tjänsten.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>89</td>
   <td>Det går inte att uppdatera starttypen för extern tjänst. Namn: %1, verklig starttyp: %2, förväntad starttyp: %3</td>
   <td>Det går inte att uppdatera starttypen för den externa tjänsten.</td>
   <td>Kontakta support.</td>
</tr>
<tr>
   <td>90</td>
   <td>Det gick inte att konfigurera System Guard Runtime Monitor för att ansluta till molntjänsten i geoområde %1. Felkod: %2</td>
   <td>System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</td>
   <td>Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Kontakta support om det inte är några problem.</td>
</tr>
<tr>
   <td>91</td>
   <td>Det gick inte att ta bort System Guard Runtime Monitor-information för geoområde. Felkod: %1</td>
   <td>System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</td>
   <td>Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Kontakta support om det inte är några problem.</td>
</tr>
<tr>
   <td>92</td>
   <td>Stoppar sändning av sensordatakvot på cyber, eftersom datakvoten överskrids. Återupptar sändningen när kvotperioden går ut. Tillståndsmask: %1</td>
   <td>Överskrid begränsningsgräns.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>93</td>
   <td>Återupptar sändning av sensordata i cybern. Tillståndsmask: %1</td>
   <td>Återuppta sändning av cyberdata.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>94</td>
   <td>Körbar Microsoft Defender för slutpunkt har startat</td>
   <td>Den körbara SenseCE-filen har startat.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>95</td>
   <td>Körbar Microsoft Defender för slutpunkt har avslutats</td>
   <td>Den körbara SenseCE-filen har avslutats.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>96</td>
   <td>Microsoft Defender för Slutpunkt Init har anropats. Resultatkod: %2</td>
   <td>Den körbara SenseCE-filen har kallat MCE-initiering.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>97</td>
   <td>Det finns anslutningsproblem till molnet för DLP-scenariot</td>
   <td>Det finns nätverksanslutningsproblem som påverkar DLP-klassificeringsflödet.</td>
   <td>Kontrollera nätverksanslutningen.</td>
</tr>
<tr>
   <td>98</td>
   <td>Anslutningen till molnet för DLP-scenariot har återställts</td>
   <td>Anslutningen till nätverket återställdes och DLP-klassificeringsflödet kan fortsätta.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>99</td>
   <td>Fel i Sense har uppstått när du kommunicerar med server: (%1). Resultat: (%2)</td>
   <td>Ett kommunikationsfel inträffade.</td>
   <td>Mer information finns i följande händelser i händelseloggen.</td>
</tr>
<tr>
   <td>100</td>
   <td>Körbar Microsoft Defender för slutpunkt kunde inte starta. Felkod: %1</td>
   <td>Det gick inte att starta SenseCE-körbara filer.</td>
   <td>Starta om enheten. Om det här felet kvarstår kontaktar du supporten.</td>
</tr>
<tr>
   <td>102</td>
   <td>Körbar microsoft Defender för slutpunktsnätverksidentifiering och svar har startat</td>
   <td>Körbar SenseNdr har startat.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
<tr>
   <td>103</td>
   <td>Microsoft Defender för slutpunkt nätverksidentifiering och svar körbar fil har avslutats</td>
   <td>Den körbara SenseNdr-filen har avslutats.</td>
   <td>Meddelande om normal användning. ingen åtgärd krävs.</td>
</tr>
</tbody>
</table>

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Relaterade ämnen
- [Registrera Windows 10-enheter](configure-endpoints.md)
- [Konfigurera enhetsproxy och internetanslutningsinställningar](configure-proxy-internet.md)
- [Felsöka Microsoft Defender för Endpoint](troubleshoot-onboarding.md)
