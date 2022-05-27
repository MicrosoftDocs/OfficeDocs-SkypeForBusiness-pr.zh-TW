---
title: 疑難排解商務用 Skype Server 統計資料
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：閱讀本主題以針對適用于 商務用 Skype Server 的統計資料管理員部署進行疑難排解。
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675275"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>疑難排解商務用 Skype Server 統計資料

**總結：** 請閱讀本主題，針對適用于 商務用 Skype Server 的統計資料管理員部署進行疑難排解。

本主題描述如何描述您可能會在應用程式事件記錄檔中看到的事件，以及您可能採取的適當動作來修正事件，以針對您的統計資料管理員部署進行疑難排解。 本主題包含下列各節：

- [代理程式事件](troubleshoot.md#BKMK_Agent)

- [接聽程式事件](troubleshoot.md#BKMK_Listener)

- [網站問題](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>代理程式事件
<a name="BKMK_Agent"> </a>

- **1000** - 無法 (Job 物件) 設定處理器限制器 — 未知的原因

- **1001** - 進程上不允許進程限制 (可能已經在 Job 物件內) 

    Agent 會在Windows Job 物件內執行，以自動限制其記憶體使用量。 如果代理程式無法啟動，而且這些事件專案存在於事件記錄檔中，則無法在伺服器上具現化 Job 物件。 若要解決此問題，可以藉由變更組態檔中的值來移除記憶體上限：

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    搜尋 「MaxProcessMemoryMB」，並將值變更為 「0」，如下所示：

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > 如果進行這項變更，代理程式通常仍會耗用 \< 100 MB 的記憶體，但不會因為預設值而強制限制為 300 MB。 如果進行這項變更，建議您密切監視記憶體使用量，以確保 Agent 不會耗用其主機電腦上的大量記憶體。

- **2000** - 用戶端初始化失敗

- **2001**- 無法連線到任何來源 IP 上的服務

  如果代理程式無法連線到接聽程式電腦，請檢查下列專案：

  1. 確定接聽程式服務正在接聽程式電腦上執行。 如果沒有，請確定 Redis 正在該伺服器上執行，然後重新開機接聽程式服務。

     檢查接聽程式電腦上的統計資料管理員事件記錄檔，以確保統計資料管理員接聽程式服務本身沒有任何問題。

  2. 使用 telnet 之類的連線工具，確認從 Agent 電腦到正確埠上接聽程式的連線能力。

     如果沒有，請確定接聽程式電腦上已針對接聽程式電腦連線到 (私人/公用/網域) 的網路類型啟用連入防火牆規則。 如果接聽程式電腦未加入網域，網路可能會列為公用，在此情況下，隨統計資料管理員一起安裝的防火牆規則預設不會套用。

- **4000** - 無法從接聽程式下載伺服器資訊 (不明原因) 

  - **4001** - 在接聽程式拓撲中找不到伺服器

    如果伺服器成功連線到接聽程式，但伺服器未新增至接聽程式快取中的拓撲，就會發生此錯誤。 解決選項：

  - 請確定您已遵循匯入拓撲的指示。 請參閱 [匯入拓撲](deploy.md#BKMK_ImportTopology)。

  - 例如，如果 Agent 位於未列在拓撲 (的伺服器上，SQL AlwaysOn 叢集中的節點) ，您必須依照匯入[拓撲](deploy.md#BKMK_ImportTopology)中的指示手動新增代理程式。

  - **4002** - 不正確接聽程式密碼

    代理程式嘗試使用的加密密碼不符合接聽程式本身的服務密碼。 卸載代理程式，並使用正確的服務密碼重新安裝。

  - **4003** - 憑證指紋不符

    安裝時提供給代理程式的憑證指紋與接聽程式目前使用的憑證指紋不符，因此會拒絕連線。 卸載代理程式，並使用正確的憑證指紋重新安裝它。

  - **4004** - 不正確回應或 HttpStatusCode

    接聽程式沒有回應預期的狀態。

  - 如果連線為 Proxy，請檢查 Proxy 組態。

  - 檢查接聽程式電腦的 StatsMan 記錄檔，以瞭解其設定問題。

  - **4005** - 無法將 XML 取消序列化

    接聽程式伺服器上的伺服器資訊已損毀，或代理程式與接聽程式電腦的版本可能不相符。 請確定版本相符，並檢查接聽程式事件記錄檔是否有問題。

## <a name="listener-events"></a>接聽程式事件
<a name="BKMK_Listener"> </a>

- **10000** - 啟動失敗 未知原因 (無法復原，且服務會因為) 

  - **10001** - 設定問題

    一般而言，當 [listener_install_location] \PerfAgentListener.exe.config檔案已手動修改且應用程式無法讀取時，就會發生這種情況。

  - **10002** - HTTP 接聽程式初始化錯誤

    當安裝期間未正確設定 URL ACL 或 SSL 憑證無效時，通常會記錄此事件。 請確定您設定中的憑證有效。 如果是，請根據部署統計資料管理員中的指示重新安裝接聽 [程式](deploy.md#BKMK_Deploy)。

  - **10003** - Redis 失敗

  - **10004** - 快取基礎結構失敗

  - **10007** - 設定 (儲存在 redis) 

    接聽程式無法連絡 Redis 或從快取擷取格式正確的資料，而且無法啟動。 請確定 Redis 服務已在伺服器上啟動並正確設定。

  - **10005** - 擷取/剖析伺服器資訊

    Redis 快取中的拓撲資訊無效。 首先，嘗試重新開機 Redis 和接聽程式。 如果錯誤持續發生，請參閱 [匯入拓撲](deploy.md#BKMK_ImportTopology) 以重新建立拓撲資料。

- **10100** - Redis PING 中斷

  - **10101** - Redis PING 每隔 60 秒 (持續中斷) 

  - **30100** - Redis PING 中斷已還原

    當接聽程式無法連線到 Redis 時，將會記錄這些專案。 確定 Redis 已啟動，且接聽程式與 Redis 之間有網路連線。

- **10200** - Redis 寫入中斷

  - **10201** - Redis 寫入中斷每隔 60 秒持續 () 

  - **30100** - Redis 寫入中斷已解決

    當接聽程式無法寫入 Redis 快取時，將會記錄這些專案。 確定 Redis 已啟動，且接聽程式與 Redis 之間有網路連線。

- **30000** - 已成功啟動

    每次啟動接聽程式時記錄。

- **22000** - 統計資料管理員代理程式的初始化成功。

- **23000** - EventLogQueryManager 的初始化 (第一次或失敗之後成功) 

- **24000** - 第一次或失敗之後 (成功初始化 serverinfo) 

- **25000** - 接聽程式在無法張貼 (或第一次成功張貼) 

- **5000** - 開始離線接聽程式以張貼資料

- **5001** - 接聽程式仍然離線一段時間

    這些事件可用於監視/警示/清除問題。

## <a name="website-issues"></a>網站問題
<a name="BKMK_Website"> </a>

- Chrome 中的重複登入提示 - 這是 1.1 版中已解決的錯誤。 如果您在 Chrome 瀏覽器中看到重複的登入提示，請確定您已升級至最新版的統計資料管理員。 若要確認您正在執行的網站版本：

  - 在 檔案總管 中，開啟預設目錄 () 

  - 以滑鼠右鍵按一下StatsManHubWebSite.dll並檢視其屬性。

  - 如果在 [KHI 橫向] 檢視或 [計數器詳細資料] 檢視中找不到電腦，請確定它是網站和集區的成員。 如果不是，則不會出現在這些檢視中。 如需在拓撲中為伺服器定義月臺和集區的相關資訊，請參閱 [匯入拓撲](deploy.md#BKMK_ImportTopology)。

  - 產品版本會顯示在描述詳細資料中。

## <a name="for-more-information"></a>相關資訊
<a name="BKMK_Website"> </a>

如需詳細資訊，請參閱下列各主題：

- [商務用 Skype Server 統計資料的規劃](plan.md)

- [部署商務用 Skype Server 統計資料](deploy.md)

- [升級商務用 Skype Server 統計資料](upgrade.md)
