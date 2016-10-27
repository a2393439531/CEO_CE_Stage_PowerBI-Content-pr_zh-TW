<properties
   pageTitle="Create a custom visual with the custom visual developer tools"
   description="Custom visuals allow you to meet your users' needs and match your app's design. Learn how to create a custom visual for Power BI using the developer tools."
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/23/2016"
   ms.author="asaxton"/>

# Create a custom visual with the custom visual developer tools

Custom visuals allow you to meet your users' needs and match your app's design. Learn how to create a custom visual for Power BI using the developer tools.

> [AZURE.NOTE] You can use this document to get up and running. For more in-depth information, see the reference information within the <bpt id="p1">[</bpt>Power BI Visuals git repo<ept id="p1">](https://github.com/Microsoft/PowerBI-visuals)</ept>.

## 需求

- NodeJS 4.0+ Required (5.0 or later recommended) <bpt id="p1">[</bpt>Download NodeJS<ept id="p1">](https://nodejs.org)</ept>

## Install NodeJS and the Power BI tools

In order to create a custom visual, you will need to install NodeJS. NodeJS is required to run the command line tools.

1. Download and install <bpt id="p1">[</bpt>NodeJS<ept id="p1">](https://nodejs.org)</ept>. Version 4.0 or later is required but it is recommended to have 5.0 or later.

2. Install the command line tools. Run the following command from a command prompt.

        npm install -g powerbi-visuals-tools

3. You can confirm that the tools are installed by running the following command without any parameters.

        pbiviz

    You should see the help output.

    <pre><code>
         +syyso+/
    oms/+osyhdhyso/
    ym/       /+oshddhys+/
    ym/              /+oyhddhyo+/
    ym/                     /osyhdho
    ym/                           sm+
    ym/               yddy        om+
    ym/         shho /mmmm/       om+
     /    oys/ +mmmm /mmmm/       om+
    oso  ommmh +mmmm /mmmm/       om+
   ymmmy smmmh +mmmm /mmmm/       om+
   ymmmy smmmh +mmmm /mmmm/       om+
   ymmmy smmmh +mmmm /mmmm/       om+
   +dmd+ smmmh +mmmm /mmmm/       om+
         /hmdo +mmmm /mmmm/ /so+//ym/
               /dmmh /mmmm/ /osyhhy/
                 //   dmmd
                       ++

       PowerBI Custom Visual Tool

    Usage: pbiviz [options] [command]

    Commands:

    new [name]        Create a new visual info              Display info about the current visual start             Start the current visual package           Package the current visual into a pbiviz file update [version]  Updates the api definitions and schemas in the current visual. Changes the version if specified help [cmd]        display help for [cmd]

    選項：

    -h, --help      output usage information -V, --version   output the version number --install-cert  Install localhost certificate
    </code></pre>

&lt;a name"ssl-setup"&gt;</a>
### Server Certificate setup

To enable a live preview of your visual, a trusted https server is needed. Before you can start, you will need to install an SSL certificate which will allow visual assets to load in your web browser. 

> [AZURE.NOTE] This is a one-time setup for your developer workstation.

To <bpt id="p1">*</bpt>add<ept id="p1">*</ept> a certificate, run the following command.

    pbiviz --install-cert

**Windows OS**

1. Select <bpt id="p1">**</bpt>Install Certificate...<ept id="p1">**</ept>*.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-windows.png)

2. Select <bpt id="p1">**</bpt>Current User<ept id="p1">**</ept> and then select <bpt id="p2">**</bpt>Next<ept id="p2">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-windows2.png)

3. Select <bpt id="p1">**</bpt>Place all certificate in the following store<ept id="p1">**</ept> and select <bpt id="p2">**</bpt>Browse...<ept id="p2">**</ept>.

4. Select <bpt id="p1">**</bpt>Trusted Root Certification Authorities<ept id="p1">**</ept> and then select <bpt id="p2">**</bpt>OK<ept id="p2">**</ept>. Select <bpt id="p1">**</bpt>Next<ept id="p1">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-windows3.png)

5. Select <bpt id="p1">**</bpt>Finish<ept id="p1">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-windows4.png)

6. Select <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> on the security warning dialog.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-windows5.png)

7. Close any browsers that you have open.

> [AZURE.NOTE] If the certificate is not recognized, you may need to restart your computer.

**OSX**

1. If the lock in the upper left is locked, select it to unlock. Search for <bpt id="p1">*</bpt>localhost<ept id="p1">*</ept> and double click on the certificate.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-osx.png)


