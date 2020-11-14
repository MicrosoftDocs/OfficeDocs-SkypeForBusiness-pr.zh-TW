---
title: 適用於虛擬桌面架構的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在 (VDI) 環境的虛擬化桌面基礎結構中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8670b7a1a2ba8393f6afddb9546cd01c276808f
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031259"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>適用於虛擬桌面架構的 Teams

本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構 (VDI) 是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。 這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。

虛擬化環境中的 Microsoft 團隊支援聊天與共同作業。 而且有了 Windows 虛擬桌面版、Citrix 和 VMware 平臺，也支援通話和會議功能。

虛擬化環境中的小組支援多種設定。 其中包括 VDI、專用、共用、持久且非持久的模式。 功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。

在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。 例如，某些高級功能可能無法在虛擬化的環境中使用，而且可能會有不同的影片解析度。

若要確保最佳的使用者體驗，請遵循本文中的指導方針。

 > [!Note]
> 如需有關不同平臺上的團隊 VDI 的詳細資訊，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 元件上的小組

在虛擬化環境中使用團隊需要下列元件。

- **虛擬化 broker** ：虛擬化提供者的資源和連線管理員（例如 Azure）
- **虛擬桌面** ：執行 Microsoft 團隊 (VM) 堆疊的虛擬機器
- **瘦用戶端** ：使用者使用物理介面的端點
- **團隊桌面應用程式** ：團隊桌面用戶端應用程式

## <a name="teams-on-vdi-requirements"></a>針對 VDI 需求的小組

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。 有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保您符合最低需求。
  
目前，使用音訊/視頻 (AV) 優化的小組，都是使用 Windows Virtual Desktop、Citrix 和 VMware 進行認證。 請參閱本節中的資訊，以確保您符合所有對適當功能的需求。

### <a name="platforms-certified-for-teams"></a>針對團隊認證的平臺

下列平臺擁有小組的虛擬桌面基礎結構解決方案。

