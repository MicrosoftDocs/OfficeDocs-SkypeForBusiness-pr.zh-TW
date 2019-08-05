---
title: 伺服器的埠與通訊協定需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: '摘要: 在執行商務用 Skype Server 前, 請先檢查埠使用方面的考慮。'
ms.openlocfilehash: 613067d90da4fb06811ca1497c83237019b3c021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192963"
---
# <a name="port-and-protocol-requirements-for-servers"></a>伺服器的埠與通訊協定需求
 
**摘要:** 在執行商務用 Skype Server 前, 請先檢查埠使用方面的考慮。
  
商務用 Skype Server 要求外部與內部防火牆的特定埠都已開啟。 此外, 如果您的組織中部署了網際網路通訊協定安全性 (IPsec), 則必須停用傳送音訊、影片和全景影片的埠範圍所使用的 IPsec。 
  
雖然這看起來可能相當令人望而生畏, 但開始使用[商務用 Skype Server 2015 規劃工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)完成這項工作的繁重動作。 當您完成您打算使用之功能的嚮導問題之後, 針對您所定義的每個網站, 您可以在 Edge 管理報表中查看防火牆報告, 並使用其中所列的資訊來建立 yourfirewall 規則。 您也可以調整所使用的許多名稱和 IP 位址, 如需詳細資訊, 請參閱[查看防火牆報告](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)。 請記住, 您可以將 Edge 系統管理報表匯出為 Excel 試算表, 而防火牆報表則會是檔案中的其中一個工作表。 
  
