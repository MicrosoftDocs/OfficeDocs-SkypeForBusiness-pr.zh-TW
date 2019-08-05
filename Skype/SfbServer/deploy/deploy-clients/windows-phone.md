---
title: 安裝並測試 Windows Phone 版商務用 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '摘要: 瞭解如何在 Windows Phone 上安裝並測試商務用 Skype。'
ms.openlocfilehash: 2796f1664ec20142bd8f9399830836c8c284ac67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188182"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>安裝並測試 Windows Phone 版商務用 Skype
 
**摘要:** 瞭解如何在 Windows Phone 上安裝並測試商務用 Skype。
  
Windows Phone 版商務用 Skype app 會將商務用 skype 目前狀態、立即訊息 (IM), 以及語音和視頻通話提供給 Windows 行動裝置。 使用 Lync 2013 的使用者會自動取得更新的應用程式, 或根據使用者的設定, 手動提示更新 app。 新的使用者可以從[Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901)下載。 Windows Phone 版商務用 Skype 應用程式僅適用于 Windows Phone 8.1 及更新版本。
  
在讓組織中的使用者下載應用程式之前, 您會想要執行下列測試, 以確定它已正確整合到您的環境中。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安裝商務用 Skype Windows Phone 8。1

1. 流覽至[Windows phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central), 將您的手機更新為 Windows phone 8.1。
    
2. 從您的手機移至 [**商店**], 然後搜尋 [**商務用 Skype**]。
    
3. 按一下 [**安裝**]。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>第一次登入商務用 Skype

1. 在 [**開始**] 畫面上, 向左滑動以查看已安裝的應用程式, 搜尋 Windows Phone 版商務用 Skype, 然後輕觸該圖示以開啟應用程式。
    
2. 輸入您的登入位址 (例如, user@domain.com) 和密碼, 然後按一下 [**完成**]。
    
     您可能會要求您輸入使用者名稱和登入位址。 [使用者名稱] 是您用來登入組織網路的使用者名稱, 可以是 user@domain.com 或 [域 \ 使用者]。
    
3. 在 [**客戶經驗改進計畫**] 畫面上, 按一下 [**加入**], 將有關 app 問題和使用方式的匿名資料傳送至 Microsoft, 或 [**不感謝**] (如果您不希望參與)。
    
4. 在 [**永不錯過您的公司電話**] 畫面上, 輸入您的行動電話號碼及國家/地區代碼。 當 Windows Phone 版商務用 Skype 無法使用 Wi-fi 或行動電話資料網路進行音訊或視頻通話時, 系統會自動呼叫此號碼, 並連接到通話的音訊部分。
    
5. 按一下 **[下一步]** 並查看通知和電話簿存取設定:
    
   - **推播通知**當您收到新的 IM 或通話時, 會收到通知。 正常**** (建議使用)。
    
     > [!IMPORTANT]
     > 如果您關閉此設定, 除非 app 是作用中, 否則您將不會收到 Im、通話或其他 Windows Phone 版商務用 Skype 通知。 
  
   - **允許存取電話簿**當您在 Windows Phone 版商務用 Skype 中搜尋連絡人時, 搜尋您行動電話上的連絡人。
    
6. 按一下 **[下一步]** 以開始使用 Windows Phone 版商務用 Skype。
    
    [需要協助您登入嗎？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>驗證行動用戶端安裝

在您設定用戶端並成功登入之後, 請使用下列測試來確認您在行動裝置上安裝的是 Windows Phone 版商務用 Skype 正常運作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>在公司目錄中搜尋連絡人

1. 在 [連絡人] 清單中, 按一下 [**搜尋**]。
    
2. 搜尋僅存在於全域通訊清單中的連絡人。
    
3. 確認連絡人名稱出現在搜尋結果中。
    
### <a name="test-instant-messaging-and-presence"></a>測試立即訊息和目前狀態

1. 在連絡人清單中, 輕觸連絡人。
    
2. 在連絡人卡片中, 輕觸 [立即訊息 (IM)] ![商務用 Skype 中立即訊息的圖示](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)圖示.
    
3. 確認 IM 視窗出現, 而且您可以輸入並傳送即時消息。
    
### <a name="test-dial-out-conferencing"></a>測試撥出式會議

1. 在 Outlook 中, 排程商務用 Skype 會議。
    
2. 在您的 Windows Phone 上, 開啟會議邀請。
    
3. 按一下會議中要加入的連結。
    
4. 從會議服務接聽通話, 並確認您已連線到會議音訊。
    
### <a name="test-push-notifications"></a>測試推播通知

1. 針對此測試選取兩個不同的使用者帳戶。 
    
2. 在使用者 A 的 Windows Phone 上, 使用使用者 A 的帳戶登入 Windows Phone 版商務用 Skype。
    
3. 在裝置上開啟另一個應用程式。
    
4. 在其他用戶端 (例如桌面用戶端), 使用使用者 B 的帳戶登入商務用 Skype。
    
5. 從使用者 B 傳送 IM 給使用者 A。
    
6. 確認 IM 通知出現在使用者 A 的行動裝置上。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>從 Windows Phone 中移除商務用 Skype

若要從行動裝置移除 Windows Phone 版商務用 Skype 應用程式: 
  
1. 從 [開始] 畫面滑動以查看應用程式清單。 
    
2. 敲擊並按住 Windows Phone 版商務用 Skype 應用程式, 然後選取 [**卸載**]。
    


