---
title: Skydda filer i Teams i en utvecklings-/testmiljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Sammanfattning: Skapa grupper som är känsliga och strikt konfidentiella i Microsoft Teams för filer i en utvecklings-/testmiljö.'
ms.openlocfilehash: 1ee543f384903c18754fa848350225799ed0b845
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587562"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a>Skydda filer i Teams i en utvecklings-/testmiljö

I den här artikeln får du stegvisa instruktioner för hur du skapar en utvecklings-/testmiljö som innehåller känsliga och strikt konfidentiella grupper för lösningen [Skydda filer i Microsoft Teams](secure-files-in-teams.md).

![Känsliga och strikt konfidentiella grupper för filer i Microsoft Teams.](../../media/sensitive-highly-confidential-teams-dev-test.png)

Använd utvecklings-/testmiljön för att experimentera och finjustera inställningarna efter dina behov innan du distribuerar grupptyperna i produktion.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill testa känsliga och strikt konfidentiella grupper på ett enkelt sätt med lägsta möjliga krav, följer du anvisningarna i [Enkel baskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).

Om du vill testa känsliga och strikt konfidentiella grupper i ett simulerat företag, följer du anvisningarna i [Synkronisering av lösenordshash](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).

>[!Note]
>Att testa känsliga och strikt konfidentiella grupper kräver inte någon simulerad företagstestmiljö, som innehåller ett simulerat intranät som är kopplat till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det här är ett alternativ där du kan testa känsliga och strikt konfidentiella grupper, samt experimentera i en miljö som motsvarar en vanlig organisation.
>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fas 2: Skapa och konfigurera grupper och användare i Azure Active Directory

I den här fasen skapar och konfigurerar du Azure AD-grupper och användare för din fiktiva organisation.

Börja med att skapa två grupper för en vanlig organisation med Azure-portalen.