您也可以在 [圖表] 表單中, 從[商務用 Skype Server 2015 文章的技術圖表](../../technical-diagrams.md)中查看 [通訊協定工作負荷] 海報, 以找出這些表格中的資訊。
> [!NOTE]
> - 如果您執行的是商務用 Skype Online (O365), 請參閱[Office 365 url 與 IP 位址範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)。 混合式環境將需要參考本主題, 並[規劃混合式連線性](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
> - 您可以擁有硬體或軟體防火牆, 我們不需要特定的模型或版本。 重要的是哪些埠是白名單, 因此防火牆不會影響商務用 Skype Server 的運作。
  
## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

本節摘要說明伺服器、負載平衡器和商務用 Skype Server 部署中的用戶端所使用的埠和通訊協定。
  
> [!NOTE]
> 商務用 Skype Server 啟動時, 會在 Windows 防火牆中開啟必要的埠。 Windows 防火牆應該已在大部分標準的應用程式中執行, 但如果沒有使用商務用 Skype Server, 就不會正常運作。 
  
如需有關 edge 元件防火牆設定的詳細資料, 請參閱[商務用 Skype server 2015 中的邊緣伺服器案例](../../plan-your-deployment/edge-server-deployments/scenarios.md)。 
  
下表列出每個內部伺服器角色上需要開啟的埠。 
  
**所需的伺服器埠 (依伺服器角色)**

|伺服器角色|服務名稱|通道|通訊協定|筆記|
|:-----|:-----|:-----|:-----|:-----|
|所有伺服器  |SQL 瀏覽器  |1434  |UDP-IN  |中央管理儲存資料庫的本機複製複本的 SQL 瀏覽器。  |
|前端伺服器  |商務用 Skype Server 前端服務  |5060  |TCP-OUT  |您也可以選擇將標準版伺服器與前端伺服器 (例如遠端通話控制伺服器) 的靜態路由使用。  |
|前端伺服器  |商務用 Skype Server 前端服務  |5061  | TCP (TLS) |由標準版伺服器和前端池使用, 可用於伺服器與用戶端 (MTLS) 之間的所有內部 SIP 通訊, 以及前端伺服器與中繼伺服器 (MTLS) 之間的 SIP 通訊。 也用於與監控伺服器進行通訊。  |
| 前端伺服器 |商務用 Skype Server 前端服務  |444  | IP-HTTPS <br/> TCP-OUT  |用於焦點間的 HTTPS 通訊 (管理會議狀態的商務用 Skype 伺服器元件) 與個別伺服器。  <br/> 此埠也用於 Survivable 分支裝置與前端伺服器之間的 TCP 通訊。  |
|前端伺服器  |商務用 Skype Server 前端服務  |135  |DCOM 與遠端程式通話 (RPC)  |用於以 DCOM 為基礎的作業, 例如移動使用者、使用者複製程式同步處理和通訊錄同步處理。  |
|前端伺服器  |商務用 Skype Server IM 會議服務  |5062  |TCP-OUT  |用於立即訊息 (IM) 會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server Web 會議服務  |8057  |TCP (TLS)  |用來偵聽來自用戶端的永久性共用物件模型 (PSOM) 連線。  |
|前端伺服器  |商務用 Skype Server Web 會議相容性服務  |8058  |TCP (TLS)  |用來從 Live Meeting 用戶端和舊版的商務用 Skype Server 中監聽永久性共用物件模型 (PSOM) 連線。  |
|前端伺服器  |商務用 Skype Server 音訊/視訊會議服務  |5063  |TCP-OUT  |用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 音訊/視訊會議服務  |57501-65535  |TCP/UDP  |用於視訊會議的媒體埠範圍。  |
|前端伺服器  |商務用 Skype Server Web 相容性服務  |80  |HTTP  |用於從前端伺服器到網路伺服器陣列 Fqdn (IIS 網頁元件所使用的 Url), 在未使用 HTTPS 時進行通訊。  |
|前端伺服器  |商務用 Skype Server Web 相容性服務  |443  |IP-HTTPS  |用來從前端伺服器與網頁伺服器陣列 Fqdn (IIS 網頁元件所使用的 Url) 進行通訊。  |
|前端伺服器  |商務用 Skype Server Web 相容性服務  |8080  |TCP 與 HTTP  |供外部存取的網頁元件使用。  |
|前端伺服器  |Web 服務器元件  |4443  |IP-HTTPS  |HTTPS (從反向 Proxy) 與 HTTPS 前端端池通訊, 以進行自動探索登入。  |
|前端伺服器  |Web 服務器元件  |8060  |TCP (MTLS)  ||
|前端伺服器  |Web 服務器元件  |8061  |TCP (MTLS)  ||
|前端伺服器  |行動服務元件  |5086  |TCP (MTLS)  |行動服務內部程式使用的 SIP 埠  |
|前端伺服器  |行動服務元件  |5087  |TCP (MTLS)  |行動服務內部程式使用的 SIP 埠  |
|前端伺服器  |行動服務元件  |443  |IP-HTTPS  ||
|前端伺服器  |商務用 Skype Server 會議助理服務 (電話撥入式會議)  |5064  |TCP-OUT  |用於電話撥入式會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 會議助理服務 (電話撥入式會議)  |5072  |TCP-OUT  |用於接聽的傳入 SIP 要求 (撥入會議)。  |
|同時執行 Collocated 轉送伺服器的前端伺服器  |商務用 Skype Server 轉送服務  |5070  |TCP-OUT  |供中繼伺服器用來將前端伺服器的傳入要求傳送到中繼伺服器。  |
|同時執行 Collocated 轉送伺服器的前端伺服器  |商務用 Skype Server 轉送服務  |5067  |TCP (TLS)  |用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。  |
|同時執行 Collocated 轉送伺服器的前端伺服器  |商務用 Skype Server 轉送服務  |5068  |TCP-OUT  |用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。  |
|同時執行 Collocated 轉送伺服器的前端伺服器  |商務用 Skype Server 轉送服務  |5081  |TCP-OUT  |用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。  |
|同時執行 Collocated 轉送伺服器的前端伺服器  |商務用 Skype Server 轉送服務  |5082  |TCP (TLS)  |用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 應用程式共用服務  |5065  |TCP-OUT  |用於應用程式共用的傳入 SIP 偵聽要求。  |
|前端伺服器  |商務用 Skype Server 應用程式共用服務  |49152-65535  |TCP-OUT  |用來共用應用程式的媒體埠範圍。  |
|前端伺服器  |商務用 Skype Server 會議宣告服務  |5073  |TCP-OUT  |用於商務用 Skype Server 會議宣告服務的傳入 SIP 要求 (也就是電話撥入式會議)。  |
|前端伺服器  |商務用 Skype Server 通話寄存服務  |5075  |TCP-OUT  |用於來電寄存應用程式的內送 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 音訊測試服務  |5076  |TCP-OUT  |用於音訊測試服務的傳入 SIP 要求。  |
|前端伺服器  |不適用  |5066  |TCP-OUT  |用於輸出增強型 9-1-1 (E9-1-1) 閘道。  |
|前端伺服器  |商務用 Skype Server 回應群組服務  |5071  |TCP-OUT  |用於回應群組應用程式的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 回應群組服務  |8404  |TCP (MTLS)  |用於回應群組應用程式的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 頻寬原則服務  |5080  |TCP-OUT  |用於由頻寬原則服務為 A/V 邊緣開啟流量的呼叫許可控制。  |
|前端伺服器  |商務用 Skype Server 檔案共用伺服器存取權  |445   |SMB/TCP  | 用來檢索儲存在檔案共用伺服器上的通訊錄、會議內容及其他專案。  |
|前端伺服器  |商務用 Skype Server 頻寬原則服務  |448  |TCP-OUT  |用於商務用 Skype Server 頻寬原則服務的呼叫許可控制。  |
|中央管理儲存所在的前端伺服器  | 商務用 Skype Server 主版複製器代理程式服務 |445  |TCP-OUT  |用來將配置資料從中央管理存儲推送到執行商務用 Skype Server 的伺服器。  |
|所有伺服器  |SQL 瀏覽器  |1434  |UDP-IN  |本機 SQL Server 實例中的中央管理儲存在本機複製複本的 SQL 瀏覽器  |
|所有內部伺服器  |各種各樣  |49152-57500  |TCP/UDP  |在所有內部伺服器上, 音訊會議所用的媒體埠範圍。 是由所有終止音訊的伺服器所使用: 前端伺服器 (適用于商務用 Skype Server 會議助理服務、商務用 Skype Server 會議宣告服務, 以及商務用 Skype Server 音訊/視訊會議服務) 與中繼伺服器。  |
|Office Web Apps 伺服器  ||443  ||由商務用 Skype Server 用來連線到 Office Web Apps 伺服器。  |
|控制器  |商務用 Skype Server 前端服務  |5060  |TCP-OUT  |您也可以選擇將靜態路由用於受信任的服務, 例如遠端通話控制伺服器。  |
|控制器  |商務用 Skype Server 前端服務  |444  |IP-HTTPS  <br/> TCP-OUT  |前端與控制器之間的伺服器間通訊。 此外, 用戶端憑證發佈 (到前端伺服器) 或驗證用戶端憑證是否已發佈。  |
|控制器  |商務用 Skype Server Web 相容性服務  |80  |TCP-OUT  |用於從董事到網頁伺服器陣列 Fqdn (IIS 網頁元件所使用的 Url) 的初始通訊。 在 [標準] 操作中, 會使用埠443和通訊協定類型 TCP, 切換到 HTTPS 流量。  |
|控制器  |商務用 Skype Server Web 相容性服務  |443  |IP-HTTPS  |用於從控制器到網頁伺服器陣列 Fqdn (IIS 網頁元件所用的 Url) 的通訊。  |
|控制器  |商務用 Skype Server 前端服務  |5061  |TCP-OUT  |用於伺服器與用戶端連線之間的內部通訊。  |
|中繼伺服器  |商務用 Skype Server 轉送服務  |5070  |TCP-OUT  |由中繼伺服器用於來自前端伺服器的傳入要求。  |
|中繼伺服器  |商務用 Skype Server 轉送服務  |5067  |TCP (TLS)  |用於來自 PSTN 閘道的傳入 SIP 要求。  |
|中繼伺服器  |商務用 Skype Server 轉送服務  |5068  |TCP-OUT  |用於來自 PSTN 閘道的傳入 SIP 要求。  |
|中繼伺服器  |商務用 Skype Server 轉送服務  |5070  |TCP (MTLS)  |用於來自前端伺服器的 SIP 要求。  |
|持續聊天前端伺服器  |持續聊天 SIP  |5041  |TCP (MTLS)  ||
|持續聊天前端伺服器  |持續聊天 Windows Communication Foundation (WCF)  |881  |TCP (TLS) 和 TCP (MTLS)  ||
|持續聊天前端伺服器  |持續聊天檔案傳輸服務  |443  |TCP (TLS)  ||
   
> [!NOTE]
> 某些遠端呼叫控制案例需要在前端伺服器或控制器與 PBX 之間建立 TCP 連線。 雖然商務用 Skype 伺服器不再使用 TCP 埠 5060, 但在遠端呼叫控制部署期間, 您會建立信任的伺服器設定, 這會將 RCC 線路伺服器 FQDN 與前端伺服器或控制器用來連線到的 TCP 埠產生關聯PBX 系統。 如需詳細資訊, 請參閱商務用 Skype Server Management Shell 檔中的**CsTrustedApplicationComputer** Cmdlet。
  
針對只使用硬體負載平衡的池 (而非 DNS 負載平衡), 下表顯示需要開啟硬體負載平衡器的埠。
  
**硬體負載平衡器埠 (如果只使用硬體負載平衡)**

|負載平衡器|通道|通訊協定|
|:-----|:-----|:-----|
|前端伺服器負載平衡器  |5061  |TCP (TLS)  |
|前端伺服器負載平衡器  |444  |IP-HTTPS  |
|前端伺服器負載平衡器  |135  |DCOM 與遠端程式通話 (RPC)  |
|前端伺服器負載平衡器  |80  |HTTP  |
|前端伺服器負載平衡器  |8080  |從前臺伺服器 (由 NTLM 驗證的用戶端和裝置) 對根憑證的 TCP 用戶端和裝置檢索  |
|前端伺服器負載平衡器  |443  |IP-HTTPS  |
|前端伺服器負載平衡器  |4443  |HTTPS (從反向 proxy)  |
|前端伺服器負載平衡器  |5072  |TCP-OUT  |
|前端伺服器負載平衡器  |5073  |TCP-OUT  |
|前端伺服器負載平衡器  |5075  |TCP-OUT  |
|前端伺服器負載平衡器  |5076  |TCP-OUT  |
|前端伺服器負載平衡器  |5071  |TCP-OUT  |
|前端伺服器負載平衡器  |5080  |TCP-OUT  |
|前端伺服器負載平衡器  |448  |TCP-OUT  |
|中繼伺服器負載平衡器  |5070  |TCP-OUT  |
|前端伺服器負載平衡器 (如果該池也會執行轉送伺服器)  |5070  |TCP-OUT  |
|控制器負載平衡器  |443  |IP-HTTPS  |
|控制器負載平衡器  |444  |IP-HTTPS  |
|控制器負載平衡器  |5061  |TCP-OUT  |
|控制器負載平衡器  |4443  |HTTPS (從反向 proxy)  |
   
您的前端池和使用 DNS 負載平衡的控制器池也必須部署硬體負載平衡器。 下表顯示在這些硬體負載平衡器上需要開啟的埠。
  
**使用 DNS 負載平衡的硬體負載平衡器埠**

|負載平衡器|通道|通訊協定|
|:-----|:-----|:-----|
|前端伺服器負載平衡器  |80  |HTTP  |
|前端伺服器負載平衡器  |443  |IP-HTTPS  |
|前端伺服器負載平衡器  |8080  |從前臺伺服器 (由 NTLM 驗證的用戶端和裝置) 對根憑證的 TCP 用戶端和裝置檢索  |
|前端伺服器負載平衡器  |4443  |HTTPS (從反向 proxy)  |
|控制器負載平衡器  |443  |IP-HTTPS  |
|控制器負載平衡器  |4443  |HTTPS (從反向 proxy)  |

**所需的用戶端埠**

|元件|通道|通訊協定|筆記|
|:-----|:-----|:-----|:-----|
|台  |67/68  |動態  |由商務用 Skype Server 用來尋找註冊機 FQDN (也就是 DNS SRV 失敗且未設定手動設定)。  |
|台  |443  |TCP (TLS)  |用於用戶端到伺服器的 SIP 流量, 以供外部使用者存取。  |
|台  |443  |TCP (PSOM/TLS)  |用於外部使用者存取網路會議會話。  |
|台  |443  |TCP (STUN/MSTURN)  |供外部使用者存取 A/V 會話及媒體 (TCP)  |
|台  |3478  |UDP (STUN/MSTURN)  |供外部使用者存取 A/V 會話及媒體 (UDP)  |
|台  |5061  |TCP (MTLS)  |用於用戶端到伺服器的 SIP 流量, 以供外部使用者存取。  |
|台  |6891-6901  |TCP-OUT  |用於商務用 Skype 用戶端與舊版用戶端之間的檔案傳輸。  |
|台  |1024-65535\*  |TCP/UDP  |音訊埠範圍 (所需的最小20個埠)  |
|台  |1024-65535\*  |TCP/UDP  |影片埠範圍 (需要20個埠的最小值)。  |
|台  |1024-65535\*  |TCP-OUT  |對等檔案傳輸 (適用于會議檔案傳輸, 用戶端使用 PSOM)。  |
|台  |1024-65535\*  |TCP-OUT  |應用程式共用。  |
|Aastra 6721ip 常見區域電話  <br/> Aastra 6725ip phone  <br/> HP 4110 IP Phone (通用區域電話)  <br/> HP 4120 IP Phone (辦公桌電話)  <br/> Polycom CX500 IP 常見區域電話  <br/> Polycom CX600 IP 電話機  <br/> Polycom CX700 IP 電話機  <br/> Polycom CX3000 IP 會議電話  |67/68  |動態  |由所列的裝置使用, 以尋找商務用 Skype 伺服器憑證、資源調配 FQDN 及註冊機 FQDN。  |
   
\*若要設定這些媒體類型的特定埠, 請使用 CsConferencingConfiguration Cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 參數)。
  
