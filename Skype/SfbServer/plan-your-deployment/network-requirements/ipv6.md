---
title: 規劃商務用 Skype 中的 IPv6
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：在安裝商務用 Skype Server 之前，請先執行 IPv6。
---

# <a name="plan-for-ipv6-in-skype-for-business"></a>規劃商務用 Skype 中的 IPv6
 
**總結：** 在安裝商務用 Skype Server 之前，請先執行 IPv6。
  
商務用 Skype Server 包括支援 ip 版本 6 (IPv6) 位址，以及的 ip 版本 4 (IPv4) 位址的支援。 

IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。 由於世界各地的裝置數目不斷增加，所以可用的 IPv4 位址已用盡。因此，許多新裝置會移至使用 IPv6 位址。 IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。 這不僅提供全新的一組位址，也提供更多的位址數目。 

一般 IPv4 位址的外觀類似如下：192.0.2.235；而 IPv6 位址的外觀如下：2001:0db8:85a3:0000:0000:8a2e:0370:7334。 在您的商務用 Skype Server 安裝中，使用 IPv6 位址之裝置的格式設定和功能變更需要數個部署和設定考慮。 

本主題包含下列各節：
  
- [IP 位址類型的概述](ipv6.md#over)
    
- [IPv6 的技術需求](ipv6.md#tech)
    
- [IPv6 的遷移和共存考慮](ipv6.md#migration)
    
如果您決定要使用 IPv6 位址，請參閱[設定商務用 Skype 文章中的 IP 位址類型](ip-address-types.md)。
  
## <a name="overview-of-ip-address-types"></a>IP 位址類型的概述
<a name="over"> </a>

在商務用 Skype Server 中設定 IP 位址時，您有三個選項。 您可以將商務用 Skype Server 設定為僅支援 ip 版本 4 (IPv4) 、只 ip 版本 6 (IPv6) ，或是 (稱為雙重堆疊) 的組合。 每種類型的設定都有幾個考慮事項：
  
- **僅 IPv4** 因為世界用完了 IPv4 位址，所以已建立 IPv6。 最後，我們會完全支援全球的 IPv6，但目前，您的企業可能需要與其通訊的許多公司和裝置都不支援 IPv6，而且可能不是一段時間。 僅限 IPv4 的設定會協助確保您的商務用 Skype Server 實施可以與大多數的現有裝置通訊。
    
- **僅 IPv6** 相反地，完整的 IPv6 執行將會排除與許多現有裝置的通訊。
    
- **雙重堆疊** 雙堆疊是一種同時啟用 IPv4 和 IPv6 位址的網路。 在商務用 Skype Server 中支援此設定，因為在大多數情況下，從完整 IPv4 轉換為完整 IPv6 會需要數年。
    
下列各節將三個設定的相容性概括在各種商務用 Skype Server 功能中。
  
> [!NOTE]
> 只有實驗室或驗證目的才支援用戶端或伺服器設定只支援 IPv6。 在實際執行部署中，不支援只有設定 IPv6。 
  
### <a name="client-registration"></a>用戶端註冊
<a name="client"> </a>

|**用戶端端點網路**|**伺服器網路**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |雙重堆疊  <br/> |
|雙重堆疊  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |
|雙重堆疊  <br/> |IPv6  <br/> |
|IPv6  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Peer-to-Peer 用戶端
<a name="peer"> </a>

對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。 這兩個用戶端都成功註冊後，支援下列組合。
  
|**用戶端端點1**|**用戶端端點2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |雙重堆疊  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>會議
<a name="conf"> </a>

會議包含音訊/視頻、應用程式共用和資料共同作業應用程式（如白板和檔案共用）。
  
|**用戶端端點網路**|**伺服器網路**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |雙重堆疊  <br/> |
|雙重堆疊  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |
|雙重堆疊  <br/> |IPv6  <br/> |
|IPv6  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>轉送伺服器/PSTN
<a name="med"> </a>

商務用 Skype Server 不支援公用交換電話網路 (PSTN) 通話的媒體旁路，如果流量是透過 IPv6 介面。 如果需要媒體旁路，建議將 PSTN 閘道設定為 IPv4。 
  
|**主要介面1**|**轉送伺服器上的 PSTN 介面 ()**|**PSTN 閘道設定**|
|:-----|:-----|:-----|
|IPv4  <br/> |雙重堆疊  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |IPv6  <br/> |
   
1. 主要介面是與商務用 Skype Server 元件通訊的介面。
  
### <a name="remote-user-peer-to-peer-communications"></a>遠端使用者 Peer-to-Peer 通訊
<a name="remote"> </a>

與遠端使用者的對等通訊包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。
  
|**遠端使用者網路**|**Edge server (外部 edge)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |IPv4  <br/> |
|雙重堆疊  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |雙重堆疊  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>前端集區和 Edge 集區設定
<a name="FE_pool"> </a>

下表顯示前端伺服器集區和內部 Edge Server 集區之間的支援矩陣。
  
**前端集區和 Edge 集區 (內部 Edge) 矩陣**

||**Edge 集區： IPv4** <br/> |**Edge 集區：雙堆疊** <br/> |**Edge 集區： IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**前端集區： IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前端集區：雙棧** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前端集區： IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\* 僅在實驗室環境中使用此組合。
  
下表是支援的內部和外部 edge 介面組合的矩陣。
  
**Edge 集區 (內部 Edge) 和 Edge 集區 (外部 Edge) 矩陣**

||**Edge 集區 (外部 Edge) ： IPv4** <br/> |**Edge 集區 (外部 Edge) ：雙堆疊** <br/> |**Edge 集區 (外部 Edge) ： IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edge 集區 (內部 Edge) ： IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**Edge 集區 (內部 Edge) ：雙堆疊** <br/> |否  <br/> |是  <br/> |否  <br/> |
|**Edge 集區 (內部 Edge) ： IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\* 僅在實驗室環境中使用此組合。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 的高級企業語音支援
<a name="Ent_V"> </a>

包含通話許可控制的部署 (CAC) 、增強型 9-1-1 (E9-1-1) 或媒體旁路，都必須設定為 IPv4 或雙堆疊式的執行。 僅使用 IPv6 的端點無法使用這些功能。
  
> [!NOTE]
> 在雙堆疊部署中，即使商務用 Skype Server 用戶端使用 IPv6 連接至商務用 Skype Server，商務用 Skype Server 還是會盡力對應適當的 IPv4 位址，以支援 E9-1-1。 
  
不支援使用 IPv6 位址的位置資訊服務。
  
Exchange 整合通訊 (UM) 不支援 IPv6。 若為 Exchange UM，請確定 DNS 解析不會傳回 IPv6 位址。 在來電傳送至語音信箱時，使用 IPv6 可能會造成失敗。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6 的其他商務用 Skype Server 功能支援
<a name="Ent_V"> </a>

除了先前提及的功能和元件之外，商務用 Skype Server 還支援 IPv6 下列功能：
  
- **常設聊天室**
    
    您可以使用拓撲產生器，設定持續聊天的 IPv6。 如需設定持續性聊天的詳細資訊，請參閱部署 Persistent Chat Server 檔。
    
- **經驗品質 (QoE) 和詳細通話記錄 (CDR) 報告**
    
    監控報告包含的 IP 位址會儲存在監控伺服器資料庫中，不論其類型是 IPv4 還是 IPv6。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 的技術需求
<a name="tech"> </a>

如果您打算為 IPv6 設定商務用 Skype Server，請牢記下列需求：
  
- 若要使用商務用 Skype Server 的 IPv6 位址，您必須為必須探索並解析為 IPv6 位址的記錄，建立網域名稱系統 (DNS) 記錄。 IPv6 DNS 使用主機 AAAA (四 A) 記錄。 如果您在部署中同時使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和裝載 AAAA 記錄。 即使您完全將部署轉換為 IPv6，您仍然可能需要 IPv4 仍在使用 IPv4 的外部使用者的 DNS 主機記錄。
    
    您可以在開始使用 IPv6 之前，先部署 IPv6 的 DNS 主機記錄。 如果用戶端或伺服器不使用 IPv6，將不會參照記錄。 過渡技術會根據轉換技術設定和原則，決定要使用哪個記錄。
    
- 每個 IPv6 位址都有一個範圍。 您可以用於 IPv6 定址的三個範圍是 IPv6 的全域位址 (類似公用 IPv4 位址) 、IPv6 唯一本機位址 (類似專用 IPv4 位址範圍) ，以及 IPv6 連結本機位址 (類似 Windows Server 中 IPv4) 的自動私人 IP 位址。 集區中的所有伺服器都應有相同範圍的 IPv6 位址。 
    
> [!IMPORTANT]
> IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以協助確保您在 Windows 伺服器層級和商務用 Skype Server 層級所指派的位址如預期的那樣運作。 請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 的遷移和共存考慮
<a name="migration"> </a>

Lync Server 2010 或 Office 通訊伺服器上不支援 IP 版本 6 (IPv6) 。 出於試驗目的，您可以測試 Lync Server 2010 和商務用 Skype Server 雙堆疊共存。 建議您先將指定中央網站的所有集區升級為商務用 Skype Server，然後再為任何集區啟用 IPv6 (雙堆疊網路) 。 [！附注] 如果您只需要為 IPv6 設定集區，建議您在實驗室環境中設定 IPv6 專用集區以進行測試。
  
在遷移和共存期間支援下列案例：
  
- IPv4 模式中的商務用 Skype Server、lync server 2013 和 lync server 2010 集區，與雙堆疊模式中商務用 Skype Server 共存。
    
- 在僅限 IPv6 模式中商務用 Skype Server 集區（如果 IPv6 為孤立的集區）。
    
## <a name="see-also"></a>另請參閱
<a name="migration"> </a>

[設定商務用 Skype 中的 IP 位址類型](ip-address-types.md)

[IP 版本6定址架構](https://tools.ietf.org/html/rfc4291)
  
[IPv6 全域單路廣播位址格式](https://tools.ietf.org/html/rfc3587)
  
[唯一的本地 IPv6 單播位址](https://tools.ietf.org/html/rfc4193)
