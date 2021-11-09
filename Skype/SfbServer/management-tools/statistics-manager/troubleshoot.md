---
title: 疑難排解商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：閱讀本主題，以疑難排解商務用 Skype Server 的統計資料管理員部署。
ms.openlocfilehash: 6e6edefe8d6070a917f817b3b6d79bf35ff36599
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857340"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>疑難排解商務用 Skype Server 統計資料
 
**摘要：** 閱讀此主題以疑難排解商務用 Skype Server 的統計資料管理員部署。
  
本主題說明如何透過描述您在應用程式事件記錄檔中看到的事件來疑難排解您的統計資料管理員部署，以及您可能採取的適當動作以修正事件。 本主題包含下列各節：
  
- [代理程式事件](troubleshoot.md#BKMK_Agent)
    
- [攔截器事件](troubleshoot.md#BKMK_Listener)
    
- [網站問題](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>代理程式事件
<a name="BKMK_Agent"> </a>

- **1000** -無法安裝處理器 Limiter (工作物件) -未知原因
    
- **1001** -不允許程式 (可能在工作物件中的處理常式限制) 
    
    代理程式會在 Windows 工作物件內執行，以自動限制其記憶體需求量。 如果代理程式不會啟動，且事件記錄檔中有這些事件專案，則無法在伺服器上具現化此工作物件。 若要解決此問題，您可以變更 config 檔案中的值來移除上限記憶體限制：
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜尋 "MaxProcessMemoryMB"，並將值變更為 "0"，如下所示：
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果進行此變更，則代理程式通常仍會消耗 \< 100 MB 的記憶體，但是不會因為預設，強制限制為 300 mb。 如果進行此變更，我們建議您密切監控記憶體使用量，以確保代理程式不會在其主機電腦上消耗大量的記憶體。 
  
- **2000** -用戶端初始化失敗
    
- **2001**—沒有任何來源 IP 上的服務連接可進行
    
    若代理程式無法連線至監聽器電腦，請檢查下列各項：
    
    1. 確定監聽器電腦上的監聽器服務正在執行中。 如果不是，請確定 Redis 在該伺服器上執行，然後重新開機監聽器服務。
        
        檢查監聽器電腦上的統計資料管理員事件記錄，以確保統計資料管理員偵聽程式服務本身沒有任何問題。
        
    2. 使用連通性工具（例如 telnet），以驗證代理程式電腦與正確埠上的監聽器的連線能力。
        
        如果不是，請確定已在監聽器電腦上為監聽器電腦連線的網路類型啟用內送防火牆規則，以 (私/public/網域) 。 如果監聽器電腦未加入網域，網路可能會列為 public，而且在此情況下，將不會預設會套用隨統計資料管理員安裝的防火牆規則。
    
- **4000** -從監聽器下載伺服器資訊失敗 (未知原因) 
    
  - **4001** -在監聽器拓撲中找不到伺服器
    
    如果伺服器順利連接至監聽器，但未將伺服器新增至攔截器快取中的拓撲，便會發生此錯誤。 解析度選項：
    
  - 請確認您已遵循匯入拓撲的指示。 請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。 
    
  - 如果代理程式位於拓撲中未列出的伺服器上 (例如，SQL AlwaysOn 叢集) 中的節點，您必須遵循匯[入拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。
    
  - **4002** -不正確監聽器密碼
    
    代理程式嘗試使用的加密密碼與監聽器本身的服務密碼不相符。 卸載代理程式，然後使用正確的服務密碼重新安裝。
    
  - **4003** -憑證指紋不符
    
    在安裝時間提供給代理程式的憑證指紋與偵聽程式目前使用的憑證上的指紋不相符，因此會拒絕連線。 卸載代理程式，然後使用正確的憑證指紋重新安裝。
    
  - **4004** -回應或 HttpStatusCode 無效
    
    攔截器未以預期的狀態回應。 
    
  - 如果連線已代理，請檢查 proxy 設定。
    
  - 檢查監聽器電腦的 StatsMan 記錄是否有其設定問題。
    
  - **4005** -無法反序列化 XML
    
    監聽器伺服器上的伺服器資訊已損毀，或代理程式與監聽器電腦之間的版本不相符。 確定版本相符，並檢查攔截器事件記錄檔是否有問題。
    
## <a name="listener-events"></a>攔截器事件
<a name="BKMK_Listener"> </a>

- **10000** —啟動失敗未知原因 (這些是無法復原，而且此服務會因結果而停止/損毀) 
    
  - **10001** —設定問題
    
    一般來說，當 [listener_install_location] \PerfAgentListener.exe.config 檔案已手動修改，且應用程式無法讀取時，就會發生這種情況。
    
  - **10002** -HTTP 攔截器初始化錯誤
    
    當安裝時 URL ACL 未正確設定，或 SSL 憑證無效時，通常會記錄此事件。 確定您的設定中的憑證是有效的。 如果是，請根據 [部署統計資料管理員](deploy.md#BKMK_Deploy)中的指示重新安裝攔截器。
    
  - **10003** — Redis 失敗
    
  - **10004** —快取基礎結構失敗
    
  - **10007** — redis 中儲存的設定 () 
    
    攔截器無法連絡 Redis，或從快取中取得格式正確的資料，而且無法啟動。 確定伺服器上已啟動並正確設定 Redis 服務。
    
  - **10005** --伺服器資訊檢索/剖析
    
    Redis 快取中的拓撲資訊無效。 首先，嘗試重新開機 Redis 和監聽器。 如果錯誤仍然存在，請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology) 以重新建立拓撲資料。
    
- **10100** — Redis PING 中斷
    
  - **10101** --Redis PING 連續中斷 (每60秒) 
    
  - **30100** —還原 Redis PING 中斷
    
    當監聽器無法連線至 Redis 時，將會記錄這些事件。 確定已啟動 Redis，且接聽程式和 Redis 之間的網路連線可供使用。
    
- **10200** — Redis 寫入中斷
    
  - **10201** （Redis 寫入中斷 (每60秒繼續) 
    
  - **30100** — Redis 寫入中斷已解決
    
    當監聽器無法寫入 Redis 快取時，將會記錄這些事件。 確定已啟動 Redis，且接聽程式和 Redis 之間的網路連線可供使用。
    
- **30000** -成功啟動
    
    在每次啟動監聽器時進行記錄。
    
- **22000** —統計資料管理員代理程式的初始化成功。
    
- **23000** —初始化 EventLogQueryManager 成功 (第一次或失敗之後) 
    
- **24000** —初始化 serverinfo 成功 (第一次或失敗之後) 
    
- **25000** -當您無法開機自檢 (或初次成功開機自檢後，監聽器會傳回線上) 
    
- **5000** —從離線的監聽器開始發佈資料
    
- **5001** -攔截器在長期間內仍保持離線狀態
    
    這些事件對於監控/警示/清除問題非常有用。
    
## <a name="website-issues"></a>網站問題
<a name="BKMK_Website"> </a>

- Chrome 中的重複登入提示-這是在1.1 版中已解決的錯誤。 如果您在 Chrome 瀏覽器中看到重複的登入提示，請確定您已升級至最新版本的統計資料管理員。 若要驗證您正在執行的網站版本：
    
  - 在檔案資源管理器中，開啟 (預設目錄) 
    
  - 在 StatsManHubWebSite.dll 上按一下滑鼠右鍵，然後查看其屬性。
    
  - 如果在 KHI 橫向模式或 [計數器詳細資料] 視圖中找不到電腦，請確定它是網站和集區的成員。 如果不是，則不會出現在這些視圖中。 如需在拓撲中定義伺服器的網站和集區的詳細資訊，請參閱匯 [入拓撲](deploy.md#BKMK_ImportTopology)。
    
  - 產品版本將會顯示在描述詳細資料中。
    
## <a name="for-more-information"></a>相關資訊
<a name="BKMK_Website"> </a>

如需詳細資訊，請參閱下列各主題：
  
- [商務用 Skype Server 統計資料的規劃](plan.md)
    
- [部署商務用 Skype Server 統計資料](deploy.md)
    
- [升級商務用 Skype Server 統計資料](upgrade.md)