|平台|解|
|----|---|
|![代表 Microsoft 的標誌](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 虛擬桌面</a> |
|![代表 Citrix 的標誌](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a> |
|![代表 VMware 的標誌](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware 範圍</a> |

### <a name="windows-virtual-desktop"></a>Windows 虛擬桌面

Windows 虛擬桌面電腦為 VDI 上的小組提供 AV 優化。 若要深入瞭解及需求及安裝，請參閱 [在 Windows 虛擬桌面電腦上使用團隊](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虛擬 App 與桌面需求

Citrix 虛擬 App 和桌面 (先前稱為 XenApp 和 XenDesktop) 為 VDI 上的小組提供 AV 優化。 借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。

您可以在 [citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。  (您必須先登入。 ) 必要元件已捆綁到 [Citrix 工作區應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 預設。 您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。

如需最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware 地平線工作區和桌面需求

VMware 範圍是一個現代平臺，可在混合式雲端上安全地傳送虛擬桌面和應用程式。 為提供最佳的使用者體驗，VMware 地平線為小組提供媒體優化功能。 這種優化改善了整個虛擬桌面和應用程式的整體生產力，並可在使用團隊進行通話與會議時改善使用者體驗。

您可以從 [ [Vmware 下載](https://my.vmware.com/web/vmware/downloads/#all_products) ] 頁面下載最新版本的 VMware。 根據預設，所需的媒體優化元件是集中式代理程式和集中式用戶端的一部分，而且不需要安裝任何其他外掛程式即可使用小組的優化功能。

若要取得如何設定團隊媒體優化的最新需求與指示，請參閱 [此 VMware 網站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安裝或更新小組桌面應用程式

您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。 決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。

針對專用的持續設定，這兩種方法都可以運作。 不過，對於非持續性設定，小組需要每電腦安裝才能有效運作。 請參閱 [非持續性設定](#non-persistent-setup) 一節。

在安裝每電腦的情況下，自動更新是停用的。 這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。 針對每位使用者安裝，會啟用自動更新。 對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。

若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。

為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。 如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。 這表示使用者處於未優化的媒體狀態。

#### <a name="dedicated-persistent-setup"></a>專用持續設定

在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。 針對持續性設定，小組支援針對每位使用者和每電腦安裝。

以下是建議的最低 VM 設定。

|參數  |工作站作業系統  |伺服器作業系統  |
|---------|---------|---------|
|vCPU   |    2個核心     |  4、6或8<br>請務必瞭解基礎非統一記憶體存取 (NUMA) 設定，並據此設定您的 Vm。     |
|RAM     |   4 GB      | 每位使用者512到 1024 MB        |
|儲存空間    | 8 GB        | 40到 60 GB        |

#### <a name="non-persistent-setup"></a>非持久性設定

在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。 這類設置通常是共用多個使用者會話。 VM 配置會根據使用者數量及可用的物理盒資源而有所不同。

針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。  (若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。 ) 這可確保在使用者會話期間有效啟動團隊 app。

將團隊與非持久設定搭配使用時，也需要設定檔的快取管理員，才能高效地進行團隊執行時間資料同步處理。這樣可確保在使用者會話期間，會快取使用者資料、設定檔和設定) 等適當的使用者特定資訊 (範例。 請確定這兩個資料夾中的資料已同步處理。  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) 
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) 

有許多可用的緩存管理器解決方案。 例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。 如需特定的設定指示，請參閱您的快取管理員提供者。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>小組快取內容排除清單以進行非持續設定

從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項： 排除這些專案有助於減少使用者的快取大小，進一步優化您的非持久設定。

- .txt 檔案
- 媒體堆疊資料夾
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) 

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>適用于企業考慮的 Microsoft 365 應用程式

當您使用 VDI 上的企業版 Microsoft 365 應用程式部署團隊時，請考慮下列事項。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>透過企業版 Microsoft 365 應用程式的新部署團隊

在透過企業版 Microsoft 365 應用程式部署團隊前，您必須先卸載任何預先存在的團隊應用程式（如果它們是使用各電腦安裝來部署）。

團隊透過適用于企業的 Microsoft 365 應用程式是針對每位使用者安裝的。 若要深入瞭解，請參閱 [安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>透過適用于企業更新的 Microsoft 365 應用程式部署團隊

團隊也會新增至企業版 Microsoft 365 應用程式的現有安裝。 由於 [企業版 Microsoft 365 應用程式] 只會針對每位使用者安裝小組，請參閱在 [VDI 上安裝或更新小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>使用團隊進行每電腦安裝和適用于企業的 Microsoft 365 應用程式

適用于企業的 Microsoft 365 應用程式不支援小組的每電腦安裝。 若要使用 [每電腦安裝]，您必須從適用于企業的 Microsoft 365 App 中排除團隊。 請參閱將 [團隊傳統型應用程式部署至 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及 [如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何透過適用于企業的 Microsoft 365 應用程式排除團隊部署

若要深入瞭解團隊和適用于企業的 Microsoft 365 應用程式，請參閱 [如何將團隊從新安裝的企業版 microsoft 365 應用程式中排除](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) ，並 [使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>將團隊桌面應用程式部署到 VM

1. 使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：

    - [32位版本](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [64位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    所需的小組桌面應用程式最低版本為版本1.3.00.4461。 舊版中不支援 (PSTN 保留。 ) 

2. 執行下列其中一項命令，將 MSI 安裝到 VDI VM：

    - 依使用者安裝 (預設) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        這個處理常式是預設安裝，可將團隊安裝到% AppData% user 資料夾中。 此時，黃金影像設定就完成了。 在非持續設定上，小組無法針對每位使用者安裝正常運作。

    - 每電腦安裝

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此程式會將團隊安裝至64位作業系統上的 [x86) ] 資料夾 (的程式檔案，以及32位作業系統上的 [程式檔案] 資料夾。 此時，黃金影像設定就完成了。 針對非持久的安裝，必須針對每台電腦安裝團隊。

        下次互動式登入會話會啟動團隊並要求認證。

        > [!NOTE]
        > 這些範例也會使用 **ALLUSERS = 1** 參數。 當您設定此參數時，[小組] Machine-Wide 安裝程式會出現在 [控制台] 的 [程式和功能] 中，以及電腦所有使用者的 [Windows 設定] & 功能。 如果有管理員認證，所有使用者都可以卸載小組。
        請務必瞭解 **ALLUSERS = 1** 與 **ALLUSER = 1** 之間的差異。 您可以在非 VDI 和 VDI 環境中使用 **ALLUSERS = 1** 參數，而 **ALLUSER = 1** 參數只會在 VDI 環境中用來指定每電腦安裝。

3. 從 VDI VM 卸載 MSI。 有兩種方式可以卸載小組。

    - PowerShell 腳本：您可以使用 [此 PowerShell 腳本](scripts/powershell-script-deployment-cleanup.md) 卸載小組，並移除使用者的 [小組] 資料夾。 針對在電腦上安裝團隊的每個使用者設定檔執行腳本。
    - 命令列：執行下列命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      這個程式會將小組從程式檔案卸載 (x86) 資料夾或 Program Files 資料夾，視作業系統環境而定。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 效能考慮的小組

有多種虛擬化設定設定，每個都有不同的焦點可供優化。 例如，配置可能會將焦點放在使用者密度上。 規劃時，請考慮下列事項，以根據貴組織的工作負載需求來優化您的設定。

- 最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。 例如，使用需要更多計算資源之應用程式之開發人員的工作負載。
- 相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。
- VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。 下列功能已停用：
    - 團隊 CSS 動畫
    - Giphy 自動啟動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>VDI 上的小組與通話與會議

除了聊天與共同作業之外，您還可以使用支援的虛擬化提供者平臺提供通話和會議的 VDI 小組。 支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者實現為基礎。 下圖提供架構的概覽。

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不受優化 (例如，在應用程式共用) 中授與控制權，您必須設定 [虛擬化提供者原則] 來關閉 [小組重新導向]。 這表示小組媒體會話不會進行優化。 如需如何設定原則以關閉小組重新導向的相關步驟，請聯絡您的虛擬化提供者。

### <a name="network-requirements"></a>網路需求

我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。 使用 [商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885) 來測試您的網路是否已準備好供團隊使用。

若要進一步瞭解如何為團隊準備您的網路，請參閱 [準備貴組織的小組網路](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>從 VDI 上的商務用 Skype 遷移到 VDI 的小組

如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。 在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：

- 在 VDI 中停用某些防病毒功能的每個平臺原則
- 在應用程式共用時提供控制權並加以控制
- 不含音訊的聊天螢幕共用
- 同時進行影片和螢幕共用的傳送和接收

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式

Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。 聊天與共同作業體驗會如期運作。 需要媒體時，有一些可能無法在 Chrome 瀏覽器中滿足使用者預期的體驗：

- 音訊與視頻資料流程體驗可能不是最佳的。 使用者可能會遇到延遲或降低品質。
- 在瀏覽器設定中無法使用裝置設定。
- 裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。
- 裝置設定也可能需要在 Windows 裝置管理中設定。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>VDI 上的小組與聊天與共同作業

如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定原則以關閉通話與會議功能

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。 可能需要一些時間 (幾個小時) ，原則才能傳播。 如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。

[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。 將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。

[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。 將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心指派原則

若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者：

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者** ]。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1.  按一下 [ **呼叫原則** ] 底下的 [ **DisallowCalling** ]。
    2.  按一下 [ **會議原則** ] 底下的 [ **AllOff** ]。
4. 按一下 **[** 套用]。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。 例如：
    - 移至 [ **語音**  >  **通話原則** ]，然後按一下 [ **DisallowCalling** ]。
    - 移至 [ **會議**  >  **會議原則** ]，然後按一下 [ **AllOff** ]。
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 完成新增使用者後，請按一下 [ **儲存** ]。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>使用聊天與共同作業將小組遷移至 VDI，以使用通話與會議優化團隊

如果您在 VDI 上有現有的小組實現，且您已將使用者層級原則設定為關閉通話與會議功能，且您是透過 AV 優化來遷移至小組，則您必須設定原則來針對 VDI 使用者上的小組開啟通話和會議功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>設定原則以開啟通話與會議功能

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。 可能需要一些時間 (幾個小時) ，才能傳播原則變更。 如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。

[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。 團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。 若要開啟所有通話功能，請指派 AllowCalling 原則。 或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。 

[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。 團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。 若要開啟所有會議功能，請指派 AllOn 原則。 或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心指派原則

若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者：

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [ **使用者** ]。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1.  按一下 [ **呼叫原則** ] 底下的 [ **AllowCalling** ]。
    2.  按一下 [ **會議原則** ] 底下的 [ **AllOn** ]。
4. 按一下 **[** 套用]。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [ **&#x2713;** (核取記號) 。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。 例如：
    - 移至 [ **語音**  >  **通話原則** ]，然後按一下 [ **AllowCalling** ]。
    - 移至 [ **會議**  >  **會議原則** ]，然後按一下 [ **AllOn** ]。
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 完成新增使用者後，請按一下 [ **儲存** ]。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例顯示如何使用 [授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱 [設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用 [授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱 [設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>在團隊中控制回退模式

當使用者從不受支援的端點連線時，使用者就會處於 [回退] 模式，但在這種情況下未優化 AV。 您可以設定下列其中一個登錄 DWORD 值來停用或啟用回退模式：

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

若要停用回退模式，請將此值設定為 **1** 。 若要只啟用音訊，請將此值設定為 **2** 。 如果該值不存在，或設定為 **0** (零) ，即表示已啟用回退模式。

[團隊版本 1.3.00.13565] 和 [更新版本] 中提供此功能。

## <a name="known-issues-and-limitations"></a>已知問題與限制

### <a name="client-deployment-installation-and-setup"></a>用戶端部署、安裝和設定

- 在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。 您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [ [安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi) ] 區段中所述。 您必須卸載目前的版本，才能更新為較新的版本。
- 團隊應該針對每個使用者或每個電腦來部署。 不支援針對每位使用者和每個電腦並行部署團隊。 若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。
- Windows 虛擬桌面及 VMware 目前不支援 MacOS 和 Linux 的用戶端。
- Citrix 目前不支援 MacOs 用戶端。
- Citrix 不支援使用在端點上定義的明確 HTTP proxy。

### <a name="calling-and-meetings"></a>通話與會議

不支援下列通話與會議功能：

- 增強的緊急服務
- 小組 app 與裝置之間的 HID 按鈕和 LED 控制項
- 背景模糊和效果
- 廣播與即時事件製造者與簡報者角色
- Location-Based 路由 (LBR) 
- 通話駐留
- 通話佇列
- 共用系統音訊/電腦音效
- 直接路由的媒體旁路

> [!NOTE]
> 我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。 這些可能包括更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。 若要深入瞭解即將推出的功能，請與您的小組代表聯繫。

下列是通話與會議的已知問題與限制：

- 與商務用 Skype 的互通性限制在音訊通話中;沒有任何視頻模態。
- 在會議或群組通話中只支援單一傳入的視頻資料流程。 當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。
- 內送和外寄的視頻資料流程解析度限制為720p 解析度。 這是 WebRTC 的限制。
- 只支援來自內送相機或畫面共用資料流程的一個影片串流。 當有傳入螢幕共用時，會顯示該螢幕共用，而不是主要喇叭的影片。
- 外寄螢幕共用：
    - 不支援應用程式共用。
- 授與控制權並加以控制：
    - 在螢幕共用或應用程式共用會話期間不支援。
    - 在 PowerPoint 共用會話期間支援。
- 僅限 Citrix 限制
    - 在多重監視器設定中進行螢幕共用時，只會共用主要監視器。
    - 不支援 CWA 上的高 DPI 縮放。

針對與 VDI 無關的小組已知問題，請參閱 [貴組織中的支援小組](Known-issues.md)。

## <a name="troubleshooting"></a>疑難排解

### <a name="troubleshoot-citrix-components"></a>Citrix 元件疑難排解

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>團隊當機或團隊登入畫面為空白

這是 Citrix VDA 版本1906和1909的已知問題。 若要解決此問題，請新增下列登錄 DWORD 值，並將它設為 204 (十六進位) 。

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

然後，重新開機 VDA。 若要深入瞭解，請參閱此 Citrix 支援文章、 [疑難排解 HDX 優化小組](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相關主題

- [使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Windows 虛擬桌面電腦上使用 Microsoft 團隊](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
