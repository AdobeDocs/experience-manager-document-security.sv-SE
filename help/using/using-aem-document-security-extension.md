---
title: Använda AEM Document Security Extension for Microsoft&reg; Office
description: Du kan styra hur mottagarna använder dina profilskyddade filer, oavsett hur mycket du distribuerar dem. Dokumentet förklarar hur du skyddar filer och hur du arbetar med skyddade filer.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
source-git-commit: 6cf19ed9439e5be5a4c2e2fa2458879f37c25b96
workflow-type: tm+mt
source-wordcount: '6136'
ht-degree: 0%

---

# Använda AEM Document Security Extension för Microsoft® Office{#using-aem-document-security-extension-for-microsoft-office}

## Protect-filer med AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Du kan styra hur mottagarna använder dina profilskyddade filer, oavsett hur mycket du distribuerar dem.

Med Document Security Extension för Microsoft® Office kan du göra följande:

* Konfigurera anslutningen till dokumentsäkerhet
* Tillämpa en profil på en fil
* Öppna webbsidorna Dokumentsäkerhet för att skapa och hantera användarprofiler
* Ta bort principskydd från en fil
* Ändra vilken profil som ska tillämpas på en fil
* Öppna webbsidorna Dokumentsäkerhet om du vill återkalla åtkomst till filer eller ändra profilen för filen
* Öppna webbsidorna Dokumentsäkerhet för att visa filens granskningshistorik

### Ansluta till en dokumentsäkerhetsserver {#connect-to-a-document-security-server}

Om du tänker tillämpa profiler på filer måste du konfigurera anslutningsinställningarna för dokumentsäkerhet. Beroende på hur Document Security Extension for Microsoft® Office är installerat kan det hända att du redan har standardanslutningsinställningar. Du kan lägga till anslutningsinställningar för en eller flera instanser av dokumentsäkerhet. Du kan hämta serverinformation från dokumentsäkerhetsadministratören.

Ange den server som du vill använda för att skydda filer eller hantera skyddade filer som standardserver. När du tillämpar en profil på en ny fil eller öppnar webbsidorna Dokumentsäkerhet ansluter Document Security Extension för Microsoft® Office till standardservern. Om du skyddar filer med mer än en instans av Dokumentskydd måste du ändra standardserverinställningen när du växlar mellan servrar. Du kan öppna filer som är skyddade av alla instanser av Dokumentskydd så länge du har behörighet att öppna filen.

Om dokumentsäkerhetsservern använder certifikatbaserad autentisering måste du installera certifikatet som du fick på den lokala datorn. Du måste välja en certifikatautentisering och ange det certifikat som du vill använda för att autentisera.

När du har konfigurerat anslutningsinställningarna för en instans av dokumentsäkerhet i ett Microsoft® Office-program, konfigureras den för alla Word-, Excel- och PowerPoint-filer.

#### Installera certifikatet på klientsidan {#install-the-client-side-certificate}

Om du måste ha åtkomst till webbsidorna Dokumentsäkerhet via certifikatautentisering eller tvåvägsautentisering får du det certifikat som du måste installera på din lokala dator. Du får en certifikatfil (.PFX- eller .P12-fil) och dess lösenord.

1. Spara certifikatfilen på den lokala datorn.
1. Dubbelklicka på certifikatfilen för att öppna guiden Importera certifikat och klicka på **Nästa**.
1. Klicka på **Nästa** om certifikatfilen visas i filnamnsrutan. Klicka på **Bläddra** om du vill hitta ett annat certifikat.
1. Ange lösenordet som du fick och klicka på **Nästa**.
1. I dialogrutan Certifikatarkiv väljer du Placera alla certifikat i följande arkiv och klickar på **Bläddra**.
1. I dialogrutan Välj certifikatarkiv väljer du Personligt, klickar på **OK**, klickar på **Nästa** och sedan på **Slutför**.

#### Konfigurera anslutningsinställningar {#configure-connection-settings}

1. Välj **Välj server** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och Office 2013.
1. Klicka antingen på **Nytt** om du vill skapa anslutningsinställningar, eller markera en befintlig anslutning och klicka på **Redigera**.
1. Skriv ett namn för anslutningen i rutan **Namn**. Du kan använda vilket namn som helst.
1. Skriv serveradressen i rutan **Serveradress**.
1. Skriv serverporten i rutan **Port**.
1. (Valfritt) Om du vill komma ihåg ditt användarnamn och lösenord markerar du **Kom ihåg lösenordet på den här datorn** och anger ditt användarnamn och lösenord i lämpliga rutor. Vi rekommenderar att du inte väljer det här alternativet om andra personer har åtkomst till datorn.
1. Klicka på **Anslut till den här servern**. Document Security Extension for Microsoft® Office försöker ansluta till den angivna servern. Beroende på vilken autentiseringstyp som har angetts gör du något av följande:

   **Användarnamn och lösenord**

   Ange det användarnamn och lösenord som du fick från administratören för dokumentsäkerhet.

   **Certifikatautentisering**

   Välj det här alternativet om du vill välja det certifikat som du har tagit emot och installerat i ditt personliga certifikatarkiv.

   Om bara en autentiseringstyp är konfigurerad för dokumentsäkerhet visas bara det alternativet.

>[!NOTE]
>
>Om du inte kan ansluta till servern kan du försöka öppna webbsidorna Dokumentsäkerhet i Internet Explorer. Om du inte kan ansluta till servern med Internet Explorer, eller om en dialogruta visar en varning om servercertifikatet, kan inte Document Security Extension för Microsoft® Office ansluta till servern. Kontakta serveradministratören om du behöver hjälp.

>[!NOTE]
>
>Om du inte kan ansluta till dokumentsäkerhet visas ett meddelande om att användarnamnet och lösenordet är felaktiga. Kontrollera konfigurationsinställningarna och försök igen. Det här meddelandet kan visas om du inte kan ansluta av någon annan anledning. Om du ansluter till servern för första gången kontrollerar du att du har angett servernamnet och porten korrekt.

#### Ange standardserver {#specify-the-default-server}

1. Gör följande:

   * Välj **Välj server** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och Office 2013.

1. Välj en server som du vill ange som standard och klicka på **Ange standard**. En stjärna visas bredvid standardservern.

