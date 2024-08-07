---
title: Installera och konfigurera AEM Document Security Extension for Microsoft Office
description: I det här dokumentet får du hjälp med att installera och konfigurera Adobe Experience Manager Document Security Extension 6.2 för Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '2821'
ht-degree: 0%

---

# Installera och konfigurera AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

I det här dokumentet får du hjälp med att installera och konfigurera Adobe Experience Manager Document Security Extension för Microsoft Office.

Det här dokumentet innehåller information om följande uppgifter:

* Dokumentsäkerhetstillägget för Microsoft Office installeras.
* Installationsprogrammet förkonfigureras så att det pekar på LiveCyclet Rights Management ES2 eller senare eller Document Security-tillägget för AEM 6.0 Forms eller senare.
* Konfigurerar det automatiska programmet för standardprincipen.

## Innan du installerar {#before-you-install}

Innan du installerar Document Security Extension för Microsoft Office bör du kontrollera att:

* Du har läst [versionsinformationen](document-security-extension-release-notes.md).
* Microsoft Office är aktiverat. Aktiveringsdialogrutan visas inte när Microsoft Office-program öppnas.
* De senaste servicepaketen för Microsoft Windows och Microsoft Office är installerade.
* Om du installerar Document Security för Microsoft Office för ett språk som inte stöds ska du öppna Office-programmet minst en gång.

>[!NOTE]
>
>Installera inte programmet i en mapp vars namn innehåller dubbelbytetecken. Om du gör det visas inte menyn AEM dokumentsäkerhet i Microsoft Office.

>[!NOTE]
>
>Det finns stöd för att installera en 32-bitarsversion av Document Security Extension på ett 64-bitars operativsystem, men motsatsen stöds inte. Du kan inte installera en 64-bitarsversion av Document Security Extension för Microsoft Office på ett 32-bitars operativsystem.

### Inaktivera McAfee VirusScan {#disable-mcafee-virusscan}

Inaktivera alternativet Buffer Overflow Protection i McAfee VirusScan-konsolen. På så sätt kan Office-programmen startas smidigt på en dator med Document Security Extension installerat. Och McAfee VirusScan med On-Access Scan är aktiverat. Dessa justeringar hjälper till att förhindra konflikter som kan hindra startprocessen.

### Avinstallera plugin-program från tredje part {#uninstall-third-party-plug-ins}

AEM Document Security Extension för Microsoft Office stöder inte tredjeparts-plugin-program för Microsoft Office-program. Eftersom det här tillägget är i konflikt med plugin-program från tredje part avinstallerar du alla icke-Adobe-plugin-program för Microsoft Office innan du installerar Document Security för Microsoft Office. Adobe har inget stöd för Document Security för Microsoft Office-program med plugin-program från tredje part installerade.

## Systemkrav {#system-requirements}

### Document Security Extension Client {#document-security-extension-client}

Kontrollera följande minimikonfigurationer som du vill installera Document Security Extension på:

* 32- eller 64-bitarsversioner av Microsoft Windows 7 eller Windows 10 på engelska, franska, tyska, japanska, italienska, spanska, portugisiska (Brasilien), koreanska, förenklad kinesiska eller traditionell kinesiska.
  **Obs!** *Dokumentsäkerhetstillägget för Microsoft Office förväntas också fungera på Microsoft Surface-enheter.*

* 32- eller 64-bitarsversioner av Office 2013, 2016, 2019 och Microsoft Office-program installerade som en del av Office 365 på engelska, franska, tyska, japanska, italienska, spanska, brasiliansk portugisiska, koreanska, förenklad kinesiska eller traditionell kinesiska.

  **Obs!**: *AEM Document Security Extension for Microsoft Office stöder inte tredjeparts-plugin-program för Microsoft Office-program. Eftersom det här tillägget kan skapa konflikt med plugin-program från andra tillverkare måste alla plugin-program från andra tillverkare än Adobe för Microsoft Office avinstalleras innan Document Security Extension för Microsoft Office installeras. Adobe har inte stöd för Document Security Extensions för Microsoft Office-program med installerade plugin-program från tredje part.*

* 1,3 GHz-processor eller bättre
* 2 GB RAM
* 100 MB ledigt hårddiskutrymme

### Dokumentsäkerhet {#document-security}

Om du vill använda Document Security Extension måste du se till att du kan ansluta till Adobe LiveCycle Rights Management ES2 och senare eller Document Security-tillägg för AEM 6.0-formulär eller senare.

