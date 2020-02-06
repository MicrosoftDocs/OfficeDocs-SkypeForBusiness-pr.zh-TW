---
title: 設定 CUCM 以與商務用 Skype 伺服器進行交互操作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要：設定 CUCM 以搭配商務用 Skype 伺服器使用。
ms.openlocfilehash: 0f8b5321b482d78d9dc833471323ae842c247246
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798070"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>設定 CUCM 以與商務用 Skype 伺服器進行交互操作
 
**摘要：** 將 CUCM 設定為與商務用 Skype 伺服器搭配使用。
  
> [!CAUTION]
> 這個功能是透過 Cisco 整合通訊管理員（CallManager 或 CUCM）版本10.5 使用 Trunks 安裝程式（僅限 TCP）來測試。 在繼續之前，請確認 CUCM 環境符合這些準則。 
  
此處所述的設定僅做為如何設定 CUCM 以搭配 VIS 使用的範例。 您也可以使用替代 CUCM 功能的其他設定和/或用法來達到相同的結果。 針對特定案例，不建議使用最佳配置。
  
若要與 VIS 進行交互操作，必須確認或變更許多 CUCM 設定。 請依照下列程式來避免遺失必要的設定。
  
### <a name="configure-the-cucm"></a>設定 CUCM

1. 登入 CUCM 並流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>控制\>分區的類別。
    
2. 在 [分區配置] 畫面中，輸入分區名稱和描述，然後按一下 [**新增**]。
    
3. 流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>控制\>呼叫搜尋空間的類別。
    
4. 在 [呼叫搜尋空間設定] 畫面中，輸入通話搜尋空間的名稱，然後在 [選取的磁碟分割] 中輸入您剛建立的磁碟分割名稱。 完成後，按一下 [**儲存**]。
    
5. 流覽至 Cisco 一體化 CM 管理-\>系統\>安全性-\>SIP 主幹安全設定檔。
    
6. 在 [SIP 中繼安全設定檔設定] 畫面中，設定 SIP 中繼安全設定檔資訊選項，如所示，然後按一下 [**新增**]。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |名稱  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |裝置安全模式  <br/> |不安全  <br/> |
   |傳入傳輸類型  <br/> |TCP + UDP  <br/> |
   |外寄運輸類型  <br/> |TCP-OUT  <br/> |
   |入站埠  <br/> |5060  <br/> |
   
7. 流覽至 Cisco 整合 CM 管理-\>裝置-\>裝置設定-\>SIP 設定檔。
    
8. 在 [SIP 設定檔設定] 畫面中，設定 SIP 設定檔資訊選項，如所示。 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |名稱  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |說明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 在同一個畫面上，向下滾動至 SDP 設定檔資訊區段。 [**早期方案] 和 [重新邀請] 選項的 SDP 工作階段層級頻寬修正**程式預設會設定為 TIAS 和 AS。 將此選項變更為 [僅供 TIAS]。 如果您保留此選項的預設設定，商務用 Skype 伺服器將無法瞭解 SIP 訊息中的頻寬修正資訊。 TIAS 代表特定的傳輸獨立應用程式，而不是指特定應用程式。 這些是在 RFC3890 中指定的 SIP 選項。
    
10. 在同一個畫面上，進一步向下滾動。 在 SIP 設定檔的 [中繼專用設定] 底下，選取 [**提供語音及視頻通話的早期支援**]，將它設為 [必要**時插入 MTP** ] 選項。 這會讓 CUCM 使用早期優惠設定傳出 SIP 通話。 CUCM 8.5 中的一項新功能是支援不需要媒體端接點（MTP）的撥出電話設定與早期優惠。
    
11. 確認在 [SIP 選項] [ping] 區段中，選取 [啟用選項 Ping 以監視 Trunks 的目的地狀態] 旁邊的方塊，然後服務類型為「無（預設）」。」
    
12. 完成後，請按一下 [**新增**]。
    
13. 流覽至 Cisco 一體化 CM 管理-\>裝置-\>幹線。 
    
