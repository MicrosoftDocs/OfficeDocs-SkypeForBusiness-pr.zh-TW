---
title: 商務用 Skype Server 中的行動效能計數器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 摘要：瞭解您可以用來監視執行整合通訊 Web API (UCWA) 和商務用 Skype Server Mcx 行動性服務之伺服器的效能計數器。
ms.openlocfilehash: 157417d7a0cbc8db2a94ecba18f984b3eedde043
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384261"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>商務用 Skype Server 中的行動效能計數器
 
**總結：** 瞭解您可以用來監視執行整合通訊 Web API (UCWA) 和商務用 Skype Server Mcx 行動性服務之伺服器的效能計數器。
  
下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊網頁 API (UCWA) 和商務用 Skype Server Mcx 行動性服務的伺服器。 
  
UCWA 資料表中的計數器類別名稱是 **LS： WEB UCWA**。
  
Mcx 行動性服務表格中的計數器類別名稱是 **LS： WEB Mobile Communication service**。

> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
  
## <a name="performance-counters-for-ucwa"></a>UCWA 的效能計數器

|計數器|描述|
|:-----|:-----|
|使用中應用程式計數  <br/> |目前的應用程式數目  <br/> |
|使用中應用程式共用的形式計數  <br/> |目前的應用程式共用形式數目  <br/> |
|使用中音訊的模態計數  <br/> |目前的音訊模態數目  <br/> |
|主動資料共同作業模式計數  <br/> |目前的資料共同作業數目  <br/> |
|Active Directory 照片取得延遲 (毫秒)   <br/> |此計數器會顯示從 active directory 中取得相片的平均 (（毫秒）)   <br/> |
|使用中的郵件模式計數  <br/> |目前的郵件模態模式數目  <br/> |
|使用中全景影片的模式計數  <br/> |目前的全景影片形式數目  <br/> |
|作用中擱置的取得計數  <br/> |目前使用中擱置的取得數目;保留伺服器的長時間連接  <br/> |
|主動會話計數  <br/> |UCWA 中每個應用程式和總數所註冊的端點數目  <br/> |
|作用中使用者實例計數  <br/> |目前的使用者實例數目  <br/> |
|不含應用程式的作用中使用者實例  <br/> |目前沒有 application 的使用者實例數目  <br/> |
|使用中影片的模態計數  <br/> |目前影片的模態數目  <br/> |
|每秒收到的應用程式建立要求  <br/> |每秒收到應用程式建立要求的速率  <br/> |
|作為 MCU 加入失敗  <br/> |作為 MCU 加入失敗的數目  <br/> |
|AV MCU 加入失敗  <br/> |AV MCU 加入失敗的次數  <br/> |
|平均應用程式啟動時間 (毫秒)   <br/> |應用程式的平均啟動時間（毫秒）  <br/> |
|會話的平均壽命 (毫秒)   <br/> |會話的平均生命週期（毫秒）  <br/> |
|資料 MCU 加入失敗  <br/> |資料 MCU 加入失敗次數  <br/> |
|Exchange 連絡人搜尋延遲 (毫秒)   <br/> |此計數器會顯示在 Exchange 中搜尋連絡人的平均時間 (（毫秒）)   <br/> |
|Exchange HD 相片取得延遲 (毫秒)   <br/> |此計數器會顯示從 Exchange 中) 取得照片的平均時間 (（毫秒）  <br/> |
|HTTP 4xx 回應數/秒  <br/> |每秒以 HTTP 4xx 代碼回應的速率  <br/> |
|HTTP 5xx 回應數/秒  <br/> |每秒以 HTTP 5xx 代碼回應的速率  <br/> |
|IM MCU 聯接失敗  <br/> |IM MCU 加入失敗的次數  <br/> |
|Active Directory 照片取得失敗的數目  <br/> |從 Active Directory 中取得相片的失敗總數  <br/> |
|連絡人搜尋失敗次數  <br/> |在 Exchange 中搜尋連絡人的失敗總數  <br/> |
|反序列化失敗次數  <br/> |反序列化失敗總數  <br/> |
|HD 相片 Get 失敗次數  <br/> |從 Exchange 取得 HD 相片的失敗總次數  <br/> |
|每個應用程式的最大訂閱數  <br/> |每個應用程式允許的最大訂閱要求數目  <br/> |
|每個批次的最大訂閱數  <br/> |每個批次允許的訂閱要求數目上限  <br/> |
|目前狀態訂閱失敗  <br/> |訂閱目前狀態失敗的次數  <br/> |
|註冊端點失敗  <br/> |註冊端點的失敗次數  <br/> |
|接收的要求數/秒  <br/> |每秒收到要求的速率  <br/> |
|每秒成功的要求  <br/> |每秒成功要求 (HTTP 2xx/3xx 回應碼的速率)   <br/> |
|成功建立應用程式 Requests/Second  <br/> |每秒成功的應用程式建立要求速率  <br/> |
|超時等候中的取得計數  <br/> |超時的擱置取得數目  <br/> |
|已接收的應用程式建立要求總數  <br/> |啟動服務後收到的應用程式建立要求總數  <br/> |
|HTTP 4xx 回應總數  <br/> |HTTP 4xx 回應總數  <br/> |
|HTTP 5xx 回應總數  <br/> |HTTP 5xx 回應總數  <br/> |
|命令通道上接收的要求總數  <br/> |命令通道上接收的要求總數  <br/> |
|成功的要求總數  <br/> |成功的要求總數  <br/> |
|起始的會話總數  <br/> |啟動服務後所初始化的會話總數  <br/> |
|因空閒超時而終止的會話總數  <br/> |因使用者空閒超時而終止的會話總數  <br/> |
|限制的應用程式總數  <br/> |節流應用程式的數目  <br/> |
   
**Mcx 行動性服務的效能計數器**

|**計數器**|**描述**|
|:-----|:-----|
|會話的平均生命週期（毫秒）  <br/> |會話的平均生命週期（毫秒）  <br/> |
|目前的推播通知訂閱  <br/> |推播通知訂閱的目前數目。 這個數目會與目前作用中的會話計數搭配使用，代表為 Windows 行動裝置或 iPhone 裝置註冊的目前作用中會話的子集。  <br/> |
|目前使用中的網路超時輪詢計數  <br/> |超時的網路輪詢數目  <br/> |
|目前使用中的輪詢計數  <br/> |目前使用中輪詢的數目 (長期保留與伺服器的連線)   <br/> |
|目前使用中的會話計數  <br/> |目前在行動服務中註冊的端點數目  <br/> |
|目前使用中的會話計數與使用中狀態訂閱  <br/> |目前使用中狀態訂閱的目前活動會話數目  <br/> |
|推播通知要求失敗/秒  <br/> |每秒失敗推播通知的速率  <br/> |
|每秒成功的推入通知要求  <br/> |每秒成功推播通知的速率  <br/> |
|限制的推播通知要求數/秒  <br/> |每秒節流推播通知的速率  <br/> |
|推播通知 Requests/Second  <br/> |每秒傳送推播通知的速率  <br/> |
|每秒失敗的要求  <br/> |每秒失敗要求的速率  <br/> |
|接收的要求數/秒  <br/> |每秒收到要求的速率  <br/> |
|拒絕的要求數/秒  <br/> |每秒拒絕要求的速率  <br/> |
|每秒成功的要求  <br/> |每秒成功要求的速率  <br/> |
|已成功啟動會話 Requests/Second  <br/> |每秒成功取得位置要求的速率。 啟動會話的要求會消耗伺服器上的大部分 CPU。 支援的負載峰值為 12/秒。 可持續性取決於伺服器上的其他負載。 [啟動會話] 通常表示登入的使用者已長時間簽入的使用者。  <br/> |
|拒絕的撥入語音通話總數  <br/> |已謝絕的撥入語音通話總數  <br/> |
|失敗的撥入語音通話總數  <br/> |失敗的撥入語音通話總數  <br/> |
|失敗的撥出語音通話總數  <br/> |失敗的撥出語音通話總數  <br/> |
|使用者終止的會話總數  <br/> |使用者終止的會話總數  <br/> |
|推播通知要求總數  <br/> |推播通知要求總數  <br/> |
|推播通知要求總數失敗  <br/> |失敗的推入通知要求總數  <br/> |
|已成功的推播通知要求總數  <br/> |成功的推播通知要求總數  <br/> |
|限制的推播通知要求總數  <br/> |已節流之推播通知要求的總數  <br/> |
|失敗的要求總數  <br/> |失敗的要求總數  <br/> |
|命令通道上接收的要求總數  <br/> |命令通道上接收的要求總數  <br/> |
|拒絕的要求總數  <br/> |拒絕的要求總數  <br/> |
|成功的要求總數  <br/> |已成功完成行動服務的總要求數  <br/> |
|會話起始計數總數  <br/> |啟動行動服務後所啟動的會話總數  <br/> |
|因使用者空閒超時而終止的會話總數  <br/> |因使用者空閒超時而終止的會話總數  <br/> |
|成功輸入語音通話總數  <br/> |輸入語音通話的成功總數  <br/> |
|成功的撥出語音通話總數  <br/> |已成功撥出語音通話的總數  <br/> |
   
> [!NOTE]
> 商務用 Skype Server 2019 不再提供舊版行動用戶端的 MCX (行動服務) 支援。 所有目前商務用 Skype 的行動裝置都已經使用整合通訊 Web API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。 具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。
