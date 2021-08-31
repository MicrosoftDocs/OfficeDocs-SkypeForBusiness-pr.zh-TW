---
title: 使用Microsoft Teams 會議室部署Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 會議室 部署大型Microsoft Endpoint Configuration Manager。
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731572"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft Teams 會議室 部署Microsoft Endpoint Configuration Manager

本文提供您所有必要的資訊，讓您使用Microsoft Teams 會議室來建立您的Microsoft Endpoint Configuration Manager。

使用 Configuration Manager 提供的便於使用的方法，您可以將作業系統和其他應用程式部署到多個目標裝置。

請使用下列說明的方法，引導您完成 Configuration Manager 組式，並根據您的組織需要自訂本指南中提供的範例套件和腳本。

![Microsoft Teams 會議室 Configuration Manager 管理部署程式。](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 此解決方案僅使用以Surface Pro型部署進行測試。 請遵循製造商的指導方針，進行不以Surface Pro。

## <a name="validate-prerequisites"></a>驗證先決條件

若要使用 configuration Manager Microsoft Teams 會議室部署應用程式，請確保您符合下列先決條件和需求。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager需求

-   Microsoft Endpoint Configuration Manager版本必須至少為 1706 或更新版本。 我們建議您使用 1710 或更高版本。 如需[有關 Configuration Manager Windows 10](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)支援，請Windows 10 Configuration Manager 支援的版本。

-   必須安裝適用于 Windows的 ADK (及部署套件) Windows 10版本。 請參閱適用于不同Windows 10的[ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本，並確保您的部署包含正確的版本。

-   網站系統伺服器必須已指派通訊點角色，且啟動映射應啟用前啟動執行環境 ([PXE) ](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) 支援，以啟用網路啟動部署。 如果未啟用 PXE 支援，您可以使用可啟動的 [媒體進行部署](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 。

-   網路存取帳戶必須配置為支援新電腦 (部署) 案例。 若要深入瞭解網路存取帳戶的組組，請參閱 Configuration [Manager 中使用的帳戶](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

-   建議您啟用[多](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)播支援 ，如果您可能同時將相同的Microsoft Teams 會議室映射部署到多個單位。

### <a name="networking-requirements"></a>網路需求

-   您的網路應該具有動態主機組態通訊協定 (DHCP) 伺服器，其為自動 IP 位址分配所配置的子網，Microsoft Teams 會議室單元將部署。

    > [!NOTE]
    > DHCP 租賃持續時間必須設定為超過影像部署持續時間的值。 否則，部署可能會失敗。

-   您的網路 ，包括交換器和虛擬 LANs (VLANs) ，應該會配置為支援 PXE。 請參閱您的網路廠商，以瞭解有關 IP Helper 和 PXE 組配置的資訊。 或者，如果 [未啟用](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) PXE 支援，您也可以使用可啟動媒體進行部署。

    > [!NOTE]
    > 針對 Surface Pro，只有在使用 Microsoft 的乙太網路介面卡或固定基座 (PXE) 才能從網路啟動。 協力廠商乙太網路介面卡不支援使用 PXE Surface Pro。 請參閱 [乙太網路介面卡和 Surface 部署](/surface/ethernet-adapters-and-surface-device-deployment) 以瞭解更多資訊。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>設定Microsoft Endpoint Configuration Manager部署

本文假設您已經擁有正常的 Configuration Manager 部署，而且不會詳述從頭部署和設定 Configuration Manager 所需的所有步驟。 檔[與組Microsoft Endpoint Configuration Manager](/configmgr/)是很好的資源;如果您尚未部署 Configuration Manager，建議您從這些資源開始。

請使用下列指示來確認作業系統部署 (OSD) 功能已正確配置。

### <a name="validate-and-upgrade-configuration-manager"></a>驗證及升級 Configuration Manager

1.  在 Configuration Manager 主控台中，前往 **管理** \> **更新和服務**。

2.  檢查已安裝的建和尚未安裝的適用更新。

3.  在 [Configuration Manager 中Windows 10支援;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)如果您需要升級部署，請選取要安裝的更新，然後選取 **下載**。

4.  下載完成後，選取更新，然後選取安裝 **更新套件**。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>設定發佈點以支援 PXE 和多播

1.  在 Configuration Manager 主控台中，前往 **系統** \> **管理發佈點**。

2.  選取將提供部署服務的通訊Microsoft Teams 會議室伺服器，**然後選取** 屬性 。

3.  選取 **PXE** Tab，並確保已啟用下列設定：
    -   啟用用戶端的 PXE 支援
    -   允許此通訊點回應傳入的 PXE 要求
    -   啟用未知的電腦支援

4.  *選擇性：* 若要啟用多播支援，請選取 **多重廣播** 選項卡，並確保已啟用下列設定：
    -   啟用多播以同時將資料傳送至多個用戶端
    -   根據網路小組的建議設定 UDP 埠範圍

### <a name="configure-the-network-access-account"></a>設定網路存取帳戶

1.  在 Configuration Manager 主控台中，前往 **管理** \> **網站組組** \> **網站**，然後選取網站。

2.  在 **設定群組** 中，選取 **設定網站元件** \> **軟體發佈**。

3.  選取網路 **存取帳戶選項卡** 。設定一或多個帳戶， **然後選取確定**。

> [!NOTE]
> 除了在通訊點伺服器上從網路存取此電腦之外，帳戶不需要任何特殊許可權。 適合使用一般網域使用者帳戶。 詳細資訊，請參閱 [Configuration Manager 中使用的帳戶](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

### <a name="configure-a-boot-image"></a>設定開機圖像

1.  在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **啟動映射**。

2.  選取 **x64 (的)**， **然後選取** 屬性 。

3.  選取 **資料來源選項卡，** 然後從啟用 **PXE** 的通訊點啟用部署此啟動映射。

4.  選取選擇性 **元件選項卡** 以安裝必要的元件：

    1.  選取星號圖示，然後搜尋 **WINPE-HTA** (HTML) 

    2.  選取 **確定** ，將 HTML 應用程式支援新增到啟動映射中。

5.  *選擇性：* 若要自訂部署體驗，請選取自訂 **選項卡** 。
    -   若要 **在部署期間 (命令** 提示) ，才啟用命令支援以進行測試。 啟用此功能後，您隨時都可以在部署期間選取 **F8，** 以啟動命令提示。
    -   您也可以指定部署期間要顯示的自訂背景影像。 若要設定影像，請啟用在 UNC 路徑 (**自訂背景圖像檔案** ，然後選取您的背景。

6.  當系統詢問時，請選取 **是** ，並將更新的啟動映射發佈至您的發佈點。

詳細資訊，請參閱使用 [Configuration Manager 管理啟動映射](/configmgr/osd/get-started/manage-boot-images)。

> [!NOTE]
> 您可以建立可啟動的 USB 媒體，針對沒有 PXE 支援的環境啟動 Configuration Manager 工作順序型部署。 可啟動的媒體僅包含啟動映射、選擇性的啟動前命令及其所需檔案，以及 Configuration Manager 二進位檔案，可支援啟動至 Windows PE，並連接到 Configuration Manager 以執行其餘的部署程式。 詳細資訊，請參閱 [建立可啟動的媒體](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。

## <a name="create-configuration-manager-packages"></a>建立 Configuration Manager 套件

> [!IMPORTANT]
> 每個 SRS 安裝程式版本所需的作業系統版本會隨著每個 MSI 版本而變更。 若要判斷給定 MSI 的最佳作業系統版本，請執行一次主控台設定腳本。 若要深入瞭解，請參閱使用 Microsoft Teams 會議室[部署Microsoft Endpoint Configuration Manager。](rooms-scale.md)

Configuration Manager 需要許多套件來部署及設定Microsoft Teams 會議室單位。

您需要建立並設定下列套件，然後將這些套件發佈至已指派通訊點伺服器角色的 Configuration Manager 網站系統。

| **套件名稱**                     | **類型**               | **描述**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS 應用程式套件     | 套裝軟體       | 適用于部署套件Microsoft Teams 會議室套件                                      |
| SRS v2 - Sysprep 套件             | 套裝軟體       | 自訂裝置套件Unattended.xml設定Microsoft Teams 會議室單位            |
| SRS v2 - Set-SRSComputerName套件 | 套裝軟體       | HTML 應用程式套件 (HTA) 在部署期間指派電腦名稱稱    |
| SRS v2 - 設定 SRS 設定         | 套裝軟體       | 套件以設定應用程式Microsoft Teams 會議室部署                          |
| SRS v2 - OS 更新套件          | 套裝軟體       | 部署強制作業系統更新的套件                                      |
| SRS v2 - 根憑證套件    | 套裝軟體       | 選擇性 - 部署根憑證的套件 (網域聯入單位所不需要的)   |
| SRS v2 - Microsoft Monitoring Agent套件 | 套裝軟體       | 選擇性 - 套件以部署及設定 Microsoft Operations Management Suite 代理程式|
| SRS v2 - WinPE 背景套件    | 套裝軟體       | 自訂背景影像套件，以用於開機影像                           |
| Windows 10 企業版                | 作業系統圖像 | 安裝安裝檔案套件 (.wim)                           |
| Surface Pro                          | 驅動程式套件         | 適用于 Microsoft Surface Pro                     |
| Surface Pro 4                        | 驅動程式套件         | 適用于 Microsoft Surface Pro 4                   |

詳細資訊，請參閱 [Configuration Manager 中的套件和程式](/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="create-folders-for-the-package-source-files"></a>建立套件來源檔案的資料夾

Configuration Manager 要求當套件來源檔案第一次建立及更新時，以特定資料夾結構整理。

在系統管理中心或主Microsoft Endpoint Configuration Manager，或您用於託管套件來源檔案的伺服器共用上建立下列資料夾結構：

-   SRS v2 - Microsoft Monitoring Agent套件
-   SRS v2 - OS 更新套件
-   SRS v2 - 根憑證套件
-   SRS v2 - Set-SRSComputerName套件
-   SRS v2 - SRS 應用程式套件
-   SRS v2 - 設定 SRS 設定
-   SRS v2 - Sysprep 套件
-   司機
    -   Surface Pro
    -   Surface Pro 4
-   作業系統
    -   Windows 10 企業版

> [!TIP]
> 您也可以下載 [並使用](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) zip 檔案，其中包含套件的資料夾結構、您需要使用的腳本，以及您需要輸入的工作順序範本。

### <a name="create-the-monitoring-agent-package"></a>建立監控代理程式套件

1. 從 下載監控代理程式 <https://go.microsoft.com/fwlink/?LinkId=828603> 。

2. 開啟命令提示視窗，Microsoft Monitoring Agent **/C：** 在命令提示符中輸入 /C，將套件解壓縮到 **SRS v2 -** Microsoft Monitoring AgentMMASetup-AMD64.exe套件資料夾。

3. 在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

4. 輸入下列資訊以建立套件：

   - 名稱<strong>：SRS v2 - Microsoft Monitoring Agent套件</strong>

   - 製造商<strong>：Microsoft Corporation</strong>

   - 版本<strong>：8.1.11081.0</strong> (輸入下載的安裝檔案) 

   - 選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 -** Microsoft Monitoring Agent套件資料夾的路徑，然後選取下一 **步**。

5. 選取 **不建立程式**，然後選取 下 **一步**。

6. 查看確認 **設定頁面** ，然後選取下 **一步**。

7. 選取 **關閉**。

### <a name="create-the-operating-system-updates-package"></a>建立作業系統更新套件

1. 在 **SRS v2 - OS 更新套件** 資料夾中，建立名為Install-SRSv2-OS-Updates.ps1 **的新 PowerShell 腳本**。

2. 將下列腳本 **複製到Install-SRSv2-OS-Updates.ps1腳本** 。 或者，您可以從這裡下載Install-SRSv2-OS-Updates.ps1[腳本。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. 將必填Windows更新套件下載至同一個資料夾。
   > [!NOTE]
   > 本文發佈時，只需要[KB4056892。](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 檢查[設定Microsoft Teams 會議室](console.md)主控台，以查看是否需要任何其他更新。

4. 在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

5. 輸入下列資訊以建立套件：
   -   名稱 **：SRS v2 – OS 更新套件**
   -   製造商 **：Microsoft Corporation**
   -   版本 **：1.0.0**
   -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - OS 更新套件** 資料夾的路徑，然後選取下 **一步**。

6. 選取 **不建立程式**，然後選取 下 **一步**。

7. 查看確認 **設定頁面** ，然後選取下 **一步**。

8. 選取 **關閉**。

### <a name="create-the-root-certificate-package-optional"></a>建立根憑證套件 (選項) 

您可以建立此套件，以發佈不會加入 Active Directory 網域之裝置之根憑證。 只有在同時套用下列兩個條件時，才能建立此套件：
-   您的部署包括內部部署 Lync 或 商務用 Skype Server。
-   Microsoft Teams 會議室單位已配置為在工作組中工作，而非網域成員。

1.  將根憑證複製到 **SRS v2 – 根憑證套件** 資料夾。

2.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

3.  輸入下列資訊以建立套件：
    -   名稱 **：SRS v2 – 根憑證套件**
    -   製造商 *：貴組織的名稱*
    -   版本 **：1.0.0**
    -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – 根憑證套件** 資料夾的路徑，然後選取下 **一步**。

4.  選取 **不建立程式**，然後選取 下 **一步**。

5.  查看確認 **設定頁面** ，然後選取下 **一步**。

6.  選取 **關閉**。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>建立Microsoft Teams 會議室套件

1.  從 下載最新版本的 **Microsoft Teams 會議室套件** <https://go.microsoft.com/fwlink/?linkid=851168> ，然後安裝至工作站。

2.  從 C 複製內容：將 **\\ x86 \\** (程式檔案) Skype會議室系統部署套件至 **SRS v2 - SRS** 應用程式套件資料夾。

3.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

4.  輸入下列資訊以建立套件：
    -   名稱 **：SRS v2 – SRS 應用程式套件**
    -   製造商 **：Microsoft Corporation**
    -   版本 **：3.1.104.0** (輸入下載的安裝檔案) 
    -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – SRS 應用程式套件** 資料夾的路徑，然後選取下 **一步**。
5.  選取 **不建立程式**，然後選取 下 **一步**。

6.  查看確認 **設定頁面** ，然後選取下 **一步**。

7.  選取 **關閉**。

### <a name="create-the-computer-name-assignment-package"></a>建立電腦名稱稱工作分派套件

1.  在 **SRS v2 - Set-SRSComputerName套件** 資料夾中，建立名為 **Set-SRSComputerName.hta 的新 HTML 應用程式** 。

2.  將下列腳本複製到 **Set-SRSComputerName.hta** 檔案。 或者，您也可以從這裡下載 Set-SRSComputerName.hta [檔案](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)。
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

4.  輸入下列資訊以建立套件：

    -   名稱 **：SRS v2 - Set-SRSComputerName套件**

    -   製造商 **：Microsoft Corporation**

    -   版本 **：1.0.0**

    -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - Set-SRSComputerName套件資料夾** 的路徑，然後選取下一 **步**。

5.  選取 **不建立程式**，然後選取 下 **一步**。

6.  查看確認 **設定頁面** ，然後選取下 **一步**。

7.  選取 **關閉**。

### <a name="create-the-sysprep-package"></a>建立 Sysprep 套件

1. 在 **SRS v2 – Sysprep 套件** 資料夾中，建立名為Unattend.xml **的新 XML 檔案** 。

2. 將下列文字複製到 **Unattend.xml檔案。** 或者，您也可以從這裡下載[Unattend.xml檔案。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. 在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

4. 輸入下列資訊以建立套件：
   -   名稱 **：SRS v2 - Sysprep 套件**
   -   製造商 **：Microsoft Corporation**
   -   版本 **：1.0.0**
   -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 – Sysprep 套件** 資料夾的路徑，然後選取下一 **步**。
5. 選取 **不建立程式**，然後選取 下 **一步**。

6. 查看確認 **設定頁面** ，然後選取下 **一步**。

7. 選取 **關閉**。

### <a name="create-the-windows-10-enterprise-package"></a>建立Windows 10 企業版套件

1.  取得Windows 10 企業版 x64 媒體，然後將 **install.wim** 檔案複製到作業系統 **\\ Windows 10 企業版** 資料夾。

2.  在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **映射**，然後選取新增 **作業系統映射**。

3.  指定您剛剛複製 **的 install.wim** 檔案路徑，然後選取下 **一步**。

4.  更新版本 **欄位** 以符合影像的Windows 10 企業版編號，然後選取下一 **步**。

5.  請閱 **閱詳細資料** 頁面，然後選取下 **一步**。

6.  選取 **關閉**。

詳細資訊，請參閱使用 [Configuration Manager 管理 OS 映射](/configmgr/osd/get-started/manage-operating-system-images)。

### <a name="create-surface-pro-device-driver-packages"></a>建立Surface Pro驅動程式套件

Microsoft Teams 會議室支援Surface Pro Surface Pro 4。 您需要為環境中擁有的每個Surface Pro建立驅動程式套件。

> [!IMPORTANT]
> 驅動程式必須與部署套件Windows 10 企業版版本Microsoft Teams 會議室相容。 若要詳細資訊，請參閱 [下載 Surface](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 裝置的最新固件和驅動程式，以及 [設定主機](console.md)。

1.  下載最新的驅動程式和固件。
    -   適用于Surface Pro：<https://www.microsoft.com/download/details.aspx?id=55484>
    -   適用于Surface Pro 4：<https://www.microsoft.com/download/details.aspx?id=49498>

2.  解壓縮下載的驅動程式和固件。 開啟命令提示視窗，在命令提示符輸入下列其中一個命令：
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **驅動程式**，然後選取匯出 **驅動程式**。

4.  選取 **下列** 網路路徑 (UNC) 中所有驅動程式，選取來源資料夾 (例如 C：_Sources 驅動程式Surface Pro) ，然後選取下 \\ \\ \\ 一步。

5.  在指定 **已輸入驅動程式詳細** 資料頁面上，選取所有列出的驅動程式，然後選取啟用這些驅動程式並允許 **電腦安裝。**

6.  選取 **類別**，建立符合 Surface 模型的新類別， **選取確定，** 然後選取下 **一步**。

7.  選取 **新套件**。

8.  指定與模型Surface Pro的套件名稱、輸入資料夾路徑以將驅動程式套件檔案儲存在中、選取確定，然後選取下一 **步**。 

9.  在啟動 **影像** 頁面上，確保未選取任何開機影像，然後選取下 **一步**。

10. 選取 **關閉**。

11. 前往 **軟體文檔** 庫作業系統驅動程式，選取資料夾建立資料夾，然後輸入符合您剛剛Surface Pro驅動程式之資料夾模型 \>  \> 的資料夾名稱。 **\>**

12. 將所有已輸入的驅動程式移至新建立的資料夾，以便更輕鬆地流覽和操作。

> [!NOTE]
> 針對您可能擁有的其他Surface Pro重複相同的步驟。 詳細資訊，請參閱在 [Configuration Manager 中管理驅動程式](/configmgr/osd/get-started/manage-drivers)。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>建立Microsoft Teams 會議室套件

1.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **應用程式管理** \> **套件**，然後選取建立 **套件**。

2.  輸入下列資訊以建立套件：

    -   名稱 **：SRS v2 - 設定 SRS 安裝套件**

    -   製造商 **：Microsoft Corporation**

    -   版本 **：1.0.0**

    -   選取此 **套件包含來源檔案** 核取方塊，輸入 **SRS v2 - 設定 SRS 安裝程式** 資料夾的路徑，然後選取下一 **步**。

3.  選取 **不建立程式**，然後選取 下 **一步**。

4.  查看確認 **設定頁面** ，然後選取下 **一步**。

5.  選取 **關閉**。



## <a name="distribute-configuration-manager-packages"></a>發佈 Configuration Manager 套件

所有套件都必須分散到已在 Configuration Manager 階層中指派通訊點角色的伺服器。 請遵循下列指示來啟動套件發佈。

1.  發佈軟體套件。

    1.  在 Configuration Manager 主控台中，前往 **軟體庫** \> **應用程式管理** \> **套件**。 選取您想要發佈的所有軟體套件，然後選取 發佈 **內容**。

    2.  查看套件清單，然後選取下 **一步**。

    3.  視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。

    4.  選取 **下一** 步，然後 **選取** 關閉 。

2.  發佈驅動程式套件。

    1.  在 Configuration Manager 主控台中，前往 **軟體庫** \> **作業系統** \> **驅動程式套件**。 選取所有要散發的驅動程式套件，然後選取發佈 **內容**。

    2.  查看套件清單，然後選取下 **一步**。

    3.  視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。

    4.  選取 **下一** 步，然後 **選取** 關閉 。

3.  發佈作業系統套件。

    1.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **映射**。 選取您想要發佈的所有作業系統影像，然後選取發佈 **內容**。

    2.  查看套件清單，然後選取下 **一步**。

    3.  視您的 Configuration Manager 階層 (將所有通訊點伺服器新) 到清單中，然後選取下一 **步**。

    4.  選取 **下一** 步，然後 **選取** 關閉 。

> [!NOTE]
> 套件發佈可能需要一些時間，視封裝大小、Configuration Manager 階層、通訊點伺服器數量，以及您的網路可用頻寬而不同。
> 
> 您必須先發佈所有套件，才能開始部署Microsoft Teams 會議室裝置。
> 
> 您可以到監控發佈狀態內容狀態，在 Configuration Manager 主控台中查看 \> **套件** \> **發佈的狀態**。

## <a name="configuration-manager-task-sequences"></a>Configuration Manager 工作順序

您可以與 Configuration Manager 一起使用工作順序來自動化將作業系統映射部署到目的電腦的步驟。 若要以Microsoft Teams 會議室方式部署 Microsoft Teams 會議室 裝置，請建立參照啟動映射的工作順序，以啟動目的地 Microsoft Teams 會議室 電腦、您想要安裝的 Windows 10 企業版 作業系統映射，以及任何其他內容 ，例如其他應用程式或軟體更新。

### <a name="import-the-sample-task-sequence"></a>輸入範例工作順序

您可以下載並輕鬆輸入範例工作順序，並自訂以滿足您的需求。

1.  [**下載**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 範例工作順序，然後將下載的 zip 檔案複製到共用位置。
2.  在 Configuration Manager 主控台中，前往 **軟體文件庫** \> **作業系統** \> **工作順序**，然後選取匯出 **工作順序**。

3.  選取 **流覽**，前往您用於步驟 1 的共用資料夾位置，選取 Microsoft Teams 會議室 部署 (**EN-US) .zip** 檔案，然後選取下一 **步**。

4.  將 **動作** 設定 **為建立新**，然後選取下 **一步**。

5.  確認設定，然後選取下 **一步**。

6.  選取 **關閉**。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>驗證參考套件是否正確連結至每個工作順序步驟。

1. 選取已輸入的工作順序， **然後選取** 編輯 。

    工作順序編輯器隨即開啟並顯示部署及設定單一裝置所需的Microsoft Teams 會議室步驟。

2. 逐步完成每個步驟並完成建議的更新：

   1. **在 PE Windows** 重新開機：此步驟會重新開機，然後將電腦引導至 Windows PXE。 此步驟不需要變更。

   2. **分區磁片 0 – UEFI：** 此步驟會抹去磁片設定，並依據設定設定建立分區。 建議您不要對此步驟進行任何變更。

   3. **設定 SRS 電腦名稱稱**：此步驟包含 HTML 應用程式，提供 UI 以在部署期間為 Microsoft Teams 會議室 裝置設定電腦名稱稱。
      -  這是一個選擇性的步驟，但只有在您想要透過替代程式管理電腦命名時，才能停用此步驟。
      -  確認已 **選取 SRS v2 - Set-SRSComputerName** 套件。 如果沒有，請流覽至套件並選取它。

   4. **應用程式作業系統**：此步驟會指定要部署的作業系統映射，以及要使用無人值守的 Sysprep 答案檔案。
      -  確認已選取Windows 10 企業版作業系統圖像檔案。
      -  確認已啟用自訂安裝的無人值守或 **Sysprep** 答案檔案，且已選取 **SRS v2 - Sysprep 套件** 。 此外，也請確保 **將** 檔案名設為 **unattend.xml。**

   5. **應用程式Windows 設定：** 此步驟會收集安裝Windows相關資訊。
      -  根據您的需求提供授權和註冊資訊，包括產品金鑰、本地系統管理員帳戶密碼 (時區) 。

   6. **將網路設定：** 此步驟可讓您指定工作組或 Active Directory 功能變數名稱和組織單位。
      > [!NOTE]
      > 請參閱[Skype會議室系統](domain-joining-considerations.md)網域加入考慮，瞭解您以 Actve Directory 網域成員Microsoft Teams 會議室部署裝置時需要採取的建議動作。
   7. **適用驅動程式：** 此步驟及其子步驟會依據您擁有的版本模型，Surface Pro部署適用的裝置驅動程式和固件。 更新每個步驟以指定與此部署相關聯的相關驅動程式套件。
      -   每個驅動程式套件都經過配置，Windows管理工具 (WMI) 篩選，根據產品與Surface Pro部署相關的驅動程式和Surface Pro。
      -   我們強烈建議您不要變更這些驅動程式的組配置，否則部署可能會失敗。

   8. **設定和Windows** 管理員：此步驟會部署及設定 Configuration Manager 用戶端。 更新此步驟以指定內建的 Configuration Manager 用戶端套件。

   9. **安裝根憑證**：此步驟會發佈未加入網域的裝置之根憑證，因此預設為選擇性且停用。
      -   如果您需要將根憑證部署到每個單元，Microsoft Teams 會議室步驟。
      -   如果您需要執行此步驟，請確認已選取 **SRS v2 -** 根憑證套件和停用 **64 位** 檔案系統重新導向。

   10. **安裝和設定監控代理** 程式：此步驟會安裝 64 位版本的 Microsoft Azure 監視器代理程式，並設定代理程式以連接到您的記錄分析工作區。
       -   此步驟預設為停用。 只有在您打算使用監控代理程式監控您的裝置健康情況時，才能Microsoft Teams 會議室步驟。
       -   編輯此步驟並更新命令列參數，以指定 **您的工作區識別碼** 和 **工作區金鑰**。
       -   請參閱 [設定 Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 監控的測試裝置，以取得操作管理套件工作區識別碼和主鍵詳細資訊。
       -   確認已 **選取 SRS v2 – Microsoft Monitoring Agent套件** 和停用 **64 位檔案系統重新導向**。
       -   有關監控您的 Microsoft Teams 會議室 部署健康情況詳細資訊，請參閱使用 Azure[監視器](azure-monitor-plan.md)規劃 Microsoft Teams 會議室 管理、使用[Azure 監視器](azure-monitor-deploy.md)部署 Microsoft Teams 會議室 管理，以及使用[Azure 監視器](azure-monitor-manage.md)管理 Microsoft Teams 會議室 裝置。

   11. **複製 SRS v2 組** Microsoft Teams 會議室：此步驟會從部署套件將所需的設定和組Microsoft Teams 會議室複製到本地硬碟。 此步驟不需要自訂。
       -   確認已 **選取 SRS v2 - SRS 應用程式套件** 和 **停用 64 位檔案系統重新** 導向。

   12. **Install-SRSv2-OS-Updates：** 此步驟會部署任何必要的作業系統更新，Microsoft Teams 會議室部署。 請執行下列動作：
       -   檢查[設定Microsoft Teams 會議室主控台](console.md)以查看需要哪些更新。
       -   確認您的 **SRS v2 – OS 更新套件** 包含所有必要的更新。
       -   確認已 **選取 SRS v2 – OS 更新** 套件。
       -   確認 PowerShell 執行策略設定為旁 **路**。

   13. **重新開機電腦**：此步驟在安裝強制作業系統更新之後，會重新開機電腦。 此步驟不需要自訂。

   14. **設定Windows元件**：此步驟會設定Windows功能。 此步驟不需要自訂。

   15. **重新開機電腦**：此步驟會重新開機電腦，Windows功能之後。 此步驟不需要自訂。

   16. **新增本地Skype** 使用者：此步驟會建立Skype帳戶，用來自動Windows並啟動Microsoft Teams 會議室應用程式。 此步驟沒有任何相關聯的軟體套件，而且不需要自訂。

   17. **設定及設定 SRS 應用程式**：此步驟會Microsoft Teams 會議室作業系統的下一次啟動時設定應用程式安裝。
       -   確認已 **選取 SRS v2 - 設定 SRS 設定套件** 和停用 **64 位** 檔案系統重新導向。

> [!IMPORTANT]
> 工作順序步驟必須按照提供的順序進行，這一點非常重要。 修改步驟順序或配置其他步驟可能會中斷部署。
>
> **設定及設定 SRS 應用程式** 步驟必須是工作順序的最後一個步驟，否則部署可能會失敗。

### <a name="create-deployment-for-the-task-sequence"></a>建立任務順序的部署

1. 選取工作順序， **然後選取** 部署 。

2. 選取 **流覽** 以選取要部署的目標集合。

3. 選取 **所有未知電腦** ，然後選取 **確定**。

4. 選取 下 **一個**。

5. 在 **用途** 下 **拉清單中** 選取可用的選項。

6. 在下列清單中選取只有媒體和 **PXE，** 然後選取下一 **步**。 
   > [!WARNING]
   > 將用途 **設定為可用****非常重要。** 請確定用途 **未****設為必要的****。** 此外，請確定您選取 **的只有媒體和 PXE** 在下列的可用 **中**。
   >
   > 將這些值設定為其他專案可能會導致所有電腦在開機Microsoft Teams 會議室取得部署映射。
7. 請勿指定任何排程，然後選取下 **一步**。

8. 請勿在使用者體驗區段內 **變更任何** 專案，並選取下 **一步**。

9. 請勿在通知 **區段內** 變更任何內容，然後選取下 **一步**。

10. 請勿變更通訊點區段內 **的內容** ，然後選取下 **一步**。

11. 確認設定，然後選取下 **一步**。

12. 選取 **關閉**。

**驗證和疑難排解解決方案**

完成任務順序Microsoft Endpoint Configuration Manager，您必須執行測試執行，以驗證任務順序可以部署及設定Microsoft Teams 會議室單位。

1.  連線其中一個支援的乙太網路介面卡，或使用 Surface Dock，將測試裝置連接到有線網路。 如果 PXE 啟動功能尚未針對您的環境進行配置，您可以使用您先前所建立 USB 快閃磁碟機上的啟動[](/configmgr/osd/deploy-use/create-bootable-media)映射，從 USB 啟動並連接到 Configuration Manager。

2.  存取固件並啟動 PXE 啟動：

    1.  請確保 Surface 裝置已關閉電源。

    2.  按住向上 **音量** 按鈕。

    3.  按並放開 **Power** 按鈕。

    4.  裝置開始啟動後，放開 **音量增加** 按鈕。

    5.  選取 **啟動組配置**。

    6.  執行下列其中一項：

        -   選取 **PXE 啟動**，然後將它拖曳到清單頂端。 或者，您也可以在網路介面卡上向左滑動，以立即啟動至裝置。 這不會影響啟動順序。
        -   選取保留啟動媒體的 USB 快閃磁碟機。

3.  選取 **離開**，然後選取 立即 **重新開機**。

4.  當系統提示時，選取 **Enter** 進行網路開機服務。

5.  WindowsPE 會載入至記憶體，而工作順序精靈會啟動。 選取 **下一** 步以繼續。

6.  選取您先前所輸入的工作順序，然後選取下 **一步**。

7.  在已應用磁片組配置之後，系統會提示您指定裝置的電腦名稱稱。 使用者介面會根據裝置上的序號顯示Surface Pro名稱。 您可以接受建議的名稱，或指定新的名稱。 請遵循電腦名稱稱作業畫面上的指示。 當您選取接受 **時**，部署即會開始。

8.  其餘的部署程式是自動的，不需要使用者輸入。

9.  部署工作順序設定完成裝置之後，會看到下列設定畫面，要求您設定Microsoft Teams 會議室設定。

    ![應用程式的初始設定Microsoft Teams 會議室畫面。](../media/room-systems-scale-image2.png)

10.  將Surface Pro插入Microsoft Teams 會議室主控台，然後設定應用程式設定。

11.  驗證已部署Microsoft Teams 會議室[中所列的](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)功能是否可執行。


若要針對安裝失敗進行疑難排解，請檢查 **SMSTS.log** 檔案，該檔案會記錄在 Configuration Manager 工作順序中執行的所有步驟。

SMSTS.log 檔案會儲存在多個路徑的其中一個，視建立程式階段而不同。 檢查下表，找出 SMSTS.log 檔案的路徑。


| **部署階段**                                                            | **任務順序記錄路徑**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WINPE，在 HDD 格式之前                                                        | \\X：Windows temp \\ \\ smstslog \\ smsts.log             |
| WINPE，在 HDD 格式之後                                                         | \\C：_SMSTaskSequence \\ \\ 記錄 Smstslog \\ smsts.log    |
| 在安裝 Configuration Manager 代理程式之前部署的作業系統 | \\c：_SMSTaskSequence \\ \\ 記錄 Smstslog \\ smsts.log    |
| 已部署作業系統和 Configuration Manager 代理程式                   | %windir% \\ System32 \\ ccm \\ log \\ Smstslog \\ smsts.log |
| 任務循序執行完成                                                | %windir% \\ System32 \\ ccm \\ log \\ smsts.log           |

> [!TIP]
> 在工作順序期間，您隨時都可以選取 **F8** 以開啟命令主控台，然後存取 SMSTS.log 檔案。

若要疑難排解 PXE 啟動問題，請檢查 Configuration Manager 伺服器上 PXE 動作特有的兩個記錄檔案：

-   位於 Configuration Manager 安裝記錄目錄中的 **Pxecontrol.log**

-   **Smspxe.log**，位於 Configuration Manager Management Point (MP) 目錄

若要進一步疑難排解您的 Configuration Manager 安裝問題，請參閱記錄Microsoft Endpoint Configuration Manager[的完整記錄檔案清單](/configmgr/core/plan-design/hierarchy/log-files)。
