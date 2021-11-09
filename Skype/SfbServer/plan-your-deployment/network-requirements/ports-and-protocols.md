---
title: 伺服器的埠與通訊協定需求
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 摘要：在實施商務用 Skype Server 之前，請先複查埠使用方式考慮。
ms.openlocfilehash: c820070fb73dd1f3325b0141a3fa05b3f19bd683
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834069"
---
# <a name="port-and-protocol-requirements-for-servers"></a>伺服器的埠與通訊協定需求
 
**摘要：** 在實施商務用 Skype Server 之前，請先複查埠使用方式考慮。
  
商務用 Skype Server 要求外部和內部防火牆上的特定埠皆已開啟。 此外，如果您的組織中已部署網際網路通訊協定安全性 (IPsec) ，IPsec 必須透過用於傳遞音訊、影片及全景影片的埠範圍加以停用。 
  
雖然這種做法似乎有點令人望而生畏，但使用商務用 Skype Server 2015 規劃工具才能進行規劃的繁重提升。 當您已完成您計畫使用哪些功能的嚮導問題後，針對您所定義的每個網站，您可以在 Edge 管理報告中查看防火牆報告，並使用這裡所列的資訊來建立防火牆規則。 您也可以調整使用的名稱和 IP 位址，如需詳細資訊，請參閱 [複查防火牆報告](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)。 請記住，您可以將 Edge 系統管理員報告匯出為 Excel 試算表，而防火牆報告將會是檔案中的其中一個工作表。 
  
您可以在 [圖表] 表單中找到這些表格中的資訊，方法是從技術圖表中的「連結到」[商務用 Skype Server 2015](../../technical-diagrams.md)文章中查看。

> [!NOTE]
> - 如果您是執行商務用 Skype 線上 (Microsoft 365 或 Office 365) 請參閱[Microsoft 365 和 Office 365 URLs 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)。 混合式環境必須參考本主題，也會 [規劃混合](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)式連線。
> - 您可以有硬體或軟體防火牆。 不需要特定的模型或版本。 重要的是將哪些埠新增至 allowlist，防火牆就不會影響商務用 Skype Server 的運作。
  
## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

本節摘要說明商務用 Skype Server 部署中的伺服器、負載平衡器和用戶端所使用的埠和通訊協定。
  
> [!NOTE]
> 商務用 Skype Server 啟動時，它會在 Windows 防火牆中開啟必要的埠。 Windows防火牆應該已經在大多數的一般應用程式中執行，但如果沒有使用商務用 Skype Server 將不會正常運作。 
  
如需 edge 元件的防火牆設定的詳細資訊，請參閱[商務用 Skype Server 2015 中的 edge Server 案例](../../plan-your-deployment/edge-server-deployments/scenarios.md)。 
  
下表列出每個內部伺服器角色上必須開啟的埠。 
  
**伺服器角色所 (的必要伺服器埠)**

