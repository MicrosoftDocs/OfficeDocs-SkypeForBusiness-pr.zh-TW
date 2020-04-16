---
title: 適用於虛擬桌面架構的 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: 瞭解如何在虛擬化桌面基礎結構（VDI）環境中執行 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee41f32ac2237e5e2c6e2e92fd18ea1c1952f7cd
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521609"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>適用於虛擬桌面架構的 Teams

本文將說明在虛擬化環境中使用 Microsoft 團隊的需求與限制。

## <a name="what-is-vdi"></a>什麼是 VDI？

虛擬桌面基礎結構（VDI）是虛擬化技術，可在資料中心的中央伺服器上託管桌面作業系統和應用程式。 這可讓使用者具備完全安全且相容的集中來源，為使用者提供完整的個人化桌面體驗。
 
虛擬化環境中的 Microsoft 團隊支援聊天與共同作業，而且還支援 Citrix 平臺、通話和會議功能。

虛擬化環境中的小組支援多種設定。 其中包括 VDI、專用、共用、持久且不持久的模式。 功能在連續開發並定期新增，功能將會在未來的幾個月和幾年中擴充。
 
在虛擬化環境中使用團隊的方式可能與在非虛擬化環境中使用團隊稍有不同。 例如，某些高級功能可能無法在虛擬化環境中使用，而且可能會有不同的影片解析度。 若要確保最佳的使用者體驗，請遵循本文中的指導方針。

## <a name="teams-on-vdi-components"></a>VDI 元件上的小組

在虛擬化環境中使用團隊需要下列元件。

- **虛擬化 broker**：虛擬化提供者的資源和連線管理員（例如 Azure）
- **虛擬桌面**：執行 Microsoft 團隊的虛擬機器（VM）堆疊
- **瘦用戶端**：使用者使用物理介面的端點
- **團隊桌面應用程式**：這是團隊桌面用戶端應用程式

## <a name="teams-on-vdi-requirements"></a>針對 VDI 需求的小組

### <a name="virtualization-provider-requirements"></a>虛擬化提供者需求

已使用主要的虛擬化解決方案提供者驗證團隊桌面應用程式。 有了多個市場供應商，我們建議您諮詢您的虛擬化解決方案供應商，以確保符合最低需求。
  
目前，具有音訊/視頻（AV）優化的團隊在使用 Citrix 進行認證。 請參閱本節中的資訊，以確保同時滿足 Citrix 與團隊需求，才能正常功能。

### <a name="partners-certified-for-teams"></a>針對團隊認證的合作夥伴

下列合作夥伴擁有小組的虛擬桌面基礎結構解決方案。

