---
title: 設定 CUCM 以與商務用 Skype Server 進行交互操作
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要：設定 CUCM 以使用商務用 Skype Server。
ms.openlocfilehash: 2e5e2cfc207fd9c4e52f7cd4da553dc756fddb4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863090"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>設定 CUCM 以與商務用 Skype Server 進行交互操作
 
**摘要：** 設定 CUCM 以使用商務用 Skype Server。
  
> [!CAUTION]
> 這項功能是透過 Cisco 整合通訊管理員 (CallManager，或是 CUCM) 版本10.5，只使用主幹安裝 over TCP 進行測試。 在繼續之前，請確認 CUCM 環境符合這些準則。 
  
這裡所述的設定只是 CUCM 如何設定為搭配 VIS 使用的範例。 其他設定和/或替代 CUCM 功能的使用方式也可以用來達到相同的結果。 不建議使用特定案例的最佳設定。
  
若要與 VIS 進行交互操作，必須確認或變更 CUCM 設定的數目。 請遵循下列程式，以避免遺失必要的設定。
  
### <a name="configure-the-cucm"></a>設定 CUCM

1. 登入 CUCM 並流覽至 Cisco 統一 CM 管理- \> 呼叫路由 \> 類別的控制 \> 分割區。
    
2. 在 [磁碟分割設定] 畫面中，輸入磁碟分割名稱和描述，然後按一下 [ **新增**]。
    
3. 流覽至 Cisco 統一 CM 管理- \> 呼叫路由 \> 類別的 Control- \> 呼叫搜尋空間。
    
4. 在 [呼叫搜尋空間設定] 畫面中，輸入呼叫搜尋空間的名稱，然後在 [選取的磁碟分割] 中輸入剛才建立之磁碟分割的名稱。 完成後，按一下 [ **儲存** ]。
    
5. 流覽 Cisco 統一 CM 管理- \> 系統 \> 安全性- \> SIP 主幹安全性設定檔。
    
6. 在 [SIP 主幹安全性設定檔設定] 畫面中，設定 SIP 主幹安全性設定檔資訊選項（如圖所示），然後按一下 [ **新增**]。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |名稱  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |裝置安全性模式  <br/> |不安全  <br/> |
   |傳入傳輸類型  <br/> |TCP + UDP  <br/> |
   |外寄傳輸類型  <br/> |TCP  <br/> |
   |傳入埠  <br/> |5060  <br/> |
   
7. 流覽 Cisco 統一 CM 管理- \> 裝置- \> 裝置設定 \> SIP 設定檔。
    
8. 在 [SIP 設定檔設定] 畫面中，設定 SIP 設定檔資訊選項（如圖所示）。 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |名稱  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |描述  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 在同一個畫面上，向下滾動至 [SDP 設定檔資訊] 區段。 「 **早期提供」和「重新邀請」選項的 SDP 工作階段層級頻寬修正** 程式預設會設定為 TIAS 和 AS。 將此選項改為 [僅限 TIAS]。 如果您保留此選項的預設值，商務用 Skype Server 將不會瞭解 SIP 郵件中的頻寬修正資訊。 TIAS 表示特定的傳輸獨立應用程式，也就是應用程式特定的應用程式。 這些是 RFC3890 中指定的 SIP 選項。
    
10. 在同一個畫面上，再向下滾動。 在 [SIP 設定檔的主幹特定設定] 底下，選取 [ **為語音和影片通話預先提供支援** ]，並將其設定為 **強制 (在必要時插入 MTP)** ] 選項。 這可讓 CUCM 使用早期的提供來設定外寄的 SIP 呼叫。 CUCM 8.5 中的一項新功能是支援外寄通話設定，但不需要 (MTP) 的媒體終止點。
    
11. 確認在 [SIP 選項 ping] 區段中，選取 [啟用選項 Ping 以監視目標狀態的主幹，且服務類型為 ' None (預設) '] 核取方塊。
    
12. 完成後，按一下 [ **新增**]。
    
13. 流覽 Cisco 統一 CM 管理- \> 裝置- \> 主幹。 
    
14. 將裝置通訊協定設定為 SIP，然後按 **[下一步]**。
    
