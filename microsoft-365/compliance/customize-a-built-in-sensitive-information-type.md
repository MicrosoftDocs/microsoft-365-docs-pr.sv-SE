---
title: Anpassa en inbyggd typ av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skapar en anpassad typ av känslig information som tillåter dig att använda regler som uppfyller organisationens behov.
ms.openlocfilehash: da79c525a268ff686c2edaf777cedf447335ed27
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227037"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="34e65-103">Anpassa en inbyggd typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="34e65-103">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="34e65-104">När du söker efter känslig information i innehåll måste du beskriva den informationen i en så kallad  *regel*  .</span><span class="sxs-lookup"><span data-stu-id="34e65-104">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  .</span></span> <span data-ttu-id="34e65-105">I dataförlustskydd (DLP) ingår regler för de vanligaste typerna av känslig information som du kan använda direkt.</span><span class="sxs-lookup"><span data-stu-id="34e65-105">Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away.</span></span> <span data-ttu-id="34e65-106">Om du vill använda de här reglerna måste du inkludera dem i en princip.</span><span class="sxs-lookup"><span data-stu-id="34e65-106">To use these rules, you have to include them in a policy.</span></span> <span data-ttu-id="34e65-107">Du kanske vill justera de inbyggda reglerna efter organisationens specifika behov, och det kan du göra genom att skapa en anpassad typ av känslig information.</span><span class="sxs-lookup"><span data-stu-id="34e65-107">You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type.</span></span> <span data-ttu-id="34e65-108">Det här avsnittet visar hur du anpassar XML-filen som innehåller den befintliga regelsamlingen för att identifiera ett större urval möjliga kreditkortsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="34e65-108">This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span>