2. Select <bpt id="p1">**</bpt>Always Trust<ept id="p1">**</ept> and close the window.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-osx2.png)

3. 輸入您的使用者名稱和密碼。 Select <bpt id="p1">**</bpt>Update Settings<ept id="p1">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/install-ssl-certificate-osx3.png)

4. Close any browsers that you have open.

> [AZURE.NOTE] If the certificate is not recognized, you may need to restart your computer.

## Enable live preview of developer visual

To enable a live preview of your custom visual, follow these steps. This allows the visual to be used within the Power BI service when editing reports.

1. Browse and sign into <bpt id="p1">[</bpt>app.powerbi.com<ept id="p1">](https://app.powerbi.com)</ept>.

2. Select the <bpt id="p1">**</bpt>gear icon<ept id="p1">**</ept> and then select <bpt id="p2">**</bpt>Settings<ept id="p2">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-settings.png)

3. Select <bpt id="p1">**</bpt>Developer<ept id="p1">**</ept> and then select <bpt id="p2">**</bpt>Enable developer visual for testing<ept id="p2">**</ept>.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-settings-enable-developer-live-preview.png)

4. Select the <bpt id="p1">**</bpt>Developer Visual<ept id="p1">**</ept> in the <bpt id="p2">**</bpt>Visualization<ept id="p2">**</ept> pane.

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-developer-visual-selection.png)

    > [AZURE.NOTE] This requires that you have run <ph id="ph1">`pbiviz start`</ph> from the visual folder on your development machine. For more information on creating your visual, see <bpt id="p1">[</bpt>Placeholder<ept id="p1">](#placeholder)</ept> in this article.

5. Select the visual in the report canvas. You can bind data in the same way you do other visuals.

You can now begin developing your visual.

## Create a new visual

You can create a new visual project by running the following command.

```
pbiviz new My Visual name
```

You can replace <bpt id="p1">*</bpt>My Visual Name<ept id="p1">*</ept> with the name you want to give the visual. This can be changed later by modifying the <ph id="ph1">`name`</ph> and <ph id="ph2">`displayName`</ph> fields within the generated <ph id="ph3">`pbiviz.json`</ph> file.

This command will create a new folder in the direct where the command was run. It will generate a basic starter template for your visual. Once the command completes, you can open the directory and use your favorite editor to start working on your new visual.

## Testing your visual in Power BI

You can test your visual within the Power BI service within reports and dashboards.

<a name="running-your-visual"></a>
### Running your visual

You can run your visual by doing the following.

1. Open a prompt.

2. Change your directory to be your visual folder. This is the folder that contains the <ph id="ph1">`pbiviz.json`</ph> file.

3. 執行下列命令。

    ```
    pbiviz start
    ```

    ![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-start-visual.png)

If you are in the wrong location, you will see an error similar to the following.

```
    error  LOAD ERROR Error: pbiviz.json not found. You must be in the root of a visual project to run this command.
        at e (C:\Users\[user]\AppData\Roaming\npm\node_modules\powerbi-visuals-tools\lib\VisualPackage.js:67:35)
        at Function.loadVisualPackage (C:\Users\[user]\AppData\Roaming\npm\node_modules\powerbi-visuals-tools\lib\VisualPackage.js:62:16)
        at Object.<anonymous> (C:\Users\[user]\AppData\Roaming\npm\node_modules\powerbi-visuals-tools\bin\pbiviz-start.js:43:15)
        at Module._compile (module.js:556:32)
        at Object.Module._extensions..js (module.js:565:10)
        at Module.load (module.js:473:32)
        at tryModuleLoad (module.js:432:12)
        at Function.Module._load (module.js:424:3)
        at Module.runMain (module.js:590:10)
        at run (bootstrap_node.js:394:7)
```

### Viewing your visual in Power BI

To view your visual in a report, go to that report and select the visual within the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> pane.

> [AZURE.NOTE] You must run the <ph id="ph1">`pbiviz start`</ph> command before doing this as discribed in the <bpt id="p1">[</bpt>Running your visual<ept id="p1">](#running-your-visual)</ept> section.

![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-developer-visual-selection.png)

You will then see the starter template for the visual.

![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-visual.png)

|Toolbar item|說明|
|---|---|
|Refresh visual|Manually refresh the visual if auto reload is disabled.|
|Toggle auto reload|When turned on, the visual will automatically update every time you save your visual file.|
|Show dataview|Shows the visual's underlying data view for debugging|
|取得說明|Documentation within GitHub|
|Send feedback|Let us know if there is anyway we can improve the experience! (Requires GitHub account)|

## Package your visual for use in Power BI Desktop and distribution

Before you can load your visual into <bpt id="p1">[</bpt>Power BI Desktop<ept id="p1">](https://powerbi.microsoft.com/desktop/)</ept>, or share it with the community in the <bpt id="p2">[</bpt>Power BI Visual gallery<ept id="p2">](https://visuals.powerbi.com)</ept>, you'll need to generate a <ph id="ph1">`pbiviz`</ph> file.

You can package your visual by doing the following.

1. Open a prompt.

2. Change your directory to be your visual folder. This is the folder that contains the <ph id="ph1">`pbiviz.json`</ph> file.

3. 執行下列命令。

    ```
    pbiviz package
    ```

This command will create a <ph id="ph1">`pbiviz`</ph> in the <ph id="ph2">`dist/`</ph> directory of your visual project. If there is already a <ph id="ph1">`pbiviz`</ph> file present, it will be overwritten.

## Updating the visuals API version

When you create a visual using <ph id="ph1">`pbiviz new`</ph>, a copy of the appropriate API type definitions and json schemas are copied into your visual's directory. You can use the <ph id="ph1">`pbiviz update`</ph> command to update these files if needed. This can be useful if we release a fix for a past API version or if you want to update to the latest API version.

### Updating your existing API version

If we release an update to an existing API, you can get the latest version by doing the following.

```
#Update your version of pbiviz
npm install -g powerbi-visuals-tools

#Run update from the root of your visual project, where pbiviz.json is located
pbiviz update
```

This will download the latest tools from npm which include the updated type definitions and schemas. Using <ph id="ph1">`pbiviz update`</ph> will overwrite the <ph id="ph2">`apiVersion`</ph> property in your <bpt id="p1">*</bpt>pbiviz.json<ept id="p1">*</ept> fiel with the latest version.

### Upgrading to a different API version

You can update to a different API version by using the same steps as mentioned above. You can explicitly specify the API version you want to use.

```
#Update your version of pbiviz
npm install -g powerbi-visuals-tools

#Run update from the root of your visual project, where pbiviz.json is located
pbiviz update 1.2.0
```

This would update yoru visual to API version 1.2.0. You can replace <ph id="ph1">`1.2.0`</ph> with whatever version your wanting to use.

> [AZURE.WARNING] The default API version used by the tools will always be the stable version of the API. Any versions later than the default API version are unstable and subject to change. They may have unexpected behaviors and behave differently between the Power BI service and Power BI Desktop. For the current stable API version, see the <bpt id="p1">[</bpt>change log<ept id="p1">](https://github.com/Microsoft/PowerBI-visuals/blob/master/ChangeLog.md)</ept>. For more information about pre-release versions, see the <bpt id="p1">[</bpt>roadmap<ept id="p1">](https://github.com/Microsoft/PowerBI-visuals/blob/master/Roadmap/README.md)</ept>.

## Inside the visual project

Your visual project is the folder that gets created when you run the <ph id="ph1">`pbiviz new`</ph> command. 

### 檔案結構

|項目|說明|
|---|---|
|assets/|Used to store visual assets (icon, screenshots, etc).|
|dist/|When you run <ph id="ph1">`pbiviz package`</ph>, the pbiviz file will be generated here.|
|src/|Typescript code for your visual.|
|style/|Less styles for your visual.|
|.gitignore|Tells git to ignore files that shouldn't be tracked in the repository.|
|capabilities.json|Used to define the <bpt id="p1">[</bpt>capabilities<ept id="p1">](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/Capabilities.md)</ept> of your visual.|
|package.json|Used by <bpt id="p1">[</bpt>npm<ept id="p1">](https://www.npmjs.com/)</ept> to manage modules.|
|pbiviz.json|Main configuration file.|
|tsconfig.json|Typescript compiler settings. Learn more about <bpt id="p1">[</bpt>tsconfig.json<ept id="p1">](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)</ept>.|

### pbiviz.json

This file is the main configuration file for your visual. It contains metadata, as well as information about your files, needed to build your visual.

```
{
    "visual": {
        "name": "myVisual", // internal visual name (should not contain spaces)
        "displayName": "My Visual!", // visual name displayed to user (used in gallery)
        "guid": "PBI_CV_xxxxxxx", // a unique id for this visual MUST BE UNIQUE
        "visualClassName": "Visual" // the entry class for your visual
        "version": "1.0.0", // visual version. Should be semantic version (increment if you update the visual)
        "description": "", // description used in gallery
        "supportUrl": "", // url to where users can get support for this visual
        "gitHubUrl": "" // url to the source in github (if applicable)
    },
    "apiVersion": "1.0.0", //API version this visual was created with
    "author": {
        "name": "", // your name
        "email": "" // your e-mail
    },
    "assets": {
        "icon": "assets/icon.png" // relative path to your icon file (20x20 png)
    },
    "style": "style/visual.less", // relative path to your less file
    "capabilities": "capabilities.json" // relative path to your capabilities definition 
}
```

### Visual source (TypeScript)

Visual code should be written in TypeScript, which is a superset of JavaScript that support more advanced features and early access to ES6/ES7 functionality.

All TypeScript files should be stored in the <ph id="ph1">`src/`</ph> directory and added to the <ph id="ph2">`files`</ph> array in <ph id="ph3">`tsconfig.json`</ph>. This allows the TypeScript compiler to load them and in what order.

When your visual is built, all of the TypeScript will be compiled into a single JavaScript file. This allows you to reference exported elements from other files without needing to manually <ph id="ph1">`require`</ph> them as long as both files are listed in the tsconfig.

You can create as many files and classes as you need to create your visual.

Learn more about <bpt id="p1">[</bpt>TypeScript<ept id="p1">](http://www.typescriptlang.org/)</ept>.

### Visual style (Less)

Visual styling is handled using cascading style sheets (CSS). For your convience, we use the Less pre-compiler which supports some advanced features such as nesting, variables, mixins, conditions, loops, etc. If you don't want to use any of these features, you can just write plain CSS in the Less file.

All Less files should be stored in the <ph id="ph1">`style/`</ph> directory. The file specified under the <ph id="ph1">`style`</ph> field within your <ph id="ph2">`pbiviz.json`</ph> file will be loaded. Any additional files should be loaded using <ph id="ph1">`@import`</ph>.

Learn more about <bpt id="p1">[</bpt>Less<ept id="p1">](http://lesscss.org/)</ept>.

## 偵錯

For tips about debugging your custom visual, see the <bpt id="p1">[</bpt>debugging guide<ept id="p1">](https://github.com/Microsoft/PowerBI-visuals/blob/master/tools/debugging.md)</ept>.

## Submit your visual to the Power BI custom visual gallery

You can <bpt id="p1">[</bpt>submit your visual<ept id="p1">](https://app.powerbi.com/visuals/info#submit)</ept> to be included in the Power BI visuals gallery. This involves sending an email with your pbiviz file attached.

## 疑難排解

**Pbiviz command not found (or similar errors)**

If you run <ph id="ph1">`pbiviz`</ph> in your terminal / command line, you should see the help screen. If not, it is not installed correctly. Make sure you have at least the 4.0 version of NodeJS installed.

For more information, see <bpt id="p1">[</bpt>Install NodeJS and the Power BI tools<ept id="p1">](#install-nodejs-and-the-power-bi-tools)</ept>...

**Cannot find the debug visual in the Visualizations tab**

The debug visual looks like a prompt icon within the <bpt id="p1">**</bpt>Visualizations<ept id="p1">**</ept> tab.

![](media/powerbi-custom-visuals-getting-started-with-developer-tools/powerbi-developer-visual-selection.png)

If you don't see it, make sure you have enabled it within the Power BI settings. 

> [AZURE.NOTE] The debug visual is currently only available in the Power BI service and not in Power BI Desktop or the mobile app. The packaged visual will still work everywhere.

For more information, see <bpt id="p1">[</bpt>Enable live preview of developer visual<ept id="p1">](#enable-live-preview-of-developer-visual)</ept>...

**Can't contact visual server**

Run the visual server with the command <ph id="ph1">`pbiviz start`</ph> in your terminal / command line from the root of your visual project. If the server is running, it is likely that your SSL vertificates weren't installed correctly.

For more information, see <bpt id="p1">[</bpt>Running your visual<ept id="p1">](#running-your-visual)</ept> or <bpt id="p2">[</bpt>Server certificate setup<ept id="p2">](#ssl-setup)</ept>.


## 請參閱

[Visualizations in Power BI](powerbi-service-visualizations-for-reports.md)  
[Custom Visualizations in Power BI](powerbi-custom-visuals.md)  
[The Power BI custom visuals gallery](https://app.powerbi.com/visuals)  
[TypeScript](http://www.typescriptlang.org/)  
[Less CSS](http://lesscss.org/)  
More questions? [Try the Power BI Community](http://community.powerbi.com/)