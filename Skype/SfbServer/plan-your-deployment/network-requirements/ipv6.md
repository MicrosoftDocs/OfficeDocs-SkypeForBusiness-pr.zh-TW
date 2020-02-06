---
title: 在商務用 Skype 中規劃 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：在您安裝商務用 Skype Server 之前，請先執行 IPv6。
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802073"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>在商務用 Skype 中規劃 IPv6
 
**摘要：** 在安裝商務用 Skype Server 之前，請先執行 IPv6。
  
商務用 Skype 伺服器包括對 IP 版本6（IPv6）位址的支援，以及對 IP 版本4（IPv4）位址的持續支援。 

IPv4 位址是32位位址，可讓電腦透過網際網路進行通訊。 由於世界各地的裝置數量不斷增加，因此可用的 IPv4 位址已耗盡。因此，許多新的裝置都要移至使用 IPv6 位址。 IPv6 位址會執行與 IPv4 位址相同的功能（有一些額外功能），但不只使用32位的 IPv6 位址，而是使用128位。 這不僅可提供一組新的位址，也能提供大量的位址。 

典型的 IPv4 位址看起來像這樣：192.0.2.235，而 IPv6 位址看起來像這樣：2001：0db8：85a3：0000：0000：8a2e：0370：7334。 使用 IPv6 位址之裝置的格式設定和功能變更需要在商務用 Skype Server 安裝中進行幾個部署和設定考慮。 

本主題包含下列各節：
  