|伺服器角色|服務名稱|連接埠|Protocol (通訊協定)|附註|
|:-----|:-----|:-----|:-----|:-----|
|所有伺服器  |SQL 瀏覽器  |1434  |UDP  |SQL瀏覽器以取得中央管理存放區資料庫的本機複製副本。  |
|Front-End 伺服器  |商務用 Skype Server Front-End 服務  |5060  |TCP  |Standard Edition 伺服器與前端伺服器搭配使用，以進行信任服務的靜態路由，例如遠端呼叫控制伺服器。  |
|前端伺服器  |商務用 Skype Server Front-End 服務  |5061  | TCP (TLS)  |用於 Standard Edition 伺服器與前端集區，以用於伺服器之間 (MTLS) 的所有內部 sip 通訊、伺服器與用戶端 (TLS) 之間的 sip 通訊，以及前端伺服器與轉送伺服器之間的 sip 通訊 (MTLS) 。 也用來與監控伺服器進行通訊。  |
| 前端伺服器 |商務用 Skype Server Front-End 服務  |444  | HTTPS: <br/> TCP  |用於 (管理會議狀態) 和個別伺服器的商務用 Skype Server 元件之間的 HTTPS 通訊。  <br/> 此埠也用於 Survivable 分支裝置和前端伺服器之間的 TCP 通訊。  |
|前端伺服器  |商務用 Skype Server Front-End 服務  |135  |DCOM 和遠端過程呼叫 (RPC)   |用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製器同步處理及通訊錄同步處理。  |
|前端伺服器  |商務用 Skype ServerIM 會議服務  |5062  |TCP  |用於立即訊息 (IM) 會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype ServerWeb 會議服務  |8057  |TCP (TLS)   |用於聆聽持續性共用物件模型 (PSOM) 來自用戶端的連線。  |
|前端伺服器  |商務用 Skype ServerWeb 會議相容性服務  |8058  |TCP (TLS)   |用於聆聽持續性共用物件模型 (PSOM) 即時會議用戶端和舊版商務用 Skype Server 的連線。  |
|前端伺服器  |商務用 Skype Server會議服務 Audio/Video  |5063  |TCP  |用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server會議服務 Audio/Video  |57501-65535  |TCP/UDP  |用於視訊會議的媒體埠範圍。  |
|前端伺服器  |商務用 Skype ServerWeb 相容性服務  |80  |HTTP  |用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 不使用 HTTPS 時。  |
|前端伺服器  |商務用 Skype ServerWeb 相容性服務  |443  |HTTPS:  |用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。  |
|前端伺服器  |商務用 Skype ServerWeb 相容性服務  |8080  |TCP 和 HTTP  |供外部存取的 web 元件使用。  |
|前端伺服器  |網頁伺服器元件  |4443  |HTTPS:  |HTTPS (，來自反向 Proxy) 與 HTTPS 前端集區間的自動探索登入通訊。  |
|前端伺服器  |網頁伺服器元件  |8060  |TCP (MTLS)   ||
|前端伺服器  |網頁伺服器元件  |8061  |TCP (MTLS)   ||
|前端伺服器  |行動服務元件  |5086  |TCP (MTLS)   |行動服務內部程式使用的 SIP 埠  |
|前端伺服器  |行動服務元件  |5087  |TCP (MTLS)   |行動服務內部程式使用的 SIP 埠  |
|前端伺服器  |行動服務元件  |443  |HTTPS:  ||
|前端伺服器  |商務用 Skype Server 會議語音應答服務 (電話撥入式會議)   |5064  |TCP  |用於電話撥入式會議的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server 會議語音應答服務 (電話撥入式會議)   |5072  |TCP  |用於在會議) 中傳入的 SIP 要求 (撥號語音應答。  |
|同時執行組合轉送伺服器的前端伺服器  |商務用 Skype Server轉送服務  |5070  |TCP  |由轉送伺服器用於來自前端伺服器到轉送伺服器的傳入要求。  |
|同時執行組合轉送伺服器的前端伺服器  |商務用 Skype Server轉送服務  |5067  |TCP (TLS)   |用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。  |
|同時執行組合轉送伺服器的前端伺服器  |商務用 Skype Server轉送服務  |5068  |TCP  |用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。  |
|同時執行組合轉送伺服器的前端伺服器  |商務用 Skype Server轉送服務  |5081  |TCP  |用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。  |
|同時執行組合轉送伺服器的前端伺服器  |商務用 Skype Server轉送服務  |5082  |TCP (TLS)   |用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。  |
|前端伺服器  |商務用 Skype Server應用程式共用服務  |5065  |TCP  |用於應用程式共用的傳入 SIP 聆聽要求。  |
|前端伺服器  |商務用 Skype Server應用程式共用服務  |49152-65535  |TCP  |用於應用程式共用的媒體埠範圍。  |
|前端伺服器  |商務用 Skype Server 會議宣告服務  |5073  |TCP  |用於商務用 Skype Server 會議宣告服務的傳入 SIP 要求 (也就是用於電話撥入式會議) 。  |
|前端伺服器  |商務用 Skype Server通話駐留服務  |5075  |TCP  |用於通話駐留應用程式的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server音訊測試服務  |5076  |TCP  |用於音訊測試服務的傳入 SIP 要求。  |
|前端伺服器  |不適用  |5066  |TCP  |用於輸出增強型 9-1-1 (E9-1-1) 閘道。  |
|前端伺服器  |商務用 Skype Server回應群組服務  |5071  |TCP  |用於回應群組應用程式的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server回應群組服務  |8404  |TCP (MTLS)   |用於回應群組應用程式的傳入 SIP 要求。  |
|前端伺服器  |商務用 Skype Server頻寬原則服務  |5080  |TCP  |用於 A/V Edge 輪流流量的頻寬原則服務的通話許可控制。  |
|前端伺服器  |商務用 Skype Server檔共用伺服器存取  |445   |SMB/TCP  | 用來取得通訊錄、會議內容，以及儲存在檔案共用伺服器上的其他專案。  |
|前端伺服器  |商務用 Skype Server頻寬原則服務  |448  |TCP  |用於商務用 Skype Server 頻寬原則服務的通話許可控制。  |
|中央管理存放區所在的前端伺服器  | 商務用 Skype Server主複製器代理程式服務 |445  |TCP  |用來將設定資料從中央管理存放區推送至執行商務用 Skype Server 的伺服器。  |
|所有伺服器  |SQL 瀏覽器  |1434  |UDP  |SQL本機 SQL Server 實例中中央管理存放區資料的本地複寫複本瀏覽器  |
|所有內部伺服器  |各種  |49152-57500  |TCP/UDP  |用於所有內部伺服器的音訊會議的媒體埠範圍。 由終止音訊的所有伺服器使用：前端伺服器 (商務用 Skype Server 會議語音應答服務、商務用 Skype Server 會議宣告服務，以及商務用 Skype Server Audio/Video 會議服務) 和轉送伺服器。  |
|OfficeWeb 應用程式伺服器  ||443  ||由商務用 Skype Server 用來連線至 Office Web Apps Server。  |
|董事  |商務用 Skype Server Front-End 服務  |5060  |TCP  |選擇性地用於信任服務的靜態路由，例如遠端呼叫控制伺服器。  |
|董事  |商務用 Skype Server Front-End 服務  |444  |HTTPS:  <br/> TCP  |前端和 Director 之間的伺服器間通訊。 此外，用戶端憑證發行 (至前端伺服器) 或驗證是否已發佈用戶端憑證。  |
|董事  |商務用 Skype ServerWeb 相容性服務  |80  |TCP  |用於從 Director 到 web 伺服器陣列 Fqdn (的初始通訊) IIS web 元件所使用的 URLs。 在正常作業中，會使用埠443和通訊協定類型 TCP 切換到 HTTPS 流量。  |
|董事  |商務用 Skype ServerWeb 相容性服務  |443  |HTTPS:  |用於從 Director 到 web 伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。  |
|董事  |商務用 Skype Server Front-End 服務  |5061  |TCP  |用於伺服器與用戶端連線之間的內部通訊。  |
|轉送伺服器  |商務用 Skype Server轉送服務  |5070  |TCP  |由轉送伺服器用於來自前端伺服器的傳入要求。  |
|轉送伺服器  |商務用 Skype Server轉送服務  |5067  |TCP (TLS)   |用於來自 PSTN 閘道的傳入 SIP 要求。  |
|轉送伺服器  |商務用 Skype Server轉送服務  |5068  |TCP  |用於來自 PSTN 閘道的傳入 SIP 要求。  |
|轉送伺服器  |商務用 Skype Server轉送服務  |5070  |TCP (MTLS)   |用於來自前端伺服器的 SIP 要求。  |
|Persistent Chat 前端伺服器  |Persistent Chat SIP  |5041  |TCP (MTLS)   ||
|Persistent Chat 前端伺服器  | (WCF) 的持續性聊天 Windows Communication Foundation  |881  |TCP (TLS) 和 TCP (MTLS)   ||
|Persistent Chat 前端伺服器  |Persistent Chat File 傳遞服務  |443  |TCP (TLS)   ||
   
> [!NOTE]
> 某些遠端呼叫控制案例需要在前端伺服器或 Director 和 PBX 之間建立 TCP 連線。 雖然商務用 Skype Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，此設定會將 RCC 線路伺服器 FQDN 與前端伺服器或 Director 用來連接 PBX 系統的 TCP 通訊埠產生關聯。 如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔中的 **CsTrustedApplicationComputer** Cmdlet。
  
針對只使用硬體負載平衡的集區 (不) DNS 負載平衡]，下表顯示需要開啟硬體負載平衡器的埠。
  
