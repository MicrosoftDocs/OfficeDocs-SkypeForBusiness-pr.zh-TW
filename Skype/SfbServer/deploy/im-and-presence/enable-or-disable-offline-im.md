---
title: '啟用或停用商務用 Skype Server 中的離線立即訊息 (IM) '
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
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 瞭解如何啟用或停用商務用 Skype Server 中的離線立即訊息 (IM) 。
ms.openlocfilehash: 31c27a84965e3b75515c206f8dc984b2eaa178eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578037"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的離線立即訊息 (IM) 
 
瞭解如何啟用或停用商務用 Skype Server 中的離線立即訊息 (IM) 。
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>啟用商務用 Skype Server 中的離線立即訊息 (IM) 

離線 IM 是內置於商務用 Skype client (2016 C2R 組建16.0.6701.1000 或更高版本) 的用戶端功能，可利用 Exchange 的 Web 服務 (EWS) ，將郵件從商務用 Skype 用戶端傳送至使用者的 Exchange 信箱。 離線 IM 使用 Exchange Web 服務 (EWS) 從商務用 Skype 用戶端將離線郵件傳送至收件者的信箱。 EWS 必須可供商務用 Skype 用戶端使用，以供傳送離線郵件。 若要深入瞭解規劃立即訊息和目前狀態，請參閱[在商務用 Skype Server 中規劃立即訊息和目前狀態](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
> [!NOTE]
> 如果使用者的信箱主控于 Exchange On-Premises，商務用 Skype 用戶端 (2016 C2R 組建 16.0.6920.1000) 是必要的 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的離線 IM

1. 開啟 [商務用 Skype Server 管理命令介面]。
    
2. 執行下列命令以啟用離線 IM。
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > 在商務用 Skype Server 2015 CU3 中，EnableOfflineIM 選項會預設設定為 $True。 若要停用，請將此值設為 $False。 
  
3. 執行下列命令，以確認已設定儲存離線 IM 的功能。
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>與 Exchange 的離線 IM 整合

如果寄件者的用戶端原則停用自動儲存至 [交談記錄] 資料夾中的離線郵件，則不能使用離線 IM (EnableIMAutoArchiving = $false) 。 沒有任何機制可檢查收件者是否可以接收離線郵件。
  
針對相同組織內傳送的離線郵件，它們會以 IM 郵件類別的電子郵件訊息的形式接收。 MissedConversation 並將會包含 Outlook 在商務用 Skype 用戶端的 [最近的清單/交談記錄] 索引標籤中 **的 [交談記錄] 資料夾中**。
  
對於從同盟組織傳送的離線郵件，他們會以電子郵件訊息方式接收，但不會收到 MisssedConversation，也不會在未接的交談或交談記錄資料夾中領取。 
  
## <a name="troubleshooting"></a>疑難排解

當離線郵件接收及處理時，會有兩分鐘的計時器。 如果離線訊息無法處理，它們就會出現在下列目錄中： 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

主要商務用 Skype ETL 記錄會包含離線郵件處理的相關資訊，也是您要調查/疑難排解的最佳來源。 
  
> [!NOTE]
> 已報告「離線訊息傳送失敗」和「草稿」資料夾填滿郵件的問題。 使用 Exchange On-Premises 信箱時發生此錯誤。 從6/14/2016 起，所有 C2R 通道都已修復此問題。  
