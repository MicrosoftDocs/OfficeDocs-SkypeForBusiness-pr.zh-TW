---
title: UCWA 商務用 Skype Server 中的事件
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
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 摘要：瞭解商務用 Skype Server 中的整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: e4f36747ec75085785aefcd323f8fd6671bbbfe8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399637"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>UCWA 商務用 Skype Server 中的事件
 
**總結：** 瞭解商務用 Skype Server 中的整合通訊 Web API (UCWA) 。
  
商務用 Skype Server 使用整合通訊 Web API (UCWA) 出於許多目的，從存取 Microsoft Exchange 以進行連絡人搜尋，以更新行動用戶端的狀態。
  
UCWA 會將操作行為記錄撰寫成事件種類的資訊、警告和錯誤。 下表說明 UCWA 元件可寫入的事件。
  
|**事件識別碼**|**事件類型**|**摘要**|**原因和解決方法**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |參考  <br/> |UCWA 初始化  <br/> |不適用  <br/> 不適用  <br/> |
|20002  <br/> |錯誤  <br/> |UCWA 在初始化期間遇到意外的例外狀況  <br/> |初始化時發生未預期的錯誤  <br/> 檢查相關事件記錄檔專案中的例外狀況詳細資料，以判斷可能的原因  <br/> |
|20003  <br/> |錯誤  <br/> |UCWA 發生未處理的例外狀況  <br/> |發生未處理的例外狀況  <br/> 重新啟動伺服器。 如果問題仍然存在，請與產品支援人員聯繫  <br/> |
|20004  <br/> |錯誤  <br/> |無法存取 HD 相片的 Exchange  <br/> |無法使用 Exchange 連接  <br/> 請確定有 Exchange 的連線  <br/> |
|20005  <br/> |參考  <br/> |從存取 HD 相片的 Exchange 復原失敗  <br/> |不適用  <br/> |
|20006  <br/> |錯誤  <br/> |無法存取連絡人搜尋的 Exchange  <br/> |無法使用 Exchange 連接  <br/> 請確定有 Exchange 的連線  <br/> |
|20007  <br/> |參考  <br/> |從 Exchange 中的搜尋連絡人復原失敗  <br/> |不適用  <br/> |
|20008  <br/> |警告  <br/> |嘗試訂閱超過每個應用程式允許的顯示狀態訂閱  <br/> |嘗試訂閱超過每個應用程式允許的顯示狀態訂閱  <br/> 檢查用戶端是否有不必要的訂閱  <br/> |
|20009  <br/> |警告  <br/> |嘗試訂閱每批次允許的目前狀態訂閱  <br/> |嘗試訂閱每批次允許的目前狀態訂閱  <br/> 檢查用戶端是否有不必要的訂閱  <br/> |
|20010  <br/> |錯誤  <br/> |無法取得 inband 資料  <br/> |無法取得 inband 資料  <br/> 如果問題仍然存在，請與產品支援人員聯繫  <br/> |
|20011  <br/> |錯誤  <br/> |無法訂閱目前狀態  <br/> |無法訂閱目前狀態  <br/> 如果問題仍然存在，請與產品支援人員聯繫  <br/> |
|20012  <br/> |錯誤  <br/> |無法註冊端點  <br/> |無法註冊端點  <br/> 如果問題仍然存在，請與產品支援人員聯繫  <br/> |
|20013  <br/> |錯誤  <br/> |IM MCU 無法使用  <br/> |IM MCU 無法使用  <br/> 查看 IM MCU 是否正在執行中  <br/> |
|20014  <br/> |參考  <br/> |從無法連線至 IM MCU 的失敗復原  <br/> |不適用  <br/> |
|20015  <br/> |錯誤  <br/> |無法使用 AV MCU  <br/> |無法使用 AV MCU  <br/> 查看 AV MCU 是否正在執行中  <br/> |
|20016  <br/> |參考  <br/> |從無法連線至 AV MCU 的失敗復原  <br/> |不適用  <br/> |
|20017  <br/> |錯誤  <br/> |無法使用 MCU  <br/> |無法使用 MCU  <br/> 查看是否正在執行 MCU  <br/> |
|20018  <br/> |參考  <br/> |從無法以 MCU 形式連線的方式復原  <br/> |不適用  <br/> |
|20019  <br/> |錯誤  <br/> |資料 MCU 無法使用  <br/> |資料 MCU 無法使用  <br/> 查看資料 MCU 是否正在執行中  <br/> |
|20020  <br/> |參考  <br/> |從無法連線至資料 MCU 的失敗復原  <br/> |不適用  <br/> |
|20021  <br/> |錯誤  <br/> |無法加入 IM MCU  <br/> |無法加入 IM MCU  <br/> 查看 IM MCU 是否正在執行中  <br/> |
|20022  <br/> |錯誤  <br/> |無法加入 AV MCU  <br/> |無法加入 AV MCU  <br/> 查看 AV MCU 是否正在執行中  <br/> |
|20023  <br/> |錯誤  <br/> |無法以 MCU 形式加入  <br/> |無法以 MCU 形式加入  <br/> 查看是否正在執行 MCU  <br/> |
|20024  <br/> |錯誤  <br/> |無法加入資料 MCU  <br/> |無法加入資料 MCU  <br/> 查看資料 MCU 是否正在執行中  <br/> |
|20025  <br/> |錯誤  <br/> |無法存取相片的 active directory  <br/> |無法使用 active directory 的連線  <br/> 確定可以使用 active directory 的連線  <br/> |
|20026  <br/> |參考  <br/> |從無法存取相片的 active directory 復原  <br/> |不適用  <br/> |
|20027  <br/> |警告  <br/> |無法反序列化  <br/> |無法反序列化  <br/> 如果問題仍然存在，請與產品支援人員聯繫  <br/> |
   

