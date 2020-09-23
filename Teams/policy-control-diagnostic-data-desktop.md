---
title: Microsoft Teams 適用的桌面用戶端必要診斷資料
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 適用的原則控制項的桌面屬性和事件清單。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbac20caa3f1eff0ead7ef0bf7f11d55b7718903
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136016"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 適用的桌面必要診斷資料

下列文章包含 Microsoft Teams 桌面事件的清單，以及每個事件收集的屬性清單。

## <a name="events"></a>事件

> [!NOTE]
> 以下所列的所有事件有共同的屬性，若要檢閱這些屬性，請參閱[隨著所有事件傳送的屬性](#properties-sent-with-all-events)。

### <a name="logging"></a>記錄

> [!NOTE]
> 如需記錄事件之屬性的相關資訊，請參閱[隨著記錄事件傳送的屬性](#properties-sent-with-logging-events)。

- **adal-anonymous-mac.ts:this.logger.logError** - 記錄當您在 Mac 裝置上匿名登入時發生的一般 SSO 錯誤。
- **adalAnonymousUtil.ts:loggingService.getInstance** - 記錄錯誤陳述式記錄，指出應用程式無法啟動匿名使用者驗證。
- **adal-anonymous-windows.ts:this.logger.logError** - 記錄當您在 Windows 裝置上匿名登入時發生的一般 SSO 錯誤。
- **adalBase.ts:this.loggingService.logError** - 記錄所需的資訊，以判斷使用者設定檔為 null 或空白。
- **adal-impl-mac.ts:this.loggingService.logError** - 記錄在驗證期間收到剖析遙測時發生問題，或在 Mac 裝置上登入時發生一般 SSO 錯誤。
- **adal-rigel-windows.ts:this.logger.logError** - 一般記錄陳述式，指出登入我們的會議室裝置時發生一般 SSO 錯誤。
- **adal-sso-windows.ts:this.loggingService.logError** - 記錄登入 Windows 裝置時發生一般 SSO 錯誤，初始化聊天服務時發生錯誤，或登入失敗資訊。
- **appOnlineService.ts:loggingService.getInstance** - 記錄由於啟動期間無法剖析的設定，或由於下載先前的使用者驗證、先前的授權設定發生的錯誤。
- **appStart.ts:loggingService.logError** - 記錄當應用程式無法啟動、磁碟空間錯誤、有效憑證錯誤，或找不到正確的憑證時發生錯誤，並重新啟動應用程式。
- **browserWindowHttp.ts:this.loggingService.logError** - 記錄資訊，指出由於檔案系統發生問題而無法更新應用程式。
- **contextInstallService.ts:loggingService.getInstance** - 記錄在下列情況時發生錯誤：
  - 嘗試剖析或讀取檔案，或解析對關聯式安裝功能而言重要的 URL。
  - URL 縮址器會嘗試執行關聯式安裝功能。
- **crashManager.ts:loggingService.logError** - 記錄資訊，以判斷應用程式當機時錯誤的原因。
- **localStorageService.ts:loggingService.getInstance** - 記錄當基本啟動資料未正確載入而無法執行應用程式時發生錯誤。
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** - 記錄應用程式當機時的錯誤資訊。
- **multiWindowManager.ts:this.logError** - 記錄當基本啟動資料未正確載入而無法執行應用程式時發生錯誤。
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** - 此事件會記錄嘗試啟動相關失敗的通知時發生錯誤。
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - 記錄嘗試使用 Outlook 會議增益集連線至會議時發生錯誤。
- **recoveryManager.ts:loggingService.getInstance** - 記錄更新復原期間發生錯誤。
- **renderer\startPage\startPage.ts:this.logger.logError** - 記錄應用程式開始頁面發生錯誤。
- **settingsService.ts:loggingService.getInstance** - 記錄應用程式設定發生錯誤。
- **updateInfo.ts:loggingService.getInstance** - 記錄傳輸更新時發生錯誤。
- **updatenotification.js:this._loggingService.logError** - 記錄發生磁碟空間問題。
- **utility.ts:loggingService.logError** - 記錄存取本機檔案 (應用程式中的檔案) 時發生錯誤。
- **utility.ts:loggingService.getInstance** - 記錄可用磁碟空間中的錯誤、顯示問題、URL 問題、Cookie 問題、通訊協定或電腦上載入應用程式的登錄機碼問題。
- **windowmanager.js:this._loggingService.logError** - 記錄發生 Cookie 問題、白色畫面問題、桌面與殼層通訊之間的問題、URL 問題、載入頁面訊息的錯誤、程序轉譯的錯誤和網路連線問題。
- **windowmanager.js:loggingService.getInstance** - 記錄當復原時段無法顯示時要指出的資訊。

### <a name="outlook-addin"></a>Outlook 增益集

> [!NOTE]
> 如需 Outlook 增益集事件屬性的相關資訊，請參閱[隨著 Outlook 增益集事件傳送的屬性](#properties-sent-with-outlook-addin-events)。

- **joinmeetingoperation** - 記錄所需的資訊，以將使用者加入會議。
- **meetingaddinapplifecycle** - 記錄有關應用程式狀態的資訊，例如啟：啟動或結束。
- **meetingaddinloadtime** - 記錄從 Outlook 載入會議資訊所需的時間。
- **openmeetingoperation** - 記錄所需的資訊，以開啟排程會議。
- **savemeetingoperation** - 記錄所需的資訊，以在排程會議時儲存會議。

### <a name="scenario"></a>案例

> [!NOTE]
> 如需案例事件屬性的相關資訊，請參閱[隨著案例事件傳送的屬性](#properties-sent-with-scenario-events)。

- **desktop_app_load** - 記錄所需的資訊，以判斷傳統型應用程式已啟動、應初始化服務，且服務可以初始化。
- **desktop_app_not_ready** - 記錄所需的資訊，以判斷傳統型應用程式尚未備妥可運作。
- **desktop_install** - 記錄所需的資訊，以判斷傳統型應用程式已安裝成功或安裝失敗。
- **desktop_previous_lifecycle_invalid** - 記錄所需的資訊，以判斷傳統型應用程式在先前執行然後當機後重新啟動。

### <a name="tracking"></a>追蹤

> [!NOTE]
> 如需追蹤事件屬性的相關資訊，請參閱[隨著追蹤事件傳送的屬性](#properties-sent-with-tracking-events)。

- **deeplink_scenario_missing** - Teams 是從深層連結啟動，但遙測/診斷不存在。
- **desktop_app_initialized** - 記錄所需的資訊，以判斷當傳統型應用程式初始化時，應用程式是否已順利啟動。
- **desktop_app_quit_exception** - 應用程式在嘗試關閉時當機。
- **desktop_blankScreenDetected** - 記錄所需的資訊，以判斷當傳統型應用程式呈現空白畫面時的錯誤。
- **desktop_blankScreenDetectedAfterRepaint** - 偵測到頁面在嘗試偵測轉譯時空白。
- **desktop_blankScreenRecoveredAfterRepaint** - 從轉譯問題復原，其中的畫面稍早未轉譯。
- **desktop_configuration_failed_to_save** - 收集需要的資訊，以判斷無法儲存桌面設定時的設定錯誤。
- **desktop_navigation_error_recovery** - 收集需要的資訊，以判斷頁面在五次嘗試之後無法載入時的桌面瀏覽錯誤。
- **desktop_previous_gpu_crashed** - 記錄所需的資訊，以判斷當桌面當機時的圖形處理單元錯誤。
- **desktop_previous_plugin_host_crashed** - 收集需要的資訊，以判斷與傳統型應用程式相關聯當機的媒體堆疊問題。
- **desktop_recovery_cleared_user_data** - 記錄應用程式當機多次，且應用程式必須清除本機快取才能復原。
- **desktop_settings_blank_on_load** - 這是應用程式設定不存在的錯誤。
- **desktop_settings_failed_to_load** - 收集需要的資訊，以判斷桌面設定無法載入的原因。
- **desktop_silent_restart** - 用戶端更新會分階段，且用戶端會在不中斷使用者的情況下更新。
- **desktop_terminated** - 記錄所需的資訊，以判斷使用者關閉傳統型應用程式時，處理程序間通訊是否已中斷連線。
- **desktop_uncaught_exception** - 未定義物件上的函數呼叫，這會導致當機或應用程式重新啟動。
- **desktop_write_storage_failed** - 記錄所需的資訊，以判斷當傳統型應用程式無法寫入儲存空間時的磁碟錯誤。
- **registration_failed** - 記錄所需的資訊，以解決增益集註冊失敗。
- **registration_success** - 記錄所需的資訊，以判斷增益集註冊是否成功。
- **security_unsupported_ipc_channel** - 不允許的處理程序間訊息為輸入。
- **sfb_running_not_connected** - 偵測到商務用 Skype 應用程式未執行。
- **sfb_not_running** - 記錄從呼叫到商務用 Skype 的「等候回應」逾時。
- **sfb_never_replied** - 追蹤與商務用 Skype 通訊時無 API 回應。
- **server_error_hit** - 追蹤來自與商務用 Skype 通訊的 ipc 管道的錯誤。
- **unexpected_sfb_ipc_disconnection** - 記錄所需的資訊，以判斷連線至服務失敗。
- **unregister_failed** - 記錄所需的資訊，以判斷取消註冊 Outlook 會議增益集中的錯誤。

## <a name="userbi-panelaction"></a>UserBI panelaction

> [!NOTE]
> 如需 UserBI panelaction 事件屬性的詳細資訊，請參閱[隨著 UserBI panelaction 事件傳送的屬性](#properties-sent-with-userbi-panelaction-events)。

- **inlinereply** - 記錄使用者是否已從通知回覆的資訊。
- **toastclick** - 記錄使用者按一下以瀏覽至快顯通知的訊息項目，以監視服務 SLA，以及載入對快顯通知的適當回應。
- **toastdismiss** - 記錄所需的資訊，以判斷當使用者關閉快顯通知的轉譯時的錯誤和延遲。

- **toast_skip** - 記錄所需的資訊，以避免傳輸延遲的快顯通知。
- **toasttimeout** - 記錄所需的資訊，以判斷當快顯通知的轉譯逾時時的錯誤和延遲。

### <a name="userbi-panelview"></a>UserBI panelview

> [!NOTE]
> 如需 UserBI panelview 事件屬性的詳細資訊，請參閱[隨著 UserBI panelview 事件傳送的屬性](#properties-sent-with-userbi-panelview-events)。

- **toastshow** - 記錄所需的資訊，以判斷是否已轉譯快顯。

## <a name="property-lists"></a>屬性清單

### <a name="properties-sent-with-all-events"></a>隨著所有事件傳送的屬性

| 屬性名稱                              | 描述                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | 事件產生時間                                              |
| EventInfo_Name                             | 事件名稱 - 用來區分事件類型             |
| EventInfo_BaseType/name                    | 事件類型 - 用來區分事件中的事件類型 |
| EventInfo_Sequence                         | 事件順序                                              |
| userAgent                                  | 瀏覽器代理程式字串                                               |
| userpdclevel                               | 使用者的隱私權資料控制設定                           |
| eventpdclevel                              | 事件的隱私權資料控制分類層級             |
| AppInfo_Language                           | 應用程式語言                                                       |
| clientType/AppInfo_ClientType              | 執行應用程式所在的用戶端類型                               |
| environment/AppInfo_Environment            | 處理使用者要求的工程環境               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | 應用程式的版本                               |
| buildtime                                  | 在工程系統中建立應用程式的時間戳記            |
| osversion/DeviceInfo_OsVersion             | 作業系統版本                                                         |
| AppInfo_ProcessArchitecture                | 系統架構 (32 位元/64 位元)                                  |
| preferredLocales                           | 使用者慣用的地區設定                                      |
| locale/AppInfo_Locale                      | 應用程式地區設定                                                         |
| os/DeviceInfo_OsName                       | 作業系統名稱                                                            |
| UserInfo_Language                          | 選取的使用者語言                                             |
| UserInfo_Id                                | 使用者識別碼                                                            |
| UserInfo_TenantId/TenantId                 | 租用戶識別碼                                                          |
| ring/UserInfo_Ring                         | 可協助以分階段方式提供應用程式的概念          |
| region                                     | 處理使用者要求的資料中心區域                       |
| UserInfo_ConfigIds/UserInfo_Etag           | 可協助識別不同實驗/推出中使用者的識別碼     |
| DeviceInfo_BrowserName                     | 瀏覽器名稱                                                       |
| DeviceInfo_BrowserVersion                  | 瀏覽器版本                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | 可協助識別裝置的識別碼                                  |
| totalMemory                                | 裝置的硬體記憶體                                      |
| cores                                      | 裝置的硬體核心                                       |
| cpuspeed                                   | 裝置的硬體 CPU 速度                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | 裝置的 CPU 架構                                     |
| UserRole                                   | 協助識別租用戶中的使用者角色                               |
| DeviceInfo_WindowsMode                     | 協助識別 Windows 安全性模式                               |
| desktopSession/Session_Id                  | 協助識別工作階段                                           |
| dbOpen                                     | 擷取本機資料庫的狀態                               |
| UserInfo_Upn                               | 使用者識別碼的單面雜湊                                  |

### <a name="properties-sent-with-logging-events"></a>隨著記錄事件傳送的屬性

| 屬性名稱         | 描述                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | 擷取關於記錄的詳細訊息                          |

### <a name="properties-sent-with-scenario-events"></a>隨著案例事件傳送的屬性

| 屬性名稱                     | 描述                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | 案例的狀態                                                               |
| Scenario_Step                     | 案例中的步驟                                                                 |
| sequence                          | 案例的序號                                                    |
| delta                             | 在案例中完成不同步驟所需的時間                               |
| elapsed                           | 自案例啟動以來的時間                                                    |
| scenario                          | 唯一地識別案例                                                       |
| Scenario_Name                     | 案例的名稱                                                               |
| errorInfo                         | 案例期間可能已發生錯誤的相關資訊                       |
| session                           | 唯一工作階段識別碼                                                                  |
| freeMemory                        | 擷取提供的可用記憶體                                                     |
| processMemory                     | 擷取處理程序記憶體                                                            |
| scenarioDelta                     | 擷取 2 個案例步驟之間的時間差異                                   |
| Session_DesktopId                 | 唯一工作階段識別碼                                                                  |
| machineLocked                     | 擷取電腦是否已鎖定                                          |
| windowIsVisible                   | 擷取應用程式視窗是否可見而可供使用                                      |
| appStates/webAppStates            | 記錄應用程式已進行的應用程式狀態清單。 這可協助您進行當機調查，因為我們可以查看應用程式所處的狀態 |
| crashDesktopSession               | 擷取當機工作階段的識別碼                                                 |
| appRuntime                        | 擷取應用程式的執行時間                                                        |
| diagnosticEvents                  | 應用程式當機前的最後 50 個網頁應用程式診斷事件                                 |
| activities                        | 在當機之前發生的最後 50 個使用者案例名稱                            |
| crashSession                      | 擷取當機工作階段的識別碼                                                 |
| crashId                           | 擷取當機工作階段的識別碼                                                 |
| isPreviousLifecycleValid          | 先前的應用程式是否已完全初始化和成功終止             |
| isSettingValid                    | preauth 設定是否有效                                                 |
| rollbackReason                    | 復原應用程式的原因                                            |
| deeplinkType                      | 深層連結的類型                                                               |
| watchdogCrash                     | 應用程式是否由於懸置而當機                                                    |
| protocols                         | 用來啟動應用程式的通訊協定                                                    |
| electronBuild                     | electron 應用程式的組建版本                                                      |
| distribution                      |  Teams 是透過 exe 或 msi 或 dmg 或 pkg 等安裝                    |
| updateTimeOfDay                   | 更新應用程式的時間                                                           |
| launchPath                        | Teams 是否已安裝在 %LOCALAPPDATA%, %PROGRAMFILES%，或其他位置   |
| loggedIn                          | 使用者是否已登入                                                          |
| envType/complianceEnvironmentType | 商業雲端或私人 (例如 DoD、GCC-High 等)                              |
| cpuusage                          | CPU 使用量                                                                          |
| installationSource                | 使用者具有的安裝類型                                                      |
| adalVersion                       | 驗證程式庫的版本                                                        |
| asyncStart                        | 應用程式使用同步或非同步啟動                                 |
| attempts                          | 在顯示封鎖畫面之前，針對使用者進行的線上檢查嘗試次數 |

### <a name="properties-sent-with-tracking-events"></a>隨著追蹤事件傳送的屬性

| 屬性名稱                      | 描述                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | 擷取追蹤事件的名稱                                              |
| numVisibleNotifications            | 可見的應用程式通知數量                                      |
| giphyEnabled                       | Giphy 服務是否已啟用                                                |
| error                              | 擷取與追蹤事件相關的錯誤詳細資料                             |
| method                             | 通訊協定方法 GET 或 POST                                                      |
| channel                            | 擷取應用程式內的處理程序間通訊通道                      |
| windowTitle                        | 與事件相關聯的顯示視窗類型                                     |
| message                            | 錯誤訊息的類型                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | 擷取工作階段偵錯目的的唯一識別碼 |
| responseCode                       | 擷取服務呼叫的回應碼                                      |
| errorUrl                           | 無法載入的 URL                                                      |
| errorCode                          | 擷取錯誤碼                                                              |
| ssoEventData                       | 驗證狀況和狀態                                                  |
| correlationId                      | 識別碼以偵錯目的，將事件與服務端關聯                      |
| errorDescription                   | 擷取錯誤碼的描述                                            |
| source                             | 用來取得 Teams 應用程式和安裝 Teams 的來源套件類型的方法       |
| windowIsDestroyed                  | 事件期間應用程式視窗的 True/False 狀態                             |
| windowIsFocused                    | 事件期間應用程式視窗的 True/False 狀態                             |
| windowIsVisible                    | 事件發生時，應用程式是否可見                                  |
| windowIsMinimized                  | 事件期間應用程式視窗的 True/False 狀態                             |
| windowIsMaximized                  | 事件期間應用程式視窗的 True/False 狀態                             |
| windowIsFullscreen                 | 事件期間應用程式視窗的 True/False 狀態                             |
| distSrc                            | 擷取登陸應用程式的使用者的發佈來源                    |
| retries                            | 嘗試連線到端點時的重試次數                            |
| uses_slimcore                      | 如果 Web 呼叫使用 slimcore，則為 True 或 False                                      |
| persistCookieExpiresIn             | Web 應用程式 Cookie 有效性的剩餘時間                             |
| tenantName                         | 應用程式使用者的租用戶名稱                                       |
| appStartReason                     | 應用程式工作階段的啟動方式，例如使用者初始化、更新之後等 |
| machineLocked                      | 在事件期間電腦是否遭鎖定或未鎖定                        |
| data                               | 擷取技術資料以進行案例調查                               |
| appRuntime                         | 擷取應用程式的執行時間                                                      |
| activities                         | 在當機之前發生的最後 50 個使用者案例名稱                          |
| timeSinceActivity                  | 自使用者上次活動以來的時間                                                    |
| appStates                          | 記錄傳統型應用程式經過的應用程式狀態清單，可協助您進行當機調查，因為它會顯示傳統型應用程式所處的狀態 |
| timeSinceAppState                  | 自應用程式狀態變更以來的時間                                                 |
| webAppStates                       | 記錄 Web 用戶端經過的應用程式狀態清單，可協助您進行當機調查，因為它會顯示 Web 用戶端應用程式所處的狀態 |
| timeSinceWebAppState               | 自 Web 應用程式狀態變更以來的時間                                             |
| diagnosticEvents                   | 應用程式當機前的最後 50 個網頁應用程式診斷事件                               |
| timeSinceLastDiagnosticEvent       | 自最後一次診斷事件傳送以來的時間                                            |
| timeSinceSecondLastDiagnosticEvent | 自最後兩次診斷事件傳送以來的時間                                     |
| appInitialized                     | Web 應用程式是否已啟動                                               |
| targetVersion                      | 應用程式將更新的目標版本                                    |
| port                               | 網際網路訊息連接埠號碼                                                     |
| originalUrl                        | 轉譯的頁面的原始位置                                         |
| deeplinkId                         | 目的地類型 Teams 連結的 GUID                                          |
| appSessionEnd                      | 事件是否在應用程式工作階段結束時發生                             |
| eventData                          | 擷取電腦狀態和應用程式設定，以發生問題時協助進行偵錯        |
| deeplinkType                       | 深層連結類型 (聊天、會議、頻道)                                    |
| previousUpdateUrl                  | 應用程式上次擷取其更新的來源位置                        |
| previousUpdateVersion              | 應用程式上次更新的版本                                          |
| previousUpdateTime                 | 應用程式二進位檔案上次更新的時間                                      |
| protocol                           | 連結的處理常式類型，例如檔案或影像                                     |
| files                              | 與事件相關聯的檔案類型，例如應用程式快取或 GPU 快取    |
| Perf_WorkingSetSizeKB              | 記憶體快取大小                                                             |
| isTimeboxingWebAppInitialize       | 應用程式是否在時間方塊計數器用完之前初始化                          |
| isExp                              | 使用中的應用程式版本是否為試驗的一部分                          |
| deviceType                         | 擷取裝置的類型                                                      |
| sanitizedErr                       | 擷取錯誤資訊處理過的版本                              |
| rigelVersion                       | 擷取 rigel 裝置的版本                                                 |
| DeviceInfo_OsSku                   | 擷取作業系統 SKU 資訊                                                      |
| isLoggedOut                        | 擷取使用者是否已登出                                               |
| complianceEnvironmentType          | 商業雲端或私人 (例如 DoD、GCC-High 等)                           |
| restartTimes                       | 先前重新啟動的確切次數                                                 |
| Skype_ResultCode                   | 擷取 Skype 和 Teams 之間交互操作通訊的結果                 |
| cpumodel                           | 擷取 CPU 的型號                                                            |
| isSlimCoreRunningOutproc           | Slimcore 元件是否在其自己的處理程序中執行                         |
| isSlimCoreStartedAsync             | 內部音訊/視訊 (A/V) 堆疊的啟動類型                               |
| networkState                       | 擷取網路的狀態                                                    |
| desktopBuildAge                    | 應用程式組建在事件時間的時間長度                                   |
| vdiMode                            | 擷取應用程式是否在 VDI 模式中執行                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>隨著 UserBI panelview 事件傳送的屬性

| 屬性           | 描述                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | 傳送給使用者的面板的 URI                   |
| Panel_Type         | 使用者存取的面板類型                          |
| Team_Id            | 使用者執行動作所在的小組識別碼 |
| Thread_Id          | 使用者存取的執行緒識別碼               |
| Panel_PreviousUri  | 上一個面板的 URI                                |
| Panel_Region       | 面板代管在應用程式中的所在地區             |
| Panel_LaunchMethod | 啟動面板的方法              |
| Panel_PreviousType | 上一個面板的類型                               |
| Thread_Type        | 使用者存取的執行緒類型                          |
| Panel_LaunchSource | 所啟動面板的來源資訊        |
| Tab_Type           | 使用者存取的標籤類型                         |
| Team_Type          | 使用者存取的小組類型                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>隨著 UserBI panelaction 事件傳送的屬性

| 屬性名稱         | 描述                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | 透過使用者動作存取之資源的 URI                  |
| Panel_Uri             | 傳送給使用者的面板的 URI                             |
| Action_Gesture        | 使用者在應用程式上執行的手勢類型                       |
| Action_ScenarioType   | 與功能的商務度量相關的功能群組       |
| Panel_Type            | 使用者存取的面板類型                                    |
| Action_Outcome        | 使用者執行的動作結果                            |
| Team_Id               | 使用者執行動作所在的小組識別碼           |
| Module_Type           | 主控使用者動作所在的模組類型                        |
| Module_Name           | 主控使用者動作所在的模組名稱                        |
| Module_Summary        | 主控使用者動作的模組摘要                       |
| Thread_Id             | 使用者存取的執行緒識別碼                         |
| Panel_PreviousUri     | 上一個面板的 URI                                          |
| Panel_Region          | 面板代管在應用程式中的所在地區                       |
| Panel_LaunchMethod    | 啟動面板的方法                        |
| Panel_PreviousType    | 上一個面板的類型                                         |
| Thread_Type           | 使用者存取的執行緒類型                                    |
| Module_State          | 使用者存取的模組狀態                               |
| Action_Scenario       | 與商務度量相關的功能群組內的功能 |
| Panel_LaunchSource    | 所啟動面板的來源資訊                  |
| Tab_Type              | 使用者存取的標籤類型                                   |
| Team_Type             | 使用者存取的小組類型                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>隨著 Outlook 增益集事件傳送的屬性

| 屬性名稱                   | 描述                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | 增益集會將帳戶與 Teams 帳戶比較，查看是否允許建立，如果比較失敗，則傳送此事件。 |
| AccountComparisonSuccessful     | 增益集會將帳戶與 Teams 帳戶比較，查看是否允許建立，如果比較成功，則傳送此事件。 |
| AdalVersion                     | 使用的驗證程式庫版本                               |
| AddinBitness                    | 增益集的版本                                                         |
| AddinLanguage                   | 使用的增益集字串語言                                     |
| AggregatorSetupCompletedTime    | 增益集載入器的設定時間                                              |
| AppDomainCreatedTime            | 增益集載入器初始化應用程式網域的時間                            |
| AppointmentDisplayTime          | 在會議建立期間顯示約會項目的時間 |
| AuthenticationCompletedTime     | 為指定要求提供驗證的時間            |
| ConnectionMode                  | 指出使用者的主要 Exchange 帳戶的連線模式     |
| ConnectionStartedTime           | Outlook 呼叫 OnConnection 的時間                                     |
| ErrorDetails                    | 擷取錯誤的詳細資料                                            |
| ErrorName                       | 擷取錯誤的名稱                                               |
| ExchangeVersion                 | 擷取 Exchange 的版本                                             |
| IsSmtpFormatError               | SMTP 位址中發生錯誤                                                    |
| IsTeamsRunning                  | 擷取是否有 Teams 程序執行中                             |
| IsTeamsUserLoggedOut            | 擷取使用者是否已登出 Teams                              |
| LanguageSetupCompletedTime      | 語言設定完成的時間                               |
| ManagedConnectTime              | 受管理增益集收到連線回撥的時間               |
| ManagedOnStartupTime            | 受管理增益集開始啟動的時間                                    |
| MTFetchCompleted                | MT 會議選項要求完成的時間                        |
| NetFrameworkVersion             | 使用的 .NET Framework                                                      |
| NetworkAvailable                | 網路可供使用                                                     |
| OperationStartTime              |  不同作業開始的時間                                  |
| OsBitness                       | 作業系統的位元                                                            |
| OutlookLanguage                 | 擷取 Outlook 應用程式的語言                                     |
| OutlookVersion                  | 擷取 Outlook 應用程式的版本                                          |
| OwnerResolutionTime             | 解決會議擁有者的時間                                        |
| ParseResponseCompletedTime      | 剖析回應完成的時間                                  |
| RecipientResolutionError        | 解決收件者的錯誤詳細資料                                 |
| RecipientsResolutionTime        | 解決所有收件者的總時間                                     |
| RehydrateCompletedTime          | 從 Outlook 讀取屬性的時間                               |
| SaveToOutlookCompletedTime      | 將屬性儲存至 Outlook 的時間                                |
| ServiceRequestStartTime         | 服務要求的開始時間                                        |
| ServiceResponseReceiveTime      | 來自服務的回應時間                                        |
| SettingsInitializeCompletedTime | 初始化設定的時間                                           |
| SetupLoggingCompletedTime       | 設定記錄的時間                                             |
| ShutdownBeginTime               | 增益集關閉的開始時間                                       |
| ShutdownCompletedTime           | 關閉的完成時間                                             |
| StartupBeginTime                | 增益集啟動的開始時間                                        |
| StartupCompletedTime            | 啟動的完成時間                                              |
| TeamsDeployment                 | 部署 Teams 用戶端 (開發、生產)                                   |
| TeamsRing                       | 登入 Teams 用戶端的目前使用者的通道                            |
| TeamsVersion                    | 擷取 Teams 應用程式的版本                                            |
| TelemetrySetupCompletedTime     | 遙測設定完成的時間                                   |
| UpnMismatch                     | Outlook 與 Teams 之間是否有 UPN 不符                  |
| UserDomain                      | 使用者的網域                                                       |
| ViewUpdatedTime                 | 更新檢視的時間                                           |