**硬體負載平衡器埠（如果只使用硬體負載平衡）**

|負載平衡器|連接埠|Protocol (通訊協定)|
|:-----|:-----|:-----|
|前端伺服器負載平衡器  |5061  |TCP (TLS)   |
|前端伺服器負載平衡器  |444  |HTTPS:  |
|前端伺服器負載平衡器  |135  |DCOM 和遠端過程呼叫 (RPC)   |
|前端伺服器負載平衡器  |80  |HTTP  |
|前端伺服器負載平衡器  |8080  |TCP-用戶端和裝置對來自前端伺服器-用戶端和裝置的根憑證的驗證  |
|前端伺服器負載平衡器  |443  |HTTPS:  |
|前端伺服器負載平衡器  |4443  |反向 proxy 中的 HTTPS ()   |
|前端伺服器負載平衡器  |5072  |TCP  |
|前端伺服器負載平衡器  |5073  |TCP  |
|前端伺服器負載平衡器  |5075  |TCP  |
|前端伺服器負載平衡器  |5076  |TCP  |
|前端伺服器負載平衡器  |5071  |TCP  |
|前端伺服器負載平衡器  |5080  |TCP  |
|前端伺服器負載平衡器  |448  |TCP  |
|轉送伺服器負載平衡器  |5070  |TCP  |
|前端伺服器負載平衡器 (如果集區也執行轉送伺服器)   |5070  |TCP  |
|Director 負載平衡器  |443  |HTTPS:  |
|Director 負載平衡器  |444  |HTTPS:  |
|Director 負載平衡器  |5061  |TCP  |
|Director 負載平衡器  |4443  |反向 proxy 中的 HTTPS ()   |
   