> [!NOTE]
> 商務用 Skype 用戶端的安裝程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。 

> [!NOTE]
> 在用戶端必須遍歷組織的防火牆 (例如, 任何外部通訊或其他組織託管的會議) 的情況下, 對於外部使用者存取所用的埠, 都是必要的。 
  
## <a name="ipsec-exceptions"></a>IPsec 例外狀況

針對網際網路通訊協定安全性 (IPsec) (請參閱已部署的 IETF RFC 4301-4309) 商業網路, 必須停用用於傳送音訊、影片和全景影片的埠範圍。 建議因需要避免由於 IPsec 協商而分配媒體埠的任何延遲。
  
下表說明建議的 IPsec 例外狀況設定。 
  
**建議的 IPsec 例外狀況**

|規則名稱|來源 IP|目的地 IP|通訊協定|來源埠|目的地埠|驗證需求|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V 邊緣伺服器內部入站  |每  |A/V 邊緣伺服器內部  |UDP 與 TCP  |每  |每  |不要驗證  |
|A/V 邊緣伺服器外部輸入  |每  |A/V 邊緣伺服器外部  |UDP 與 TCP  |每  |每  |不要驗證  |
|A/V 邊緣伺服器內部出站  |A/V 邊緣伺服器內部  |每  |UDP &amp; TCP  |每  |每  |不要驗證  |
|A/V 邊緣伺服器外部輸出  |A/V 邊緣伺服器外部  |每  |UDP 與 TCP  |每  |每  |不要驗證  |
|中繼伺服器入站  |每  |仲介  <br/> 伺服器 (s)  |UDP 與 TCP  |每  |每  |不要驗證  |
|轉送伺服器出站  |仲介  <br/> 伺服器 (s)  |每  |UDP 與 TCP  |每  |每  |不要驗證  |
|會議助理入站  |每  |運行會議助理的前端伺服器  |UDP 與 TCP  |每  |每  |不要驗證  |
|會議助理出站  |運行會議助理的前端伺服器  |每  |UDP 與 TCP  |每  |每  |不要驗證  |
|A/V 會議入站  |每  |前端伺服器  |UDP 與 TCP  |每  |每  |不要驗證  |
|A/V 會議輸出  |前端伺服器  |每  |UDP 與 TCP  |每  |每  |不要驗證  |
|Exchange 入站  |每  |Exchange 整合通訊  |UDP 與 TCP  |每  |每  |不要驗證  |
|應用程式共用伺服器入站  |每  |應用程式共用伺服器  |TCP-OUT  |每  |每  |不要驗證  |
|應用程式共用伺服器出站  |應用程式共用伺服器  |每  |TCP-OUT  |每  |每  |不要驗證  |
|Exchange 輸出  |Exchange 整合通訊  |每  |UDP 與 TCP  |每  |每  |不要驗證  |
|台  |每  |每  |UDP-IN  |指定的媒體埠範圍  |每  |不要驗證  |