15. 在 [裝置資訊] 底下，將裝置名稱和描述設定 (可能是 SfBVideoInterop_SIPTrunk) 之類的專案，並將媒體資源群組清單設為包含適當媒體資源的 MRGL。 
    
16. 進一步向下方滾動。 不需要 (MTP) 的媒體終止點，如果尚未取消核取，請將其取消勾選。 請選取在所有使用中的 **整合 CM 節點上執行** 的選項。 請注意，您應該將所有的 CUCM 節點新增至商務用 Skype Server 設定。
    
17. 進一步向下方滾動。 如圖所示，設定來電和連接方設定選項。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |呼叫搜尋空間 AAR  <br/> |CSS_SfBVideoInterop  <br/> |
    |連接的當事方轉換 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 進一步向下方滾動。 在 SIP 主幹設定的 [SIP 資訊目的] 區段中，指定 VIS 集區的 FQDN 或集區中個別 VIS 伺服器的 IP 位址 (新增多個專案) 。 在 [目的地埠] 中，指定 VIS 正在接聽的埠，以供來自 CUCM 的連線 (預設值為 6001) 。 此外，請指定您先前建立的 SIP 主幹安全性設定檔和 SIP 設定檔（如圖所示）。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |SIP 主幹安全性設定檔  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |重新路由呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |對話方塊外參考呼叫搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |訂閱通話搜尋空間  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 設定檔  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 信號方法  <br/> |RFC 2833  <br/> |
   
19.  進一步向下方滾動。 視您的系統設定記錄資訊。 將其保留為 [ **無**] 是很好的方式。 
    
20. 完成後，按一下 [ **新增**]。
    
21. 流覽至 Cisco 統一 CM 管理- \> 通話路由 \> 傳送/尋找路由 \> 模式。
    
22. 在 [路由模式設定] 畫面中，輸入如下所示的模式定義參數。 向下滾動至「所叫的協力廠商轉換」區段，然後設定遮罩為 [已顯示]，然後在完成時按一下 [ **新增** ]。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |路由模式  <br/> |7779999  <br/> |
    |路由分割區  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |描述  <br/> |SfBVideoInterop 的分割區  <br/> |
    |閘道/路由清單  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |呼叫方轉換遮罩  <br/> |+ 14257779999  <br/> |
   
23. 流覽至 Cisco 統一 CM 管理- \> 呼叫路由- \> SIP 路由模式。
    
24. 在 [SIP 路由模式設定] 畫面中，設定 [模式定義] 選項（如圖所示），然後按一下 [ **新增**]。
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    | 模式用法 <br/> |網域路由  <br/> |
    |IPv4 模式  <br/> |使用 IPv6 時，contoso.com (留下空白)   <br/> |
    |IPv6 模式  <br/> |使用 IPv4 時，contoso.com (留下空白)   <br/> |
    |描述  <br/> |SIPRoute 到 mediarv 的模式  <br/> |
    |路由分割區  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 主幹/路由清單  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |封鎖模式] 核取方塊  <br/> |保留未勾選  <br/> |
   
25. 如果您已從預設設定變更音訊或影片位元速率，您必須將其恢復為預設值。 若要設定 Audio/Video 通話的位元速率，請流覽至 Cisco 統一 CM 管理- \> 系統- \> 地區資訊- \> 地區。 預設值如下所示：
    
    |**參數**|**建議的設定**|
    |:-----|:-----|
    |區域  <br/> |預設  <br/> |
    |音訊編解碼器偏好清單  <br/> |系統預設值  <br/> |
    |音訊位元速率上限  <br/> |64 kbps (g.722，g.711)   <br/> |
    |影片通話的最長會話位元速率  <br/> |200000 kbps  <br/> |
    |會話位元速率上限  <br/> |2000000000 kbps  <br/> |
   
此時，CUCM 影片閘道已設定為搭配 VIS 使用。 在您想要整合的每個 VTC 中，都需要進行對應的設定。
> [!NOTE]
> 若要改善復原能力，您可以設定此 CUCM 閘道，以與第二個影片交互操作伺服器或 VIS 集區搭配使用。 如需詳細資訊，請參閱 [恢復機制](../../plan-your-deployment/video-interop-server.md#resiliency) 。
  
## <a name="see-also"></a>另請參閱

[設定 VTC 以與商務用 Skype Server 進行交互操作](configure-a-vtc-for-interoperation.md)
