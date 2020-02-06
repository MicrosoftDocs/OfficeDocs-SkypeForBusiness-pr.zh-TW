---
title: 疑難排解商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：請閱讀本主題，以針對商務用 Skype Server 的統計管理員部署進行疑難排解。
ms.openlocfilehash: a787297b25b983303e65f398dfb7b275ae044944
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816212"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>疑難排解商務用 Skype Server 統計資料
 
**摘要：** 閱讀本主題以針對商務用 Skype Server 的統計管理員部署進行疑難排解。
  
本主題描述如何透過描述您在應用程式事件日誌中看到的事件，以及您可以採取以修正事件的適當動作來疑難排解統計資料管理員部署。 本主題包含下列各節：
  
- [代理程式事件](troubleshoot.md#BKMK_Agent)
    
- [偵聽程式事件](troubleshoot.md#BKMK_Listener)
    
- [網站問題](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>代理程式事件
<a name="BKMK_Agent"> </a>

- **1000** -無法設定處理器 Limiter （工作物件）-未知原因
    
- **1001** -進程不允許程式限制（可能是工作物件內）
    
    Agent 會在 Windows 工作物件內執行，以自動限制其記憶體需求量。 如果代理程式無法啟動，且事件記錄中存在這些事件專案，則無法在伺服器上將工作物件具現化。 若要解決此問題，您可以變更 config 檔案中的值來移除上限記憶體限制：
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜尋 "MaxProcessMemoryMB"，然後將值變更為 "0"，如下所示：
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果進行這項變更，則代理程式通常仍會\<佔用 100 MB 的記憶體，但在預設情況下，它不會被強制限制為 300 mb。 如果進行這項變更，我們建議您密切監視記憶體使用量，以確保代理程式不會在其主機電腦上佔用大量記憶體。 
  
- **2000** -用戶端初始化失敗
    
- **2001**-在任何來源 IP 上無法與服務建立連線
    
    如果代理程式無法連線至監聽器電腦，請檢查下列專案：
    
1. 確定偵聽程式服務正在監聽程式電腦上執行。 如果不是，請確定 Redis 正在該伺服器上執行，然後重新開機監聽器服務。
    
    檢查偵聽程式電腦上的統計資料管理員事件記錄，以確保統計資料管理員攔截器服務本身沒有任何問題。
    
2. 使用連接工具（例如 telnet）來驗證從代理程式電腦到正確埠上的監聽器的連線性。
    
    如果不是，請確定已針對監聽器電腦所連接的網路類型（私人/公用/網域），在監聽器電腦上啟用 [接收] 防火牆規則。 如果監聽器電腦沒有加入網域，網路可能會列為公用，而且在該情況下，安裝了 [統計資料管理器] 的防火牆規則預設不會套用。
    
- **4000** -從偵聽程式下載伺服器資訊失敗（不明原因）
    
  - **4001** -在偵聽程式拓撲中找不到伺服器
    
    如果伺服器已成功連線到偵聽程式，但未將伺服器新增到攔截器快取的拓撲中，就會發生此錯誤。 解析度選項：
    
  - 請確定您已按照匯入拓撲的指示進行。 請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。 
    
  - 如果該代理位於拓撲中未列出的伺服器上（例如，SQL AlwaysOn 群集中的節點），您將需要按照匯[入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增該代理程式。
    
  - **4002** -不正確監聽器密碼
    
    代理程式嘗試使用的加密密碼與監聽器本身的服務密碼不相符。 卸載該代理程式，然後使用正確的服務密碼重新安裝。
    
  - **4003** -憑證指紋不相符
    
    在安裝時間提供給 Agent 的憑證指紋與監聽器目前使用的憑證上的指紋不相符，因此連線將遭到拒絕。 卸載該代理程式，然後使用正確的憑證指紋重新安裝。
    
  - **4004** -不正確回應或 HttpStatusCode
    
    監聽器沒有回應預期的狀態。 
    
  - 如果連線是已設定代理的，請檢查 proxy 設定。
    
  - 檢查監聽器電腦的 StatsMan 記錄是否有其設定的問題。
    
  - **4005** -無法反序列化 XML
    
    監聽器伺服器上的伺服器資訊已損壞，或是代理程式與監聽器電腦之間可能有版本不相符的問題。 請確定版本相符，然後檢查監聽器事件記錄檔是否有問題。
    
## <a name="listener-events"></a>偵聽程式事件
<a name="BKMK_Listener"> </a>

- **10000** -啟動失敗不明原因（這些無法還原，且服務會因結果而停止/損毀）
    
  - **10001** -配置問題
    
    一般來說，當 [listener_install_location] \PerfAgentListener.exe.config 檔案已手動修改且無法由應用程式讀取時，就會發生這種情況。
    
  - **10002** -HTTP 偵聽程式初始化錯誤
    
    當在安裝期間未正確設定 URL ACL 或 SSL 憑證無效時，通常會記錄這個事件。 確定您的設定中的憑證有效。 如果是，請根據 [[部署統計資料管理器](deploy.md#BKMK_Deploy)] 中的指示來重新安裝該偵聽程式。
    
  - **10003** -Redis 失敗
    
  - **10004** -緩存基礎結構失敗
    
  - **10007** -設定（儲存在 redis 中）
    
    監聽器無法與 Redis 聯繫，或從快取中取得格式正確的資料，但無法啟動。 確認已在伺服器上啟動並正確設定 Redis 服務。
    
  - **10005** -伺服器資訊檢索/分析
    
    Redis 快取中的拓撲資訊無效。 首先，請嘗試重新開機 Redis 和偵聽程式。 如果錯誤持續出現，請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)，以重新建立拓撲資料。
    
- **10100** -Redis PING 中斷
    
  - **10101** -Redis PING 連續停機（每60秒）
    
  - **30100** -已還原 Redis PING 中斷
    
    當監聽器無法連線至 Redis 時，就會記錄這些訊息。 確保 Redis 已啟動，且可以使用偵聽程式與 Redis 之間的網路連線。
    
- **10200** -Redis 寫入中斷
    
  - **10201** -繼續 Redis 寫入停止（每隔60秒）
    
  - **30100** -已解決 Redis 寫入中斷問題
    
    當監聽器無法寫入 Redis 快取時，就會記錄這些訊息。 確保 Redis 已啟動，且可以使用偵聽程式與 Redis 之間的網路連線。
    
- **30000** -成功啟動
    
    在每次啟動監聽器時記錄。
    
- **22000** -統計資料管理器代理程式的初始化成功。
    
- **23000** -初始化 EventLogQueryManager 成功（第一次或失敗之後）
    
- **24000** -初始化 serverinfo 成功（第一次或失敗之後）
    
- **25000** -監聽器在無法開機自檢（或第一次成功張貼）後回到線上
    
- **5000** -在離線時啟動監聽器以進行資料張貼
    
- **5001** -監聽器在延長期間內仍處於離線狀態
    
    這些事件對於監視/觸發/清除問題可能很有用。
    
## <a name="website-issues"></a>網站問題
<a name="BKMK_Website"> </a>

- Chrome 中重複的登入提示-這是已在版本1.1 中解決的錯誤。 如果您在 Chrome 瀏覽器中看到重複的登入提示，請確定您已升級至最新版本的統計資料管理員。 若要確認您正在執行的網站版本：
    
  - 在檔案資源管理器中開啟（預設目錄）
    
  - 以滑鼠右鍵按一下 [StatsManHubWebSite]，並查看其屬性。
    
  - 如果在 KHI 橫向視圖或 [計數器詳細資料] 視圖中找不到電腦，請確定它是網站和池的成員。 如果不是，就不會出現在這些視圖中。 如需在拓撲中定義伺服器的網站和池的相關資訊，請參閱匯[入拓撲](deploy.md#BKMK_ImportTopology)。
    
  - 產品版本將會顯示在描述詳細資料中。
    
## <a name="for-more-information"></a>如需詳細資訊
<a name="BKMK_Website"> </a>

如需詳細資訊，請參閱下列內容：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [部署商務用 Skype Server 統計資料](deploy.md)
    
- [升級商務用 Skype Server 統計資料](upgrade.md)
