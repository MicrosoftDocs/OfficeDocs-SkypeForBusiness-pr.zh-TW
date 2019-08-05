---
title: 設定與商務用 Skype 伺服器交互操作的 VTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '摘要: 設定 VTC 裝置以搭配商務用 Skype 伺服器使用。'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193463"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>設定與商務用 Skype 伺服器交互操作的 VTC
 
**摘要:** 將 VTC 裝置設定為與商務用 Skype 伺服器搭配使用。
  
您必須針對將透過 SIP 幹線與 Cisco 整合通訊管理員 (CallManager 或 CUCM) 視頻閘道連線到商務用 Skype VIS 伺服器的每個 VTC, 執行下列設定自訂程式。
  
此處所述的設定僅做為如何設定 CUCM 以搭配 VIS 使用的範例。 您也可以使用替代 CUCM 功能的其他設定和/或用法來達到相同的結果。 針對特定案例, 不建議使用最佳配置。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>設定註冊至 CUCM 的 VTC

1. 登入 Cisco VTC 裝置, 然後流覽至 [配置-\>系統設定]\>-[設定]。
    
2. 確認下列設定, 視需要修正: 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |預配模式  <br/> | CUCM <br/> |
   |ExternalManager 位址  <br/> | CUCM 的 FQDN <br/> |
   | ExternalManager 網域 <br/> |CUCM 的網域  <br/> |
   
3. 流覽至 [配置\>-系統設定\>-網路]。
    
4. 確認下列設定, 視需要修正: 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |DNS 功能變數名稱  <br/> | CUCM 的網功能變數名稱稱 <br/> |
   |DNS 伺服器1位址  <br/> | 您想要的 DNS 伺服器位址 <br/> |
   
5. 流覽至 [配置\>-系統設定\>-網路服務]。 確定已關閉 H-323 模式, 且已開啟 SIP 模式。 
    
6. 當端點註冊至 CUCM 時, 這些選項會自動設定。 確認下列設定, 視需要修正: 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |H. 323 Mode  <br/> | 出 <br/> |
   |HTTP 模式  <br/> | 按 <br/> |
   | SIP 模式 <br/> | 按 <br/> |
   |Telnet 模式  <br/> | 按 <br/> |
   |WelcomeText  <br/> | 按 <br/> |
   |XMLAPI 模式  <br/> | 按 <br/> |
   
7. 流覽至 [配置\>-系統設定\>-SIP]。
    
8. 確認下列設定, 視需要修正: 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |設定檔 1-DefaultTransport  <br/> | TCP-OUT <br/> |
   |設定檔 1-輸出  <br/> | 出 <br/> |
   |設定檔 1-TlsVerify  <br/> | 按 <br/> |
   |設定檔 1-類型  <br/> | Cisco <br/> |
   |設定檔 1-URI  <br/> | 在 CUCM 註冊時自動指派 <br/> |
   |Proxy 1-位址  <br/> |CUCM 的主機名稱  <br/> |
   
VTC 現在已針對互用性進行設定。 在服務開始之前, 請先在 CUCM 端執行最後一個步驟。
### <a name="configure-vtc-devices-on-cucm"></a>在 CUCM 上設定 VTC 裝置

1. 登入 CUCM 並流覽至 Cisco 一體化 CM 管理-\>裝置-\>電話-\>尋找。 
    
2. 選取要設定的 VTC 裝置。 確認 [電話設定] 畫面上的下列設定, 並視需要修正。 變更或驗證這些設定之後, 按一下 [**儲存**]。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |裝置資訊-電話按鈕範本  <br/> | 標準 Cisco Telepresence 編解碼器 C40 <br/> |
   |裝置資訊-常用的電話設定檔  <br/> | 標準常用電話設定檔 <br/> |
   |裝置資訊-呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置資訊-AAR 通話搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置資訊-媒體資源群組清單  <br/> | MRGL_SfBVideoInterop <br/> |
   |通訊協定的特定資訊-裝置安全設定檔  <br/> | Cisco Telepresence 編解碼器 C40 <br/> |
   |通訊協定特定資訊-重新路由呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |通訊協定的特定資訊-訂閱通話搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |通訊協定的特定資訊-SIP 設定檔  <br/> | Telepresence 端點的標準 SIP 設定檔 <br/> |
   
3. 儲存 VTC 設定之後, 請重新流覽裝置的 [電話設定] 畫面。 在畫面頂端的 [關聯] 群組中, 按一下影片交互操作的關聯。 這會顯示 [目錄號碼設定] 畫面。 
    
4. 確認下列設定, 視需要修正: 
    
    根據目錄號碼資訊和目錄編號設定, 進行適當的變更。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   | 目錄號碼資訊-路由分區 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |目錄號碼設定-呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 備用方及機密存取層級設定-MLPP 呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置上的第1行 (本機號碼)  <br/> | 視需要 <br/> |
   |裝置上的第1列-ASCII 顯示 (來電者識別碼)  <br/> | 視需要 <br/> |
   
5. 完成後, 請滾動至畫面頂端, 然後按 [**儲存**]。 
    
此 VTC 裝置的設定現已完成。 您將需要針對企業中的其他 VTC 裝置重複此程式。