使用 DNS 負載平衡的前端集區和 Director 集區也必須部署硬體負載平衡器。 下表顯示這些硬體負載平衡器上需要開啟的埠。
  
**硬體負載平衡器埠（如果使用 DNS 負載平衡）**

|負載平衡器|連接埠|Protocol (通訊協定)|
|:-----|:-----|:-----|
|前端伺服器負載平衡器  |80  |HTTP  |
|前端伺服器負載平衡器  |443  |HTTPS:  |
|前端伺服器負載平衡器  |8080  |TCP-用戶端和裝置對來自前端伺服器-用戶端和裝置的根憑證的驗證  |
|前端伺服器負載平衡器  |4443  |反向 proxy 中的 HTTPS ()   |
|Director 負載平衡器  |443  |HTTPS:  |
|Director 負載平衡器  |4443  |反向 proxy 中的 HTTPS ()   |

**必要的用戶端埠**

|元件|連接埠|Protocol (通訊協定)|附註|
|:-----|:-----|:-----|:-----|
|用戶端  |67/68  |DHCP  |由商務用 Skype Server 用來尋找註冊機 FQDN (也就是，如果 DNS SRV 失敗，且未設定手動設定) 。  |
|用戶端  |443  |TCP (TLS)   |用於外部使用者存取的用戶端對伺服器 SIP 流量。  |
|用戶端  |443  |TCP (PSOM/TLS)   |用於外部使用者存取 web 會議會話。  |
|用戶端  |443  |TCP (STUN/MSTURN)   |用於外部使用者存取 A/V 會話和媒體 (TCP)   |
|用戶端  |3478  |UDP (STUN/MSTURN)   |用於外部使用者存取 A/V 會話和媒體 (UDP)   |
|用戶端  |5061  |TCP (MTLS)   |用於外部使用者存取的用戶端對伺服器 SIP 流量。  |
|用戶端  |6891-6901  |TCP  |用於商務用 Skype 用戶端和舊版用戶端之間的檔案傳輸。  |
|用戶端  |1024-65535 \*  |TCP/UDP  |音訊埠範圍 (至少需要20個埠)   |
|用戶端  |1024-65535 \*  |TCP/UDP  |影片埠範圍 (至少需要20個埠) 。  |
|用戶端  |1024-65535 \*  |TCP  |對等檔案傳輸 (若為會議檔案傳輸，用戶端會使用 PSOM) 。  |
|用戶端  |1024-65535 \*  |TCP  |應用程式共用。  |
|Aastra 6721ip 公共區域電話  <br/> Aastra 6725ip 電話機  <br/> HP 4110 IP 電話 (公共區域電話)   <br/> HP 4120 IP 電話 (電話機)  <br/> Polycom CX500 IP 公共區域電話  <br/> Polycom CX600 IP 電話機  <br/> Polycom CX700 IP 服務台電話  <br/> Polycom CX3000 IP 會議電話  |67/68  |DHCP  |由所列裝置使用以尋找商務用 Skype Server 憑證、布建 fqdn 和註冊機 FQDN。  |
   
