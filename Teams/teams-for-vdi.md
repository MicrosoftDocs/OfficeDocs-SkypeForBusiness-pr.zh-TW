---
title: 適用於虛擬桌面架構的 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬桌面基礎結構 (VDI) 環境中執行Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b85befa685458f5460ab21bb962af3f0df4f004
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681584"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>適用於虛擬桌面架構的 Teams

本文將說明在虛擬環境中使用Microsoft Teams的需求與限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構 (VDI) 是虛擬化技術，在資料中心的集中式伺服器上託管桌面作業系統和應用程式。 這可為擁有完全安全且相容集中來源的使用者提供完整且個人化的桌面體驗。

在虛擬環境中Teams支援聊天和共同作業。 此外，Azure 虛擬桌面、Citrix 和 VMware 平臺也支援通話和會議功能。

Teams也支援虛擬環境中的多個設定。 這些包括 VDI、專用、共用、持續性和非持續性模式。 功能正在持續開發，且會定期新增，且功能會隨著時間而擴展。

在虛擬環境中使用Teams可能與在非虛擬環境中使用Teams有些不同。 例如，一些進階功能可能無法在虛擬環境中使用，而且視訊解析度可能會有所不同。

若要確保使用者獲得最佳體驗，請依照本文中的指引進行。

> [!Note]
> 如需在不同平臺上Teams VDI 的詳細資訊，請[參閱依平臺Teams功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="teams-on-vdi-components"></a>VDI 元件上的Teams

在虛擬環境中使用Teams需要下列元件。

- **虛擬化代理人**：虛擬化提供者的資源和連線管理員，例如 Azure
- **虛擬桌面**：執行Teams的虛擬機器 (VM) 堆疊
- **精簡用戶端**：使用者實際介面使用的裝置
- **Teams桌面應用程式**：Teams桌面用戶端應用程式

## <a name="teams-on-vdi-requirements"></a>VDI 需求Teams

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

Teams桌面應用程式已與前置字元虛擬化解決方案提供者進行驗證。 透過多個市場提供者，建議您洽詢虛擬化解決方案提供者，以確保您符合最低需求。
  
目前，Teams具有音訊/視訊 (AV) 優化的 VDI 已通過 Azure 虛擬桌面、Citrix 和 VMware 認證。 請檢閱本節中的資訊，確保您符合所有適當功能的需求。

### <a name="platforms-certified-for-teams"></a>通過Teams認證的平臺

下列平臺有適用于Teams的虛擬桌面基礎結構解決方案。

|平台|解決 方案|
|----|---|
|![代表 Microsoft 的標誌。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虛擬桌面</a>，<a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![代表 Citrix 的標誌。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬應用程式和桌面</a> |
|![代表 VMware 的標誌。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虛擬桌面

Azure 虛擬桌面為 VDI 上的Teams提供 AV 優化。 若要深入瞭解需求與安裝，請參閱[在 Azure 虛擬桌面上使用Teams](/azure/virtual-desktop/teams-on-wvd)。

### <a name="windows-365"></a>Windows 365

Windows 365使用 Azure 虛擬桌面提供的 AV 優化，以確保從雲端電腦獲得最佳Teams體驗。 若要深入瞭解需求與安裝，請參閱[在雲端電腦上使用Teams](/windows-365/enterprise/teams-on-cloud-pc)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虛擬應用程式和桌面需求

Citrix 虛擬應用程式和桌面 (先前稱為 XenApp 和 XenDesktop) 提供 VDI 上Teams的 AV 優化。 有了 Citrix 虛擬應用程式和桌面，VDI 上的Teams除了聊天和共同作業之外，還支援通話和會議功能。

您可以在 [Citrix 下載網站](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版的 Citrix 虛擬應用程式和桌面。  (您必須先登入。) 根據預設，必要的元件會搭售到 [Citrix 工作區應用程式 (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 。 您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。

如需最新的伺服器和用戶端需求，請參閱 Citrix 網站上[的優化Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)文章。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace 和桌面需求

VMware Horizon 是現代化平臺，可安全地跨混合式雲端傳遞虛擬桌面和應用程式。 為了提供絕佳的使用者體驗，VMware Horizon 為Teams提供媒體優化。 這項優化改善虛擬桌面和應用程式的整體生產力，並增強使用Teams通話和會議時的使用者體驗。

您可以從 [VMware 下載](https://customerconnect.vmware.com/downloads/#all_products) 頁面下載最新版的 VMware Horizon。 根據預設，必要的媒體優化元件是 Horizon Agent 和 Horizon 用戶端的一部分，不需要安裝任何其他外掛程式，即可使用Teams優化功能。

若要取得有關如何設定Teams媒體優化的最新需求和指示，請參閱 VMware 網站上的設定[媒體優化Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)文章。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安裝或更新Teams桌面應用程式

您可以使用每台電腦安裝或每位使用者使用 MSI 套件來部署 VDI Teams桌面應用程式。 決定使用方式取決於您使用的是持續性或非持續性設定，以及貴組織的相關功能需求。

針對專用的持續性設定，每台電腦和每位使用者安裝都可運作。 不過，對於非持續性設定，Teams需要每台電腦安裝才能有效率地工作。 請參閱 [非持續性設定一](#non-persistent-setup) 節。

透過每台電腦安裝，自動更新會停用。 這表示若要更新Teams應用程式，您必須卸載目前的版本，才能更新至較新的版本。 透過個別使用者的安裝，系統會啟用自動更新。

> [!IMPORTANT]
> 讓 VDI 環境中Teams桌面應用程式保持在最新狀態。 Teams不支援發行日期比[目前版本發行日期](/officeupdates/teams-app-versioning)早 90 天以上的傳統型應用程式版本。 不支援的Teams桌面應用程式版本會向使用者顯示封鎖頁面，並要求他們更新其應用程式。

針對大部分的 VDI 部署，建議您使用每台電腦安裝部署Teams。 若要更新至最新Teams版本，請從卸載程式開始，接著執行最新的Teams版本部署。

若要Teams VDI 環境中的 AV 優化才能正常運作，輕型用戶端裝置必須能夠存取網際網路。 如果細用戶端裝置無法存取網際網路，優化啟動將無法成功。 這表示使用者處於非優化的媒體狀態。

#### <a name="dedicated-persistent-setup"></a>專用的持續性設定

在專用的持續性設定中，使用者的本機作業系統變更會在使用者登出後保留。 針對持續性設定，Teams支援每一使用者和每台電腦安裝。

以下是建議的最低 VM 設定。

|參數  |工作站作業系統  |伺服器作業系統  |
|---------|---------|---------|
|vCPU   |    2 個核心     |  4、6 或 8 核心<br>請務必瞭解基礎非統一記憶體存取 (NUMA) 設定，並據此設定 VM。     |
|RAM     |   4 GB      | 每個使用者 512 MB 到 1 GB        |
|儲存空間    | 8 GB        | 40 GB 到 60 GB        |

#### <a name="non-persistent-setup"></a>非持續性設定

在非持續性設定中，使用者的本機作業系統變更不會在使用者登出後保留。 這類設定通常是共用的多使用者會話。 VM 設定會根據使用者數量和可用的實體伺服器資源而有所不同。

對於非持續性設定，Teams桌面應用程式必須每台電腦安裝到金色影像。 這可確保在使用者會話期間有效率地啟動Teams應用程式。 若要深入瞭解，請參閱[在 VDI 上安裝或更新Teams桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節。

在非持續性設定中使用Teams也需要設定檔快取管理員，才能有效率地Teams執行時間資料同步處理。 有效率的資料同步處理可確保在使用者會話期間快取適當的使用者特定資訊 (，例如使用者的資料、設定檔或設定) 。 確認已同步處理這兩個資料夾中的資料：<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> 漫遊資料夾會 (，或者如果您正在使用資料夾重新導向，則需要快取管理員) ，以確保Teams應用程式具有執行應用程式所需的執行時間資料和檔案。 這是降低網路延遲問題或網路故障的必要條件，否則會導致應用程式錯誤，以及因為資料和檔案無法使用而導致體驗緩慢。

有各種不同的快取管理員解決方案可用，例如 [FSLogix](/fslogix/overview)。 如需特定設定指示，請洽詢快取管理員提供者。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams非持續性設定的快取內容排除清單

從Teams快取資料夾中排除下列專案。 `%AppData%/Microsoft/Teams` 排除這些專案有助於縮減使用者快取大小，進一步優化非持續性設定。

- .txt檔案
- 媒體堆疊資料夾
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps 企業版考慮

當您在 VDI 上使用Microsoft 365 Apps 企業版部署Teams時，請考慮下列事項。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>透過 Microsoft 365 Apps 企業版 新Teams部署

在透過Microsoft 365 Apps 企業版部署Teams之前，如果您是使用每一台電腦安裝來部署，您必須先卸載任何預先存在的Teams應用程式。

Teams到 Microsoft 365 Apps 企業版 會個別使用者安裝。 若要深入瞭解，請參閱[在 VDI 上安裝或更新Teams桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>透過Microsoft 365 Apps 企業版更新Teams部署

Teams也會新增至現有的 Microsoft 365 Apps 企業版 安裝。 由於Microsoft 365 Apps 企業版只為每個使用者安裝Teams，請參閱[VDI 上安裝或更新Teams桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>將Teams與每台電腦一起安裝及Microsoft 365 Apps 企業版

Microsoft 365 Apps 企業版不支援每部電腦Teams的安裝。 若要使用每台電腦安裝，您必須將Teams排除在Microsoft 365 Apps 企業版。 請參閱[將Teams桌面應用程式部署到 VM](#deploy-the-teams-desktop-app-to-the-vm)以及[如何透過Microsoft 365 Apps 企業版節排除Teams部署](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何透過Microsoft 365 Apps 企業版排除Teams部署

若要深入瞭解Teams和Microsoft 365 Apps 企業版，請參閱[如何將Teams從新安裝的Microsoft 365 Apps 企業版中排除](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)，以及[使用群組原則控制Teams的安裝](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>將Teams桌面應用程式部署到 VM

1. 使用下列其中一個連結下載符合 VDI VM 作業系統的Teams MSI 套件：

    - [32 位版本](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [64 位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > 如果是政府雲端，請參閱[使用 Windows Installer (MSI) 大量安裝Teams，](msi-deployment.md)以取得 MSI 檔案的下載連結。

    Teams傳統型應用程式的最低版本是版本 1.3.00.4461。 舊版不支援 PSTN 保留。

2. 執行下列其中一個命令，將 MSI 安裝到 VDI VM：

    - 個別使用者安裝 (預設) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此程式是預設安裝，會將Teams安裝到 `%AppData%` 使用者資料夾。 此時，金色影像設定已完成。

        > [!IMPORTANT]
        > Teams無法針對非持續性設定的每個使用者安裝正常運作。

    - 每台電腦安裝

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此程式會在電腦上新增必要的登錄機碼，讓Teams安裝程式知道這是 VDI 實例。  如果沒有，安裝程式會出錯，指出：「安裝已失敗。  偵測不到 VDI 環境時，無法為所有使用者安裝。」

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此程式會將Teams安裝到 `%ProgramFiles(x86)%` 64 位作業系統上的資料夾，以及安裝到 `%ProgramFiles%` 32 位作業系統上的資料夾。 此時，金色影像設定已完成。

        > [!IMPORTANT]
        >  非持續性設定需要每台電腦安裝Teams。

        當下一個互動式登入會話開始時，Teams啟動並要求認證。

        > [!NOTE]
        > 這些範例也會使用參數 `ALLUSERS=1` 。 當您設定此參數 **時，Teams Machine-Wide安裝程式** 會出現在 **主控台** 的 **[程式和功能**] 和 [**應用程式] &** **Windows 設定** 中所有電腦使用者的功能中。 所有使用者只要具備系統管理員認證，就可以卸載Teams。
        >
        > 請務必瞭解兩者之間的 `ALLUSERS=1` 差異。 `ALLUSER=1` 參數 `ALLUSERS=1` 可用於非 VDI 和 VDI 環境中，而 `ALLUSER=1` 參數僅用於 VDI 環境以指定每部電腦安裝。

3. 從 VDI VM 卸載 MSI。 卸載Teams的方法有兩種。

    - **PowerShell 腳本**：您可以使用 [Teams部署清理](scripts/powershell-script-deployment-cleanup.md)PowerShell 腳本來卸載Teams並移除使用者的Teams資料夾。 針對電腦上安裝Teams的每個使用者設定檔執行腳本。
    - **命令列**：執行下列命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      視作業系統環境而定，此程式會從 `%ProgramFiles(x86)%` 資料夾或 `%ProgramFiles%` 資料夾卸載Teams。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 效能考慮的Teams

有各種不同的虛擬化設定設定，每個設定都有不同的優化焦點。 例如，設定可能會著重于使用者密度。 規劃時，請考慮下列專案，以根據貴組織的工作負載需求來協助優化設定。

- **最低需求**：某些工作負載可能需要使用高於最低需求的資源進行設定。 例如，針對使用需要更多運算資源之應用程式的開發人員工作負載。
- **相依性**：這些相依性包括基礎結構、工作負載，以及Teams桌面應用程式外部的其他環境考慮。
- **VDI 上的停用功能**：Teams停用 VDI 需要大量 GPU 的功能，這有助於改善暫時性的 CPU 使用率。 下列功能已停用：
    - Teams CSS 動畫
    - Giphy 自動啟動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>使用通話和會議在 VDI 上Teams

除了聊天和共同作業之外，VDI 上的通話和會議Teams可在支援的虛擬化提供者平臺上使用。 支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者實作為基礎。 下圖提供架構的概觀。

![顯示 VDI 架構上Teams的圖表。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果您目前在 VDI 中未執行 AV 優化的Teams，而且您使用尚未支援優化的功能 (例如在應用程式共用) 時授與及控制，則必須設定虛擬化提供者原則，以關閉Teams重新導向。 這表示Teams媒體會話不會優化。 如需如何設定原則以關閉Teams重新導向的步驟，請連絡您的虛擬化提供者。

### <a name="network-requirements"></a>網路需求

我們建議您評估您的環境，以找出可能會影響整體雲端語音和視訊部署的任何風險和需求。 使用[商務用 Skype網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試您的網路是否已準備好進行Teams。

若要深入瞭解如何為Teams準備您的網路，請參閱[準備貴組織的網路以供Teams](prepare-network.md)使用。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>從 VDI 上的商務用 Skype移轉到 VDI 上的Teams

如果您要從 VDI 上的商務用 Skype移轉到 VDI 上的Teams，除了兩個應用程式之間的差異之外，在實作 VDI 時會有一些差異。 商務用 Skype VDI 中目前不支援Teams VDI 的部分功能如下：

- 停用 VDI 中部分 AV 功能的每個平臺原則
- 在應用程式共用時給予並取得控制權
- 不含音訊的聊天畫面分享
- 同時傳送和接收視訊和螢幕畫面分享

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>在 Chrome 瀏覽器上Teams VDI 的Teams桌面應用程式

Teams在 Chrome 瀏覽器上未提供使用 AV 優化來取代 VDI 的Teams桌面應用程式。 聊天和共同作業體驗如預期般運作。 需要媒體時，Chrome 瀏覽器上的某些體驗可能不符合使用者預期：

- 音訊和視訊串流體驗可能不是最佳體驗。 使用者可能會遇到延遲或品質降低的問題。
- 瀏覽器設定中無法使用裝置設定。
- 裝置管理是透過瀏覽器處理，需要在瀏覽器網站設定中進行多個設定。
- 裝置設定可能也需要在Windows裝置管理中設定。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>使用聊天和共同作業在 VDI 上Teams

如果貴組織只想在Teams中使用聊天和共同作業功能，您可以設定使用者層級原則，關閉 Teams 中的通話和會議功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定原則以關閉通話和會議功能

您可以使用Teams系統管理中心或 PowerShell 來設定原則。 最多幾個小時後原則變更就會散播。 如果您沒有立即看到指定帳戶的變更，請在幾個小時後再試一次。

[**通話原則**](teams-calling-policy.md)：Teams包含內建 **的 DisallowCalling** 通話原則，其中會關閉所有通話功能。 將 **不允許縮** 放原則指派給在虛擬環境中使用Teams組織中的所有使用者。

[**會議原則**](meeting-policies-overview.md)：Teams包含內建的 **AllOff** 會議原則，其中會關閉所有會議功能。 將 **AllOff** 原則指派給在虛擬環境中使用Teams組織中的所有使用者。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用Teams系統管理中心指派原則

若要將 **DisallowCalling** 通話原則和 **AllOff** 會議原則指派給使用者：

1. 在系統管理中心的左側導 Teams覽畫面中，移至 [**使用者]**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話原則]** 底下，按一下 **[不允許縮放]**。
    2. 在 **[會議原則]** 底下，按一下 **[AllOff]**。
4. 按一下 [ **套用]**。

若要一次將原則指派給多位使用者：

1. 在Teams系統管理中心的左側導覽中，移至 [**使用者**]，然後搜尋使用者或篩選檢視以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請按一下表格頂 **端&#x2713;(** 核取記號) 。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Teams系統管理中心的左側導覽畫面中，移至您要指派的原則。 例如：
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

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>使用聊天和共同作業在 VDI 上移轉Teams，以優化通話和會議Teams

如果您已經在 VDI 上使用聊天和共同作業來實作Teams，其中您已設定使用者層級原則來關閉通話和會議功能，而您是透過 AV 優化移轉到Teams，則必須設定原則，為 VDI 使用者開啟這些Teams的通話和會議功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>設定原則以開啟通話和會議功能

您可以使用Teams系統管理中心或 PowerShell 來設定和指派通話和會議原則給使用者。 可能需要幾個小時的時間 () 原則變更才會散播。 如果您沒有看到指定帳戶的變更，請在幾個小時後再試一次。

[**通話原則**](teams-calling-policy.md)：Teams控制哪些通話功能可供使用者使用。 Teams包含內建 **的 AllowCalling** 通話原則，其中會開啟所有通話功能。 若要開啟所有通話功能，請指派 **AllowCalling 原則** 。 或者，建立自訂通話原則來開啟您要的通話功能，並將它指派給使用者。

[**會議原則**](meeting-policies-overview.md)：Teams中的會議原則控制使用者可以建立的會議類型，以及組織中使用者排程的會議參與者可用的功能。 Teams包含內建的 **AllOn** 會議原則，其中會開啟所有會議功能。 若要開啟所有會議功能，請指派 **AllOn** 原則。 或者，建立自訂會議原則來開啟您要的會議功能並指派使用者。

#### <a name="assign-policies-using-the-teams-admin-center"></a>使用Teams系統管理中心指派原則

若要將 **AllowCalling** 通話原則和 **AllOn** 會議原則指派給使用者：

1. 在系統管理中心的左側導 Teams覽畫面中，移至 [**使用者]**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話原則]** 底下，按一下 **[允許縮放]**。
    2. 在 **[會議原則]** 底下，按一下 **[AllOn]**。
4. 按一下 [ **套用]**。

若要一次將原則指派給多位使用者：

1. 在Teams系統管理中心的左側導覽中，移至 [**使用者**]，然後搜尋使用者或篩選檢視以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請按一下表格頂 **端&#x2713;(** 核取記號) 。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列動作：

1. 在 Teams系統管理中心的左側導覽畫面中，移至您要指派的原則。 例如：
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

## <a name="control-fallback-mode-in-teams"></a>在 Teams 中控制後援模式

當使用者從不受支援的端點連線時，使用者會處於後援模式，而 AV 未優化。 您可以設定下列其中一個登錄 `DWORD` 值，停用或啟用後援模式：

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

若要停用後援模式，請將值設為 **1**。 若要只啟用音訊，請將值設為 **2**。 如果值不存在或設為 **0** (零) ，則會啟用後援模式。

此功能適用于 Teams 版本 1.3.00.13565 及更新版本。

## <a name="disable-audio-and-video-settings-for-vdi"></a>停用 VDI 的音訊和視訊設定

Teams VDI 原則可在Teams模組中使用。 這些原則在非優化的 VDI 環境中為使用中並強制執行。

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

當 VDI 原則設定為在 VDI `DisableCallsAndMeetings` 上登 `$true` 入Teams的使用者無法：

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

當 VDI 原則設定為登入 `$true` VDI `DisableAudioVideoInCallsAndMeetings` Teams的使用者時，他們會：

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

- 透過每台電腦安裝，VDI 上的Teams不會以非 VDI Teams用戶端的方式自動更新。 您必須安裝新的 MSI 來更新 VM 映射，如[VDI 上安裝或更新Teams桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)一節中所述。 您必須解除安裝目前的版本，以更新至較新的版本。
- 在 Citrix 環境中，如果使用者在執行Teams時中斷與虛擬機器的連線，Teams更新可能會導致使用者在重新連線時處於未優化的 AV 狀態。 我們建議使用者在中斷與 Citrix 虛擬機器的連線前結束Teams，以免發生這種情況。
- Teams應該每個使用者或每台電腦部署。 不支援針對每個使用者和每部電腦同時部署Teams。 若要從每部電腦或每位使用者移轉到其中一個模式，請遵循卸載程式，然後重新部署至任一模式。
- Azure 虛擬桌面目前不支援macOS和 Linux 型用戶端。
- 快速租使用者切換可能會導致 VDI 上的通話相關問題，例如螢幕畫面分享無法使用。 重新開機用戶端將會減輕這些問題。

### <a name="notifications"></a>通知

- Windows Server 2016主機不支援Windows工作列上的訊息計數通知和目前狀態。

### <a name="calling-and-meetings"></a>通話和會議

不支援下列通話和會議功能：

- 任何多視窗功能，例如新會議體驗或新會議體驗隨附的任何功能
- Citrix 和 VMware Teams應用程式與裝置之間的 HID 按鈕和 LED 控制項
- 背景模糊和效果
- 廣播和即時活動製作人和簡報者角色
- Location-Based路由 (LBR) 
- PSTN 通話回撥鈴聲
- 共用系統音訊/電腦音效
- 直接路由的媒體旁路
- 縮放控制項

> [!NOTE]
> 我們正在努力新增目前僅適用于非 VDI 環境中的通話和會議功能。 這些功能可能包括更多對品質的系統管理員控制、其他螢幕畫面分享案例，以及最近新增至Teams的進階功能。 請連絡您的Teams代表，以深入瞭解即將推出的功能。

以下是通話和會議的已知問題和限制：

- 商務用 Skype的互通性僅限於音訊通話;沒有視訊形式。
- 內送和外寄視訊串流解析度限制為 720p 解析度。
- 僅支援來自內送相機或螢幕共用串流的一個視訊串流。 當有內送螢幕共用時，會顯示該螢幕共用，而不是主要喇叭的視訊。
- 如果裝置已中斷連線，然後重新連線，Teams不會切換為使用使用者選取的最後一個音訊裝置。
- 即時活動未優化。
- 外寄螢幕畫面分享：
  - 不支援應用程式共用。
- 授與控制權並取得控制權：
  - 螢幕共用或應用程式共用會話期間不支援。
  - 在PowerPoint共用會話期間支援。

如需Teams與 VDI 無關的已知問題，請參閱[貴組織的支援Teams](/MicrosoftTeams/troubleshoot/teams-welcome)。

## <a name="troubleshooting"></a>疑難排解

### <a name="troubleshoot-citrix-components"></a>疑難排解 Citrix 元件

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams當機或Teams登入畫面為空白

這是 Citrix VDA 版本 1906 和 1909 的已知問題。 若要解決此問題，請新增下列登錄 `DWORD` 值，並將其設為 `204` (十六進位) 。

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

然後重新開機 VDA。 若要深入瞭解，請參閱這篇 Citrix 支援文章：[針對Microsoft Teams的 HDX 優化進行疑難排解](https://support.citrix.com/article/CTX253754)。

## <a name="related-topics"></a>相關主題

- [使用 Windows Installer (MSI) 大量安裝Teams](msi-deployment.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Azure 虛擬桌面上使用 Microsoft Teams](/azure/virtual-desktop/teams-on-wvd)