- [IP 位址類型概覽](ipv6.md#over)
    
- [IPv6 的技術需求](ipv6.md#tech)
    
- [IPv6 的移轉與共存考量](ipv6.md#migration)
    
如果您決定要使用 IPv6 位址，請參閱[商務用 Skype 文章中的設定 IP 位址類型](ip-address-types.md)。
  
## <a name="overview-of-ip-address-types"></a>IP 位址類型概覽
<a name="over"> </a>

在商務用 Skype Server 中設定 IP 位址時，有三個選項可供您選擇。 您可以將商務用 Skype Server 設定為僅支援 IP 版本4（IPv4）、僅限 IP 版本6（IPv6），或是兩者的組合（稱為雙堆疊）。 每個類型的設定都要考慮幾個問題：
  
- **僅限 IPv4**由於世界的 IPv4 位址不足，所以已建立 IPv6。 我們最終會在全球完全支援 IPv6，但在這段時間，您企業可能需要與之通訊的許多公司和裝置都不支援 IPv6，而且可能不需要一段時間。 僅提供 IPv4 的設定將有助於確保您的商務用 Skype 伺服器實現可以與大多數現有的裝置通訊。
    
- **僅限 IPv6**相反地，完整的 IPv6 實現會排除與許多現有裝置的通訊。
    
- **雙堆疊**雙堆疊是啟用 IPv4 和 IPv6 位址的網路。 商務用 Skype Server 支援此設定，因為在大多數情況下，從完整 IPv4 轉換到完整 IPv6 時會需要幾年的時間。
    
下列各節概述了各種商務用 Skype 伺服器功能這三種設定的相容性。
  
> [!NOTE]
> 只有在 lab 或驗證目的中，才支援僅含 IPv6 的用戶端或伺服器設定。 生產部署中不支援僅限 IPv6 的配置。 
  
### <a name="client-registration"></a>用戶端註冊
<a name="client"> </a>

|**用戶端端點網路**|**伺服器網路**|
|:-----|:-----|
|Ipv4/ipv6  <br/> |Ipv4/ipv6  <br/> |
|Ipv4/ipv6  <br/> |雙堆疊  <br/> |
|雙堆疊  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |
|雙堆疊  <br/> |IPv6  <br/> |
|IPv6  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>對等用戶端
<a name="peer"> </a>

對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。 在兩個用戶端都成功註冊之後，就支援下列組合。
  
|**用戶端端點1**|**用戶端端點2**|
|:-----|:-----|
|Ipv4/ipv6  <br/> |Ipv4/ipv6  <br/> |
|Ipv4/ipv6  <br/> |雙堆疊  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>會議
<a name="conf"> </a>

會議包括音訊/視頻、應用程式共用和資料共同作業應用程式（例如 whiteboarding 和檔案共用）。
  
|**用戶端端點網路**|**伺服器網路**|
|:-----|:-----|
|Ipv4/ipv6  <br/> |Ipv4/ipv6  <br/> |
|Ipv4/ipv6  <br/> |雙堆疊  <br/> |
|雙堆疊  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |
|雙堆疊  <br/> |IPv6  <br/> |
|IPv6  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>中繼伺服器/PSTN
<a name="med"> </a>

如果通信量是透過 IPv6 介面，商務用 Skype Server 不支援公用交換電話網絡（PSTN）通話的媒體旁路。 如果需要媒體旁路，建議 PSTN 閘道設定為 IPv4。 
  
|**主要介面1**|**PSTN 介面（在中繼伺服器上）**|**PSTN 閘道設定**|
|:-----|:-----|:-----|
|Ipv4/ipv6  <br/> |雙堆疊  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |IPv6  <br/> |
   
1. 主要介面是與商務用 Skype 伺服器元件進行通訊的介面。
  
### <a name="remote-user-peer-to-peer-communications"></a>遠端使用者對等通訊
<a name="remote"> </a>

與遠端使用者進行對等通訊時，包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。
  
|**遠端使用者網路**|**Edge 伺服器（外部邊緣）**|
|:-----|:-----|
|Ipv4/ipv6  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |Ipv4/ipv6  <br/> |
|雙堆疊  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |雙堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>前臺端池和邊緣池設定
<a name="FE_pool"> </a>

下表顯示前端伺服器池與內部邊緣伺服器池之間的支援矩陣。
  
**前端池與邊緣池（內部邊緣）矩陣**

||**Edge 池： IPv4** <br/> |**Edge 池：雙堆疊** <br/> |**Edge 池： IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**前端池： IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前部端池：雙堆疊** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前臺端池： IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\*僅在實驗室環境中使用此組合。
  
下表是支援的內部和外部邊緣介面組合的矩陣。
  
**Edge 池（內部邊緣）與邊緣池（外部邊緣）矩陣**

||**Edge 池（外部邊緣）： IPv4** <br/> |**Edge 池（外部邊緣）：雙堆疊** <br/> |**Edge 池（外部邊緣）： IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edge 池（內部邊緣）： IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**Edge 池（內部邊緣）：雙堆疊** <br/> |否  <br/> |是  <br/> |否  <br/> |
|**Edge 池（內部邊緣）： IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\*僅在實驗室環境中使用此組合。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>針對 IPv6 的高級企業語音支援
<a name="Ent_V"> </a>

包括 [呼叫許可控制（CAC）]、[增強9-1-1 （E9-1）] 或 [媒體旁路] 的部署，必須設定為僅使用 IPv4 或雙堆疊式實現。 使用 IPv6 的端點無法使用下列任何一項功能。
  
> [!NOTE]
> 在雙堆疊部署中，即使商務用 Skype 伺服器用戶端使用 IPv6 連線到商務用 Skype 伺服器，商務用 Skype Server 也會盡最佳努力，將適當的 IPv4 位址對應至支援 E9-1-1。 
  
不支援含 IPv6 位址的位置資訊服務。
  
Exchange 整合通訊（UM）不支援 IPv6。 針對 Exchange UM，請確定 DNS 解析沒有傳回 IPv6 位址。 使用 IPv6 可能會在來電傳送至語音信箱時造成失敗。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>適用于 IPv6 的其他商務用 Skype Server 功能支援
<a name="Ent_V"> </a>

除了先前提及的功能和元件之外，商務用 Skype Server 支援 IPv6 的功能如下：
  
- **常設聊天室**
    
    您可以使用拓撲建立器，將 IPv6 設定成持續聊天。 如需有關設定持續聊天的詳細資訊，請參閱部署持久聊天伺服器檔。
    
- **經驗品質（QoE）和通話詳細資料錄製（CDR）報告**
    
    無論是 IPv4 或 IPv6 類型，監視報告都包含儲存在監視伺服器資料庫的 IP 位址。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 的技術需求
<a name="tech"> </a>

如果您打算為 IPv6 設定商務用 Skype Server，請記住下列需求：
  
- 若要在商務用 Skype Server 上使用 IPv6 位址，您需要針對必須發現並解析為 IPv6 位址的記錄，建立網域名稱系統（DNS）記錄。 IPv6 DNS 使用主機 AAAA （四 A）記錄。 如果您在部署中同時使用 IPv4 和 IPv6，最好是針對 IPv6 與主機 AAAA 記錄，設定及維護主機 A 記錄。 即使您將部署完全轉換為 IPv6，您仍然可能需要仍使用 IPv4 之外部使用者的 IPv4 DNS 主機記錄。
    
    您可以先部署 IPv6 DNS 主機記錄，然後再開始使用 IPv6。 如果用戶端或伺服器不使用 IPv6，將不會參照該記錄。 轉場技術將根據轉換技術設定與原則，決定要使用哪一筆記錄。
    
- 每個 IPv6 位址都有一個範圍。 您可以用來進行 IPv6 定址的三個作用域是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍），以及 IPv6 鏈路本機位址（類似中的自動私人 IP 位址）適用于 IPv4 的 Windows Server）。 一個池內的所有伺服器都應該有相同範圍的 IPv6 位址。 
    
> [!IMPORTANT]
> IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以協助確保您在 Windows Server 層級及商務用 Skype Server 層級指派的位址如期運作。 如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 的移轉與共存考量
<a name="migration"> </a>

Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本6（IPv6）。 針對試驗目的，您可以測試 Lync Server 2010 和商務用 Skype Server 雙堆疊共存。 我們建議您在針對任何一個池啟用 IPv6 （雙堆疊網路）之前，先將指定中央網站的所有池升級至商務用 Skype 伺服器。 如果您只需要設定適用于 IPv6 的 pool，我們建議您在實驗室環境中設定 IPv6 專用池以進行測試。
  
在遷移和共存期間支援下列案例：
  
- 商務用 skype Server、Lync Server 2013 和 Lync Server 2010 池（在 IPv4 模式中，與商務用 Skype Server 在雙堆疊模式中共存）。
    
- 商務用 Skype Server pool （僅限 IPv6 模式）（如果 IPv6 專用池是各自為政的）。
    
## <a name="see-also"></a>另請參閱
<a name="migration"> </a>

[在商務用 Skype 中設定 IP 位址類型](ip-address-types.md)

[IP 版本6定址架構](https://tools.ietf.org/html/rfc4291)
  
[IPv6 全域單播位址格式](https://tools.ietf.org/html/rfc3587)
  
[唯一的局部 IPv6 單播位址](https://tools.ietf.org/html/rfc4193)
