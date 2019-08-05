---
title: 在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)。
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191533"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)
 
瞭解如何在商務用 Skype Server 中啟用或停用離線立即訊息 (IM)。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用離線立即訊息 (IM)

離線 IM 是內置於商務用 Skype 用戶端 (2016 C2R 組建16.0.6701.1000 或更新版本) 的用戶端功能, 可利用 Exchange Web 服務 (EWS) 從商務用 Skype 用戶端傳送郵件給使用者的 Exchange 信箱。 離線 IM 使用 Exchange Web 服務 (EWS) 從商務用 Skype 用戶端傳送離線郵件至收件者的信箱。 您必須提供 EWS, 才能傳送離線訊息給商務用 Skype 用戶端。 若要深入瞭解如何規劃立即訊息和目前狀態, 請參閱[規劃商務用 Skype Server 中的立即訊息和目前狀態](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> 如果使用者的信箱託管于 Exchange 內部部署中, 則需要商務用 Skype 用戶端 (2016 C2R 組建 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用離線 IM

1. 開啟商務用 Skype Server 管理命令介面。
    
2. 執行下列命令以啟用離線 IM。
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在商務用 Skype Server 2015 CU3 中, [EnableOfflineIM] 選項預設會設定為 [$True]。 若要停用, 請將此值設定為 [$False]。 
  
3. 執行下列命令, 確認已設定儲存離線 IM 的功能。
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>與 Exchange 進行離線 IM 整合

如果寄件者擁有可停用自動將離線訊息儲存至 [交談記錄] 資料夾 (EnableIMAutoArchiving = $false) 的用戶端原則, 就不會提供離線 IM。 沒有任何機制可以檢查收件者是否可以接收離線訊息。
  
如果您在同一個組織中傳送離線訊息, 這些郵件將會以電子郵件訊息的方式收到, 並將郵件分類至 IM。MissedConversation 並將包含在 Outlook 未接的**交談**資料夾中, 以及將在商務用 Skype 用戶端的 [最近的清單/交談記錄] 索引標籤中挑選的交談記錄。
  
如果您是從同盟組織傳送的離線郵件, 他們將會以電子郵件訊息 (不含 IM) 的形式收到。MisssedConversation 並不會在 [未接的交談] 或 [交談記錄] 資料夾中拾取。 
  
## <a name="troubleshooting"></a>疑難排解

當您收到並處理離線訊息時, 會出現兩分鐘的計時器。 如果離線訊息無法處理, 它們會出現在下列目錄中: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

主要的商務用 Skype ETL 記錄將包含離線訊息處理的相關資訊, 也是您要調查/疑難排解的最佳來源。 
  
> [!NOTE]
> 已報告離線訊息無法傳送的問題, 且 [草稿] 資料夾已填入郵件中。 此發生于 Exchange 內部部署信箱。 此問題已于6/14/2016 的所有 C2R 通道中修正。  