1. Gå till Azure-portalen på [https://portal.azure.com](https://portal.azure.com) från en separat flik i webbläsaren. Om det behövs loggar du in med autentiseringsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration eller betalda prenumeration för Microsoft 365 E5.

2. I Azure-portalen klickar du på **Azure Active Directory > Grupper**.

3. Gå till bladet **Grupper – Alla grupper** och klicka på **+ Ny grupp**.

4. På bladet **Grupp**:

   - Välj **Säkerhet** i **Grupptyp**.

   - Skriv **C-Suite** i **Namn**.

   - Välj **Tilldelad** i **Typ av medlemskap**.

5. Klicka på **Skapa** och stäng sedan bladet **Grupp**.

6. Upprepa steg 3–5 för en ny grupp med namnet **Marknadspersonal**.

Nästa steg är att konfigurera automatisk licensiering så att medlemmarna i dina grupper automatiskt tilldelas licenser för dina Microsoft 365- och EMS-prenumerationer.

1. Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.

2. Välj **Microsoft 365 Enterprise E5** i listan och klicka sedan på **Tilldela**.

3. På bladet **Tilldela licens** klickar du på **Användare och grupper**.

4. I listan med grupper väljer du följande:

   - C-Suite

   - Marknadspersonal

5. Klicka på **Välj** och sedan på **Tilldela**.

6. Stäng fliken för Azure-portalen i webbläsaren.

Därefter [ansluter du med Azure Active Directory PowerShell för Graph-modulen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Fyll i organisationsnamn, plats och lösenord samt kör dessa kommandon från PowerShell-kommandotolken eller en ISE (Integrated Script Environment) för att skapa användarkonton och lägga till dem i grupper:

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> Ett gemensamt lösenord används för automatisering och enklare konfiguration i utvecklings-/testmiljön. Självklart rekommenderas detta inte för produktionsprenumerationer.

Använd stegen för att kontrollera att gruppbaserad licensiering fungerar som den ska.

1. På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Administratör**.

2. Klicka på **Användare**under den nya fliken **Administrationscenter för Microsoft 365** i webbläsaren.

3. I listan med användare klickar du på **CEO**.

4. I fönstret med egenskaperna för **CEO**-användarkontot, kontrollerar du att det har tilldelats till **Microsoft 365 Enterprise E5**-licensen (i **Produktlicenser**).

## <a name="phase-3-create-retention-labels"></a>Fas 3: Skapa kvarhållningsetiketter

I den här fasen skapar du kvarhållningsetiketter till de olika säkerhetsnivåerna för dokumentmapparna på underliggande SharePoint-webbplats.

1. Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com) med ditt globala administratörskonto.

2. På fliken **Start – Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Klassifikationer > Etiketter**.

3. Klicka på **Kvarhållningsetiketter > Skapa en etikett**.

4. I fönstret **Namnge din etikett** skriver du **Känslig** i **Namnge din etikett**. Klicka sedan på **Nästa**.

5. Klicka på **Nästa** i fönstret **Filplansbeskrivningar**.

6. I fönstret **Etikettinställningar** anger du vid behov **Kvarhållning** till **På** och klickar sedan på **Nästa**.

7. I fönstret **Granska inställningarna** klickar du på **Skapa etiketten**.

8. Upprepa steg 3–7 för ytterligare en kvarhållningsetikett med namnet **Strikt konfidentiell**.

9. I fönstret **Start > Etiketter** klickar du på **Publicera etiketter**.

10. Klicka på **Välj etiketter att publicera** i fönstret **Välj etiketter att publicera**.

11. I fönstret **Välj etiketter** klickar du på **Lägg till** och markerar alla fyra etiketterna.

12. Klicka på **Klar**.

13. I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.

14. Klicka på **Nästa** i fönstret **Välj platser**.

15. I fönstret **Namnge principen** skriver du **Organisationsexempel** i **Namn** och klickar sedan på **Nästa**.

16. I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.

## <a name="phase-4-create-your-teams"></a>Fas 4: Skapa dina grupper

I den här fasen skapar och konfigurerar du känsliga och strikt konfidentiella grupper i ditt organisationsexempel.

### <a name="sensitive-team-for-marketing-campaigns"></a>Känslig grupp för marknadsföringskampanjer

Skapa en grupp på den känsliga nivån för medlemmarna i marknadsföringsgruppen som ska samarbeta i pågående marknadsföringskampanjer:

1. [Skapa en ny privat grupp](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) med namnet **Marknadsföringskampanjer**.
2. Öppna gruppen **Marknadsföringskampanjer**.
3. I verktygsfältet för gruppen klickar du på **Filer**.
4. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
5. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
6. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
7. Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.

Därefter konfigurerar du dokumentmappen för den underliggande SharePoint-webbplatsen för marknadsföringskampanjer med etiketten Känslig.

1. På fliken **Marknadsföringskampanjer-Start** i webbläsaren klickar du på **Dokument**.
2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 
3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 
4. I **Inställningar-Använd etikett** väljer du **Känslig** och klickar sedan på **Spara**.

Därefter konfigurerar du en princip för dataförlustskydd (DLP) som meddelar användarna när de delar ett dokument med etiketten Känslig på en underliggande SharePoint-webbplats (som inkluderar marknadsföringskampanjplatsen) och som finns utanför organisationen.

1. Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com/) med ditt globala administratörskonto.

2. På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.

3. I fönstret **Start > Dataförlustskydd** klickar du på **Skapa en princip**.

4. I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.

5. I fönstret **Namnge principen** skriver du **Etiketten Känslig, SharePoint-webbplatser** i **Namn**. Klicka sedan på **Nästa**.

6. I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.

7. Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.

8. I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Redigera**.

9. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.

10. I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.

11. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.

12. I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Nästa**.

13. I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.

14. I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.

15. I textrutan skriver du eller klistrar in följande:

    Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den. Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord. Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.

16. Klicka på **OK**.

17. I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Nästa**.

18. I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.

19. I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.

