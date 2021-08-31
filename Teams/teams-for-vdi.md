---
title: 適用於虛擬桌面架構的 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬桌面基礎結構Microsoft Teams VDI (中執行) 程式。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1353d46d77f12ea7d829f4170f6dedf335e9395
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729532"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>適用於虛擬桌面架構的 Teams

本文將說明在虛擬化環境中使用Microsoft Teams的需求和限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構 (VDI) 是虛擬化技術，在資料中心集中式伺服器上託管桌面作業系統和應用程式。 這可讓擁有完全安全且符合規範的集中式來源的使用者獲得完全個人化的桌面體驗。

Microsoft Teams環境中，支援聊天和共同合作。 此外，使用 Azure 虛擬桌面、Citrix 和 V Azure 平臺，通話和會議功能也受到支援。

Teams環境中，系統支援多種配置。 這些包括 VDI、專用、共用、永久和非持續性模式。 功能正在持續開發中，並且會定期新增，且功能將會于未來幾個月和數年內擴充。

在Teams環境中使用應用程式可能與在非虛擬化Teams環境中使用應用程式稍有不同。 例如，某些進位功能可能無法在虛擬化環境中使用，而且視像解析度可能會有所不同。

若要確保最佳的使用者體驗，請遵循本文中的指引。

> [!Note]
> 有關在不同平臺上Teams VDI 的詳細資訊，請參閱[Teams平臺的功能。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams VDI 元件上的

在Teams環境中使用應用程式需要下列元件。

- **虛擬化代理**：虛擬化提供者的資源和連接管理員，例如 Azure
- **虛擬桌面**：虛擬機器 (虛擬機器) 堆疊Microsoft Teams
- **精簡用戶端**：使用者實際介面的端點
- **Teams桌面應用程式**：Teams桌面用戶端應用程式

## <a name="teams-on-vdi-requirements"></a>Teams VDI 需求

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

桌面Teams已與領先虛擬化解決方案提供者驗證。 對於多個市場提供者，我們建議您諮詢您的虛擬化解決方案提供者，以確保您符合最低需求。
  
目前，Teams音訊/視 (AV) 的 VDI 已通過 Azure 虛擬桌面、Citrix 和 V3 的認證。 請閱閱本節的資訊，以確保您符合正確功能的所有需求。

### <a name="platforms-certified-for-teams"></a>平臺已Teams

下列平臺提供適用于 Teams 的虛擬桌面基礎結構Teams。

|平台|解決 方案|
|----|---|
|![代表 Microsoft 的標誌。](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure 虛擬桌面</a> |
|![代表 Citrix 的標誌。](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬應用程式與桌面</a> |
|![代表 V3 的標誌。](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure 虛擬桌面

Azure 虛擬桌面提供 VDI Teams AV 優化。 若要深入瞭解和需求及安裝，請參閱在 Azure 虛擬Teams[使用應用程式](/azure/virtual-desktop/teams-on-wvd)。

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>奇思虛擬應用程式與桌面需求

在 VDI 上 (XenApp 和 XenDesktop) 提供視Teams的 AV 優化。 有了 Citrix 虛擬 App 和桌面Teams，VDI 上的應用程式除了支援聊天和共同合作之外，還支援通話和會議功能。

您可以在 Citrix 下載網站下載最新版本的 [Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)虛擬 App 和桌面。  (您必須先登錄。) 根據預設，必要元件會套件到 Citrix Workspace 應用程式 [ (CWA) ](https://www.citrix.com/downloads/workspace-app/) 和虛擬傳遞代理程式 (VDA) 。 您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。

有關最新的伺服器和用戶端需求，請參閱 [此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace 和桌面需求

V Azure Horizon 是一個現代化平臺，可安全地跨混合式雲端傳遞虛擬桌面和應用程式。 為了提供出色的使用者體驗，V3 Horizon 提供媒體優化Teams。 此優化可改善虛擬桌面和應用程式的整體生產力，並增強使用 Teams 通話和會議時Teams。

您可以從 V 試用版下載頁面下載[最新版本的 V3 Horizon。](https://customerconnect.vmware.com/downloads/#all_products) 根據預設，所需的媒體優化元件是 Horizon Agent 和 Horizon Client 的一部分，因此不需要安裝任何其他外掛程式，以使用 Teams。

若要取得有關如何設定媒體優化功能的最新需求Teams，請參閱[此 V3 網站](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上Teams或更新桌面應用程式

您可以使用每Teams安裝或使用 MSI 套件的每個使用者安裝來部署 VDI 的桌面應用程式。 決定使用哪種方法取決於您是使用持續性或非持續性設定，以及貴組織的關聯功能需求。

對於專用的永久設定，任一方法都適合使用。 不過，對於非持續性設定，Teams需要每部電腦安裝，才能有效率地運作。 請參閱 [非持續性設定一](#non-persistent-setup) 節。

每部電腦安裝時，自動更新會停用。 這表示若要更新 Teams應用程式，您必須卸載目前的版本，以更新至較新版本。 每使用者安裝時，自動更新會啟用。 對於大部分的 VDI 部署，建議您使用Teams部署。

若要更新至最新版本Teams，請從卸載程式開始，Teams版本部署。

若要Teams VDI 環境中進行 AV 優化以正常運作，精簡用戶端端點必須能夠存取網際網路。 如果精簡用戶端端點無法存取網際網路，優化啟動將不會成功。 這表示使用者是未優化的媒體狀態。

#### <a name="dedicated-persistent-setup"></a>專用永久設定

在專用的永久設定中，使用者登出後會保留使用者的當地作業系統變更。 針對永久設定，Teams支援每個使用者和每部電腦安裝。

以下是建議的最小值 VM 組組。

|參數  |工作站作業系統  |伺服器作業系統  |
|---------|---------|---------|
|vCPU   |    2 個核心     |  4、6 或 8<br>瞭解 NUMA (的基本非統一) 存取權，並據此設定您的虛擬機器。     |
|RAM     |   4 GB      | 每個使用者 512 到 1024 MB        |
|儲存空間    | 8 GB        | 40 到 60 GB        |

#### <a name="non-persistent-setup"></a>非持續性設定

在非持續性設定中，使用者登出後不會保留使用者的當地作業系統變更。 這類設定是一般共用的多使用者會話。 VM 組式會依據使用者數量和可用的實體方塊資源而不同。

對於非持續性設定，Teams桌面應用程式必須安裝在每部電腦上，以至金色影像。  (若要深入瞭解，請參閱在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或更新 Teams 桌面應用程式一節。) 這可確保在使用者會話期間有效率地啟動 Teams 應用程式。

在Teams設定中使用資料庫也需要設定檔-緩存管理員，Teams執行時間資料同步處理。 有效的資料同步處理可確保在使用者會話 (使用者的資料、設定檔或設定等適當的使用者特定資訊) 在使用者的會話期間進行緩存。 確認這兩個資料夾中的資料已同步處理：<br>

- C：\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache) 
- C：\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams) 

> [!NOTE]
> 若要確保 Teams 應用程式具有執行應用程式所需的執行時間資料和檔案， (或如果您使用資料夾重新導向，則需要快處理管理員) 。 這是為了減少網路延遲問題或網路問題所必須的，否則會造成應用程式錯誤，以及因數據與檔案無法使用而造成緩慢的體驗。

有許多可用的緩存管理員解決方案。 例如 [，FSLogix](/fslogix/overview)。 請參閱您的緩存管理員提供者，以獲得特定組組指示。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams非持續性設定之緩存內容排除清單

將下列專案排除在 Teams 資料夾 %appdata%/Microsoft/Teams。 排除這些專案有助於減少使用者緩存大小，進一步優化非持續性設定。

- .txt檔案
- 媒體堆疊資料夾
- 會議-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache) 

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365 Apps 企業版考慮

當您在 VDI 上使用 Teams部署Microsoft 365 Apps 企業版時，請考慮下列事項。

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>新部署Teams Microsoft 365 Apps 企業版

在透過 Teams部署Microsoft 365 Apps 企業版，您必須先卸載任何預先Teams應用程式 ，如果他們是使用每部電腦安裝進行部署。

Teams每個Microsoft 365 Apps 企業版安裝一次。 若要深入瞭解，請參閱在 VDI 上安裝Teams[更新桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)> 一節。

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams更新來Microsoft 365 Apps 企業版部署

Teams也會新增到現有的 Microsoft 365 Apps 企業版。 由於Microsoft 365 Apps 企業版僅Teams使用者安裝，請參閱在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或Teams桌面應用程式>一節。

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>使用Teams機器安裝及Microsoft 365 Apps 企業版

Microsoft 365 Apps 企業版不支援每部電腦安裝 Teams。 若要使用每部電腦安裝，您必須將Teams排除Microsoft 365 Apps 企業版。 請參閱將[桌面Teams應用程式部署到虛擬機器](#deploy-the-teams-desktop-app-to-the-vm)，以及如何透過Teams[排除Microsoft 365 Apps 企業版](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)部署。

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>如何透過Teams排除Microsoft 365 Apps 企業版

若要深入瞭解Teams Microsoft 365 Apps 企業版，請參閱如何將 Teams 排除在 Microsoft 365 Apps 企業版[的新安裝](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps)，以及使用群組原則來控制[Teams。](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>將桌面Teams應用程式部署到虛擬機器

1. 使用下列Teams之一下載符合 VDI VM 作業系統的 MSI 套件：

    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 有關政府雲端，[請參閱Microsoft Teams安裝Microsoft Endpoint Configuration Manager](msi-deployment.md) MSI 檔案的下載連結。

    桌面應用程式的最低Teams版本為版本 1.3.00.4461。  (版本不支援 PSTN 保留) 

2. 執行下列其中一個命令，將 MSI 安裝到 VDI VM：

    - 每個使用者安裝 (預設) 
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        此程式是預設安裝，Teams %AppData% 使用者資料夾。 此時，金色影像設定已完成。 Teams無法與非持續性設定上的每個使用者安裝一起正常運作。

    - 每部電腦安裝

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        此程式會新增必要的登錄機碼至電腦，讓安裝程式Teams知道它是 VDI 實例。  如果沒有安裝，安裝程式就會發生錯誤，指出：「安裝失敗。  當未偵測到 VDI 環境時，無法為所有使用者安裝。」

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        此程式會Teams 64 位作業系統上的 (x86) 資料夾，以及 32 位作業系統上的程式檔案資料夾。 此時，金色影像設定已完成。 非Teams安裝時，必須安裝每部電腦。

        下一個互動式登入會話Teams並詢問認證。

        > [!NOTE]
        > 這些範例也會使用 **ALLUSERS=1** 參數。 當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，&應用程式會顯示Windows 設定適用于電腦的所有使用者。 然後所有使用者都可以卸載Teams，如果他們有系統管理員認證。
        瞭解 **ALLUSERS=1** 與 **ALLUSER=1** 的差異非常重要。 **ALLUSERS=1** 參數可用於非 VDI 和 VDI 環境，而 **ALLUSER=1** 參數僅適用于 VDI 環境，以指定每部電腦安裝。

3. 從 VDI VM 卸載 MSI。 有兩種方法可以卸載Teams。

    - PowerShell 腳本：您可以使用[這個 PowerShell](scripts/powershell-script-deployment-cleanup.md)腳本來卸載Teams並移除Teams資料夾。 針對每一個使用者設定檔執行腳本，Teams電腦上安裝該設定檔。
    - 命令列：執行下列命令。
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      此程式會視Teams環境 (x86) 資料夾或程式檔案資料夾中卸載程式檔案。

## <a name="teams-on-vdi-performance-considerations"></a>Teams VDI 的績效考慮

有各種不同的虛擬化設定設定，每個設定都有不同的優化焦點。 例如，組組可能會著重于使用者密度。 規劃時，請考慮下列專案，協助根據貴組織的工作量需求優化您的設定。

- 最低需求：某些工作負載可能需要使用高於最低需求的資源進行設定。 例如，針對使用需要更多計算資源之應用程式之開發人員的工作負載。
- 相依性：這些包括基礎結構、工作負載和其他環境考慮的相依性，Teams應用程式。
- VDI 上的停用功能：Teams停用 VDI 的 GPU 密集功能，這有助於改善暫態 CPU 使用率。 下列功能已停用：
    - TeamsCSS 動畫
    - Giphy 自動啟動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams VDI 使用通話和會議

除了聊天和共同Teams，支援虛擬化提供者平臺Teams VDI 上的通話和會議功能。 支援的功能是以 WebRTC 媒體堆疊和虛擬化提供者的實現為基礎。 下圖提供架構概觀。

![顯示 VDI 架構Teams圖表。](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 如果您目前執行 Teams VDI 時沒有 AV 優化，而且使用尚未支援優化的功能 (例如應用程式共用時提供並控制) ，您必須設定虛擬化提供者政策以關閉 Teams 重新導向。 這表示Teams媒體會話不會優化。 如需如何設定關閉重新導向Teams相關步驟，請與您的虛擬化提供者聯繫。

### <a name="network-requirements"></a>網路需求

我們建議您評估您的環境，找出可能會影響整體雲端語音和視像部署的任何風險與需求。 使用 商務用 Skype[網路評定](https://www.microsoft.com/download/details.aspx?id=53885)工具，測試您的網路是否已準備好Teams。

若要深入瞭解如何準備您的網路以Teams，請參閱準備貴組織的網路[以Teams。](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>從 VDI 商務用 Skype的用戶端Teams VDI 上的應用程式

如果您要從 VDI 上的 商務用 Skype移至 VDI 上的 Teams，除了這兩個應用程式之間的差異之外，在 VDI 也實現時也會有一些差異。 VDI 中目前不支援的Teams VDI 商務用 Skype如下：

- 在 VDI 中停用部分 AV 功能的每個平臺策略
- 在 App 共用時給予並控制
- 從沒有音訊的聊天分享螢幕畫面
- 同時傳送和接收視像和螢幕畫面共用

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams瀏覽器與 VDI Teams桌面應用程式

Teams瀏覽器上的應用程式無法以 AV 優化取代 VDI Teams桌面應用程式。 聊天和共同合作體驗如預期運作。 當需要媒體時，Chrome 瀏覽器上的某些體驗可能不符合使用者預期：

- 音訊和視音訊串流體驗可能並非最佳。 使用者可能會遭遇延遲或品質降低的問題。
- 瀏覽器設定中無法提供裝置設定。
- 裝置管理是透過瀏覽器處理，需要瀏覽器網站設定中的多個設定。
- 您可能需要在裝置管理中設定Windows設定。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams聊天和共同合作使用 VDI

如果貴組織只想在 Teams 中使用聊天和共同Teams，您可以設定使用者層級策略，以在 Teams 中關閉通話和Teams。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定關閉通話和會議功能的政策

您可以使用系統管理中心或 PowerShell Microsoft Teams設定策略。 可能需要幾個小時 (，) 策略變更才能傳播。 如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。

[**通話策略**](teams-calling-policy.md)：Teams包括內建的 DisallowCalling 通話政策，其中所有通話功能都已關閉。 將 DisallowCalling 政策指派給組織中在虛擬化環境中Teams的所有使用者。

[**會議政策**](meeting-policies-in-teams.md)：Teams包含內建的 AllOff 會議政策，其中會關閉所有會議功能。 將 AllOff 政策指派給組織中在虛擬化環境中Teams使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用系統管理中心Microsoft Teams指派政策

若要將 DisallowCalling 通話策略和 AllOff 會議策略指派給使用者：

1. 在系統管理中心的左側導Microsoft Teams，請前往 **使用者**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話政策中**， **Click DisallowCalling.**
    2. 在 **[會議政策>** 下，按一下 **[AllOff>**。
4. 按一下 **[Apply.**

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列操作：

1. 在系統管理中心的左側導Microsoft Teams，前往您想要指派的政策。 例如：
    - 請前往 **[**  >  **語音通話政策**，然後按一下 **[取消禁止使用Calling>**。
    - 前往[  >  **會議會議政策**，然後按一下 **AllOff**。
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 新增使用者完成後，請按一下 [**儲存。**

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派策略

下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話策略指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議策略指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>使用Teams和共同合作在 VDI 上遷移Teams通話和會議來優化通話和會議

如果您在 VDI 上有現有的 Teams 與聊天和共同合作的實現，其中您設定了使用者層級策略以關閉通話和會議功能，而您正使用 AV 優化移轉至 Teams，則必須設定策略，為 VDI 使用者上的 Teams 開啟通話和會議功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>設定開啟通話和會議功能的政策

您可以使用系統管理Microsoft Teams PowerShell 來設定和指派通話和會議政策給使用者。 可能需要幾個小時 (，) 策略變更才能傳播。 如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。

[**通話策略**](teams-calling-policy.md)：Teams控制哪些通話功能可供使用者使用。 Teams包含內建的 AllowCalling 通話政策，其中所有通話功能都開啟。 若要開啟所有通話功能，請指派 AllowCalling 政策。 或者，建立自訂通話策略以開啟您想要的通話功能，並將它指派給使用者。

[**會議政策**](meeting-policies-in-teams.md)：Teams中的會議政策可控制使用者可以建立的會議類型，以及貴組織中使用者所排程的會議參與者可用的功能。 Teams包含內建的 AllOn 會議政策，其中所有會議功能都開啟。 若要開啟所有會議功能，請指派 AllOn 策略。 或者，建立自訂會議策略以開啟您想要的會議功能，並指派給使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用系統管理中心Microsoft Teams指派政策

若要將 AllowCalling 通話策略和 AllOn 會議策略指派給使用者：

1. 在系統管理中心的左側導Microsoft Teams，請前往 **使用者**。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]。
3. 請執行下列動作：
    1. 在 **[通話政策>** 下，按一下 **[AllowCalling>**。
    2. 在 **[會議政策>** 下，按一下 **[AllOn.**
4. 按一下 **[Apply.**

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請按一下&#x2713;() 上方的核取方塊。 
3. 按一下 [編輯設定]，進行所需的變更，然後按一下 [套用]。

或者，您也可以執行下列操作：

1. 在系統管理中心的左側導Microsoft Teams，前往您想要指派的政策。 例如：
    - 前往 **[語音**  >  **通話政策**，然後按一下 **AllowCalling。**
    - 前往[  >  **會議會議政策**，然後按一下 **AllOn。**
2. 選取 [管理使用者]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 新增使用者完成後，請按一下 [**儲存。**

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派策略

下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 AllowCalling 通話策略指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOn 會議策略指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="control-fallback-mode-in-teams"></a>控制項的後Teams

當使用者從不支援的端點進行連接時，使用者會進入退後模式，而 AV 未優化。 您可以設定下列其中一個註冊表 DWORD 值，以停用或啟用退後模式：

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

若要停用退後模式，將值設為 **1。** 若要僅啟用音訊，請設定為 **2。** 如果值不存在或設為 0 (**0，)** 會啟用退後模式。

此功能可在版本 1.3.00.13565 Teams版本 1.3.00.13565 及更新版本中提供。

## <a name="disable-audio-and-video-settings-for-vdi"></a>停用 VDI 的音訊和視像設定

TeamsVDI 政策可在 Microsoft Teams 模組中提供。 這些策略在未優化的 VDI 環境中是使用中且強制執行的。

- New-CsTeamsVdiPolicy  
- Grant-CsTeamsVdiPolicy
- Remove-CsTeamsVdiPolicy
- Set-CsTeamsVdiPolicy

> [!NOTE]
> 這僅適用于未優化的環境。

### <a name="update-a-module-name"></a>更新模組名稱

update-Module -Name MicrosoftTeams -AllowPrerelease

```PowerShell
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

### <a name="set-policies-to-limit-calling-features"></a>設定限制通話功能的政策

當具有此 VDI 策略設定 -DisableCallsAndMeetings $true在 VDI 上Teams使用者時，他們不應能夠：

- 撥打電話。
- 加入會議。
- 從聊天執行螢幕分享。

應該停用所有類型的通話。

> [!NOTE]
> 這僅適用于未優化的環境。

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

使用 VDI 策略設定 -DisableAudioVideoInCallsAndMeetings $true在 VDI 上登Teams時，他們應該能夠：

- 從聊天執行螢幕分享。
- 加入會議並共用螢幕。 將音訊移至手機。
- 使用者不應該從 VDI 進行人員對人的音訊和視像通話。

> [!NOTE]
> 這僅適用于未優化的環境。

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>已知問題和限制

### <a name="client-deployment-installation-and-setup"></a>用戶端部署、安裝和設定

- 每部電腦安裝Teams VDI 上的更新不會以非 VDI 和用戶端Teams的方式自動更新。 您必須安裝新的 MSI 以更新 VM 映射，如在[VDI](#install-or-update-the-teams-desktop-app-on-vdi)上安裝或更新Teams桌面應用程式一節中所述。 您必須解除安裝目前的版本，以更新至較新的版本。
- 在 Citrix 環境中，如果使用者在 Teams 執行時與虛擬機器中斷連接，Teams 更新可能會導致使用者重新連接時，AV 狀態未優化。 建議您在使用者從Teams中斷連接之前先退出此帳戶，以避免發生此情況。
- Teams使用者或每部電腦部署。 不支援Teams使用者和每部電腦同時部署用戶端。 若要從每部電腦或每個使用者遷移到其中一種模式，請遵循卸載程式，然後重新調配至任一模式。
- Azure 虛擬桌面目前不支援 macOS 和 Linux 型用戶端。
- 快速租使用者切換可能會導致 VDI 上的通話相關問題，例如螢幕畫面共用無法提供。 重新開機用戶端將會減輕這些問題。

### <a name="calling-and-meetings"></a>通話和會議

不支援下列通話和會議功能：

- 任何多視窗功能，例如新的會議體驗或任何新會議體驗隨附的功能
- 增強的緊急服務
- 應用程式與裝置之間的 HID 按鈕Teams LED 控制項
- 背景模糊和效果
- 廣播和即時活動製作人及簡報者角色
- Location-Based LBR (路由) 
- PSTN 通話回鈴鈴聲
- 共用系統音訊/電腦音效
- 直接路由的媒體旁路
- 通話停駐
- 縮放控制項

> [!NOTE]
> 我們正在努力新增目前僅適用于非 VDI 環境的通話和會議功能。 這些可能包括對品質的更多系統管理員控制、其他螢幕共用案例，以及最近新加入至 Teams。 請與您的Teams聯絡，以深入瞭解即將推出的功能。

以下是通話和會議的已知問題和限制：

- 與通話的商務用 Skype僅限於音訊通話;沒有視音訊模式。
- 傳入和傳出視音訊串流解析度限制為 720p 解析度。
- 僅支援來自內接相機或螢幕共用流的一個視音訊流。 當有傳入的螢幕共用時，畫面共用會顯示，而不是主要喇叭的視像。
- Teams切換為使用使用者選取的最後一個音訊裝置 ，如果裝置已中斷連接，然後重新連接。
- 即時活動未優化。
- 外發畫面共用：
    - 不支援應用程式共用。
- 提供控制權並控制：
    - 在螢幕畫面共用或應用程式共用會話期間不支援。
    - 在共用會話PowerPoint支援。
- 僅以黃水晶為限的限制
   - 不支援 CWA 上的高 DPI 縮放比例。

若要Teams與 VDI 不相關的已知問題，請參閱Teams[支援。](/MicrosoftTeams/troubleshoot/teams-welcome)

## <a name="troubleshooting"></a>疑難排解

### <a name="troubleshoot-citrix-components"></a>疑難排解黃水晶元件

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams當機或Teams畫面為空白

這是關於 1906 和 1909 的 Citrix VDA 版本已知問題。 若要解決此問題，請新增下列註冊表 DWORD 值，並設定為 204 (十六進位) 。

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

接著，重新開機 VDA。 若要深入瞭解，請參閱此關於針對 系統進行[HDX](https://support.citrix.com/article/CTX253754)優化的疑難Teams。

## <a name="related-topics"></a>相關主題

- [使用 MSI Microsoft Teams安裝](msi-deployment.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 azure Microsoft Teams桌面使用](/azure/virtual-desktop/teams-on-wvd)
