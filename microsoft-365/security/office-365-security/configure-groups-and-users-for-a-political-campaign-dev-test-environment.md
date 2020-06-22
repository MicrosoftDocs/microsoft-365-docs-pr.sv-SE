---
title: Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Sammanfattning: skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d8c315364e9a00a49ad825ef2652ff4e8a7476b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755278"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj

 **Sammanfattning:** skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.

Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö som innehåller förenklade användarkonton och grupper i en lösning för [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Steg 1: skapa en utvecklings-/test miljö för Office 365

I den här fasen får du provprenumerationer för Office 365 E5 och Enterprise Mobility + Security (EMS) E5 för en fiktiv organisation som representerar en politisk kampanj.

Följ anvisningarna i **fas 2** i [Enkel baskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Registrera dig sedan för en utvärderingsprenumeration på EMS E5 och lägg till den i samma organisation som utvärderingsprenumerationen.

1. Om det behövs loggar du in på administrationscentret med autentiseringsuppgifterna för utvärderingsprenumerationens globala administratörskonto. Mer information finns i [Så här loggar du in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Klicka på panelen **Administratör**.

3. På fliken **Microsoft 365 administrationscenter** i webbläsaren klickar du **Fakturering > Köpa tjänster**i det vänstra navigeringsfältet.

4. På sidan **Köpa tjänster** hittar du **Enterprise Mobility + Security E5**-objekt. Håll muspekaren över den och klicka på **Starta kostnadsfri utvärderingsversion**.

5. På sidan **Bekräfta din beställning** väljer du **Prova nu**.

6. På sidan **Beställningskvitto** klickar du **Fortsätt**.

Aktivera sedan EMS E5-licensen för ditt globala administratörskonto.

1. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfältet på fliken **Microsoft 365 administrationscenter** i webbläsaren.

2. Klicka på det globala administratörskontot och klicka sedan på **Redigera** för **Produktlicenser**.

3. I fönstret **Produktlicenser** ställer du in produktlicensen för **Enterprise Mobility + Security E5** till **På**, klickar **Spara** och klickar sedan två gånger på **Stäng**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Steg 2: skapa och konfigurera Azure Active Directory-grupper (AD)

I den här fasen skapar och konfigurerar du Azure AD-grupper för din kampanj.

Börja med att skapa en uppsättning grupper för en typisk politisk kampanj med Azure-portalen.

1. Gå till Azure-portalen vid [https://portal.azure.com](https://portal.azure.com) på en separat flik i webbläsaren. Om det behövs loggar du in med inloggningsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration av Office 365 E5.

2. Klicka på **Azure Active Directory > Användare och grupper > Alla grupper** i Azure-portalen.

3. Utför följande steg för varje gruppnamn i den här listan:

   - Seniora och strategisk personal

   - IT-personal

   - Analyspersonal

   - Normal baspersonal

   - Driftspersonal

   - Fältpersonal

1. Gå till bladet **Alla grupper** och klicka på **+ Ny grupp**.

2. Skriv gruppens namn från listan i **namn**.

3. Välj **Dynamiska användare** i **Medlemskap**.

4. Klicka på **Ja** för att **Aktivera Office-funktioner**.

5. Klicka på **Lägg till dynamisk fråga**.

6. I **Lägg till användare där** väljer du **Avdelning**.

7. I nästa fält väljer du **Är lika med**.

8. I nästa fält skriver du gruppnamnet från listan.

9. Klicka på **Lägg till fråga**och klicka sedan på **Skapa**.

10. Klicka på **Användare och grupper – Alla grupper**.

Därefter konfigurerar du grupperna så att medlemmarna automatiskt tilldelas Office 365 E5- och EMS E5-licenser.

1. Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.

2. Välj **Enterprise Mobility + Security E5** och **Office 365 Enterprise E5** och klicka sedan på **+ Tilldela**.

3. I bladet **Tilldela licens** klickar du på **Användare och grupper**.

4. I listan med grupper väljer du följande:

   - Analyspersonal

   - Fältpersonal

   - IT-personal

   - Driftspersonal

   - Normal baspersonal

   - Seniora och strategisk personal

5. Klicka **Välj** och klicka sedan **Tilldela**.

6. Stäng fliken Azure Portal i webbläsaren.

## <a name="phase-3-add-your-user-accounts"></a>Steg 3: lägga till användarkonton

I den här fasen lägger du till exempelanvändarkonton för din politiska kampanj.

Först [Anslut med Azure Active Directory PowerShell för diagrammodulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Därefter fyller du i ditt organisationsnamn, din plats och ett vanligt lösenord och kör dessa kommandon från PowerShells kommandotolk eller integrerat skriptmiljö (ISE):

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> Användningen av ett vanligt lösenord här är för Automatisering och enklare konfiguration för en utvecklings-/testmiljö. Detta rekommenderas inte för produktionsprenumerationer. När du loggar in med vart och ett av dessa nya användarkonton kommer du att uppmanas att ändra lösenordet.

Använd de här anvisningarna för att kontrollera att dynamiska gruppmedlemskap och gruppbaserad licensiering fungerar som de ska.

1. På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Administratör**.

2. Klicka **Användare**under den nya fliken **administrationscentret för Microsoft 365** i webbläsaren.

3. I listan över användare klickar du på **Kandidat**.

4. Kontrollera att du har en lista över egenskaperna för **Kandidat** användarkonto:

   - Det är en medlem i gruppen **Seniora och strategisk personal** (i **Gruppmedlemskap**).

   - Den har tilldelats **Enterprise Mobility + Security E5**- och **Office 365 Enterprise E5**-licenser (i **Produktlicenser**).

5. Stäng användarkontofönstret för **Kandidat**.

## <a name="record-values-for-future-reference"></a>Skriv upp värden för framtida referens

Skriv upp dessa värden för att arbeta med utvärderingsprenumerationer för Office 365 och EMS för denna utvecklings-/testmiljö:

- Organisationens namn för utvärderingsversionen: ![Understrykning](../../media/Common-Images/TableLine.png)

  Till exempel är ”contoso” organisationsnamnet för utvärderingsprenumerationen i domännamnet contoso.onmicrosoft.com.

- Det globala administratörsnamnet: ![Understrykning](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Anteckna lösenordet för kontot och det vanliga första lösenordet för de andra användarkontona på en säker plats.

## <a name="next-step"></a>Nästa steg

Skapa fyra olika typer av SharePoint Online-gruppwebbplatser i den här utvecklings-/testmiljön med [Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>Se även

[Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[TLG (Test Lab Guides) för integrering med molntjänster](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Integrering av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