## Installerar Document Security Extension för Microsoft Office {#installing-document-security-extension-for-microsoft-office}

Du kan hämta installationsprogrammet från [hämtningssidan](download-installer.md). Du kan inte anpassa den körbara installationsfilen direkt, men den kan installeras interaktivt eller i tyst läge. Logga in i Windows som administratör för att installera programvaran.

Det finns separata installationsprogram för 32- och 64-bitarsversioner av Microsoft Office. Om du har en 32-bitarsversion av Microsoft Office hämtar du DocumentSecurityExtensionforMicrosoftOffice.exe. Om du har en 64-bitarsversion av Microsoft Office hämtar du DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>I det här dokumentet används en 32-bitars installationsfil (DocumentSecurityExtensionforMicrosoftOffice.exe) för att förklara olika kommandon och alternativ. Om du använder en 64-bitarsversion av Microsoft Office använder du 64-bitarsinstallationsfilen (DocumentSecurityExtensionforMicrosoftOffice64.exe) för att utföra de åtgärder som anges i det här dokumentet.

### Installera i tyst läge {#install-in-silent-mode}

Använd ett extraheringsverktyg för filer, till exempel WinZip, för att extrahera `DocumentSecurityExtensionforMicrosoftOffice.exe` från installationsfilen. Öppna kommandotolken, gå till mappen som innehåller installationsfilen och skriv följande text:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

Installationsprogrammet är också tillgängligt som en MSI-fil som kan användas för anpassning.

### Installera en MSI-fil i tyst läge {#install-an-msi-file-in-silent-mode}

1. Använd ett extraheringsverktyg, till exempel WinZip, för att extrahera filen `DocumentSecurityExtensionforMicrosoftOffice.msi` från ZIP-filen.

