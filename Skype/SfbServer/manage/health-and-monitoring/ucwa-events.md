---
title: 在商務用 Skype Server 中 UCWA 事件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 摘要：瞭解商務用 Skype Server 中的整合通訊網頁 API （UCWA）。
ms.openlocfilehash: db6aee15564fe9fca05c33ec5a6dd37988195956
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817622"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>在商務用 Skype Server 中 UCWA 事件
 
**摘要：** 瞭解商務用 Skype Server 中的整合通訊網頁 API （UCWA）。
  
商務用 Skype Server 會使用整合通訊 Web API （UCWA）來實現多種用途，從存取 Microsoft Exchange 進行連絡人搜尋，以更新行動用戶端的目前狀態。
  
UCWA 會將操作行為的記錄寫入為事件種類的資訊、警告和錯誤。 下表說明可由 UCWA 元件所撰寫的事件。
  
|**事件識別碼**|**事件種類**|**摘要**|**原因與解決方式**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |參考  <br/> |UCWA 初始化  <br/> |不適用  <br/> 不適用  <br/> |
|20002  <br/> |出錯  <br/> |UCWA 在初始化期間遇到意外的例外狀況  <br/> |初始化時發生意外的錯誤  <br/> 檢查相關聯的事件記錄條目中的例外詳細資料，以判斷可能的原因  <br/> |
|20003  <br/> |出錯  <br/> |UCWA 遇到未處理的例外狀況  <br/> |發生未處理的例外狀況  <br/> 重新開機伺服器。 如果問題持續發生，請與產品支援人員聯繫  <br/> |
|20004  <br/> |出錯  <br/> |無法存取 HD 相片的 Exchange  <br/> |無法連線到 Exchange  <br/> 確認已提供與 Exchange 的連線  <br/> |
|20005  <br/> |參考  <br/> |已從無法存取 HD 相片的 Exchange 復原  <br/> |不適用  <br/> |
|20006  <br/> |出錯  <br/> |無法存取連絡人搜尋的 Exchange  <br/> |無法連線到 Exchange  <br/> 確認已提供與 Exchange 的連線  <br/> |
|20007  <br/> |參考  <br/> |已從 Exchange 中的搜尋連絡人復原失敗  <br/> |不適用  <br/> |
|20008  <br/> |警告  <br/> |嘗試訂閱超過每個應用程式允許的目前狀態訂閱  <br/> |嘗試訂閱超過每個應用程式允許的目前狀態訂閱  <br/> 檢查用戶端是否有不必要的訂閱  <br/> |
|20009  <br/> |警告  <br/> |每批次嘗試訂閱超過允許的目前狀態訂閱  <br/> |每批次嘗試訂閱超過允許的目前狀態訂閱  <br/> 檢查用戶端是否有不必要的訂閱  <br/> |
|20010  <br/> |出錯  <br/> |無法檢索 inband 資料  <br/> |無法檢索 inband 資料  <br/> 如果問題持續發生，請與產品支援人員聯繫  <br/> |
|20011  <br/> |出錯  <br/> |無法訂閱目前狀態  <br/> |無法訂閱目前狀態  <br/> 如果問題持續發生，請與產品支援人員聯繫  <br/> |
|20012  <br/> |出錯  <br/> |無法註冊端點  <br/> |無法註冊端點  <br/> 如果問題持續發生，請與產品支援人員聯繫  <br/> |
|20013  <br/> |出錯  <br/> |IM MCU 無法使用  <br/> |IM MCU 無法使用  <br/> 查看 IM MCU 是否正在執行  <br/> |
|20014  <br/> |參考  <br/> |已從無法連線至 IM MCU 的故障復原  <br/> |不適用  <br/> |
|20015  <br/> |出錯  <br/> |無法使用 AV MCU  <br/> |無法使用 AV MCU  <br/> 查看 AV MCU 是否正在執行  <br/> |
|20016  <br/> |參考  <br/> |從無法連線到 AV MCU 的故障復原  <br/> |不適用  <br/> |
|20017  <br/> |出錯  <br/> |無法使用 MCU  <br/> |無法使用 MCU  <br/> 查看是否正在執行 MCU  <br/> |
|20018  <br/> |參考  <br/> |從無法連線到 MCU 的方式復原  <br/> |不適用  <br/> |
|20019  <br/> |出錯  <br/> |資料 MCU 無法使用  <br/> |資料 MCU 無法使用  <br/> 查看資料 MCU 是否正在執行  <br/> |
|20020  <br/> |參考  <br/> |從無法連線到資料 MCU 的情況中復原  <br/> |不適用  <br/> |
|20021  <br/> |出錯  <br/> |無法加入 IM MCU  <br/> |無法加入 IM MCU  <br/> 查看 IM MCU 是否正在執行  <br/> |
|20022  <br/> |出錯  <br/> |無法加入 AV MCU  <br/> |無法加入 AV MCU  <br/> 查看 AV MCU 是否正在執行  <br/> |
|20023  <br/> |出錯  <br/> |無法以 MCU 進行加入  <br/> |無法以 MCU 進行加入  <br/> 查看是否正在執行 MCU  <br/> |
|20024  <br/> |出錯  <br/> |無法加入資料 MCU  <br/> |無法加入資料 MCU  <br/> 查看資料 MCU 是否正在執行  <br/> |
|20025  <br/> |出錯  <br/> |無法存取相片的 active directory  <br/> |無法使用 active directory 連線  <br/> 確定有可用的連線至 active directory  <br/> |
|20026  <br/> |參考  <br/> |已復原無法存取相片的 active directory  <br/> |不適用  <br/> |
|20027  <br/> |警告  <br/> |無法反序列化  <br/> |無法反序列化  <br/> 如果問題持續發生，請與產品支援人員聯繫  <br/> |
   