Här är den resulterande konfigurationen för marknadsföringskampanjens grupp.

![Konfiguration av gruppen Marknadsföringskampanjer.](../../media/sensitive-team-config-dev-test.png)

### <a name="company-strategy-team-site"></a>Gruppwebbplats för företagsstrategi

Skapa en strikt konfidentiell grupp för medlemmar i ledningsgruppen som ska samarbeta om företagsstrategin:

1. [Skapa en ny privat grupp](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) med namnet **Företagsstrategi**.
2. Öppna gruppen **Företagsstrategi**.
3. I verktygsfältet för gruppen klickar du på **Filer**.
4. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
5. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
6. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
7. Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.
8. Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.

Därefter konfigurerar du dokumentmappen för företagsstrategins underliggande SharePoint-webbplats med etiketten Strikt konfidentiellt.

1. På fliken **Företagsstrategi-Start** i webbläsaren klickar du på **Dokument**.
2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 
3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 
4. I **Inställningar-Använd etikett** väljer du **Strikt konfidentiellt** och klickar sedan på **Spara**.

Därefter konfigurerar du en DLP-princip som blockerar användare när de delar ett dokument med etiketten Strikt konfidentiellt på en underliggande SharePoint-webbplats (som inkluderar företagsstrategiplatsen) som finns utanför organisationen.

1. Logga in på [efterlevnadsportalen i Microsoft 365](https://compliance.microsoft.com/) som global administratör.

2. På den nya fliken **Efterlevnad i Microsoft 365** i webbläsaren klickar du på **Principer > Dataförlustskydd**.

3. I fönstret **Start > Dataförlustskydd** klickar du på **Skapa en princip**.

4. I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.

5. I fönstret **Namnge principen** skriver du **Etiketten Strikt konfidentiellt, SharePoint-webbplatser** i **Namn**. Klicka sedan på **Nästa**.

6. I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.

7. Inaktivera platserna **Exchange-e-post**, **OneDrive-konton** och **Chatt- och kanalmeddelanden i Teams** i listan med platser och klicka sedan på **Nästa**.

8. I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Redigera**.

9. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och klickar sedan på **Kvarhållningsetiketter**.

10. I fönstret **Kvarhållningsetiketter** klickar du på **Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.

11. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.

12. I fönstret **Anpassa typen av innehåll som du vill skydda** klickar du på **Nästa**.

13. I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.

14. I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.

15. I textrutan skriver du eller klistrar in följande:

    Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den. Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord. Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.

16. Klicka på **OK**.

17. I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.

18. I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.

19. I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.

Använd [anvisningarna](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) till att konfigurera en känslighetsetikett med följande inställningar:

- Etikettnamnet är Företagsstrategi
- Kryptering är aktiverat
- Gruppen Företagsstrategi har samredigeringsbehörighet

Publicera den nya etiketten när du har skapat den. Om du loggar in som medlem i gruppen Företagsstrategi, kommer du att se den nya etiketten i alternativet Känslighet i verktygsfältet Start i Word, Excel och PowerPoint. Välj etiketten Företagsstrategi från alternativet Känslighet om du vill tilldela etiketten till en fil.

Här är den resulterande konfigurationen för gruppen Företagsstrategi.

![Konfiguration av gruppen Företagsstrategi.](../../media/highlyconfidential-team-config-dev-test.png)

Filer som finns i dokumentavsnittet på företagsstrategins underliggande SharePoint-webbplats, tilldelas kvarhållningsetiketten Strikt konfidentiellt och omfattas av den konfigurerade DLP-principen. Filer kan också ha tilldelats känslighetsetiketten för företagsstrategin.

## <a name="next-step"></a>Nästa steg

När du är redo för produktionsdistribution kan du läsa mer i [Skydda filer i Microsoft Teams](secure-files-in-teams.md) för detaljerad information och länkar till steg för steg-distributionsartiklar.

## <a name="see-also"></a>Se även

[Integrering av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
