---
title: 適用於虛擬桌面架構的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬桌面基礎結構 (VDI) 環境中執行 Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90e577f9d6ef7567387fbc7a26a944d20e976f66
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773702"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>適用於虛擬桌面架構的 Teams

本文將說明在虛擬環境中使用 Microsoft Teams 的需求與限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構 (VDI) 是虛擬化技術，在資料中心的集中式伺服器上託管桌面作業系統和應用程式。 這可為擁有完全安全且相容集中來源的使用者提供完整且個人化的桌面體驗。

虛擬環境中的 Teams 支援聊天和共同作業。 此外，Azure 虛擬桌面、Citrix 和 VMware 平臺也支援通話和會議功能。

Teams 也支援虛擬環境中的多個設定。 這些包括 VDI、專用、共用、持續性和非持續性模式。 功能正在持續開發，且會定期新增，且功能會隨著時間而擴展。

在虛擬環境中使用 Teams 可能與在非虛擬環境中使用 Teams 有些不同。 例如，一些進階功能可能無法在虛擬環境中使用，而且視訊解析度可能會有所不同。

若要確保使用者獲得最佳體驗，請依照本文中的指引進行。

> [!Note]
> 如需不同平臺上 Teams VDI 的詳細資訊，請參閱 [各平臺的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 元件上的 Teams

在虛擬環境中使用 Teams 需要下列元件。

- **虛擬化代理人**：虛擬化提供者的資源和連線管理員，例如 Azure
- **虛擬桌面**：執行 Teams 的虛擬機器 (VM) 堆疊
- **精簡用戶端**：使用者實際介面使用的裝置
- **Teams 傳統型應用程式**：Teams 桌面用戶端應用程式

## <a name="teams-on-vdi-requirements"></a>使用 VDI 需求的 Teams

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

Teams 傳統型應用程式已與前置字元虛擬化解決方案提供者進行驗證。 透過多個市場提供者，建議您洽詢虛擬化解決方案提供者，以確保您符合最低需求。
  
目前，含音訊/視訊 (AV) 優化的 Teams VDI 已通過 Azure 虛擬桌面、Citrix 和 VMware 認證。 請檢閱本節中的資訊，確保您符合所有適當功能的需求。

### <a name="platforms-certified-for-teams"></a>通過 Teams 認證的平臺

下列平臺提供適用于 Teams 的虛擬桌面基礎結構解決方案。

|平台|解決 方案|
|----|---|
|![代表 Microsoft 的標誌。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虛擬桌面</a>，<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![代表 Citrix 的標誌。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬應用程式和桌面</a> |
|![代表 VMware 的標誌。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虛擬桌面

Azure 虛擬桌面為 Teams 的 VDI 提供 AV 優化。 若要深入瞭解需求與安裝，請參閱 [在 Azure 虛擬桌面上使用 Teams](/azure/virtual-desktop/teams-on-wvd)。

### <a name="windows-365"></a>Windows 365

Windows 365使用 Azure 虛擬桌面提供的 AV 優化，以確保從雲端電腦獲得最佳 Teams 體驗。 若要深入瞭解需求與安裝，請參閱 [在雲端電腦上使用 Teams](/windows-365/enterprise/teams-on-cloud-pc)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虛擬應用程式和桌面需求

Citrix 虛擬應用程式和桌面 (先前稱為 XenApp 和 XenDesktop) 提供適用于 VDI 上 Teams 的 AV 優化。 使用 Citrix 虛擬應用程式和桌面，除了聊天和共同作業之外，VDI 上的 Teams 還支援通話和會議功能。

您可以在 [Citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版的 Citrix 虛擬應用程式和桌面。  (您必須先登入。) 根據預設，必要的元件會搭售到 [Citrix 工作區應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 。 您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。

如需最新的伺服器和用戶端需求，請參閱 Citrix 網站上 [的 Microsoft Teams 優化](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) 文章。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace 和桌面需求

VMware Horizon 是現代化平臺，可安全地跨混合式雲端傳遞虛擬桌面和應用程式。 為了提供絕佳的使用者體驗，VMware Horizon 為 Teams 提供媒體優化。 這項優化改善虛擬桌面和應用程式的整體生產力，並增強使用 Teams 通話和會議時的使用者體驗。

您可以從 [VMware 下載](https://customerconnect.vmware.com/downloads/#all_products) 頁面下載最新版的 VMware Horizon。 根據預設，必要的媒體優化元件是 Horizon Agent 和 Horizon 用戶端的一部分，不需要安裝任何其他外掛程式即可使用 Teams 的優化功能。

若要取得有關如何設定 Teams 媒體優化的最新需求和指示，請參閱 VMware 網站上 [的為 Microsoft Teams 設定媒體優化](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) 一文。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安裝或更新 Teams 傳統型應用程式

您可以使用每台電腦安裝或每位使用者使用 MSI 套件來部署適用于 VDI 的 Teams 傳統型應用程式。 決定使用方式取決於您使用的是持續性或非持續性設定，以及貴組織的相關功能需求。

針對專用的持續性設定，每台電腦和每位使用者安裝都可運作。 不過，對於非持續性設定，Teams 需要每台電腦安裝，才能有效率地工作。 請參閱 [非持續性設定一](#non-persistent-setup) 節。

透過每台電腦安裝，自動更新會停用。 這表示若要更新 Teams 應用程式，您必須卸載目前的版本，才能更新到較新的版本。 透過個別使用者的安裝，系統會啟用自動更新。

> [!IMPORTANT]
> 讓您 VDI 環境中的 Teams 傳統型應用程式保持在最新狀態。 不支援發行日期比 [目前版本發行日期](/officeupdates/teams-app-versioning) 早 90 天以上的 Teams 傳統型應用程式版本。 不支援的 Teams 傳統型應用程式版本會向使用者顯示封鎖頁面，並要求他們更新其應用程式。

針對大部分的 VDI 部署，我們建議您使用每台電腦安裝部署 Teams。 若要更新至最新的 Teams 版本，請從卸載程式開始，然後再從最新的 Teams 版本部署開始。

若要讓 VDI 環境中的 Teams AV 優化正常運作，輕型用戶端裝置必須能夠存取網際網路。 如果細用戶端裝置無法存取網際網路，優化啟動將無法成功。 這表示使用者處於非優化的媒體狀態。

#### <a name="dedicated-persistent-setup"></a>專用的持續性設定

在專用的持續性設定中，使用者的本機作業系統變更會在使用者登出後保留。 針對持續性設定，Teams 支援每個使用者和每台電腦安裝。

以下是建議的最低 VM 設定。

|參數  |工作站作業系統  |伺服器作業系統  |
|---------|---------|---------|
|vCPU   |    2 個核心     |  4、6 或 8 核心<br>請務必瞭解基礎非統一記憶體存取 (NUMA) 設定，並據此設定 VM。     |
|RAM     |   4 GB      | 每個使用者 512 MB 到 1 GB        |
|儲存空間    | 8 GB        | 40 GB 到 60 GB        |

#### <a name="non-persistent-setup"></a>非持續性設定

在非持續性設定中，使用者的本機作業系統變更不會在使用者登出後保留。 這類設定通常是共用的多使用者會話。 VM 設定會根據使用者數量和可用的實體伺服器資源而有所不同。

若要進行非持續性設定，每台電腦都必須安裝 Teams 傳統型應用程式，才能顯示金色影像。 這可確保在使用者會話期間有效率地啟動 Teams 應用程式。 若要深入瞭解，請參閱 [在 VDI 上安裝或更新 Teams 傳統型應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 一節。

在非持續性設定中使用 Teams 也需要設定檔快取管理員，才能有效率地進行 Teams 執行時間資料同步處理。 有效率的資料同步處理可確保在使用者會話期間快取適當的使用者特定資訊 (，例如使用者的資料、設定檔或設定) 。 確認已同步處理這兩個資料夾中的資料：<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> 漫遊資料夾會 (，或者如果您正在使用資料夾重新導向，則需要快取管理員) ，以確保 Teams 應用程式具有執行應用程式所需的執行時間資料和檔案。 這是降低網路延遲問題或網路故障的必要條件，否則會導致應用程式錯誤，以及因為資料和檔案無法使用而導致體驗緩慢。

有各種不同的快取管理員解決方案可用，例如 [FSLogix](/fslogix/overview)。 如需特定設定指示，請洽詢快取管理員提供者。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams 非持續性設定的快取內容排除清單

從 Teams 快取資料夾中排除下列專案。 `%AppData%/Microsoft/Teams` 排除這些專案有助於縮減使用者快取大小，進一步優化非持續性設定。

- .txt檔案
- 媒體堆疊資料夾
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps 企業版考慮

當您在 VDI 上使用Microsoft 365 Apps 企業版部署 Teams 時，請考慮下列事項。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>透過 Microsoft 365 Apps 企業版 新部署的 Teams

在透過 Microsoft 365 Apps 企業版 部署 Teams 之前，如果您是使用每一台電腦安裝來部署，您必須先卸載任何預先存在的 Teams 應用程式。

每個使用者會安裝透過Microsoft 365 Apps 企業版團隊。 若要深入瞭解，請參閱 [在 VDI 上安裝或更新 Teams 傳統型應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 一節。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>透過Microsoft 365 Apps 企業版更新的 Teams 部署

Teams 也會新增至現有的 Microsoft 365 Apps 企業版 安裝。 由於Microsoft 365 Apps 企業版只為每個使用者安裝 Teams，請參閱[VDI 上的安裝或更新 Teams 桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>透過每台電腦安裝和Microsoft 365 Apps 企業版使用 Teams

Microsoft 365 Apps 企業版不支援 Teams 的每個電腦安裝。 若要使用每台電腦安裝，您必須將 Teams 排除在Microsoft 365 Apps 企業版。 請參閱[將 Teams 桌面應用程式部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)以及[如何透過Microsoft 365 Apps 企業版區段排除 Teams 部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何透過 Microsoft 365 Apps 企業版 排除 Teams 部署

若要深入瞭解 Teams 和 Microsoft 365 Apps 企業版，請參閱[如何將 Teams 排除于新安裝的 Microsoft 365 Apps 企業版](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)和[使用 群組原則 控制 Teams 的安裝。](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>將 Teams 傳統型應用程式部署到 VM

1. 使用下列其中一個連結下載符合您 VDI VM 作業系統的 Teams MSI 套件：

    - [32 位版本](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [64 位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > 如果是政府雲端，請參閱 [使用 Windows Installer (MSI) 大量安裝 Teams ](msi-deployment.md) ，以取得 MSI 檔案的下載連結。

2. 執行下列其中一個命令，將 MSI 安裝到 VDI VM：

    - 個別使用者安裝 (預設) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此程式是預設安裝，會將 Teams 安裝到 `%AppData%` 使用者資料夾。 此時，金色影像設定已完成。

        > [!IMPORTANT]
        > Teams 無法針對非持續性設定的每個使用者安裝正常運作。

    - 每台電腦安裝

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此程式會在電腦上新增必要的登錄機碼，讓 Teams 安裝程式知道這是 VDI 實例。  如果沒有，安裝程式會出錯，指出：「安裝已失敗。  偵測不到 VDI 環境時，無法為所有使用者安裝。」

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此程式會將 Teams 安裝到 `%ProgramFiles(x86)%` 64 位作業系統上的資料夾，以及 `%ProgramFiles%` 32 位作業系統上的資料夾。 此時，金色影像設定已完成。

        > [!IMPORTANT]
        >  非持續性設定需要每台電腦安裝 Teams。

        當下一個互動式登入會話開始時，Teams 會啟動並要求認證。

        > [!NOTE]
        > 這些範例也會使用參數 `ALLUSERS=1` 。 當您設定此參數時，**[Teams Machine-Wide安裝程式**] 會出現在 **[主控台** 中的 **程式和功能**] 以及 [**Windows 設定**] 中 [**應用程式] &功能** 中，供電腦的所有使用者使用。 所有使用者只要具備系統管理員認證，就可以卸載 Teams。
        >
        > 請務必瞭解兩者之間的 `ALLUSERS=1` 差異。 `ALLUSER=1` 參數 `ALLUSERS=1` 可用於非 VDI 和 VDI 環境中，而 `ALLUSER=1` 參數僅用於 VDI 環境以指定每部電腦安裝。

3. 從 VDI VM 卸載 MSI。 卸載 Teams 的方法有兩種。

    - **PowerShell 腳本**：您可以使用 [Teams 部署清理](scripts/powershell-script-deployment-cleanup.md) PowerShell 腳本來卸載 Teams，並移除使用者的 Teams 資料夾。 針對在電腦上安裝 Teams 的每個使用者設定檔執行腳本。
    - **命令列**：執行下列命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      視作業系統環境而定，此程式會從 `%ProgramFiles(x86)%` 資料夾或 `%ProgramFiles%` 資料夾卸載 Teams。

## <a name="teams-on-vdi-performance-considerations"></a>Teams 的 VDI 效能考慮

有各種不同的虛擬化設定設定，每個設定都有不同的優化焦點。 例如，設定可能會著重于使用者密度。 規劃時，請考慮下列專案，以根據貴組織的工作負載需求來協助優化設定。

- **最低需求**：某些工作負載可能需要使用高於最低需求的資源進行設定。 例如，針對使用需要更多運算資源之應用程式的開發人員工作負載。
- **相依性**：這些相依性包括對基礎結構、工作負載，以及 Teams 桌面應用程式外部的其他環境考慮的相依性。
- **VDI 上的停用功能**：Teams 會針對 VDI 停用需要大量 GPU 的功能，這有助於改善暫時性的 CPU 使用率。 下列功能已停用：
    - Teams CSS 動畫
    - Giphy 自動啟動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>具有通話和會議的 VDI Teams

除了聊天和共同作業之外，支援的虛擬化提供者平臺也提供具有通話和會議功能的 VDI Teams。 支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者實作為基礎。 下圖提供架構的概觀。

![顯示 Teams VDI 架構的圖表。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果您目前在 VDI 中未執行 AV 優化的 Teams，而且您使用尚未支援的功能進行優化 (例如在應用程式共用) 時授與及控制，則必須設定虛擬化提供者原則，以關閉 Teams 重新導向。 這表示 Teams 媒體會話不會優化。 如需如何設定原則以關閉 Teams 重新導向的步驟，請連絡您的虛擬化提供者。

### <a name="network-requirements"></a>網路需求

我們建議您評估您的環境，以找出可能會影響整體雲端語音和視訊部署的任何風險和需求。 使用[商務用 Skype網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試您的網路是否可供 Teams 使用。

若要深入瞭解如何準備 Teams 的網路，請參閱 [準備貴組織的 Teams 網路](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>從 VDI 上的 商務用 Skype 移轉到 VDI 上的 Teams

如果您要從 VDI 上的商務用 Skype移轉到 VDI 上的 Teams，除了兩個應用程式之間的差異之外，在實作 VDI 時會有一些差異。 在 商務用 Skype VDI 中，Teams VDI 目前不支援的某些功能如下：

- 停用 VDI 中部分 AV 功能的每個平臺原則
- 在應用程式共用時給予並取得控制權
- 不含音訊的聊天畫面分享
- 同時傳送和接收視訊和螢幕畫面分享

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 瀏覽器上的 Teams 與適用于 VDI 的 Teams 傳統型應用程式

Chrome 瀏覽器上的 Teams 不會提供使用 AV 優化取代 VDI 的 Teams 傳統型應用程式。 聊天和共同作業體驗如預期般運作。 需要媒體時，Chrome 瀏覽器上的某些體驗可能不符合使用者預期：

- 音訊和視訊串流體驗可能不是最佳體驗。 使用者可能會遇到延遲或品質降低的問題。
- 瀏覽器設定中無法使用裝置設定。
- 裝置管理是透過瀏覽器處理，需要在瀏覽器網站設定中進行多個設定。
- 您可能也需要在 Windows 裝置管理中設定裝置設定。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>使用聊天和共同作業的 Teams VDI

如果貴組織只想要使用 Teams 中的聊天和共同作業功能，您可以設定使用者層級原則，關閉 Teams 中的通話和會議功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定原則以關閉通話和會議功能

您可以使用 Teams 系統管理中心或 PowerShell 來設定原則。 最多幾個小時後原則變更就會散播。 如果您沒有立即看到指定帳戶的變更，請在幾個小時後再試一次。

[**通話原則**](teams-calling-policy.md)：Teams 包含內建的 **[不允許** 通話] 通話原則，其中所有通話功能都已關閉。 將 **不允許縮放** 原則指派給在虛擬環境中使用 Teams 的所有組織使用者。

[**會議原則**](meeting-policies-overview.md)：Teams 包含內建的 **AllOff** 會議原則，其中會關閉所有會議功能。 將 **AllOff** 原則指派給在虛擬環境中使用 Teams 的組織中的所有使用者。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用 Teams 系統管理中心指派原則

若要將 **DisallowCalling** 通話原則和 **AllOff** 會議原則指派給使用者：

1. 在 Teams 系統管理中心的左側導覽中，移至 **[使用者]**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話原則]** 底下，按一下 **[不允許縮放]**。
    2. 在 **[會議原則]** 底下，按一下 **[AllOff]**。
4. 按一下 [ **套用]**。

若要一次將原則指派給多位使用者：

1. 在 Teams 系統管理中心的左側導覽中，移至 [ **使用者**]，然後搜尋使用者或篩選檢視以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請按一下表格頂 **端&#x2713;(** 核取記號) 。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Teams 系統管理中心的左側導覽中，移至您要指派的原則。 例如：
    - 移至 **[語音**  >  **通話原則**]，然後按一下 **[取消通話]**。
    - 移至 **[會議**  >  **會議原則**]，然後按一下 [**AllOff]**。
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 當您完成新增使用者時，請按一下 [ **儲存]**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例示範如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將通話原則指派給 `DisallowCalling` 使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理通話原則，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例示範如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將會議原則指派給 `AllOff` 使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理會議原則，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>透過聊天和共同作業在 VDI 上移轉 Teams，以優化使用通話和會議的 Teams

如果您已經在 VDI 上使用聊天和共同作業來實作 Teams，其中已設定使用者層級原則以關閉通話和會議功能，而且您是透過 AV 優化移轉到 Teams，則必須設定原則，為 VDI 使用者上的 Teams 開啟通話和會議功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>設定原則以開啟通話和會議功能

您可以使用 Teams 系統管理中心或 PowerShell 來設定和指派通話和會議原則給使用者。 可能需要幾個小時的時間 () 原則變更才會散播。 如果您沒有看到指定帳戶的變更，請在幾個小時後再試一次。

[**通話原則**](teams-calling-policy.md)：Teams 中的通話原則可控制哪些通話功能可供使用者使用。 Teams 包含內建 **的 AllowCalling** 通話原則，其中會開啟所有通話功能。 若要開啟所有通話功能，請指派 **AllowCalling 原則** 。 或者，建立自訂通話原則來開啟您要的通話功能，並將它指派給使用者。

[**會議原則**](meeting-policies-overview.md)：Teams 中的會議原則會控制使用者可以建立的會議類型，以及組織中使用者排程的會議參與者可用的功能。 Teams 包含內建的 **AllOn** 會議原則，其中會開啟所有會議功能。 若要開啟所有會議功能，請指派 **AllOn** 原則。 或者，建立自訂會議原則來開啟您要的會議功能並指派使用者。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用 Teams 系統管理中心指派原則

若要將 **AllowCalling** 通話原則和 **AllOn** 會議原則指派給使用者：

1. 在 Teams 系統管理中心的左側導覽中，移至 **[使用者]**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話原則]** 底下，按一下 **[允許縮放]**。
    2. 在 **[會議原則]** 底下，按一下 **[AllOn]**。
4. 按一下 [ **套用]**。

若要一次將原則指派給多位使用者：

1. 在 Teams 系統管理中心的左側導覽中，移至 [ **使用者**]，然後搜尋使用者或篩選檢視以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請按一下表格頂 **端&#x2713;(** 核取記號) 。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Teams 系統管理中心的左側導覽中，移至您要指派的原則。 例如：
    - 移至 **[語音**  >  **通話原則**]，然後按一下 [**允許縮放]**。
    - 移至 **[會議**  >  **會議原則**]，然後按一下 [**AllOn]**。
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 當您完成新增使用者時，請按一下 [ **儲存]**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例示範如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將通話原則指派給 `AllowCalling` 使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理通話原則，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例示範如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將會議原則指派給 `AllOn` 使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理會議原則，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>Teams 中的控制後援模式

當使用者從不受支援的端點連線時，使用者會處於後援模式，而 AV 未優化。 您可以設定下列其中一個登錄 `DWORD` 值，停用或啟用後援模式：

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

若要停用後援模式，請將值設為 **1**。 若要只啟用音訊，請將值設為 **2**。 如果值不存在或設為 **0** (零) ，則會啟用後援模式。

這項功能可在 Teams 版本 1.3.00.13565 和更新版本中使用。

## <a name="disable-audio-and-video-settings-for-vdi"></a>停用 VDI 的音訊和視訊設定

Teams 模組中提供 Teams VDI 原則。 這些原則在非優化的 VDI 環境中為使用中並強制執行。

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> 這僅適用于未優化的環境。

### <a name="update-a-module-name"></a>更新模組名稱

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>設定原則以限制通話功能

當 VDI 原則設定為在 VDI `DisableCallsAndMeetings` 上登 `$true` 入 Teams 的使用者時，他們無法：

- 撥打電話。
- 加入會議。
- 從聊天畫面分享。

應停用所有類型的通話。

> [!NOTE]
> 這僅適用于未優化的環境。

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

當 VDI 原則設定為在 VDI `DisableAudioVideoInCallsAndMeetings` 上登 `$true` 入 Teams 的使用者時，他們：

- 可以從聊天畫面分享。
- 可以加入會議並共用螢幕，並將音訊移至手機。
- 無法按住 VDI 的一對一音訊和視訊通話。

> [!NOTE]
> 這僅適用于未優化的環境。

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>已知問題與限制

### <a name="client-deployment-installation-and-setup"></a>用戶端部署、安裝和設定

- 透過每台電腦安裝，VDI 上的 Teams 不會以非 VDI Teams 用戶端的方式自動更新。 您必須安裝新的 MSI 來更新 VM 映射，如 [在 VDI 上安裝或更新 Teams 傳統型應用程式](#install-or-update-the-teams-desktop-app-on-vdi) 一節中所述。 您必須解除安裝目前的版本，以更新至較新的版本。
- 在 Citrix 環境中，如果使用者在 Teams 執行期間中斷與虛擬機器的連線，Teams 更新可能會讓使用者在重新連線時處於非優化狀態。 我們建議使用者在中斷與 Citrix 虛擬機器的連線前結束 Teams，以免發生這種情況。
- Teams 應該在每一個使用者或每台電腦上部署。 不支援針對每個使用者和每部電腦同時部署 Teams。 若要從每部電腦或每位使用者移轉到其中一個模式，請遵循卸載程式，然後重新部署至任一模式。
- Azure 虛擬桌面目前不支援 macOS 和 Linux 型用戶端。
- 快速租使用者切換可能會導致 VDI 上的通話相關問題，例如螢幕畫面分享無法使用。 重新開機用戶端將會減輕這些問題。

### <a name="notifications"></a>通知

- Windows Server 2016主機不支援 Windows 工作列上的訊息計數通知和目前狀態。

### <a name="calling-and-meetings"></a>通話和會議

不支援下列通話和會議功能：

- Teams 應用程式和 Citrix 和 VMware 裝置之間的 HID 按鈕和 LED 控制項
- Citrix 和 VMware 的背景模糊和效果
- 廣播和即時活動製作人和簡報者角色
- Location-Based路由 (LBR) 
- PSTN 通話回撥鈴聲
- 共用系統音訊/電腦音效
- 直接路由的媒體旁路
- 縮放控制項

> [!NOTE]
> 我們正在努力新增目前僅適用于非 VDI 環境中的通話和會議功能。 這些功能可能包括更多對品質的系統管理員控制、其他螢幕畫面分享案例，以及最近新增至 Teams 的進階功能。 請連絡您的 Teams 代表，以深入瞭解即將推出的功能。

以下是通話和會議的已知問題和限制：

- 商務用 Skype的互通性僅限於音訊通話;沒有視訊形式。
- 內送和外寄視訊串流解析度限制為 720p 解析度。
- 如果裝置已中斷連線，然後重新連線，Teams 就不會切換為使用使用者選取的最後一個音訊裝置。
- 即時活動未優化。
- 外寄螢幕畫面分享：
  - VMware 和 AVD/W365 不支援應用程式共用。
- 授與控制權並取得控制權：
  - 應用程式共用會話期間不支援。

如需與 VDI 無關的 Teams 已知問題，請參閱 [支援組織中的 Teams](/MicrosoftTeams/troubleshoot/teams-welcome)。

## <a name="troubleshooting"></a>疑難排解

### <a name="troubleshoot-citrix-components"></a>疑難排解 Citrix 元件

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams 當機或 Teams 登入畫面為空白

這是 Citrix VDA 版本 1906 和 1909 的已知問題。 若要解決此問題，請新增下列登錄 `DWORD` 值，並將其設為 `204` (十六進位) 。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

然後重新開機 VDA。 若要深入瞭解，請參閱這篇 Citrix 支援文章： [Microsoft Teams HDX 優化疑難排解](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相關主題

- [使用 Windows Installer (MSI) 大量安裝 Teams ](msi-deployment.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Azure 虛擬桌面上使用 Microsoft Teams](/azure/virtual-desktop/teams-on-wvd)
