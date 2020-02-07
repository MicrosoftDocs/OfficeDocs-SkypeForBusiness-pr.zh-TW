---
title: 使用 Microsoft 端點 Configuration Manager 部署 Microsoft 團隊聊天室
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 請閱讀本主題，瞭解如何在大規模部署中部署 Microsoft 團隊會議室。
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
ms.openlocfilehash: eb1e4337f97f16df6d7ef039bf4ba095ed692995
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827921"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft 端點 Configuration Manager 部署 Microsoft 團隊聊天室

本文提供使用 Microsoft 端點設定管理員建立 Microsoft 團隊聊天室部署的所有必要資訊。

透過 Configuration Manager 提供的便於使用的方法，您可以將作業系統及其他應用程式部署到多個目標裝置。

使用下面所示的方法引導您完成 Configuration Manager 設定，並視貴組織的需求自訂整個本指南所提供的範例套件與腳本。

![使用 Configuration Manager 的 Microsoft 團隊聊天室部署程式](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 此解決方案只經過以 Surface Pro 式部署進行測試。 針對不是以 Surface Pro 為基礎的設定，請遵循製造商的指導方針。

## <a name="validate-prerequisites"></a>驗證先決條件

若要使用 Configuration Manager 來部署 Microsoft 團隊聊天室，請確定您符合下列先決條件及需求。

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration 管理員需求

-   Microsoft 端點 Configuration Manager 版本必須至少為1706或更新版本。 我們建議使用1710或更新版本。 請參閱[Configuration manager 中的 windows 10 支援](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)，以瞭解 configuration manager 支援的 windows 10 版本。

-   必須安裝適用于 Windows 10 的 Windows 評估版和部署套件（ADK）版本。 請參閱您可以搭配不同版本 Configuration Manager 使用的[Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk)版本，並確保您的部署包含正確的版本。

-   網站系統伺服器必須已獲指派發佈點角色，且應啟用啟動影像以進行[開機前執行環境（PXE）支援](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network)，才能啟用網路啟動的部署。 如果未啟用 PXE 支援，您可以針對您的部署使用[可引導媒體](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)。

-   必須將網路存取帳戶設定為支援新的電腦（裸機）部署案例。 若要深入瞭解網路存取帳戶的設定，請參閱[Configuration Manager 中使用的帳戶](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

-   如果您很可能同時將相同的 Microsoft 團隊會議室影像部署到多個單元，建議您啟用[多播支援](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)。

### <a name="networking-requirements"></a>網路需求

-   您的網路應該有一個動態主機設定通訊協定（DHCP）伺服器，該伺服器是針對自動 IP 位址分配，將其部署到 Microsoft 團隊會議室單元的子網。

    > [!NOTE]
    > DHCP 租約期限必須設定為超過映射部署持續時間的值。 否則，部署可能會失敗。

-   您的網路（包括交換器和虛擬 Lan （Vlan））應該設定為支援 PXE。 如需 IP 協助程式和 PXE 設定的詳細資訊，請參閱您的網路廠商。 或者，如果沒有啟用 PXE 支援，您也可以將[可引導媒體](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)用於部署。

    > [!NOTE]
    > 在 Surface Pro 裝置上，只有當您使用乙太網路介面卡或來自 Microsoft 的插接站時，才支援從網路啟動（PXE 啟動）。 協力廠商乙太網路介面卡不支援使用 Surface Pro 進行 PXE 啟動。 如需詳細資訊，請參閱[乙太網路介面卡與 Surface 部署](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)。

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>針對作業系統部署設定 Microsoft 端點 Configuration Manager

本文假設您已經有良好的 Configuration Manager 部署，而且不會詳細說明部署和設定 Configuration Manager 的所有步驟所需的步驟。 Microsoft 端點設定管理員的[檔和設定指導](https://docs.microsoft.com/configmgr/)方針是一種很好的資源;如果您尚未部署 Configuration Manager，我們建議您從這些資源開始。

使用下列指示確認作業系統部署（OSD）功能已正確設定。

### <a name="validate-and-upgrade-configuration-manager"></a>驗證和升級 Configuration Manager

1.  在 Configuration Manager 主控台中，移至 [**管理** \> **更新及服務**]。

2.  檢查已安裝的組建以及尚未安裝的適用更新。

3.  [在 Configuration Manager 中查看 Windows 10 版支援](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client);如果您需要升級您的部署，請選取您要安裝的更新，然後選取 [**下載**]。

4.  下載完成後，請選取更新，然後選取 [**安裝更新套件**]。

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>設定發佈點以支援 PXE 和多播

1.  在 Configuration Manager 主控台中，移至 [**管理** \> **發佈點**]。

2.  選取將提供 Microsoft [小組聊天室] 部署的發佈點伺服器，然後選取 [**屬性**]。

3.  選取 [ **PXE** ] 索引標籤，並確認已啟用下列設定：
    -   為用戶端啟用 PXE 支援
    -   允許此發佈點回應傳入的 PXE 要求
    -   啟用未知電腦支援

4.  *選用：* 若要啟用多播支援，請選取 [**多播**] 索引標籤，並確認已啟用下列設定：
    -   啟用多播以同時傳送資料給多個用戶端
    -   根據您的網路小組的建議設定 UDP 埠範圍

### <a name="configure-the-network-access-account"></a>設定網路存取帳戶

1.  在 Configuration Manager 主控台中，移至 [**管理** \> **網站** \>設定**網站**]，然後選取 [網站]。

2.  在 [**設定**] 群組中，選取 [**設定網站元件** \> **軟體發佈**]。

3.  選取 [**網路存取帳戶**] 索引標籤。設定一或多個帳戶，然後選取 **[確定]**。

> [!NOTE]
> 帳戶不需要任何特殊權利，除了從發佈點伺服器的 [**從網路存取此電腦**] 許可權以外。 一般網域使用者帳戶將是適當的。 如需詳細資訊，請參閱[Configuration Manager 中使用的帳戶](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)。

### <a name="configure-a-boot-image"></a>設定啟動影像

1.  在 Configuration Manager 主控台中，移至**軟體庫** \> **作業系統** \> **啟動影像**。

2.  選取 **[啟動影像（x64）**]，然後選取 [**屬性**]。

3.  選取 [**資料來源**] 索引標籤，然後**從啟用 PXE 的發佈點啟用此啟動影像**。

4.  選取 [**選用元件**] 索引標籤來安裝必要的元件：

    1.  選取 [星形] 圖示，然後搜尋 **[HTML （WinPE-HTA）** ]

    2.  選取 **[確定]** ，將 HTML 應用程式支援新增至啟動影像。

5.  *選用：* 若要自訂部署體驗，請選取 [**自訂**] 索引標籤。
    -   如果您想要在部署期間存取命令提示字元，請啟用**命令支援（僅限測試）** 。 啟用此功能時，您可以在部署期間的任何時間選取**F8**來啟動命令提示字元。
    -   您也可以指定要在部署期間顯示的自訂背景圖像。 若要設定影像，請啟用 **[指定自訂背景圖像檔案（UNC 路徑**）]，然後選取您的背景。

6.  出現提示時，請選取 **[是]** ，然後將更新的啟動影像發佈到您的發佈點。

如需詳細資訊，請參閱[使用 Configuration Manager 管理啟動影像](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)。

> [!NOTE]
> 您可以建立可啟動的 USB 媒體，以針對沒有 PXE 支援的環境啟動 Configuration Manager 任務順序部署。 可啟動的媒體只包含啟動影像、選用的預先啟動命令以及其必要的檔案，以及 Configuration Manager 二進位檔案以支援在 Windows PE 中啟動，並在其餘的部署程式中連線至 Configuration Manager。 如需詳細資訊，請參閱[建立可引導媒體](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)。

## <a name="create-configuration-manager-packages"></a>建立 Configuration Manager 套件

> [!IMPORTANT]
> 每個 SRS 安裝程式版本所需的作業系統版本都會隨每個 MSI 發行而變更。 若要判斷特定 MSI 的最佳作業系統版本，請執行一次主控台安裝程式腳本。 若要深入瞭解，請參閱[使用 Microsoft 端點建構管理員部署 Microsoft 團隊聊天室](rooms-scale.md)。

Configuration Manager 需要多個套件來部署並設定 Microsoft 團隊會議室單位。

您需要建立並設定下列套件，然後將它們發佈到已指派發佈點伺服器角色的 Configuration Manager 網站系統。

| **套件名稱**                     | **類型**               | **說明**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS 應用程式套件     | 軟體套件       | Microsoft 團隊聊天室部署套件封裝                                      |
| SRS v2-Sysprep 套件             | 軟體套件       | [自訂以無人參與的 .xml] 來設定 Microsoft 團隊會議室單位            |
| SRS v2-設定 SRSComputerName 套件 | 軟體套件       | 要在部署期間指派電腦名稱稱的 HTML 應用程式（HTA）套件    |
| SRS v2-設定 SRS 設定         | 軟體套件       | 打包以設定 Microsoft 團隊聊天室應用程式的部署                          |
| SRS v2-OS 更新套件          | 軟體套件       | 打包以部署強制的作業系統更新                                      |
| SRS v2-根憑證套件    | 軟體套件       | 選用-套件來部署根憑證（不需要網域加入的單位）  |
| SRS v2-Microsoft Monitoring Agent 套件 | 軟體套件       | 選用-套件部署並設定 Microsoft Operations Management Suite 代理程式|
| SRS v2-WinPE 背景套件    | 軟體套件       | 要搭配啟動影像使用的自訂背景圖像套件                           |
| Windows 10 企業版                | 作業系統影像 | 作業系統安裝檔案（安裝 .wim）的封裝                          |
| Surface Pro                          | 驅動程式套件         | Microsoft Surface Pro 裝置驅動程式和固件套件                     |
| Surface Pro 4                        | 驅動程式套件         | Microsoft Surface 專業版4的裝置驅動程式和固件套件                   |

如需詳細資訊，請參閱[Configuration Manager 中的套件與程式](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)。

### <a name="create-folders-for-the-package-source-files"></a>建立套件來源檔案的資料夾

在第一次建立及更新時，Configuration Manager 需要將套件來源檔案組織在特定資料夾結構中。

在 Microsoft 端點 Configuration Manager 管理中心網站或主要網站上建立下列資料夾結構，或在您用來存放套件來源檔案的伺服器共用上建立下列資料夾結構：

-   SRS v2-Microsoft Monitoring Agent 套件
-   SRS v2-OS 更新套件
-   SRS v2-根憑證套件
-   SRS v2-設定 SRSComputerName 套件
-   SRS v2-SRS 應用程式套件
-   SRS v2-設定 SRS 設定
-   SRS v2-Sysprep 套件
-   驅動程式
    -   Surface Pro
    -   Surface Pro 4
-   作業系統
    -   Windows 10 企業版

> [!TIP]
> 您也可以[下載](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)並使用 zip 檔案，其中包含套件的資料夾結構、您需要使用的腳本，以及您必須匯入的任務順序範本。

### <a name="create-the-monitoring-agent-package"></a>建立監視代理套件

1. 從<https://go.microsoft.com/fwlink/?LinkId=828603>下載監視代理程式。

2. 在命令提示字元中開啟 [命令提示字元] 視窗，然後輸入**MMASetup-AMD64/c：** ，將套件解壓縮至 [ **SRS V2-Microsoft Monitoring Agent 套件**] 資料夾。

3. 在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

4. 輸入下列資訊來建立套件：

   - 名稱<strong>： SRS v2-Microsoft Monitoring Agent 套件</strong>

   - 製造商<strong>： Microsoft Corporation</strong>

   - 版本<strong>： 8.1.11081.0</strong> （輸入下載的安裝檔版本）

   - 選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS V2-Microsoft Monitoring Agent 套件**資料夾的路徑，然後選取 **[下一步]**。

5. 選取 [**不建立程式**]，然後選取 **[下一步]**。

6. 查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

7. 選取 [**關閉**]。

### <a name="create-the-operating-system-updates-package"></a>建立作業系統更新套件

1. 在 [ **SRS v2-OS 更新套件**] 資料夾中，建立名為**Install-SRSv2-OS-Updates**的新 PowerShell 腳本。

2. 將下列腳本複製到**Install-SRSv2-OS-Updates**腳本中。 或者，您也可以從[這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下載 Install-SRSv2-OS-Updates. ps1 腳本。
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
3. 將強制執行的 Windows 更新套件下載到同一個資料夾中。
   > [!NOTE]
   > 發佈本文時，只需要[KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 。 請核取 [[設定 Microsoft 團隊聊天室] 主控台](console.md)，查看是否需要任何其他更新。

4. 在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

5. 輸入下列資訊來建立套件：
   -   名稱： **SRS v2-OS 更新套件**
   -   製造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS V2-OS 更新套件**資料夾的路徑，然後選取 **[下一步]**。

6. 選取 [**不建立程式**]，然後選取 **[下一步]**。

7. 查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

8. 選取 [**關閉**]。

### <a name="create-the-root-certificate-package-optional"></a>建立根憑證套件（選用）

您可以建立此套件，以發佈不會加入 Active Directory 網域之裝置的根憑證。 只有在符合下列條件時，才能建立此套件：
-   您的部署包括內部部署 Lync 或商務用 Skype 伺服器。
-   Microsoft 球隊房間單元已設定為在工作組中工作，而不是網域成員。

1.  將根憑證複製到 [ **SRS v2] （根憑證套件**資料夾）中。

2.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

3.  輸入下列資訊來建立套件：
    -   名稱： **SRS v2 –根憑證套件**
    -   製造商：*貴組織的名稱*
    -   版本： **1.0.0**
    -   選取 [**此套件包含來源**檔案] 核取方塊，輸入 [ **SRS V2 –根憑證套件**] 資料夾的路徑，然後選取 **[下一步]**。

4.  選取 [**不建立程式**]，然後選取 **[下一步]**。

5.  查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

6.  選取 [**關閉**]。

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>建立 Microsoft 團隊聊天室部署套件封裝

1.  從<https://go.microsoft.com/fwlink/?linkid=851168>下載最新版本的**Microsoft 團隊聊天室部署套件**，然後將其安裝到工作站。

2.  將**C：\\Program Files （x86）\\Skype 室系統部署套件**中的內容複寫到**SRS v2-srs 應用程式**套件資料夾中。

3.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

4.  輸入下列資訊來建立套件：
    -   名稱： **srs v2 – Srs 應用程式套件**
    -   製造商： **Microsoft Corporation**
    -   版本： **3.1.104.0** （輸入下載的安裝檔版本）
    -   選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS V2 – SRS 應用程式套件**資料夾的路徑，然後選取 **[下一步]**。
5.  選取 [**不建立程式**]，然後選取 **[下一步]**。

6.  查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

7.  選取 [**關閉**]。

### <a name="create-the-computer-name-assignment-package"></a>建立電腦名稱稱指派套件

1.  在**SRS v2-Set-SRSComputerName 套件**資料夾中，建立名為**SET-SRSCOMPUTERNAME**的新 HTML 應用程式。

2.  將下列腳本複製到**Set-SRSComputerName**檔中。 或者，您也可以從[這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下載 Set-SRSComputerName 的 .hta 檔案。
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
3.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

4.  輸入下列資訊來建立套件：

    -   名稱： **SRS v2-Set-SRSComputerName 套件**

    -   製造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS v2 SRSComputerName 套件**資料夾的路徑，然後選取 **[下一步]**。

5.  選取 [**不建立程式**]，然後選取 **[下一步]**。

6.  查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

7.  選取 [**關閉**]。

### <a name="create-the-sysprep-package"></a>建立 Sysprep 套件

1. 在 [ **SRS v2 – Sysprep 套件**] 資料夾中，建立名為**UNATTEND.XML**的新 XML 檔案。

2. 將下列文字複製到**無人參與 .xml**檔案中。 或者，您可以從[這裡](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)下載無人參與的 .xml 檔案。
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
3. 在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

4. 輸入下列資訊來建立套件：
   -   名稱： **SRS v2-Sysprep 套件**
   -   製造商： **Microsoft Corporation**
   -   版本： **1.0.0**
   -   選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS V2-Sysprep 套件**資料夾的路徑，然後選取 **[下一步]**。
5. 選取 [**不建立程式**]，然後選取 **[下一步]**。

6. 查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

7. 選取 [**關閉**]。

### <a name="create-the-windows-10-enterprise-package"></a>建立 Windows 10 企業版套件

1.  取得 Windows 10 企業版 x64 媒體，然後將**安裝 .wim**檔案複製到**作業系統\\Windows 10 企業版**資料夾中。

2.  在 Configuration Manager 主控台中，移至**軟體庫** \> **作業系統** \>的**作業系統影像**，然後選取 [**新增作業系統影像**]。

3.  指定您剛複製的**安裝 .wim**檔案的路徑，然後選取 **[下一步]**。

4.  更新**版本**欄位，使其符合 Windows 10 企業版影像的組建編號，然後選取 **[下一步]**。

5.  查看 [**詳細資料**] 頁面，然後選取 **[下一步]**。

6.  選取 [**關閉**]。

如需詳細資訊，請參閱[使用 Configuration Manager 管理作業系統映射](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)。

### <a name="create-surface-pro-device-driver-packages"></a>建立 Surface Pro 裝置驅動程式套件

Surface Pro 和 Surface Pro 4 都支援 Microsoft 球隊會議室。 您需要針對您的環境中的每個 Surface Pro 模型建立驅動程式套件。

> [!IMPORTANT]
> 驅動程式必須與 Windows 10 企業版組建和 Microsoft 團隊聊天室部署套件版本相容。 如需詳細資訊，請參閱[下載 Surface 裝置的最新固件和驅動程式](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)，並[設定](console.md)主機。

1.  下載最新的驅動程式和固件。
    -   針對 Surface Pro：<https://www.microsoft.com/download/details.aspx?id=55484>
    -   針對 Surface Pro 4：<https://www.microsoft.com/download/details.aspx?id=49498>

2.  解壓縮已下載的驅動程式和固件。 開啟命令提示字元視窗，然後在命令提示字元中，輸入下列其中一個命令：
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **作業系統** \> **驅動程式**]，然後選取 [匯**入驅動程式**]。

4.  選取 **[匯入下列網路路徑（UNC）] 中的 [所有驅動程式**]，選取 [來源]\\資料夾\\（\\例如，C： _Sources 驅動程式 Surface Pro），然後選取 **[下一步]**。

5.  在 [**指定匯入的驅動程式的詳細資料**] 頁面上，選取所有列出的驅動程式，然後選取 [**啟用這些驅動程式並允許電腦安裝它們**]。

6.  選取 [**類別**]，建立與 Surface 模型相符的新類別，選取 **[確定]**，然後選取 **[下一步**]。

7.  選取 [**新增套件**]。

8.  指定與 Surface Pro 模型相符的套件名稱，輸入要儲存驅動程式套件檔案的資料夾路徑，選取 **[確定]**，然後選取 **[下一步**]。

9.  在 [**啟動影像**] 頁面上，確認沒有選取任何啟動影像，然後選取 **[下一步]**。

10. 選取 [**關閉**]。

11. 移至**軟體庫** \> **作業系統** \> **驅動程式**，選取**資料夾\>的 [建立資料夾**]，然後輸入與您剛匯入驅動程式的 Surface Pro 模型相符的資料夾名稱。

12. 將所有已匯入的驅動程式移至新建立的資料夾，以便更輕鬆地流覽和操作。

> [!NOTE]
> 針對您可能擁有的其他 Surface Pro 模型重複相同的步驟。 如需詳細資訊，請參閱[Configuration Manager 中的管理驅動程式](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)。

### <a name="create-microsoft-teams-rooms-configuration-package"></a>建立 Microsoft 團隊會議室配置套件

1.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]，然後選取 [**建立套件**]。

2.  輸入下列資訊來建立套件：

    -   名稱： **SRS v2-設定 SRS 安裝套件**

    -   製造商： **Microsoft Corporation**

    -   版本： **1.0.0**

    -   選取 [**此套件包含來源**檔案] 核取方塊，輸入**SRS V2-[設定 srs 設定**] 資料夾的路徑，然後選取 **[下一步]**。

3.  選取 [**不建立程式**]，然後選取 **[下一步]**。

4.  查看 [**確認設定**] 頁面，然後選取 **[下一步]**。

5.  選取 [**關閉**]。



## <a name="distribute-configuration-manager-packages"></a>發佈 Configuration Manager 套件

所有套件都必須發佈到 Configuration Manager 階層中已指派發佈點角色的伺服器。 遵循下列指示來啟動套件發佈。

1.  發佈軟體套件。

    1.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **應用程式管理** \> **套件**]。 選取所有您要發佈的軟體套件，然後選取 [**發佈內容**]。

    2.  查看套件清單，然後選取 **[下一步]**。

    3.  根據您的 Configuration Manager 階層，將所有發佈點伺服器（或發佈點群組）新增至清單，然後選取 **[下一步]**。

    4.  選取 **[下一步]**，然後選取 [**關閉**]。

2.  發佈驅動程式套件。

    1.  在 Configuration Manager 主控台中，移至**軟體庫** \> **作業系統** \> **驅動程式套件**。 選取您要發佈的所有驅動程式套件，然後選取 [**發佈內容**]。

    2.  查看套件清單，然後選取 **[下一步]**。

    3.  根據您的 Configuration Manager 階層，將所有發佈點伺服器（或發佈點群組）新增至清單，然後選取 **[下一步]**。

    4.  選取 **[下一步]**，然後選取 [**關閉**]。

3.  發佈作業系統封裝。

    1.  在 Configuration Manager 主控台中，移至**軟體庫** \> **作業系統** \>的**作業系統影像**。 選取所有您想要散佈的作業系統影像，然後選取 [**發佈內容**]。

    2.  查看套件清單，然後選取 **[下一步]**。

    3.  根據您的 Configuration Manager 階層，將所有發佈點伺服器（或發佈點群組）新增至清單，然後選取 **[下一步]**。

    4.  選取 **[下一步]**，然後選取 [**關閉**]。

> [!NOTE]
> 套件發佈可能需要一些時間，視套件大小、Configuration Manager 階層、發佈點伺服器數目，以及您網路中可用的頻寬而定。
> 
> 您必須先發佈所有套件，才能開始部署 Microsoft 團隊會議室。
> 
> 您可以前往**監視** \> **發佈狀態** \> **內容狀態**，在 Configuration Manager 主控台中查看套件發佈的狀態。

## <a name="configuration-manager-task-sequences"></a>Configuration Manager 任務序列

您可以將任務順序與 Configuration Manager 搭配使用，以自動將作業系統映射部署到目的地電腦的步驟。 若要以自動化的方式部署 Microsoft 團隊會議室，您可以建立一個工作序列，參照用於啟動目的地 Microsoft 團隊聊天室電腦的啟動影像、您想要安裝的 Windows 10 企業版作業系統影像，以及任何其他其他內容，例如其他應用程式或軟體更新。

### <a name="import-the-sample-task-sequence"></a>匯入範例任務序列

您可以下載並輕鬆匯入範例任務序列，並加以自訂以符合您的需求。

1.  [**下載**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)範例任務序列，並將下載的 zip 檔案複製到共用位置。
2.  在 Configuration Manager 主控台中，移至 [**軟體庫** \> **作業系統** \> ]**任務序列**，然後選取 [匯**入任務序列**]。

3.  選取 **[流覽]**，移至您在步驟1中使用的共用資料夾位置，選取 [ **Microsoft 團隊聊天室部署（zh-cn） .zip**檔案]，然後選取 **[下一步]**。

4.  將**動作**設定為 [**新建**]，然後選取 **[下一步]**。

5.  確認設定，然後選取 **[下一步]**。

6.  選取 [**關閉**]。

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>驗證參照套件是否已正確連結至每個任務序列步驟。

1. 選取匯入的任務序列，然後選取 [**編輯**]。

    [任務順序編輯器] 隨即開啟，並顯示您需要部署並設定 Microsoft 團隊會議室單位的每個順序步驟。

2. 逐步執行每個步驟，並完成建議的更新：

   1. **在 WINDOWS PE 中重新開機**：此步驟會重新開機，然後將電腦引導至 Windows PXE。 此步驟不需要任何變更。

   2. [**分區磁片0– UEFI**]：此步驟會根據設定的設定，來擦除磁片設定並建立分區。 我們建議您不要對此步驟進行任何變更。

   3. **設定 SRS 電腦名稱**：此步驟包含一個 HTML 應用程式，可在部署期間提供 UI 來設定 Microsoft 團隊會議室單位的電腦名稱稱。
      -  這是一個選用的步驟，但只有在您想要透過備用程式管理電腦命名時，才能停用。
      -  確認已選取 [ **SRS v2-Set-SRSComputerName**套件]。 如果沒有，請流覽到套件並選取。

   4. 套用**作業系統**：此步驟指定要部署的作業系統映射，以及要使用的無人參與 Sysprep 答案檔案。
      -  確認已選取正確的 Windows 10 企業版作業系統影像檔案。
      -  確認已啟用 [**針對自訂安裝使用無人參與或 Sysprep 答案**檔案]，並且已選取 [ **SRS V2-Sysprep 套件**]。 另外，請確認 **[檔案名] 已設定**為 [**無人參與 .xml**]。

   5. 套用**Windows 設定**：此步驟會收集 Windows 安裝的相關資訊。
      -  提供授權及註冊資訊，包括產品金鑰、當地系統管理員帳戶密碼及時區（視您的需求而定）。

   6. [套用**網路設定**]：此步驟可讓您指定 [工作組] 或 [Active Directory 功能變數名稱] 和 [組織單位]。
      > [!NOTE]
      > 請參閱[Skype 會議室系統網域加入考慮](domain-joining-considerations.md)在將 Microsoft 團隊會議室部署為 Actve Directory 網域的成員時所需採取的建議動作。
   7. 套用**驅動程式：** 這個步驟及其子步驟是根據您所擁有的 Surface Pro 模型來部署適用的裝置驅動程式和固件。 更新每個步驟，以指定與此部署相關聯的相關驅動程式套件。
      -   每個驅動程式套件都設定為利用 Windows 管理工具（WMI）篩選器，以根據 Surface Pro 品牌和型號部署相關的驅動程式和固件。
      -   我們強烈建議您不要變更這些驅動程式的設定，否則部署可能會失敗。

   8. **設定 Windows 與 Configuration manager**：此步驟會部署並設定 configuration manager 用戶端。 更新此步驟以指定內建 Configuration Manager 用戶端套件。

   9. **安裝根憑證**：此步驟會為非網域加入的裝置發佈根憑證，因此預設為選用並停用。
      -   如果您需要將根憑證部署到 Microsoft 團隊會議室單位，請啟用此步驟。
      -   如果您需要執行此步驟，請確認已選取 [ **SRS v2 –根憑證套件**] 和 [**停用64位檔案系統**重新導向]。

   10. **安裝並設定監視代理程式**：此步驟會安裝64位版本的 Microsoft Azure 監視器代理，並將代理程式設定為連線到您的 Log Analytics 工作區。
       -   此步驟預設為停用。 只有在您要使用監視 Agent 來監視 Microsoft 團隊會議室單位的健康情況時，才能啟用此步驟。
       -   編輯這個步驟並更新命令列參數，以指定您的**工作區識別碼**和**工作區金鑰**。
       -   如需取得作業管理套件工作區識別碼和主鍵的詳細資訊，請參閱[設定 Azure 監視的測試裝置](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)。
       -   確認已選取 [ **SRS v2 – Microsoft Monitoring Agent 封裝**及**停用64位檔案系統**重新導向]。
       -   如需有關監視 Microsoft 團隊會議室部署狀況的詳細資訊，請參閱使用[azure 監視器規劃 Microsoft 團隊聊天室管理](azure-monitor-plan.md)、[使用 Azure 監視器部署 microsoft](azure-monitor-deploy.md)團隊聊天室管理，以及[使用 Azure 監視器管理 microsoft 團隊會議室裝置](azure-monitor-manage.md)。

   11. **複製 SRS V2 設定檔**：此步驟會將所需的設定和配置檔案從 Microsoft 團隊聊天室部署套件複製到本機硬碟。 此步驟不需要自訂。
       -   確認已選取 [ **srs v2 – srs] 應用程式套件**和 [**停用64位檔案系統**重新導向]。

   12. **安裝-SRSv2-OS-更新**：此步驟會將 Microsoft 小組聊天室部署所需的任何強制作業系統更新部署。 請執行下列步驟：
       -   檢查 [[設定 Microsoft 團隊聊天室] 主控台](console.md)，查看需要哪些更新。
       -   確認您的**SRS v2-OS 更新套件**包含所有需要的更新。
       -   確認已選取 [ **SRS v2-OS 更新套件**]。
       -   確認 [PowerShell 執行原則] 設定為 [**略過**]。

   13. **重新開機電腦**：此步驟會在安裝必要的作業系統更新之後，重新開機電腦。 此步驟不需要自訂。

   14. **設定 Windows 元件**：此步驟會配置必要的 Windows 功能。 此步驟不需要自訂。

   15. **重新開機電腦**：此步驟會在設定 Windows 功能之後重新開機電腦。 此步驟不需要自訂。

   16. **新增本機 Skype 使用者**：此步驟會建立用來自動登入 Windows 的本機 skype 帳戶，並啟動 Microsoft 團隊聊天室應用程式。 這個步驟沒有任何與它相關聯的軟體套件，且不需要進行自訂。

   17. **設定和設定 SRS 應用程式**：此步驟會針對下次啟動作業系統，為 Microsoft 團隊聊天室應用程式安裝進行配置。
       -   確認已選取 [ **srs v2]-[設定 Srs 安裝套件**] 和 [**停用64位檔案系統**重新導向]。

> [!IMPORTANT]
> 任務序列步驟必須遵循所提供的順序，這一點非常重要。 修改步驟順序或設定其他步驟可能會中斷部署。
>
> **設定和設定 SRS 應用程式**步驟必須是任務序列中的最後一個步驟，否則部署可能會失敗。

### <a name="create-deployment-for-the-task-sequence"></a>建立任務序列的部署

1. 選取任務序列，然後選取 [**部署**]。

2. 選取 **[流覽]** 以選取要部署的 [目標集合]。

3. 選取 [**所有未知電腦**]，然後選取 **[確定]**。

4. 選取 **[下一步]**。

5. 選取 [在**用途**] 下拉式清單中的 [**可用**]。

6. 在 [**可用至下列**清單] 中，選取 [**僅限媒體和 PXE** ]，然後選取 **[下一步]**。
   > [!WARNING]
   > 將 [**目的**] 設定為 [**可用**] 非常重要。 確定**用途****未設定為**[**必要**]。 此外，請務必在 [**可供下列**] 中選取 [**僅限媒體和 PXE** ]。
   >
   > 如果將這些值設定為其他值，可能會導致所有電腦在啟動時取得 Microsoft 團隊會議室部署影像。
7. 請勿指定任何排程，然後選取 **[下一步]**。

8. 請勿變更 [**使用者體驗**] 區段中的任何專案，然後選取 **[下一步]**。

9. 請勿變更 [**通知**] 區段中的任何專案，然後選取 **[下一步]**。

10. 請勿變更 [**發佈點**] 區段中的任何專案，然後選取 **[下一步]**。

11. 確認設定，然後選取 **[下一步]**。

12. 選取 [**關閉**]。

<a name="validate-and-troubleshoot-the-solution"></a>驗證及疑難排解解決方案
--------------------------------------

完成 Microsoft 端點設定管理員的工作序列之後，您必須執行測試執行，以驗證任務序列是否可部署並設定 Microsoft 團隊會議室單位。

1.  使用其中一個支援的乙太網配接器或使用 Surface dock，將測試裝置連線到有線網路。 如果尚未針對您的環境設定 PXE 啟動功能，您可以使用[您先前建立](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media)的 usb 快閃記憶體磁碟機上的啟動影像，然後連線至 Configuration Manager。

2.  存取固件並啟動 PXE 啟動：

    1.  確認 Surface 裝置已關閉電源。

    2.  按住**音量**按鈕。

    3.  按下並放開 [**電源**] 按鈕。

    4.  在裝置開始啟動之後，請放開**Volume**按鈕。

    5.  選取 [**啟動配置**]。

    6.  請執行下列其中一項操作：

        -   選取 [ **PXE 引導**]，然後將它拖曳到清單頂端。 或者，您可以在網路介面卡上向左滑動，立即引導至裝置。 這不會影響啟動順序。
        -   選取裝有啟動媒體的 USB 快閃記憶體磁片磁碟機。

3.  選取 [結束 **]，然後選取 [****立即重新開機**]。

4.  出現提示時，請選取 [針對網路引導服務**輸入**]。

5.  Windows PE 會載入到記憶體中，任務序列嚮導將會啟動。 選取 **[下一步]** 繼續。

6.  選取您先前匯入的任務序列，然後選取 **[下一步]**。

7.  在應用磁片設定之後，系統會提示您指定裝置的電腦名稱稱。 使用者介面會根據 Surface Pro 裝置的序列值，顯示建議的電腦名稱稱。 您要麼接受建議的名稱，要麼指定一個新的名稱。 依照 [電腦名稱稱指派] 畫面上的指示進行。 當您選取 [**接受**] 時，就會開始部署。

8.  部署程式的其餘部分是自動操作，不會要求您提供任何其他的使用者輸入。

9.  部署工作序列完成設定裝置之後，您會看到下列配置畫面，要求您設定 Microsoft 團隊聊天室應用程式設定。

    ![Microsoft 團隊聊天室應用程式的初始設定畫面](../media/room-systems-scale-image2.png)

10.  將 Surface Pro 插入 Microsoft 團隊聊天室主控台，然後設定應用程式設定。

11.  驗證[Microsoft 團隊聊天室](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)中所列的功能是否可協助您在已部署的裝置上運作。


若要排查失敗的安裝問題，請檢查**SMSTS**檔案，該檔案會記錄 Configuration Manager 工作序列中執行的所有步驟。

SMSTS 檔案會根據組建程式的階段，儲存在其中一個路徑上。 檢查下表，找出 SMSTS 檔案的路徑。


| **部署階段**                                                            | **任務序列記錄路徑**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE，在 HDD 格式之前                                                        | X：\\Windows\\Temp\\smstslog\\smsts             |
| WinPE，在 HDD 格式化之後                                                         | C：\\_SMSTaskSequence\\記錄\\Smstslog\\smsts    |
| 在安裝 Configuration Manager 代理程式之前部署的作業系統 | c：\\_SMSTaskSequence\\記錄\\Smstslog\\smsts    |
| 已部署的作業系統與 Configuration Manager 代理                   | % windir%\\System32\\ccm\\記錄\\Smstslog\\smsts |
| 任務循序執行完成                                                | % windir%\\System32\\ccm\\記錄\\smsts 記錄           |

> [!TIP]
> 您可以在任務序列期間隨時選取**F8** ，以開啟命令主控台，然後取得 SMSTS 檔案的存取權。

若要疑難排解 PXE 啟動問題，請檢查 Configuration Manager 伺服器上特定于 PXE 動作的兩個記錄檔：

-   **Pxecontrol 記錄**，位於 Configuration Manager 安裝記錄目錄中

-   位於 Configuration Manager 管理點（MP）記錄目錄中的**Smspxe 記錄**

如需可用來進一步疑難排解 Configuration Manager 安裝的記錄檔案完整清單，請參閱 Microsoft 端點 Configuration Manager[記錄檔參考](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)。
