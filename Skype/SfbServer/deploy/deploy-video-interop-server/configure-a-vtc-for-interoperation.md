---
title: 設定 VTC 以與商務用 Skype Server 進行交互操作
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要：設定 VTC 裝置與商務用 Skype Server 搭配使用。
ms.openlocfilehash: 1165b4bf569701d71a435a4162ef9feb9ef3018f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594677"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>設定 VTC 以與商務用 Skype Server 進行交互操作
 
**摘要：** 設定 VTC 裝置與商務用 Skype Server 搭配使用。
  
您將需要針對透過 SIP 主幹和 Cisco 整合通訊管理員 (CallManager 或 CUCM) 的視頻閘道，來連接至商務用 Skype VIS server 的每個 VTC 執行下列設定自訂程式。
  
這裡所述的設定只是 CUCM 如何設定為搭配 VIS 使用的範例。 其他設定和/或替代 CUCM 功能的使用方式也可以用來達到相同的結果。 不建議使用特定案例的最佳設定。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>設定 VTC 註冊的 CUCM

1. 登入 Cisco VTC 裝置，並流覽至 [設定- \> 系統設定-布建] \> 。
    
2. 請確認下列設定，並視需要進行修正： 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |布建模式  <br/> | CUCM <br/> |
   |ExternalManager 位址  <br/> | CUCM 的 FQDN <br/> |
   | ExternalManager 網域 <br/> |CUCM 所在的網域  <br/> |
   
3. 流覽至 [設定- \> 系統設定- \> 網路]。
    
4. 請確認下列設定，並視需要進行修正： 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |DNS 功能變數名稱  <br/> | CUCM 的功能變數名稱 <br/> |
   |DNS 伺服器1位址  <br/> | 您想要的 DNS 伺服器位址 <br/> |
   
5. 流覽至 [設定- \> 系統設定- \> 網路服務]。 確定已關閉 H 323 模式，且已開啟 SIP 模式。 
    
6. 當端點已向 CUCM 註冊時，會自動設定這些選項。 請確認下列設定，並視需要進行修正： 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |上的323模式  <br/> | 關閉 <br/> |
   |HTTP 模式  <br/> | 開啟 <br/> |
   | SIP 模式 <br/> | 開啟 <br/> |
   |Telnet 模式  <br/> | 開啟 <br/> |
   |WelcomeText  <br/> | 開啟 <br/> |
   |XMLAPI 模式  <br/> | 開啟 <br/> |
   
7. 流覽至 [設定- \> 系統設定- \> SIP]。
    
8. 請確認下列設定，並視需要進行修正： 
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |設定檔 1-DefaultTransport  <br/> | TCP <br/> |
   |設定檔 1-輸出  <br/> | 關閉 <br/> |
   |設定檔 1-TlsVerify  <br/> | 開啟 <br/> |
   |設定檔 1-類型  <br/> | Cisco <br/> |
   |設定檔 1-URI  <br/> | 在 CUCM 註冊時自動指派 <br/> |
   |Proxy 1-位址  <br/> |CUCM 的主機名稱  <br/> |
   
VTC 現在已設定為交互操作。 在服務可以開始之前，請先在 CUCM 側執行一些最後的步驟。
### <a name="configure-vtc-devices-on-cucm"></a>在 CUCM 上設定 VTC 裝置

1. 登入 CUCM 並流覽至 Cisco 統一 CM 管理- \> 裝置- \> 電話- \> 找到。 
    
2. 選取要設定的 VTC 裝置。 在 [電話設定] 畫面上，確認下列設定，並視需要進行修正。 變更或驗證這些設定後，按一下 [ **儲存**]。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   |裝置資訊-電話按鈕範本  <br/> | 標準 Cisco Telepresence 編解碼器 C40 <br/> |
   |裝置資訊-通用電話設定檔  <br/> | 標準通用電話設定檔 <br/> |
   |裝置資訊-呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置資訊-AAR 呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置資訊-媒體資源群組清單  <br/> | MRGL_SfBVideoInterop <br/> |
   |通訊協定特定資訊-裝置安全性設定檔  <br/> | Cisco Telepresence 編解碼器 C40 <br/> |
   |通訊協定特定資訊-重新路由呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |通訊協定特定資訊-訂閱通話搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |通訊協定特定資訊-SIP 設定檔  <br/> | Telepresence 端點的標準 SIP 設定檔 <br/> |
   
3. 儲存 VTC 設定之後，請重新導覽裝置的「電話設定」畫面。 在 [關聯] 群組中的畫面頂端，按一下影片交互操作的關聯。 這會顯示 [目錄號碼] 設定畫面。 
    
4. 請確認下列設定，並視需要進行修正： 
    
    進行適當的變更，如目錄號碼資訊和目錄編號設定所示。
    
   |**參數**|**建議的設定**|
   |:-----|:-----|
   | 目錄號碼資訊-路由分割區 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |目錄號碼設定-呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 備選方和機密存取層級設定-MLPP 呼叫搜尋空間  <br/> | CSS_SfBVideoInterop <br/> |
   |裝置顯示幕上的第1列 (來電者識別碼)   <br/> | 視需要 <br/> |
   |裝置-ASCII 顯示幕上的第1列 (來電者識別碼)   <br/> | 視需要 <br/> |
   
5. 完成時，請滾到畫面的頂端，然後按 [ **儲存**]。 
    
現在已完成此 VTC 裝置的設定。 您將需要針對企業中的其他 VTC 裝置重複此程式。