|Partner|合作夥伴解決方案|
|----|---|
|![代表 Citrix 的標誌](media/citrix.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 虛擬 App 與桌面</a> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 虛擬 App 與桌面需求

Citrix 虛擬 App 與桌上型電腦（先前稱為 XenApp 和 XenDesktop）為 VDI 上的小組提供 AV 優化。 借助 Citrix 虛擬 App 和電腦版，VDI 的小組除了聊天與共同作業之外，還支援通話和會議功能。

您可以在[這裡](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)下載最新版本的 Citrix 虛擬 App 和桌上型電腦。 （您必須先登入。）預設會將必要的元件捆綁到[Citrix 工作區應用程式（CWA）](https://www.citrix.com/downloads/workspace-app/)和虛擬傳遞代理程式（VDA）。 您不需要在 CWA 或 VDA 上安裝任何其他元件或外掛程式。

如需最新的伺服器和用戶端需求，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>在 VDI 上安裝或更新小組桌面應用程式

您可以使用每電腦安裝或使用 MSI 套件的每個使用者安裝，部署 VDI 版團隊桌面應用程式。 決定使用哪種方法，取決於您使用的是持續性或非持續設定，以及貴組織的相關功能需求。
針對專用的持續設定，這兩種方法都可以運作。  不過，對於非持續性設定，小組需要使用每電腦安裝才能有效運作。 請參閱[非持續性設定](#non-persistent-setup)一節。

在安裝每電腦的情況下，自動更新是停用的。 這表示若要更新團隊應用程式，您必須卸載目前的版本，才能更新為較新的版本。 針對每位使用者安裝，會啟用自動更新。 對於大多數的 VDI 部署，我們建議您使用每電腦安裝來部署團隊。

若要更新為最新的團隊版本，請先從最新的團隊版本部署開始卸載程式。

為了讓 VDI 環境中的團隊 AV 優化功能正常運作，瘦用戶端端點必須能夠存取網際網路。 如果瘦用戶端端點無法使用網際網路存取，優化啟動將會失敗。 這表示使用者處於未優化的媒體狀態。

#### <a name="dedicated-persistent-setup"></a>專用持續設定

在專用的持續設定中，使用者會在使用者登出後保留使用者的本機作業系統變更。  針對持續設定，團隊支援每個使用者和每電腦的安裝。

以下是建議的最低 VM 設定。

|參數  |工作站作業系統  |伺服器作業系統  |
|---------|---------|---------|
|vCPU   |    2個核心     |  4、6或8<br>瞭解基礎非一致性記憶體存取（NUMA）設定並據此設定您的 Vm 非常重要。     |
|RAM     |   4 GB      | 每位使用者512到 1024 MB        |
|儲存空間    | 8 GB        | 40到 60 GB        |

#### <a name="non-persistent-setup"></a>非持久性設定

在非永久性設定中，使用者登出後，使用者的本機作業系統變更就不會保留。 這類設置通常是共用多個使用者會話。 VM 配置會根據使用者數量及可用的物理盒資源而有所不同。

針對非持續性設定，小組桌面應用程式必須安裝在每一台電腦上的黃金影像中。 （若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)）。這可確保在使用者會話期間有效啟動團隊 app。 將團隊與非持久設定搭配使用時，也需要設定檔的快取管理員，才能高效地進行團隊執行時間資料同步處理。這樣可確保在使用者會話期間會快取適當的使用者特定資訊（例如，使用者資料、設定檔和設定）。  有許多可用的緩存管理器解決方案。 例如， [FSLogix](https://docs.microsoft.com/fslogix/overview)。 如需特定的設定指示，請參閱您的快取管理員提供者。

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>小組快取內容排除清單以進行非持續設定

從 [團隊快取] 資料夾（% appdata%/Microsoft/Teams.）中排除下列各項：  排除這些說明可減少使用者的快取大小，進一步優化您的非持久設定。

- .txt 檔案
- 媒體堆疊資料夾

### <a name="office-365-proplus-considerations"></a>Office 365 專業增強版考慮

在 VDI 上使用 Office 365 專業增強版部署團隊時，請考慮下列事項。

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a>透過 Office 365 專業增強版新的團隊部署

在透過 Office 365 專業增強版部署團隊之前，您必須先卸載任何預先存在的團隊應用程式（如果這些 app 是使用各電腦安裝來部署的）。

透過 Office 365 專業增強版的團隊是針對每位使用者所安裝。 若要深入瞭解，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。

#### <a name="teams-deployments-through-office-365-proplus-updates"></a>透過 Office 365 專業增強版更新的團隊部署

團隊也會新增至 Office 365 專業增強版的現有安裝。 由於 Office 365 專業增強版只會針對每位使用者安裝小組，請參閱[安裝或更新 VDI 區段上的小組桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)。

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a>使用團隊進行每電腦安裝和 Office 365 專業增強版

Office 365 專業增強版不支援小組的每電腦安裝。 若要使用 [每電腦安裝]，您必須從 Office 365 專業增強版中排除團隊。 請參閱將[團隊桌面應用程式部署到 VM](#deploy-the-teams-desktop-app-to-the-vm) ，以及[如何透過 Office 365 專業增強版區段排除團隊部署](#how-to-exclude-teams-deployment-through-office-365-proplus)。

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a>如何透過 Office 365 專業增強版排除團隊部署

若要深入瞭解團隊和 Office 365 專業增強版，請參閱[如何從新安裝的 Office 365 專業增強版中排除團隊](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus)，並[使用群組原則來控制團隊的安裝](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)。

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>將團隊桌面應用程式部署到 VM

1. 使用下列其中一個連結，下載與您的 VDI VM 作業系統相符的團隊 MSI 套件：

    - [32位版本](https://statics.teams.cdn.office.net/production-windows/1.3.00.4461/Teams_windows.msi)
    - [64位版本](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.4461/Teams_windows_x64.msi)

    所需的小組桌面應用程式最低版本為版本1.3.00.4461。 （舊版中不支援 PSTN 保留。）

2. 執行下列其中一項命令，將 MSI 安裝到 VDI VM：

    - 每位使用者安裝（預設）
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        這是預設安裝，可將團隊安裝至 [% AppData% user] （使用者）資料夾。 此時，黃金影像設定就完成了。 在非持久性設定上，小組將無法與每位使用者安裝正常運作。

    - 每電腦安裝

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        這會將團隊安裝至64位作業系統上的 [程式檔案（x86）] 資料夾，以及32位作業系統上的 [程式] 資料夾。 此時，黃金影像設定就完成了。 針對非持久的安裝，必須針對每台電腦安裝團隊。

        下次互動式登入會話會啟動團隊並要求認證。

    > [!NOTE]
    > 這些範例也會使用**ALLUSERS = 1**參數。 當您設定此參數時，系統會在 [控制台] 的 [程式和功能] 和 [應用程式 & Windows 設定] 中的 [應用程式] 中，顯示「團隊電腦範圍」的安裝程式。 如果有管理員認證，所有使用者都可以卸載小組。 請務必瞭解**ALLUSERS = 1**與**ALLUSER = 1**之間的差異。 **ALLUSERS = 1**參數可以在非 VDI 和 VDI 環境中使用，而**ALLUSER = 1**參數只會在 VDI 環境中用來指定每電腦安裝。

3. 從 VDI VM 卸載 MSI。

    有兩種方式可以卸載團隊：  
  
    - PowerShell 腳本（建議使用）

    - 命令列：
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      這會從 [程式檔（x86）] 資料夾或 [Program Files] 資料夾中卸載小組，視作業系統環境而定。

## <a name="teams-on-vdi-performance-considerations"></a>VDI 效能考慮的小組

有許多虛擬化設定設定，每個都有不同的焦點可供優化。 例如，使用者密度。 規劃時，請考慮下列事項，以根據貴組織的工作量需求來優化您的設定：

- 最低需求：某些工作負載可能需要使用超過最低需求的資源進行設定。 例如，使用需要更多計算資源之應用程式之開發人員的工作負載。
- 相依性：這些專案包括在小組桌面應用程式以外的基礎結構、工作負載及其他環境考慮因素的相依性。
- VDI 上停用的功能：團隊會針對 VDI 停用 GPU 密集型功能，這可以協助改善暫時的 CPU 利用率。 下列功能已停用：
    - 團隊 CSS 動畫
    - Giphy 自動啟動

## <a name="teams-on-vdi-with-calling-and-meetings"></a>VDI 上的小組與通話與會議

除了聊天與共同作業之外，您還可以使用 Citrix 與會議支援來使用與客戶進行通話與會議支援的小組。 支援的功能是以 WebRTC 媒體堆疊和 Citrix 專用的實現為基礎。 下圖提供架構的概覽。

![顯示 VDI 架構小組的圖表](media/teams-on-vdi-architecture.png)

不支援以下通話與會議功能：

- 增強的緊急服務
- 小組 app 與裝置之間的 HID 按鈕和 LED 控制項
- 背景模糊和效果
- 廣播/即時事件
- 以位置為基礎的路由（LBR）
- 通話駐留
- 通話佇列

> [!IMPORTANT]
> 如果您目前在 VDI 中執行的團隊沒有 AV 優化，且您使用的功能尚不支援（例如，在應用程式共用時授與控制權），您必須設定 Citrix 原則，以關閉小組重新導向。 這表示小組媒體會話不會進行優化。 如需如何設定原則以關閉小組重新導向的步驟，請參閱此[Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)。

我們正在努力新增目前僅適用于非 VDI 環境中的通話與會議功能。 這些專案可能包含更多系統管理員控制品質、其他螢幕共用案例，以及最近新增至團隊的高級功能。 若要深入瞭解即將推出的功能，請與您的小組代表聯繫。

### <a name="network-requirements"></a>網路需求

我們建議您評估您的環境，以找出任何風險與需求，這些風險與需求可能會影響您的整體雲端語音及視頻部署。 使用[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試您的網路是否已準備好供團隊使用。

若要進一步瞭解如何為團隊準備您的網路，請參閱[準備貴組織的小組網路](prepare-network.md)。

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>從 VDI 上的商務用 Skype 遷移到 VDI 的小組

如果您是從 VDI 的商務用 Skype 遷移到 VDI 的小組，除了兩個應用程式之間的差異之外，也會有一些差異。 在商務用 Skype VDI 中，「團隊 VDI」目前不支援的部分功能如下：

- 使用限制媒體比對的原則控制 VDI 通話體驗
- 在 VDI 中停用某些防病毒功能的每個平臺原則
- 在應用程式共用時提供控制權並加以控制
- 不含音訊的聊天螢幕共用
- 同時進行影片和螢幕共用的傳送和接收

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 瀏覽器上的小組與 VDI 的小組桌面應用程式

Chrome 瀏覽器上的小組無法使用 AV 優化來為 VDI 的小組桌面應用程式提供取代。 聊天與共同作業體驗會如期運作。 需要媒體時，有一些經驗可能無法在 Chrome 瀏覽器中滿足使用者的預期：

- 音訊與視頻資料流程體驗可能不是最佳的。 使用者可能會遇到延遲或降低品質。
- 在瀏覽器設定中無法使用裝置設定。
- 裝置管理是透過瀏覽器處理，且需要瀏覽器網站設定中的多項設定。
- 裝置設定也可能需要在 Windows 裝置管理中設定。

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>VDI 上的小組與聊天與共同作業

如果您的組織想要只使用團隊中的聊天與共同作業功能，您可以設定使用者層級原則，以關閉小組中的通話與會議功能。 此功能層級不需要 Citrix 虛擬 App 與桌上型電腦。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定原則以關閉通話與會議功能

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定原則。 策略變更可能需要幾個時間（幾個小時）才能傳播。 如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。

[**通話**](teams-calling-policy.md)原則：團隊包含內建的 DisallowCalling 通話原則，其中所有的通話功能都已關閉。 將 DisallowCalling 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。

[**會議原則**](meeting-policies-in-teams.md)：團隊包含內建的 AllOff 會議原則，其中所有會議功能都已關閉。 將 AllOff 原則指派給貴組織中的所有使用虛擬化環境中的小組的使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心指派原則

若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者，請遵循下列步驟：

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]****。
3. 請執行下列動作：
    1.  按一下 [**呼叫原則**] 底下的 [ **DisallowCalling**]。
    2.  按一下 [**會議原則**] 底下的 [ **AllOff**]。
4. 按一下 **[** 套用]。

若要一次將原則指派給多個使用者，請參閱[大量編輯 Teams 使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。 例如：
    - 移至 [**語音** > **通話原則**]，然後按一下 [ **DisallowCalling**]。
    - 移至 [**會議** > **會議原則**]，然後按一下 [ **AllOff**]。
3. 選取 [管理使用者]****。
4. 在 [管理使用者]**** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]****。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 DisallowCalling 通話原則指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOff 會議原則指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>使用通話與會議，在 VDI 上將團隊遷移到與 Citrix 進行聊天與共同作業

如果您在 VDI 上有現有的小組實現，且您已將使用者層級原則設定為關閉通話與會議功能，且您是透過 AV 優化來移植到 Citrix，則您必須設定原則來針對 VDI 使用者的小組開啟與會議功能。

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>設定原則以開啟通話與會議功能

您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來設定通話與會議原則，並指派給您的使用者。 要傳播原則變更，可能需要一些時間（幾個小時）。 如果您沒有立即看到特定帳戶的變更，請在幾個小時後再試一次。

[**通話**](teams-calling-policy.md)原則：在團隊中呼叫原則控制使用者可以使用哪些通話功能。 團隊包含內建的 AllowCalling 通話原則，其中所有的通話功能都已開啟。 若要開啟所有通話功能，請指派 AllowCalling 原則。 或者，建立自訂通話原則來開啟您想要的通話功能，並將它指派給使用者。 

[**會議原則**](meeting-policies-in-teams.md)：團隊中的會議原則控制使用者可以建立的會議類型，以及由貴組織中的使用者所排程的會議參與者所提供的功能。 團隊包含內建的 AllOn 會議原則，其中所有會議功能都已開啟。 若要開啟所有會議功能，請指派 AllOn 原則。 或者，建立自訂會議原則來開啟您想要的會議功能，並指派給使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心指派原則

若要將 AllowCalling 通話原則和 AllOn 會議原則指派給使用者，請遵循下列步驟：

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]****。
3. 請執行下列動作：
    1.  按一下 [**呼叫原則**] 底下的 [ **AllowCalling**]。
    2.  按一下 [**會議原則**] 底下的 [ **AllOn**]。
4. 按一下 **[** 套用]。

若要一次將原則指派給多個使用者，請參閱[大量編輯 Teams 使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至您要指派的原則。 例如：
    - 移至 [**語音** > **通話原則**]，然後按一下 [ **AllowCalling**]。
    - 移至 [**會議** > **會議原則**]，然後按一下 [ **AllOn**]。
3. 選取 [管理使用者]****。
4. 在 [管理使用者]**** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]****。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例顯示如何使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) ，將 AllowCalling 通話原則指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理通話原則，請參閱[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用[授與 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) ，將 AllOn 會議原則指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 來管理會議原則，請參閱[設定 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)。

## <a name="known-issues-and-limitations"></a>已知問題與限制

### <a name="client-deployment-installation-and-setup"></a>用戶端部署、安裝和設定

- 在每電腦安裝中，VDI 上的團隊不會以非 VDI 團隊用戶端的方式自動更新。 您必須安裝新的 MSI 來更新 VM 影像，如在 VDI 的 [[安裝或更新團隊桌面應用程式](#install-or-update-the-teams-desktop-app-on-vdi)] 區段中所述。 您必須卸載目前的版本，才能更新為較新的版本。
- 團隊應該針對每個使用者或每個電腦來部署。 不支援針對每位使用者和每個電腦並行部署團隊。  若要從每個電腦或每位使用者遷移到其中一個模式，請遵循卸載程式，然後重新部署到其中一種模式。
- 在此時間，Citrix 不支援 MacOs 和 Linux 版用戶端。
- Citrix 不支援使用在端點上定義的明確 HTTP proxy。 

### <a name="calling-and-meetings"></a>通話與會議

- 與商務用 Skype 的互通性限制在音訊通話中，沒有視頻模態。
- 目前不支援雙音調多重頻率（DTMF）與電話系統互動。
- 以匿名使用者身分加入團隊會議不是 AV 優化的。 使用者可以加入會議，且有未優化的體驗。
- 在會議或群組通話中只支援單一傳入的視頻資料流程。 當多人傳送影片時，任何指定時間只會顯示主要喇叭的影片。  
- 內送和外寄的視頻資料流程解析度限制為720p 解析度。 這是 WebRTC 的限制。
- 只支援來自內送相機或畫面共用資料流程的一個影片串流。 當有內送螢幕共用時，就會顯示畫面共用，而不是主要喇叭的影片。
- 外寄螢幕共用：
    - 不支援應用程式共用。
- 授與控制權並加以控制：  
    - 在螢幕共用或應用程式共用會話期間不支援。
    - 在 PowerPoint 共用會話期間支援。
- 在多重監視器設定中進行螢幕共用時，只會共用主要監視器。
- 不支援 CWA 上的高 DPI 縮放。

針對與 VDI 無關的小組已知問題，請參閱[小組的已知問題](Known-issues.md)。

## <a name="troubleshooting"></a>疑難排解

#### <a name="troubleshoot-citrix-components"></a>Citrix 元件疑難排解

如需如何針對 VDA 和 CWA 問題進行疑難排解的資訊，請參閱[此 Citrix 網站](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)。

## <a name="related-topics"></a>相關主題

- [使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