14. 將裝置通訊協定設定為 SIP，然後按 **[下一步]**。
    
15. 在 [裝置資訊] 底下，設定裝置名稱和描述（可能是 SfBVideoInterop_SIPTrunk 的內容），並將媒體資源群組清單設定為包含合適媒體資源的 MRGL。 
    
16. 進一步向下滾動。 如果視頻通話沒有取消核取，就不需要媒體端接點（MTP），請取消核取。 選取 [**在所有使用中整合的 CM 節點上執行**] 選項。 請注意，您應該將所有 CUCM 節點新增至商務用 Skype 伺服器設定。
    
17. 進一步向下滾動。 設定 [撥入通話] 和 [連線的通訊錄設定] 選項，如所示。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |呼叫搜尋空間 AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |已連線的參與方轉換 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 進一步向下滾動。 在 SIP 中繼設定的 [SIP 資訊目標] 區段底下，指定 VIS 池的 FQDN 或池中個別 VIS 伺服器的 IP 位址（新增多個專案）。 在 [目的地埠] 中，指定 VIS 正在接聽的埠，以取得從 CUCM 的連線（預設值為6001）。 另外，請指定您先前建立的 SIP 幹線安全設定檔和 SIP 設定檔，如所示。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |SIP 中繼安全設定檔  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |重新路由呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |[離開] 對話方塊請參閱呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |訂閱通話搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 設定檔  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 信號方法  <br/> |RFC 2833  <br/> |
   
19.  進一步向下滾動。 根據您的系統設定錄製資訊。 您可以將它設為 [**無**]。 
    
20. 完成後，請按一下 [**新增**]。
    
21. 流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>路由/查尋\>路由模式。
    
22. 在 [路由模式設定] 畫面中，輸入如下所示的模式定義參數。 向下滾動至 [呼叫方轉換] 區段，並設定遮罩，如圖所示，然後按一下 [完成時**新增**]。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |路線模式  <br/> |7779999  <br/> |
    |路由分區  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |說明  <br/> |SfBVideoInterop 的磁碟分割  <br/> |
    |閘道/路由清單  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |已呼叫參與方轉換遮罩  <br/> |+ 14257779999  <br/> |
   
23. 流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>SIP 路由模式。
    
24. 在 [SIP 路由模式設定] 畫面中，設定 [模式定義] 選項，如圖所示，然後按一下 [**新增**]。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    | 模式用法 <br/> |網域路由  <br/> |
    |IPv4 模式  <br/> |contoso.com （如果使用 IPv6，請保留空白）  <br/> |
    |IPv6 模式  <br/> |contoso.com （如果使用 IPv4，則留空）  <br/> |
    |說明  <br/> |SIPRoute 模式至 mediarv  <br/> |
    |路由分區  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 幹線/路由清單  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |[封鎖模式] 核取方塊  <br/> |保持未選取狀態  <br/> |
   
25. 如果您已從預設設定變更音訊或影片位元速率，您必須將它們傳回預設值。 若要設定音訊/視頻通話的位元速率，請流覽至 Cisco 一體化 CM 管理\>-系統\>區域資訊\>區域。 預設值如下所示：
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |地區  <br/> |設置  <br/> |
    |音訊編解碼器喜好設定清單  <br/> |系統預設值  <br/> |
    |音訊位元速率上限  <br/> |64 kbps （722，711）  <br/> |
    |針對視頻通話的最大會話位元速率  <br/> |200000 kbps  <br/> |
    |會話位元速率上限  <br/> |2000000000 kbps  <br/> |
   
此時，CUCM 視頻閘道設定為與 VIS 搭配使用。 相對應的設定將需要在您想要整合的每個 VTC 上執行。
> [!NOTE]
> 若要改善復原能力，您可能會想要將此 CUCM 閘道設定為使用第二個視頻交互操作伺服器或 VIS 池來運作。 如需詳細資訊，請參閱[復原機制](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
## <a name="see-also"></a>另請參閱

[設定與商務用 Skype 伺服器交互操作的 VTC](configure-a-vtc-for-interoperation.md)
