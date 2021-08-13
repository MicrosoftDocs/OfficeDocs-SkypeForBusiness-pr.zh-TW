---
title: 商務用 Skype Server 統計資料的規劃
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 的統計資料管理員。
ms.openlocfilehash: 045586a1fd6c53ff1985602b20e390416142fd3dc9d3ddc3f6b9384d8d9955ec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333265"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a>商務用 Skype Server 統計資料的規劃

**摘要：** 閱讀此主題以瞭解商務用 Skype Server 的統計資料管理員。

 商務用 Skype Server 的統計資料管理員是一種強大的工具，可讓您即時查看商務用 Skype Server 狀況和效能資料。 您可以每隔幾秒輪詢每數百部伺服器上的效能資料，並在統計資料管理員網站上立即查看結果。

您可以使用 [統計資料管理員] 來找出持續效能問題、查看對環境所做的計畫變更，追蹤中斷的解決方式，以及其他更多的結果。 現成的統計資料管理員會使用重要健康情況指示器 (KHI) 閾值來設定，而且可以自訂以符合您的部署的獨特需求。

在內部部署中，您可以在單一伺服器主控所有伺服器端統計資料管理員元件的內部部署中部署統計資料管理員。 如需部署統計資料管理員的詳細資訊，請參閱[部署統計資料管理員以取得商務用 Skype Server](deploy.md)。 如果您已有統計資料管理員的現有部署，但尚未升級為版本2.0，請參閱[release 2.0 的新功能](plan.md#BKMK_WhatsNew)和[升級統計資料管理員的商務用 Skype Server](upgrade.md)。

本主題包含下列各節：

- [特性和功能](plan.md#BKMK_Features)

- [版本2.0 的新功能](plan.md#BKMK_WhatsNew)

- [元件](plan.md#BKMK_Components)

- [內部部署](plan.md#BKMK_DeploymentOptions)

- [需求](plan.md#BKMK_Requirements)

- [安全性注意事項](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a>特性和功能
<a name="BKMK_Features"> </a>

統計資料管理員可讓您：

- 即時查看所有伺服器的原始資料。  (資料會以極高的速率進行抽樣，並在小於一秒內傳送至網站。 ) 

- 查看針對特定角色進行匯總的資料;例如，前端伺服器、轉送伺服器、Edge Server 等等。

- 向下流覽以查看特定網站、網站內特定集區的資料，以及集區中的特定伺服器。

- 建立自訂圖表，以預設顯示所選的計數器。

- 僅在 X 軸和 y 軸上，或在 X 軸上進行縮放及平移。

- 使用日期範圍或時間點來篩選資料。

- 根據建立的主要健康情況指示器，查看伺服器效能 (KHIs) 。 KHIs 代表具有定義之狀況良好範圍的效能計數器集合。

- 查看每個計數器的詳細度量。

- 比較多個人口或伺服器上的資料。

- View 潛在的計數器報告，以找出未向儀表板服務報告目前資料的代理人。

- 將圖表資料的特定實例儲存至檔案。

- 即時查看 KHIs，包含更新。 如果啟用 [歷程記錄] 視圖，只會顯示新的失敗。

  - 一次查看所有 KHIs

  - 透過伺服器 (景觀 view 查看 KHIs) 

  - View KHI 定義

## <a name="whats-new-in-release-20"></a>版本2.0 的新功能
<a name="BKMK_WhatsNew"> </a>

下列說明版本2.0 中的新功能。 如果您有現有的統計資料管理員部署，但尚未升級，請參閱[升級統計資料管理員以取得商務用 Skype Server](upgrade.md)。

- 已針對 Edge Media、Fabric Health、集區容錯移轉和註冊案例新增方案視圖。

- 已新增許多新的計數器，供 SQL 伺服器、更商務用 Skype 使用計數器等等。

- 與統計資料管理員代理程式的監看員節點整合–如果在監看員節點上安裝代理程式，它會將綜合交易統計資料包告為計數器傳回統計資料管理員。

- 許多可靠性和效能的增強功能。

若要驗證您正在執行的統計資料管理員網站版本：

- 在檔案資源管理器中，開啟 (預設目錄) C:\Program 檔案 \ 商務用 Skype Server StatsMan WebSite\bin

- 在 StatsManHubWebSite.dll 上按一下滑鼠右鍵，並查看其屬性

- 產品版本將會顯示在描述詳細資料中。

## <a name="components"></a>元件
<a name="BKMK_Components"> </a>

統計資料管理員包含下列元件：

- **代理。** 在每個受監視伺服器上執行的輕量代理程式。 代理程式允許具有本機匯總的效能計數器的可設定高率輪詢。

- **聽眾。** 伺服器端 API，會從所有代理程式接收資料，並在人口中匯總資料。

- **樞紐。** 會做為系統的用戶端 API，在網頁伺服器上執行 (s) ，並為透過網站所連接的用戶端提供即時資料更新。  (會在網站 msi 中自動安裝 Hub。 ) 

- **網站。** 一種使用者介面，可將系統中所有可用的功能集中在一起。

此外，[統計資料管理員] 也需要 **Redis**，這是一種開放來源的資料結構伺服器，供記憶體快取之用。 如需下載 Redis 的詳細資訊，請參閱 [部署統計資料管理員](deploy.md#BKMK_Deploy) 。

## <a name="on-premises-deployment"></a>內部部署
<a name="BKMK_DeploymentOptions"> </a>

在內部部署中，單一伺服器會裝載所有伺服器端統計資料管理員元件。

下圖顯示內部部署，其中的統計資料管理員網站、Hub、接聽程式和 Redis 快取系統會主控于單一機器上。 統計資料管理員監控三台商務用 Skype 伺服器，每個伺服器都有一個代理程式將資料傳送至監聽器。 使用者連線到單一網站，以查看統計資料管理員匯總的所有資料：

![內部部署的統計管理員](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a>需求
<a name="BKMK_Requirements"> </a>

在您部署統計資料管理員之前，您必須考慮下列軟體、網路及硬體需求。

### <a name="software-requirements"></a>軟體需求

- Windows Server 2016 和2019

- IIS (會自動安裝) 

- Redis

- 統計資料管理員服務 (會自動安裝) 

- PSExec-需要進行遠端代理程式部署

- .NET 4.5 (隨附于 2012 R2) -代理程式和伺服器端元件所需的元件
- 下載[商務用 Skype Server、Real-Time 統計資料管理員 (64 位) ](https://www.microsoft.com/en-in/download/details.aspx?id=57518)

### <a name="networking-requirements"></a>網路需求


|**主控伺服器**|**Agents**|**聽眾**|
|:-----|:-----|:-----|
|最小十億位元全雙工網路。  <br/> |輸出 TCP 埠 8443 (可自訂的埠號碼) 與監聽器通訊。  <br/> |監聽器埠在所有伺服器上都必須相同。  <br/> |
|輸入 TCP 埠80或443開啟以主控網站。  <br/> |||
|輸入 TCP 埠 8443 (可自訂的埠號碼) 供代理程式與其通訊。  <br/> |||

在安裝期間，會自動建立監聽器和網站的防火牆埠。 針對代理程式，安裝會假設預設允許輸出 TCP 連線。

### <a name="hardware-requirements"></a>硬體需求

在內部部署中，一部伺服器主控所有伺服器端統計資料管理員元件的伺服器，平均有 16 GB RAM 和 4 CPU 的伺服器應該能夠每秒支援大約150的範例。 若要判斷您可以支援多少計數器/代理程式，請使用下列計算：

100 server \* 80 計數器 \* 1 每分鐘從每個代理程式/60 秒 = 每秒大約133樣本。

## <a name="security-considerations"></a>安全考量
<a name="BKMK_Security"> </a>

伺服器間的所有流量都會加密。

- 加密 HTTPS 流量) 預設會透過埠 8443 (傳送，而不是從 Agent 傳送至監聽器伺服器。

- 代理程式會驗證服務器上的 SSL 指紋，以確保監聽器伺服器是預期的收件者。 請注意，代理程式會使用憑證指紋驗證 (，而不是鏈式驗證) 。 因為可能會使用自我簽署的憑證，所以不會執行完整的憑證驗證。

- 當代理程式滿意後，該監聽器便會透過監聽器所驗證的方式來顯示密碼。

- 代理程式會在連接到監聽器時，開始傳輸效能資料。

## <a name="for-more-information"></a>相關資訊
<a name="BKMK_Security"> </a>

如需詳細資訊，請參閱下列各主題：

- [部署商務用 Skype Server 統計資料](deploy.md)

- [升級商務用 Skype Server 統計資料](upgrade.md)

- [疑難排解商務用 Skype Server 統計資料](troubleshoot.md)