1. Öppna kommandotolken, gå till mappen som innehåller MSI-filen och skriv följande text:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Konfigurera installationsprogrammet på förhand för att ansluta till dokumentsäkerhet {#preconfiguring-the-installer-to-connect-to-document-security}

Du kan förkonfigurera Document Security Extension för installationsprogrammet för Microsoft Office så att det pekar på en LiveCycle- eller AEM. Detta säkerställer att användare som installerar Document Security Extension för Microsoft Office kan använda funktionerna utan att behöva konfigurera en anslutning. Användarna kan öppna skyddade dokument utan att behöva göra någon konfiguration. De kan dock inte skydda nya dokument förrän de konfigurerar klienten att använda en viss server.

I följande steg beskrivs hur du skapar och konfigurerar en MSI-fil. Den här MSI-filen innehåller registervärdena. Dessa värden krävs för att förkonfigurera Document Security Extension för Microsoft Office-installationsprogrammet till LiveCyclet eller AEM som är installerad i ditt företag.

### Krav för att anpassa installationsprogrammet {#prerequisites-for-customizing-the-installer}

Använd Orca-databasredigeraren för att anpassa installationsprogrammet. I följande steg beskrivs hur du skapar en anpassad MSI-fil genom att ändra en kopia av MSI-installationsfilen med hjälp av Orca-databasredigeraren. Orca finns som en del av Windows SDK för Windows Server 2008 och .NET Framework 3.5.

<!--

For more information about how to edit Microsoft Windows&reg; Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>Du bör göra en fullständig säkerhetskopiering av alla installationsfiler innan du skapar den anpassade MSI-filen.

#### Installera Orca {#install-orca}

1. Hämta Windows SDK för Windows Server 2008 och .NET Framework 3.5.
1. Dubbelklicka på filen Orca.msi i mappen \Microsoft SDK\bin.

   Du behöver även MSI-varianten av installationsfilen. Kontakta Adobe support för att få den senaste versionen av MSI-installationsprogrammet.

   >[!NOTE]
   >
   >Stäng alltid filen DocumentSecurityExtensionforMicrosoftOffice.msi innan du kör installationsprogrammet. Du kan inte köra installationsprogrammet om Orca använder MSI-filen.

### Skapa och konfigurera MSI-filen {#create-and-configure-the-msi-file}

1. Klicka på **[!UICONTROL Start > Program > Orca]**.

1. Klicka på **[!UICONTROL Arkiv > Öppna]** och bläddra sedan till filen `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Välj Egenskap i listan med tabeller (till vänster).

1. Redigera följande nyckelnamnsvärden efter behov för din Enterprise-installation av Rights Management eller Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>K</strong><strong>e</strong><strong>y Name</strong></p> </td>
   <td><p><strong>Beskrivning</strong></p> </td>
   <td><p><strong>K</strong><strong>e</strong><strong>y-standardvärde</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Visa ditt namn.</p> </td>
   <td><p>Standardserver</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>URL för värdserver.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Välj Register i listan med tabeller (till vänster).

1. Redigera följande nyckelnamnsvärde.

   | **Nyckelnamn** | **Beskrivning** | **Standardvärde för nyckelvärde** |
   |---|---|---|
   | `IsDefault` | Standardservern för APS. | Standardserver |

1. Spara den ändrade filen i samma katalog som innehåller det ursprungliga MSI-installationsprogrammet.

   >[!NOTE]
   >
   >Ett vanligt tillvägagångssätt är att använda samma filnamn som den ursprungliga MSI-filen (till exempel `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Konfigurera automatisk tillämpning av en standardprincip {#configuring-automatic-application-of-a-default-policy}

Som en del av konfigurationen kan du konfigurera automatisk tillämpning av en standardprofil så att Document Security Extension för Microsoft Office skyddar alla dokument som sparas.

Du kan ange något av följande alternativ:

* Protect alla dokument med en standardprofil.
* Låt användarna spara en fil i oskyddat format när de inte kan ansluta till servern. Tack vare den här flexibiliteten kan du ta hänsyn till fall när användare skapar dokument när de inte är anslutna till nätverket (t.ex. när de befinner sig på ett flygplan).

När du har aktiverat funktionen för automatisk tillämpning av principer skyddas dokumentet med standardprofilen i följande fall:

* En användare redigerar och sparar ett nytt dokument
* En användare redigerar och sparar ett oskyddat dokument
* Användaren öppnar ett program som öppnas med ett standarddokument, redigerar och sedan sparar dokumentet

### Konfigurera principfunktionen för automatisk tillämpning i MSI-filen {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Innan du börjar förkonfigurerar du installationsprogrammet så att det pekar på LiveCyclet eller AEM Forms Server, vilket beskrivs ovan i den här artikeln.

1. Klicka på **[!UICONTROL Start > Program > Orca]**.

1. Klicka på **[!UICONTROL Arkiv > Öppna]** och bläddra sedan till filen `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Välj Egenskap i listan med tabeller (till vänster).

1. Redigera följande nyckelnamnsvärden efter behov för företagsinstallationen av Rights Management eller dokumentsäkerhet.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nyckelnamn</strong></p> </td>
   <td><p><strong>Beskrivning</strong></p> </td>
   <td><p><strong>K</strong><strong>e</strong><strong>y-standardvärde</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Aktivera eller inaktivera funktionen för automatisk tillämpning av principer.</p> <p><code>1</code>: Aktivera</p> <p>0: Inaktivera</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>Principen är GUID som ska användas när nya dokument sparas. Det här värdet gäller för funktionen Automatiskt tillämpad princip.</p> </td>
   <td><p>Hexadecimalt princip-ID som det visas på RM-servern</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>Server-URL.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Serverportnummer.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Avgör om dokument kan skapas utan dokumentsäkerhetsskydd om klienten inte kan kontakta servern för att skydda dokumentet första gången det sparas.</p> <p>1: Tillåt oskyddade sparningar </p> <p>0: Förhindra att nya dokument skapas när klienten inte kan kontakta servern för att spara dokumentet.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>Alternativet `AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` är användbart när du vill påminna kunderna om att skydda alla dokument utan att tvinga dem att göra det. Det är också användbart när du vet att användare skapar dokument när de inte är anslutna till nätverket. Du vill inte hindra dem från att skapa och spara dokument.

1. Spara den ändrade filen i samma katalog som den ursprungliga MSI-filen.

   >[!NOTE]
   >
   >Ett vanligt tillvägagångssätt är att använda samma filnamn som den ursprungliga MSI-filen (till exempel `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Automatiskt skydd av nya dokument {#enabling-automatic-protection-of-new-documents}

Administratören kan aktivera möjligheten att automatiskt skydda alla dokument som användaren sparar. Administratören konfigurerar principfunktionen Auto-apply i installationsprogrammet för Document Security Extension för Microsoft Office.

Om principen Automatiskt tillämpat är aktiverad skyddas alla dokument som användaren sparar med standardprofilen. Den här åtgärden gäller i följande situationer:

* När en användare skapar ett nytt dokument redigerar och sparar det.
* När en användare öppnar ett oskyddat dokument redigeras det och sparas.

Mer information om hur du konfigurerar principen för autotillämpning finns i [Konfigurera ett automatiskt program för standardprincipen](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Aktivera bandfritt användargränssnitt {#enable-ribbon-less-user-interface}

Du kan aktivera/inaktivera det bandfria användargränssnittet genom att ändra inställningarna i Windows-registret. Så här uppdaterar du registret och aktiverar ett bandfritt användargränssnitt:

1. Säkerhetskopiera Windows-registret innan du ändrar det. Mer information finns i [Ändra Windows-registret](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. Gå till HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 eller HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 i Registereditorn
1. Skapa ett nytt Dword-värde (32-bitars) med namnet **HidePluginUI**.

1. Ange värdet 1 för egenskapen **HidePluginUI** om du vill aktivera ett bandfritt användargränssnitt.

1. Stäng Registereditorn.

## Aktivera vattenstämpel för utskrift i Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

Du kan ändra inställningarna för Windows-registret så att den dynamiska vattenstämpeln finns samtidigt som befintliga sidhuvuden och sidfötter. Med registerinställningarna blir vattenstämpeln bara tillgänglig vid utskrift. Så här uppdaterar du registret och aktiverar vattenstämplar vid utskrift:

1. Säkerhetskopiera Windows-registret innan du ändrar det. Mer information finns i [Ändra Windows-registret](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. Gå till HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 eller HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 i Registereditorn
1. Skapa en ny registernyckel **WatermarkMode**.
1. I registernyckeln WatermarkMode skapar du ett **WatermarkMode** i DWORD och anger värdet **WatermarkMode** till **1** i DWORD.

1. Stäng Registereditorn.

>[!NOTE]
>
>I Utforskaren kan du använda Arkiv-menyn eller snabbmenyn för att skapa ett Microsoft Excel-dokument. För dokument som skapats med angivna metoder går det inte att hämta eller ändra utskriftsdatumet. Det är en begränsning för Microsoft Excel. AEM dokumentsäkerhetsvattenstämplar är beroende av dokumentets utskriftsdatum. För sådana dokument återställs vattenstämpeln till ett tidigare datum. Dessutom behålls inte sidhuvuden och sidfötter.

## Lägga till en anpassad försättsblad i ett dokument {#coverpage}

En användare kan försöka öppna det skyddade dokumentet på en dator som inte har något AEM Document Security för Microsoft Office-plugin installerat. Sådana datorer kan inte öppna dokumentet. På sådana datorer kan du visa en försättssida med instruktioner om hur du hämtar AEM Document Security för Microsoft Office-plugin och annan information.

### Innan du konfigurerar en försättsblad {#before-you-configure-a-cover-page}

* Säkerhetskopiera filen CommonResources.dll. Standardsökvägen är:

   * **(För 32-bitarskontor på 32-bitarsdatorer)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(För 32-bitarskontor på 64-bitarsdatorer)** C:\Program filer (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(För 64-bitarskontor på 64-bitarsdatorer)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Kontrollera att du har Microsoft Visual Studio 2008 eller senare installerat. Du kan även använda andra verktyg för att redigera DLL-filerna.
* Extrahera arkivet templates.zip. Arkivet innehåller mallarna .xlsx, .docx och .pptx för försättssidan. Använd endast mallar för filtyperna .xlsx, .docx och .pptx. Du kan skapa egna mallar för andra filtyper. Anpassa mallar så att de innehåller anpassade meddelanden och instruktioner. template.zip finns här:

[Hämta fil](assets/templates.zip)

### Struktur för filen CommonResources.dll {#structure-of-the-commonresources-dll-file}

Filen CommonResources.dll innehåller information om resursmallarna. Den innehåller två namnidentifierare: TEMPLATE_FILE och RT_MANIFEST. Om du vill aktivera en anpassad försättsblad ändras identifieraren för namnet TEMPLATE_FILE. Namnidentifieraren TEMPLATE_FILE har sex resurser:

<table>
 <tbody>
  <tr>
   <td><p><strong>Resurs</strong></p> </td>
   <td><p><strong>Representerar </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Konfigurera mallen som en försättssida {#configure-the-template-as-a-cover-page}

1. Öppna Microsoft Visual Studio. Bläddra och öppna filen CommonResources.dll för redigering.

   >[!NOTE]
   >
   >Om filen inte visas i Utforskaren öppnar du filen igen med alternativet Öppna med. Välj resursredigeraren som redigerare.

1. Expandera katalogen TEMPLATE_FILE i fönstret Solution Explorer och ta bort resurserna 101.

1. Lägg till resurserna:

   1. Välj ett projekt i Solution Explorer och klicka på Egenskaper på Projekt-menyn.
   1. Välj fliken Resurser.
   1. I verktygsfältet Resurs-Designer pekar du på Lägg till resurs och klickar på pilen. För resurstyp väljer du TEMPLATE_FILE och klickar på importera.
   1. Bläddra till filen Resource.xlsx i dialogrutan **`Add existing file to resources`** och klicka sedan på Öppna. Filen läggs till i katalogen TEMPLATE_FILE.

   >[!NOTE]
   >
   >Kontrollera att språkinställningarna är korrekta. Ta bort resursen med neutralt språk.

1. Upprepa steg 2 och 3 för alla resurstyper.

   >[!NOTE]
   >
   >Ta inte bort resurstyper och lägg till dem i slumpmässig ordning. Efter 101, konfigurera 102 och så vidare.

### Paketera filen CommonResources.dll med installationsprogrammet AEM Document Security-tillägget för Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

Du kan anpassa filen CommonResources.dll och lägga till en anpassad försättsblad. När du har anpassat filen kan du ersätta originalfilen manuellt med den anpassade filen på alla arbetsstationer eller välja en automatiserad metod för att ersätta filen.

I en stor miljö är det svårt och tidsödande att manuellt ersätta standardfilen `CommonResources.dll file` med en anpassad `CommonResources.dll`-fil. Du kan använda ett självextraherande verktyg och paketeringsverktyg (till exempel WinZip Self-Extractor) för att paketera den anpassade filen CommonResources.dll med AEM Document Security Extension för Microsoft Office-installationsprogrammet. Senare kan du distribuera det anpassade installationsprogrammet till alla arbetsstationer. Den här metoden minskar den tid som krävs för att ersätta standardfilen `CommonResources.dll` med en anpassad fil. Det ser också till att alla arbetsstationer har den CommonResources.dll-fil som krävs. Självextraherings- och paketeringsverktyg är bara en av många möjliga metoder för att automatiskt ersätta en fil. Du kan välja vilken metod som helst som passar din miljö.

Du kan utföra följande steg för att paketera den anpassade `CommonResources.dll`-filen med installationsprogrammet AEM Document Security-tillägget för Microsoft Office:

1. Installera ett självuppackande verktyg och paketeringsverktyg. Exempel: WinZip-självextraheraren.
1. Skapa en ny mapp. YOUR_FOLDER_NAME
1. Placera det ursprungliga installationsprogrammet AEM Document Security Extension och den anpassade CommonResources.dll-filen i den nya mappen.
1. Skapa en gruppfil i mappen. Till exempel YOUR_FOLDER_NAME\Installer.bat
1. Öppna gruppfilen för redigering och lägg till följande kod i gruppfilen:

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   Om du använder någon annan version av LiveCyclet eller AEM Forms på JEE, förutom LiveCycle Rights Management ES 4 och version 11.0.0, ska du ersätta sökvägen för registernyckeln enligt följande:

   * (LiveCycle® ES2 och version 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (LiveCycle® ES3 och version 10.0)
   * (LiveCycle® ES4 och version 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms på JEE och senare) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. I ovanstående kod ersätter du alla förekomster av YOUR_FOLDER_NAME med namnet på mappen som du skapade i steg 2.
1. **(För AEM Document Security Extension for Microsoft Office installer with .exe extension only)** Ersätt följande kodrad:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
med

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Spara och stäng gruppfilen.
1. Använd ett självuppackande och paketeringsverktyg för att paketera mappen som innehåller:

   * Filen CommonResources.dll
   * Det ursprungliga installationsprogrammet AEM Document Security-tillägget för Microsoft Office
   * Och, gruppfilen

   >[!NOTE]
   >
   >Kontrollera att det självextraherande paketet är inställt på att köras som administratör och automatiskt
   >kör gruppfilen när extraheringen är klar.

Det självextraherande installationsprogrammet AEM Document Security Extension för Microsoft Office paketerar en anpassad CommonResources.dll-fil och är klart för distribution.