### Använda autentiseringsleverantörer från tredje part {#using-third-party-authentication-providers}

Du kan använda autentiseringsleverantörer från tredje part med AEM Forms Document Security. Dessa autentiseringsleverantörer hjälper dig att lägga till ett extra åtkomstlager till de skyddade dokumenten. AEM Forms Document Security har stöd för följande utökade autentiseringsarbetsflöden:

* Utökad autentisering med standardwebbadressen för AEM Forms
* Utökad autentisering med en anpassad URL
* Standardarbetsflöde för utökad autentisering med tredjepartsidentitetsleverantörer konfigurerade på AEM Forms på JEE-servern
* Anpassat arbetsflöde för utökad autentisering med tredjepartsidentitetsleverantörer konfigurerade på AEM Forms på JEE-servern
* Utökad autentisering med en anpassad sida för att lista SAML-autentiseringar

#### Utökad autentisering med AEM Forms-standardwebbadress {#extended-authentication-using-default-aem-forms-url}

Du kan använda AEM Forms-standardwebbadressen för utökad autentisering. Standardlandningssidan innehåller Adobe-branding. Dessutom används AEM Forms standardinställningar för att använda AEM Forms-standardwebbadressen för utökad autentisering.

Utför följande steg för att aktivera utökad autentisering med standardURL för landning i Adobe:

1. Öppna användargränssnittet för AEM Forms Admin.
1. Navigera till Tjänster > Dokumentsäkerhet > Konfiguration > Serverkonfiguration.
1. Aktivera alternativet Tillåt utökad autentisering.
1. Ange URL:en för utökad autentisering. Standardwebbadressen är http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Klicka på **[!UICONTROL Spara]**.

   >[!NOTE]
   >
   >Använd ett fullständigt kvalificerat värdnamn i URL:en. Adobe rekommenderar att du använder HTTPS-protokollet.

   Nu är AEM Forms Document Security konfigurerat att använda utökad autentisering med AEM Forms standardstartadress.

   ![](assets/third-party-authentication.png)

#### Utökad autentisering med en anpassad landnings-URL {#extended-authentication-with-a-custom-landing-url}

Du kan använda en anpassad URL för utökad autentisering. Det ger flexibilitet att visa en anpassad autentiseringssida med anpassad varumärkning. Exempel: varumärkning för din organisation.

Du kan paketera den anpassade autentiseringssidan i en krigsfil och distribuera krigsfilen till AEM Forms Server. Krigsfilen innehåller fullständig logik för att godkänna inloggningsuppgifter och autentisera mot AEM Forms Server. AEM Forms Document Security har följande krav för den anpassade autentiseringssidan:

* Autentiseringssidan ska skicka användarnamn som j_username och password som j_password. Sidan ska också skicka source_url och login_url som dolda parametrar.
* När autentiseringen är klar bör sidan stängas automatiskt.

Så här aktiverar du utökad autentisering med en anpassad landnings-URL:

1. Distribuera WAR-filen för anpassad autentisering till AEM Forms Server.
1. Öppna användargränssnittet för AEM Forms Admin.
1. Navigera till Tjänster > Dokumentsäkerhet > Konfiguration > Serverkonfiguration.
1. Aktivera alternativet Tillåt utökad autentisering och ange en anpassad URL för utökad autentisering.
1. Lägg till följande poster i filen `config.xml` under SSO-noden efter posten *&lt;node name=&quot;AllowedUrls&quot;>*:

   >[!NOTE]
   >
   >&lt;entry key=&quot;sso-l&quot; value=&quot;/ sample_/login.jsp&quot;/>`!!discoiqbr!!`&lt;entry key=&quot;sso-s&quot; value=&quot;/ sample_/welcome.jsp&quot;>`!!discoiqbr!!`&lt;entry key=&quot;sso-o&quot; value=&quot;/ sample_/logout.jsp&quot;/>`!!discoiqbr!!`

   Stegvis information om hur du uppdaterar filen config.xml finns i [Redigera konfigurationsfilen för dokumentsäkerhet manuellt](https://experienceleague.adobe.com/en/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions#manually_editing_the_document_security_configuration_file).

   Nu är AEM Forms dokumentsäkerhet konfigurerat att använda utökad autentisering med en anpassad landnings-URL

#### Standardarbetsflöde för utökad autentisering med tredjepartsidentitetsleverantörer konfigurerade på AEM Forms Server {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

Utökad autentisering kan använda olika typer av autentisering som är tillgängliga på AEM Forms Server. Exempel: SAML, [Fler exempel].

Obs! Om SAML-providers är konfigurerade på AEM Forms Server visas en sida med alla identitetsleverantörer som konfigurerats för SAML-autentisering innan landnings-URL:en visas.

Följande skärm visas när ett skyddat dokument öppnas i Acrobat.

#### Anpassat arbetsflöde för utökad autentisering när SAML-providers konfigureras på AEM Forms Server {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Om SAML-providers är konfigurerade på AEM Forms Server visas en sida med alla identitetsleverantörer som konfigurerats för SAML-autentisering innan landnings-URL:en visas.

Krävs för att konfigurera ett anpassat, utökat autentiseringsarbetsflöde när SAML-providers har konfigurerats på AEM Forms Server:

* SAML-autentiseringar har konfigurerats på AEM Forms Server
* Anpassat krig, som innehåller en anpassad autentiseringssida och fullständig logik för att acceptera inloggningsuppgifter och autentisera mot AEM Forms Server, distribueras till AEM Forms Server.

#### Använda anpassad sida för att lista SAML-autentiseringar {#using-custom-page-for-listing-saml-authentications}

Du kan också visa en anpassad sida som innehåller alla autentiseringsproviders som är konfigurerade på AEM Forms Server. Skapa en sådan sida:

1. Paketera den anpassade autentiseringssidan i en krigsfil och distribuera krigsfilen till AEM Forms Server. Krigsfilen innehåller fullständig logik för att godkänna inloggningsuppgifter och autentisera mot AEM Forms Server.
1. Öppna AEM Forms Admin-gränssnittet och gå till **[!UICONTROL Inställningar]**> **[!UICONTROL Användarhantering]** > **[!UICONTROL Konfiguration]** > **[!UICONTROL Inställningar för SAML-tjänstleverantör]**.
1. Lägg till följande i fältet Egna egenskaper och klicka på **[!UICONTROL Spara]**.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   Nu är AEM Forms Document Security konfigurerat att visa en anpassad sida som innehåller alla konfigurerade autentiseringsproviders.

### Hämta ett användarkonto {#obtaining-a-user-account}

Om du inte redan har ett Document Security-konto kan Document Security starta registreringsprocessen när dessa händelser inträffar:

* En dokumentsäkerhetsanvändare som vill skicka en principskyddad fil till dig lägger till dig i en profil.
* Dokumentsäkerhetsadministratören skapar ett konto åt dig.

När du har registrerat och aktiverat ditt konto kan du använda principskyddade filer som du har fått behörighet att använda via en profil.

>[!NOTE]
>
>Om du får en principskyddad fil och inte har något dokumentskyddskonto kontaktar du den person som skickade filen. Om du får en inbjudan att registrera dig kan du kontakta avsändaren för att få hjälp.

Om du får en e-postregistreringsinbjudan från Document Security kan du registrera dig genom att använda URL:en i e-postmeddelandet för att öppna onlineregistreringssidan. Efter registreringen får du ett andra meddelande om hur du aktiverar ditt konto.

#### Hämta ett externt användarkonto {#obtain-an-external-user-account}

1. Öppna e-postmeddelandet om registrering av dokumentsäkerhet. Den URL som meddelandet innehåller är en länk till dokumentsäkerhetssidan för registrering av externa användare. Om du inte får något registreringsmeddelande kontaktar du den person som skickade filen.
1. Klicka på URL:en eller kopiera den och klistra in den i webbläsaren.
1. Skriv ditt namn, organisation och lösenord i rutorna. Lösenordet kan bestå av en kombination av åtta tecken.

   >[!NOTE]
   >
   >Se till att du väljer ett lösenord som är enkelt att komma ihåg. Det finns ingen metod för att hitta glömda lösenord.

1. Klicka på **Registrera**. Ett meddelande visas som informerar dig om att du kan söka efter ett aktiveringsmeddelande via e-post.
1. Öppna bekräftelsemeddelandet om registrering av dokumentsäkerhet.
1. Klicka på den URL som visas i meddelandet.
1. Klicka på länken till inloggningssidan.
1. I rutan **Användarnamn** skriver du den e-postadress som du är registrerad under med Dokumentsäkerhet. Den här e-postadressen är ditt standardanvändarnamn för dokumentsäkerhet.
1. I rutan **Lösenord** anger du lösenordet som du skapade när du registrerade dig.
1. Klicka på **Logga in**.

### Skapa och hantera policyer {#creating-and-managing-policies}

Om du har behörighet från administratören för dokumentsäkerhet kan du skapa profiler som ska tillämpas på dina egna filer på sidan Profiler på webbsidorna Dokumentsäkerhet.

Vissa principinställningar som är tillgängliga för att skapa profiler på webbsidorna Dokumentsäkerhet stöds inte för Word-, Excel- och PowerPoint-filer. Följande tabeller beskriver hur principbehörigheterna mappar till Word-, Excel- och PowerPoint-funktioner.

<table>
 <thead>
  <tr>
   <th><p>Behörigheter</p></th>
   <th><p>Word, Excel och PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Skriv ut &gt; Inte tillåtet</p></td>
   <td><p>Det är inte tillåtet att skriva ut filen.</p></td>
  </tr>
  <tr>
   <td><p>Skriv ut &gt; Tillåtet</p></td>
   <td><p>Det är tillåtet att skriva ut filen.</p><p><strong>Obs!</strong>: <i>Om en profil ger kopieringsbehörighet men inte behörighet att skriva ut, kan innehåll som kopieras till en annan fil skrivas ut.</i></p></td>
  </tr>
  <tr>
   <td><p>Skriv ut &gt; Låga rader. Endast</p></td>
   <td><p>Ej tillämpligt.</p></td>
  </tr>
  <tr>
   <td><p>Ändra &gt; Alla</p></td>
   <td><p>Filen kan ändras.</p><p>När den här behörigheten inte ges kan du inte ändra skyddade Word- och Excel-filer. Du kan ändra PowerPoint-filer men inte spara ändringarna eller visa bildspel för ändrade filer.</p></td>
  </tr>
  <tr>
   <td><p>Ändra &gt; Inte tillåtet</p></td>
   <td><p>Användare kan inte ändra skyddade filer.</p></td>
  </tr>
  <tr>
   <td><p>Ändra &gt; Ändra sidor</p></td>
   <td><p>Ej tillämpligt.</p><p>Det inkluderar infogning, borttagning och rotering av sidor.</p></td>
  </tr>
  <tr>
   <td><p>Ändra &gt; Fill &amp; Sign</p></td>
   <td><p>Ej tillämpligt.</p></td>
  </tr>
  <tr>
   <td><p>Offline</p></td>
   <td><p>Filen kan öppnas offline.</p></td>
  </tr>
  <tr>
   <td><p>Kopiera</p></td>
   <td><p>Filinnehåll kan kopieras till andra filer.</p></td>
  </tr>
  <tr>
   <td><p>Skärm Reader </p></td>
   <td><p>Skärmläsare (enheter för användare med nedsatt syn) kan läsa filinnehållet.</p></td>
  </tr>
  <tr>
   <td><p>Giltighet för behörighet</p></td>
   <td><p>Stöds.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Allmänna inställningar</p></th>
   <th><p>Word, Excel och PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Giltighetsperiod</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Granskningsdokument</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Automatisk offlineleasingperiod</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Externa auktoriseringsleverantörer</p></td>
   <td><p>Stöds.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Avancerade inställningar</p></th>
   <th><p>Word, Excel och PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Dynamiska vattenstämplar</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Plugin-program för certifiering</p></td>
   <td><p>Ej tillämpligt.</p></td>
  </tr>
  <tr>
   <td><p>Krypteringsalgoritm och nyckellängd </p></td>
   <td><p>Alla alternativ stöds.</p></td>
  </tr>
  <tr>
   <td><p>Dokumentbegränsning</p></td>
   <td><p>Allt filinnehåll krypteras alltid oavsett inställningen i profilen.</p></td>
  </tr>
  <tr>
   <td><p>Felmeddelande vid nekad åtkomst</p></td>
   <td><p>Stöds.</p></td>
  </tr>
 </tbody>
</table>

Mer information om hur du skapar och hanterar profiler finns i [Slutanvändarhjälpen för dokumentsäkerhet](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Använd profiler {#applying-policies}

Du kan tillämpa alla tillgängliga profiler på en fil, inklusive profiler som du har skapat och profiler som ingår i de principuppsättningar som du har tillgång till. Innan du tillämpar en profil måste du spara filen.

När du har tillämpat en profil läggs den till i listan Senast använda på menyn AEM dokumentsäkerhet för att göra det enklare för dig att tillämpa de profiler som du använder oftast. I listan Senast använda visas endast profiler för den server som du är ansluten till eller standardservern om du inte har loggat in på en annan Document Security-instans.

>[!NOTE]
>
>Profiler kan bara tillämpas på Word-filer (.doc, .docx, .docm), Excel-filer (.xls, .xlsx, .xlsm) och PowerPoint-filer (.ppt, .pptx, .pptm) i Microsoft® Office 2010 och 2013. Du kan inte använda profiler på Word-mallfiler (.dot), Excel-mallfiler (.xlt) och PowerPoint-designmallfiler (.pot).

#### Tillämpa en profil {#apply-a-policy}

1. I Document Security Extension för Microsoft® Office 2010 och 2013 på fliken **Dokumentsäkerhet** väljer du **Skydda > Välj profil**.

   Om du har valt användarnamn och lösenord som autentiseringsmetod på servern och ännu inte har angett inloggningsinformation för dokumentsäkerhet visas en dialogruta med ditt användarnamn och lösenord.

1. Välj en profil i listan och klicka på **Använd**.
1. Spara filen.

#### Använd en nyligen använd princip {#apply-a-recently-used-policy}

1. I Document Security Extension för Microsoft® Office 2010 och 2013 väljer du **Skydda** > *[Principnamn]* på fliken **Dokumentsäkerhet**.
1. Spara filen.

## Arbeta med skyddsskyddade filer {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Filutgivaren äger immateriell egendom i principskyddade filer, som dokumentskyddet skyddar.

Du kan använda principskyddade filer oavsett om du är intern eller extern i förhållande till filutgivarens organisation. Dokumentsäkerhet måste känna igen dig för att kunna öppna principskyddade filer. Det måste göras via LDAP/Active Directory. Eller så måste den göra det som lokal användare för LiveCycle-/AEM-formulär på JEE, eller genom att registrera efter en inbjudan.

Om du tar emot en principskyddad fil och inte har något Document Security-konto kontaktar du avsändaren för att få hjälp. Om du får en inbjudan att registrera dig kan du kontakta avsändaren för att få hjälp.

### Arbeta med principskyddade filer i Microsoft® Office {#working-with-policy-protected-files-in-microsoft-office}

Document Security Extension för Microsoft® Office begränsar vissa funktioner i Word, Excel och PowerPoint för att skydda filutgivarens immateriella egendom. Om du inte har behörighet att ändra filen kan du inte spara ändringar i den.

Om du arbetar med en principskyddad fil kanske vissa produktfunktioner inte är tillgängliga eller inte fungerar som vanligt. Om en oskyddad fil är öppen aktiveras de flesta funktioner, förutom de som gör att du kan importera eller kopiera innehåll från en principskyddad fil utan kopierings- eller exportbehörighet.

>[!NOTE]
>
>När du använder Office-program som stöder Document Security Extension rekommenderar vi att du inaktiverar inställningen Windows DEP. För att Office-programmen ska kunna startas smidigt på en dator med Document Security Extension och McAfee VirusScan med On-Access Scan aktiverat inaktiverar du alternativet Buffer Overflow Protection i McAfee VirusScan Console. Justeringen hjälper till att förhindra potentiella konflikter.

Om en funktion inte är tillgänglig är kommandonamnet på menyn och den relaterade verktygsfältsknappen inte tillgängliga. När du håller muspekaren över kommandot eller knappen i Document Security Extension för Microsoft® Office visas ett verktygstips som anger att kommandot inte är tillgängligt av Document Security.

### Öppna principskyddade filer {#opening-policy-protected-files}

Du kan öppna principskyddade filer på samma sätt som du använder för att öppna andra filer. Om du inte redan har loggat in på Dokumentsäkerhet uppmanas du att göra det. Det vill säga om du inte är ansluten till Internet och kan öppna filen offline. Om du avbryter inloggningen nekas åtkomst.

Om du inte har behörighet att öppna filen informeras du om att åtkomst nekas. Om filåtkomsträttigheterna har återkallats kan du även dirigeras till en uppdaterad version av filen om en sådan finns tillgänglig. Om du inte kan öppna en principskyddad fil kontaktar du filutgivaren.

När en skyddad fil är öppen anges det i texten i namnlisten att filen är skyddad AEM dokumentsäkerhet.

När du öppnar ett skyddat dokument i Document Security Extension för Microsoft® Office från SharePoint Server måste du se till att Office-programmet som är kopplat till filtypen, t.ex. Word, Excel eller PowerPoint, är öppet. Om du försöker öppna filen utan att öppna det associerade programmet kanske inte dokumentet öppnas och ett felmeddelande om att du måste installera det tillämpliga plugin-programmet visas. Förutom att öppna det program som krävs rekommenderar Adobe att du rensar cachemappen. Gör det innan du öppnar ett skyddat dokument i Document Security Extension för Office från SharePoint Server. När du öppnar ett skyddat dokument från SharePoint Server inaktiveras dessutom alla behörigheter i dokumentet, oavsett vilken princip som tillämpades.

Beroende på vilken autentiseringsmetod som har implementerats för dokumentsäkerhet kan du uppmanas att välja autentiseringsmetod när du öppnar ett skyddat dokument. Om Dokumentsäkerhet har stöd för mer än en autentiseringsmetod visas autentiseringsalternativen för dig. Om t.ex. en dokumentsäkerhetsserver tillhandahåller både användarnamn/lösenord och certifikatautentisering kan du välja lämplig autentiseringsmetod. Om certifikatbaserad autentisering är aktiverat uppmanas du att använda certifikatet som du har tagit emot och installerat.

Användarupplevelsen när skyddade filer öppnas beror på konfigurationen för ömsesidig autentisering på servern. Om bara ett giltigt klientcertifikat är installerat visas ingen dialogruta för autentisering och filerna öppnas korrekt. Om flera klientcertifikat är installerade på en dator visas dock en autentiseringsdialogruta. Användaren måste välja ett giltigt certifikat för att kunna öppna den skyddade filen.

### Ta bort principskydd från en fil {#removing-policy-protection-from-a-file}

Om du tilläts ta bort skyddsprofiler från filer som du har skyddat. Om du gör det skyddas filen inte längre av Dokumentsäkerhet.

1. Välj **Ta bort** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och 2013.

   Om du ännu inte har angett någon inloggningsinformation för dokumentsäkerhet visas en dialogruta med ditt användarnamn och lösenord.

>[!NOTE]
>
>Om du inte kan ta bort en profil från en fil som du har skyddat kontaktar du en säkerhetsadministratör för dokumentet.

### Visa säkerhetsinställningar {#viewing-security-settings}

Du kan visa de behörigheter som du har för den aktuella filen för utskrift. Du kan även visa behörigheter för den aktuella filen när du kopierar från, ändrar och öppnar offline, tillsammans med filens giltighetsperiod.

I Document Security Extension för Microsoft® Office 2010 visas din behörighet för filen i gruppen Security Status på fliken Document Security.

Gör följande:

* I Document Security Extension för Microsoft® Office 2010 och 2013 klickar du på ett objekt på fliken **Dokumentsäkerhet** i gruppen **Säkerhetsstatus** .

### Spara dokument när principen för automatisk tillämpning är aktiverad {#saving-documents-when-auto-apply-policy-is-enabled}

Om administratören har aktiverat automatisk tillämpning av principfunktioner skyddas alla dokument som du skapar eller redigerar automatiskt när du sparar dokumentet.

Om policyn Auto-apply är aktiverad uppmanas du att logga in på Document Security-servern i Document Security Extension för Microsoft® Office. Ange ditt användarnamn och lösenord så att servern kan autentisera dig. Om du har angett rätt inloggningsuppgifter sparas och skyddas dokumentet.

>[!NOTE]
>
>Om du inte kan logga in på Dokumentskydd kan det hända att dokumentet inte sparas. Detta beror på hur administratören har konfigurerat principen för automatisk tillämpning. Fråga administratören om hur dokument hanteras i den här situationen.

### Synkroniserar för offlineåtkomst {#synchronizing-for-offline-access}

Med hjälp av profiler kan du öppna filer när du är offline och inte är ansluten till Dokumentsäkerhet. Du måste tidigare ha loggat in på Dokumentsäkerhet för att kunna upprätta dina autentiseringsuppgifter med servern innan du kan arbeta offline. Om du tänker arbeta med filer offline rekommenderar Adobe att du synkroniserar med dokumentsäkerhet. Gör det innan du kopplar från för att se till att principinställningarna för dina filer är uppdaterade med servern. Adobe rekommenderar även att du öppnar filen online en gång innan du öppnar den offline. Om du inte öppnar filen online eller synkroniserar med servern kan du fortfarande använda profilskyddade filer offline. Låneperioden för offlinelån får dock inte ha gått ut och principinställningarna för filen får inte ha ändrats sedan du senast synkroniserade manuellt eller automatiskt med servern.

Gör följande:

* Välj **Synkronisera offline** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och 2013.

  ***Obs!**: Knappen Synkronisera offline är tillgänglig även om användaren inte har offlinebehörighet för dokumentet. Men om du markerar knappen händer ingenting.*

### Arbeta med dynamiska vattenstämplar {#working-with-dynamic-watermarks}

Document Security Extension for Microsoft® Office har stöd för dynamiska textbaserade vattenstämplar i policyskyddade dokument. En dynamisk vattenstämpel kan innehålla information som kan ändras, t.ex. datum, tid, användarnamn eller principens namn. Om en användare skriver ut en principskyddad fil och filen innehåller en dynamisk vattenstämpel och behörighet att skriva ut, visas vattenstämpeln i utdata.

Document Security Extension stöder inte vattenstämpelfunktioner. Funktioner för vattenstämplar är bland annat PDF-baserade vattenstämplar, flera element i en vattenstämpel och textformateringsalternativ. De innehåller även sidintervallet.

Du kan skapa en dynamisk vattenstämpel med hjälp av webbsidorna Dokumentsäkerhet. Mer information finns i [Slutanvändarhjälpen för dokumentsäkerhet](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/work-with-document-security/document-security).

Document Security Extension for Microsoft® Office har stöd för följande vattenstämpelfunktioner:

<table>
 <thead>
  <tr>
   <th><p>Vattenstämpelalternativ för dokumentskydd</p></th>
   <th><p>Word, Excel och PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Principnamn</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Vattenstämpelnamn</p></td>
   <td><p>Stöds.</p></td>
  </tr>
  <tr>
   <td><p>Använd som bakgrund</p></td>
   <td><p>Visningsbeteendet för en dynamisk vattenstämpel är detsamma oavsett om du väljer Använd som bakgrund eller inte.</p><p>För Word 2010 och 2013 visas den dynamiska vattenstämpeln bara i utskriftslayout och förhandsgranskningsläge. </p><p>För Excel 2010 och 2013 visas det också i vyerna Förhandsgranska och Sidlayout.</p></td>
  </tr>
  <tr>
   <td><p>Lodrät position</p></td>
   <td><p>Stöds</p></td>
  </tr>
  <tr>
   <td><p>Vågrät position</p></td>
   <td><p>Stöds</p><p>I Excel 2010 och 2013 fungerar inte den vågräta placeringen av vattenstämplar med punkter.</p></td>
  </tr>
  <tr>
   <td><p>Skala</p></td>
   <td><p>Stöds</p></td>
  </tr>
  <tr>
   <td><p>Position</p></td>
   <td><p>Stöds</p></td>
  </tr>
  <tr>
   <td><p>Opacitet</p></td>
   <td><p>Stöds</p></td>
  </tr>
 </tbody>
</table>

### Öppna webbsidorna Dokumentsäkerhet {#opening-the-document-security-web-pages}

Du kan öppna webbsidorna Dokumentsäkerhet för att skapa och uppdatera dina användarprofiler och visa status och granskningsinformation om dina profilskyddade filer. Du kan också använda webbsidorna Dokumentsäkerhet för att ändra profiler eller återkalla åtkomst för en profilskyddad fil.

Om du vill öppna webbsidorna Dokumentsäkerhet går du till Dokumentsäkerhetstillägg för Microsoft® Office 2010 och 2013 och väljer **Skapa och hantera profiler** på fliken **Dokumentsäkerhet** . Om du ännu inte har angett någon inloggningsinformation öppnas webbläsaren på serverinloggningssidan.

### Ändra profiler {#changing-policies}

Om du har behörighet, vanligtvis som dokumentsäkerhetsadministratör eller filutgivare, kan du senare tillämpa en annan profil på en fil eller ändra inställningarna för den profil som används för tillfället.

Om du vill ändra inställningarna för en profil använder du webbsidorna Dokumentsäkerhet.

1. Gör följande:

   * Gå till Document Security Extension för Microsoft® Office 2010 eller 2013 och välj **Skydda > Ändra skydd** på fliken **Dokumentsäkerhet**.

1. Välj en profil i listan och klicka på **Använd**.

### Återkalla filåtkomstbehörighet {#revoking-file-access-privileges}

Du kan återkalla möjligheten att öppna filer som du har skyddat. När du återkallar filåtkomst kan du ange ett meddelande när användare försöker öppna det och ange en URL till en uppdaterad version om den ersätts med en ändrad kopia.

1. Gör följande:

   * Välj **Återkalla** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och 2013.

   Webbsidorna Dokumentsäkerhet öppnas på sidan Återkalla dokument.

1. Ange ett meddelande som ska visas och, om det är tillgängligt, en URL för den uppdaterade versionen och klicka på **OK**.

Mer information om hur du återkallar behörigheter för filåtkomst finns i [Slutanvändarhjälpen för dokumentsäkerhet](https://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Behörigheterna kan återställas via webbsidorna Dokumentsäkerhet.

### Visa filgranskningshistoriken {#viewing-the-file-audit-history}

Dokumentsäkerhet kan spara granskningshistorik för principskyddade filer så att du kan granska de åtgärder som användarna utför på filerna.

Granskade händelser för Word-, Excel- och PowerPoint-filer innehåller följande:

**Skydda en princip för ett nytt dokument** som tillämpas på en fil

**Visa dokumentet** har öppnats

**Stäng dokument** Filen har stängts

**Återkalla dokument** Åtkomstbehörighet har tagits bort för filen

**Ångra dokumentbehörigheter** har returnerats till filen

**Ändra dokumentet** Filen har ändrats och sparats lokalt

**Skriv ut högupplöst** fil utskriven

**Ändra säkerhetshanterare** Principskydd har tagits bort från filen

**Byt profil på dokument** Ny princip som tillämpas på filen från webbsidorna Dokumentsäkerhet

### Visa granskningshistorik för en fil {#view-the-audit-history-for-a-file}

Välj **Granskningshistorik** på fliken **Dokumentsäkerhet** i Document Security Extension för Microsoft® Office 2010 och 2013.

Webbsidorna Dokumentsäkerhet öppnas på sidan Händelser där granskade händelser för den aktuella filen visas.

### Begränsade funktioner i Microsoft® Office {#microsoft-office-restricted-features}

För att skydda din immateriella egendom är vissa Microsoft® Office-funktioner inte tillgängliga när en principskyddad fil är öppen. Listan över funktioner som inte är tillgängliga beror på vilka behörigheter som ges till den aktuella användaren. Vissa funktioner är bara otillgängliga för skyddade filer och andra är inte tillgängliga för alla filer när du befinner dig i en skyddad session. Vanligtvis är du i en skyddad session från den tidpunkt du öppnar en principskyddad fil tills du stänger programmet eller sessionen förfaller.

De flesta profiler ger fullständig behörighet till filutgivaren. Andra användare kan lägga märke till ytterligare funktionsbegränsningar.

Om ett kommando inte är tillgängligt är kommandonamnet på menyn och den relaterade verktygsfältsknappen nedtonade.

>[!NOTE]
>
>Om du tillämpar en princip på en fil som innehåller en länk till en inbäddad fil tillämpas inte principen på den länkade filen. Dokumentsäkerhet för Microsoft® Office ger inte skydd åt länkade filer.

* Principskyddade Word-, Excel- och PowerPoint-filer kan inte öppnas i webbläsaren Internet Explorer.
* Användare som endast tilldelats behörigheten Ändra kan inte kopiera innehåll till en fil från ett annat program med hjälp av Urklipp i Windows. Användare kan kopiera innehåll till filer genom att aktivera alternativet Microsoft® Office Clipboard.
* När du öppnar en principskyddad fil i Microsoft® Office blir inte Skriv ut skärm-tangenten tillgänglig förrän du stänger programmet eller sessionen förfaller.
* Document Security för Microsoft® Office stöder inte WebDAV (Web-based Distributed Authoring and Versioning). Vanligtvis kan du inte öppna en principskyddad fil från en WebDAV-mapp. Om du kan öppna en principskyddad fil har du inte behörighet att spara, skriva ut, ändra eller kopiera från filen.

Den allmänna säkerhet som gäller för principskyddade filer omfattar följande begränsningar:

Många vanliga funktioner kan begränsas i Word, Excel och PowerPoint under en skyddad session.

Om en principskyddad fil som inte tillåter användaren att göra ändringar i den är öppen, är kommandon som ändrar filen på något sätt inte tillgängliga. Endast kommandon som öppnar eller skapar dokument och ändrar programinställningarna är tillgängliga.

#### Begränsningar för Word 2010 och Word 2013 {#word-2010-and-word-2013-restrictions}

När du öppnar en principskyddad fil i Word går det inte att spara automatisk filåterställningsinformation förrän du stänger och startar om Word. Dessutom är funktionerna som listas nedan begränsade i de situationer som beskrivs:

**Arkiv > Nytt > Nytt från befintligt** Tillgängligt, men det går inte att spara filer som skapats med det här kommandot när en principskyddad fil är öppen. Innehåll i den nya filen kan inte kopieras till en annan fil.

**Arkiv > Spara** Begränsad av behörigheten Ändra.

**Arkiv > Spara som** Alla alternativ som begränsas av behörigheten Ändra.

**Arkiv > Skriv ut** Alla alternativ som begränsas av utskriftsbehörigheten. Inte tillgängligt om inte principen tillåter utskrift med hög upplösning.

**Arkiv > Spara och skicka** Alla alternativ är inte tillgängliga under en skyddad session.

**Arkiv > Info > Protect-dokument > Kryptera med lösenord, Lägg till digital signatur, Markera som slutgiltig, Begränsa behörigheter för personer** Inte tillgängligt under en skyddad session.

**Arkiv > Arbetsflöden** Inte tillgängligt under en skyddad session.

***Obs!**: Det går bara att starta ett arbetsflöde i Word, Excel och PowerPoint 2010 i Office Professional Plus 2010, Office Enterprise 2010, Office Ultimate 2010 och fristående 2010-versioner.*

**Blogginlägg > Publish** Inte tillgängligt under en skyddad session.

**Arkiv > Server > Filserverns aktivitetsmeny** Inte tillgänglig under en skyddad session.

**Hem > Urklipp > Kopiera** Begränsat av behörigheten Kopiera. Om kopiering inte tillåts går det inte att klistra in kopierat innehåll i någon annan fil eller i Office Clipboard. Innehåll kan kopieras inuti den skyddade filen om användaren har ändringsbehörighet.

**Hem > Urklipp > Klistra in** Begränsat av behörigheten Ändra.

**Hem > Urklipp > Klistra in special** Begränsat av behörigheten Ändra.

**Infoga > Text > Objekt** Inte tillgängligt under en skyddad session. Det går inte att infoga principskyddade filer när som helst.

**Meddelanden** De flesta alternativen på den här fliken är inte tillgängliga under en skyddad session.

**Granska > Korrektur > Forskning** Begränsad av behörigheten Kopiera. Inte tillgängligt om kopiering inte tillåts.

**Granska > Korrektur > Synonymordbok** Begränsad av behörigheten Kopiera. Inte tillgängligt om kopiering inte tillåts.

**Review > Language > Translate > Translate Document** Enabled with the Copy permission.

**Granska > Språk > Översätt > Översätt markerad text** aktiverad med behörigheten Kopiera.

**Review > Language > Translate > Mini Translator** Enabled with the Copy permission.

**Granska > Jämför > Jämför** Inte tillgängligt under en skyddad session. Policyskyddade filer kan inte jämföras när som helst.

**Review > Protect > Block Authors** Unavailable during a protected session.

**Granska > Protect > Begränsa redigering** Inte tillgängligt under en skyddad session.

**Visa > Makron** Kopieringsbehörigheten begränsar vissa makron, vilket gör dem otillgängliga om inte kopiering tillåts.

**Tillägg** kan inte läggas till eller tas bort under en skyddad session.

**Online Collaboration** är inte tillgängligt under en skyddad session.

**Princip för primära och underordnade dokument** styr deldokument när du öppnar dem i det primära dokumentet. Om de öppnas separat går det inte att skriva ut, kopiera från eller ändra deldokument.

**Sammanfattningen** är inte tillgänglig under en skyddad session.

**Bildrutor (och alla relaterade kommandon)** är inte tillgängliga under en skyddad session.

**Dokumentpanelen** är inte tillgänglig under en skyddad session.

**Utvecklare > Dokumentmall** Inte tillgänglig under en skyddad session. Du öppnar kommandot genom att välja Arkiv > Alternativ > Anpassa > fliken Utvecklare > Mallar > Dokumentmall.

**Disposition > Primärt dokument > Skapa underdokument, infoga underdokument** Inte tillgängligt under en skyddad session.

#### Begränsningar för Excel 2010 och Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Funktionerna nedan är begränsade i de situationer som beskrivs nedan:

**Arkiv > Nytt > Nytt från befintligt** är tillgängligt, men det går inte att spara filer som skapats med det här kommandot under en skyddad session. Innehåll i den nya filen kan inte kopieras till en annan fil.

**Arkiv > Spara, Spara som** Begränsat av behörigheten Ändra.

**Arkiv > Spara som > PDF** Inte tillgänglig under en skyddad session.

**Arkiv > Skriv ut** Begränsad av utskriftsbehörighet. Inte tillgängligt om inte principen tillåter utskrift med hög upplösning.

**Arkiv > Info > Protect-dokument** Inte tillgängligt under en skyddad session.

**Arkiv > Info > Protect Workbook** Inte tillgänglig under en skyddad session.

**Arkiv > Spara och skicka** Inte tillgängligt under en skyddad session.

**Arkiv > Alternativ > Tillägg** Det går inte att lägga till eller ta bort under en skyddad session.

**Arkiv > Arbetsflöden** Inte tillgängligt under en skyddad session.

***Obs!**: Det går bara att starta ett arbetsflöde i Word, Excel och PowerPoint 2010 i Office Professional Plus 2010, Office Enterprise 2010, Office Ultimate 2010 och fristående 2010-versioner.*

**Arkiv > Server > Filserverns aktivitetsmeny** Inte tillgänglig under en skyddad session.

**Hem > Urklipp > Kopiera** Begränsat av behörigheten Kopiera. Om kopiering inte tillåts går det inte att klistra in kopierat innehåll i någon annan fil eller i Microsoft® Office Clipboard. Innehåll kan kopieras inuti den skyddade filen om användaren har ändringsbehörighet.

**Hem > Urklipp > Klistra in** Begränsat av behörigheten Ändra.

**Hem > Urklipp > Klistra in special** Begränsat av behörigheten Ändra.

**Hem > Celler > Format > Flytta eller Kopiera blad** Inte tillgängligt under en skyddad session.

**Hem > Celler > Infoga > Infoga blad** Inte tillgängligt under en skyddad session.

**Hem > Celler > Ta bort > Ta bort blad** Inte tillgängligt under en skyddad session.

**Hem > Redigering > Fyllning > Över kalkylblad** Begränsat av behörigheten Ändra.

**Infoga > Tabeller > Tabell** Begränsad av behörigheten Ändra.

**Infoga > Tabeller > Pivottabell** Principskyddade filer kan inte väljas i guiden Skapa.

**Infoga > Text > Objekt** Inte tillgängligt under en skyddad session. Det går inte att infoga principskyddade filer när som helst.

**Infoga > Text > Sidhuvud och sidfot** Begränsad av behörigheten Ändra. Inte tillgängligt för ett profilskyddat dokument.

**Data > Hämta externa data** Det går inte att importera data från principskyddade filer.

**Data > Disposition > Delsummor** Begränsad av behörigheten Ändra.

**Data > Dataverktyg > Dataverifiering** Begränsad av behörigheten Ändra.

**Granska > Korrektur > Forskning** Begränsad av behörigheten Kopiera.

**Granska > Korrektur > Synonymordbok** Begränsad av behörigheten Kopiera.

**Granska > Språk > Översätt** Begränsad av behörigheten Kopiera.

**Review > Changes > Protect Sheet** Unavailable during a protected session.

**Granska > Ändringar > Protect Workbook** Inte tillgänglig under en skyddad session.

**Review > Changes > Share Workbook** Unavailable during a protected session.

**Review > Changes > Protect and Share Workbook** Unavailable during a protected session.

**Granska > Ändringar > Tillåt användare att redigera intervall** Inte tillgängligt under en skyddad session.

**Granska > Ändringar > Spåra ändringar > Markera ändringar** Inte tillgängligt för en principskyddad fil som innehåller en dynamisk vattenstämpel.

**Visa > Makron** Begränsad av behörigheten Ändra.

**Visa > Spara Workspace**-kommandot fungerar inte.

**Utvecklare > XML > Expansionspaket** Kopieringsbehörigheten begränsar vissa makron, vilket gör dem otillgängliga om du inte tillåter kopiering.

**Formler > Formelgranskning > Felkontroll** Begränsad av behörigheten Ändra. Inte tillgängligt om inte ändring tillåts.

**Online Collaboration** är inte tillgängligt under en skyddad session.

**Spara information för automatisk återställning** Inte tillgänglig under en skyddad session.

***Obs!**Om du försöker ändra en cell i en principskyddad fil utan behörighet visas en varning i Excel om att du inte kan använda kommandot Ta bort bladets skydd för att ta bort skyddet.*

#### Begränsningar för PowerPoint 2010 och PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Funktionerna nedan är begränsade i de situationer som beskrivs nedan:

**Arkiv > Nytt > Nytt från befintligt** är tillgängligt, men det går inte att spara filer som skapats med det här kommandot under en skyddad session. Innehåll i den nya filen kan inte kopieras till en annan fil.

**Arkiv > Spara** Begränsad av behörigheten Ändra.

**Arkiv > Spara som** Alla alternativ som begränsas av behörigheten Ändra.

**Arkiv > Skriv ut** Alla alternativ som begränsas av utskriftsbehörigheten. Inte tillgängligt om inte principen tillåter utskrift med hög upplösning.

**Arkiv > Spara och skicka** Inte tillgängligt under en skyddad session.

**Arkiv > Info > Protect Presentation > Kryptera med lösenord, Lägg till en digital signatur, Markera som slutgiltig, Begränsa behörigheter för personer** Inte tillgängligt under en skyddad session.

**Arkiv > PowerPoint-alternativ > Spara information för automatisk återställning** Inte tillgängligt under en skyddad session.

**Arkiv > Server > Filserverns aktivitetsmeny** Inte tillgänglig under en skyddad session.

**Hem > Urklipp > Kopiera** Begränsat av behörigheten Kopiera. Om kopiering inte tillåts går det inte att klistra in kopierat innehåll i dokumentet, i någon annan fil eller i Office Clipboard. Innehåll kan kopieras inuti den skyddade filen om användaren har ändringsbehörighet.

**Hem > Urklipp > Klistra in** Begränsat av behörigheten Ändra. Om kopiering inte tillåts går det inte att klistra in kopierat innehåll i dokumentet.

**Hem > Urklipp > Klistra in special** Begränsat av behörigheten Ändra.

**Hem > Bilder > Nya bilder > Bilder från disposition, Återanvänd bilder** Inte tillgängligt under en skyddad session.

**Infoga > Text > Objekt** Inte tillgängligt under en skyddad session. Det går inte att infoga principskyddade filer när som helst.

**Design > Bakgrund > Bakgrundsformat, Dölj bakgrundsgrafik, Formatera bakgrund** Inte tillgängligt för en principskyddad fil som innehåller en dynamisk vattenstämpel.

**Bildspel > Konfigurera > Spela in bildspel** Begränsat av ändringsbehörighet.

**Granska > Korrektur > Synonymordbok** Begränsad av behörigheten Kopiera.

**Granska > Språk > Översätt** Begränsad av behörigheten Kopiera.

**Review > Language > Translate > Mini Translator** Enabled with the Copy permission.

**Visa > Presentationsvyer > Bildspel** Begränsat av behörigheten Ändra. Om ändringar inte tillåts kan bildspel inte visas om filen har ändrats.

**Visa > Makron** Kopieringsbehörigheten begränsar vissa makron, vilket gör dem otillgängliga om inte kopiering tillåts.

**Tillägg** kan inte läggas till eller tas bort under en skyddad session.

**Online Collaboration** är inte tillgängligt under en skyddad session.

## Använd autentiseringsproviders från tredje part {#use-third-party-authentication-providers}

Du kan använda autentiseringsleverantörer från tredje part med AEM Forms Document Security. Dessa autentiseringsleverantörer hjälper dig att lägga till ett extra åtkomstlager till de skyddade dokumenten. AEM Forms Document Security har stöd för följande utökade autentiseringsarbetsflöden:

* Utökad autentisering med standardwebbadressen för AEM Forms
* Utökad autentisering med en anpassad URL
* Standardarbetsflöde för utökad autentisering med tredjepartsidentitetsleverantörer konfigurerade på AEM Forms på JEE-servern
* Anpassat arbetsflöde för utökad autentisering med tredjepartsidentitetsleverantörer konfigurerade på AEM Forms på JEE-servern
* Utökad autentisering med en anpassad sida för att lista SAML-autentiseringar

## Ordlista {#glossary}

Mer information om LiveCycle och AEM formulär om JEE-terminologi finns i [Kapitel 19: Ordlista](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-5/forms/pdf/using-designer.pdf).