<span data-ttu-id="34e65-109">Du kan använda det här exemplet och tillämpa det på andra inbyggda typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="34e65-109">You can take this example and apply it to other built-in sensitive information types.</span></span> <span data-ttu-id="34e65-110">Du hittar en lista med vanliga typer av känslig information och XML-definitioner under [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="34e65-110">For a list of default sensitive information types and XML definitions, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="34e65-111">Exportera XML-filen för de aktuella reglerna</span><span class="sxs-lookup"><span data-stu-id="34e65-111">Export the XML file of the current rules</span></span>

<span data-ttu-id="34e65-112">Om du vill exportera XML-koden måste du [ansluta till Säkerhets- och efterlevnadscenter via PowerShell-fjärranvändning.](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="34e65-112">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](/powershell/exchange/connect-to-scc-powershell).</span></span>

1. <span data-ttu-id="34e65-113">I PowerShell anger du följande för att visa organisationens regler på skärmen.</span><span class="sxs-lookup"><span data-stu-id="34e65-113">In the PowerShell, type the following to display your organization's rules on screen.</span></span> <span data-ttu-id="34e65-114">Om du inte har skapat egna regler visas bara de inbyggda standardreglerna som kallas för Regelpaket för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34e65-114">If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. <span data-ttu-id="34e65-115">Lagra organisationens regler i en variabel genom att skriva följande.</span><span class="sxs-lookup"><span data-stu-id="34e65-115">Store your organization's rules in a variable by typing the following.</span></span> <span data-ttu-id="34e65-116">Om du lagrar något i en variabel blir det lätt tillgängligt senare i ett format som fungerar med fjärrkommandon i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34e65-116">Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>

   ```powershell
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```

3. <span data-ttu-id="34e65-117">Gör en formaterad XML-fil med alla dessa data genom att skriva följande.</span><span class="sxs-lookup"><span data-stu-id="34e65-117">Make a formatted XML file with all that data by typing the following.</span></span> <span data-ttu-id="34e65-118">( `Set-content` är den del av cmdleten som skriver XML till filen.)</span><span class="sxs-lookup"><span data-stu-id="34e65-118">(`Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span>

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="34e65-119">Kontrollera att du använder den filplats där regelpaketet faktiskt lagras.</span><span class="sxs-lookup"><span data-stu-id="34e65-119">Make sure that you use the file location where your rule pack is actually stored.</span></span> <span data-ttu-id="34e65-120">`C:\custompath\` är en platshållare.</span><span class="sxs-lookup"><span data-stu-id="34e65-120">`C:\custompath\` is a placeholder.</span></span>

## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="34e65-121">Hitta den regel som du vill ändra i XML-filen</span><span class="sxs-lookup"><span data-stu-id="34e65-121">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="34e65-122">Ovanstående cmdletar exporterade hela *regelsamlingen*, som innehåller de standardregler vi tillhandahåller.</span><span class="sxs-lookup"><span data-stu-id="34e65-122">The cmdlets above exported the entire *rule collection*, which includes the default rules we provide.</span></span> <span data-ttu-id="34e65-123">Därefter måste du söka specifikt efter den regeln för kreditkortsnummer som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="34e65-123">Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span>

1. <span data-ttu-id="34e65-124">Använd en textredigerare för att öppna XML-filen som du exporterade i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="34e65-124">Use a text editor to open the XML file that you exported in the previous section.</span></span>

2. <span data-ttu-id="34e65-125">Rulla ned till `<Rules>`-taggen, som är början på avsnittet som innehåller DLP-reglerna.</span><span class="sxs-lookup"><span data-stu-id="34e65-125">Scroll down to the `<Rules>` tag, which is the start of the section that contains the DLP rules.</span></span> <span data-ttu-id="34e65-126">Eftersom den här XML-filen innehåller informationen för hela regelsamlingen innehåller den annan information längst upp som du behöver bläddra förbi för att komma till reglerna.</span><span class="sxs-lookup"><span data-stu-id="34e65-126">Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.</span></span>

3. <span data-ttu-id="34e65-127">Leta efter *Func_credit_card* för att hitta regeldefinitionen för kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-127">Look for *Func_credit_card* to find the Credit Card Number rule definition.</span></span> <span data-ttu-id="34e65-128">I XML kan regelnamn inte innehålla blanksteg, så blankstegen ersätts vanligtvis med understreck och regelnamn förkortas ibland.</span><span class="sxs-lookup"><span data-stu-id="34e65-128">In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated.</span></span> <span data-ttu-id="34e65-129">Ett exempel på detta är regeln för amerikanska socialförsäkringsnummer som förkortas till _SSN_.</span><span class="sxs-lookup"><span data-stu-id="34e65-129">An example of this is the U.S. Social Security number rule, which is abbreviated _SSN_.</span></span> <span data-ttu-id="34e65-130">XML-koden för regeln för kreditkortsnummer bör se ut som i följande kodexempel.</span><span class="sxs-lookup"><span data-stu-id="34e65-130">The Credit Card Number rule XML should look like the following code sample.</span></span>

   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

<span data-ttu-id="34e65-131">Nu när du har hittat regeldefinitionen för kreditkortsnummer i XML kan du anpassa regelns XML-kod så att den uppfyller dina behov.</span><span class="sxs-lookup"><span data-stu-id="34e65-131">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs.</span></span> <span data-ttu-id="34e65-132">En uppdatering av XML-definitioner finns i [Termordlistan](#term-glossary) i slutet av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="34e65-132">For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.</span></span>

## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="34e65-133">Ändra XML-koden och skapa en ny typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="34e65-133">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="34e65-134">Först måste du skapa en ny typ av känslig information eftersom du inte kan ändra själva standardreglerna.</span><span class="sxs-lookup"><span data-stu-id="34e65-134">First, you need to create a new sensitive information type because you can't directly modify the default rules.</span></span> <span data-ttu-id="34e65-135">Du kan göra en mängd olika saker med anpassade typer av känslig information, vilket beskrivs i [Skapa en anpassad typ av känslig information i Säkerhets- och efterlevnadscenter PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="34e65-135">You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="34e65-136">I det här exemplet kommer vi att hålla det enkelt och bara ta bort samarbetsbevis och lägga till nyckelord till regeln för kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-136">For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>

<span data-ttu-id="34e65-137">Alla XML-regeldefinitioner bygger på följande allmänna mall.</span><span class="sxs-lookup"><span data-stu-id="34e65-137">All XML rule definitions are built on the following general template.</span></span> <span data-ttu-id="34e65-138">Du måste kopiera och klistra in XML-definitionen för kreditkortsnummer i mallen, ändra vissa värden (observera “.</span><span class="sxs-lookup"><span data-stu-id="34e65-138">You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ".</span></span> <span data-ttu-id="34e65-139">.</span><span class="sxs-lookup"><span data-stu-id="34e65-139">.</span></span> <span data-ttu-id="34e65-140">."</span><span class="sxs-lookup"><span data-stu-id="34e65-140">."</span></span> <span data-ttu-id="34e65-141">platshållarna i följande exempel) och överför sedan den ändrade XML-koden som en ny regel som kan användas i principer.</span><span class="sxs-lookup"><span data-stu-id="34e65-141">placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." />
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
   <!-- Paste the Credit Card Number rule definition here.-->
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

<span data-ttu-id="34e65-142">Nu har du något som liknar följande XML-kod.</span><span class="sxs-lookup"><span data-stu-id="34e65-142">Now, you have something that looks similar to the following XML.</span></span> <span data-ttu-id="34e65-143">Eftersom regelpaket och regler identifieras via sina unika GUID:er behöver du skapa två GUID:er, en för regelpaketet och en för att ersätta GUID:en för regeln för kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-143">Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule.</span></span> <span data-ttu-id="34e65-144">GUID:en för entitets-ID i följande kodexempel är GUID:en för vår inbyggda regeldefinition, som du måste ersätta med en ny.</span><span class="sxs-lookup"><span data-stu-id="34e65-144">The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.</span></span> <span data-ttu-id="34e65-145">Det finns flera sätt att generera GUID:er, men det kan du enkelt göra i PowerShell genom att skriva **[guid]::NewGuid()**.</span><span class="sxs-lookup"><span data-stu-id="34e65-145">There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span>

```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>

 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f">
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="34e65-146">Ta bort kravet på samarbetsbevis från en typ av känslig information</span><span class="sxs-lookup"><span data-stu-id="34e65-146">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="34e65-147">Nu när du har en ny typ av känslig information som du kan ladda upp till Säkerhets- &amp; och efterlevnadscenter är nästa steg att göra regeln mer specifik.</span><span class="sxs-lookup"><span data-stu-id="34e65-147">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific.</span></span> <span data-ttu-id="34e65-148">Ändra regeln så att den bara söker ett 16-siffrigt tal som passerar kontrollsumman men inte kräver ytterligare (samarbets)bevis, till exempel nyckelord.</span><span class="sxs-lookup"><span data-stu-id="34e65-148">Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence, like keywords.</span></span> <span data-ttu-id="34e65-149">För att göra detta måste du ta bort den del av XML-datan som söker efter ett samarbetsbevis.</span><span class="sxs-lookup"><span data-stu-id="34e65-149">To do this, you need to remove the part of the XML that looks for corroborative evidence.</span></span> <span data-ttu-id="34e65-150">Samarbetsbevis är mycket användbart för att minska falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="34e65-150">Corroborative evidence is very helpful in reducing false positives.</span></span> <span data-ttu-id="34e65-151">I det här fallet finns det vanligtvis vissa nyckelord eller ett utgångsdatum i närheten av kreditkortsnumret.</span><span class="sxs-lookup"><span data-stu-id="34e65-151">In this case there are usually certain keywords or an expiration date near the credit card number.</span></span> <span data-ttu-id="34e65-152">Om du tar bort dessa bevis bör du också justera hur säker du är på att du har hittat ett kreditkortsnummer genom att sänka `confidenceLevel`, vilket är 85 i exemplet.</span><span class="sxs-lookup"><span data-stu-id="34e65-152">If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>

```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="34e65-153">Söka efter nyckelord som är specifika för din organisation</span><span class="sxs-lookup"><span data-stu-id="34e65-153">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="34e65-154">Du kanske vill att ett samarbetsbevis krävs men vill ha olika eller ytterligare nyckelord, och du kanske vill ändra var du söker efter dessa bevis.</span><span class="sxs-lookup"><span data-stu-id="34e65-154">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence.</span></span> <span data-ttu-id="34e65-155">Du kan justera  `patternsProximity` för att expandera eller förminska fönstret för att få samarbetsbevis kring det 16-siffriga talet.</span><span class="sxs-lookup"><span data-stu-id="34e65-155">You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number.</span></span> <span data-ttu-id="34e65-156">Om du vill lägga till egna nyckelord måste du definiera en nyckelordslista och referera till den i regeln.</span><span class="sxs-lookup"><span data-stu-id="34e65-156">To add your own keywords, you need to define a keyword list and reference it within your rule.</span></span> <span data-ttu-id="34e65-157">I följande XML-data läggs nyckelorden “företagskort” och “Contoso-kort” till så att alla meddelanden som innehåller dessa fraser inom 150 tecken från ett kreditkortsnummer identifieras som kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-157">The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span>

```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a><span data-ttu-id="34e65-158">Ladda upp regeln</span><span class="sxs-lookup"><span data-stu-id="34e65-158">Upload your rule</span></span>

<span data-ttu-id="34e65-159">Gör följande om du vill ladda upp regeln.</span><span class="sxs-lookup"><span data-stu-id="34e65-159">To upload your rule, you need to do the following.</span></span>

1. <span data-ttu-id="34e65-160">Spara den som en .xml-fil med Unicode-kodning.</span><span class="sxs-lookup"><span data-stu-id="34e65-160">Save it as an .xml file with Unicode encoding.</span></span> <span data-ttu-id="34e65-161">Det här är viktigt eftersom regeln inte fungerar om filen sparas med en annan kodning.</span><span class="sxs-lookup"><span data-stu-id="34e65-161">This is important because the rule won't work if the file is saved with a different encoding.</span></span>

2. [<span data-ttu-id="34e65-162">Ansluta till Säkerhets- och efterlevnadscenter via PowerShell-fjärranvändning.</span><span class="sxs-lookup"><span data-stu-id="34e65-162">Connect to the Security and Compliance Center via Remote PowerShell.</span></span>](/powershell/exchange/connect-to-scc-powershell)

3. <span data-ttu-id="34e65-163">Skriv följande i PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34e65-163">In the PowerShell, type the following.</span></span>

   ```powershell
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="34e65-164">Kontrollera att du använder den filplats där regelpaketet faktiskt lagras.</span><span class="sxs-lookup"><span data-stu-id="34e65-164">Make sure that you use the file location where your rule pack is actually stored.</span></span>  <span data-ttu-id="34e65-165">`C:\custompath\` är en platshållare.</span><span class="sxs-lookup"><span data-stu-id="34e65-165">`C:\custompath\` is a placeholder.</span></span>

4. <span data-ttu-id="34e65-166">Bekräfta genom att skriva Y och sedan trycka på **Retur**.</span><span class="sxs-lookup"><span data-stu-id="34e65-166">To confirm, type Y, and then press **Enter**.</span></span>

5. <span data-ttu-id="34e65-167">Kontrollera att den nya regeln har laddats upp och dess visningsnamn genom att skriva:</span><span class="sxs-lookup"><span data-stu-id="34e65-167">Verify that your new rule was uploaded and its display name by typing:</span></span>

   ```powershell
   Get-DlpSensitiveInformationType
   ```

<span data-ttu-id="34e65-168">Om du vill börja använda den nya regeln för att identifiera känslig information måste du lägga till regeln i en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="34e65-168">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy.</span></span> <span data-ttu-id="34e65-169">Mer information om hur du lägger till regeln i en princip finns i [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="34e65-169">To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>

## <a name="term-glossary"></a><span data-ttu-id="34e65-170">Termordlista</span><span class="sxs-lookup"><span data-stu-id="34e65-170">Term glossary</span></span>

<span data-ttu-id="34e65-171">Det här är definitionerna av de termer som du stötte på under denna procedur.</span><span class="sxs-lookup"><span data-stu-id="34e65-171">These are the definitions for the terms you encountered during this procedure.</span></span>

|<span data-ttu-id="34e65-172">**Villkor**</span><span class="sxs-lookup"><span data-stu-id="34e65-172">**Term**</span></span>|<span data-ttu-id="34e65-173">**Definition**</span><span class="sxs-lookup"><span data-stu-id="34e65-173">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="34e65-174">Entitet</span><span class="sxs-lookup"><span data-stu-id="34e65-174">Entity</span></span>|<span data-ttu-id="34e65-175">Entiteter är det som vi kallar typer av känslig information, till exempel kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-175">Entities are what we call sensitive information types, such as credit card numbers.</span></span> <span data-ttu-id="34e65-176">Varje entitet har en unik GUID som ID.</span><span class="sxs-lookup"><span data-stu-id="34e65-176">Each entity has a unique GUID as its ID.</span></span> <span data-ttu-id="34e65-177">Om du kopierar en GUID och söker efter den i XML-koden hittar du XML-regeldefinitionen och alla lokaliserade översättningar av den XML-regeln.</span><span class="sxs-lookup"><span data-stu-id="34e65-177">If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule.</span></span> <span data-ttu-id="34e65-178">Du kan också hitta den här definitionen genom att hitta GUID:en för översättningen och sedan söka efter denna GUID.</span><span class="sxs-lookup"><span data-stu-id="34e65-178">You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="34e65-179">Funktioner</span><span class="sxs-lookup"><span data-stu-id="34e65-179">Functions</span></span>|<span data-ttu-id="34e65-180">XML-filen refererar till  `Func_credit_card`, som är en funktion i kompilerad kod.</span><span class="sxs-lookup"><span data-stu-id="34e65-180">The XML file references  `Func_credit_card`, which is a function in compiled code.</span></span> <span data-ttu-id="34e65-181">Funktioner används för att köra komplexa reguljära uttryck och verifiera att kontrollsummorna matchar för våra inbyggda regler.) Eftersom det här händer i koden visas inte vissa av variablerna i XML-filen.</span><span class="sxs-lookup"><span data-stu-id="34e65-181">Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="34e65-182">IdMatch</span><span class="sxs-lookup"><span data-stu-id="34e65-182">IdMatch</span></span>|<span data-ttu-id="34e65-183">Det här är identifieraren som mönstret försöker matcha – till exempel ett kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="34e65-183">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="34e65-184">Nyckelordslistor</span><span class="sxs-lookup"><span data-stu-id="34e65-184">Keyword lists</span></span>|<span data-ttu-id="34e65-185">XML-filen refererar även till  `keyword_cc_verification` och  `keyword_cc_name`, som är listor med nyckelord, från vilka vi letar efter matchningar inom  `patternsProximity` för entiteten.</span><span class="sxs-lookup"><span data-stu-id="34e65-185">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity.</span></span> <span data-ttu-id="34e65-186">Dessa visas för närvarande inte i XML-koden.</span><span class="sxs-lookup"><span data-stu-id="34e65-186">These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="34e65-187">Mönster</span><span class="sxs-lookup"><span data-stu-id="34e65-187">Pattern</span></span>|<span data-ttu-id="34e65-188">Mönstret innehåller en lista över vad typen av känslig information söker efter.</span><span class="sxs-lookup"><span data-stu-id="34e65-188">The pattern contains the list of what the sensitive type is looking for.</span></span> <span data-ttu-id="34e65-189">Det omfattar nyckelord, reguljära uttryck och interna funktioner som utför uppgifter som att verifiera kontrollsummor.</span><span class="sxs-lookup"><span data-stu-id="34e65-189">This includes keywords, regexes, and internal functions, which perform tasks like verifying checksums.</span></span> <span data-ttu-id="34e65-190">Typer av känslig information kan ha flera mönster med unik konfidens.</span><span class="sxs-lookup"><span data-stu-id="34e65-190">Sensitive information types can have multiple patterns with unique confidences.</span></span> <span data-ttu-id="34e65-191">Det här är användbart när du skapar en typ av känslig information som ger hög konfidens om ett samarbetsbevis påträffas och lägre eller ingen konfidens om inget samarbetsbevis påträffas.</span><span class="sxs-lookup"><span data-stu-id="34e65-191">This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="34e65-192">Mönstret confidenceLevel</span><span class="sxs-lookup"><span data-stu-id="34e65-192">Pattern confidenceLevel</span></span>|<span data-ttu-id="34e65-193">Det här är konfidensnivån som DLP-motorn hittade en matchning för.</span><span class="sxs-lookup"><span data-stu-id="34e65-193">This is the level of confidence that the DLP engine found a match.</span></span> <span data-ttu-id="34e65-194">Den här konfidensnivån associeras med en matchning för mönstret om kraven för mönstret uppfylls.</span><span class="sxs-lookup"><span data-stu-id="34e65-194">This level of confidence is associated with a match for the pattern if the pattern's requirements are met.</span></span> <span data-ttu-id="34e65-195">Det här är det konfidensmått som du bör välja när du använder e-postflödesregler för Exchange (även kallade transportregler).</span><span class="sxs-lookup"><span data-stu-id="34e65-195">This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="34e65-196">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="34e65-196">patternsProximity</span></span>|<span data-ttu-id="34e65-197">När vi hittar det som liknar ett mönster för kreditkortsnummer är  `patternsProximity` den närhet till det talet där vi söker efter samarbetsbevis.</span><span class="sxs-lookup"><span data-stu-id="34e65-197">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="34e65-198">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="34e65-198">recommendedConfidence</span></span>|<span data-ttu-id="34e65-199">Det här är den konfidensnivå som vi rekommenderar för den här regeln.</span><span class="sxs-lookup"><span data-stu-id="34e65-199">This is the confidence level we recommend for this rule.</span></span> <span data-ttu-id="34e65-200">Den rekommenderade konfidensen gäller för entiteter och tillhörigheter.</span><span class="sxs-lookup"><span data-stu-id="34e65-200">The recommended confidence applies to entities and affinities.</span></span> <span data-ttu-id="34e65-201">För entiteter utvärderas aldrig det här talet mot  `confidenceLevel` för mönstret.</span><span class="sxs-lookup"><span data-stu-id="34e65-201">For entities, this number is never evaluated against the  `confidenceLevel` for the pattern.</span></span> <span data-ttu-id="34e65-202">Det är bara ett förslag som hjälper dig att välja en konfidensnivå om du vill tillämpa en.</span><span class="sxs-lookup"><span data-stu-id="34e65-202">It's merely a suggestion to help you choose a confidence level if you want to apply one.</span></span> <span data-ttu-id="34e65-203">För tillhörigheter måste  `confidenceLevel` för mönstret vara högre än  `recommendedConfidence` för att en åtgärd för ett e-postflöde ska anropas.</span><span class="sxs-lookup"><span data-stu-id="34e65-203">For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked.</span></span> <span data-ttu-id="34e65-204">`recommendedConfidence` är standardkonfidensnivån som används i e-postflödesregler som anropar en åtgärd.</span><span class="sxs-lookup"><span data-stu-id="34e65-204">The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action.</span></span> <span data-ttu-id="34e65-205">Om du vill kan du manuellt ändra e-postflödesregeln så att den anropas baserat på mönstrets konfidensnivå i stället.</span><span class="sxs-lookup"><span data-stu-id="34e65-205">If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|

## <a name="for-more-information"></a><span data-ttu-id="34e65-206">Mer information</span><span class="sxs-lookup"><span data-stu-id="34e65-206">For more information</span></span>

- [<span data-ttu-id="34e65-207">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="34e65-207">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="34e65-208">Skapa en anpassad känslig informationstyp</span><span class="sxs-lookup"><span data-stu-id="34e65-208">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="34e65-209">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="34e65-209">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)