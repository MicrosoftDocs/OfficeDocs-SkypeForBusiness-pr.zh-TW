---
title: 商務用 Skype Server 統計資料的規劃
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
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：請閱讀本主題，瞭解商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816232"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>商務用 Skype Server 統計資料的規劃

**摘要：** 若要瞭解商務用 Skype Server 的統計資料管理員，請閱讀本主題。

 商務用 Skype Server 的 [統計資料管理員] 是一種強大的工具，可讓您即時查看商務用 Skype Server 健康情況和效能資料。 您可以每隔幾秒在數百個伺服器上輪詢效能資料，並立即在統計資料管理器網站上查看結果。

您可以使用 [統計資料管理器] 來找出持續的效能問題、查看已規劃變更對您的環境的結果、追蹤中斷的解決方式等等。 在該框中，統計管理員是使用金鑰健康情況指標（KHI）閾值來設定，而且可以根據您的部署的獨特需求加以自訂。

您可以在內部部署中部署統計資料管理器，其中單一伺服器會託管所有伺服器端統計資料管理器元件。 如需有關部署統計管理員的詳細資訊，請參閱[部署商務用 Skype Server 的統計資料管理器](deploy.md)。 如果您已有現有的統計資料管理員部署，但您尚未升級至發行2.0，請參閱[版本2.0 的新增功能](plan.md#BKMK_WhatsNew)和[商務用 Skype Server 的 [升級統計資料管理員]](upgrade.md)。

本主題包含下列各節：

- [功能與功能](plan.md#BKMK_Features)

- [版本2.0 的新功能](plan.md#BKMK_WhatsNew)

- [元件](plan.md#BKMK_Components)

- [內部部署](plan.md#BKMK_DeploymentOptions)

- [需求](plan.md#BKMK_Requirements)

- [安全性考慮](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>功能與功能
<a name="BKMK_Features"> </a>

[統計資料管理器] 可讓您：

- 即時查看所有伺服器的原始資料。 （以極高的速率取樣資料，並以少於一秒的時間傳送到網站。）

- 針對特定角色來查看匯總的資料;例如，[前端伺服器]、[中繼伺服器]、[Edge 伺服器] 等等。

- 向下切入以查看特定網站的資料、網站內的特定 pool，以及池中的特定伺服器。

- 建立自訂圖表，以便預設顯示所選的計數器。

- 在 X 軸與 y 軸上，或只在 X 軸上縮放和平移。

- 使用日期範圍或時間點來篩選資料。

- 根據已建立的金鑰健康情況指示（KHIs）來查看伺服器效能。 KHIs 代表已定義正常範圍的效能計數器集合。

- 查看每個計數器的詳細度量單位。

- 比較多個人口或伺服器上的資料。

- 查看潛在的計數器報告，找出未向儀表板服務報告目前資料的代理程式。

- 將圖表資料的特定實例儲存至檔案。

- 即時查看 KHIs，包括更新。 如果已啟用 [歷程記錄] 視圖，就只會顯示新的失敗。

  - 一次查看所有 KHIs

  - 依伺服器查看 KHIs （橫向視圖）

  - 查看 KHI 定義

## <a name="whats-new-in-release-20"></a>版本2.0 的新功能
<a name="BKMK_WhatsNew"> </a>

下列說明版本2.0 的新增功能。 如果您已有部署的統計資料管理員，但尚未升級，請參閱[商務用 Skype Server 的升級統計資料管理器](upgrade.md)。

- 已針對 Edge 媒體、結構健康情況、池容錯移轉及註冊案例新增案例視圖。

- 已為 SQL server 新增許多新的計數器、更多商務用 Skype 使用量計數器等。

- [統計資料管理員] 代理程式的 [觀察程式節點整合]-如果該代理程式已安裝在監視者節點上，它會將綜合交易處理統計資料包告為計數器傳回統計資料管理員。

- 許多可靠性和效能的改進。

若要確認您執行的統計資料管理器網站版本是否正常：

- 在檔案資源管理器中，開啟（預設目錄） C:\Program Files\Skype for Business Server StatsMan WebSite\bin

- 以滑鼠右鍵按一下 [StatsManHubWebSite] 並查看其屬性

- 產品版本將會顯示在描述詳細資料中。

## <a name="components"></a>元件
<a name="BKMK_Components"> </a>

[統計資料管理器] 由下列元件組成：

- **代理程式.** 在每個受監視的伺服器上執行的輕型代理程式。 代理程式允許可設定的高速率輪詢與本機集合的效能。

- **接聽程式.** 從所有代理程式接收資料的伺服器端 API，以及跨人口匯總資料。

- **中樞.** 充當系統的用戶端 API，在 web 伺服器上執行，並提供透過網站連線的用戶端即時資料更新。 （中樞會自動安裝為網站 msi 的一部分）。

- **Web.** 可將系統中所有可用功能集中在一起的使用者介面。

此外，統計資料管理員還需要**Redis**，也就是用來進行記憶體中快取的開放式資料結構伺服器。 如需有關下載 Redis 的詳細資訊，請參閱[部署統計資料管理器](deploy.md#BKMK_Deploy)。

## <a name="on-premises-deployment"></a>內部部署
<a name="BKMK_DeploymentOptions"> </a>

在內部部署的部署中，單一伺服器會託管所有伺服器端統計資料管理員元件。

下圖顯示內部部署，其中統計管理員網站、中樞、偵聽程式及 Redis 緩存系統都是在單一電腦上託管。 [統計資料管理員] 正在監視三個商務用 Skype 伺服器，每一個都有一個代理程式將資料傳送到監聽器。 使用者連線到單一網站，以查看統計資料管理員匯總的所有資料：

![統計管理員內部部署](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>需求
<a name="BKMK_Requirements"> </a>

在部署統計資料管理器之前，您必須先考慮下列軟體、網路和硬體需求。

### <a name="software-requirements"></a>軟體需求

- Windows Server 2016 和2019

- IIS （自動安裝）

- Redis

- Statistics 管理員服務（自動安裝）

- PSExec-需要執行遠端代理程式部署

- .NET 4.5 （隨附于 2012 R2）-代理程式和伺服器端元件所需
- 下載[商務用 Skype Server、即時統計資料管理器（64位）](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>網路需求


|**主機伺服器**|**代理程式**|**接聽程式**|
|:-----|:-----|:-----|
|最低十億位元全雙工網路。  <br/> |輸出 TCP 埠8443（可自訂埠號碼）與監聽器通訊。  <br/> |偵聽程式埠在所有伺服器上都必須是相同的。  <br/> |
|輸入 TCP 埠80或443開啟以託管網站。  <br/> |||
|入站 TCP 埠8443（可自訂埠號碼），可供代理程式與其通訊。  <br/> |||

在安裝期間，系統會自動建立監聽器和網站的防火牆埠。 針對代理程式，安裝會假設預設允許出站 TCP 連線。

### <a name="hardware-requirements"></a>硬體需求

在內部部署中，單一伺服器會將所有伺服器端統計資料管理器元件組成一個主機，且有 16 GB RAM 和4個 CPU 的伺服器應該能夠支援每秒平均150樣本。 若要判斷您可以支援多少計數器/代理程式，請使用下列計算：

100 server \*80 每\*秒從每個代理程式/60 秒的每分鐘樣本1樣本 = 大約每秒133樣本。

## <a name="security-considerations"></a>安全性考慮
<a name="BKMK_Security"> </a>

伺服器之間的所有流量都會經過加密。

- 加密的 HTTPS 流量會透過埠8443（預設）傳送到偵聽程式伺服器。

- Agent 將在伺服器上驗證 SSL 指紋，以確保監聽器伺服器為預期的收件者。 請注意，代理程式會使用證書指紋驗證（而不是鏈式驗證）。 因為可以使用自我簽署的憑證，所以它不會進行完整的憑證驗證。

- 在符合代理程式的真實情況下，系統會透過監聽器驗證該代理程式來出示該密碼。

- 代理程式會開始以連線到監聽器的連線來傳送效能資料。

## <a name="for-more-information"></a>如需詳細資訊
<a name="BKMK_Security"> </a>

如需詳細資訊，請參閱下列內容：

- [部署商務用 Skype Server 統計資料](deploy.md)

- [升級商務用 Skype Server 統計資料](upgrade.md)

- [疑難排解商務用 Skype Server 統計資料](troubleshoot.md)