\* 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 及 ClientMediaPortRange 參數) 。
  
> [!NOTE]
> 商務用 Skype 用戶端的安裝程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。 

> [!NOTE]
> 在用戶端必須透過組織的防火牆 (的任何情況下（例如，其他組織所主控的外部通訊或會議) ），都需要用於外部使用者存取的埠。 
  
## <a name="ipsec-exceptions"></a>IPsec 例外狀況

針對網際網路通訊協定安全性 (IPsec)  (的商業網路請參閱 IETF RFC 4301-4309) 已部署，IPsec 必須透過用於傳遞音訊、影片及全景影片的埠範圍加以停用。 為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。
  
下表說明建議採用的 IPSec 例外設定。 
  
**建議的 IPsec 例外**

|規則名稱|來源 IP|目的地 IP|Protocol (通訊協定)|來源連接埠|目的地連接埠|驗證需求|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|A/V Edge Server (輸入的內部流量)  |任何  |A/V Edge Server (內部流量)  |UDP 和 TCP  |任何  |任何  |不驗證  |
|A/V Edge Server (輸入的外部流量)  |任何  |A/V Edge Server (外部流量)  |UDP 和 TCP  |任何  |任何  |不驗證  |
|A/V Edge Server (輸出的內部流量)  |A/V Edge Server (內部流量)  |任何  |UDP &amp; TCP  |任何  |任何  |不驗證  |
|A/V Edge Server (輸出的外部流量)  |A/V Edge Server (外部流量)  |任何  |UDP 和 TCP  |任何  |任何  |不驗證  |
|中繼伺服器 (輸入流量)  |任何  |調解  <br/> 伺服器 (s)   |UDP 和 TCP  |任何  |任何  |不驗證  |
|中繼伺服器 (輸出流量)  |調解  <br/> 伺服器 (s)   |任何  |UDP 和 TCP  |任何  |任何  |不驗證  |
|會議服務員 (輸入流量)  |任何  |執行會議服務員的前端伺服器  |UDP 和 TCP  |任何  |任何  |不驗證  |
|會議服務員 (輸出流量)  |執行會議服務員的前端伺服器  |任何  |UDP 和 TCP  |任何  |任何  |不驗證  |
|A/V 會議 (輸入流量)  |任何  |前端伺服器  |UDP 和 TCP  |任何  |任何  |不驗證  |
|A/V 會議 (輸出流量)  |前端伺服器  |任何  |UDP 和 TCP  |任何  |任何  |不驗證  |
|Exchange (輸入流量)  |任何  |Exchange Unified Messaging  |UDP 和 TCP  |任何  |任何  |不驗證  |
|應用程式共用伺服器輸入  |任何  |應用程式共用伺服器  |TCP  |任何  |任何  |不驗證  |
|應用程式共用伺服器輸出  |應用程式共用伺服器  |任何  |TCP  |任何  |任何  |不驗證  |
|Exchange (輸出流量)  |Exchange Unified Messaging  |任何  |UDP 和 TCP  |任何  |任何  |不驗證  |
|用戶端  |任何  |任何  |UDP  |指定的媒體連接埠範圍  |任何  |不驗證  |